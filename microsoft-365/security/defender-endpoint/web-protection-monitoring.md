---
title: 監視 Microsoft Defender ATP 中的 web 流覽安全性
description: 在 Microsoft Defender ATP 中使用 web 保護以監視網頁流覽安全性
keywords: web 保護，網頁威脅防護，網頁流覽，監控，報表，卡片，網域清單，安全性，網路釣魚，惡意程式碼，exploit，網站，網路保護，Edge，Internet Explorer，Chrome，Firefox，網頁瀏覽器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 629e18c7387f6063254f3482f93a5e17023c7316
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499951"
---
# <a name="monitor-web-browsing-security"></a>監視網頁流覽安全性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web 保護可讓您透過 Microsoft Defender Security Center 中 **報告 > web 保護** ，來監控組織的 web 流覽安全性。 報告包含的卡片可提供 web 威脅偵測統計資料。

- **隨時間變化的 web 威脅防護** 偵測-此趨勢卡會在過去30天、過去3個月、過去6個月的 (，顯示在選取的時段內，由類型偵測到的 web 威脅數目) 
 
    ![顯示網路威脅防護偵測一段時間的卡片影像](images/wtp-blocks-over-time.png)

- **Web 威脅防護摘要** -此卡片會顯示過去30天內的 web 威脅偵測總數，顯示不同網路威脅類型的散佈。 選取切片時，會開啟包含惡意網站或有害網站的網域清單。

    ![顯示網路威脅保護摘要的卡片影像](images/wtp-summary.png)

>[!Note]
>在 [卡片] 或 [網域] 清單中的區塊反映之前，可能需要長達12小時。

## <a name="types-of-web-threats"></a>Web 威脅類型

Web 保護會將惡意及有害的網站分類，如下所示：

- **網路釣魚** -包含冒牌網頁表單和其他網路釣魚詐騙機制的網站，其設計目的是欺騙使用者 divulging 認證及其他敏感資訊。
- **惡意** 網站，主控惡意程式碼和利用程式碼
- **自訂指示器** -已新增至您 [自訂指示器清單](manage-indicators.md) 進行封鎖的 URLs 或網域的網站

## <a name="view-the-domain-list"></a>查看網域清單

在 [ **網頁威脅防護] 摘要** 卡中，選取特定的 web 威脅類別，以開啟 [ **網域** ] 頁面。 此頁面會顯示 [威脅] 類別底下的網域清單。 此頁面提供每個網域的下列資訊：

- **存取計數** -網域中 URLs 的要求數目
- **區塊** -封鎖要求的次數
- **存取趨勢** -在存取嘗試數目上的變更
- **威脅類別** -web 威脅類型
- **裝置** -具有存取嘗試的裝置數目

選取一個網域，以查看已嘗試存取該網域中 URLs 的裝置清單及 URLs 清單。

## <a name="related-topics"></a>相關主題

- [Web 保護概觀](web-protection-overview.md)
- [Web 內容篩選](web-content-filtering.md)
- [網頁威脅防護](web-threat-protection.md)
- [回應 Web 威脅](web-protection-response.md)
