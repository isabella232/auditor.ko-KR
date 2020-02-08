---
description: 필터 포함은 시작 URL에서 감사가 크롤링할 수 있는 링크를 제한합니다. 필터 제외를 사용하면 감사에서 링크 크롤링 작업을 할 수 없습니다.
seo-description: 필터 포함은 시작 URL에서 감사가 크롤링할 수 있는 링크를 제한합니다. 필터 제외를 사용하면 감사에서 링크 크롤링 작업을 할 수 없습니다.
seo-title: 필터 포함 및 제외
title: 필터 포함 및 제외
uuid: 477fc38c-7351-42dd-8209-2fb7549ee34c
translation-type: tm+mt
source-git-commit: c697f3d759ad1f086f16a39e03062431583ffd7f

---


# 필터 포함 및 제외{#include-and-exclude-filters}

필터 포함은 시작 URL에서 감사가 크롤링할 수 있는 링크를 제한합니다. 필터 제외를 사용하면 감사에서 링크 크롤링 작업을 할 수 없습니다.

<!--
Content from ObservePoint (https://help.observepoint.com/articles/2872121-include-and-exclude-filters) with their permission. Modified slightly for style and Auditor emphasis.
-->

필터 포함 및 제외 필터는 감사에 대한 지침을 제공합니다. 포함 및 제외 필터를 비워 두면 감사가 시작 URL의 링크부터 시작하여 모든 링크를 크롤할 수 있습니다.

![](assets/filter.png)

포함 필터, 제외 필터 또는 두 가지 조합을 적용하여 감사에서 크롤할 수 있는 링크에 대한 지침을 제공할 수 있습니다.

필터 포함 필드의 항목은 해당 항목과 일치하는 페이지만 스캔하여 제한합니다. 필터 제외 필드의 항목은 해당 항목과 일치하는 페이지를 검색하지 못하도록 합니다.

포함 및 제외 필터는 전체 URL, 부분 URL 또는 유효한 페이지와 일치하는 정규 표현식일 수 있습니다.

## 우선 순위 {#section-e9d42419dd3f459bb20e7a33c6104f12}

1. **시작 URL은** 다른 URL보다 우선하며, URL이 제외 필터의 항목과 일치하는 경우에도 감사 중에 항상 방문됩니다. 시작 URL 파섹

   ![](assets/startingpage.png)

   위의 이미지에서 감사는 시작 페이지의 `document.links` 속성에서 링크를 검색합니다. 이러한 링크는 감사에서 스캔할 수 있습니다.

1. **포함 URL은** 시작 페이지에서 연결되어 있어야 합니다. 그렇지 않으면 검색할 수 없고 찾을 수 없습니다.

   ![](assets/includefilter.png)

   위의 이미지에서 포함 필터를 추가하면 해당 URL이 필터와 일치하는 URL로 제한됩니다. 이제 5개의 링크만 감사에서 스캔할 수 있습니다.

1. **URL을** 제외하면 자격 조건으로부터 링크가 제거됩니다.

   ![](assets/excludefilter.png)

   위의 이미지에서 제외 필터를 추가하면 해당 링크에서 URL이 차단됩니다. 이제 세 개의 링크만 감사에서 스캔할 수 있습니다.

## 시작 URL {#section-ccb46abcd96f4a8ab171245015d2b724}

감사자는 시작 URL에 대해 단일 페이지가 필요합니다. 시작 URL 파섹 시작 페이지에서 검색된 모든 링크는 포함 및 제외 필터에 따라 방문할 수 있습니다. Exclude 항목이 시작 URL과 일치하는 경우 무시됩니다.

## 필터 포함 {#section-7626060a56a24b658f8c05f031ac3f5f}

포함 필터는 감사 중에 스캔할 수 있는 링크를 제한합니다. 필터 포함:

* 정규화된 URL
* 부분 URL
* 전체 또는 부분 URL과 일치하는 정규 표현식
* 위의 모든 조합

포함 필터에 URL 또는 정규 표현식을 추가해도 해당 특정 URL이 감사에서 검색되지 않습니다. 감사는 시작 URL의 링크를 검사한 다음 자격 조건을 갖춘 링크를 탐색합니다. 감사는 500개의 스캔한 URL의 제한에 도달하거나 더 이상 자격 조건을 갖춘 링크를 찾을 때까지 검사 및 탐색 프로세스를 계속합니다.

>[!NOTE]
>
>경우에 따라 500페이지 검색을 완료하는 데 최대 48시간이 걸릴 수 있습니다.

기본적으로 감사는 시작 URL의 모든 하위 도메인을 검색합니다. 포함 필터를 제공하여 명시적으로 재정의되지 않는 한 검색에서 다음 regex include 필터를 사용합니다.

`^https?://([^/:\?]*\.)?mysite.com`

이렇게 하면 시작 URL 페이지에 있는 링크가 방문해도 됩니다. 시작 URL 파섹

기본 포함 필터를 사용하면 감사가 크롤링할 수 있는 광범위한 범위가 제공됩니다. 특정 섹션이나 페이지를 보려면 이 상자에 필터를 추가하여 특정 감사 지침을 제공합니다. 이 경우 기본값을 감사 스캔할 디렉토리로 바꿉니다. 또한 필터 포함을 사용하여 도메인 간 감사를 수행하여 한 도메인에서 감사를 시작하고 다른 도메인에서 감사를 끝나야 합니다. 이렇게 하려면 트래버스할 도메인을 입력합니다. 모든 경우에 필터 URL 포함을 찾으려면 감사되는 페이지에서 검색되어야 합니다.

필터 포함에는 정확한 URL, 부분 URL 또는 정규 표현식을 포함할 수 있습니다. 예를 들어 시작 URL이 [!DNL http://mysite.com]있는 경우 기본적으로 다음 페이지를 검색할 수 있습니다(굵은체 문자 참고).

```
http://mysite.com
http
<b>s</b>://mysite.com
http://
<b>www</b>.mysite.com/home
http://
<b>dev</b>.mysite.com/home
http://
<b>my</b>.mysite.com/products/products_and_services.html
```

복잡한 URL 패턴의 경우 ObservePoint [의 정규 표현식 테스터를](http://regex.observepoint.com/)사용합니다.

일반적인 패턴 [일치 사용 사례는 ObservePoint에](https://help.observepoint.com/articles/2872116-common-regular-expressions-for-observepoint) 대한 일반 정규 표현식을 참조하십시오.

## 필터 제외 {#section-00aa5e10c878473b91ba0844bebe7ca9}

제외 필터를 사용하면 URL이 감사되지 않습니다. 정확한 URL, 부분 URL 또는 정규 표현식을 사용할 수 있습니다. 제외 필터의 항목과 일치하는 URL은 방문되지 않습니다. 시작 URL 파섹 시작 URL은 항상 감사에서 스캔합니다.

## 필터 및 URL 테스트 {#section-3cfa125b1756411395a64701e128efa0}

Auditor 내에서 필터 및 URL을 테스트할 수 있습니다.

감사를 만드는 동안 고급 필터 **[!UICONTROL 테스트를 클릭합니다]**. 필터와 URL을 입력한 다음 적용을 **[!UICONTROL 클릭합니다]**.

![](assets/test-advanced-filters.png)

## ObservePoint 설명서 {#section-79cdc8e850d047969b6d2badf6bbd6f9}

이 기사는 ObservePoint와 협력하여 개발되었습니다. 최신 정보는 ObservePoint 설명서를 [참조하십시오](https://help.observepoint.com/articles/2872121-include-and-exclude-filters).
