---
description: 이 참조는 Adobe Experience Platform Auditor에서 수행하는 테스트에 대한 자세한 정보를 제공합니다.
seo-description: 이 참조는 Adobe Experience Platform Auditor에서 수행하는 테스트에 대한 자세한 정보를 제공합니다.
seo-title: 테스트 참조
title: 테스트 참조
uuid: f1d0769e-a2bd-4cec-acd1-146793644895
translation-type: tm+mt
source-git-commit: 00d184c1fa1eece9eec8f27896bfbf72fa32bfb6
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 100%

---


# 테스트 참조{#test-reference}

이 참조는 Adobe Experience Platform Auditor에서 수행하는 테스트에 대한 자세한 정보를 제공합니다.

**현재 테스트 규칙 버전:** 1.0.5

각 테스트에 가중치가 적용됩니다. 테스트 점수는 할당된 가중치와 동일합니다. 만약 가중치가 5인 테스트에 통과한다면 5점을 받습니다.

* 0: 인지해야 하는 문제에 대해 경고하지만 점수에 영향을 주지 않습니다.
* 1: 최적화를 권장합니다. 데이터 정확성에 영향을 주지 않습니다.
* 2: 이 테스트가 실패하면 Experience Cloud의 최신 기능 및 수정 사항에 액세스할 수 없게 됩니다.
* 3: 효율성 및 구현이 우수 사례를 따르는지 여부를 테스트합니다.
* 4: 장애는 신뢰할 수 없는 데이터를 수집했음을 의미합니다.
* 5: 장애는 데이터 손실이 발생할 수 있음을 의미합니다.

테스트는 통과/실패합니다. 테스트 조건의 준수 여부를 테스트하므로 부분적인 준수에 대한 부분 점수는 없습니다. 예를 들어, 테스트에서 최신 버전의 Adobe 솔루션을 확인했는데 한 버전만 뒤처진 경우, 다섯 버전 뒤처진 것과 동일한 점수를 받게 됩니다. 최신 버전에는 성능 향상 및 버그 수정이 포함되어 있으므로 최신 버전을 사용하는 것이 좋습니다.

레벨 4 또는 5 결과를 수정하는 것이 **좋습니다**.

레벨 1-3 결과를 수정하는 것이 **좋습니다**.

## Platform Auditor는 어떤 Adobe 기술을 평가합니까? {#section-52833b71c05448aaae508e6070a387f5}

* Advertising Cloud DSP
* Advertising Cloud Search
* Analytics
* DTM
* Experience Cloud ID Service(이전 Marketing Cloud ID Service)
* Target

다음 Adobe 솔루션은 현재 테스트 규칙에 포함되어 있지 않습니다. 이러한 솔루션에 대한 지원은 향후 업데이트 시 제공될 수 있습니다.

* Advertising Cloud Creative
* Audience Manager
* Campaign
* Adobe Experience Platform Launch
