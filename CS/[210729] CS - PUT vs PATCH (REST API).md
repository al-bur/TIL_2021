# [210729] CS - PUT vs PATCH (REST API)

**REST API란**

> REST는 Representational State Transfer라는 용어의 약자로서 2000년도에 로이 필딩 (Roy Fielding)의 박사학위 논문에서 최초로 소개되었습니다. 로이 필딩은 HTTP의 주요 저자 중 한 사람으로 그 당시 웹(HTTP) 설계의 우수성에 비해 제대로 사용되어지지 못하는 모습에 안타까워하며 웹의 장점을 최대한 활용할 수 있는 아키텍처로써 REST를 발표했다고 합니다. - [출처](https://meetup.toast.com/posts/92)

> HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고, HTTP Method(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 CRUD Operation을 적용하는 것을 의미한다. [출처](https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html)

<br>

![REST API METHOD](https://user-images.githubusercontent.com/64825713/127438891-22314a6b-f965-4d24-8cf1-72e794821388.png)


<br>

### PUT vs PATCH

---

오늘의 주제는 `REST API`의 대표적인 메서드중  `PUT`메서드와 이와 비슷한 역할을 하는 `PATCH` 메서드에 관한 것입니다.  `PUT` 메서드는 리소스를 수정하고 싶을 때 보내는 요청이므로 `PATCH` 또한 같은 목적의 요청입니다.

<br>

**그렇다면 무엇이 다를까요?**

`PUT`은 리소스의 모든 정보를 변경할 때 쓰이고

`PATCH`는 리소스의 일부 정보를 변경할 때 쓰입니다.

<br>

| 회원(member) | 1      |
| ------------ | ------ |
| 이름(name)   | 이참외 |
| 나이(age)    | 16     |
| 성별(gender) | Male   |

<br>

`PUT 예시`

```javascript
// PUT/member/1
{
	name: 'kim' 
}
```

<br>

위처럼 `name`에 대한 정보만을 보내게 되면, DB상에는 `name`에 대한 변경된 정보외에는 `null` 값으로 대체가 되버린다.

| 회원(member) | 1    |
| ------------ | ---- |
| 이름(name)   | kim  |
| 나이(age)    |      |
| 성별(gender) |      |

<br>

`PATCH 예시`

```javascript
//PATCH/member/1

{
	name: 'kim'
}
```

<br>

하지만, `PATCH`를 사용하게 되면, `name`에 대한 정보만을 변경시켜준다.

| 회원(member) | 1    |
| ------------ | ---- |
| 이름(name)   | kim  |
| 나이(age)    | 16   |
| 성별(gender) | Male |



**그렇기 때문에, 리소스의 일부를 수정할 때는 `PATCH`를 사용해주고 전체를 수정할 때는 `PUT`을 사용해주면 된다.**
