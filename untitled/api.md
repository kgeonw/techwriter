---
description: Sendbird 블로그 발췌
---

# API 문서를 작성하는 법



나는 실무에서 API 문서를 제작해본 적이 없어 나 혼자라도 경력을 쌓아야겠다 라고 생각했다.

첫 번째로 API 문서를 작성하는 방법을 구글링 하던 중, 좋은 글이 있어 기록한다.

모든 문장을 1:1로 번역하지 않고, 주요 내용들만 추려서, 그리고 참고할 링크들을 살려서 정리했다.

원문을 보려면 [여기](https://blog.sendbird.com/a-guide-to-writing-api-documentation)

+ 그리고 참고할 만한 다양한 사이와 기본적인 규칙을 알려준 SendBird에게 감사의 말을 전한다.



## 구조\(Structure\)

### 1.     내용이 충실한 소개글, 서론에 집중하라

개발자들에게는 친숙한 기본 개념도 누군가에는 명확하지 않은 개념일 수 있다. 새로운 사용자에게 서비스의 기본 개념이나 플랫폼\(안드로이드와 같은 OS\), 사용된 언어\(JAVA나 Swift\)를 리기 위한 소개글을 써라.

 [SendBird documentation](https://docs.sendbird.com/platform?utm_source=Blog&utm_medium=Referral-Text)를 예로 들면,  Platform API에 URL 인코딩\(encoding\)과 multipart request와 관한 섹션과 SendBird의 기초 셋업 단계를 설명하는 섹션이이 있다. 누군가에게는 “누가 이걸몰라”라고 생각할지 모르지만 “URL safety라고?”하면서 질문할지도 모른다.

물론 정말 필요하지 않은 설명의 위험이 늘 있다.  그래도 부족한 설명 보다는 추가적인 설명을 목표로 한다. 필요 없는 설명은 기본 개념을 추가하지 않은 것만큼 피해야한다. 하지 전문가들은 종종 신입들의 필요를 과소평가한다. 

신이 학생들을 가르치는 선생님이라고 생각해보라. 무엇을 평균 수준의 학생이라고 조준할 것인가?



### 2.     독자들이 가능한 빨리 핵심 기능을 시도하게 하라.

API, 라이브러리, SDK는 종종 하나의 핵심 기능을 제공한다. 설령 다른 기능들을 함께 제공할지도 하나의 목표를 가진다: **핵심 기능 구현.** 

사용자가 API를 설치하는 것을 익히기 전에 암호화된 파일을 보내는 것을 알기를 원하진 않을 것이다. 그저 시작점을 알려주고 더 자세한 특징들은 스스로 시도해보도록 하라.

[Stripe](https://stripe.com/docs)는 아주 좋은 예를 제공한다. 상호작용할 수 있는 "Try now" 섹션을 참고해라.



### 3.     과도한 \*네스팅을 피하라.

> \*네스팅\(\*Nesting\) 
>
> \(1\) [서브루틴](https://terms.naver.com/entry.nhn?docId=852166&ref=y) 중에 다른 서브루틴을 짜넣는 것. 더욱이 일반적으로는 [프로그램 루틴](https://terms.naver.com/entry.nhn?docId=833918&ref=y) 중에 다른 프로그램 루틴 또는 일군의 [데이터](https://terms.naver.com/entry.nhn?docId=847441&ref=y)를 짜넣는 것.  
> \(2\) 높은 우선도\(priority\)의 분배가 낮은 우선도의 분배 처리를 중단하는 것.
>
> **출처: \[네이버 지식백과\]** [네스트 구성](https://terms.naver.com/entry.nhn?docId=830466) \[nesting\] \(컴퓨터인터넷IT용어대사전, 2011. 1. 20., 전산용어사전편찬위원회\)



로컬 그룹에 모든 것을 세분화하고 싶을지도 모르나 과도한 nesting일 피해라.

_1. Messages_

    _1.1 Sending messages_

        _a. Sending text messages_

        _b. Sending file messages_

            _i. Sending binary files_

                _\* Multipart requests_

                _\* Using multipart requests to send binary files_

이런 구조는 2 레벨 이상 세분화된 섹션은 사이드 네비게이션 메뉴에 표시되지 않을 수 있다. 사실 하나의 단계로 확장하는 것이 이상적일 지도 모른다. 두번째 문제는 좋은 디자인과 연관이 있다. 어떻게 모든 헤드\(h1부터 h6까지\)를 직관적으로 구분해서 사용자가 문서에서 어디쯤 읽고 있는지 정확히 알릴 수 있는가?

_1. Messages_

    _1.1 Sending text messages_

    _1.2 Sending file messages_

        _a. Sending binary files_

문서의 구조를 단조롭게 하면 카테고리화와 검색성 사이의 조화를 이루게 된다. 하지만 간결성은 가장 짧은 시간에 해결책을 찾으려는 개발자에게 무척이나 귀중하다.



## 서식\(Formatting\)

현대 개발자 문서는 디자인과 서식에 큰 중요성을 두고 있다.[ Gmail API 문서](https://developers.google.com/gmail/api/v1/reference/users/labels/update)를 예로 보자.  [Stripe’s API reference](https://stripe.com/docs/api#authentication)의 문서도 아름답게 디자인 되어있다.

\(.. 생략 ..\)

문서를 계획할 때 어떻게 보일지를 염두해 두어라. 디자인 요소들은 다양한 문맥에서 재사용할 수 있어야하고 일관되어야 한다.



### 1.     가벼운 마크업 랭귀지는 증명된 선택사항

문서가 웹사이드에서 전형적으로 렌더링 되기에 기본은 HTML이 된다. 그러나 HTML 소스를 사용하여 문서를 작성하기엔 시간 소모도 크고 실수가 생기기도 쉽다. [마크다운](https://daringfireball.net/projects/markdown/syntax)과 같은 LML은 웹을 빠르고 효율적으로 쓰도록 돕는다. 

Header, 문단, 링크가 한 문단에 있다 치자. HTML은 다음과 같은 것을 요구할 것이다: 

```text
<h1>Header here</h1>
<p>Reference this <a href=”https://www.example.com/”>link</a> for a more detailed description.</p>
```

  
같은 내용을 마크다운으로 쓴다:

```text
#Header here
Reference this [link](https://www.example.com/) for a more detailed description
```



### 2.     특별한 이유가 아니고서야 하나의 페이지를 만들어라.

단순한 질문의 해결책을 찾기 위해 아무도 세 개의 세분화된 링크를 타고가는 것을 원하지 않는다. 한 페이지 문서는 필적할 수 없는 검색성을 제공한다. Ctrl + F키를 이길 수 없다는 것을 인정해라. 모든 섹션의 목록을 보여주는 사이드바가 제공되더라도 한 페이지의 문서는 조감도를 얻는 것과 같다. [Parse Android docs](http://docs.parseplatform.org/android/guide/)예를 보면도 “목차”를 제공하지 않고서도 Users, Objects, and Sessions와 같은 컴포넌트들을 포함하고 있다. 하지만 광범위한 API를 가지고 있는 경우, 모든 정보를 한 페이지에 넣는 것은 불편하고 페이지 로딩을 느리게할 수 있다. 이러한 경우는 피하자. \([GitHub’의 API docs](https://developer.github.com/v3/) 참고\)



### 3.     표를 이용해라.

코드 문서는 본질적으로 많은 정보를 포함한다. 코드 파라미터와 변수의 경우는 표를 이용하여 정보를 전달하라. [Peter Gruenbaum의 기사](https://www.programmableweb.com/news/web-api-documentation-best-practices/2010/08/12)에서는 4열 구조\(Name,  Type, Description, Remarks\)를 추천한다.

![resource: Peter Gruenbarum&apos;s article](../.gitbook/assets/image%20%2831%29.png)

 [SendBird](https://docs.sendbird.com/platform?utm_source=Blog&utm_medium=Referral-Text&_ga=2.199464174.1799238679.1565728700-1150278189.1565728700#user_3_create_a_user)의 경우 비슷한 구조에 “description”와 “remarks.”를 합쳐 3열의 표를 사용한다. 추가 열을 추가하고 일반적인 “description” 열에 작성할지 API의 디자인에 따라 선택해야 한다.







## 쓰기와 문법\(Writing and grammar\)



### 1.     독자를 ‘you’라 지칭하고 능동태를 사용하여라.

_Not: "Code is written by a developer."_ 

_Rather: "A developer writes code."_



### 2.     대명사를 사용할 때는 he or she를 포괄할 수 있는 they를 사용해라. 많은 API 문서에서 “Users”를 사용하는데 다음과 같이 사용하자:

지칭하는 대상이 단수여도 매번 ‘he or she’,  ‘him or her’를 사용하기 보다 they, them으로 포괄하기.

“_A user might encounter X. In that case, you could provide him with feature Y.”_

_è “ A user might encounter X. In that case, you could provide them with feature Y.”_

또는 they를 사용기 위하여 user를 복수처리하기

 _“Users might encounter X. In that case, you could provide them with feature Y.”_

\_\_

### 3.     제목에 대문자를 사용할 때, 일관되게 쓰자.

제목에 대문자를 사용하는데에는 두 가지 방법이 있다:

“_Cooking a Great Apple Pie_”처럼 주요 단어의 첫 알파벳을 대문자 처리. AP 또는 시카고 스타일 표준에 따른 방법.

 “_Cooking a great apple pie_.”: sentence case 방법. 가독성이 더 있음.

어느 것을 선택하는지는 글쓴이 마음이지만 다른 이들과도 일관되게 사용하는게 중요하다.



## 참고 링

* [Twilio](https://www.twilio.com/docs/)
* [Stripe](https://stripe.com/docs) 
* [Google](https://developers.google.com/gmail/api/v1/reference/)
* [Facebook](https://developers.facebook.com/docs/graph-api) 
* [https://docs.sendbird.com](https://docs.sendbird.com/?utm_source=Blog&utm_medium=Referral-Text).
* [Writing the docs](http://www.writethedocs.org/guide/) 
* [Google’s documentation style guide](https://github.com/google/styleguide/tree/gh-pages/docguide) 
* [Parse](http://blog.parse.com/learn/engineering/designing-great-api-docs/)

