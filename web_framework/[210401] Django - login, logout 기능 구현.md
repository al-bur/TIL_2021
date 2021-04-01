## [210401] Django - login, logout

### 1. login 구현

---

```python
# accounts/views.py 
from django.contrib.auth import login as auth_login
from django.contrib.auth.forms import AuthenticationForm
from django.views.decorators.http import require_http_methods

@require_http_methods(['GET', 'POST'])
def login(request):
    if request.method == 'POST':
        form = AuthenticationForm(data=request.POST)
        if form.is_valid():
            # request.user를 사용하면 로그인 되어있지 않은 상황에서는 불가능
            auth_login(request, form.get_user())
            return redirect(request.GET.get('next') or 'articles:index')
    else:
        form = AuthenticationForm()
    context = {
        'form': form,
    }
    return render(request, 'accounts/form.html', context)
```

- 기본적으로 장고가 제공해주는 `AuthenticationForm()`을 사용하여 사용자들이 로그인 할 수 있는 form을 제공해준다.
- 로그인 되어 있지 않은 사용자가 로그인을 시도할 때는 `GET` 방식으로 요청이 들어오기 때문에 `AuthentificationForm()`을 서버에서 제공해준다.
- 이후, 사용자는 로그인 정보를 입력하여 로그인을 시도한다.
- 입력한 정보를 `form.is_valid()`를 통해 유효성 검사를 한후 `auth_login`을 통해서 session을 저장하게 되고 로그인에 성공한다.
- `redirect(request.GET.get('next'))`를 작성해준 이유는 사용자가 views decorator인 `@login_required`에 걸리게 되면 login을 하는 페이지로 이동이 되어진다. `url`내부  `next` 뒤에 원래 가려고 했던 경로를 보관해놓았다가  login을 진행하고 나면 사용자를 해당 경로에 보내주기 위해 `get('next')`를 사용해주었다.



<br>

### 2. logout 구현

---

```python
from django.contrib.auth import logout as auth_logout

def logout(request):
    if request.method == 'POST':
        auth_logout(request)
    return redirect('articles:index')
```

- 로그아웃 구현은 로그인 구현보다 쉬운 편이다.
- Django에서 제공해주는 `logout`을 사용해서 진행
- session을 삭제해주면서 logout을 진행한다.
- 로그아웃을 하면 기본 페이지(index)로 돌려보내준다.
