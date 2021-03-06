---
title: Admin center 中的 microsoft 365 報告-Microsoft Office 啟用
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 87c24ae2-82e0-4d1e-be01-c3bcc3f18c60
description: 瞭解如何取得 Office 啟用報告，以瞭解哪些使用者已啟用其 Office 訂閱，以及識別可能需要其他説明的使用者。
ms.openlocfilehash: e82c67560be7ccaa3780547e6c95a2823e7f0adf
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514989"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-office-activations"></a>Admin center 中的 microsoft 365 報告-Microsoft Office 啟用

Microsoft 365 **報告** 儀表板會向您顯示組織中各產品的活動概況。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。 請參閱[報告概觀主題](activity-reports.md)。
  
您可從 [Office 啟用] 報告中檢視哪些使用者至少已在一部裝置上啟用其 Office 訂閱。 它可提供 Microsoft 365 應用程式（適用于企業、Project 和 Visio Pro for Office 365 訂閱）的細目分類，以及在桌面和裝置上進行的啟動細分。 此報告有助您找出可能需要額外協助的使用者，並支援他們啟用其 Office 訂閱。
  
> [!NOTE]
> 您必須是 Microsoft 365 中的全域系統管理員、全域讀取者或報告讀取器、Exchange、SharePoint、小組服務、小組通訊或商務用 Skype 系統管理員，才能查看報告。  
  
## <a name="how-to-get-to-the-office-activations-report"></a>如何查看 Office 啟用報告

1. 在系統管理中心中，移至 **[報告]** \> <a href="https://admin.microsoft.com/Adminportal/Home?source=applauncher#/reportsUsage" target="_blank">[使用量]</a> 頁面。

    
2. 從 [ **選取報告** ] 下拉式清單中，選取 [ **Office 365** 啟用] \> ****。 
  
## <a name="interpret-the-office-activations-report"></a>解讀 Office 啟用報告

您可以透過查看 [啟用] 和 [**使用者**]**圖表，以** 查看組織的 Office 啟用。 
  
![Office 啟用計數](../../media/8c0ae08d-2d71-4437-9147-12c345bb5e9d.png)
  
|項目|描述|
|:-----|:-----|
|1  <br/> |[Office 啟用] 報告會顯示目前的 Office 授權啟用狀況 [截至圖表右上角顯示的報告日期為止]。  <br/> |
|2   <br/> |每個報告中的資料通常會涵蓋過去24到48小時。  <br/> |
|3   <br/> |啟用 **圖表會** 顯示桌面機和裝置上的 Office 啟用計數。  <br/> |
|4   <br/> |[ **使用者** ] 圖表會顯示已啟用的使用者計數，以及已在桌面或裝置上啟用 Office 訂閱的使用者。  <br/> |
|5   <br/> | **在 [啟用**] 圖表上，Y 軸是 Office 啟用的計數。  <br/>  在 [ **使用者** ] 圖表上，Y 軸是使用者啟用 Office 的執行活動。  <br/>  這兩份圖表的 X 軸都代表該特定報告的已選取日期範圍。  <br/> |
|6   <br/> |您可以透過選取圖例中的專案來篩選所看到的圖表。 例如， **在 [啟用** ] 圖表中，選取 [ **windows 作業系統**]、[ **Mac 作業系統**]、[ **windows 10** 行動裝置]、[ **iOS** ] 或 [ **Android** ]，以查看只與各項相關的資訊。 變更此選取項目並不會變更格線資料表中的資訊。 <br/> ![裝置的啟用資料](../../media/59d3ec6e-2a6e-4b21-8aac-c73038c47b9f.png)  <br/> |
|7   <br/> | 下表顯示使用者層級的 Office 啟用的明細。這是已獲得 Office 產品指派的所有使用者清單。您可以新增其他欄至表格中。  <br/> ![Office 啟用可用欄](../../media/410a4baa-cef8-4676-bf7c-02a907a3a575.png)<br/> [使用者 **名稱**] 是使用者的電子郵件地址。  <br/> [**顯示名稱**] 是使用者的完整名稱。  <br/> **產品授權** 是指指派給此使用者的產品。  <br/> [**上次啟動日期**] 是指使用者在桌面上或裝置上啟用 Office 的日期。  <br/> 如果使用者使用 Office 透過共用電腦啟用，則 **使用中共用電腦啟用** 為 true。 <br/> **Windows** 指的是使用者啟用 Office 的 Windows 桌面數目。  <br/> **Mac** 是指使用者啟用 Office 的 Mac 桌面數目。  <br/> **Windows 10** 行動裝置指的是使用者啟用 Office 的 Windows 10 行動裝置數目。  <br/> **iOS** 是指使用者在其上啟用 Office 的 iOS 裝置數目。  <br/> **Android** 指的是使用者啟用 Office 的 Android 裝置數目。  <br/>  如果貴組織的原則防止您檢視可識別之使用者資訊的報告，您可以變更所有這類報告的隱私權設定。 請參閱 [Microsoft 365 系統管理中心的活動報告](activity-reports.md)中的 [報告] 區段中的 [**隱藏使用者詳細資料**]。  <br/> |
|||
   

