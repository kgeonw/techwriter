# \[Project\] 나만의 웹페이지 만들기 \(github + hugo\)

## 1. Go 설치하기

다음은 Hugo를 이용할 수 있는 go 프로그램을 Windows 작업 환경에 설치하는 방법을 소개한다.

\[[설치 페이지](%20https://golang.org/dl)\] 

![Go &#xC124;&#xCE58; &#xD398;&#xC774;&#xC9C0;](../.gitbook/assets/image%20%2812%29.png)

![Go &#xC124;&#xCE58; &#xC644;&#xB8CC;](../.gitbook/assets/image%20%2810%29.png)

{% hint style="warning" %}
Go의 설치 파일은 C:\Go에 설치된다. 원하는 곳에 설치 가능하지만 환경 변수 설정이 필요하다. 
{% endhint %}



### 1.1. Go 환경 변수설정하기

{% embed url="https://github.com/golang/go/wiki/SettingGOPATH" %}

작업물이 저장될 위치는 선택 가능하다. 

1. 원하는 위치에 폴더 생성
2. 시작\(Start\) 버튼에서 오른쪽 버튼 눌 **제어판\(Control Panel\)** 선택 &gt; **시스템과 보안 \(System and Security**\) &gt; **시스템**  선택 \(제어판\시스템 및 보안\시스템\)
3. 왼쪽의 메뉴에서 **고급 시스템 설정\(Advanced systems\)** 선택
4. **환경 변수\( Environment Variables\)** 버튼 클릭
5. User에 대한 **환경 변수\(User variables\)** 항목에  **새로 만들기\(New\)** 클릭
6. **변수 이름**란에 _GOPATH_ 입력
7. **변수 값**란에 1번 단계에서 생성한 폴더의 경로 입력
8. **확인** 클릭

![step 2](../.gitbook/assets/image%20%289%29.png)

![step 6](../.gitbook/assets/image%20%286%29.png)

{% hint style="info" %}
WIndows 10의 경우 

There is a faster way to edit `Environment Variables` via search:

* Left click on "Search" and type `env` or `environment`.
* Select "Edit environment variables for your account".
* ... and follow steps above.

### Windows 10 \(cli version\)

* Open a command prompt \(windows-key + r then type "cmd"\) or a powershell window \(windows-key + i\)
* Type `setx GOPATH %USERPROFILE%\go` \(this will set the `GOPATH` to your `[home folder]\go` e.g. `C:\Users\yourusername\go`
* Close the command or powershell window \(the environment variable is only available for new command or powershell windows, not for the current window\).
{% endhint %}



## 2. Hugo 설치

내가 설치한 건 Hugo를 실행할 수 있는 Go라는 툴이었고,

환경 변수를 변경하였으나 Go 사이트에 안내된 대로 소스를 빌드할 수 없었다.

당연한걸! Hugo를 설치하지 않았으니.

Hugo 설치하는 동[영상 ](https://youtu.be/G7umPCU-8xc)가이드를 보았고 손 쉽게 설치했다.

역시 글 보단 영상이군.

![](../.gitbook/assets/image%20%2826%29.png)

`$ hugo new site blog`명령으로 C:/Hugo/bin 폴더에 blog 폴더를 생성하다.

![](../.gitbook/assets/image%20%2830%29.png)

## 3. Git 설치

웹포트폴리오를 제작하려고 예전에 Github 계정은 이미 개설해두었다.

당시 유튜브 강의를 보면서 어찌 clone까지 했던 것 같은데 기억도 잘 안나고.

다시 구글링.

![](../.gitbook/assets/image%20%2825%29.png)

위 이미지에서 막힌 부분: **4. Open the terminal.**

터미널. 이게 뭐였더라.. 명령창이 있어야했던 것 같은데.

**개념정리! Git: Github을 명령어로  실행하기 위한 명령창.**

Git을 다운 받았다. config와 Initialize까지 성공.

![](../.gitbook/assets/image%20%2817%29.png)

Git과 Github - 

이것 저것 설치하고 동시에 개념을 익히다보니 혼란스러다.

Git에 대한 설명, 다운로드, 가이드는 아래 사이트에 자세히 나와있다.

+ 동영상 강의까지

## 4. Github와 연동

Hugo가 적용될 Submodule 폴더를 생성해야 한다.

휴고 공식 사이트와 Integeous 님의 블로그를 참고하여 진행하였다. 

> #### Step-by-step Instructions[ ](https://gohugo.io/hosting-and-deployment/hosting-on-github/#step-by-step-instructions) <a id="step-by-step-instructions"></a>
>
> 1. Create a `<YOUR-PROJECT>` \(e.g. `blog`\) repository on GitHub. This repository will contain Hugo’s content and other source files.
> 2. Create a `<USERNAME>.github.io` GitHub repository. This is the repository that will contain the fully rendered version of your Hugo website.
> 3. `git clone <YOUR-PROJECT-URL> && cd <YOUR-PROJECT>`
> 4. Paste your existing Hugo project into a new local `<YOUR-PROJECT>` repository. Make sure your website works locally \(`hugo server` or `hugo server -t <YOURTHEME>`\) and open your browser to [http://localhost:1313](http://localhost:1313/).
> 5. Once you are happy with the results:
>    * Press Ctrl+C to kill the server
>    * Before proceeding run `rm -rf public` to completely remove the `public` directory
> 6. `git submodule add -b master git@github.com:<USERNAME>/<USERNAME>.github.io.git public`. This creates a git [submodule](https://github.com/blog/2104-working-with-submodules). Now when you run the `hugo`command to build your site to `public`, the created `public` directory will have a different remote origin \(i.e. hosted GitHub repository\).

\(출처:[ Hugo 사이트](https://gohugo.io/hosting-and-deployment/hosting-on-github/#step-by-step-instructions)\)

Github에서 두 개의 Repository를 만든다.

blog - \(Main\)

naraewool.github.io - \(Hugo website\)

![](../.gitbook/assets/image%20%2832%29.png)

그리고 main을 원격저장소로 지정하고 hugo website를 submodule로 등록한다.

![](../.gitbook/assets/image%20%2819%29.png)

![](../.gitbook/assets/image%20%2842%29.png)

계속 오류나더니 드디어 public 폴더가 생성되고 submodule로 지정되었다. 

![](../.gitbook/assets/image%20%2837%29.png)



#### \*submoduel이란?



## 5. Hugo 테마 적용

$`hugo new site blog` 명령으로 로컬에서 컨텐츠를 관리하기 위한 장소를 생성하라 했다.![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-LlbB5vOTN4RbAekKufd%2F-LlbBBPz9WDkH2iQ02ZC%2Fimage.png?alt=media&token=ca9a2c1a-d723-4499-bcbe-c64a705072ad)

​‌

내가 바로 이 구역의 코린이. \(코딩 + 어린이\) 

코린이는 저걸 Windows cmd 창에 입력해야하는지, Hugo 입력창에 입력해야 하는지, '$'는 입력해야 하는게 아닌 건지조차 혼란스러웠다. 이 당시에는 git 설치 전으로 Windows cmd 창을 이용했다.

개발자들이 보면 정말 별거 아닌 문제들이지만, 나에겐 모든 것이 새롭고 쉬운 단계들마저 꽤 오랜 시간이 소요되기도 했다.  

그래도 하나하나 알아가다보면 익숙해지겠지. 그리고 나와 같은 비전공자에게도 이 글이 도움이 될 수 있진 않을까.

​‌

어쨌든 Hugo 사이트에서 마음에 드는 테마를 찾았다.‌

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-LlbBzCM5Y4h4ybGoAGU%2F-LlbCR4PK2YxHaPGiaad%2Fimage.png?alt=media&token=c5573bc6-2300-4c6c-95ea-1c6e6b8f0a2d)

html, css 배울 때 혼자 만들어보겠다고 했던 그런 느낌이랑 많이 비슷해서 이 테마를 적용하여 블로그를 만든다면 css 코드도 보며 더 배울 수 있을 것 같았다.

​‌

좋아! 다음 단계.‌

github 저장소 주소를 복사하여 휴고 Theme 폴더에 클론을 하라한다.‌

위 테마의 주소를 저장한 후, 설치한 Git을 통해 처음으로 클론을 시도한다.‌

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-LlbDw2acXvftGTkxUDt%2F-LlbE8daML-zPX3F5V3D%2Fimage.png?alt=media&token=ea4b0b80-dfa4-4e35-b11f-0d8ef43abbec)

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-LlbDw2acXvftGTkxUDt%2F-LlbDwmBTlkpii8iAqSa%2Fimage.png?alt=media&token=ef4140b0-0610-4bde-98a2-048d02d92904)

오! 성공적으로 theme 폴더에 내가 원한 테마가 클론되었다.‌

그 다음은 'config.toml 파일을 선택한 테마의 설명에 따라 수정한다'‌

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-LlbDw2acXvftGTkxUDt%2F-LlbFCplYiGB-zNtHqOT%2Fimage.png?alt=media&token=f9cf5dab-526b-4475-8b6e-07a27f99cf76)

toml 파일은 뭐고 어떤 응용 프로그램으로 열어야 하는지...‌

메모장으로 열어볼까?‌

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-LlbGKGqvXSfs0h08iJV%2F-LlbGNIv_r_zshrvBg46%2Fimage.png?alt=media&token=6e20de89-0604-4988-9f6d-368e6e07235e)

음~ 열리는 구나. 정보를 대충 넣어보았음. 

여기서 부터 혼동이 시작되었던 것 같다.

어느 블로그에서 github과 Hugo로 블로그를 만드는 포스팅을 보았고, github과 gitbook을 연동해서 블로그 만드는 걸 보고-

나는 github과 gitbook을 연동해서 블로그를 만들고 거기에 hugo를 적용할 수 있을거라고 착각했다.



+ \(추가\)

HTML 공부할 때 설치했던 atom으로 열었더니 아름답게 잘 보인다.

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-LlnEjwXnHrDegy_pGMP%2F-LlnEkRC5uoytD_UQwhi%2Fimage.png?alt=media&token=03a1b9e4-5813-45c0-a9de-4e5c13d8815b)

​‌

그리고 Integious 님의 블로그에 따르면,

Hugo 테마를 클론하는 것보다 submodule로 만들면, 테마가 개인 원격 저장소에 존재하는 동시에 submodule로 잡혀있어 블로그를 관리하는 컴퓨터나 OS가 바뀌어도 테마를 찾아 헤맬 필요가 없다고 한다. 그래서 다시 Submodule화 했다.‌

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-Lln2rlAx3nkZgprq3oD%2F-Lln3Lq7-Vs3BDCz5CX_%2Fimage.png?alt=media&token=dae0cd4b-e7f8-489d-bfbb-81d1afe2e1e0)

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-Lln2rlAx3nkZgprq3oD%2F-Lln39DYkbLzIV8Pwd0v%2Fimage.png?alt=media&token=b27c1cfe-01b9-4155-af42-1737ca98551d)

위는 Cloning 한 테마. 밑에 폴더는 Submodule 추가한 테마.‌

Cloning한 폴더를 그냥 삭제 해도 되는지, submodule 폴더는 이름을 변경을 해도 되는지 모르겠다.

​‌적용한 테마가 잘 보이는지 `$ hugo server` 명령을 치고 안내해주는 주소\([//localhost:1313/](//localhost:1313/)\)를 치면,

탁!

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-LlnEV1ZlPLFjn6m4fe9%2F-LlnEWAlolu-PvRFScGX%2Fimage.png?alt=media&token=3eaea46f-cfe1-46f6-92a0-5c9e1a2dde16)

오잉,  hugo 테마가 보이는 것 같은데  컨텐츠가 하나도 안 보이네.

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-LlnEV1ZlPLFjn6m4fe9%2F-LlnEaEs9MJuJGOQFkYz%2Fimage.png?alt=media&token=96cc310f-ca98-4787-9195-8ba604fbe540)

자 이제 컨텐츠를 채워나가보자!

## 6. Hugo 글 쓰기

또 다른 블로그를 참고해서 Hugo 글쓰기를 시도했다. \([참고 블로그](https://blog.lulab.net/infra/install-hugo-and-configure-for-your-blog/#hugo-%EA%B8%80-%EC%83%9D%EC%84%B1)\)‌

 archetypes 폴더 엤는 default.md 파일을 다음과 같이 수정:

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-LlhotUET7VkH6HrlviF%2F-LlhowIrk75Gwg60kDZj%2Fimage.png?alt=media&token=69882211-45aa-4ea7-b51a-d55f88a07ffc)

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-Llhpa4j4V6WDMo7eoAu%2F-LlhqsY79tIBEMgWs4bI%2Fimage.png?alt=media&token=e4ba42f6-4c99-4050-9bfe-a3769373b34a)

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LlTRqTlfHUvElfY0jUp%2F-Llhpa4j4V6WDMo7eoAu%2F-LlhrqPGTIVPbjHofAuF%2Fimage.png?alt=media&token=17832552-7e23-4f2b-8064-04a9f6b81d93)

-hold-















