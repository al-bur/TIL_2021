## [210316] [Django - ModelForm](https://docs.djangoproject.com/en/3.1/topics/forms/modelforms/)

### 1. 주제

---

먼저, Django는 `MTV` 디자인 패턴을 따른다. 여기서 사용자(Client)가 웹페이지 상에서 정보를 입력하면 이 정보를 처리해주는 로직을 짜야한다. Django에서는 `Template`인 `html`을 구성할 때 이 정보를 전달해주기 위해서 `<form>`이라는 시맨틱 태그를 사용해준다. 일반적으로, `<form>`내에 `input` 과 `label`태그들을 직접 입력해서 `html`을 작성하고는 한다. 하지만 Django에서는 `forms.py`를 따로 생성해줘서 생성된 클래스를 가져다가 `html`에서 사용해준다. 특히, Django에서 제공하는 `ModleForm`에 대해서 공부한 것을 정리해보려고 한다!

<br>

### 2. ModelForm

---

프로젝트내에서 이미 생성된 `model.py`에서 정의된 `model 클래스`를 이용해서 `form`을 생성하게 도움을 주는 Django내 class를 `ModelForm`이라고 보면된다. 기존의 `form` 클래스를 이용해서도 따로 field들을 생성해주고 사용할 수 있지만, 그 field들이 기존에 존재하던 `model 클래스`의 field들과 같다면 `굳이 다시 만들 필요가 있을지 의문이다.`

이러한 코드의 중복 사용을 방지하기 위해서는 `ModelForm`을 사용해주면 된다.

<br>

```python
# forms.py
from myapp.models import Article

# Create the form class.
class ArticleForm(ModelForm):
	class Meta:
	model = Article
	fields = ['pub_date', 'headline', 'content', 'reporter']

# Creating a form to add an article.
form = ArticleForm()

# Creating a form to change an existing article.
article = Article.objects.get(pk=1)
form = ArticleForm(instance=article)
```

<br>

### 3. ModelForm 사용 예시

#### 3.1 사용자(client)에게 정보를 입력할 수 있는 form 제공

---

`ModelForm`은 여러 기능이 있겠지만, 사용자에게 정보를 받아올 수 있게 비어있는 `form`을 제공하는 기능을 먼저 살펴보려고 합니다. `forms.py`와 `views.py`를 통해서 기능을 설명하려고 한다.

<br>

```python
# forms.py
from django import forms
from .models import Article # Article이 models.py에 class로 선언되어있는 상황

class ArticleForm(forms.ModelForm):
    class Meta:
        model = Article
        # form이 Article 클래스가 가지고 있는 fields들을 다 가지게 됨
        # 기존에 있던 models.py내 Article 클래스의 정보를 가지고 오는 것이므로 코드 재사용
        fields = '__all__'
        # fields = ['title', 'content',]
```

<br>

```python
# views.py
from django.shortcuts import render
from .forms import ArticleForm

def create(request):
    # ArticleForm 클래스의 form이라는 인스턴스 생성
    # form은 비어있는 form을 가지게 된다.
    form = ArticleForm()
    # context에 담아서 render
    context = [
		'form': form,
    ]
    return render(request, 'articles/create,html', context)
```

<br>

#### 3.2 기존에 있던 데이터를 불러와 수정하고 저장

---

위의 상황처럼 사용자(client)로부터 정보를 입력 받아올 수 있게 비어있는 `form`을 제공할 수도 있지만 미리 저장된 정보를 불러와서 정보를 수정하고 `Update`할 때도 `ModelForm`을 사용해줄 수 있다.

<br>

```python
# forms.py는 위와 동일
# views.py
from .forms import ArticleForm
from .models import Article

# primary_key는 db에 데이터가 저장될 때 저절로 생성되는 key ( ex) 1,2,3,4,5 )
def update(request, primary_key):
    # 기존의 데이터 중 인자로 받은 primary_key와 같은 값을 가진 데이터를 article에 할당
	article = Article.objects.get(pk=primary_key)
    if request.method == 'POST':
        # 기존 데이터 update 진행
        form = ArticleForm(request.POST, instance=article)
        # 유효성 검사 진행
        if form.is_valid():
			# 유효하면 저장
            form.save()
            return redirect(다른페이지)
    else:
        form = AritcleForm(instance=article)
    # is_valid()에서 false가 나오기도 하기 때문에 indentation 아래 방식으로 진행
    context = [
        'form': form,
        'article': article,
    ]
    return render(request, 다른경로, context)

```

<br>

### 4. 정리

---

이렇게 Django에서는 데이터 모델링을 통해 `models.py`에 생성해놓았던 클래스를 이용해서 사용자(client)에게 정보를 입력받을 수 있는 `form`을 위해 `ModelForm`을 제공해준다. 
