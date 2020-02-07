---
description: 이 참조는 Auditor가 구성을 위해 수행하는 테스트에 대한 자세한 정보를 제공합니다.
seo-description: 이 참조는 Auditor가 구성을 위해 수행하는 테스트에 대한 자세한 정보를 제공합니다.
seo-title: 구성
title: 구성
uuid: d40d815c-edfe-48b9-921f-cea1b0b54a0a
translation-type: tm+mt
source-git-commit: c697f3d759ad1f086f16a39e03062431583ffd7f

---


# 구성

이 참조는 Auditor가 구성을 위해 수행하는 테스트에 대한 자세한 정보를 제공합니다.

구성 테스트는 구현의 특정 설정, 값 또는 잠재적인 충돌을 검색합니다. 감사자는 다른 규칙에 대해 태그를 평가하고 권장 우수 사례를 제시합니다.

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
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Advertising Cloud - 전환 이름에는 영숫자만 사용합니다.</b> </p> <p>두께:3 </p> </td> 
   <td colname="col2"> <p>ev_conversion_property_name <span class="codeph"> 매개 변수는 "</span> ev_transid<span class="codeph"> " 매개 변수를 제외하고 숫자 및 소수점 값만 포함해야 합니다(</span>ev_transid <span class="codeph"></span> 값은 텍스트 또는 숫자 값을 포함할 수 있음). </p> <p>ev_ <span class="codeph"> 로 시작하는 URL</span> 매개 변수가 포함된 evertech.net <span class="codeph"> 픽셀을 찾습니다</span>. </p> <p>예: </p> <p><span class="codeph"> http://pixel.everesttech.net/1180/t?ev_page_load=1&amp;ev_revenue=$12&amp;ev_transid=1hf74i47 </span> </p> </td> 
   <td colname="col3"> <p> 거래 속성 매개 변수에는 숫자 및 소수점 값만 포함되어야 합니다. </p> <p> <p>경고: 다른 모든 값 유형은 데이터 손실을 초래할 수 있습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Advertising Cloud - 전환 이름에는 URL 안전 문자가 사용됩니다.</b> </p> <p>두께:3 </p> </td> 
   <td colname="col2"> <p> 전환 속성 이름에는 앰퍼샌드 또는 물음표가 포함될 수 없습니다. </p> <p> 예: </p> <p><span class="codeph"> http://pixel.everesttech.net/1180/t?ev_revenue&amp;order=12&amp;ev_transid=</span> </p> </td> 
   <td colname="col3"> <p>거래 속성 매개 변수에 인코딩되지 않은 앰퍼샌드 또는 물음표가 포함되어 있지 않은지 확인하십시오. 이렇게 하면 URL 형식이 중단됩니다. </p> <p> <p>경고:인코딩되지 않은 앰퍼샌드 또는 물음표가 포함된 속성 매개 변수(예:ev_form <span class="codeph"> Complete?=1</span> 또는 <span class="codeph"> ev_formComplete&amp;Submit=1</span>)로 인해 데이터가 손실될 수 있습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Advertising Cloud - 올바르게 구현된 거래 ID</b> </p> <p>두께:1 </p> </td> 
   <td colname="col2"> <p> 속성 이름은 <span class="codeph"> ev_transid=</span> 비워 둘 수 없습니다. </p> <p>예: </p> <p> <span class="codeph"> http://pixel.everesttech.net/1180/t?ev_page_load=1&amp;ev_revenue= 12&amp; ev_transid=</span> </p> </td> 
   <td colname="col3"> <p>속성 이름 <span class="codeph"> ev_transid=</span> 은 값(<span class="codeph"> ev_transid=</span>) 없이 남겨둘 수 없습니다. 값이 없으면 트랜잭션 데이터 손실이 있을 수 있습니다. ev_transid=에 값을 <span class="codeph"> 할당하거나</span> 픽셀에서 매개 변수를 제거합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Analytics - DOM에서 인스턴스화</b> </p> <p>두께:5 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/sc/implement/impl_testing.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> Adobe Analytics 코드가 설치되지 않았거나 실행되지 않았습니다. 분석 코드가 웹 페이지를 찾을 수 없을 때 0을 반환합니다. </p> </td> 
   <td colname="col3"> <p>Analytics 태그가 페이지에 구현되어 있고 후속 스크립트 활동에서 차단되지 않았는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Analytics - 한 번 인스턴스화</b> </p> <p>두께:5 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/sc/implement/" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> Adobe Analytics 코드가 페이지에서 두 번 이상 검색되었습니다.. 분석 코드가 웹 페이지를 찾을 수 없을 때 0을 반환합니다. </p> </td> 
   <td colname="col3"> <p>페이지에 Analytics 태그가 하나만 있어야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Analytics - 최신 버전</b> </p> <p>두께:3 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/sc/appmeasurement/release" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 페이지에서 최신 버전의 Analytics 코드 라이브러리를 실행하고 있지 않습니다. 향상된 성능을 활용하고 최신 기능을 제공하기 위해 Experience Cloud 기술을 지원하는 코드 라이브러리가 지속적으로 업데이트되고 변경되고 있습니다. 분석 코드가 웹 페이지를 찾을 수 없을 때 0을 반환합니다. </p> </td> 
   <td colname="col3"> <p>최신 버전의 Analytics 라이브러리를 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>DTM - 타사 태그가 DOM 준비 후 비동기적으로 로드됩니다.</b> </p> <p>두께:3 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/dtm/load_order.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>사용자 경험과 정확한 데이터 수집 간의 균형을 맞추기 위해 타사 태그를 DOM에서 바로 트리거해야 합니다. 이렇게 하면 사이트 기능에 영향을 주지 않고 이러한 추적 스크립트가 실행됩니다. </p> </td> 
   <td colname="col3"> <p>타사 픽셀을 실행하는 모든 규칙을 조정하여 DOM 준비에서 문제를 해결합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Experience Cloud ID 서비스 - 최신 버전</b> </p> <p>두께:2 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/dtm/macid.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 페이지에서 방문자 ID 서비스 코드 라이브러리의 최신 버전인 visitorAPI.js를 실행하고 있지 않습니다 <span class="codeph"></span>. 향상된 성능을 활용하고 최신 기능을 제공하기 위해 Experience Cloud 기술을 지원하는 코드 라이브러리가 지속적으로 업데이트되고 변경되고 있습니다. </p> </td> 
   <td colname="col3"> <p>최신 버전의 방문자 ID 서비스 라이브러리를 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>시작 - 최신 버전</b> </p> <p>두께:2 </p> <p><a href="https://docs.adobelaunch.com/getting-started" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>이러한 페이지에는 최신 버전의 론치 코드 라이브러리(터빈)가 실행되고 있지 않습니다. 향상된 성능을 활용하고 최신 기능을 제공하기 위해 Experience Cloud 기술을 지원하는 코드 라이브러리가 지속적으로 업데이트되고 변경되고 있습니다. </p> </td> 
   <td colname="col3"> <p> Launch 라이브러리를 다시 만들고 게시하여 Launch 라이브러리를 업데이트합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Target - 최신 버전</b> </p> <p>두께:2 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/target/dtm/update-target-tool.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 페이지에서 최신 버전의 Target 코드 라이브러리를 실행하고 있지 않습니다. 향상된 성능을 활용하고 최신 기능을 제공하기 위해 Experience Cloud 기술을 지원하는 코드 라이브러리가 지속적으로 업데이트되고 변경되고 있습니다. </p> </td> 
   <td colname="col3"> <p>최신 버전의 Target 라이브러리를 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Target - mboxDefault 앞에 mboxCreate </b> </p> <p>두께:5 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/target/ov2/r_target-atjs-mboxcreate.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>mboxCreate의 적절한 <span class="codeph"></span> 사용은 다음과 비슷합니다. </p> <p> <span class="codeph"> &lt;div class="mboxDefault"&gt;&lt;!-고객 컨텐츠—&gt;&lt;/div&gt;&lt;script&gt;mboxCreate('myMboxName')&lt;/script&gt;</span> </p> </td> 
   <td colname="col3"> <p>mboxCreate() <span class="codeph"> 를 호출하기 전에</span> &lt;div class="mboxDefault"&gt;&lt;/div&gt; <span class="codeph"></span>태그를 포함해야 합니다. at.js는 사용자를 위해 하나를 추가하지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>대상 - 유효한 DOCTYPE</b> </p> <p>두께:5 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/target/ov2/r_target-atjs-mboxcreate.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 잘못된 DOCTYPE이 검색되었습니다. 이 시나리오에서는 mbox가 실행되지 않습니다. </p> <p>at.js의 경우 DOCTYPE이 표준 모드여야 합니다. 그렇지 않으면 Target이 작동하지 않습니다. </p> </td> 
   <td colname="col3"> <p>페이지에서 DOCTYPE을 업데이트합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

