---
title: 威脅與弱點管理
description: 這項新功能使用以遊戲為基礎的風險方式，來探索、優先順序和修正端點漏洞與錯誤配置。
keywords: 威脅 & 弱點管理，威脅與弱點管理，microsoft defender for endpoint TVM，microsoft defender for endpoint TVM，弱點管理，漏洞評估，威脅和弱點掃描，安全的設定評估，Microsoft Defender for endpoint，端點漏洞，下一代
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
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: 474b8f032d32668eaea3a477da013c2b8e74019b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934162"
---
# <a name="threat-and-vulnerability-management"></a>威脅與弱點管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

有效地識別、評估和修正端點弱點，是在執行健康的安全性計畫及降低組織風險方面 pivotal。 威脅和弱點管理是一種能降低組織暴露程度、強化端點表面區域，並提高組織彈性的基礎結構。

以感應器即時探索弱點與錯誤配置，而不需要代理程式或定期掃描。 它會根據威脅情況、組織中的偵測、有缺陷裝置的敏感資訊和商務內容來劃分安全性漏洞。

觀賞這段影片，快速流覽威脅與弱點管理。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a>橋接工作流程缺口

威脅和弱點管理已內建、即時和雲端已通電。 它會與 microsoft 端點安全性堆疊、microsoft 智慧型 security Graph 及 application analytics 知識庫完全整合。  

「弱點管理」是業界中的第一個解決方案，可在修正過程中，彌合安全性管理與 IT 系統管理之間的缺口。 透過與 Microsoft Intune 和 Microsoft Endpoint Configuration Manager 整合，建立安全性工作或票證。

### <a name="real-time-discovery"></a>即時探索

為了探索端點漏洞及錯誤配置，威脅與弱點管理會使用相同的無代理程式內建 Defender，以減少繁瑣的網路掃描和 IT 負荷。

它還提供：

- **即時設備清查** -架 to Defender for Endpoint 的裝置會自動向儀表板報告及推入弱點及安全性設定資料。
- 深入瞭解 **軟體和弱點**-光學架構中的軟體和弱點，以及軟體變更（如安裝、卸載及修補程式）。 針對第一個和協力廠商應用程式，會以行動的緩解建議來報告新發現的漏洞。
- **應用程式執行時間內容** -應用程式使用模式的可見度，以改善優先順序和決策的制定。
- 設定 **狀況**-查看組織的安全性設定或錯誤配置。 會在儀表板中報告問題，並提供切實可行的安全性建議。

### <a name="intelligence-driven-prioritization"></a>智慧導向的優先順序

威脅與弱點管理可協助客戶設定優先順序，並將重點放在組織最緊迫和最高風險的弱點上。 它會 fuses 具有動態威脅及商業內容的安全性建議：

- **以動態方式公開新興的攻擊，以** 與安全性建議的優先順序對齊。 威脅和弱點管理著重于目前正被利用的漏洞，以及帶來最高風險的新興威脅。
- 查明作用中的 **違規行為**-關聯威脅與弱點管理和 EDR 真知灼見，以優先順序組織內的作用中破壞使用的漏洞。
- **保護高價值資產** -利用業務關鍵型應用程式、機密資料或高價值的使用者來識別公開的裝置。

### <a name="seamless-remediation"></a>無縫修復

威脅與弱點管理可讓安全性管理員和 IT 系統管理員無縫地共同作業，以修正問題。

- **已傳送的修復要求**-從特定安全性建議的 Microsoft Intune 中建立修復工作。 我們打算將此功能擴充為其他 IT 安全性管理平臺。
- **替代的緩解** -深入瞭解其他緩解措施，例如可降低軟體弱點相關風險的設定變更。
- **即時修復狀態** -即時監控整個組織中的修復活動狀態和進度。

## <a name="threat-and-vulnerability-management-walk-through"></a>威脅及弱點管理逐步進行

請觀看這段影片，以取得威脅與弱點管理的全面逐步說明。

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a>功能窗格 

區域 | 描述
:---|:---
**儀表板**   | 取得組織公開分數、Microsoft 安全分數、裝置洩密發佈、主要安全性建議、熱門的軟體、熱門的修復活動，以及主要公開裝置資料的高層次的視圖。
[**安全性建議**](tvm-security-recommendation.md) | 請參閱安全性建議和相關威脅資訊的清單。 當您從清單中選取專案時，會開啟彈出面板，其中包含弱點詳細資料、開啟軟體頁面的連結，以及修正和例外狀況選項。 您也可以在 Intune 中開啟票證（如果您已透過 Azure Active Directory 加入您的裝置，且已在 Defender for Endpoint 中啟用了 intune 連線）。
[**修復**](tvm-remediation.md) | 請參閱您已建立的修復活動和建議的例外狀況。
[**軟體庫存**](tvm-software-inventory.md) | 查看您組織中有缺陷的軟體清單，以及弱點和威脅資訊。
[**弱點**](tvm-weaknesses.md) | 請參閱您組織中 (Cve) 的常見漏洞與洩密清單。
[**活動時間表**](threat-and-vuln-mgt-event-timeline.md) | 查看可能影響組織風險的事件。

## <a name="apis"></a>API

執行威脅與弱點管理相關 API 通話，以自動化弱點管理工作流程。 若要深入瞭解，請參閱[Microsoft Tech Community 博客文章](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)。

相關 APIs 請參閱下列文章：

- [受支援的適用於端點的 Microsoft Defender API](exposed-apis-list.md)
- [電腦 APIs](machine.md)
- [建議 APIs](vulnerability.md)
- [分數 APIs](score.md)
- [軟體 APIs](software.md)
- [弱點 APIs](vulnerability.md)
- [列出電腦和軟體的弱點](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a>另請參閱

- [支援的作業系統和平台](tvm-supported-os.md)
- [威脅與弱點管理儀表板](tvm-dashboard-insights.md)
- [博客： Microsoft 的威脅 & 弱點管理現在可協助成千上萬的客戶即時探索、優先考慮和修復弱點。](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)
