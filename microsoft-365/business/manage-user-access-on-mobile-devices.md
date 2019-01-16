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
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866434"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="7e672-103">管理使用者如何在行動裝置上存取 Office 文件</span><span class="sxs-lookup"><span data-stu-id="7e672-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="7e672-p101">控制使用者如何存取 Office 檔案從其行動裝置的原則設定預設為**關閉**的。我們建議您接受 android （英文）、 iOS，以及 Windows 10 建立應用程式原則在安裝期間套用至所有使用者的預設值。您可以在安裝程式完成後建立多個原則。</span><span class="sxs-lookup"><span data-stu-id="7e672-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="7e672-107">控制使用者如何透過行動裝置存取 Office 檔案的設定</span><span class="sxs-lookup"><span data-stu-id="7e672-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="7e672-108">下列設定可用來管理使用者如何存取 Office 工作檔案：</span><span class="sxs-lookup"><span data-stu-id="7e672-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7e672-109">設定</span><span class="sxs-lookup"><span data-stu-id="7e672-109">Setting</span></span>  <br/> |<span data-ttu-id="7e672-110">描述</span><span class="sxs-lookup"><span data-stu-id="7e672-110">Description</span></span>  <br/> |
|<span data-ttu-id="7e672-111">需要 PIN 或指紋才能存取 Office App</span><span class="sxs-lookup"><span data-stu-id="7e672-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="7e672-112">如果此設定是**在**使用者必須提供另一份表單的驗證，以及其使用者名稱和密碼，才能在使用者的行動裝置上使用 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7e672-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="7e672-113">在登入失敗達下列次數時重設 PIN</span><span class="sxs-lookup"><span data-stu-id="7e672-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="7e672-114">為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。</span><span class="sxs-lookup"><span data-stu-id="7e672-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="7e672-115">在 Office App 閒置下列時間之後要求使用者重新登入</span><span class="sxs-lookup"><span data-stu-id="7e672-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="7e672-116">此設定決定了閒置多久之後，系統會提示使用者重新登入。</span><span class="sxs-lookup"><span data-stu-id="7e672-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="7e672-117">拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案</span><span class="sxs-lookup"><span data-stu-id="7e672-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="7e672-p102">聰明使用者可能會有 jailbroken 或根目錄的裝置。這表示使用者可以修改作業系統，可讓裝置多受限於惡意程式碼。**在**此設定時封鎖這些裝置。</span><span class="sxs-lookup"><span data-stu-id="7e672-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="7e672-121">允許使用者從 Office App 複製內容到個人 App</span><span class="sxs-lookup"><span data-stu-id="7e672-121">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="7e672-p103">我們根據預設，允許這但**上**設定時，使用者可以複製資訊工時檔案中為個人的檔案。如果設定為**關閉**，使用者無法將複製資訊從工作檔案個人應用程式或個人帳戶。</span><span class="sxs-lookup"><span data-stu-id="7e672-p103">We allow this by default, but when the setting is **On**, the user can copy information in a work file to a personal file. If the setting is **Off**, the user can't copy information from a work file to a personal app or personal account.  </span></span><br/> |
   

