---
title: Microsoft 365 商務版中的保護功能如何對應 Intune 設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 8/13/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: 了解 Microsoft 365 Business 中的保護功能如何對應至 Intune 設定。訂閱提供您修改 Intune 設定授權。
ms.openlocfilehash: 5ee5a457fe3f265dd37f6806ca8c11fe096718b6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866389"
---
# <a name="how-do-protection-features-in-microsoft-365-business-map-to-intune-settings"></a>Microsoft 365 商務版中的保護功能如何對應 Intune 設定

## <a name="android-and-ios-application-protection-settings"></a>Android 和 iOS 應用程式保護設定

下表詳述 Android 和 iOS 應用程式原則設定對應至 Intune 設定的方式。
  
若要尋找 [Intune] 設定使用 Microsoft 365 商務系統管理認證登入，移至**系統中心**，然後**Intune**。
  
 **重要：** Microsoft 365 Business 訂閱提供授權修改 Intune 的所有設定。請參閱[開始 Intune 的簡介。](https://docs.microsoft.com/intune/introduction-intune)
  
按一下您想要選取，例如 for Android、 應用程式原則原則名稱，然後選擇 [**原則設定**。
  
[**保護工作檔案遺失或竊裝置的時機**
  
|**Android 或 iOS 應用程式原則設定**|**Intune 設定**|
|:-----|:-----|
|在下列時間之後刪除非作用中裝置上的工作檔案  <br/> |將應用程式資料抹除前的離線間隔 (天)  <br/> |
|強制使用者將工作檔案儲存到商務用 OneDrive  <br/> 請注意，僅允許商務用 OneDrive  <br/> |選取可儲存公司資料的儲存體服務  <br/> |
|||
   
[**管理使用者如何存取行動裝置中的 Office 檔案**
  
|**Android 或 iOS 應用程式原則設定**|**Intune 設定**|
|:-----|:-----|
|在下列時間之後刪除非作用中裝置上的工作檔案  <br/> |將應用程式資料抹除前的離線間隔 (天)  <br/> |
|強制使用者將工作檔案儲存到商務用 OneDrive  <br/> 請注意，僅允許商務用 OneDrive  <br/> |選取可儲存公司資料的儲存體服務  <br/> |
|加密工作檔案  <br/> |加密應用程式資料  <br/> |
|[**管理使用者如何存取行動裝置中的 Office 檔案** <br/> ||
|需要 PIN 或指紋才能存取 Office App  <br/> | 需要 PIN 才能存取  <br/>  這也會做出下列設定：  <br/> 為 [**是]** **允許簡單 PIN** <br/> **Pin 長度**為 4  <br/> 為 [**是]** **允許指紋，而不是 PIN** <br/> 用以**否]** 的 [**停用應用程式時受管理的裝置 PIN 的 PIN** <br/> |
|在登入失敗達下列次數時重設 PIN (在不需要 PIN 時會停用此設定)  <br/> |重設 PIN 前的嘗試次數  <br/> |
|在 Office App 閒置下列時間之後要求使用者重新登入 (在不需要 PIN 時會停用此設定)  <br/> | 重新檢查存取需求前的剩餘時間 (分鐘)  <br/>  這也會做出下列設定：  <br/> **逾時**設為分鐘  <br/>  這和您在 Microsoft 365 商務版中設定的分鐘數相同。  <br/> **離線寬限期**設為 720 分鐘預設  <br/> |
|拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案  <br/> |禁止受管理的應用程式在經過越獄或 Root 的裝置上執行  <br/> |
|允許使用者從 Office App 複製內容到個人 App  <br/> | 限制利用其他應用程式剪下、複製及貼上  <br/>  如果 Microsoft 365 商務] 選項設定為**在**然後這三個選項也都會設為 Intune 中的**所有應用程式**：  <br/> **[允許應用程式將資料傳送至其他應用程式]** <br/> **[允許應用程式接收其他應用程式的資料]** <br/> **[限制利用其他應用程式剪下、複製及貼上]** <br/>  如果 Microsoft 365 商務] 選項設定為**在**則所有 Intune 選項是會都設為：  <br/> **允許應用程式傳送資料至其他應用程式**設定為**受管理應用程式的原則** <br/> **允許應用程式以接收來自其他應用程式的資料**設定為 [**所有應用程式** <br/> **Restrict 剪下、 複製及貼上與其他應用程式**設定為**受管理的原則與貼上中的應用程式** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Windows 10 App 保護設定

下表詳述 Windows 10 應用程式原則設定對應至 Intune 設定的方式。
  
若要尋找 Intune 設定] 中，使用 Microsoft 365 商務系統管理認證，登入移至[Azure 入口網站](https://portal.azure.com)，然後選取**多個服務**，然後輸入 Intune 將**篩選器**中的選取 [ **Intune 應用程式保護** \> **應用程式原則**。
  
 **重要**： Microsoft 365 Business 訂閱提供您修改 Intune 設定授權的對應至 Microsoft 365 Business 中可用的設定。 
  
按一下您想要選取，該原則名稱，然後選擇從左側的巡覽來探索可用的設定的 [****一般]、 [工作分派**、 允許應用程式**、**去除應用程式**、**所需的設定**，或**進階設定**。 
  
|**Windows 10 應用程式原則設定**|**Intune 設定**|
|:-----|:-----|
|加密工作檔案  <br/> |**進階設定**\> **資料保護**：**撤銷的加密上的按鍵 unenroll**和**Revoke 存取受保護的資料裝置註冊至 MDM**皆被設為**上**。  <br/> |
|防止使用者將公司資料複製到個人的檔案。  <br/> |**所需的設定**\> **Windows 資訊保護模式**。**在**Microsoft 365 Business 中對應至：**隱藏會覆寫**，**關閉**Microsoft 365 Business 中對應至：**關閉**。<br/> |
|Office 文件存取控制  <br/> | 如果這然後設為**上**的 Microsoft 365 Business、  <br/> **進階設定**\> **存取**、**使用 Windows Hello for Business 做為登入 Windows 的方法**設為**上**具有下列其他設定：  <br/> **設定 PIN 的所需的字元數下限**設為**4**。  <br/> **設定使用中 Windows Hello 商務 PIN 的大寫字母**設為**不允許使用 PIN 的大寫字母**。  <br/> **設定使用中 Windows Hello 商務 PIN 的小寫字母**設為**不允許使用 PIN 的小寫字母**。  <br/> **設定使用的特殊字元的 Windows Hello for Business PIN**設為**不允許使用的特殊字元的 PIN**。  <br/> **指定的時間 （以天數） PIN 可用系統前要求使用者變更**其設定為**0**。  <br/> **指定的可，不能重複使用的使用者帳戶相關聯的過去 Pin 數目**設為**0**。  <br/> **會清除裝置之前所允許的驗證失敗的次數**設為相同相同 Microsoft 365 商務 (預設為 5)。  <br/> **最大時間量 （以分鐘為單位） 之後裝置處於閒置狀態之會導致成為 PIN 或鎖定的密碼裝置允許**相同 Microsoft 365 商務設為相同。  <br/> |
|啟用復原受保護的資料  <br/> |**進階設定**\> **資料保護**：**企業資料保護圖示顯示**和**使用 Azure RMS 的 WIP**設定**上**。  <br/> |
|保護其他公司雲端位置  <br/> |**進階設定**\> **保護網域**與**雲端資源**顯示網域與 SharePoint 網站。  <br/> |
|這些 App 使用的檔案已受保護  <br/> |受保護的應用程式的清單會列在**允許應用程式**。  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Windows 10 裝置保護設定

下表詳述 Windows 10 裝置組態設定對應至 Intune 設定的方式。
  
若要尋找 Intune 設定] 中，使用 Microsoft 365 商務系統管理認證，登入移至[Azure 入口網站](https://portal.azure.com)，請選取**多個服務**，然後輸入 Intune 將**篩選器**中的選取**Intune** \> **裝置設定** \> **設定檔**。然後選取 [ **Windows 10 的裝置原則** \> **屬性** \> **設定**。
  
|**Windows 10 裝置原則設定**|**Intune 設定**|
|:-----|:-----|
|使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害  <br/> |[允許即時監視] = [開啟]  <br/> [允許雲端保護] = [開啟]  <br/> [提示使用者提交範例] = [自動傳送安全的範例] (預設非 PII 自動提交)  <br/> |
|協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅  <br/> |**SmartScreen** **Edge 瀏覽器設定**] 中會設為**所需**。  <br/> |
|閒置這段時間之後關閉裝置螢幕 (分鐘)  <br/> |在停止活動最少幾分鐘後鎖定螢幕 (分鐘)  <br/> |
|允許使用者從 Microsoft Store 下載 App  <br/> |自訂 URI 原則  <br/> |
|允許使用者存取 Cortana  <br/> |**一般**\> **Cortana**設為**block**中 Intune 設為**關閉**Microsoft 365 Business 中時。  <br/> |
|允許使用者接收來自 Microsoft 的 Windows 祕訣和廣告  <br/> |**Windows （聚焦）**，如果這設為**關閉**Microsoft 365 Business 中遭到封鎖所有。  <br/> |
|自動讓 Windows 10 裝置保持在最新狀態  <br/> | 此設定位於**Microsoft Intune** \> **服務更新-Windows 10 更新鈴響**、 選擇 [U **Windows 10 裝置更新原則**]，然後按一下 [**內容** \> **設定**。  <br/>  當 [Microsoft 365 商務] 設定設為**上**時，下列設定值的所有設定：  <br/> **服務分支**設為**CB** (CBB 時這關閉 Microsoft 365 Business)。  <br/> **Microsoft 產品更新**已設為 [**允許**。  <br/> **Windows 驅動程式**會設定為**允許**。  <br/> **自動更新行為**設定為使用中 [**自動安裝在維護時間**：  <br/> **之後開始時間**設為**6 AM**。  <br/> **作用中的小時結束**設為**10 PM**。  <br/> **品質更新延期期間 （天）** 設為**0**。  <br/> **功能更新延期期間 （天）** 設為**0**。  <br/> **傳遞最佳化下載模式**設定為**與對等相同的 NAT 後方混合 HTTP**。  <br/> |
|||
   

