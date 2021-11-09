---
title: "자동화 튜링 테스트"
linkTitle: "자동화 튜링 테스트"
weight: 1
aliases: ["/documentation/ko/worst_practices/captchas/"]    
---

캡차(CAPTCHA)는 컴퓨터와 인간을 구분하기 위한 완전 자동화된 공공 튜링 테스트(Completely Automated 
Public Turing Test to telling Computer and Humans addition)의 줄임말로, 자동화를 방지하도록 명시되어 
있으므로 시도하면 안됩니다! CAPTCHA 검사를 수행하기 위해서는 중요한 두 가지 작업이 있습니다.

* 테스트 환경에서 CAPTCHA 비활성화
* 테스트가 CAPTCHA를 우회할 수 있도록 후크 추가

