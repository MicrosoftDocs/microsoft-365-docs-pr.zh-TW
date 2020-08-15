---
title: SharePoint Online 中的縮製和統合
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: 瞭解如何搭配 Web Essentials 使用縮制和捆綁技術，以減少 HTTP 要求，以及在線上 SharePoint 中載入網頁所需的時間。
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688293"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>SharePoint Online 中的縮製和統合

本文說明如何搭配 Web Essentials 使用縮制和捆綁技術，以減少 HTTP 要求數目，以及減少在線上 SharePoint 載入網頁所需的時間。
  
當您自訂網站時，您可以將大量額外的檔案新增至伺服器，以支援自訂。 新增額外的 JavaScript、CSS 及影像會增加伺服器的 HTTP 要求數目，進而會增加顯示網頁所需的時間。 如果您有多個相同類型的檔案，您可以將這些檔案捆綁到一起，以更快速地下載這些檔案。
  
若為 JavaScript 和 CSS 檔案，您也可以使用稱為縮制的方法，您可以透過移除不必要的空白及其他字元來減少檔案的總大小。
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>使用 Web Essentials 縮制及捆綁 JavaScript 與 CSS 檔案

您可以使用協力廠商軟體（如 Web Essentials）來捆綁 CSS 和 JavaScript 檔案。
  
> [!IMPORTANT]
> Web Essentials 是協力廠商、開放來源、以群組為基礎的專案。 軟體是 Visual Studio 2012 和 Visual Studio 2013 的擴充功能，且不受 Microsoft 支援。 若要下載 Web Essentials，請流覽網站，網址為 [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) 。 
  
Web Essentials 提供兩種捆綁形式：
  
- 。束： CSS 和 JavaScript 檔案
    
- sprite：只有在 Visual Studio 2013 中才能使用的影像 () 
    
如果現有的功能包含一些在自訂主版頁面內參照的署名元素，您可以使用 Web Essentials，例如：
  
![自訂主版頁面中的品牌元素螢幕擷取畫面](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **在 Web Essentials 中建立 TE000127218 與 CSS 捆綁**
  
1. 在 Visual Studio 的 [解決方案資源管理器] 中，選取要包含在束中的檔案。
    
2. 以滑鼠右鍵按一下選取的檔案，然後從快顯功能表中選取 [ **Web Essentials** \> **Create JavaScript 束** 檔案]。 例如： 
    
    ![顯示 Web 基本功能功能表選項的螢幕擷取畫面](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>查看捆綁 JavaScript 與 CSS 檔案的結果

當您建立 JavaScript 與 CSS 束時，Web Essentials 會建立一個稱為食譜檔案的 XML 檔案，該檔案會識別 JavaScript 和 CSS 檔案以及其他一些設定資訊： 
  
![JavaScript 和 CSS 配方檔的螢幕擷取畫面](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
此外，如果在捆綁食譜中將 minify 旗標設定為 true，則檔案的大小也會隨之一起縮小。 這表示已建立新的 minified 的 JavaScript 檔版本，您可以在主版頁面中參照。
  
![Minify 旗標設定為 true 的螢幕擷取畫面](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
當您從網站載入頁面時，您可以使用網頁瀏覽器中的開發人員工具（例如 Internet Explorer 11）來查看傳送至伺服器的要求數量，以及每個檔案的載入時間。
  
下圖是縮制之前載入 JavaScript 與 CSS 檔案的結果。
  
![顯示正在下載 80 個項目的螢幕擷取畫面](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
將 CSS 和 JavaScript 檔捆綁在一起後，每個檔案的要求數目會降至74，而每個檔案的時間則只會稍晚于要個別下載的原始檔案：
  
![顯示正在下載 74 個項目的螢幕擷取畫面](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
在捆綁後，JavaScript 的系序檔案會從815KB 中大幅減少為365KB：
  
![顯示降低下載大小的螢幕擷取畫面](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>建立影像 sprite 以捆綁影像

與捆綁 JavaScript 和 CSS 檔案的方式類似，您可以將許多小圖示及其他常見的圖像組合成較大的 sprite 工作表，然後使用 CSS 來顯示個別的圖像。 使用者的網頁瀏覽器只會下載 sprite 工作表一次，然後再將它快取到本機電腦上，而不是下載每個個別的圖像。 這可減少網頁伺服器的下載數目及來回行程，以提升頁面負載效能。
  
 **在 Web Essentials 中建立影像子畫面**
  
1. 在 Visual Studio 的 [解決方案資源管理器] 中，選取要包含在束中的檔案。
    
2. 以滑鼠右鍵按一下選取的檔案，然後從快顯功能表中選取 [ **Web Essentials** \> **建立影像 sprite** ]。 例如： 
    
    ![顯示如何建立影像精靈的螢幕擷取畫面](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. 選擇用來儲存 sprite 檔案的位置。 Sprite 檔是一個 XML 檔，用來描述 sprite 中的設定和檔案。 下圖顯示 sprite PNG 檔案及其對應的 sprite XML 檔案的範例。
    
    ![精靈檔案的螢幕擷取畫面](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![精靈 XML 檔案的螢幕擷取畫面](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

