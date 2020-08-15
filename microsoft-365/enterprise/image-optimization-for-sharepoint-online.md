---
title: SharePoint 線上傳統發佈網站的影像優化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: 瞭解如何使用格式副本及子畫面，以提升 SharePoint 線上傳統發佈網站上的影像效能。
ms.openlocfilehash: 47d0f085c13c192417842fcef88c695fe875124c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688495"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a>SharePoint 線上傳統發佈網站的影像優化

網頁的載入速度取決於轉譯頁面（包括影像、HTML、JavaScript 及 CSS）所需之所有元件的組合大小。 影像是讓您的網站更有吸引力，但其大小可能會影響效能的極佳方式。 透過壓縮和調整大小，並使用子畫面，您可以抵消超大影像的效果。 您可以使用 SharePoint 影像轉譯，上傳單一大影像，並顯示影像的區段，以允許重複使用，而不是重新載入。

>[!NOTE]
>本主題適用于 SharePoint 線上傳統發佈網站，而非現代入口網站。 如需 SharePoint Online 新式入口網站中的圖像優化的詳細資訊，請參閱 [在 SharePoint Online 新式入口網站頁面中優化圖像](modern-image-optimization.md)。
  
## <a name="using-sprites-to-speed-up-image-loading"></a>使用子畫面加快影像載入速度

|||
|:-----|:-----|
| 圖像 sprite 包含許多較小的影像。 使用 CSS 您可以選取複合影像的一部分，以絕對位置顯示頁面的特定部分。 基本上，您只需在頁面上移動單一影像，而不是載入多個影像，並透過小型視窗顯示該圖像的一小部分，在此視窗中，會向使用者顯示其子畫面影像的必要部分。 SharePoint 線上使用 sprite，在 sprite spcommon.png 中顯示其各種圖示。  <br/>  如下所述：  <br/>  影像壓縮  <br/>  圖像優化  <br/>  SharePoint 影像轉譯  <br/> |![Spcommon 的螢幕擷取畫面](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)|
   
這可提高效能，因為您只下載一個影像，而不是多個，然後再快取並重複使用該影像。 即使圖像未保持快取，但只要有單一影像（而不是多個影像），此方法就會減少對伺服器的 HTTP 要求總數，以減少頁面載入時間。 這實際上是一種圖像捆綁的形式。 如果影像不經常變更（例如，如上所述的 SharePoint 範例中所示），這是非常實用的技巧。 您可以使用 [Web Essentials](https://vswebessentials.com/)，協力廠商，以群組為基礎的專案，在 Microsoft Visual Studio 中輕鬆做到這一點。 如需詳細資訊，請參閱 [SharePoint Online 中的縮制和捆綁](https://go.microsoft.com/fwlink/?LinkId=708698)。
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a>使用影像壓縮及優化，以加速頁面載入速度

影像壓縮及優化是關於減少您在網站上使用之影像的檔案大小。 通常，減少圖像大小的最佳技巧是將圖像的大小調整為將在網站上查看的最大尺寸。 使用的影像沒有任何意義的意義。 使用影像編輯器確定影像的尺寸是否正確，是減少頁面大小的快速快捷的方式。
  
圖像大小正確之後，下一步是優化這些影像的壓縮。 有各種可用於壓縮及優化的工具，包括照片庫和協力廠商工具。 要壓縮的關鍵是為了盡可能縮小檔案大小，而不會喪失任何可辨識的品質給使用者。 請務必在高定義顯示幕上測試壓縮檔，以確保這些檔案的外觀仍有效。
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a>使用 SharePoint 影像轉譯器加速頁面下載

影像轉譯是 SharePoint Online 中的一項功能，可讓您根據預先定義的影像尺寸，提供不同版本的影像。 當網站上的 CSS 已修復使用者所產生的圖像內容或圖像維度（例如寬度和高度）時，這一點特別重要。 即使圖像是由 CSS 修正，仍然會載入完整解析度影像。 在此情況下，您可以使用影像轉譯來減少檔案大小。
  
> [!NOTE]
> 轉譯功能只有在啟用發佈功能時才能 SharePoint。 您可以在 [設定網站設定] 下啟用發佈 [ \> \> 管理網站功能 \> SharePoint 伺服器發佈]。 否則不會出現此選項。
  
影像轉譯重新調整大小的運作方式是取得您定義的最小尺寸（寬或高），然後調整圖像大小，以根據鎖定的長寬比例自動調整其他尺寸的大小。 根據預設，它會將圖像從中心裁剪掉剩餘的維度。 例如，如果您定義 100px wide 和50px 的格式副本，而您的原始影像為1000px 寬和800px 高，將會調整大小，使800px 維度現在50px，而1000px 維度 (現在會從圖像中心裁剪的 62.5 px) 。
  
步驟相對簡單，但若要使用轉譯格式，您必須先在 SharePoint 網站上的轉譯，再新增影像。 此外，您還需要 SharePoint 伺服器發佈基礎結構 (網站集合層級) 和 SharePoint 的伺服器發佈 (網站層級) 功能已開啟。
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a>新增影像格式副本以加速頁面載入速度
  
1. 確認執行此程式的使用者帳戶至少具有網站集合最上層網站的「設計」許可權，且該網站已發佈至網頁。

2. 在網頁瀏覽器中，移至發佈網站集合的最上層網站。

3. 選擇 [ **設定** ] 圖示。

4. 在 [ **網站設定** ] 頁面的 [ **外觀與風格** ] 區段中，您將會看到內建的影像轉譯。

    您可以使用現成的轉譯轉譯，或選擇 [ **影像** 轉譯] 來建立新的格式副本。

    ![影像轉譯的螢幕擷取畫面](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. 在 [ **圖像** 轉譯] 頁面上，選擇 [ **新增專案**]。

    ![新增項目的螢幕擷取畫面](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. 在 [ **新增影像** 轉譯] 頁面的 [ **名稱** ] 方塊中，輸入此格式副本的名稱。

7. 在 [ **寬度** ] 和 [ **高度** ] 文字方塊中，輸入格式副本的寬度和高度（以圖元為單位），然後選擇 [ **儲存**]。

    ![影像轉譯名稱的螢幕擷取畫面](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a>使用影像轉譯的自訂裁剪

根據預設，影像轉譯會從影像的中央產生。 您可以裁剪您要使用的圖像部分，以調整個別圖像的圖像轉譯。 您可以依格式副本逐個裁剪圖像。 透過使用 SharePoint 的 blob 快取，為每個轉譯器建立影像的版本，裁剪圖像可加快頁面載入速度。 這樣一來，伺服器負載便會減少，因為圖像只會重新調整大小一次，然後準備好將其提供給使用者多次。 如需如何裁切圖像呈現方式的詳細資訊，請參閱 [裁剪圖像](https://go.microsoft.com/fwlink/p/?LinkId=525626)轉譯。
  

