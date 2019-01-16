---
title: 設定 Windows 10 裝置的應用程式保護設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 了解如何建立的應用程式管理原則及保護工時 Windows 10 裝置上的檔案。
ms.openlocfilehash: acf19a72d994185a35b2e425f8334a73a121ee10
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866321"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>設定 Windows 10 裝置的應用程式保護設定

## <a name="create-an-app-management-policy-for-windows-10"></a>建立適用於 Windows 10 的應用程式管理原則

如果您的使用者擁有個人 Windows 10 裝置並會在其中處理工作的話，您也可以在保護您在這些裝置上的資料。
  
1. 以全域管理員認證登入[Microsoft 365 Business](https://portal.office.com) 。選擇 [移至系統管理中心的 [**管理**] 磚。 
    
2. 在系統入口網站的**裝置原則**卡片、 上選擇 [**新增原則**]。
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. 在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。 
    
4. 在**原則類型**] 下選擇 [ **for Windows 10 應用程式管理**]。
    
5. [* * 裝置類型 * *，選擇 [**個人**] 或 [**公司擁有**。
    
6. **加密工作檔案**會自動開啟。 
    
7. **防止使用者將複製的個人檔案的公司資料與強制其儲存至 OneDrive for Business 的工時檔案**如果設定為**在**您不想將儲存在其電腦上的工作檔案的使用者。 
    
8. 依序展開 [**管理使用者如何存取裝置上的 Office 檔案**\>您想方式進行設定。**管理使用者如何存取行動裝置上的 Office 裝置**預設為**關閉，** 但建議您**加以開啟**並接受預設值。如需詳細資訊，請參閱[可用的設定](protection-settings-for-windows-10-devices.md#bkmk_settings)。 
    
    您一律可以回復成預設值使用**預設設定重設**] 連結。 
    
9. 依序展開 [ **Windows 裝置上的資料復原**和它建議**您開啟它**。
    
    您必須先建立資料修復代理憑證，才能瀏覽至其位置。如需相關指示，請參閱[建立並驗證加密檔案系統 (EFS) 資料修復代理 (DRA) 憑證](https://go.microsoft.com/fwlink/p/?linkid=853700)。
    
    根據預設，工作檔案加密所使用的祕密金鑰會儲存在裝置中，且與使用者設定檔關聯。只有該使用者可以開啟並解密該檔案。不過，如果裝置遺失或是使用者遭到移除，檔案就會一直停留在加密狀態。系統管理員可以使用資料修復代理程式 (DRA) 憑證來解密該檔案。
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. 如果您想要新增其他網域或以確定在所有列出的應用程式中的檔案將會受到保護的 SharePoint Online 位置，展開**Protect 其他網路和雲端位置**。如果您需要為其中一個欄位中輸入一個以上的項目，請使用分號 （;） 之間的項目。 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. 接下來決定**誰將會得到這些設定？** 如果您不想要使用預設**的所有使用者**安全性] 群組中，選擇 [**變更**，並選擇 [將會得到這些設定的安全性群組\>**選取**。
    
12. 最後，選擇 [**新增]** 以儲存原則，並將其指派給裝置。 
    
## <a name="available-settings"></a>可用的設定

下列設定可用來管理使用者如何存取 Office 工作檔案。
  
如需詳細資訊，請參閱 [Microsoft 365 商務版中的保護功能如何對應 Intune 設定](map-protection-features-to-intune-settings.md)。
  
|**設定**|**描述**|
|:-----|:-----|
|需要 PIN 或指紋才能存取 Office App  <br/> |如果此設定是**在**使用者必須提供另一份表單的驗證，以及其使用者名稱和密碼，才能在使用者的行動裝置上使用 Office 應用程式。  <br/> |
|在登入失敗達下列次數時重設 PIN  <br/> |為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。  <br/> |
|在 Office App 閒置下列時間之後要求使用者重新登入  <br/> |此設定決定閒置多久之後，系統會提示使用者重新登入。  <br/> |
   

