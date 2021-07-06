---
title: DLP 如何與安全性 & 規範中心 & Exchange 系統管理中心的運作方式
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 瞭解安全性 & 合規性中心中的 dlp 如何使用 dlp 和郵件流程規則 (Exchange 系統管理中心) 的傳輸規則。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7cd4eaafbd334c8886e0e6aa72d8c0e4c53a81e
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300049"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a>DLP 在 Microsoft 365 規範中心與 Exchange 系統管理中心之間的運作方式

在 Microsoft 365 中，您可以在兩個不同的系統管理中心建立「資料遺失防護」 (DLP) 原則：
  
- 在 **Microsoft 365 規範中心** 中，您可以建立單一 DLP 原則，協助保護 SharePoint、OneDrive、Exchange、Teams 和現在端點裝置中的內容。 建議您在這裡建立 DLP 原則。 如需詳細資訊，請參閱 [資料遺失防護參考](data-loss-prevention-policies.md)。
    
- 在 **Exchange 系統管理中心**，您可以建立 DLP 原則，以協助只保護 Exchange 中的內容。 這項原則可以使用 Exchange 郵件流程規則 (也稱為傳輸規則) ，因此它具有處理電子郵件時特有的選項。 如需詳細資訊，請參閱[Exchange 系統管理中心的 [DLP](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)]。
    
在這些系統管理中心建立的 DLP 策略並排運作-本主題說明如何執行。
  
![安全性與合規性中心及 Exchange 系統管理中心的 DLP 頁面](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>安全性 & 規範中心中的 dlp 如何在 Exchange 系統管理中心中使用 dlp 和郵件流程規則

在安全性 & 規範中心建立 DLP 原則之後，原則會部署至原則所包含的所有位置。 若原則包括 Exchange Online，該原則會與其同步處理，並以與在 Exchange 系統管理中心中建立的 DLP 原則完全相同的方式執行。 
  
如果您已在 Exchange 系統管理中心建立 DLP 原則，這些原則將繼續與您在安全性 & 規範中心建立之電子郵件的任何原則並排運作。 不過，請注意，在 Exchange 系統管理中心建立的規則具有優先權。 會先處理所有 Exchange 郵件流程規則，然後處理安全性 & 規範中心的 DLP 規則。
  
這表示：
  
- Exchange 郵件流程規則封鎖的郵件不會透過安全性 & 規範中心內建立的 DLP 規則進行掃描。

- dlp 不會掃描 Exchange 郵件流程規則或任何其他篩選器所執行的郵件。
    
- 如果 Exchange 郵件流程規則會以一種方式修改郵件，使其符合 Security & 合規性中心的 DLP 原則（例如新增外部使用者），則 DLP 規則會偵測到這種情況，並視需要強制執行原則。
    
另請注意 Exchange，使用「停止處理」動作的郵件流程規則不會影響在安全性 & 規範中心處理 DLP 規則的處理常式，他們仍會進行處理。
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>安全性 & 規範中心與 Exchange 系統管理中心的原則提示

原則提示可使用 Exchange 系統管理中心中建立的 dlp 原則和郵件流程規則，或是在安全性 & 規範中心內建立的 dlp 原則使用，但不能同時使用這兩者。 這是因為這些原則儲存在不同的位置，但是原則秘訣只能從單一位置進行繪製。
  
如果您已在 Exchange 系統管理中心中設定原則提示，則在安全性 & 規範中心內設定的任何原則提示，都不會向使用者顯示 Outlook 網頁版和 Outlook 2013 及更新版本，直到您關閉 Exchange 系統管理中心中的秘訣。 這可確保您目前的 Exchange 郵件流程規則將繼續運作，直到您選擇切換到安全性 & 規範中心為止。
  
請注意，當原則提示只能從單一位置繪製時，系統會永遠傳送電子郵件通知，即使您同時在安全性 & 規範中心和 Exchange 系統管理中心中使用 DLP 原則也是一樣。
