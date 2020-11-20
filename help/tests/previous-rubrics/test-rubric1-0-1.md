---
description: Adobe Experience Platform Auditor 테스트에 대한 정보
seo-description: Adobe Experience Platform Auditor 테스트에 대한 정보
seo-title: 테스트 지침 1.0.1
title: 테스트 지침 1.0.1
uuid: 2ed2572e-ddb8-4899-b3a9-1329afdd7905
translation-type: ht
source-git-commit: 00d184c1fa1eece9eec8f27896bfbf72fa32bfb6
workflow-type: ht
source-wordcount: '2727'
ht-degree: 100%

---


# 테스트 지침 1.0.1{#test-rubric}

## 테스트 지침 1.0.1{#topic-25ed23afdfaf4a12b149ff276965b043}

## 경고 {#alerts}

이 참조는 Adobe Experience Platform Auditor에서 테스트에 대해 표시하는 경고에 대한 자세한 정보를 제공합니다.

알림은 인지해야 하는 문제를 보여주지만 점수에 영향을 주지 않습니다. 이러한 우수 사례 추천은 경우에 따라 구현에 적용되지 않을 수 있습니다.

<table id="table_031432C9BB804A6F90E7FF572739E169"> 
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
    --> <p><b>Advertising Cloud - 구현된 변환 태그 수정</b> </p> <p>가중치: 0 </p> </td> 
   <td colname="col2"> <p>올바른 변환 태그가 사용되는지 확인합니다. </p> <p> <p>경고: 더 이상 사용되지 않는 TubeMogul 변환 태그를 사용하면 데이터가 손실될 수 있습니다. </p> </p> </td> 
   <td colname="col3"> <p>변환 픽셀을 새로운 Advertising Cloud 이미지 전용 변환 태그로 업그레이드합니다. </p> <p>Adobe Experience Platform Launch의 Advertising Cloud 확장을 사용하면 이러한 작업을 손쉽게 수행할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Advertising Cloud - 사용된 JS 태그 수정</b> </p> <p>가중치: 0 </p> </td> 
   <td colname="col2"> <p>Advertising Cloud는 최신 JavaScript 태그를 사용해야 합니다. </p> </td> 
   <td colname="col3"> <p>Advertising Cloud JavaScript를 최신 버전으로 업그레이드하십시오. 더 이상 사용되지 않는 JavaScript 버전을 사용하면 기능이 손실될 수 있습니다. </p> <p>이 작업은 Platform Launch용 Advertising Cloud 확장을 사용하여 보다 손쉽게 수행할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Advertising Cloud - 이미지 전용 태그</b> </p> <p>가중치: 0 </p> </td> 
   <td colname="col2"> <p>Advertising Cloud 이미지 픽셀 형식은 다음 권장 형식 중 하나와 일치해야 합니다. </p> <p> 
     <ul id="ul_D85BE9C8A8654DE890E1A814E3573D86"> 
      <li id="li_E2AEDD76AC7044E8AD6AE8375858D198"> <p><span class="codeph"> http(s)://rtd.tubemogul.com/upi/?sid=&lt;HASH_VALUE&gt;</span> </p> </li> 
      <li id="li_1EEFA03516BF445294B5EC5DED891758"> <p><span class="codeph"> http(s)://rtd-tm.everesttech.net/upi/?sid=&lt;HASH_VALUE&gt;</span> </p> </li> 
      <li id="li_F72206B142214217BDD34356D2F3D8AD"> <p><span class="codeph"> http(s)://pixel.everesttech.net/px2/&lt;NUMERIC_ID&gt;?</span> </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Advertising Cloud 픽셀을 새로운 Advertising Cloud 이미지 전용 태그로 업그레이드하여 전체 Advertising Cloud 기능을 활용할 수 있습니다. </p> <p>Platform Launch의 Advertising Cloud 확장을 사용하면 이러한 작업을 손쉽게 수행할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Advertising Cloud - 세그먼트 픽셀 DSP 동기화 사용</b> </p> <p>가중치: 0 </p> </td> 
   <td colname="col2"> <p>TubeMogul 세그먼트 픽셀에 DSP 동기화 설정이 포함되어 있는지 확인하고 픽셀에 설정을 추가하는 것이 좋습니다. </p> <p>DSP 동기화 설정은 쿼리 문자열 매개 변수를 사용하여 결정되므로 </p> <p>태그를 실행하는 경우<span class="codeph">("https://rtd.tubemogul.com/upi/?sid=&lt;HASH_VALUE&gt;"</span> </p> <p> 또는 <span class="codeph">"http(s)://rtd-tm.everesttech.net/upi/?sid=&lt;HASH_VALUE&gt;"</span> </p> <p> 또는 <span class="codeph">"http(s)://pixel.everesttech.net/px2/&lt;NUMERIC_ID&gt;?"</span> </p> <p>그리고 태그에 URL 매개 변수 <span class="codeph">"sid="가 포함)</span> </p> <p>URL 매개 변수 <span class="codeph">"cs=0"</span> 또는<span class="codeph"> "cs=1"</span>이 <span class="codeph">있는지 확인하고, 없다면 대상 일치율이 향상될 수 있도록</span> "cs=1"을 해당 픽셀에 추가하는 것이 좋습니다. </p> </td> 
   <td colname="col3"> <p> DSP 동기화가 발생할 수 있도록 URL 매개 변수 <span class="codeph">"cs=1"</span>을 Advertising Cloud 픽셀에 추가하여 대상 일치율을 높입니다. </p> <p>Platform Launch의 Advertising Cloud 확장을 사용하면 이러한 작업을 손쉽게 수행할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>DTM - pageBottom 콜백 배치</b> </p> <p>가중치: 0 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/dtm/using/client-side/t-add-header-fooder-code.html" format="html" scope="external"> 추가 정보</a> </p> 
    <!--
      TEa9df69942f404055a64262889c8b21d3 
    --> </td> 
   <td colname="col2"> <p>Dynamic Tag Management에는 <span class="codeph">_satellite.pageBottom()</span> 함수가 필요합니다. 닫기 body 태그 바로 앞에 인라인 스크립트를 추가하여 DTM 기능이 적절히 작동하도록 합니다. </p> <p> <p>참고: 태그가 <i>&lt;body&gt;</i>의 마지막<span class="codeph"> 태그가 되는 것이 좋습니다</span>. <span class="codeph">&lt;body&gt; </span>태그 내에 있는 경우에도 작동할 수도 있지만, 우수 사례가 아니므로 제대로 기능하지 않거나 예기치 않거나 원치 않는 결과로 작동할 수 있습니다. </p> </p> </td> 
   <td colname="col3"> <p>닫기 <span class="codeph">&lt;/body&gt;</span> 태그 바로 앞에 인라인 스크립트를 추가하여 DTM 기능이 적절히 작동하도록 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>DTM - 자체 호스팅</b> </p> <p>가중치: 0 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/dtm/using/client-side/client-side-information.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> DTM 라이브러리는 <span class="filepath">assets.adobedtm.com</span>의 Adobe Akamai 인스턴스에서 호스팅 중입니다. </p> <p> 자체 호스팅은 캐시 제어를 통해 웹 사이트 성능을 더욱 강력하게 제어하고 타사 스크립트 의존성을 줄이며 게시 프로세스를 더욱 강력하게 제어할 수 있기 때문에 DTM을 로드하는 데 권장되는 방법입니다. DTM 라이브러리는 자체 웹 호스팅 또는 CDN을 통해 호스팅 및 관리할 수 있습니다. </p> </td> 
   <td colname="col3"> <p>자체 호스팅은 페이지에서 DTM을 로드하는 데 권장되는 방법입니다. Akamai CDN을 통한 DTM 호스팅은 대부분의 경우 작동하지만 자체 호스팅이 페이지 성능을 향상시킵니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b> Experience Cloud ID 서비스 - AdobeOrg 하나만 사용</b> </p> <p>가중치: 0 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/id-service/using/intro/id-request.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>일반적인 MCID 구현에서는 단일 AdobeOrg를 사용해야 합니다. </p> </td> 
   <td colname="col3"> <p>이 구현에 대해 여러 AdobeOrg ID가 있는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Launch - pageBottom 콜백 배치</b> </p> <p>가중치: 0 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/launch/using/intro/get-started/quick-start.html" format="html" scope="external"> 추가 정보</a> </p> 
    <!--
      TE48c499b022f545c5bccc6f8bde169685 
    --> </td> 
   <td colname="col2"> <p>Platform Launch를 동기식으로 배포한 경우 페이지 본문에서 <span class="codeph">pageBottom </span>콜백 함수를 마지막으로 정의해야 합니다 </p> <p> <p>참고: 태그가 <i>&lt;body&gt;</i>의 마지막<span class="codeph"> 태그가 되는 것이 좋습니다</span>. <span class="codeph">&lt;body&gt; </span>태그 내에 있는 경우에도 작동할 수도 있지만, 우수 사례가 아니므로 제대로 기능하지 않거나 예기치 않거나 원치 않는 결과로 작동할 수 있습니다. </p> </p> </td> 
   <td colname="col3"> <p>닫기 <span class="codeph">&lt;/body&gt;</span> 태그 바로 앞에 인라인 스크립트를 추가하여 DTM 기능이 적절히 작동하도록 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Launch - 자체 호스팅</b> </p> <p>가중치: 0 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/launch/using/intro/get-started/quick-start.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>Platform Launch 라이브러리는 <span class="filepath">assets.adobedtm.com</span>의 Adobe Akamai 인스턴스에서 호스팅 중입니다. </p> <p>자체 호스팅은 캐시 제어를 통해 웹 사이트 성능을 더욱 강력하게 제어하고 타사 스크립트 의존성을 줄이며 게시 프로세스를 더욱 강력하게 제어할 수 있기 때문에 Platform Launch를 로드하는 데 권장되는 방법입니다. Platform Launch 라이브러리는 자체 웹 호스팅 또는 CDN을 통해 호스팅 및 관리할 수 있습니다. </p> </td> 
   <td colname="col3"> <p>Akamai CDN을 통한 Platform Launch 호스팅은 대부분의 경우 작동하지만 페이지 성능을 개선하기 위한 첫 번째 단계로 자체 호스팅이 구현되는 것이 좋습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Launch - 비동기적으로 배포해야 함</b> </p> <p>가중치: 0 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/launch/using/intro/get-started/quick-start.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>최적의 성능을 위해 Platform Launch를 비동기적으로 배포해야 합니다. </p> </td> 
   <td colname="col3"> <p>인라인 스크립트에 async 매개 변수를 포함시켜 적절한 비동기 Platform Launch 기능인지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b> Target - mboxDefault의 콘텐츠</b> </p> <p>가중치: 0 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/target/using/implement-target/implementing-target.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> at.js를 사용할 때는 mboxDefault에 콘텐츠가 있어야 합니다. </p> </td> 
   <td colname="col3"> <p>콘텐츠를 사용할 수 있는지 확인합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 구성 {#configuration}

이 참조는 Platform Auditor가 구성을 위해 수행하는 테스트에 대한 자세한 정보를 제공합니다.

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
    --> <p><b>Launch - 최신 버전</b> </p> <p>가중치: 2 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/launch/using/intro/get-started/quick-start.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>이러한 페이지에서 최신 버전의 Platform Launch 코드 라이브러리(Turbine)를 실행하고 있지 않습니다. 향상된 성능을 활용하고 최신 기능을 제공하기 위해 Experience Cloud 기술을 지원하는 코드 라이브러리가 지속적으로 업데이트 및 변경되고 있습니다. </p> </td> 
   <td colname="col3"> <p> Platform Launch 라이브러리를 다시 구축 및 게시하여 Platform Launch 라이브러리를 업데이트합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Target - 최신 버전</b> </p> <p>가중치: 2 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/dtm/using/tools/target.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 페이지에서 최신 버전의 Target 코드 라이브러리를 실행하고 있지 않습니다. 향상된 성능을 활용하고 최신 기능을 제공하기 위해 Experience Cloud 기술을 지원하는 코드 라이브러리가 지속적으로 업데이트 및 변경되고 있습니다. </p> </td> 
   <td colname="col3"> <p>최신 버전의 Target 라이브러리를 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Target - mboxDefault가 mboxCreate보다 우선함 </b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/target/using/implement-target/implementing-target.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p><span class="codeph">mboxCreate</span>의 적절한 사용은 다음과 유사합니다. </p> <p> <span class="codeph"> &lt;div class="mboxDefault"&gt;&lt;!-Customer content--&gt;&lt;/div&gt;&lt;script&gt;mboxCreate('myMboxName')&lt;/script&gt;</span> </p> </td> 
   <td colname="col3"> <p><span class="codeph">mboxCreate()</span>를 호출하기 전에 <span class="codeph">&lt;div class="mboxDefault"&gt;&lt;/div&gt;</span> 태그를 포함해야 합니다. at.js는 사용자를 위해 추가하지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Target - 유효한 DOCTYPE</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/target/using/implement-target/implementing-target.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 잘못된 DOCTYPE이 검색되었습니다. 이 시나리오에서는 mbox가 실행되지 않습니다. </p> <p>at.js의 경우 DOCTYPE이 표준 모드여야 합니다. 그렇지 않으면 Target이 작동하지 않습니다. </p> </td> 
   <td colname="col3"> <p>페이지에서 DOCTYPE을 업데이트합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 태그 일관성 {#tag-consistency}

이 참조는 Platform Auditor가 태그 일관성을 위해 수행하는 테스트에 대한 자세한 정보를 제공합니다.

Platform Auditor의 일관성 테스트는 검사한 모든 페이지에서 일치하지 않는 것을 찾습니다. 이는 정확한 데이터 수집을 위해 사이트의 모든 페이지에서 동일해야 하는 값 또는 구성입니다.

<table id="table_4F9ED873BAF741D19BFB0F297B3A1FDB"> 
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
    --> <p><b>Analytics - 일관된 코드 버전 </b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/analytics/implementation/home.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 둘 이상의 Analytics 코드 버전을 찾았습니다. </p> </td> 
   <td colname="col3"> <p>Analytics의 모든 인스턴스를 현재 버전으로 바꿉니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 태그 유무 {#tag-presence}

이 참조는 Platform Auditor가 태그 존재 확인을 위해 수행하는 테스트에 대한 자세한 정보를 제공합니다.

Platform Auditor는 태그의 존재 여부, 페이지 코드가 올바른 위치에 있는지 여부를 평가합니다.

<table id="table_98A2E3F7B3154EEFA76D0CAE2FE97CAB"> 
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
    --> <p><b>Advertising Cloud - 코드 유무</b> </p> <p>가중치: 5 </p> </td> 
   <td colname="col2"> <p> Advertising Cloud 태그는 DOM에서 사용할 수 없습니다. </p> </td> 
   <td colname="col3"> <p>Platform Launch의 Advertising Cloud 확장을 사용하여 Advertising Cloud 태그를 구현합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Advertising Cloud - 구현된 세그먼트 픽셀</b> </p> <p>가중치: 5 </p> </td> 
   <td colname="col2"> <p> Advertising Cloud 세그먼트 픽셀을 새로운 Advertising Cloud 이미지 전용 태그로 업그레이드합니다. 더 이상 사용되지 않는 AMO 세그먼트 태그를 사용하면 데이터가 손실될 수 있습니다. </p> </td> 
   <td colname="col3"> <p>Platform Launch용 Advertising Cloud 확장을 사용하여 Advertising Cloud 세그먼트 픽셀을 구현합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Analytics - DOM에서 로드됨</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/analytics/implementation/home.html" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> Adobe Analytics 태그가 검색되지 않았습니다. </p> </td> 
   <td colname="col3"> <p>최신 버전의 Analytics를 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b> DTM - 라이브러리가 로드됨</b> </p> <p>가중치: 5 </p> <p>추가 정보: </p> <p> 
     <ul id="ul_7E706EBC2E4649A69732E6982E116E22"> 
      <li id="li_9AF0257E39C347A9AE6D8D8FFBD66B38"><a href="https://docs.adobe.com/content/help/ko-KR/dtm/using/admin/c-troubleshooting.html" format="html" scope="external"> DTM 문제 해결</a> </li> 
      <li id="li_7B422BCCD2654B0A9059799FB5276BE8"><a href="https://docs.adobe.com/content/help/ko-KR/dtm/using/client-side/t-add-header-fooder-code.html" format="html" scope="external"> 머리글 및 바닥글 코드 추가</a> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p> 전역 _satellite 개체를 DOM에서 찾을 수 없습니다. Dynamic Tag Management가 설치되지 않았거나 실행되지 않았습니다. </p> </td> 
   <td colname="col3"> <p>DTM 라이브러리가 페이지에 구현되어 있고 후속 스크립트 활동에서 차단되지 않았는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b> DTM - 하나의 포함 코드</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/dtm/using/client-side/code.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 프로덕션 사이트는 하나의 DTM 라이브러리만 로드해야 합니다. </p> </td> 
   <td colname="col3"> <p>프로덕션 라이브러리만 페이지에 로드되고 있는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>DTM - pageBottom 콜백이 &lt;body&gt;에 있음</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/dtm/using/client-side/t-add-header-fooder-code.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> Dynamic Tag Management에 필요한 <span class="codeph">_satellite.pageBottom()</span> 콜백을 페이지의 <span class="codeph">&lt;body&gt;</span> 내에서 찾을 수 없습니다. </p> <p>페이지에서 <span class="codeph">pageBottom </span>호출을 전혀 찾을 수 없거나 <span class="codeph">&lt;head&gt;</span> 태그(또는 기타 예기치 않은 위치)에 있는 경우 이 테스트가 실패합니다. <span class="codeph">pageBottom</span>이 <span class="codeph">&lt;body&gt;</span> 태그 내 어딘가에 있는 경우에만 전달됩니다. 페이지에 전혀 없으면 작동하지 않으며 다른 두 개의 <span class="codeph">pageBottom</span> 테스트 또한 실패합니다. </p> </td> 
   <td colname="col3"> <p>닫기 <span class="codeph">&lt;/body&gt;</span> 태그 바로 앞에 인라인 스크립트를 추가하여 DTM 기능이 적절히 작동하도록 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>DTM - pageBottom 태그가 실행됨</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/dtm/using/client-side/t-add-header-fooder-code.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> DTM <span class="codeph">pageBottom</span> 태그가 검색되지 않았습니다. </p> <p>이 문제는 호출이 <span class="codeph">if (false) {_satellite.pageBottom()}</span>와 유사한 결과를 가져오는 <span class="codeph">if</span>문 내에 있을 경우 발생할 수 있습니다. 따라서 태그가 존재하고 올바르게 배치되어 있더라도 태그가 실행되지 않을 수 있습니다. </p> </td> 
   <td colname="col3"> <p>모든 페이지에 DTM <span class="codeph">pageBottom</span> 호출을 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Experience Cloud ID Service - 코드 유무</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/id-service/using/implementation/implementation-methods.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>Experience Cloud ID Service 코드를 찾을 수 없습니다. Experience Cloud ID(MCID)는 Experience Cloud 솔루션의 가치를 극대화하기 위해 매우 권장되며 Experience Cloud 솔루션 전반에서 매우 중요합니다. </p> </td> 
   <td colname="col3"> <p> 최신 버전의 MCID를 설치하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Experience Cloud ID Service - 쿠키 유무</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/id-service/using/implementation/implementation-guides.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> AMCV_</span> 쿠키를 찾을 수 없습니다. <span class="codeph"> VisitorAPI.js</span> 코드에서 방문자 개체를 인스턴스화해야 합니다. </p> </td> 
   <td colname="col3"> <p> DTM 구현인 경우 AdobeOrg ID가 MCID 도구에 제대로 입력되었는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Experience Cloud ID Service - MID 값 유무</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/id-service/using/intro/cookies.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> <span class="codeph">AMCV_</span> 쿠키에 MID 값이 없습니다. </p> </td> 
   <td colname="col3"> <p>다시 테스트하여 MCID API 지연을 확인합니다. 상태가 지속되면 Adobe 고객 지원 센터에 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b> Launch - 라이브러리가 로드됨</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/launch/using/intro/get-started/quick-start.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 전역 _satellite 개체를 DOM에서 찾을 수 없습니다. Launch가 설치되지 않거나 실행되지 않습니다. </p> </td> 
   <td colname="col3"> <p>Platform Launch 라이브러리가 페이지에 구현되어 있고 후속 스크립트 활동에서 차단되지 않았는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Launch - 여러 개의 포함 스크립트가 없음</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/launch/using/intro/get-started/quick-start.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>페이지에 여러 개의 포함 스크립트가 로드되어서는 안 됩니다. 프로덕션 사이트는 하나의 Platform Launch 라이브러리만 로드해야 합니다. </p> </td> 
   <td colname="col3"> <p>프로덕션 라이브러리만 페이지에 로드되고 있는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Launch - pageBottom 콜백이 &lt;body&gt;에 있음</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/launch/using/intro/get-started/quick-start.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> Platform Launch에 필요한 <span class="codeph">_satellite.pageBottom()</span> 콜백을 페이지의 <span class="codeph">&lt;body&gt;</span> 내에서 찾을 수 없습니다. </p> <p>페이지에서 <span class="codeph">pageBottom </span>호출을 전혀 찾을 수 없거나 <span class="codeph">&lt;head&gt;</span> 태그(또는 기타 예기치 않은 위치)에 있는 경우 이 테스트가 실패합니다. <span class="codeph">pageBottom</span>이 <span class="codeph">&lt;body&gt;</span> 태그 내 어딘가에 있는 경우에만 전달됩니다. 페이지에 전혀 없으면 작동하지 않으며 다른 두 개의 <span class="codeph">pageBottom</span> 테스트 또한 실패합니다. </p> </td> 
   <td colname="col3"> <p>닫기 <span class="codeph">&lt;/body&gt;</span> 태그 바로 앞에 인라인 스크립트를 추가하여 Platform Launch 기능이 적절히 작동하도록 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b>Launch - pageBottom 콜백은 비동기적으로 배포할 때 존재하지 않아야 합니다.</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/launch/using/intro/get-started/quick-start.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>페이지에서 <span class="codeph">_satellite.pageBottom()</span> 콜백이 발견되었으며, 이는 Platform Launch가 비동기적으로 배포된 경우에는 해당되지 않습니다. </p> </td> 
   <td colname="col3"> <p><span class="codeph">_satellite.pageBottom()</span> 스크립트를 제거하여 적절한 Platform Launch 기능을 활성화합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b> Target - 코드 여부</b> </p> <p>가중치: 5 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/target/using/implement-target/implementing-target.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>DOM에서 Target을 정의해야 합니다. </p> </td> 
   <td colname="col3"> <p>최신 버전의 Target (at.js)을 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <!--
      1.0.1 
    --> <p><b> Target - &lt;head&gt;에 로드된 라이브러리</b> </p> <p>가중치: 4 </p> <p><a href="https://docs.adobe.com/content/help/ko-KR/target/using/implement-target/implementing-target.html" format="html" scope="external"> 추가 정보</a> </p> 
    <!--
      TE61c380082a4b4706b28a84aa047599a7 
    --> </td> 
   <td colname="col2"> <p> Target 라이브러리는 <span class="codeph">&lt;head&gt;</span> 태그에 로드되어야 합니다. </p> </td> 
   <td colname="col3"> <p> Target 라이브러리가 <span class="codeph">&lt;head&gt;</span> 태그에 로드되었는지 확인합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

