---
title: 最新版本的廣泛部署範例
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: 部署最新版本的組織如何使用適用於 Windows 10 和 Microsoft 365 Apps 的通道。
ms.openlocfilehash: fd1d8ddd342b2781470378c879ef70d2ba304316
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686163"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a>最新版本的廣泛部署範例

此通道組態範例適用於使用最新版本的快速部署，以符合這些商業優先順序的組織：

- 使用 Microsoft 應用程式和服務確保業務持續性。
- 利用 Microsoft 提供的最新功能和修正功能，將裝置、服務及資料安全性最大化。
- 利用 Microsoft 提供的最新功能，將使用者生產力最大化。

這些目標會轉換為 IT 工作，以利用使用者和裝置的一個具代表性子集在廣泛部署之前驗證功能，找出快速生產部署與早期審查之間的平衡。

我們的範例組織在全球於歐洲、非洲、亞太地區和美洲各地有 5,000 名員工。 70% 的員工使用 Microsoft 365 E3，而其餘組織使用 Microsoft 365 E5。

>[!Note]
>此範例的設計可向您說明如何使用部署階段和群組，其適用於許多類型和規模的組織。
>

此組織的 IT 基礎結構： 

- 多數具同質性，使用 Windows、Microsoft 365 Apps 和 Microsoft 雲端服務，涵蓋已安裝基座的 60%。 在多年密集作業以簡化並改善 IT 基礎結構之後，仍存在一些舊版系統。
- 由經驗豐富的人員維護，且任務目標是要透過遵循 Microsoft 在其版本的引領之下，讓使用者和其裝置具生產力且受保護。

## <a name="deployment-and-update-stages"></a>部署和更新階段

根據最新版本的快速部署目標，此範例組織使用雙步驟部署程序。

1. **使用預覽或試驗部署：** 運用早期採用者、IT 人員、具代表性組態的使用者和訓練人員進行驗證並反覆執行。 

   早期採用者、IT 人員、具代表性組態的使用者可先使用其他應用程式和裝置來驗證功能，之後再將新功能推出至組織的其餘應用程式和裝置。

   變更管理員可在廣泛推出之前快速瀏覽新功能，且可以規劃通知訊息和推出。

   訓練人員可以在廣泛推出之前，針對新功能規劃新的內部課程，或更新現有課程。

2. **生產部署：** 依地區、部門或其他部署方法向所有其餘使用者推出。

## <a name="deployment-configuration-for-windows-10"></a>Windows 10 的部署組態

整體目標是在驗證「發行預覽通道」變更之後，透過一組具代表性使用者及其裝置來執行最新「半年通道」發行的廣泛部署。

如需有關 Windows 10 部署方法和策略的詳細資訊，請參閱 [Windows 10 部署](https://docs.microsoft.com/windows/deployment/)。

| 階段 | 通道 | 部署群組 |
|:-------|:-------|:-----|
| 試驗 |  **發行預覽通道**  <ul><li>目的：部署功能更新給 IT 人員和早期採用者，以驗證具代表性的裝置和組態 (語言、協力廠商應用程式)。 </li><li> 說明：商業客戶完全符合規範並受支援，且不會計入您的支援合約。 </li></ul> | **Win10ReleasePreviewChannel** (範例名稱) <br><br> 成員是包含下列項目的群組： <ul><li> 跨部門和位置的 Windows 愛好者 </li><li> 具有需要驗證組態的人員 </li><li> IT 系統管理員和 IT 部署人員 </li><li> 變更管理員 </li><li> 內部訓練人員 </li></ul> |
| 生產環境 |  **半年通道**  <ul><li>目的：將最新功能更新廣泛部署至組織的其餘部分。 </li><li> 說明：完全符合規範並受支援。 </li></ul> | **Win10SemiAnnualChannel** (範例名稱) <br><br> 成員為不在 Win10ReleasePreviewChannel 群組中的所有使用者。 |
||||

此組織使用與部署半年通道發行 (例如 Windows Update 或 Windows Server Update Services) 的相同方式來部署發行預覽通道承載的最佳做法，並對這兩個通道更新套用相同原則。

持續更新程序：

1. 將發行預覽通道變更部署至 Win10ReleasePreviewChannel (範例名稱) 部署群組。
2. Win10ReleasePreviewChannel 群組成員向 IT 部署人員確認「發行預覽通道」變更可運作，而 IT 部署人員可以向 Microsoft 提供意見反應，並等候下一個「發行預覽通道」變更，以進行其他驗證。
3. 半年通道功能變更會部署到 Win10SemiAnnualChannel 部署群組。 

>[!Note]
>雖然半年通道為建議的通道，您的 IT 部門應利用其管理工具，並決定何時在組織內部署最新的半年通道發行，然後分批推出。
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a>Microsoft 365 Apps 的部署組態

整體目標是在驗證「目前通道 (預覽)」變更之後，透過一組具代表性使用者來執行最新「目前通道」發行的廣泛部署。

如需有關 Microsoft 365 Apps 部署方法和策略的詳細資訊，請參閱 [Microsoft 365 Apps 部署](https://docs.microsoft.com/deployoffice/plan-office-365-proplus)。

| 階段 | 通道 | 部署群組 |
|:-------|:-------|:-----|
| 試驗 |  **目前通道 (預覽)** <ul><li> 目的：{讓具代表性的一組使用者可以一瞥新 Microsoft 365 Apps 的功能} 只要功能的部署經過「目前通道 (預覽)」 使用者的測試並針對生產準備就緒，功能的部署會隨即更新。 </li><li> 說明：完全符合規範並受支援。</li><li> 頻率：每個月更新 2 到 3 次。 </li></ul> | **AppsCurrentChannelPreview** (範例名稱) <br><br> 成員是包含下列項目的群組： <ul><li> 跨部門和位置的 Office 應用程式愛好者 </li><li> 具有需要驗證組態的人員 </li><li> IT 系統管理員和 IT 部署人員 </li><li> 變更管理員 </li><li> 內部訓練人員 </li></ul>|
| 生產環境 | **目前通道** <ul><li> 目的：將最新功能更新廣泛部署至組織的其餘部分。 </li><li> 說明：完全符合規範並受支援。 </li></ul> |  **AppsCurrentChannel** (範例名稱) <br><br> 成員為不在 AppsCurrentChannelPreview 群組中的所有使用者。 |
|||

持續更新程序：

1. 目前通道 (預覽) 的變更會部署至 AppsCurrentChannelPreview 部署群組。
2. AppsCurrentChannelPreview 群組成員向 IT 部署人員確認目前通道 (預覽) 變更可運作，而 IT 部署人員可以向 Microsoft 提供意見反應，並等候下一個「目前通道 (預覽)」發行，以進行其他驗證。
3. 目前通道變更會部署至 AppsCurrentChannel 部署群組。 

## <a name="visual-summary"></a>視覺摘要

以下是此範例組織所使用的產品、通道和部署群組。 

![用於廣泛部署最新版本的部署群組](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a>另請參閱

[部署和更新通道範例組態](deploy-update-channels-examples.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)
