---
title: 管理使用者如何在行動裝置上存取 Office 文件
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
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
description: 深入了解可協助 Office 相關應用程式的安全存取從行動裝置的保護原則。
ms.openlocfilehash: 75dbe79acccabd851c43259a165e79bfe3c509c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866434"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>管理使用者如何在行動裝置上存取 Office 文件

 控制使用者如何存取 Office 檔案從其行動裝置的原則設定預設為**關閉**的。我們建議您接受 android （英文）、 iOS，以及 Windows 10 建立應用程式原則在安裝期間套用至所有使用者的預設值。您可以在安裝程式完成後建立多個原則。 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>控制使用者如何透過行動裝置存取 Office 檔案的設定

下列設定可用來管理使用者如何存取 Office 工作檔案：
  
|||
|:-----|:-----|
|設定  <br/> |描述  <br/> |
|需要 PIN 或指紋才能存取 Office App  <br/> |如果此設定是**在**使用者必須提供另一份表單的驗證，以及其使用者名稱和密碼，才能在使用者的行動裝置上使用 Office 應用程式。  <br/> |
|在登入失敗達下列次數時重設 PIN  <br/> |為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。  <br/> |
|在 Office App 閒置下列時間之後要求使用者重新登入  <br/> |此設定決定了閒置多久之後，系統會提示使用者重新登入。  <br/> |
|拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案  <br/> |聰明使用者可能會有 jailbroken 或根目錄的裝置。這表示使用者可以修改作業系統，可讓裝置多受限於惡意程式碼。**在**此設定時封鎖這些裝置。<br/> |
|允許使用者從 Office App 複製內容到個人 App  <br/> |我們根據預設，允許這但**上**設定時，使用者可以複製資訊工時檔案中為個人的檔案。如果設定為**關閉**，使用者無法將複製資訊從工作檔案個人應用程式或個人帳戶。<br/> |
   

