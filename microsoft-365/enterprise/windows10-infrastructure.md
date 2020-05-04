---
title: Microsoft 365 企業版的 Windows 10 企業版基礎結構
description: 提供在 Microsoft 365 Enterprise 的一部分上部署 Windows 10 企業版時所需步驟的高階指導方針。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 檔，Windows 10 企業版，部署
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: d1019547fb16fd4fd5669ebd5286e8c9e32668fe
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011920"
---
# <a name="phase-3-windows-10-enterprise"></a>階段 3：Windows 10 企業版

![階段 3：Windows 10 企業版](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise 包含 Windows 10 企業版，可讓您執行更多和保持安全的工具。 Windows 10 企業版：

- **已整合，以簡化**雲端的功能，協助降低管理當今現代 IT 裝置環境的複雜性，不論大小為何。
- **具有智慧安全性**-它是最安全的 Windows 版本，其設計目的在於搭配搭配使用的智慧安全性功能，以更好地保護您的組織。
- **可讓創造性和團隊合作**-解除其創造力和團隊合作，以提供使用者最喜歡的工作效率。

您必須瞭解部署 Windows 10 作業系統的不同方式，並為您的組織選擇適當的方式。 視您的 Microsoft 365 Enterprise 訂閱而定，您需要設定 Windows 10 服務和安全性功能，以充分利用 Windows 10。

>[!Note]
>若要同時部署 Windows 10 企業版和 Microsoft 365 應用程式，並移至[新式桌面](https://www.microsoft.com/microsoft-365/modern-desktop)，請參閱[新式桌面部署中心](https://aka.ms/howtoshift)。
>

## <a name="windows-10-deployment"></a>Windows 10 部署

您可以利用多種方式，為組織部署 Windows 10 企業版。 在這裡，我們將重點講述如何透過這些新式部署案例來設定及部署 Windows 10 企業版映射。

| 部署案例 | 何時使用 |
|:--- |:--- |
| [使用 Microsoft 端點 Configuration Manager 做為就地升級](windows10-deploy-inplaceupgrade.md) | 如果您需要將 Windows 7 或 Windows 8.1 電腦升級至目前的 Windows 10 企業<a href="https://aka.ms/windows-10-release-information" target="_blank">版</a>，且您的電腦目前是以<a href="https://docs.microsoft.com/mem/configmgr/core/understand/introduction" target="_blank">Configuration Manager （目前的分支）</a>進行管理，請選取此選項。 |
| [使用 Windows Autopilot](windows10-deploy-autopilot.md) | 如果您要設定的新 Windows 電腦具有 Windows 10 企業版、版本1703或更新版本，請選取此選項。 使用者可輸入其工作或學校帳戶的認證，以使用您所需的設定來啟動設定。 |

如果這些部署案例不符合您組織的需求，則可以深入瞭解其他案例，並瞭解每個[Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)中的功能和限制。 您也可以自行<a href="https://aka.ms/planforwin10deployment" target="_blank">規劃 Windows 10 部署</a>。

您可以使用下列文章深入瞭解 Windows 10：

- [Microsoft 365 Enterprise 產品頁面](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [部署及更新 Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>其他服務和功能
在 Windows 10 企業版部署的一部分中，您可以新增這些額外的服務和功能。

### <a name="windows-analytics"></a>Windows Analytics

Windows 會使用診斷資料，提供豐富的可運作資訊，協助您深入瞭解作業效率，以及環境中 Windows 10 裝置的健康情況。

* 升級準備情況-升級準備可協助您移至 Windows 10，並以新的 Windows 10 功能更新保持最新狀態。 
* 更新規範-更新規範是針對想要深入瞭解所有 Windows 10 裝置的 IT 系統管理員，不需要任何其他基礎結構需求。
* 裝置健康情況-您可以使用裝置健康情況，主動偵測和修正使用者影響的問題。

如需詳細資訊，請參閱[Windows Analytics 一覽](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)。

### <a name="windows-security"></a>Windows 安全性

Windows 10 提供的功能可協助防範威脅、協助您保護裝置，以及協助您進行存取控制。 使用 Windows 10 時，您會獲得重要的安全性功能，可在啟動時立即保護您的裝置。 Microsoft 365 E3 新增諸如 Windows Hello 企業版、Windows Defender 應用程式控制和 Windows 資訊保護等安全性功能。 使用 Microsoft 365 E5，您可以從 Microsoft 365 E3 安全性加上雲端式安全性功能和 Microsoft Defender 高級威脅防護，獲得所有保護。 

若要深入瞭解使用 Windows 10 Enterprise 所獲得的安全性功能，並取得如何部署、管理、設定及疑難排解三項重要安全性功能的指導，請參閱「[步驟5：部署 Windows 10 企業版安全性功能](windows10-enable-security-features.md)」。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

在 Microsoft 內部進行查看，並瞭解公司如何[部署 Windows 10 企業版，以及如何使用強大的驗證、Intune 和 Microsoft DEFENDER ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何執行 Microsoft 365 企業版

請參閱 Contoso Corporation （虛構但有代表性的跨國企業）如何[部署 Windows 10 企業版](contoso-win10.md)。

![Contoso 公司](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![步驟 1](../media/stepnumbers/Step1.png)| [為 Windows 10 企業版準備您的組織](windows10-prepare-your-org.md) |
