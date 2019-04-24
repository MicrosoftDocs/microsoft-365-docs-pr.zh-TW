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
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 了解如何建立的應用程式管理原則，以及保護 Windows 10 裝置上的工作檔案。
ms.openlocfilehash: 289c6a74f6ccb53f6a833612a7b4a5bcddd3ea56
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278155"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>設定 Windows 10 裝置的應用程式保護設定

## <a name="create-an-app-management-policy-for-windows-10"></a>建立適用於 Windows 10 的應用程式管理原則

如果您的使用者擁有個人 Windows 10 裝置並會在其中處理工作的話，您也可以在保護您在這些裝置上的資料。
  
1. 登入[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=837890)使用全域系統管理員認證。 選擇 [移至系統管理中心的 [**管理**] 磚。 
    
2. 在左側導覽中，選擇 [**裝置** \> **原則** \> **新增**。

3. 在 [**新增原則**] 窗格中，輸入此原則的唯一名稱。 
    
4. [**原則類型**] 下選擇 [**用於 Windows 10 應用程式管理**]。
    
5. [* * 裝置類型 * *，選擇 [**個人**] 或 [**公司所擁有**。
    
6. **加密工作檔案**會自動開啟。 
    
7. **防止使用者複製到個人檔案的公司資料並強制他們將工作將檔案儲存到商務用 OneDrive**如果設定為**在**您不想要在其電腦上的工作檔案儲存的使用者。 
    
8. 依序展開 [**管理使用者如何存取裝置上的 Office 檔案**\>設定您想要的設定。 **管理使用者如何存取行動裝置上的 Office 裝置**已**關閉**，根據預設，但建議您將它**開啟**，並接受預設值。 如需詳細資訊，請參閱[可用的設定](#available-settings)。 
    
    您隨時可以使用 [**重設預設設定**] 連結回復到預設設定。 
    
9. 依序展開 [**修復 Windows 裝置上的資料**，並建議，您將它**開啟**。
    
    您必須先建立資料修復代理憑證，才能瀏覽至其位置。如需相關指示，請參閱[建立並驗證加密檔案系統 (EFS) 資料修復代理 (DRA) 憑證](https://go.microsoft.com/fwlink/p/?linkid=853700)。
    
    根據預設，工作檔案加密所使用的祕密金鑰會儲存在裝置中，且與使用者設定檔關聯。只有該使用者可以開啟並解密該檔案。不過，如果裝置遺失或是使用者遭到移除，檔案就會一直停留在加密狀態。系統管理員可以使用資料修復代理程式 (DRA) 憑證來解密該檔案。
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. 如果您想要新增其他網域或 SharePoint Online 的位置，以確保所有列出的應用程式中的檔案會受到保護，請展開 [**保護其他網路及雲端位置**]。 如果您需要為任何欄位輸入多個項目，請在每個項目之間插入分號 (;)。 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. 下一步] 決定**人員會收到這些設定？** 如果您不想要使用預設**的所有使用者**安全性] 群組中，選擇 [**變更**] 中，選擇會收到這些設定的安全性群組\>**選取**。
    
12. 最後，選擇 [**新增]** 以儲存原則，並將它指派到裝置。 
    
## <a name="available-settings"></a>可用的設定

下列設定可用來管理使用者如何存取 Office 工作檔案。
  
如需詳細資訊，請參閱 [Microsoft 365 商務版中的保護功能如何對應 Intune 設定](map-protection-features-to-intune-settings.md)。
  
|**設定**|**描述**|
|:-----|:-----|
|需要 PIN 或指紋才能存取 Office App  <br/> |如果此設定是**在**使用者必須提供另一種形式的驗證，除了使用者名稱和密碼，才能在其行動裝置上使用 Office 應用程式。  <br/> |
|在登入失敗達下列次數時重設 PIN  <br/> |為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。  <br/> |
|在 Office App 閒置下列時間之後要求使用者重新登入  <br/> |此設定決定閒置多久之後，系統會提示使用者重新登入。  <br/> |
   

