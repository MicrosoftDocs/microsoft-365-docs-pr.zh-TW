---
title: Office 365 影片中的租用戶隔離
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，將說明租使用者隔離如何將每個租使用者的儲存影片分別保留在 Office 365 影片中。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fc67b17aa40b3bca9ce6d73ebb7e18319e780339
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918927"
---
# <a name="tenant-isolation-in-office-365-video"></a>Office 365 影片中的租用戶隔離

> [!NOTE]
> Office 365 影片將會由 Microsoft Stream 取代。 若要深入瞭解將智慧加入影片共同作業的新企業影片服務，並瞭解目前 Microsoft 365 影片客戶的過渡計畫，請參閱 [Office 365 video 中轉至 Microsoft Stream](/stream/migrate-from-office-365)。

## <a name="introduction"></a>簡介

Azure 儲存體用來儲存多個 Office 365 服務的資料，包括 Office 365 影片和 Sway。 Azure 儲存體包含 Blob 儲存區，也就是用來儲存非結構化資料的高擴充性、REST 型雲端物件存放區。 Azure 儲存體使用簡易的存取控制模型;每個 Azure 訂閱可以建立一或多個儲存帳戶。 每個儲存帳戶都有單一私密金鑰，用來控制對該儲存體帳戶中所有資料的存取。 這支援與應用程式相關聯的儲存體，而且這些應用程式可完全控制其相關聯的資料;例如，Sway 將內容儲存在 Azure 儲存體中。 Sway 的所有客戶內容都儲存在共用的 Azure 儲存體帳戶中。 每個使用者的內容位於 Azure storage 中個別的 blob 目錄樹中。

管理客戶環境存取權的系統 (例如，Azure 入口網站、SMAPI 等 ) 會在 Microsoft 所運作的 Azure 應用程式內隔離。 這會以邏輯方式將客戶存取基礎結構與客戶應用程式和儲存層分隔開來。

## <a name="tenant-isolation-in-office-365-video"></a>Office 365 影片中的租用戶隔離

[Office 365 影片](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) 是一個企業入口網站，可提供組織，以高安全性組織的目標，以進行電子公告、共用及探索影片內容。 在 Office 365 影片中，每個租使用者的影片都會在所有位置保持隔離和加密，而且只有具有組織影片存取權和許可權的已驗證使用者可以使用這些影片。 Office 365 影片使用技術組合來達成此目的：

- 線上 SharePoint 用來儲存影片檔及中繼資料 (影片標題、描述等等 ) 。 它也會提供安全性與合規性層 (，包括驗證) 和搜尋功能。
- Azure 媒體服務提供轉碼、適應性流式處理、使用 AES 加密) 的安全傳遞 (，以及縮圖功能。

[Azure 媒體服務](https://azure.microsoft.com/services/media-services/) 是一種平臺即服務，可在雲端啟用端對端媒體工作流程。 此平臺提供 REST API，以利用 PlayReady) 進行上傳、編碼、加密 (，以及透過全球的 Azure 資料中心傳遞媒體。

所有上傳的 Office 365 影片都會透過 HTTPS 進行。 當上載影片檔時，它會儲存在 SharePoint 線上，而且檔案的副本會透過加密通道傳送至 Azure 媒體服務。 Azure 媒體服務會將影片 transcodes 成多種格式，以針對觀賞體驗 (例如行動、低頻寬、高頻寬等 ) 進行優化。 這些檔案和上傳時所取得的原始檔案，都是儲存在 Azure Blob 儲存區中。 使用每個 MPEG 通用加密封裝演算法 (或舊版 PlayReady 版本) 進行播放，然後在儲存至 Azure Blob 儲存區之前，使用 AES 256 儲存量加密，以 AES 128 加密檔。  (使用 Azure 媒體服務用戶端 SDK，客戶可以控制使用哪些加密。 例如，在上傳 it Azure Blob 儲存裝置之前，客戶可以套用 Azure 媒體服務儲存加密 (AES 256) 到高價值媒體資產。 ) 

Azure 媒體服務也會產生影片的縮圖，它會隨同縮圖中繼資料一起傳送，以透過加密通道 SharePoint 線上。