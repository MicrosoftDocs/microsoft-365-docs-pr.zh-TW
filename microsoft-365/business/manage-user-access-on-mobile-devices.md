---
title: 管理使用者如何在行動裝置上存取 Office 文件
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 了解保護原則，可協助 Office 應用程式的安全存取從行動裝置。
ms.openlocfilehash: b77d30686b26f95de684238d1b9afd57550a7c7f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278602"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>管理使用者如何在行動裝置上存取 Office 文件

 控制使用者如何透過行動裝置存取 Office 檔案的原則設定預設為**關閉**。 建議您在設定時接受預設值，以建立適用於所有使用者的 Android、iOS 和 Windows 10 應用程式原則。 設定完成後，您可以建立更多原則。 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>控制使用者如何透過行動裝置存取 Office 檔案的設定

下列設定可用來管理使用者如何存取 Office 工作檔案：
  
|||
|:-----|:-----|
|設定  <br/> |描述  <br/> |
|需要 PIN 或指紋才能存取 Office App  <br/> |如果此設定是**在**使用者必須提供另一種形式的驗證，除了使用者名稱和密碼，才能在其行動裝置上使用 Office 應用程式。  <br/> |
|在登入失敗達下列次數時重設 PIN  <br/> |為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。  <br/> |
|在 Office App 閒置下列時間之後要求使用者重新登入  <br/> |此設定決定閒置多久之後，系統會提示使用者重新登入。  <br/> |
|拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案  <br/> |聰明的使用者可能擁有已進行 JB 或 Root 破解的裝置。 這表示使用者能夠修改作業系統，這可能導致裝置較容易遭到惡意程式碼的攻擊。 **此設定時**，會封鎖這些裝置。  <br/> |
|允許使用者從 Office App 複製內容到個人 App  <br/> |我們預設允許此行為，但**在**設定時，使用者可以複製資訊工作檔案中的個人檔案。 如果設定為**關閉**，使用者不能複製資訊工作檔案到個人 app 或個人帳戶。  <br/> |
   

