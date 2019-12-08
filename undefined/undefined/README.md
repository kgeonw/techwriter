# \[Project\] Gitbook을 이용한 블로그 만들기

## 블로그 제작에 Gitbook을 선택한 이유

**Plugin**: In general, the plugin system no longer exists. However, important plugins have become first-class features in the new version. Here is a non-exhaustive list:

* Syntax highlighting \(`prism`\)
* Image captions \(`image-captions`\)
* Heading anchors \(`headings`\)
* Easily selecting code snippet content \(`copy-code`\)
* Algolia's search \(`algolia`, `lunr`\)
* Google Analytics \(`ga`\)
* Edit on GitHub button \(`github`, `github-buttons`\)
* Page's table of content \(`atoc`, `toc`\)
* Code block filename/tabs \(`codeblock-filename`, `code-tabs`\)

The syntax of some plugins are still supported in Markdown \([see the list]()\).

Some plugins are being considered to be implemented in the future as well. Here is an updated list of those plugins:

* Support for math \(`mathjax` or `katex` plugins\)

 Open a feature request in [Canny](https://gitbook.canny.io/feature-requests) if you want to see a plugin's feature implemented in GitBook

## Gitbook - Github 연동하기

Gitbook로 블로그를 작성하긴 했는데 Hugo 테마를 적용하고 커밋을 해도 왜 서버에 접근하지 못할까?

당연했던 것.

Github와 Gitbook연동을 하지 않았다.

아보느 님의 유튜브 강의를 통해 쉽게 해결했다.

![](../../.gitbook/assets/image%20%2837%29.png)

![](../../.gitbook/assets/image%20%2845%29.png)

![](../../.gitbook/assets/image%20%2834%29.png)

연동을 했더니 드디어 Gitbook으로 썼던 컨텐츠들이 Github에 보이기 시작했다.



### 번외: 나의 뻘짓 

여기서부터 또 혼란의 시대. \(혹시라도 이걸 보고 따라 하시는 분이 계시다면 이 부분은 과감히 넘어가 주세요.\)

이번엔 작성한 컨텐츠를 로컬로 가져와볼까?

![](../../.gitbook/assets/image%20%2818%29.png)

Github의 blog repository에 있던 데이터들도 내 로컬 pc로 들어왔다.

![](../../.gitbook/assets/image%20%2830%29.png)

그런데 아직도 개념이 잘 서지 않는다.

Hugo를 사용하기 위해 repository를 blog랑 naraewool.io.git을 만들었는데 master를 클론해야하는지 Sub을 클론해야하는지..



[Integerous 님의 블로그](https://ryan-han.com/post/etc/creating_static_blog/)에 따르면,

* 하나는 Hugo의 컨텐츠와 소스파일들을 포함할 `<YOUR-PROJECT>` 저장소 생성 \(나의 경우 `blog`라는 이름으로 생성\)
* 다른 하나는 렌더링된 버전의 Hugo 웹사이트를 포함할 `<USERNAME>.github.io` 저장소 생성 \(`integerous.github.io`\)

그럼 마스터에 넣으면 되는게 맞는 것 같기도 하고.

점점 어려워진다.



## 깃에서 데이터 복구하기 

Gitbook과 연동한 Github 페이지가 내 계정으로 접속해도 계속 빈 페이지만 나와 처음부터 다시 시작하고자 Github에서 repository를 과감히 삭제했다.

![Settings &amp;gt; Danger Zone &amp;gt; Delete this repository](../../.gitbook/assets/image%20%284%29.png)

그런데 다음 날 로그인했더니, Gitbook에 내 글들이 모두 사라진게 아닌가.

두두둥.

github에서 복구는 어려운 것 같고 \(복구 방법이 있을지 모르겠지만 아직 이해하기 힘들고 너무 단계가 복잡하다.\)

Gitbook 메뉴를 뒤졌다.

![](../../.gitbook/assets/image%20%285%29.png)

다행히 Archive에서 나의 활동 로그들이 다 남았고, 나는 특정 게시글을 작성/편집했던 순간으로 들어와 Merge할 수 있었다.

![](../../.gitbook/assets/image%20%287%29.png)

그리고 분실한 카테고리는... 

다른 레파지토리에 있던 소스를 데스크탑에 다운로드 받아 로컬저장소와 직접 복- 붙.

![](../../.gitbook/assets/image%20%282%29.png)

카테고리 하나가 날라서 그 카테고리 폴더만 복사하고, Summery.md에서 목차만 바꿔주면 될 줄 알았는데 이미지 파일의 갯수가 달랐다. 추가분만 복-붙하면 될줄 알았는데 서로 넘버링이 달랐다. 

같은 파일 이름을 가진 이미지 파일이 서로 다른 이미지 였던 것이다.

포기하고, 새로 작성.

다행히 모바일 폰에서는 내 깃북 페이지가 살아있어 텍스트만 복사해두었다.

![](../../.gitbook/assets/image%20%2851%29.png)

그리고 Gitbook과 Github을 동기화 하려고, 원격 저장소를 연결했다.

![](../../.gitbook/assets/image%20%288%29.png)

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

![](../../.gitbook/assets/image%20%2814%29.png)



## Q. 왜 내 Github 주소로 Gitbook 블로그가 보이지 않을까?

github의 기본 주소인 _username_.github.io/_project name_을 치면 내 gitbook 페이지가 보일 거라 생각했다.

gitbook과 github을 성공적으로 연동해서 github에는 컨텐츠들이 잘 보이는

![](../../.gitbook/assets/image%20%281%29.png)

_username_.github.io/_project name_에 접속하면 메인 페이지가 gitbook에서 설정한 페이지가 아니라 github에서 수정한 레파지토리의 description만 보인_._ 

![](../../.gitbook/assets/image%20%2813%29.png)

왜 naraewool.github.io  또는 naraewool.github.io/\[project name\] 주소를 쳐도 내 Gitbook에서 작성한 블로그가 보이지 않는걸까? 



당시엔 다음과 같이 생각했다:

_'왜지? Hugo를 설치하고 나서 이 문제가 생긴 것 같다. Hugo를 통한 스킨 설정은 잠시 보류. Github에 적용할 수 있는 테마를, 나는 Gitbook에 적용할 수 있다고 착각하고 시작한 잘못. 3일을 뻘짓했네. 어쨌든 Hugo는 잠시 뒤로 하고, Gitbook이 Github의 메인 주소로 나타났으면 좋겠는데 그게 안된다. 새로 접하는 툴이 이것 저것 많아 더 혼란만 가중된 상태에서 어느 것 하나 제대로 되는게 없다. 아는 것이 많지 않으니 삽질로부터 배우는 수밖에."_



그런데 이 프로젝트에서 도움을 받았던 아보느님 블로그에 질문을 드렸는데, 깃허브와의 연동은 마크다운으로 작성이 편한 분들을 위해 연동하는 것이고 깃북으로 작성한 페이지는 깃북 주소로 곧바로 접속하면 된다고 하셨다: username.gitbook.io/projectname

아! 난 그동안 무엇을 했단 말인가.

난 깃허브를 연습하기 위해 깃북과 연동해서 사용하려 했던 것인데 사실 나에겐 마크다운보다 마이크로소프트 워드나 네이버 블로그와 같은 UI를 보이는 깃북이 더 편했다.

음. 다시 플랫폼을 바꿔야 한단 말인가.

생각이 많아졌지만 일단 며칠 간 쓴 글들을 발행하는 게 목적이니, 깃북으로라도 블로그를 꾸준히 써나가야겠다.



## 마크다운으로 글 쓰기

아무리 깃북이 편하다해도 깃허브 연동한 효과를 누리려면, 마크다운으로 글 한번은 써봐야지.

사실 마크다운으로 글쓰는데 익숙해지고 싶어서 애초부터 블로그를 티스토리가 아닌 깃허브에서부터 시작했으니까.

먼저 규칙들을 익혀볼까.

\[출처: [깃북 공식홈페이지](https://docs.gitbook.com/content-editing/markdown)\]

### Text formatting

We support all the classic inline Markdown formatting:

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2Fgitbook%2F-LLFdOg_bHdztKQ8lRdc%2F-LLFdfwYQacaWHsT5Mlz%2Fexample-md-bold.gif?alt=media&token=c1be5d04-4172-4ab4-af6d-b9c94ae836d3)

| Formatting | Markdown version | Result |
| :--- | :--- | :--- |
| Bold | `**bold**` | **text** |
| Italic | `_italic_` | _italic_ |
| Strikethrough | `~strikethrough~` | ~~strikethrough~~ |

### Titles

* Heading 1: `# A first-level title`
* Heading 2: `## A second-level title`
* Heading 3: `### A third-level title`

### Code blocks

```````⏎```` creates a new code block.

```````py⏎```` creates a new code block with Python syntax highlighting.

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2Fgitbook%2F-L9nloxhiQArLklasHES%2F-L9o-nG7M0J1ZTqBcdvM%2Fcodeblocks.gif?alt=media&token=f1bb8f6a-218f-49d4-b2e6-ed0115d702db)

### Lists

We automatically detect ordered and un-ordered lists as you type. Begin a line with `-` or `*` to start a bullet list. Being a line with `1.` to start a numbered list. Use `Tab` to go one level deeper, and `Shift+Tab` to go up.

* 목록 레벨1 \(\*눌러 목록 생성 \)
  * 레벨 2 \(\* +  탭 키눌러 하위 레벨로 바꾸\)
    * 레벨 3
      * 레벨 4
        * 레벨 5
      * 레벨 4 \(Shift + Tab 눌러 레벨 한 단계 올리기\)

### Quotes

Begin a line with `>` to make a block quote.



\[마크다운 자체에 대해 더 알아보려면: [http://commonmark.org/help/](http://commonmark.org/help/)참고\]

#### -

##  <a id="text-formatting"></a>



