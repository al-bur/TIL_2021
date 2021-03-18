## [210318] [Django - managing static files(1)](https://docs.djangoproject.com/en/3.1/topics/forms/modelforms/)

### 1. what is static file?

---

정적 파일이라고 하며 JavaScript, CSS, image 등과 같이 개발자가 사전에 미리 서버에 저장 해둔 파일들을 말합니다. 웹페이지를 개발할 때 이 정적 파일들을 프로젝트 단위로 관리하기도 하고 앱 단위로 관리하기도 한다. 

**Django에서는 static file을 어떻게 관리하는 지 code를 보며 설명해보겠다**

<br>

### 2. Managing static files

---

```python
STATIC_URL = '/static/'
```

장고를 통해서 프로젝트를 생성하였다면 settings.py에 이미 `STATIC_URL`이 설정되어 있을 것이다. 이 설정을 통해서 `static` 파일에 대한 URL의 고정값이 설정된다. 예를 들어, `TEMPLATES` 내 `html`에서 `{% static '파일경로' %}`은 `/static/파일경로`로 최종적으로 변경이 되어 해당 경로를 참조할 수 있게 된다.

<br>

```python
STATICFILES_DIRS = [
    BASE_DIR / '프로젝트이름' / 'staticfiles',
]
```

다음은 `STATICFILES_DIRS`이다. `STATIC_URL`을 사용해주면 각 app 밑에 존재하는 `static`을 자동으로 참조할 수 있다. 하지만 app이 아닌 프로젝트 밑에 존재하는 `static` 파일들은 자동으로 참조를 해줄 수 없습니다. 그래서  `STATICFILES_DIRS`를 통해서 해당 경로에도 static files이 있으니 참조해라라고 알려줄 수 있습니다.

<br>

```python
STATIC_ROOT = BASE_DIR / '폴더이름'
```

마지막으로 `STATIC_ROOT`이다. 해당 프로젝트내에 존재하는 모든 static file들을 해당 경로에 `폴더이름`과 동일한 이름을 가진 폴더를 생성해서 그 폴더에 모아놓겠다는 뜻이다. 이는 추후 `collectstatic`을 통해 배포를 위한 준비를 할 수 있다. 

조사에 따르면 `STATIC_ROOT`는 개발 단계에서 사용되기 보다는 배포 단계에서 사용되는 것이라고 한다.

<br>

### 3. 기타
---

[stackoverflow - what is difference between STATIC_ROOT and STATICFILES_DIRS](https://stackoverflow.com/questions/24022558/differences-between-staticfiles-dir-static-root-and-media-root)

```python
STATIC_URL = '/static/'

if not DEBUG: 
    STATIC_ROOT = '/home/django/www-data/site.com/static/'

STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'static/'),
]
```

 -> 개발 과정에서는 `STATIC_ROOT`를 쓰지 않고 `STATICFULES_DIRS`만 사용하고 추후 배포시 `STATIC_ROOT`도 사용한다고 이해하면 될 것 같다. 

