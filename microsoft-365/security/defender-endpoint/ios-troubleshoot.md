---
title: 針對 iOS 上與 Microsoft Defender for Endpoint 相關的 FAQs 進行問題及尋找答案
description: 疑難排解與常見問題-Microsoft Defender for Endpoint on iOS
keywords: microsoft，defender，Microsoft Defender for Endpoint，ios，疑難排解，常見問題，如何
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b82b6993ce9ed5a3f0f3e6e13e8a260a185c9730
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194970"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a>在 iOS 上的 Microsoft Defender for Endpoint 上進行問題的疑難排解及尋找答案 FAQs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

本主題提供疑難排解資訊，可協助您處理當您在 iOS 上使用 Microsoft Defender for Endpoint 時可能發生的問題。



> [!NOTE]
> IOS 上的 Defender for Endpoint 會使用 VPN，以便提供 Web 保護功能。 這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>開啟 VPN 時，應用程式無法運作
偵測到主動 VPN 時，有些應用程式停止運作。 您可以在使用這類應用程式時停用 VPN。 

根據預設，iOS 上的 Defender for Endpoint 會包含並啟用 web 保護功能。 [Web 保護](web-protection-overview.md) 可協助保護裝置免受網頁威脅，並保護使用者免受網路釣魚攻擊。 IOS 上的 Defender for Endpoint 會使用 VPN，以提供此保護。 請注意，這是本機 VPN，與傳統 VPN 不同，網路流量不會傳送到裝置外。

預設為啟用時，可能需要停用 VPN。 例如，當設定 VPN 時，您想要執行一些無法運作的應用程式。 在這種情況下，您可以依照下列步驟，從裝置上的應用程式中選擇停用 VPN：

1. 在您的 iOS 裝置上，開啟 **設定** 應用程式，按一下或點擊 **[一般**]，然後再按一下 [ **VPN**]。
1. 按一下或點擊 Microsoft Defender for Endpoint 的「i」按鈕。
1. 關閉連線停用 VPN 的 **要求**。

    > [!div class="mx-imgBorder"]
    > ![需要時 VPN 設定連接](images/ios-vpn-config.png)

> [!NOTE]
> 停用 VPN 時，將無法使用 Web 保護。 若要重新啟用 Web 保護，請開啟裝置上的 Microsoft Defender for Endpoint app，然後按一下或點擊 [ **啟動 VPN**]。

## <a name="co-existence-with-multiple-vpn-profiles"></a>與多個 VPN 設定檔共存

Apple iOS 不支援多個 **全裝置的** vpn 同時作用中。 雖然裝置上可以有多個 VPN 設定檔，但一次只能有一個 VPN 可用。

Microsoft Defender for Endpoint VPN 可以與其他設定為個別 *應用程式* 或 *"個人"* 的 vpn 共同存在。

## <a name="battery-consumption"></a>電池消耗

在設定應用程式中，iOS 只會顯示使用者在特定期間內可看到之應用程式的電池使用方式。 螢幕上顯示之應用程式的電池使用量只是針對該時段，而且會根據許多因素（包括 CPU 和網路使用量）進行 iOS 計算。 Microsoft Defender for Endpoint 會在背景中使用本機/環路傳回 VPN，檢查任何惡意網站或連線的網頁流量。 任何應用程式的網路封包都會進行此項檢查，從而導致無法準確計算 Microsoft Defender for Endpoint 的電池使用量。 Microsoft Defender for Endpoint 的實際電池消耗遠遠小於裝置上的 [電池設定] 頁面上顯示的數目。

在後臺執行的 Microsoft Defender for Endpoint 的每日平均電池使用量 **大約是該天使用的整體電池占 8.81%**。 根據使用者裝置上的 Microsoft Defender for Endpoint 的實際使用量，此度量值是透過 Apple 報告，而由於上述原因，也可能會考慮到具有網路活動的其他應用程式。

此外，使用的 VPN 也是本機 VPN，與傳統的 VPN 不同的是，網路流量不會傳送到裝置外。

## <a name="data-usage"></a>資料使用量

Microsoft Defender for Endpoint 會使用本機/回送 VPN，檢查任何惡意網站或連線的網頁流量。 由於這個原因，可不准確為端點資料使用量進行 Microsoft Defender 資料使用量的考慮。 我們也會發現，如果裝置只在行動裝置網路上，服務提供者所報告的資料使用狀況非常接近實際消耗，而在設定應用程式中，Apple 會顯示大約 1.5 x 到2的實際消耗的資料。

我們也對其他 VPN 服務有類似的觀察，而且已將此報告為 Apple。

此外，若要提供更好的保護，Microsoft Defender 的端點也是最新的。 不過，我們正在努力優化 Microsoft Defender for Endpoint 的資料使用量。

## <a name="report-unsafe-site"></a>報告不安全的網站

網路釣魚網站會為了取得您的個人或財務資訊，模仿可信的網站。 就診「 [提供網路保護的意見](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 反應」頁面，以報告可能是仿冒網站的網站。

## <a name="malicious-site-detected"></a>偵測到惡意網站

Microsoft Defender for Endpoint 會保護您免受網路釣魚或其他網路型攻擊。 如果偵測到惡意的網站，將會封鎖連線，並會將警示傳送至組織的安全性中心入口網站。 警示包括 connection 的功能變數名稱、遠端 IP 位址和裝置詳細資料。

此外，在 iOS 裝置上會顯示通知。 在通知上敲擊會開啟下列畫面，讓使用者複查詳細資料。

> [!div class="mx-imgBorder"]
> ![報告為不安全通知的網站影像](images/ios-phish-alert.png)

## <a name="data-and-privacy"></a>資料和隱私權

如需收集資料與隱私權的詳細資訊，請參閱 [隱私權資訊-Microsoft Defender For Endpoint on iOS](ios-privacy.md)。

