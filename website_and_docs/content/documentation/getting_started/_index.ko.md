---
title: "시작하기"
linkTitle: "시작하기"
weight: 2
description: >
  Selenium을 처음 이용하시는 고객분께는 즉시 최신 정보를 제공해드릴 수 있는 리소스가 몇 가지 있습니다
        [
          "/documentation/ko/getting_started/", 
          "/documentation/ko/getting_started/quick/",
          "/documentation/ko/selenium_installation/",
          "/documentation/ko/getting_started_with_webdriver/"
        ]
---

{{% pageinfo color="warning" %}}
<p class="lead">
   <i class="fas fa-language display-4"></i> 
   Page being translated from 
   English to Korean. Do you speak Korean? Help us to translate
   it by sending us pull requests!
</p>
{{% /pageinfo %}}

Selenium은 _WebDriver_ 의 사용을 통해 대부분의 모든 브라우저의 자동화를 지원합니다.   
_WebDriver_ 는 웹 브라우저의 동작을 제어하기 위한 언어 중립 인터페이스를 정의하는 API와 프로토콜 입니다.  
각 브라우저는 *드라이버* 라고 불리는 특정한 웹 드라이버 구현에 의해 작동됩니다.    
드라이버는 브라우저로의 위임을 담당하는 구성 요소이며, Selenium과 브라우저와의 통신을 처리합니다.  

이러한 분리는 브라우저 공급 업체가 브라우저 구현을 책임지게하려는 의식적인 노력의 일부입니다.  
Selenium은 가능한 한 이러한 타사의 드라이버를 사용하지만, 현실적으로 불가능할 경우 프로젝트에서 유지&관리하는 자체 드라이버도 제공합니다.  

Selenium 프레임워크는 이 모든 부분을 하나로 묶습니다.    
서로 다른 브라우저 백엔드를 투명하게 사용할 수 있는   
사용자 대면 인터페이스를 통해 브라우저 간 및 플랫폼 간의 자동화가 가능합니다. 

Selenium 설치는 다른 프로젝트들과는 다를 수 있습니다. Selenium을 자동화 프로젝트에 사용하기 위해서는 당신이 선택한 언어로 바인딩된 라이브러리 설치가 필요합니다. 자동화와 테스트를 실행하기 위한 브라우저와 웹드라이버 바이너리가 추가적으로 필요합니다.


After completing the setup, you can run the code snippet shown at the 
[starting page] in our docs. Then head to the 
 section to learn more about
browser automation with Selenium.

Selenium 설치는 세 단계로 나눌 수 있습니다.

1. 원하는 프로그래밍 언어로 [Selenium 라이브러리를 설치]({{< ref "/installing_selenium_libraries.md" >}})한다.
2. 브라우저를 자동화하도록 [브라우저 드라이버를 설정]({{< ref "/installing_browser_drivers.md" >}})한다.(예: Firefox용 GeckoDriver)
3. (선택 사항) 테스트를 확장하려면 [Selenium 그리드]({{< ref "/grid.md" >}})를 설정 및 구성.

로우 코드/레코드 및 재생 도구로 시작하려면 [Selenium IDE](https://selenium.dev/selenium-ide)를 누르십시오.

설정을 완료한 후 문서의 [시작 페이지](/ko/documentation) 에 표시된 코드 조각을 실행할 수 있습니다. 그런 다음 Selenium과 함께 브라우저 자동화에 대해 자세히 알아보려면 [WebDriver]({{< ref "/webdriver.md" >}})로 이동하십시오.
