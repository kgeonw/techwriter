# Web API Documentation Best Practices



태블릿 PC, 모바일폰, SNS\(Social Networking\)과 같이 다양한 기술에 대해서 기술하는 Peter Gruenbaum의 포스팅을 번역했다. \[[원문 보기](https://www.programmableweb.com/news/web-api-documentation-best-practices/2010/08/12)\]

Software as a Service\(SaaS\)의 인기에 힘 입어 많은 Web API가 생겨났지만 API 가이드의 형식\(Format\)과 질\(quality\)은 모두 제각각이다. 좋은 문서는 비용을 절감할 뿐 아니라 해당 플랫폼에 관심 있어하는 개발자를 독려하고 흥미를 유지시킨다. 이상적으로 해당 문서는 네 가지 영역을 다루어야 한다: **overview, getting started, sample code, and references**

![](../.gitbook/assets/image%20%2827%29.png)

이 글에서는 Web API 문서에 특화된 최상의 방법\(best practices\)을 소개한다.

**자동생성 문서\(Auto-generate Documentation\)**

API 문서를 작성하는데 필요한 일을 최소화하려면 당신이 제작한 문서가 얼마나 많이 자동화되었는지 확인하는 것이 좋다. \*SOAP 기반 API의 경우, \*\*WSDL에서 정보를 가져와 문서 페이지 생성이 사용할 수 있다. Windows Communication Foundation과 같은 어떤 플랫폼은 REST 서비스를 위한 help 페이지를 자동으로 생산한다. 하지만 자동생성문서는 단지 시작일 뿐, 여전히 개요\(overview\) 뿐 아니라 문서의 모든 요소\(element\)에 대해 기술해야 한다.

> \*SOAP\(simple Object Access Protocol\): 일반적으로 널리 알려진 HTTP, HTTPS, SMTP 등을 통해 XML 기반의 메시지를 컴퓨터 네트워크 상에서 교환하는 프로토콜. 웹서비스에서 기본적인 메시지를 전달하는 기반이 된다. SOAP에는 몇 가지 형태의 메시지 패턴이 있지만, 보통의 경우 원격 프로시져 호출\(Remote Procedure Call:RPC\) 패턴으로 네트워크 노드\(클라이언트\)에서 달ㅡㄴ쪽 노드\(서버\)쪽으로 메시지를 요청하고, 서버는 메시지를 즉시 응답하게 된다. SOAP은 XM-RPC와 WDDX에서 envelope/heade/body로 이루어진 구조와 전송\(transport\)과 상호 중립성\(interaction neutaility\)의 개념을 가져왔다. SOAP은 XML을 근간으로 헤더와 바디를 조합하는 디자인 패턴으로 설계되어 있다. ‘헤더’는 선택사항으로 반복이나 보안 및 트렌잭션을 정보로 하는 메타 정보를 가지고 있다. ‘바디’ 부분은 주요한 정보인 정보를 가지고 있다. \[출처: 위키피디아\]
>
> \*\*WSDL\(Web Services Description Language\): 웹 서비스 기술 언어 또는 기술된 정의 파일의 총칭으로 XML로 기술된다. 웹 서비스의 구체적 내용이 기술되어 있어 서비스 제공 장소, 서비스 메시지 포맷, 프로토콜 등이 기술된다. \[출처: 위키피디아\]

\*\*\*\*

**샘플 코드 포함\(Include Sample Code\)**

개발자들은 작업의 베이스로 시작할 수 있고 배울 수 있는 샘플코드를 다른 어느 것보다 좋아한다. Web API의 강점 중 하나는 플랫폼과 프로그래밍 언어가 각각 별개라는 것이다. 불행히도 이것은 문서를 생성할 때 추가적인 일을 필요로 한다. Python, Ruby, Java, C\#, PHP 등 각 언어에서 API 호출을 만들줄 알아야 한다. 모든 언어에 대해 샘플 코드를 작성해야하는가? 그것은 실용적이지 않을지도 모른다. 대신 어떤 언어가 가장 많이 쓰이는지 파악하여 해당 언어에 집중하라.

\*\*\*\*

**요청과 응답의 예를 설명하라\(Show Example Requests and Responses\)**

샘플 코드와 더불어 요청\(request\)과 응답\(\(response\)에 HTTP, XML, and JSON 샘플을 갖는 것은 중요하다. 하지만 샘플만 가지고서는 충분하지 않다. 호출\(Call\)의 목적을 설명하고 각각의 요소\(element\)를 설명하는 표가 필요하다. Name, Type, Description, Remark의 열을 가진 표를 추천한다.

![](https://www.programmableweb.com/wp-content/web-api-table.gif)

Type 열은 형식\(format\)과 관련하여 필요한 대부분의 정보를 제공할지 모르지만 remark 섹션은 더욱 더 명확하게 하기 위해 필요할지 모른다. XML 요소가 날짜라면 당신은 날짜의 형식을 명시해야 한다. 시간이라면 시간대\(time-zone\)을 명시해야 한다.

\*\*\*\*

**인증과 에러 처리에 대한 설명 \(Explain Authentication and Error Handling\)**

인증\(Authentication\)은 Web API를 위해 필수적이므로 어떻게 인증서\(credential\)을 얻을 수 있는지 어떻게 이 인증서들이 웹 서버로 전달되는지 설명해야 한다. 어떻게 API 키를 얻는지에 대한 단계별지시 절차\(instructions\)가 필요할 수도 있다. 샘플 코드는 개발자들에게 종종 어떻게 키가 작동하는지 유용하게 쓰인다.

어떻게 에러가 처리되는지도 설명해야 할 것이다. 예를 들어, 어느 HTTP 호출이 인증되지 않은 인증서를 사용하여 데이터를 요청하거나 또는 존재하지 않는 데이터를 사용하여 어떤 액션을 요청할 수도 있다. 현재 에러 정보를 다시 전달하는 표준적인 방법은 없다. 그래서 개발자들은 어떻게 에러 정보가 다시 전달되는지, 왜 에러가 발생하는지, 어떻게 문제를 해결할지 이해할 필요가 있다.

마지막으로 Web API는 고유의 데이터를 포함하는 HTTP의 위에 있다는 것을 기억해라. 따라서 문서를 요하는 HTTP 관련 정보를 가질지 모른다. 이것은 캐쉬\(cashing\), 컨텐츠 타입, 상태 코드\(Status code\)를 포함할 수 있다.

\*\*\*\*

**참고할 예시** **Examples to Look At**

Web API 업계 사람들에게 어느 문서는 종종 잘 작성된 예시로 여겨진다. 클라우드 기반 전화통신\(telephony\)를 제공하고 [훌륭한 문서](http://www.twilio.com/docs/index)를 보유한 Twillo다.

무엇을 잘한 걸까? 먼저 개발자가 물어볼 수 있는 모든 조각\(Piece\)들을 가지고 있다: 튜토리얼, 샘플코드, 서론, 참조, 에러와 경고 사전. 그들의 참고 자료는 잘 정리되어있고, 기초 URI, 테이블의 속성, HTTP 메소드\(GET, POST, PUT, DELETE, XML 예제와 설명\)와 같은 정보가 잘 쪼개져있다. 게다가 전반적인 웹사이트의 느낌\(feel\), 외향\(look\)과 잘 어울리는 서식\(formatting\)을 가지고 있고, 탐색\(navigation\)하기도 좋다.

Twillo만큼 잘 정돈된 문서를 제작하는데 필요한 시간과 자원이 없다면 Wiki로 쉽게 취합해라. 이 방법이 Tweeter가 한 방법으로,  [위키 스타일의 문서](https://developer.twitter.com/)는 시작하기\(getting started\), FAQ, 참고자료\(reference material\)에서 간단한 목록으로 체계화 된다. 각각의 참조는 URL, 지원되는 서식과 HTTP 메소드의 목록, 샘플 응답\(sample response\)을 포함한다.

Web API는 상당히 새롭고 그 문서들을 위한 최상의 방법들은 여전히 발전하고 있다. 일반적인 API 문서를 위해 좋은 방법\(good practice\)를 따라하는 것과 더불어 당신의 Web API를 위해 문서를 생성할 때 위의 가이드를 따라해라.

