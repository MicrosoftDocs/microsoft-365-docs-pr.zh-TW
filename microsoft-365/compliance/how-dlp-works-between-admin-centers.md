---
title: DLP 如何與安全性 & 規範中心 & Exchange 系統管理中心的運作方式
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
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
description: 瞭解安全性 & 合規性中心中的 DLP 如何搭配 DLP 和郵件流程規則使用，以在 Exchange 系統管理中心中 (傳輸規則) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd8a3eb0e7bb859ab9e10551fadd22cc7dcb2a39
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905935"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>DLP 如何在安全性與合規性中心和 Exchange 系統管理中心之間工作

在 Office 365 中，您可以在兩個不同的系統管理中心建立資料遺失防護 (DLP) 原則：
  
- 在 [ **安全性 & 規範中心**] 中，您可以建立單一 DLP 原則，協助保護 SharePoint、OneDrive、Exchange 及現在 Microsoft 小組中的內容。 建議您盡可能在這裡建立 DLP 原則。 如需詳細資訊，請參閱 [安全性 & 規範中心中的 DLP](data-loss-prevention-policies.md)。
    
- 在 **exchange 系統管理中心** 中，您可以建立 DLP 原則，以協助只保護 Exchange 中的內容。 這項原則可以使用 Exchange 郵件流程規則 (也稱為傳輸規則) ，因此它具有處理電子郵件時特有的選項。 如需詳細資訊，請參閱 [Exchange 系統管理中心的 DLP](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。
    
在這些系統管理中心建立的 DLP 策略並排運作-本主題說明如何執行。
  
![安全性與合規性中心和 Exchange 系統管理中心的 DLP 頁面](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>安全性 & 規範中心內的 DLP 如何在 Exchange 系統管理中心中使用 DLP 和郵件流程規則

在安全性 & 規範中心建立 DLP 原則之後，原則會部署至原則所包含的所有位置。 若原則包含 Exchange Online，則該原則同步處理並強制執行，其方式與 Exchange 系統管理中心建立的 DLP 原則完全相同。 
  
如果您已在 Exchange 系統管理中心中建立 DLP 原則，這些原則將繼續對您在安全性 & 合規性中心建立之電子郵件的任何原則進行工作。 不過，請注意，在 Exchange 系統管理中心中建立的規則會具有優先權。 會先處理所有 Exchange 郵件流程規則，然後處理安全性 & 合規性中心的 DLP 規則。
  
這表示：
  
- 由 Exchange 郵件流程規則封鎖的郵件不會透過在安全性 & 合規性中心建立的 DLP 規則進行掃描。
    
- 如果 Exchange 郵件流程規則修改郵件的方式，使其符合安全性 & 合規性中心的 DLP 原則（例如新增外部使用者），則 DLP 規則會偵測到此郵件，並視需要強制執行原則。
    
另外請注意，使用「停止處理」動作的 Exchange 郵件流程規則不會影響在安全性 & 規範中心處理 DLP 規則的處理常式，他們仍會進行處理。
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>安全性 & 規範中心與 Exchange 系統管理中心中的原則提示

原則秘訣可以搭配在 Exchange 系統管理中心中建立的 DLP 原則和郵件流程規則，或是在安全性 & 合規性中心建立的 DLP 原則來運作，但不能同時使用這兩者。 這是因為這些原則儲存在不同的位置，但是原則秘訣只能從單一位置進行繪製。
  
如果您已在 Exchange 系統管理中心中設定原則提示，在安全性 & 合規性中心中所設定的任何原則提示，都不會顯示在網頁和 Outlook 2013 和更新版本中 Outlook 的使用者，除非您關閉 Exchange 系統管理中心中的秘訣。 這可確保您目前的 Exchange 郵件流程規則可以繼續運作，直到您選擇切換到安全性 & 規範中心為止。
  
請注意，當原則提示只能從單一位置繪製時，系統會永遠傳送電子郵件通知，即使您同時在安全性 & 規範中心和 Exchange 系統管理中心中使用 DLP 原則也是一樣。
