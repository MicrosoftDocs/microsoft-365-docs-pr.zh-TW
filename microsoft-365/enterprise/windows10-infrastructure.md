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
ms.date: 08/28/2019
ms.author: greglin
ms.openlocfilehash: 92a786f40c10170cf0eb5f91f765bad4dc044c97
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112667"
---
# <a name="phase-3-windows-10-enterprise"></a>階段 3：Windows 10 企業版

![階段 3：Windows 10 企業版](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 企業版包含 Windows 10 企業版，可讓您進行更多作業及保持安全的工具。 Windows 10 企業版：

- **為了簡單起見整合**-控管的 cloud 電源，若要協助減少管理今天的複雜性的現代 IT 裝置環境中的，不論大小。
- **提供智慧安全性**-曾經是最安全的 Windows 版本，請使用智慧安全性功能專為合作更妥善地保護您的組織。
- **可讓發揮創意並實現團隊合作**-解除鎖定發揮創意並實現團隊合作來傳遞最生產力體驗的使用者和 IT 會告訴。

您需要了解您可以部署 Windows 10 的作業系統，並選擇適合貴組織的不同方式。 根據您的 Microsoft 365 企業版訂閱，也有 Windows 10 服務與安全性功能，您必須設定成充分 Windows 10。

>[!Note]
>若要同時部署 Windows 10 企業版和 Office 365 專業增強版，並且改為使用[現代化電腦](https://www.microsoft.com/microsoft-365/modern-desktop)，請參閱[現代化電腦的部署中心](https://aka.ms/howtoshift)。
>

## <a name="windows-10-deployment"></a>Windows 10 部署

有多種方法可以為貴組織中部署 Windows 10 企業版。 在這裡，我們將著重於如何設定及部署 Windows 10 企業版映像，透過這些現代化的部署案例。

| 部署案例 | 使用時機 |
|:--- |:--- |
| [使用 Microsoft 端點 Configuration Manager 以進行就地升級](windows10-deploy-inplaceupgrade.md) | 如果您要升級 Windows 7 或<a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Configuration Manager （最新分支）</a>目前管理 Windows 10 企業版的<a href="https://aka.ms/windows-10-release-information" target="_blank">目前版本</a>的 Windows 8.1 電腦與您的電腦，請選取這個選項。 |
| [使用 Windows Autopilot](windows10-deploy-autopilot.md) | 如果您正在設定新有 Windows 10 企業版，版本 1703年或更新版本預先安裝的 Windows 電腦，請選取這個選項。 使用者將會啟動安裝程式使用您所需的設定，藉由輸入他們的公司或學校帳戶認證。 |

如果這些部署案例不符合您組織的需求，您可以了解其他案例，並了解的功能和每個在[Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)中的限制。 您也可以自行<a href="https://aka.ms/planforwin10deployment" target="_blank">規劃 Windows 10 部署</a>。

您可以深入了解 Windows 10 使用以下文章：

- [Microsoft 365 Enterprise 產品頁面](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [部署及更新 Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>其他服務與功能
Windows 10 企業版部署的一部分，您可以新增這些額外的服務和功能。

### <a name="windows-analytics"></a>Windows Analytics

Windows 用來提供豐富、 可採取動作的資訊可協助您深入了解深層作業效率和您環境中的 Windows 10 裝置的健康狀況情形診斷資料。

* 升級整備-升級整備可協助您移動到 Windows 10，並保持最新的 Windows 10 功能更新。 
* 升級相容性-升級相容性為目標的 IT 系統管理員想要取得所有 Windows 10 裝置，沒有任何其他基礎結構需求的全方位檢視。
* 裝置健全狀況-您可以使用裝置健全狀況主動偵測及修復使用者影響問題。

如需詳細資訊，請參閱[Windows Analytics 概觀](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)。

### <a name="windows-security"></a>Windows 安全性

Windows 10 提供功能，協助防範威脅，協助保護您的裝置，並協助使用存取控制。 與 Windows 10 中，您可以取得重要的安全性功能，以保護您的裝置權限從開始。 Microsoft 365 E3，新增安全性功能，例如 Windows Hello 企業、 Windows Defender 應用程式控制和 Windows 資訊保護。 使用 Microsoft 365 E5，您要從 Microsoft 365 E3 安全性加上雲端為基礎的安全性功能和 Microsoft Defender 進階威脅防護取得所有的保護。 

若要深入了解您取得 Windows 10 企業版和取得指導方針如何部署、 管理、 設定及疑難排解三個主要的安全性功能的安全性功能，請參閱[步驟 5： 部署 Windows 10 企業版安全性功能](windows10-enable-security-features.md)。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

一窺 Microsoft 並了解如何公司[部署 Windows 10 企業版，且正在使用 Intune，且 Microsoft Defender ATP 的強式驗證](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何執行 Microsoft 365 企業版

請參閱如何 Contoso Corporation、 虛構但有代表性的跨國企業、[部署 Windows 10 企業版](contoso-win10.md)。

![Contoso 公司](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![步驟 1](./media/stepnumbers/Step1.png)| [準備您的組織，Windows 10 企業版](windows10-prepare-your-org.md) |
