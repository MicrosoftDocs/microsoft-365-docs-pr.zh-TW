---
title: 商務用 OneDrive 和 SharePoint Online 中的資料加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: 了解 OneDrive for Business 和 SharePoint Online 中的資料安全性加密基本項目。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca93d04fa21487ad054cd9cb924dff1fc15abfbd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922627"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>商務用 OneDrive 和 SharePoint Online 中的資料加密

了解 OneDrive for Business 和 SharePoint Online 中的資料安全性加密基本項目。
  
## <a name="security-and-data-encryption-in-office-365"></a>Office 365 中的安全性和資料加密

Microsoft 365 是高度安全的環境，可提供多層的廣泛保護：實體資料中心安全性、網路安全性、存取安全性、應用程式安全性和資料安全性。 本文特別著重在OneDrive for Business 和 SharePoint Online 的傳輸中和靜態加密等方面。
  
觀看下列影片，了解資料加密如何運作。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>傳輸中資料的加密

在OneDrive for Business 和 SharePoint Online 中，資料進出資料中心的方式有兩種。
  
- **用戶端與伺服器通訊** 在網際網路上使用 SSL/TLS 連線與OneDrive for Business 通訊。所有 SSL 連線都是使用 2048 位元機碼加以建立。

- **在資料中心間移動資料** 在資料中心間移動資料的主要原因是為了讓異地複寫進行災害復原。例如，SQL Server交易記錄和 Blob 儲存體差異會隨時此管道流動。若己使用私人網路傳輸資料，則系統會進一步以業界領先的加密方式保護資料。 

## <a name="encryption-of-data-at-rest"></a>靜態資料的加密

靜態加密包括兩個元件：BitLocker 磁碟層級加密，以及客戶內容的每一檔案加密。
  
服務針對OneDrive for Business 和 SharePoint Online 部署了 BitLocker。 在 Microsoft 365 多承租人和以多承租人技術為基礎的新專用環境中 SharePoint，每個檔案加密也是在商務用 OneDrive。
  
當 BitLocker 加密磁碟中的所有資料時，每一檔案的加密會進一步地納入每個檔案唯一的加密金鑰。此外，每個檔案的每次更新都會使用自己的加密金鑰進行加密。在儲存之前，已加密內容的金鑰會儲存在與內容不同的實體位置。此加密的每個步驟都會使用搭配 256 位元機碼的進階加密標準 (AES)，並與聯邦資訊處理標準 (FIPS) 140-2 相容。已加密的內容會分散到資料中心的數個容器中，而且每個容器都有唯一的認證。這些認證會儲存在內容或內容金鑰等不同的實體位置。
  
如需有關 FIPS 140-2 規範的詳細資訊，請參閱 [FIPS 140-2 相容性](/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))。
  
檔案層級的靜態加密會利用 Blob 儲存體提供無限制的虛擬儲存體成長空間，以便提供更全面的保護。OneDrive for Business 和 SharePoint Online 中的所有客戶內容都會移轉至 Blob 儲存體。以下是保護資料的方法：
  
1. 所有內容都會以多個金鑰加密，並分散到資料中心。每個要儲存的檔案都會依大小分成一或多個區塊。接著，每個區塊都會使用自己唯一的金鑰加密。也會以相同的方式處理更新：由使用者提交的變更集或差異項目都會分成數個區塊，每個區塊都會以自己的金鑰加密。

2. 所有這些區塊包括檔案、檔案片段及更新差異項目都會在我們的 Blob 存放區中儲存為 Blob。這些區塊也會隨機地分散至多個 Blob 容器中。

3. 用來從其元件中重新組合檔案的「地圖」則儲存在內容資料庫中。

4. 每個 Blob 容器中的存取類型 (包括讀取、寫入、列舉及刪除) 都有自己特有的認證。每個認證集都會保留在安全的金鑰存放區中，且會定期重新整理。

換句話說，每一檔案靜態加密都包含三種不同的儲存類型，每個類型都有不同的功能：
  
- 內容會在 Blob 存放區中儲存為已加密 Blob。每個內容區塊的金鑰都會加密，且分別儲存在內容資料庫中。內容本身不會保留任何解密線索。

- 內容資料庫是 SQL Server 資料庫，它會保留一份地圖，以便尋找並重新組合 Blob 存放庫中保留的所有內容 Blob，以及解密這些 Blob 所需的金鑰。

Blob 存放區、內容資料庫以及金鑰存放區等三種儲存體元件都位於不同的實體位置，而這些元件中保留的資訊其本身均無法使用。如此提供了前所未有的安全性層級。若非存取這三種元件，則無法擷取區塊的金鑰、也無法將金鑰解密以供使用；無法將金鑰與其對應的區塊相關聯，也無法從其組成的區塊中重新建構文件。