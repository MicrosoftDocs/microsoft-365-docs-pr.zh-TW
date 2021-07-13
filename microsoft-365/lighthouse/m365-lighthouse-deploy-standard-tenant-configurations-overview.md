---
title: 使用基線部署標準租使用者設定的概覽
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 針對受管理的服務提供者 (MSPs) 使用 Microsoft 365 Lighthouse，瞭解如何使用比較基準部署標準租使用者設定。
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409174"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>使用基線部署標準租使用者設定的概覽 

> [!NOTE]
> 本文所述的功能都是在預覽中進行變更，而且只有符合 [需求](m365-lighthouse-requirements.md)的合作夥伴才能使用。 如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。

Microsoft 365 Lighthouse 基線為您提供可重複且可伸縮的方式，可讓您評估和管理跨多個承租人的 Microsoft 365 安全性設定。 基準也會協助監控核心安全性原則和租使用者規範標準，以及保護使用者、裝置及資料的設定。

其設計目的是協助合作夥伴以其自己的節奏來啟用安全性採用，Microsoft 365 Lighthouse 為 Microsoft 365 服務提供一組標準的基準參數和預先定義的設定。 這些安全性設定有助於衡量承租人的 Microsoft 365 安全性和合規性進度。

您可以從 Microsoft 365 Lighthouse 中查看預設的基準及其部署步驟。 若要將基準套用至租使用者，請在左功能窗格中選取 [ **承租人** ]，然後選取租使用者。 接下來，移至 [ **部署計畫** ] 索引標籤，並執行所需的基準。

## <a name="standard-baseline-security-templates"></a>標準基準安全性範本

Microsoft 365 Lighthouse 安全性工作負載的標準基準設定，是為了協助所有受管理的承租人達到安全性範圍和合規性的可接受狀態。

下表中的基準設定標配 Microsoft 365 Lighthouse 預設的基準。<br><br>

| 基準設定 | 描述 |
|--|--|
| 需要對系統管理員進行 MFA | 僅限報告的條件式存取原則，需要系統管理員的多重驗證。 所有的雲端應用程式都需要這種方式。 |
| 需要對使用者進行 MFA | 僅限報告的條件式存取原則，需要使用者的多重要素驗證。 所有的雲端應用程式都需要這種方式。 |
| 封鎖舊版驗證 | 僅限報告的條件式存取原則，以封鎖舊版用戶端驗證。 |
| 在 Microsoft 端點管理員中註冊裝置– Azure AD Join | 裝置註冊，以允許租使用者裝置 Microsoft 端點管理員註冊。 這是透過設定 Azure Active Directory 和 Microsoft 端點管理員之間的自動註冊來完成。 |
| 防病毒 (AV) 原則設定 | 具有預先設定 Microsoft Defender 防毒軟體設定之 Windows 裝置的裝置設定檔。 |
| 視窗10符合性原則設定 | 具備預先設定的 Windows 裝置原則，以符合基本規範的需求。 |

## <a name="related-content"></a>相關內容

 (文章[部署 Microsoft 365 Lighthouse 基線](m365-lighthouse-deploy-baselines.md)) 
[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml) (文章) 
