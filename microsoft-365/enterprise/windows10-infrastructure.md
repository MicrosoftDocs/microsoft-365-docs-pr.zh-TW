---
title: Microsoft 365 企業版的 Windows 10 企業版基礎結構
description: 針對 Microsoft 365 企業版的一部分部署在電腦上的 Windows 10 企業版所需的步驟提供高階指導。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 文件、 Windows 10 企業版部署
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 88517c6b8de95c54ee9a2e47d4545266eb198249
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289431"
---
# <a name="phase-3-windows-10-enterprise"></a>階段 3：Windows 10 企業版

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 企業版包含 Windows 10 企業版，可讓您進行更多作業及保持安全的工具。 Windows 10 企業版：

- **為了簡單起見整合**-控管的 cloud 電源，若要協助減少管理今天的複雜性的現代 IT 裝置環境中的，不論大小。
- **提供智慧安全性**-曾經是最安全的 Windows 版本，請使用智慧安全性功能專為合作更妥善地保護您的組織。
- **可讓發揮創意並實現團隊合作**-解除鎖定發揮創意並實現團隊合作來傳遞最生產力體驗的使用者和 IT 會告訴。

您需要了解您可以部署 Windows 10 的作業系統，並選擇適合貴組織的不同方式。 根據您的 Microsoft 365 企業版訂閱，也有 Windows 10 服務與安全性功能，您必須設定成充分 Windows 10。

Windows 10 達成了 Microsoft 365 企業版的這些策略商務案例：

- 運用集體知識和專業技能，讓組織中的使用者可探索、共用及改善檔案、資訊和想法
- 隨時隨地在裝置上安全地工作，以達成更多目標，同時維持彈性的工作方式
- 通過產業驗證符合合規性的全球標準，提供控制和可見度讓您安心
- 保護您的資訊，並降低資料遺失風險
- 偵測和防範外部威脅-監控、 報告及分析活動，以回應迅速提供組織的安全性
- 保護您的使用者和自己的帳戶
- 使用增強的隱私權和法規遵循來支援貴組織，以符合一般資料保護規定 (GDPR)
- 為桌面軟體與裝置取得並保持在目前最新狀態，同時降低安全性風險並將 IT 部門的效率最大化

如需詳細資訊，請參閱[使用 Microsoft 365 進行數位轉換](http://transform.microsoft.com) (英文)。 

>[!Note]
>若要同時部署 Windows 10 企業版和 Office 365 專業增強版，並且改為使用[現代化電腦](https://www.microsoft.com/microsoft-365/modern-desktop)，請參閱[現代化電腦的部署中心](http://aka.ms/howtoshift)。
>

## <a name="windows-10-deployment"></a>Windows 10 部署

有多種方法可以為貴組織中部署 Windows 10 企業版。 在這裡，我們將著重於如何設定及部署 Windows 10 企業版映像，透過這些現代化的部署案例。

| 部署案例 | 使用時機 |
|:--- |:--- |
| [使用 System Center Configuration Manager 以進行就地升級](windows10-deploy-inplaceupgrade.md) | 如果您要升級 Windows 7 或<a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager （最新分支）</a>目前管理 Windows 10 企業版的<a href="https://aka.ms/windows-10-release-information" target="_blank">目前版本</a>的 Windows 8.1 電腦與您的電腦，請選取這個選項。 |
| [使用 Windows Autopilot](windows10-deploy-autopilot.md) | 如果您正在設定新有 Windows 10 企業版，版本 1703年或更新版本預先安裝的 Windows 電腦，請選取這個選項。 使用者將會啟動安裝程式使用您所需的設定，藉由輸入他們的公司或學校帳戶認證。 |

如果這些部署案例不符合您組織的需求，您可以了解其他案例，並了解的功能和每個在[Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)中的限制。 您也可以靠您自己的<a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 部署計劃</a>。

您可以深入了解 Windows 10 使用以下文章：

- [Microsoft 365 Enterprise 產品頁面](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [部署並更新 Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>其他服務與功能
Windows 10 企業版部署的一部分，您可以新增這些額外的服務和功能。

### <a name="windows-analytics"></a>Windows Analytics

Windows 用來提供豐富、 可採取動作的資訊可協助您深入了解深層作業效率和您環境中的 Windows 10 裝置的健康狀況情形診斷資料。

* 升級整備-升級整備可協助您移動到 Windows 10，並保持最新的 Windows 10 功能更新。 
* 升級相容性-升級相容性為目標的 IT 系統管理員想要取得所有 Windows 10 裝置，沒有任何其他基礎結構需求的全方位檢視。
* 裝置健全狀況-您可以使用裝置健全狀況主動偵測及修復使用者影響問題。

如需詳細資訊，請參閱[Windows Analytics 概觀](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)。

### <a name="windows-security"></a>Windows 安全性

Windows 10 提供功能，協助防範威脅，協助保護您的裝置，並協助使用存取控制。 與 Windows 10 中，您可以取得重要的安全性功能，以保護您的裝置權限從開始。 Microsoft 365 E3，新增安全性功能，例如 Windows Hello 企業、 Windows Defender 應用程式控制和 Windows 資訊保護。 使用 Microsoft 365 E5，您可以取得所有保護從 Microsoft 365 E3 安全性加上雲端為基礎的安全性功能和 Windows Defender 進階威脅防護。 

若要深入了解您取得 Windows 10 企業版和取得指導方針如何部署、 管理、 設定及疑難排解三個主要的安全性功能的安全性功能，請參閱[步驟 5： 部署 Windows 10 企業版安全性功能](windows10-enable-security-features.md)。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

一窺 Microsoft 並了解公司如何規劃、 部署，及管理更新適用於 Windows 10，請參閱：

- [準備您的組織以便進行完美的 Windows 10 部署](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [採用 Microsoft 的 Windows 即服務](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [在 Microsoft 以就地升級方式部署 Windows 10](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [使用 Windows Hello 企業版實作強大的使用者驗證](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- [Windows 10 部署：Microsoft IT 的秘訣與技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (影片)
- [Windows Defender ATP 可協助偵測複雜的威脅](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- [使用 Windows Defender 和 Windows Defender ATP 保護現代的企業](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (影片)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何執行 Microsoft 365 企業版

請參閱如何 Contoso Corporation、 虛構但有代表性的跨國企業、[部署 Windows 10 企業版](contoso-win10.md)。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [準備您的組織，Windows 10 企業版](windows10-prepare-your-org.md) |
