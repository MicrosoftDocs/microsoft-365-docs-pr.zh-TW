---
title: Microsoft 365 系統管理中心報告中的 Microsoft Office 啟用
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 87c24ae2-82e0-4d1e-be01-c3bcc3f18c60
description: 了解如何取得 Office 啟用報告，若要知道哪些使用者已啟用其 Office 訂閱，並識別可能需要額外協助的使用者。
ms.openlocfilehash: de558c75009007bbc02a1c5ca51bb7c86a97c47a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353754"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-office-activations"></a>Microsoft 365 系統管理中心報告中的 Microsoft Office 啟用

Microsoft 365**報告**儀表板顯示您的活動概觀跨組織中的產品。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
您可從 [Office 啟用] 報告中檢視哪些使用者至少已在一部裝置上啟用其 Office 訂閱。它提供 Office 365 專業增強版、Project 及 Visio Pro for Office 365 訂閱啟用的明細，以及各桌上型電腦和裝置的啟用明細。此報告有助您找出可能需要額外協助的使用者，並支援他們啟用其 Office 訂閱。
  
> [!NOTE]
> 您必須是全域系統管理員在 Microsoft 365 或 Exchange、 SharePoint、 商務用 Skype 系統管理員或報告讀取者，才能查看報告。 
  
## <a name="how-to-get-to-the-office-activations-report"></a>如何查看 Office 啟用報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">[使用量]</a> 頁面。

    
2. 從 [**選取 [報告]** 下拉式清單，選取 [ **Office 365** \> **啟用**。 
  
## <a name="interpret-the-office-activations-report"></a>解讀 Office 啟用報告

您可以透過檢視貴組織的 Office 啟用查看 [**啟用**] 與 [**使用者**] 圖表。 
  
![計數的 Office 啟用](../../media/8c0ae08d-2d71-4437-9147-12c345bb5e9d.png)
  
|||
|:-----|:-----|
|1  <br/> |[Office 啟用] 報告會顯示目前的 Office 授權啟用狀況 [截至圖表右上角顯示的報告日期為止]。  <br/> |
|2  <br/> |每個報告中的資料通常涵蓋的最後一個 24 到 48 小時。  <br/> |
|3  <br/> |[**啟用**] 圖表顯示您的 Office 啟用計數桌上型電腦和裝置上。  <br/> |
|4  <br/> |[**使用者**] 圖表會顯示已啟用的使用者和已啟用電腦或裝置上的 Office 訂閱的使用者計數..  <br/> |
|5  <br/> | 在 [**啟用**] 圖表中，Y 軸是 Office 啟用數目。  <br/>  在 [**使用者**] 圖表中，Y 軸是使用者的執行中活動啟用 Office。  <br/>  這兩份圖表的 X 軸都代表該特定報告的已選取日期範圍。  <br/> |
|6  <br/> |您可以篩選您會看到所選取項目在圖例中的圖表。 例如，在 [**啟用**] 圖表中，選取 [ **Windows 作業系統**、 **Mac OS**、 **Windows 10 行動裝置版**、 **iOS**或**Android**以查看只與其個別相關的資訊。 變更此選取項目並不會變更格線資料表中的資訊。 <br/> ![裝置的啟用資料](../../media/59d3ec6e-2a6e-4b21-8aac-c73038c47b9f.png)  <br/> |
|7  <br/> | 下表顯示使用者層級的 Office 啟用的明細。這是已獲得 Office 產品指派的所有使用者清單。您可以新增其他欄至表格中。  <br/> ![Office 啟用可用的欄](../../media/410a4baa-cef8-4676-bf7c-02a907a3a575.png)<br/> **Username**是使用者的電子郵件地址。  <br/> **顯示名稱**為的完整名稱，如果使用者。  <br/> **產品授權**] 是指派給此位使用者的產品。  <br/> **上次啟用日期**指的是使用者在電腦或裝置啟用 Office 的日期。  <br/> True 是表示如果使用者使用共用的電腦啟用 Office 是**使用共用電腦啟用**。 <br/> **Windows**指的是 Windows 桌上型電腦啟動 Office 的使用者數目。  <br/> **Mac**指的是 Mac 桌上型電腦啟動 Office 的使用者數目。  <br/> **Windows 10 行動裝置版**指的是 Windows 10 行動裝置啟動 Office 的使用者數目。  <br/> **iOS**指的是 iOS 裝置啟動 Office 的使用者數目。  <br/> **Android**是指使用者啟用 Office 的 Android 裝置數目。  <br/>  如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 查看 [**隱藏報告中的使用者詳細資料**] 區段中[的 Microsoft 365 系統管理中心的活動報告](activity-reports.md)中。  <br/> |
|||
   

