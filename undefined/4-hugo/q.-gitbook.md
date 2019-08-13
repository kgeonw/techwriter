# Q. Gitbook에서 날라가버린 데이터들은 어떻게 복구할까



Gitbook과 연동한 Github 페이지가 내 계정으로 접속해도 계속 빈 페이지만 나와 처음부터 다시 시작하고자 Github에서 repository를 과감히 삭제했다.

![Settings &amp;gt; Danger Zone &amp;gt; Delete this repository](../../.gitbook/assets/image%20%284%29.png)

그런데 다음 날 로그인했더니, Gitbook에 내 글들이 모두 사라진게 아닌가.

두두둥.

github에서 복구는 어려운 것 같고 \(복구 방법이 있을지 모르겠지만 아직 이해하기 힘들고 너무 단계가 복잡하다.\)

Gitbook 메뉴를 뒤졌다.

![](../../.gitbook/assets/image%20%285%29.png)

다행히 Archive에서 나의 활동 로그들이 다 남았고, 나는 특정 게시글을 작성/편집했던 순간으로 들어와 Merge할 수 있었다.

![](../../.gitbook/assets/image%20%286%29.png)

그리고 분실한 카테고리는... 

다른 레파지토리에 있던 소스를 데스크탑에 다운로드 받아 로컬저장소와 직접 복- 붙.

![](../../.gitbook/assets/image%20%282%29.png)

카테고리 하나가 날라서 그 카테고리 폴더만 복사하고, Summery.md에서 목차만 바꿔주면 될 줄 알았는데 이미지 파일의 갯수가 달랐다. 추가분만 복-붙하면 될줄 알았는데 서로 넘버링이 달랐다. 

같은 파일 이름을 가진 이미지 파일이 서로 다른 이미지 였던 것이다.

포기하고, 새로 작성.

다행히 모바일 폰에서는 내 깃북 페이지가 살아있어 텍스트만 복사해두었다.

![](../../.gitbook/assets/image%20%2839%29.png)

그리고 Gitbook과 Github을 동기화 하려고, 원격 저장소를 연결했다.

![](../../.gitbook/assets/image%20%287%29.png)

원격저장소가 알고 있는 저장소를 모두 알려준다길래

```text
$git remote -v
```

다음 명령어를 쳤더니, 오잉 저 밑에 두 개는 뭐지?

구글링 해서 원격저장소를 초기화 하고 다시 내 레파지토리를 연결하였다.

```text
$ git remote remove origin
$ git remote origin [url]
```

![](../../.gitbook/assets/image%20%2810%29.png)



