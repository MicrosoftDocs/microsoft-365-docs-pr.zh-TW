---
title: 垃圾郵件和大量電子郵件有什麼不同?
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/7/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: 客戶有時候會 askwhat 垃圾郵件和大量電子郵件之間的差異？本主題的目的在於說明差異，並提供 Exchange Online 和 Exchange Online Protection （EOP）中提供的不同選項的相關資訊。
ms.openlocfilehash: 55924ac5e83ca109fd66d1723cdb7c5f43f20df6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895032"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>垃圾郵件和大量電子郵件有什麼不同?

客戶有時會問「垃圾郵件和大量電子郵件有什麼不同?」。本主題旨在說明其中差異，並提供關於 Exchange Online 和 Exchange Online Protection (EOP) 中針對這兩種郵件而提供之不同選項的資訊。
  
 **什麼是垃圾郵件？**
  
垃圾郵件是一種「垃圾」郵件，即服務所篩選的來路不明 (通常是不想要的) 電子郵件。服務預設會根據傳送端 IP 位址的信譽來拒絕垃圾郵件。不過，郵件如果通過 IP 檢查、但被內容篩選分類為垃圾郵件，則會傳送至預定收件者的 [垃圾郵件] 資料夾。 
  
> [!NOTE]
> 對內容篩選郵件執行的動作可透過 Exchange 系統管理中心（EAC）中的內容篩選原則加以設定，如[Office 365 中的設定反垃圾郵件原則](configure-your-spam-filter-policies.md)所述。 此外，如果您不同意垃圾郵件分類，您可以透過幾種方式來報告您認為是垃圾郵件或非垃圾郵件的郵件，如[將垃圾郵件、非垃圾郵件和網路釣魚詐騙郵件提交給 microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)所述。 
  
 **什麼是大量電子郵件？**
  
大量電子郵件 (也稱為灰色郵件) 是一種較難分類出來的電子郵件類型。不像垃圾郵件是一種持續性威脅，大量電子郵件通常不太包含會重傳的廣告或行銷訊息。有些使用者想要大量電子郵件 (事實上，他們可能刻意登記要收到這些郵件)，有些使用者則認為這類郵件是垃圾郵件。例如，有些使用者想要收到 Contoso Corporation 寄來的廣告電子郵件或未來某個網路安全大會的邀請，有些使用者則認為這類電子郵件是垃圾郵件。
  
## <a name="how-to-manage-bulk-email"></a>如何管理大量電子郵件

要如何管理大量電子郵件，這並不是個非黑即白的決策，因為如果將所有大量電子郵件都分類為垃圾郵件，則想要它的使用者可能會抱怨並將它提交成誤標記為垃圾郵件的誤判 (非垃圾郵件) 郵件。另一方面，如果讓所有大量電子郵件都通過，則不想要它的使用者可能會抱怨並將它提交成誤進收件匣的漏擋垃圾郵件 (誤判正常)。
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>在內容篩選原則中啟用大宗郵件敏感度控制

根據您公司在大量電子郵件上的原則，系統管理員可以選擇指派大量電子郵件的臨界值。 設定可透過 EAC 中的內容篩選原則加以設定。 如需步驟，請參閱[Office 365 中的設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。 您可以選擇1-9 中的臨界值設定，其中1將最大的大量電子郵件標記為垃圾郵件，而9則可以傳遞大多數大量電子郵件。 服務則會執行已設定的動作 (例如將郵件傳送至收件者的 [垃圾郵件] 資料夾)。 
  

