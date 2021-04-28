# [210428] Django - DRF_Serializers

### 1. DRF

DRF는 `Django REST Framework`를 의미하여  RESTful한 API를 쉽게 만들 수 있도록 해준다. 

https://www.django-rest-framework.org/

위의 사이트에 가면 DRF에 대해서 자세하게 알 수 있습니다!

Django를 이용해서 손수 JSON 포맷을 만들거나 내장 라이브러리를 사용해도 되지만 `DRF`를 통하면 훨씬 더 편하게 API를 만들 수 있어서 많은 사람들이 사용중이다.

DRF에서 특히 `Serializers`에 대해서 사용해보고 공부해본 것을 정리해보았다!

<br>

### 2. Serializers

---

API를 제공하기 위해서는 대부분 `JSON`형태로 클라이언트 서버에 보내서 클라이언트 서버에서 `JSON`을 가지고 렌더링 해주는 것이 최신 웹의 트렌드라고 볼 수 있다. 이렇게 Django에서 처리되는 데이터를 `JSON` 형태로 손쉽게 변환해 줄 수 있게 도와주는 것이 `Serializers`라고 보면된다.

Django에서 직접 렌더링을 하려면 `ModelForm`을 이용했던 것처럼 `JSON` 형태로 Response를 보내주기 위해서 `Serializers`를 이용해주는데, 먼저 `serializers.py`를 생성해서 `serializers`를 선언해줘야한다.

<br>

### 3. 코드

---

**먼저, Serializers에서 참조할 model을 선언해줘야한다**

```python
# models.py
class Article(models.Model):
    title = models.CharField(max_length=100)
    content = models.TextField()
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)
```

<br>

**Serializers 선언** - `ModelForm`을 선언할 때 `model = Article`을 해주는 것처럼 `Serializers`를 선언할 때도 동일하게 `model`을 참조한다.

```python
from rest_framework import serializers
from .models import Article

class ArticleSerializer(serializers.ModelSerializer):
    class Meta:
        model = Article
        fields = '__all__'
```

<br>

**선언한 Serializers 활용** - Response를 보내주는 데 serializer를 통해서 변환한 데이터(serializer.data)를 보내준다.

```python
from django.shortcuts import get_list_or_404
from rest_framework import status
from rest_framework.response import Response
from rest_framework.decorators import api_view
from .models import Article
from .serializers import ArticleListSerializer, ArticleSerializer


# api_view 데코레이터는 필수이다. 없으면 error
@api_view(['GET', 'POST'])
def article_list(request):
    if request.method == 'GET':
        articles = get_list_or_404(Article)
        # many=True로 설정해줘야함 (다수 데이터)
        serializer = ArticleListSerializer(articles, many=True)
        # serialized된 데이터는 인자로 무조건 줘야함
        return Response(serializer.data)
    elif request.method == 'POST':
        serializer = ArticleSerializer(data=request.data)
        if serializer.is_valid(raise_exception=True):
            serializer.save()
            return Response(serializer.data, status=status.HTTP_201_CREATED)
```

