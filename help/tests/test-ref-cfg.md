---
description: 이 참조는 Adobe Experience Platform Auditor에서 구성을 확인하기 위해 수행하는 테스트에 대한 자세한 정보를 제공합니다.
seo-description: This reference provides more information about the tests Adobe Experience Platform Auditor performs for configuration.
seo-title: Configuration
title: 구성
uuid: d40d815c-edfe-48b9-921f-cea1b0b54a0a
exl-id: e331d874-09f5-4a31-ad8c-6ee5d0849245
source-git-commit: 286a857b2ff08345499edca2e0eb6b35ecf02332
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 100%

---

# 구성

이 참조는 Adobe Experience Platform Auditor에서 구성을 확인하기 위해 수행하는 테스트에 대한 자세한 정보를 제공합니다.

구성 테스트는 구현에서 특정 설정, 값 또는 잠재적인 충돌을 검사합니다. Platform Auditor는 다른 규칙에 대해 태그를 평가하고 우수 사례를 권장합니다.

<table id="table_A8A1FC360482447185C8460A18426638"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 테스트 </th> 
   <th colname="col2" class="entry"> 기준 </th> 
   <th colname="col3" class="entry"> 권장 사항 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Advertising Cloud - 변환 이름은 영숫자만 사용</b> </p> <p>가중치: 3 </p> </td> 
   <td colname="col2"> <p>다음 <span class="codeph">ev_conversion_property_name</span> 매개 변수는 "<span class="codeph">ev_transid</span>" 매개 변수를 제외하고 숫자 값과 십진수 값을 포함해야 합니다(<span class="codeph">ev_transid</span> 값은 텍스트 또는 숫자 값을 포함할 수 있음). </p> <p><span class="codeph">ev_</span>로 시작하는 URL 매개 변수가 포함된 <span class="codeph">everesttech.net</span> 픽셀을 찾습니다. </p> <p>예: </p> <p><span class="codeph"> http://pixel.everesttech.net/1180/t?ev_page_load=1&amp;ev_revenue=$12&amp;ev_transid=1hf74i47 </span> </p> </td> 
   <td colname="col3"> <p> 거래 속성 매개 변수에는 숫자 및 십진수 값만 포함되어야 합니다. </p> <p> <p>경고: 다른 모든 값 유형은 데이터 손실을 초래할 수 있습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Advertising Cloud - 변환 이름은 URL 안전 문자를 사용</b> </p> <p>가중치: 3 </p> </td> 
   <td colname="col2"> <p> 변환 속성 이름에 앰퍼샌드 또는 물음표를 포함해서는 안 됩니다. </p> <p> 예: </p> <p><span class="codeph"> http://pixel.everesttech.net/1180/t?ev_revenue&amp;order=12&amp;ev_transid=</span> </p> </td> 
   <td colname="col3"> <p>거래 속성 매개 변수에 인코딩되지 않은 앰퍼샌드 또는 물음표가 포함되어 있지 않아야 합니다. 이렇게 하면 URL 형식이 손상됩니다. </p> <p> <p>경고: 인코딩되지 않은 앰퍼샌드 또는 물음표가 포함된 속성 매개 변수(예: <span class="codeph">ev_formComplete?=1</span> 또는 <span class="codeph">ev_formComplete&amp;Submit=1</span>)로 인해 데이터가 손실될 수 있습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Advertising Cloud - 올바르게 구현된 거래 ID</b> </p> <p>가중치: 1 </p> </td> 
   <td colname="col2"> <p> 속성 이름 <span class="codeph">ev_transid=</span>는 비워 둘 수 없습니다. </p> <p>예: </p> <p> <span class="codeph"> http://pixel.everesttech.net/1180/t?ev_page_load=1&amp;ev_revenue= 12&amp; ev_transid=</span> </p> </td> 
   <td colname="col3"> <p>속성 이름 <span class="codeph">ev_transid=</span>는 값(<span class="codeph">ev_transid=</span>) 없이 비워둘 수 없습니다. 값 없이 비워 두면 거래 데이터가 손실될 수 있습니다. <span class="codeph">ev_transid=</span>에 값을 할당하거나 픽셀에서 매개 변수를 제거합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Analytics - DOM에서 인스턴스화</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/analytics/implementation/home.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> Adobe Analytics 코드가 설치되지 않았거나 실행되지 않았습니다. 웹 페이지에 Analytics 코드가 없을 때 0을 반환합니다. </p> </td> 
   <td colname="col3"> <p>Analytics 태그가 페이지에 구현되어 있고 후속 스크립트 활동에서 차단되지 않았는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Analytics - 한 번 인스턴스화</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/analytics/implementation/home.html" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> Adobe Analytics 코드가 페이지에서 두 번 이상 검색되었습니다. 웹 페이지에 Analytics 코드가 없을 때 0을 반환합니다. </p> </td> 
   <td colname="col3"> <p>페이지에 Analytics 태그가 하나만 있어야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Analytics - 최신 버전</b> </p> <p>가중치: 3 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/analytics/implementation/appmeasurement-updates.html" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 페이지에서 최신 버전의 Analytics 코드 라이브러리를 실행하고 있지 않습니다. 향상된 성능을 활용하고 최신 기능을 제공하기 위해 Experience Cloud 기술을 지원하는 코드 라이브러리가 지속적으로 업데이트 및 변경되고 있습니다. 웹 페이지에 Analytics 코드가 없을 때 0을 반환합니다. </p> </td> 
   <td colname="col3"> <p>최신 버전의 Analytics 라이브러리를 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>DTM - DOM Ready 이후 타사 태그가 비동기적으로 로드</b> </p> <p>가중치: 3 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/dtm/using/resources/load-order.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>사용자 경험과 정확한 데이터 수집 간의 균형을 맞추기 위해 타사 태그를 DOM Ready에서 바로 트리거해야 합니다. 이렇게 하면 사이트 기능에 영향을 주지 않고 이러한 추적 스크립트가 실행됩니다. </p> </td> 
   <td colname="col3"> <p>DOM Ready에서 시작할 수 있는 타사 픽셀을 실행하는 모든 규칙을 조정하여 이 문제를 해결합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Experience Cloud ID Service - 최신 버전</b> </p> <p>가중치: 2 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/dtm/using/tools/macid.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 페이지에서 방문자 ID 서비스 코드 라이브러리의 최신 버전인 <span class="codeph">visitorAPI.js</span>를 실행하고 있지 않습니다. 향상된 성능을 활용하고 최신 기능을 제공하기 위해 Experience Cloud 기술을 지원하는 코드 라이브러리가 지속적으로 업데이트 및 변경되고 있습니다. </p> </td> 
   <td colname="col3"> <p>최신 버전의 방문자 ID 서비스 라이브러리를 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Launch - 최신 버전</b> </p> <p>가중치: 2 </p> <p><a href="https://adobe.com/go/launch_help_get_started" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>이러한 페이지에서 최신 버전의 Platform Launch 코드 라이브러리(Turbine)를 실행하고 있지 않습니다. 향상된 성능을 활용하고 최신 기능을 제공하기 위해 Experience Cloud 기술을 지원하는 코드 라이브러리가 지속적으로 업데이트 및 변경되고 있습니다. </p> </td> 
   <td colname="col3"> <p> Platform Launch 라이브러리를 다시 구축 및 게시하여 Platform Launch 라이브러리를 업데이트합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Target - 최신 버전</b> </p> <p>가중치: 2 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/dtm/implementing/target/update-target-tool.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 페이지에서 최신 버전의 Target 코드 라이브러리를 실행하고 있지 않습니다. 향상된 성능을 활용하고 최신 기능을 제공하기 위해 Experience Cloud 기술을 지원하는 코드 라이브러리가 지속적으로 업데이트 및 변경되고 있습니다. </p> </td> 
   <td colname="col3"> <p>최신 버전의 Target 라이브러리를 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Target - mboxDefault가 mboxCreate보다 우선함 </b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/target/using/implement-target/client-side/mbox-implement/mbox-download.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p><span class="codeph">mboxCreate</span>의 적절한 사용은 다음과 유사합니다. </p> <p> <span class="codeph"> &lt;div class="mboxDefault"&gt;&lt;!-Customer content--&gt;&lt;/div&gt;&lt;script&gt;mboxCreate('myMboxName')&lt;/script&gt;</span> </p> </td> 
   <td colname="col3"> <p><span class="codeph">mboxCreate()</span>를 호출하기 전에 <span class="codeph">&lt;div class="mboxDefault"&gt;&lt;/div&gt;</span> 태그를 포함해야 합니다. at.js는 사용자를 위해 추가하지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Target - 유효한 DOCTYPE</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/help/ko-KR/target/using/implement-target/client-side/faq-at-js/target-atjs-faq.html#what-html-doctype-does-atjs-require" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 잘못된 DOCTYPE이 검색되었습니다. 이 시나리오에서는 mbox가 실행되지 않습니다. </p> <p>at.js의 경우 DOCTYPE이 표준 모드여야 합니다. 그렇지 않으면 Target이 작동하지 않습니다. </p> </td> 
   <td colname="col3"> <p>페이지에서 DOCTYPE을 업데이트합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
