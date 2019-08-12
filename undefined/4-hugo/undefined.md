# Gitbook - Github 연동

Gitbook로 블로그를 작성하긴 했는데 Hugo 테마를 적용하고 커밋을 해도 왜 서버에 접근하지 못할까?

당연했던 것.

Github와 Gitbook연동을 하지 않았다.

[아보느 님의 유튜브 강의](https://youtu.be/e9DMxI_XOPI)를 통해 쉽게 해결했다.

![](../../.gitbook/assets/image%20%2828%29.png)

Gitbook으로 글쓰기 를 선택 후,

![](../../.gitbook/assets/image%20%2835%29.png)

![](../../.gitbook/assets/image%20%2825%29.png)

연동을 했더니 드디어 Gitbook으로 썼던 컨텐츠들이 Github에 보이기 시작했다.



이번엔 로컬로 가져와볼까?

![](../../.gitbook/assets/image%20%2813%29.png)

Github의 blog repository에 있던 데이터들도 내 로컬 pc로 들어왔다.

![](../../.gitbook/assets/image%20%2823%29.png)

그런데 아직도 개념이 잘 서지 않는다.

Hugo를 사용하기 위해 repository를 blog랑 naraewool.io.git을 만들었는데 master를 클론해야하는지 Sub을 클론해야하는지..



[Integerous 님의 블로그](https://ryan-han.com/post/etc/creating_static_blog/)에 따르면,

* 하나는 Hugo의 컨텐츠와 소스파일들을 포함할 `<YOUR-PROJECT>` 저장소 생성 \(나의 경우 `blog`라는 이름으로 생성\)
* 다른 하나는 렌더링된 버전의 Hugo 웹사이트를 포함할 `<USERNAME>.github.io` 저장소 생성 \(`integerous.github.io`\)

그럼 마스터에 넣으면 되는게 맞는 것 같기도 하

