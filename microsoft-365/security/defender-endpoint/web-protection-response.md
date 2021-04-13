---
title: 在 Microsoft Defender for Endpoint 中回應 web 威脅
description: 回應與惡意網站和有害網站相關的提醒。 瞭解網頁威脅防護如何透過網頁瀏覽器和 Windows 通知通知使用者
keywords: web 保護，網頁威脅防護，網頁流覽，警示，回應，安全性，網路釣魚，惡意程式碼，exploit，網站，網路保護，Edge，Internet Explorer，Chrome，Firefox，網頁瀏覽器，通知，使用者，Windows 通知，封鎖頁面
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
ms.openlocfilehash: 110b379863b4c6e23c947c56faf831e136231237
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688474"
---
# <a name="respond-to-web-threats"></a>回應 Web 威脅

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Microsoft Defender for Endpoint 中的 Web 保護功能可讓您有效地調查與您自訂指示器清單中的惡意網站和網站相關的提醒。

## <a name="view-web-threat-alerts"></a>查看網頁威脅警示
Microsoft Defender for Endpoint 會針對惡意或可疑的 web 活動產生下列 [警示](manage-alerts.md) ：
- **網路保護封鎖的可疑** 連線-當使用者嘗試存取您自訂指示器清單中的惡意網站或網站 *時，會* 產生此警示，以 *封鎖* 模式中的網路保護
- **網路保護偵測到可疑** 的連線-當以「 *僅供審核* 」模式中的網路保護方式偵測到自訂指示器清單中的訪問惡意網站或網站時，就會產生此警示。

每個警示都提供下列資訊： 
- 嘗試存取封鎖的網站的裝置
- 用來傳送 web 要求的應用程式或程式
- 自訂指示器清單中的惡意 URL 或 URL
- 回應回應程式的建議動作

![與 web 威脅防護相關的提醒影像](images/wtp-alert.png)

>[!Note]
>為了降低警示數量，Microsoft Defender for Endpoint 會將相同裝置上相同網域的 web 威脅偵測，合併到單一警示。 只產生一個提醒並計算在 [web 保護報告](web-protection-monitoring.md)中。

## <a name="inspect-website-details"></a>檢查網站詳細資料
您可以在警示中，選取網站的 URL 或網域，以深入瞭解。 這會開啟有關該特定 URL 或網域的頁面，其中包含各種資訊，包括：
- 嘗試存取網站的裝置
- 與網站相關的事件及警示
- 在組織中的事件看到網站的頻率

    ![[網域] 或 [URL 實體詳細資料] 頁面的圖像](images/wtp-website-details.png)

[深入瞭解 URL 或網域實體頁面](investigate-domain.md)

## <a name="inspect-the-device"></a>檢查裝置
您也可以檢查嘗試存取封鎖 URL 的裝置。 在 [警示] 頁面上選取裝置的名稱，會開啟一個頁面，其中包含裝置的完整資訊。

[深入瞭解裝置實體頁面](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>使用者的網頁瀏覽器和 Windows 通知

使用 Microsoft Defender for Endpoint 中的 web 保護，您的使用者將無法使用 Microsoft Edge 或其他瀏覽器來訪問惡意或有害的網站。 因為封鎖是透過 [網路保護](network-protection.md)來執行，所以他們會看到來自網頁瀏覽器的一般錯誤。 他們也會看到來自 Windows 的通知。

![Microsoft Edge 的影像，顯示403錯誤和 ](images/wtp-browser-blocking-page.png)
 *microsoft edge 封鎖* 的 Windows 通知網頁威脅

![Chrome 網頁瀏覽器的影像，顯示安全連線警告，以及 ](images/wtp-chrome-browser-blocking-page.png)
 *在 Chrome 上封鎖* 的 Windows 通知網頁威脅

## <a name="related-topics"></a>相關主題
- [Web 保護概觀](web-protection-overview.md)
- [Web 內容篩選](web-content-filtering.md)
- [網頁威脅防護](web-threat-protection.md)
- [監視 Web 安全性](web-protection-monitoring.md)
