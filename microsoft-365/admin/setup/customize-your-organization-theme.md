---
title: 自訂群組織的主題
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: '瞭解如何變更 Microsoft 365 的預設主題，並加以自訂，使其符合您公司的徽標或色彩。 '
ms.openlocfilehash: 7392ea43c32635a9852b0fbceed80475d99c9d64
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580682"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>自訂群組織的 Microsoft 365 主題

做為 Microsoft 商務用 Microsoft 365 訂閱的系統管理員，您可以變更顯示在組織中所有人員的上方導覽列中的預設主題：

- 新增您的公司標誌。
- 變更色彩，使其符合其他品牌。
- 當使用者選取您的徽標時，請新增目的地連結。
  
## <a name="customize-your-theme-in-the-admin-center"></a>在系統管理中心自訂您的主題

1. 在系統管理中心中，移至 [ **設定** \> **組織設定** ] 頁面，然後選擇 [ **組織設定檔** ] 索引標籤。

2. 在 [ **組織設定檔** ] 索引標籤上選擇 [ **自訂主題**]。

3. 在 [ **海關 themes** ] 面板上，變更組織所需的主題元素：

    - **使用自訂的標誌影像**：選擇是否要使用 URL 中的影像或上傳影像。 如果您使用 URL，請確定 URL 使用 HTTPS，且圖像為任何大小任何格式的 200 x 30 圖元。 您可以將在 10 KB 以內的徽標上傳為 JPG、PNG、GIF 或 SVG 格式的 200 x 30 圖元。

      > [!NOTE]
      > 若要在 SharePoint 行動裝置應用程式中顯示徽標，請只使用 SVG 影像。 以任何其他格式上傳的影像，不會顯示在應用程式中。 在 SharePoint 行動裝置應用程式中無法按一下標誌。

    - **讓標誌可按一下**：您可以在導覽列中使用您的徽標，作為任何公司資源的連結。 您可以在這裡輸入徽標的 URL，從 HTTP://或 HTTPs://開始。 這是選擇性的。

    - **選取背景圖像**：選取影像並上傳您自己的 JPG、PNG 或 GIF 解析度為 1366 x 50 圖元，不超過 15 KB。 此背景影像會在每個頁面的上方導覽列中出現。

      > [!NOTE]
      > 包含文字的影像可能無法如預期般顯示。 顯示在導覽列右邊和左邊的內建元素可能會因服務而異，而且您的文字可能會被這些元素遮住。

    - **導覽列色彩**：選取要用於導覽列背景的色彩。 導覽列會出現在每一頁的頂端。

    - **文字和圖示**：選取用於上方導覽列中文字和圖示的顏色。

    - **強調文字色彩**：選取導覽列按鈕懸停色彩及頁面重音（如按鈕和某些應用程式中的文字）所使用的色彩。

    - **防止使用者覆寫主題**：翻轉此切換，可防止使用者從我們的主題選取範圍選取自己的主題。 這不會讓使用者無法設定高對比主題。

    - **顯示使用者名稱**：選擇是否要在使用者登入時，在頁面右上方的 [帳戶管理員] 的進入點顯示使用者的完整名稱。 根據預設，使用者會看到其照片或其縮寫，如果沒有上載任何照片。

4. 選取 **[儲存變更]**。

您可以在系統管理中心中立即看到新的主題。 在短暫的延遲之後，您可以在整個 Microsoft 365 中看到它，包括在 Outlook 的頁面、SharePoint、 [SharePoint 行動應用程式 iOS](https://support.microsoft.com/office/339402ce-16bb-4c97-9475-0c5375ccef7a)，以及 [SharePoint 適用于 Android 的行動應用程式](https://support.microsoft.com/office/d875654b-fb0a-4dbe-a17a-a676cf936284)。

您可以隨時移除自訂圖示或自訂色彩。 只需回到 [主題] 頁面，然後選取 [ **移除自訂主題**]。
  
## <a name="best-practices"></a>最佳做法

- **標誌影像**：使用 SVG 檔案類型，讓您的徽標顯示在所有畫面上的高解析度及所有縮放比例。

- **自訂色彩**：選擇具有您挑選之 **標誌圖像** 之高對比比例的導覽列 **背景色彩**。 選擇與導覽列 **背景色彩** 具有高對比比例的 **文字和圖示** 色彩，讓所有文字和圖示清晰可見。

- **強調色彩**：選擇在白色或淺色背景上顯示效果很好的色彩。 口音色彩是用來色彩顯示在白色或淺色背景上的某些連結和按鈕。 例如，口音色彩是用來在使用者的收件匣和其 Office.com 入口網站頁面上色彩元素。
  
- **對比度**：文字、圖示或按鈕色彩及背景色彩的建議對比比率為4.5：1。
  
## <a name="related-articles"></a>相關文章

[在 [我的 App] 頁面和 App 啟動器上新增自訂磚](../manage/customize-the-app-launcher.md)