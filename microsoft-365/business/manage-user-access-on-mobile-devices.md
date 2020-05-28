---
title: 管理使用者如何在行動裝置上存取 Office 文件
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 深入瞭解保護原則，可讓您管理使用者從行動裝置存取 Office 應用程式和工作檔的方式。
ms.openlocfilehash: f613e518c3607010cae55443456be9d3ddc3d689
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403071"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>管理使用者如何在行動裝置上存取 Office 文件

 控制使用者從行動裝置存取 Office 檔案的原則設定預設為**關閉**。 建議您在設定時接受預設值，以建立適用于所有使用者的 Android、iOS 和 Windows 10 應用程式原則。 設定完成後，您可以建立更多原則。 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>控制使用者如何透過行動裝置存取 Office 檔案的設定

下列設定可用來管理使用者如何存取 Office 工作檔案：
  
|||
|:-----|:-----|
|設定  <br/> |說明  <br/> |
|需要 PIN 或指紋才能存取 Office App  <br/> |若此設定為 [**開啟**]，除了使用者的使用者名稱和密碼以外，使用者還必須提供另一種形式的驗證，才能在其行動裝置上使用 Office 應用程式。  <br/> |
|在登入失敗達下列次數時重設 PIN  <br/> |為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。  <br/> |
|在 Office App 閒置下列時間之後要求使用者重新登入  <br/> |此設定會決定使用者在有多久之後才會收到重新登入的時間。  <br/> |
|拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案  <br/> |聰明的使用者可能擁有已進行 JB 或 Root 破解的裝置。 這表示使用者可以修改作業系統，這可讓裝置更容易遭到惡意程式碼攻擊。 當此設定為 [**開啟**] 時，即會封鎖這些裝置。  <br/> |
|不允許使用者從 Office 應用程式複製內容到個人應用程式  <br/> |當設定為 [**開啟**] 時，使用者無法將工作檔案中的資訊複製到個人檔案。 如果設定為 [**關閉**]，使用者可以將工作檔案中的資訊複製到個人 app 或個人帳戶。  <br/> |
   

