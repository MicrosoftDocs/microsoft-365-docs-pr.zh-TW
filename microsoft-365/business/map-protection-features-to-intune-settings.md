---
title: Microsoft 365 商務進階版如何對應至 Intune 設定中的保護功能
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: 瞭解 Microsoft 365 商務進階版如何對應至 Intune 設定中的保護功能。 訂閱提供您的授權，可修改 Intune 設定。
ms.openlocfilehash: 9a6dcf014e009389e49860fa96486c264c22f501
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580107"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>Microsoft 365 商務進階版如何對應至 Intune 設定中的保護功能

## <a name="android-and-ios-application-protection-settings"></a>Android 和 iOS 應用程式保護設定

下表詳述 Android 和 iOS 應用程式原則設定對應至 Intune 設定的方式。
  
若要尋找 Intune 設定，請使用您的 Microsoft 365 商務進階版系統管理員認證登入，然後 **移至 [系統管理中心]** 和 [ **intune**]。
  
 > [!IMPORTANT]
 > 
 > Microsoft 365 商務進階版訂閱可讓您修改所有 Intune 設定的授權。 請參閱 [Intune 簡介開始吧。](/intune/introduction-intune)
  
選取您想要的原則名稱 &mdash; （例如，適用于 Android 的應用程式原則）， &mdash; 然後選擇 [ **原則設定**]。
  
低於在 **裝置遺失或遭竊時保護工作檔**
  
|**Android 或 iOS 應用程式原則設定**|**Intune 設定**|
|:-----|:-----|
|在下列時間之後刪除非作用中裝置上的工作檔案  <br/> |將應用程式資料抹除前的離線間隔 (天)  <br/> |
|強制使用者將工作檔案儲存到商務用 OneDrive  <br/> 請注意，僅允許商務用 OneDrive  <br/> |選取可儲存公司資料的儲存體服務  <br/> |
|||
   
在 [**管理行動裝置中使用者存取 Office 檔案的方式**
  
|**Android 或 iOS 應用程式原則設定**|**Intune 設定**|
|:-----|:-----|
|在下列時間之後刪除非作用中裝置上的工作檔案  <br/> |將應用程式資料抹除前的離線間隔 (天)  <br/> |
|強制使用者將工作檔案儲存到商務用 OneDrive  <br/> 請注意，僅允許商務用 OneDrive  <br/> |選取可儲存公司資料的儲存體服務  <br/> |
|加密工作檔案  <br/> |加密應用程式資料  <br/> |
|在 [**管理行動裝置中使用者存取 Office 檔案的方式** <br/> ||
|需要 PIN 或指紋才能存取 Office App  <br/> | 需要 PIN 才能存取  <br/>  這也會做出下列設定：  <br/> **允許簡易 PIN** 為 **[是]** <br/> **Pin 碼長度** 為4  <br/> **允許指紋，而不是 PIN 碼** 到 **是** <br/> **裝置 PIN 碼未管理時停用應用程式 PIN 碼**  <br/> |
|當登入失敗時，重設 PIN 碼 (此動作會停用（如果不需要 PIN）)   <br/> |PIN 重設之前的嘗試次數  <br/> |
|在 Office 應用程式閒置時，需要使用者重新登入 (如果不需要 PIN 碼會停用此功能)   <br/> | 重新檢查存取需求前的剩餘時間 (分鐘)  <br/>  這也會做出下列設定：  <br/> **超時** 設定為分鐘  <br/>  這和您在 Microsoft 365 商務版中設定的分鐘數相同。  <br/> **離線寬限期** 預設設定為720分鐘  <br/> |
|拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案  <br/> |禁止受管理的應用程式在經過越獄或 Root 的裝置上執行  <br/> |
|允許使用者從 Office App 複製內容到個人 App  <br/> | 限制利用其他應用程式剪下、複製及貼上  <br/>  如果 Microsoft 365 商務進階版選項設定為 [**開啟**]，則這三個選項也會設定為 Intune 中的 **所有應用程式**：  <br/> **允許應用程式將資料傳送到其他應用程式** <br/> **[允許應用程式接收其他應用程式的資料]** <br/> **限制利用其他應用程式剪下、複製及貼上** <br/>  如果 Microsoft 365 商務版選項設定為 [**開啟**]，則所有的 Intune 選項會設定為：  <br/> **允許應用程式將資料傳送至其他應用** 程式設定為 **受原則管理的應用程式** <br/> [**允許應用程式接收來自其他應用** 程式的資料] 設定為 [**所有應用** 程式] <br/> **限制與其他應用程式的剪下、複製及貼** 上，設定為 **具有貼上的原則管理應用程式** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Windows 10 App 保護設定

下表詳述 Windows 10 應用程式原則設定對應至 Intune 設定的方式。
  
若要尋找 Intune 設定，請使用您的 Microsoft 365 商務進階版系統管理員認證登入，然後移至[Azure 入口網站](https://portal.azure.com)。 選取 [ **更多服務**]，然後在 **篩選器** 中輸入 Intune。 選取 [ **Intune 應用程式保護** \> **應用程式原則**]。
  
 > [!IMPORTANT]
 >
 >Microsoft 365 商務進階版訂閱可讓您只修改對應至 Microsoft 365 商務進階版中可用設定的 Intune 設定。 
  
若要探索可用的設定，請選取您想要的原則名稱，然後選擇左側流覽窗格中的 **[一般]、[工作分派**]、[ **允許的應用程式**、 **免除應用程式**、 **必要設定** 或 **高級設定** ]。 
  
|**Windows 10 應用程式原則設定**|**Intune 設定**|
|:-----|:-----|
|加密工作檔案  <br/> |**高級設定** \>**資料保護**：**在取消註冊時撤銷加密金鑰**，並 **撤銷對 MDM 註冊的受保護資料裝置的存取**，都是設定為 [**開啟**]。  <br/> |
|防止使用者將公司資料複製到個人檔案。  <br/> |**必要設定** \>**Windows 資訊保護模式**。 **在 Microsoft 365 商務進階版** 會對應至：**隱藏覆寫**，**關閉** 于 Microsoft 365 商務進階版地圖 to： **Off**。  <br/> |
|Office 文件存取控制  <br/> | 如果這是在 Microsoft 365 商務進階版中設定為 [**開啟**]，則  <br/> **高級設定** \>**Access**，**使用 Windows Hello for Business 做為登入 Windows 的方法**，則會設定為 [**開啟**]，具有下列其他設定：  <br/> **設定 PIN 碼所需的最小字元數** 設定為 **4**。  <br/> **在 [Windows Hello 企業版 PIN] 中設定大寫字母的使用**，**不允許使用大寫字母做為 PIN 碼**。  <br/> **在 [Windows Hello 企業版 PIN] 中設定小寫字母的使用**，以 **不允許使用小寫字母進行 PIN 碼**。  <br/> **在 [Windows Hello 企業版 PIN] 中設定特殊字元的使用**，**不允許在 PIN 碼中使用特殊字元**。  <br/> **指定在系統要求使用者變更之前可使用 PIN 碼的時段 (天數)** 設定為 **0**。  <br/> **指定可以與無法重複使用之使用者帳戶相關聯的過去 pin 碼數目** 設定為 **0**。  <br/> 在 **擦除裝置之前所允許的驗證失敗次數**，設定為與 Microsoft 365 商務版 (預設) 相同。  <br/> 在 **裝置閒置時，可讓裝置變成 PIN 碼或已鎖定密碼的最長 (時間)** 會設定為與 Microsoft 365 商務版中的相同。  <br/> |
|啟用復原受保護的資料  <br/> |**高級設定** \>**資料保護**：**顯示企業資料保護圖示**，並 **使用 Azure RMS for WIP** 已設定為 [**開啟**]。  <br/> |
|保護其他公司雲端位置  <br/> |**高級設定** \>**受保護的網域** 和 **雲端資源** 顯示網域和 SharePoint 網站。  <br/> |
|這些 App 使用的檔案已受保護  <br/> |受保護應用程式的清單會列在 **允許的應用程式** 中。  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Windows 10 裝置保護設定

下表詳述 Windows 10 裝置組態設定對應至 Intune 設定的方式。
  
若要尋找 Intune 設定，請使用您的 Microsoft 365 商務進階版系統管理員認證登入，並移至 [Azure 入口網站](https://portal.azure.com)，然後選取 [**其他服務**]，然後在 [intune] 中輸入 **篩選器**，選取 [ **intune** \> **裝置** 設定 \> **設定檔**]。 然後選取 [Windows 10 屬性]**的 [裝置原則**] \>  \> **設定**。
  
|**Windows 10 裝置原則設定**|**Intune 設定**|
|:-----|:-----|
|使用 Windows Defender 防毒軟體來協助保護電腦免於遭受病毒與其他威脅的侵害  <br/> |[允許即時監視] = [開啟]  <br/> [允許雲端保護] = [開啟]  <br/> [提示使用者提交範例] = [自動傳送安全的範例] (預設非 PII 自動提交)  <br/> |
|協助保護電腦免於遭受 Microsoft Edge 中的網路安全威脅  <br/> |在 **Edge Browser** 設定中 **SmartScreen** 設定為 [**必要**]。  <br/> |
|閒置這段時間之後關閉裝置螢幕 (分鐘)  <br/> |在停止活動最少幾分鐘後鎖定螢幕 (分鐘)  <br/> |
|允許使用者從 Microsoft Store 下載 App  <br/> |自訂 URI 原則  <br/> |
|允許使用者存取 Cortana  <br/> |**一般** \>在 Microsoft 365 商務進階版中設定為 **off** 時， **Cortana** 會設定為在 Intune 中 **封鎖**。  <br/> |
|允許使用者接收來自 Microsoft 的 Windows 祕訣和廣告  <br/> |**Windows 聚光燈**，如果在 Microsoft 365 商務進階版中將其設為 **off** ，便會封鎖。  <br/> |
|自動讓 Windows 10 裝置保持在最新狀態  <br/> | 此設定是在 **Microsoft Intune** \> **服務更新-Windows 10 更新環** 中，選擇 [ **Windows 10 裝置的更新原則**]，然後按一下 [**屬性**] \> **設定**。  <br/>  當 [Microsoft 365 商務進階版] 設定設為 [**開啟**] 時，會設定下列所有設定：  <br/> 當 Microsoft 365 商務進階版) 中關閉此功能時，**服務分支** 會設定為 **CB** (CBB。  <br/> **Microsoft 產品更新** 已設定為 [ **允許**]。  <br/> **Windows 驅動程式** 設定為 [**允許**]。  <br/> **自動更新行為** 會設定為 **在維護時間和下列專案中自動安裝** ：  <br/> **當時段開始時間** 設定為 **6 AM**。  <br/> 使用 **時段結束** 設定為 **10 PM**。  <br/> **品質更新延期期間 (天數)** 設定為 **0**。  <br/> **功能更新延期期間 (天數)** 設定為 **0**。  <br/> **傳遞優化下載模式** 是設定為 **使用相同 NAT 的對等的 HTTP 混合**。  <br/> |
|||
