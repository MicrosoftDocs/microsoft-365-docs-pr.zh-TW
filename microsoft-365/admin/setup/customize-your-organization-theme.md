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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: '瞭解如何變更 Microsoft 365 的預設主題，並自訂主題以配合公司標誌或色彩。 '
ms.openlocfilehash: 9d17ac800fb0fe38627fcb7842ed5555d2ac28ae
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926879"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>為您的組織自訂 Microsoft 365 主題

做為商務用 Microsoft 365 訂閱的系統管理員，您可以變更組織中每個人的上方流覽列顯示的預設主題：

- 新增您的公司標誌。
- 變更色彩以配合品牌的其餘部分。
- 新增使用者選取您的標誌時要前往的目的地連結。
  
## <a name="customize-your-theme-in-the-admin-center"></a>在系統管理中心自訂主題

1. 在系統管理中心中，前往設定 \> **組織** 設定頁面，然後選擇組織 **設定檔分頁**。

2. 在組織 **設定檔的 Tab** 上，選擇自訂 **主題**。

3. 在主題 **面板** 上，變更您為組織想要的主題元素：

    - **使用自訂標誌影像**：選擇是否要使用 URL 中的影像或上傳影像。 如果您使用 URL，請確認 URL 是使用 HTTPS，且圖像大小為 200 x 30 圖元，為任何大小的任何格式。 您可以在 10 KB 以下上傳 JPG、PNG、GIF 或 SVG 格式的 200 x 30 圖元標誌。

      > [!NOTE]
      > 若要在 SharePoint 行動應用程式中顯示標誌，請僅使用 SVG 影像。 以任何其他格式上傳的影像不會顯示在應用程式中。 標誌在 SharePoint Mobile App 中無法點按。

    - **讓標誌可點** 按一下：您可以在流覽欄中使用標誌做為任何公司資源的連結。 您可以在這裡輸入標誌的 URL，從HTTP://或HTTPs://。 這是選擇性的。

    - **選取背景影像**：選取影像，然後上傳您自己的 JPG、PNG 或 GIF ，解析度為 1366 x 50 圖元，且不超過 15 KB。 此背景影像會在每個頁面的上方導覽列中出現。

      > [!NOTE]
      > 包含文字的影像可能無法如預期方式顯示。 顯示在流覽欄左右兩側的內建元素可能會隨服務而不同，而且您的文字可能會因這些元素而遮住了。

    - **流覽欄色彩**：選取用於流覽欄背景的色彩。 流覽列會顯示于每一頁的頂端。

    - **文字和圖示**：選取用於上方導覽列中文字和圖示的顏色。

    - **強調色**：選取用於流覽欄按鈕的色彩，以將游標停留在色彩和頁面重音上，例如按鈕和特定應用程式上的文字。

    - **防止使用者覆蓋主題**：翻轉此切換開關以防止使用者在我們的主題選取範圍中自行選擇主題。 這無法防止使用者設定高對比主題。

    - **顯示使用者名稱**：選擇在使用者已簽署時，是否要在進入點顯示使用者的全名，並顯示在頁面右上方的帳戶管理員。 根據預設，如果沒有上傳相片，使用者會看到他們的相片或縮寫。

4. 選取 **[儲存變更]**。

您可以馬上在系統管理中心看到新的主題。 經過一小段延遲之後，您可以在整個 Microsoft 365 中查看它，包括 Outlook、SharePoint、iOS 版 [SharePoint](https://support.microsoft.com/office/339402ce-16bb-4c97-9475-0c5375ccef7a)行動應用程式，以及 Android 版 [SharePoint 行動](https://support.microsoft.com/office/d875654b-fb0a-4dbe-a17a-a676cf936284)應用程式上的頁面。

您可以隨時移除自訂圖示或自訂色彩。 只要返回主題頁面，然後選取移除 **自訂主題。**
  
## <a name="best-practices"></a>最佳做法

- **標誌影像**：使用 SVG 檔案類型，讓標誌在所有螢幕上及所有縮放等級上以高解析度顯示。

- **自訂色彩**：選擇具有高對比比例的 **Nav bar** 背景色彩，以及 **您** 挑選的標誌影像。 選擇高 **對比度** 的文字和圖示色彩，讓所有文字和圖示清楚顯示。

- **強調色**：挑選一個在白色或淺色背景上顯示的色彩。 強調色是用來為顯示在白色或淺色背景上的連結和按鈕著色。 例如，重音色彩可用來為使用者之信箱及其入口網站頁面上Office.com元素。
  
- **對比比例**：建議的文字、圖示或按鈕色彩與背景色彩之間的對比比例為 4.5：1。
  
## <a name="related-articles"></a>相關文章

[在 [我的 App] 頁面和 App 啟動器上新增自訂磚](../manage/customize-the-app-launcher.md)