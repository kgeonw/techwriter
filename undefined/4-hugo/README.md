# \#4 Hugo 테마 적용

$`hugo new site blog` 명령으로 로컬에서 컨텐츠를 관리하기 위한 장소를 생성하라 했다.

![](../../.gitbook/assets/image%20%283%29.png)



코딩 입문자는 저걸 Windows cmd 창에 입력해야하는지, Hugo 입력창에 입력해야 하는지, '$'는 입력해야 하는게 아닌 건지조차 혼란스럽다. 

개발자들이 보면 웃겠지만, 나에겐 모든 것이 새롭.

그래도 하나하나 알아가다보면 익숙해지겠지.



어쨌든 마음에 드는 테마를 찾았다.

![](../../.gitbook/assets/image%20%2821%29.png)

html, css 배울 때 혼자 만들어보겠다고 했던 그런 느낌이랑 많이 비슷해서 이 테마를 적용하여 블로그를 만든다면 css 코드도 보며 더 배울 수 있을 것 같았다. 



좋아! 다음 단계.

github 저장소 주소를 복사하여 휴고 Theme 폴더에 클론을 하라한다.

위 테마의 주소를 저장한 후, 설치한 Git을 통해 처음으로 클론을 시도한다.

![](../../.gitbook/assets/image%20%288%29.png)

![](../../.gitbook/assets/image%20%2838%29.png)

오! 성공적으로 theme 폴더에 내가 원한 테마가 클론되었다.

그 다음은 'config.toml 파일을 선택한 테마의 설명에 따라 수정한다'

![](../../.gitbook/assets/image%20%2832%29.png)

toml 파일은 뭐고 어떤 응용 프로그램으로 열어야 하는지...

메모장으로 열어볼까?

![](../../.gitbook/assets/image%20%2827%29.png)

음~ 열리는 구나. 정보를 대충 넣어보았음.



Hugo 테마를 클론하는 것보다 submodule로 만들면, 테마가 개인 원격 저장소에 존재하는 동시에 submodule로 잡혀있어 블로그를 관리하는 컴퓨터나 OS가 바뀌어도 테마를 찾아 헤맬 필요가 없다고 한다. 그래서 다시 Submodule화 했다.

![](../../.gitbook/assets/image%20%2831%29.png)

![](../../.gitbook/assets/image%20%2828%29.png)

위는 Cloning 한 테마. 밑에 폴더는 Submodule 추가한 테마. 

Cloning한 폴더를 그냥 삭제 해도 되는지, submodule 폴더는 이름을 변경을 해도 되는지 모르겠다. 



드

![](../../.gitbook/assets/image%20%2816%29.png)

![](../../.gitbook/assets/image%20%2818%29.png)

드디어 hugo 테마가 보이기 시작했는데 컨텐츠가 하나도 안 보이네

![](../../.gitbook/assets/image%20%2817%29.png)

