---
title: 部署 Microsoft 365 Lighthouse 基線
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
description: 針對受管理的服務提供者 (MSPs) 使用 Microsoft 365 Lighthouse，瞭解如何部署 Microsoft 365 Lighthouse 的比較基準。
ms.openlocfilehash: f329993443b4bd3003a3e8460d77f9b73ac10fc6
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409101"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>部署 Microsoft 365 Lighthouse 基線 

> [!NOTE]
> 本文所述的功能都是在預覽中進行變更，而且只有符合 [需求](m365-lighthouse-requirements.md)的合作夥伴才能使用。 如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。

Microsoft 365 Lighthouse 基準可讓您部署標準的受管理租使用者設定，以保護租使用者使用者、裝置和資料。 Microsoft 365 Lighthouse 標配六個預設基準設定：

- 需要對系統管理員進行 MFA
- 需要對使用者進行 MFA
- 封鎖舊版驗證
- 在 Microsoft 端點管理員中設定裝置註冊– Azure AD Join
- 設定 Windows 裝置的 Defender 防病毒原則
- 設定 Windows 裝置的相容性原則

## <a name="before-you-begin"></a>開始之前

請確認您和您的客戶租使用者符合[Microsoft 365 Lighthouse 需求](m365-lighthouse-requirements.md)中所列的需求。

## <a name="learn-more-about-the-default-baseline"></a>深入瞭解預設基線

從左導覽窗格選取 [ **基線** ]，以開啟 [比較基準] 頁面。 您會看到預設的基準已經新增至預設租使用者群組 (所有承租人) 。 若要查看預設的基準設定，請選取 [ **view 基線** ] 以開啟 [預設基線] 頁面。 設定會列為部署步驟。 選取任何部署步驟，以查看部署詳細資料和使用者影響。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="預設基線頁面的螢幕擷取畫面。 >。":::

## <a name="deploy-a-baseline-configuration"></a>部署基準設定  

1. 在左導覽頁面中，選取 [ **承租人** ] 以查看您的架承租人清單。

2. 選取您要部署基準設定的承租人。

3. 選取 [ **部署計畫** ] 索引標籤，以查看已新增至租使用者之部署計畫之基準的所有部署步驟。

4. 選取部署步驟以開啟 [部署步驟] 頁面。

5. 選取 **[套用] 將選取** 的部署步驟套用至租使用者。 如果部署步驟指出「此動作需要手動步驟」，請務必完成手動步驟，以便正確套用部署步驟。

## <a name="related-content"></a>相關內容

[使用基線部署標準租](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) 使用者設定 (篇文章) \
[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml) (文章) 