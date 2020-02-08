---
description: 이 참조에서는 Auditor가 태그 존재에 대해 수행하는 테스트에 대한 자세한 정보를 제공합니다.
seo-description: 이 참조에서는 Auditor가 태그 존재에 대해 수행하는 테스트에 대한 자세한 정보를 제공합니다.
seo-title: 태그 존재
title: 태그 존재
uuid: 91aa355b-7022-431c-9837-e108b5ce604d
translation-type: tm+mt
source-git-commit: c697f3d759ad1f086f16a39e03062431583ffd7f

---


# 태그 존재

이 참조에서는 Auditor가 태그 존재에 대해 수행하는 테스트에 대한 자세한 정보를 제공합니다.

Auditor는 태그가 있는지 여부와 페이지 코드의 올바른 위치에 있는지 여부를 평가합니다.

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
   <td colname="col1"> <p><b>Advertising Cloud - 코드 프레젠스</b> </p> <p>두께:5 </p> </td> 
   <td colname="col2"> <p> Advertising Cloud 태그는 DOM에서 사용할 수 없습니다. </p> </td> 
   <td colname="col3"> <p>Advertising Cloud Launch Extension을 사용하여 Advertising Cloud 태그를 구현합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Advertising Cloud - 구현된 세그먼트 픽셀</b> </p> <p>두께:5 </p> </td> 
   <td colname="col2"> <p> Advertising Cloud 세그먼트 픽셀을 새 Advertising Cloud 이미지 전용 태그로 업그레이드합니다. 더 이상 사용되지 않는 AMO 세그먼트 태그를 사용하면 데이터가 손실될 수 있습니다. </p> </td> 
   <td colname="col3"> <p>Advertising Cloud 시작 확장을 사용하여 Advertising Cloud 세그먼트 픽셀을 구현합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Analytics - DOM에서 로드됨</b> </p> <p>두께:5 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/sc/implement/" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> Adobe Analytics 태그가 검색되지 않았습니다. </p> </td> 
   <td colname="col3"> <p>최신 버전의 Analytics를 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> DTM - 라이브러리가 로드됨</b> </p> <p>두께:5 </p> <p>추가 정보: </p> <p> 
     <ul id="ul_7E706EBC2E4649A69732E6982E116E22"> 
      <li id="li_9AF0257E39C347A9AE6D8D8FFBD66B38"><a href="https://docs.adobe.com/content/help/en/dtm/using/admin/c-troubleshooting.html" format="html" scope="external"> DTM 문제 해결</a> </li> 
      <li id="li_7B422BCCD2654B0A9059799FB5276BE8"><a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/t-add-header-fooder-code.html" format="html" scope="external"> 머리글 및 바닥글 코드 추가</a> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p> 전역 _satellite 개체를 DOM에서 찾을 수 없습니다. 다이내믹 태그 관리가 설치되지 않았거나 실행되지 않았습니다. </p> </td> 
   <td colname="col3"> <p>DTM 라이브러리가 페이지에 구현되어 있고 후속 스크립트 활동에서 차단되지 않았는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> DTM - 하나의 포함 코드</b> </p> <p>두께:5 </p> <p><a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/code.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 프로덕션 사이트는 하나의 DTM 라이브러리만 로드해야 합니다. </p> </td> 
   <td colname="col3"> <p>프로덕션 라이브러리만 페이지에 로드되어 있는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>DTM - pageBottom 콜백이 &lt;body&gt;에 있음</b> </p> <p>두께:5 </p> <p><a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/t-add-header-fooder-code.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 다이내믹 태그 관리에 필요한 <span class="codeph"> &lt;body&gt;</span> 페이지 내에서 _satellite.pageBottom() <span class="codeph"></span> 콜백을 찾을 수 없습니다. </p> <p>페이지에서 page Bottom <span class="codeph"></span>호출을 전혀 찾을 수 없거나 <span class="codeph"> &lt;head&gt;</span> 태그(또는 기타 예기치 않은 위치)에 있는 경우 이 테스트가 실패합니다. pageBottom이 <span class="codeph"> &lt;body&gt;</span> 태그 내 어딘가에 있는 경우에만 전달됩니다 <span class="codeph"></span> . 페이지에 전혀 없으면 작동하지 않고 다른 두 페이지인 하위 <span class="codeph"> 테스트도</span> 실패합니다. </p> </td> 
   <td colname="col3"> <p>닫는 <span class="codeph"> &lt;/body&gt;</span> 태그 바로 앞에 인라인 스크립트를 추가하여 적절한 DTM 기능을 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>DTM - pageBottom 태그가 실행됨</b> </p> <p>두께:5 </p> <p><a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/t-add-header-fooder-code.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> DTM <code> pageBottom</code> 태그가 검색되지 않았습니다. </p> <p>이 문제는 호출이 <code> if</code> 문 내에 있을 때 발생할 수 있습니다. 이 경우 비슷한 결과가 <code> if (false) {_satellite.pageBottom()}</code>발생합니다. 따라서 태그가 존재하고 올바르게 배치되는 동안 태그가 실행되지 않을 수 있습니다. </p> </td> 
   <td colname="col3"> <p>모든 페이지에 DTM <code> pageBottom</code> 호출을 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Experience Cloud ID 서비스 - 코드 현재 상태</b> </p> <p>두께:5 </p> <p><a href="https://docs.adobe.com/content/help/en/id-service/using/intro/overview.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>Experience Cloud ID 서비스 코드를 찾을 수 없습니다. Experience Cloud ID(MCID)는 Experience Cloud 솔루션의 가치를 최대한 활용하고 Experience Cloud 솔루션 간의 ID 관리에 중요한 역할을 하도록 권장됩니다. </p> </td> 
   <td colname="col3"> <p> 최신 버전의 MCID를 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Experience Cloud ID 서비스 - 쿠키 현재 상태</b> </p> <p>두께:5 </p> <p><a href="https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/implementation-guides.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> AMCV <span class="codeph"> _</span> 쿠키를 찾을 수 없습니다. VisitorAPI.js 코드에서 방문자 <span class="codeph"> 개체를 인스턴스화해야</span> 합니다. </p> </td> 
   <td colname="col3"> <p> DTM 구현인 경우 AdobeOrg ID가 MCID 도구에 제대로 입력되었는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Experience Cloud ID 서비스 - MID 값이 있음</b> </p> <p>두께:5 </p> <p><a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> AMCV_ <span class="codeph"></span> 쿠키에 MID 값이 없습니다. </p> </td> 
   <td colname="col3"> <p>다시 테스트하여 MCID API 지연을 확인합니다. 상태가 지속되면 Adobe 고객 지원 센터에 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.5 
    </draft-comment> <p><b> 시작 - 라이브러리가 로드됨</b> </p> <p>두께:5 </p> <p><a href="https://docs.adobe.com/content/help/en/launch/using/intro/get-started/quick-start.html" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> 전역 _satellite 개체를 DOM에서 찾을 수 없습니다. 론치가 설치되지 않았거나 실행되지 않았습니다. </p> </td> 
   <td colname="col3"> <p>Launch 라이브러리가 페이지에 구현되어 있고 후속 스크립트 활동에서 차단되지 않았는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.5 
    </draft-comment> <p><b>시작 - 여러 개의 포함 스크립트가 없음</b> </p> <p>두께:5 </p> <p><a href="https://docs.adobe.com/content/help/en/launch/using/intro/get-started/quick-start.html" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>페이지에 여러 개의 포함 스크립트가 로드되면 안 됩니다. 프로덕션 사이트는 하나의 Launch 라이브러리만 로드해야 합니다. </p> </td> 
   <td colname="col3"> <p>프로덕션 라이브러리만 페이지에 로드되어 있는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.5 
    </draft-comment> <p><b>Launch - pageBottom 콜백이 &lt;body&gt;에 있음</b> </p> <p>두께:5 </p> <p><a href="https://docs.adobe.com/content/help/en/launch/using/intro/get-started/quick-start.html" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> _satellite.pageBottom() <span class="codeph"> 콜백을 페이지의</span> &lt;body&gt; <span class="codeph"></span> 내에서 찾을 수 없습니다. 이 콜백은 Launch에 필요합니다. </p> <p>페이지에서 page Bottom <span class="codeph"></span>호출을 전혀 찾을 수 없거나 <span class="codeph"> &lt;head&gt;</span> 태그(또는 기타 예기치 않은 위치)에 있는 경우 이 테스트가 실패합니다. pageBottom이 <span class="codeph"> &lt;body&gt;</span> 태그 내 어딘가에 있는 경우에만 전달됩니다 <span class="codeph"></span> . 페이지에 전혀 없으면 작동하지 않고 다른 두 페이지인 하위 <span class="codeph"> 테스트도</span> 실패합니다. </p> </td> 
   <td colname="col3"> <p>닫기 <span class="codeph"> &lt;/body&gt;</span> 태그 바로 앞에 인라인 스크립트를 추가하여 적절한 Launch 기능을 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.5 
    </draft-comment> <p><b>Launch - pageBottom 콜백은 비동기적으로 배포할 때 존재하지 않아야 합니다.</b> </p> <p>두께:5 </p> <p><a href="https://docs.adobe.com/content/help/en/launch/using/intro/get-started/quick-start.html" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>페이지에서 <span class="codeph"> _satellite.pageBottom()</span> 콜백이 발견되었으며, 이는 Launch가 비동기적으로 배포된 경우에는 해당되지 않습니다. </p> </td> 
   <td colname="col3"> <p>_satellite<span class="codeph"> .pageBottom()</span> 스크립트를 제거하여 적절한 Launch 기능을 활성화합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b> Target - 코드 존재</b> </p> <p>두께:5 </p> <p><a href="https://docs.adobe.com/content/help/en/target/using/implement-target/implementing-target.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>DOM에서 Target을 정의해야 합니다. </p> </td> 
   <td colname="col3"> <p>최신 버전의 Target(at.js)을 설치합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Target - &lt;head&gt;에 로드된 라이브러리</b> </p> <p>두께:4 </p> <p><a href="https://docs.adobe.com/content/help/en/target/using/implement-target/implementing-target.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> Target 라이브러리는 <span class="codeph"> &lt;head&gt;</span> 태그에 로드되어야 합니다. </p> </td> 
   <td colname="col3"> <p> Target 라이브러리가 <span class="codeph"> &lt;head&gt;</span> 태그에 로드되었는지 확인합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
