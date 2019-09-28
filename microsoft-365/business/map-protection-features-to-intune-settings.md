---
title: Microsoft 365 商務版中的保護功能如何對應 Intune 設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 8/13/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: 了解 Microsoft 365 商務版中的保護功能如何對應 Intune 設定。 訂閱提供您的授權，來修改 Intune 設定。
ms.openlocfilehash: 316dc8efbe69057f049bf8fadd3c3f41c358a33e
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287949"
---
# <a name="how-do-protection-features-in-microsoft-365-business-map-to-intune-settings"></a>Microsoft 365 商務版中的保護功能如何對應 Intune 設定

## <a name="android-and-ios-application-protection-settings"></a>Android 和 iOS 應用程式保護設定

下表詳述 Android 和 iOS 應用程式原則設定對應至 Intune 設定的方式。
  
尋找 [Intune] 設定中，登入您 Microsoft 365 商務版系統管理員認證時，請移至**系統管理中心**，然後再**Intune**。
  
 **重要：** Microsoft 365 商務版訂閱提供您的授權，來修改設定 Intune 設定。 請參閱[簡介若要開始使用 Intune。](https://docs.microsoft.com/intune/introduction-intune)
  
按一下您想要選取，例如 Android 應用程式原則的原則名稱，然後選擇 [**原則設定**。
  
在**裝置遺失或遭竊時保護工作檔案**
  
|**Android 或 iOS 應用程式原則設定**|**Intune 設定**|
|:-----|:-----|
|在下列時間之後刪除非作用中裝置上的工作檔案  <br/> |將應用程式資料抹除前的離線間隔 (天)  <br/> |
|強制使用者將工作檔案儲存到商務用 OneDrive  <br/> 請注意，僅允許商務用 OneDrive  <br/> |選取可儲存公司資料的儲存體服務  <br/> |
|||
   
在 [**管理使用者如何存取 Office 檔案中的行動裝置**] 下
  
|**Android 或 iOS 應用程式原則設定**|**Intune 設定**|
|:-----|:-----|
|在下列時間之後刪除非作用中裝置上的工作檔案  <br/> |將應用程式資料抹除前的離線間隔 (天)  <br/> |
|強制使用者將工作檔案儲存到商務用 OneDrive  <br/> 請注意，僅允許商務用 OneDrive  <br/> |選取可儲存公司資料的儲存體服務  <br/> |
|加密工作檔案  <br/> |加密應用程式資料  <br/> |
|在 [**管理使用者如何存取 Office 檔案中的行動裝置**] 下 <br/> ||
|需要 PIN 或指紋才能存取 Office App  <br/> | 需要 PIN 才能存取  <br/>  這也會做出下列設定：  <br/> **允許簡單 pin] 設定**為 [**是]** <br/> **Pin 碼長度**設為 4  <br/> **允許指紋取代 pin] 設定**為 [**是]** <br/> 為 [**否]** 的 [**停用應用程式管理裝置的 pin 碼時的 pin 碼** <br/> |
|在登入失敗達下列次數時重設 PIN (在不需要 PIN 時會停用此設定)  <br/> |重設 PIN 前的嘗試次數  <br/> |
|在 Office App 閒置下列時間之後要求使用者重新登入 (在不需要 PIN 時會停用此設定)  <br/> | 重新檢查存取需求前的剩餘時間 (分鐘)  <br/>  這也會做出下列設定：  <br/> **逾時**設為分鐘  <br/>  這和您在 Microsoft 365 商務版中設定的分鐘數相同。  <br/> **離線寬限期**預設會設定為 720 分鐘  <br/> |
|拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案  <br/> |禁止受管理的應用程式在經過越獄或 Root 的裝置上執行  <br/> |
|允許使用者從 Office App 複製內容到個人 App  <br/> | 限制利用其他應用程式剪下、複製及貼上  <br/>  如果 Microsoft 365 商務版選項設定為 [**開啟**]，然後這三個選項也都會設為在 Intune 中的**所有應用程式**：  <br/> **允許應用程式將資料傳送到其他應用程式** <br/> **[允許應用程式接收其他應用程式的資料]** <br/> **限制利用其他應用程式剪下、複製及貼上** <br/>  如果 Microsoft 365 商務版選項設定為 [**開啟**]，然後所有 Intune 選項都設定為：  <br/> **允許應用程式將傳送至其他應用程式的資料**設定為**受原則管理應用程式** <br/> **允許應用程式接收其他應用程式的資料**設定為 [**所有應用程式** <br/> **Restrict 剪下、 複製及貼上利用其他應用程式**設定為**與貼上的受原則管理應用程式** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Windows 10 App 保護設定

下表詳述 Windows 10 應用程式原則設定對應至 Intune 設定的方式。
  
若要尋找 Intune 設定，而登入您 Microsoft 365 商務版系統管理員認證，移至[Azure 入口網站](https://portal.azure.com)，然後選取**多個服務**，並輸入 Intune，在**篩選**中，選取 [ **Intune 應用程式防護** \> **應用程式原則**。
  
 **重要**： Microsoft 365 商務版訂閱提供您的授權，來修改僅 Intune 設定對應至 Microsoft 365 商務版中可用的設定。 
  
按一下您想要選取的原則名稱，然後選擇**一般]、 [工作分派**、**允許的應用程式**、**去除應用程式**、**所需的設定**，或**進階設定**從左側導覽中探索可用的設定。 
  
|**Windows 10 應用程式原則設定**|**Intune 設定**|
|:-----|:-----|
|加密工作檔案  <br/> |**進階設定** \> **資料保護**：**撤銷的加密金鑰上的取消**和**MDM 註冊之撤銷存取受保護的資料裝置**都設定為**上**。  <br/> |
|防止使用者將公司資料複製到個人檔案。  <br/> |**需要設定** \> **Windows 資訊保護模式**。 **在**Microsoft 365 商務版中對應至：**隱藏會覆寫**，**關閉**Microsoft 365 商務版中對應至：**關閉**。  <br/> |
|Office 文件存取控制  <br/> | 如果這設定為**上**在 Microsoft 365 商務版，然後  <br/> **進階設定** \> **存取**，**使用 Windows Hello 企業版以登入 Windows 的方法**設定為**上**，使用下列其他設定：  <br/> **設定的最小 pin 碼所需的字元數**設為**4**。  <br/> **設定 Windows hello 企業 pin 大寫字母運用**設為 [**不允許使用 pin 的大寫字母**。  <br/> **設定使用 Windows hello 企業 pin 的小寫字母**設為 [**不允許使用 pin 的小寫字母**。  <br/> **設定使用 Windows hello 企業 pin 的特殊字元**設為 [**不允許使用 pin 碼的特殊字元**。  <br/> **指定一段時間 （天） 系統之前，可以使用 pin 碼要求使用者變更**其設定為**0**。  <br/> **指定的可，不能重複使用的使用者帳戶相關聯的過去 pin 碼數目**設為**0**。  <br/> **將 [在抹除裝置之前所允許的驗證失敗的次數**設為相同 Microsoft 365 商務版 (預設值為 5)。  <br/> **最大時間量 （以分鐘為單位） 之後裝置處於閒置狀態，會導致成為 PIN 或密碼鎖定裝置允許**設為相同如 Microsoft 365 商務版所示。  <br/> |
|啟用復原受保護的資料  <br/> |**進階設定** \> **資料保護**：**企業資料保護圖示顯示**] 和 [**針對 WIP 使用 Azure RMS**設定為**On**。  <br/> |
|保護其他公司雲端位置  <br/> |**進階設定** \> **受保護的網域**和**雲端資源**顯示網域和 SharePoint 網站。  <br/> |
|這些 App 使用的檔案已受保護  <br/> |受保護的應用程式的清單會列在**允許的應用程式**。  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Windows 10 裝置保護設定

下表詳述 Windows 10 裝置組態設定對應至 Intune 設定的方式。
  
若要尋找 Intune 設定，而登入您 Microsoft 365 商務版系統管理員認證，移至[Azure 入口網站](https://portal.azure.com)，然後選取**多個服務**，並輸入 Intune，在**篩選**中，選取 [ **Intune** \> **裝置設定** \> **設定檔**。 然後選取 [**適用於 Windows 10 裝置原則** \> **屬性** \> **設定**。
  
|**Windows 10 裝置原則設定**|**Intune 設定**|
|:-----|:-----|
|使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害  <br/> |[允許即時監視] = [開啟]  <br/> [允許雲端保護] = [開啟]  <br/> [提示使用者提交範例] = [自動傳送安全的範例] (預設非 PII 自動提交)  <br/> |
|協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅  <br/> |**Edge 瀏覽器設定**中的 [ **SmartScreen**設為**必要**。  <br/> |
|閒置這段時間之後關閉裝置螢幕 (分鐘)  <br/> |在停止活動最少幾分鐘後鎖定螢幕 (分鐘)  <br/> |
|允許使用者從 Microsoft Store 下載 App  <br/> |自訂 URI 原則  <br/> |
|允許使用者存取 Cortana  <br/> |**一般** \> **Cortana**設為當設為**關閉**Microsoft 365 商務版中的 Intune 中的**區塊**。  <br/> |
|允許使用者接收來自 Microsoft 的 Windows 祕訣和廣告  <br/> |**Windows （聚焦）**，所有 blocked 如果這設定為 [**關閉**Microsoft 365 商務版中。  <br/> |
|自動讓 Windows 10 裝置保持在最新狀態  <br/> | 此設定位於 [ **Microsoft Intune** \> **服務更新-Windows 10 更新通道**，選擇 [U**針對 Windows 10 裝置的 [更新原則]**，然後按一下 [**內容** \> **設定**。  <br/>  當 Microsoft 365 商務版設定設為**上**時，會設定所有的下列設定：  <br/> **服務分支**是設定為 [ **CB** (CBB 這 Microsoft 365 商務版中關閉時)。  <br/> **Microsoft 產品更新**] 設定為**允許**。  <br/> **[Windows 驅動程式**設為**允許**。  <br/> **自動更新行為**設定為使用**自動安裝在維護階段**：  <br/> **小時開始後**設為**上午 6 點**。  <br/> **作用中的時數結束**設為**10 PM**。  <br/> **品質更新延遲期間 （天）** 設為**0**。  <br/> **功能更新延遲期間 （天）** 設為**0**。  <br/> **傳遞最佳化下載模式**設定為**HTTP 混合相同 NAT 後對等**。  <br/> |
|||
   

