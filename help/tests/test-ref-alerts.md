---
description: 이 참조는 Auditor가 테스트에 대해 표시하는 경고에 대한 자세한 정보를 제공합니다.
seo-description: 이 참조는 Auditor가 테스트에 대해 표시하는 경고에 대한 자세한 정보를 제공합니다.
seo-title: 경고
title: 경고
uuid: 8f05b3c1-2427-4691-a88f-1de98f120a02
translation-type: ht
source-git-commit: 762ff31ca4d5ed69d1b813589e419c51a40d5920

---


# 경고{#alerts}

이 참조는 Auditor가 테스트에 대해 표시하는 경고에 대한 자세한 정보를 제공합니다.

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
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Advertising Cloud - 구현된 변환 태그 수정</b> </p> <p>가중치: 0 </p> </td> 
   <td colname="col2"> <p>올바른 변환 태그가 사용되는지 확인합니다. </p> <p> <p>경고: 더 이상 사용되지 않는 TubeMogul 변환 태그를 사용하면 데이터가 손실될 수 있습니다. </p> </p> </td> 
   <td colname="col3"> <p>변환 픽셀을 새로운 Advertising Cloud 이미지 전용 변환 태그로 업그레이드합니다. </p> <p>Advertising Cloud Launch Extension을 사용하면 이러한 기능을 가장 쉽게 수행할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Advertising Cloud - 사용된 JS 태그 수정</b> </p> <p>가중치: 0 </p> </td> 
   <td colname="col2"> <p>Advertising Cloud는 최신 JavaScript 태그를 사용해야 합니다. </p> </td> 
   <td colname="col3"> <p>Advertising Cloud JavaScript를 최신 버전으로 업그레이드하십시오. 더 이상 사용되지 않는 JavaScript 버전을 사용하면 기능이 손실될 수 있습니다. </p> <p>이 작업은 Advertising Cloud Launch Extension을 사용하여 보다 손쉽게 수행할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Advertising Cloud - 이미지 전용 태그</b> </p> <p>가중치: 0 </p> </td> 
   <td colname="col2"> <p>Advertising Cloud 이미지 픽셀 형식은 다음 권장 형식 중 하나와 일치해야 합니다. </p> <p> 
     <ul id="ul_D85BE9C8A8654DE890E1A814E3573D86"> 
      <li id="li_E2AEDD76AC7044E8AD6AE8375858D198"> <p><span class="codeph"> http(s)://rtd.tubemogul.com/upi/?sid=&lt;HASH_VALUE&gt;</span> </p> </li> 
      <li id="li_1EEFA03516BF445294B5EC5DED891758"> <p><span class="codeph"> http(s)://rtd-tm.everesttech.net/upi/?sid=&lt;HASH_VALUE&gt;</span> </p> </li> 
      <li id="li_F72206B142214217BDD34356D2F3D8AD"> <p><span class="codeph"> http(s)://pixel.everesttech.net/px2/&lt;NUMERIC_ID&gt;?</span> </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Advertising Cloud 픽셀을 새로운 Advertising Cloud 이미지 전용 태그로 업그레이드하여 전체 Advertising Cloud 기능을 활용할 수 있습니다. </p> <p>Advertising Cloud Launch Extension을 사용하면 이러한 기능을 가장 쉽게 수행할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Advertising Cloud - 세그먼트 픽셀 DSP 동기화 사용</b> </p> <p>가중치: 0 </p> </td> 
   <td colname="col2"> <p>TubeMogul 세그먼트 픽셀에 DSP 동기화 설정이 포함되어 있는지 확인하고 픽셀에 설정을 추가하는 것이 좋습니다. </p> <p>DSP 동기화 설정은 쿼리 문자열 매개 변수를 사용하여 결정되므로 </p> <p>태그를 실행하는 경우<span class="codeph">("https://rtd.tubemogul.com/upi/?sid=&lt;HASH_VALUE&gt;"</span> </p> <p> 또는 <span class="codeph">"http(s)://rtd-tm.everesttech.net/upi/?sid=&lt;HASH_VALUE&gt;"</span> </p> <p> 또는 <span class="codeph">"http(s)://pixel.everesttech.net/px2/&lt;NUMERIC_ID&gt;?"</span> </p> <p>그리고 태그에 URL 매개 변수 <span class="codeph">"sid="가 포함)</span> </p> <p>URL 매개 변수 <span class="codeph">"cs=0"</span> 또는<span class="codeph"> "cs=1"</span>이 <span class="codeph">있는지 확인하고, 없다면 대상 일치율이 향상될 수 있도록</span> "cs=1"을 해당 픽셀에 추가하는 것이 좋습니다. </p> </td> 
   <td colname="col3"> <p> DSP 동기화가 발생할 수 있도록 URL 매개 변수 <span class="codeph">"cs=1"</span>을 Advertising Cloud 픽셀에 추가하여 대상 일치율을 높입니다. </p> <p>Advertising Cloud Launch Extension을 사용하면 이러한 기능을 가장 쉽게 수행할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      CAce6db25bc8c443409f0fcc5ac9d622c3 
    </draft-comment> <p><b>DTM - pageBottom 콜백 배치</b> </p> <p>가중치: 0 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/ko_KR/dtm/t_add_header_fooder_code.html" format="html" scope="external"> 추가 정보</a> </p> 
    <draft-comment>
      TEa9df69942f404055a64262889c8b21d3 
    </draft-comment> </td> 
   <td colname="col2"> <p>Dynamic Tag Management에는 <span class="codeph">_satellite.pageBottom()</span> 함수가 필요합니다. 닫기 <span class="codeph">&lt;/body&gt;</span> 태그 바로 앞에 인라인 스크립트를 추가하여 DTM 기능이 적절히 작동하도록 합니다. </p> <p> <p>참고: 태그가 <span class="codeph">&lt;body&gt;</span>의 <i>마지막</i> 태그가 되는 것이 좋습니다. <span class="codeph">&lt;body&gt; </span>태그 내에 있는 경우에도 작동할 수도 있지만, 우수 사례가 아니므로 제대로 기능하지 않거나 예기치 않거나 원치 않는 결과로 작동할 수 있습니다. </p> </p> </td> 
   <td colname="col3"> <p>닫기 <span class="codeph">&lt;/body&gt;</span> 태그 바로 앞에 인라인 스크립트를 추가하여 DTM 기능이 적절히 작동하도록 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>DTM - 자체 호스팅</b> </p> <p>가중치: 0 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/ko_KR/dtm/deployment.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> DTM 라이브러리는 <span class="filepath">assets.adobedtm.com</span>의 Adobe Akamai 인스턴스에서 호스팅 중입니다. </p> <p> 자체 호스팅은 캐시 제어를 통해 웹 사이트 성능을 더욱 강력하게 제어하고 타사 스크립트 의존성을 줄이며 게시 프로세스를 더욱 강력하게 제어할 수 있기 때문에 DTM을 로드하는 데 권장되는 방법입니다. DTM 라이브러리는 자체 웹 호스팅 또는 CDN을 통해 호스팅 및 관리할 수 있습니다. </p> </td> 
   <td colname="col3"> <p>자체 호스팅은 페이지에서 DTM을 로드하는 데 권장되는 방법입니다. Akamai CDN을 통한 DTM 호스팅은 대부분의 경우 작동하지만 자체 호스팅이 페이지 성능을 향상시킵니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b> Experience Cloud ID 서비스 - AdobeOrg 하나만 사용</b> </p> <p>가중치: 0 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/ko_KR/mcvid/mcvid_id_request.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>일반적인 MCID 구현에서는 단일 AdobeOrg를 사용해야 합니다. </p> </td> 
   <td colname="col3"> <p>이 구현에 대해 여러 AdobeOrg ID가 있는지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.5 
    </draft-comment> <p><b>Launch - pageBottom 콜백 배치</b> </p> <p>가중치: 0 </p> <p><a href="https://docs.adobelaunch.com/getting-started" format="https" scope="external"> 추가 정보</a> </p> 
    <draft-comment>
      TE48c499b022f545c5bccc6f8bde169685 
    </draft-comment> </td> 
   <td colname="col2"> <p>Launch는 동기식으로 배포된 경우 페이지 본문에서 <span class="codeph">pageBottom </span>콜백 함수를 마지막으로 정의해야 합니다. </p> <p> <p>참고: 태그가 <i>&lt;body&gt;</i>의 마지막<span class="codeph"> 태그가 되는 것이 좋습니다</span>. <span class="codeph">&lt;body&gt; </span>태그 내에 있는 경우에도 작동할 수도 있지만, 우수 사례가 아니므로 제대로 기능하지 않거나 예기치 않거나 원치 않는 결과로 작동할 수 있습니다. </p> </p> </td> 
   <td colname="col3"> <p>Launch는 동기식 배포를 위해 <span class="codeph">_satellite.pageBottom()</span> 함수가 필요합니다. 닫기 <span class="codeph">&lt;/body&gt;</span> 태그 바로 앞에 인라인 스크립트를 추가하여 실행 기능이 적절히 작동하도록 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Launch - 자체 호스팅</b> </p> <p>가중치: 0 </p> <p><a href="https://docs.adobelaunch.com/getting-started" format="https" scope="external"> Launch로 시작하기</a> </p> <p><a href="https://docs.adobelaunch.com/client-side-information/asynchronous-deployment" format="https" scope="external"> Launch 비동기식 배포</a> </p> </td> 
   <td colname="col2"> <p>Launch 라이브러리는 <span class="filepath">assets.adobedtm.com</span>의 Adobe Akamai 인스턴스에서 호스팅 중입니다. </p> <p>자체 호스팅은 캐시 제어를 통해 웹 사이트 성능을 더욱 강력하게 제어하고 타사 스크립트 의존성을 줄이며 게시 프로세스를 더욱 강력하게 제어할 수 있기 때문에 Launch를 로드하는 데 권장되는 방법입니다. Launch 라이브러리는 자체 웹 호스팅 또는 CDN을 통해 호스팅 및 관리할 수 있습니다. </p> </td> 
   <td colname="col3"> <p>Akamai CDN을 통한 Launch 호스팅은 대부분의 경우 작동하지만 페이지 성능을 개선하기 위한 첫 번째 단계로 자체 호스팅이 구현되는 것이 좋습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b>Launch - 비동기적으로 배포해야 함</b> </p> <p>가중치: 0 </p> <p><a href="https://docs.adobelaunch.com/getting-started" format="https" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p>최적의 성능을 위해 Launch를 비동기적으로 배포해야 합니다. </p> </td> 
   <td colname="col3"> <p>인라인 스크립트에 async 매개 변수를 포함시켜 적절한 비동기 Launch 기능인지 확인합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <draft-comment>
      1.0.1 
    </draft-comment> <p><b> Target - mboxDefault의 콘텐츠</b> </p> <p>가중치: 0 </p> <p><a href="https://experiencecloud.adobe.com/resources/help/en_US/target/ov2/r_target-atjs-mboxcreate.html" format="html" scope="external"> 추가 정보</a> </p> </td> 
   <td colname="col2"> <p> at.js를 사용할 때는 mboxDefault에 콘텐츠가 있어야 합니다. </p> </td> 
   <td colname="col3"> <p>콘텐츠를 사용할 수 있는지 확인합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

