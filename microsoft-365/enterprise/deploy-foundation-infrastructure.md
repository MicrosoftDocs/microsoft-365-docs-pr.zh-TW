---
title: Microsoft 365 企業版底層基礎結構
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解貴組織中部署 Microsoft 365 企業版底層基礎結構的主要階段。
ms.openlocfilehash: abc38dc0eb3d33f7af9e2c91f020a735cf0c8d96
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866118"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a>Microsoft 365 企業版底層基礎結構

若要完全發揮 Microsoft 365 企業版的優點，您需要從底層基礎結構開始部署。 

## <a name="foundation-infrastructure-for-deploying-microsoft-365-enterprise"></a>部署 Microsoft 365 企業版的底層基礎結構

底層基礎結構是您可以在其上部署生產力工作負載 (如 Office 365 中的 Microsoft Teams 和 Exchange Online) 和案例 (例如移轉至 Microsoft 365 及自動化用戶端更新) 的基礎。它提供智慧安全性與整合，可簡化持續的管理，確保您的用戶端軟體會以最新的生產力與安全性增強功能進行更新。

您將使用下列階段在組織中規劃和部署 Microsoft 365 企業版的底層基礎結構：

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[階段 1：網路](networking-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[階段 2：身分識別](identity-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[階段 3：Windows 10 企業版](windows10-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[階段 4：Office 365 專業增強版](office365proplus-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[階段 5：行動裝置管理](mobility-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[階段 6：資訊保護](infoprotect-infrastructure.md)|


在結束每個階段前，您必須檢查允出準則，其為一組您必須符合的必要條件以及要考慮的選用條件。每個階段的允出準則可確保您的內部部署和雲端基礎結構與產生的端對端設定符合 Microsoft 365 企業版部署需求。

請觀看這段關於基礎結構內容運作方式的短片。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

下圖顯示在整體 Microsoft 365 企業版部署內容中的底層基礎結構及您的部署路徑。

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="fasttrack"></a>FastTrack

FastTrack 是由 Microsoft 工程師提供的持續且可重複的好處，作為訂閱的一部分供您使用，可協助您以自己的步調移轉到雲端。FastTrack 也可在您有需要時，讓您存取合格合作夥伴的其他服務。至今隨著超過 40000 位啟用此服務的客戶，FastTrack 可協助最大化 ROI、加速部署，以及提高整個組織中的採用率。請參閱[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)。 

如果您想要利用 FastTrack 來部署 Microsoft 365 企業版，您可以使用 FastTrack [Microsoft 365 部署建議程式](https://aka.ms/microsoft365setupguide)，以了解有關部署及設定基礎結構的指導方針。您必須以全域管理員身分登入 Office 365 或 Microsoft 365 租用戶，以便存取此頁面。

## <a name="next-step"></a>下一步

如果您有 Office 365、Enterprise Mobility + Security 或 Windows 10 企業版現有的基礎結構，請參閱[使用現有基礎結構部署 Microsoft 365 企業版](deploy-with-existing-infrastructure.md)。此文章會逐步引導您了解每個階段的允出準則。使用此資訊，您可以更快判斷要讓 IT 基礎結構與 Microsoft 365 企業版相容所需的變更。

如果沒有，則可以使用[階段 1：網路](networking-infrastructure.md)開始您的 Microsoft 365 企業版端對端部署。