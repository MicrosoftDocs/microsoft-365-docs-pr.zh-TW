---
title: 設定反垃圾郵件原則
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/9/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: 垃圾郵件篩選會自動啟用的全公司透過預設的反垃圾郵件原則 （連線篩選器、 垃圾郵件篩選器及輸出垃圾郵件）。 身為系統管理員，您可以檢視和編輯預設的反垃圾郵件原則，使其符合您組織的需求，但是您無法刪除這些原則。 精確性，您也可以建立自訂原則並將它們套用至指定的使用者、 群組或網域中，您組織中。 自訂原則的優先順序預設會高於預設原則，但您可以變更原則的優先順序。
ms.openlocfilehash: 2ee5833bf476123a84411a7ad645b9f8c5d0b2b8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599580"
---
# <a name="configure-the-anti-spam-policies"></a>設定反垃圾郵件原則

垃圾郵件篩選會自動啟用的全公司透過預設的反垃圾郵件原則 （連線篩選器、 垃圾郵件篩選器及輸出垃圾郵件）。 身為系統管理員，您可以檢視和編輯預設的反垃圾郵件原則，使其符合您組織的需求，但是您無法刪除這些原則。 精確性，您也可以建立自訂原則並將它們套用至指定的使用者、 群組或網域中，您組織中。 自訂原則的優先順序預設會高於預設原則，但您可以變更原則的優先順序。 
  
如需設定反垃圾郵件原則的相關資訊，請參閱下列主題：
  
[設定連線篩選原則](configure-the-connection-filter-policy.md) (英文)
  
[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> 若為 EOP 獨立版客戶：EOP 內容篩選預設會將偵測到的垃圾郵件傳送至每位收件者的 [垃圾郵件] 資料夾。 不過，為了確保 [**移至垃圾郵件] 資料夾的郵件**] 動作將會使用內部部署信箱，您必須設定兩個 Exchange 郵件流程規則 （也稱為傳輸規則） 上您的內部部署伺服器，以偵測 EOP 所新增的垃圾郵件標頭。 如需詳細資料，請參閱[確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 
  
[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)
  

