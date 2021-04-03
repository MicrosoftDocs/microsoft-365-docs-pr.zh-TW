---
title: 管理使用者如何在行動裝置上存取 Office 文件
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
ms.openlocfilehash: a48aa241c9e70cf087da3f1701e859dae7238024
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578380"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="53f8c-103">管理使用者如何在行動裝置上存取 Office 文件</span><span class="sxs-lookup"><span data-stu-id="53f8c-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="53f8c-104">本文適用于 Microsoft 365 商務版 Premium。</span><span class="sxs-lookup"><span data-stu-id="53f8c-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="53f8c-105">控制使用者從行動裝置存取 Office 檔案的原則設定預設為 **關閉** 。</span><span class="sxs-lookup"><span data-stu-id="53f8c-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="53f8c-106">建議您在設定時接受預設值，以建立適用于所有使用者的 Android、iOS 和 Windows 10 應用程式原則。</span><span class="sxs-lookup"><span data-stu-id="53f8c-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="53f8c-107">設定完成後，您可以建立更多原則。</span><span class="sxs-lookup"><span data-stu-id="53f8c-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="53f8c-108">控制使用者如何透過行動裝置存取 Office 檔案的設定</span><span class="sxs-lookup"><span data-stu-id="53f8c-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="53f8c-109">下列設定可用來管理使用者如何存取 Office 工作檔案：</span><span class="sxs-lookup"><span data-stu-id="53f8c-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="53f8c-110">設定</span><span class="sxs-lookup"><span data-stu-id="53f8c-110">Setting</span></span>  <br/> |<span data-ttu-id="53f8c-111">說明</span><span class="sxs-lookup"><span data-stu-id="53f8c-111">Description</span></span>  <br/> |
|<span data-ttu-id="53f8c-112">需要 PIN 或指紋才能存取 Office App</span><span class="sxs-lookup"><span data-stu-id="53f8c-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="53f8c-113">若此設定為 [ **開啟**]，除了使用者的使用者名稱和密碼以外，使用者還必須提供另一種形式的驗證，才能在其行動裝置上使用 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="53f8c-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="53f8c-114">在登入失敗達下列次數時重設 PIN</span><span class="sxs-lookup"><span data-stu-id="53f8c-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="53f8c-115">為了避免未經授權的使用者隨機猜測 PIN，當達到您指定的輸入錯誤次數時將會重設 PIN。</span><span class="sxs-lookup"><span data-stu-id="53f8c-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="53f8c-116">在 Office App 閒置下列時間之後要求使用者重新登入</span><span class="sxs-lookup"><span data-stu-id="53f8c-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="53f8c-117">此設定會決定使用者在有多久之後才會收到重新登入的時間。</span><span class="sxs-lookup"><span data-stu-id="53f8c-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="53f8c-118">拒絕在已進行 JB 或 Root 破解的裝置上存取工作檔案</span><span class="sxs-lookup"><span data-stu-id="53f8c-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="53f8c-119">聰明的使用者可能擁有已進行 JB 或 Root 破解的裝置。</span><span class="sxs-lookup"><span data-stu-id="53f8c-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="53f8c-120">這表示使用者可以修改作業系統，這可讓裝置更容易遭到惡意程式碼攻擊。</span><span class="sxs-lookup"><span data-stu-id="53f8c-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="53f8c-121">當此設定為 [ **開啟**] 時，即會封鎖這些裝置。</span><span class="sxs-lookup"><span data-stu-id="53f8c-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="53f8c-122">不允許使用者從 Office 應用程式複製內容到個人應用程式</span><span class="sxs-lookup"><span data-stu-id="53f8c-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="53f8c-123">當設定為 [ **開啟**] 時，使用者無法將工作檔案中的資訊複製到個人檔案。</span><span class="sxs-lookup"><span data-stu-id="53f8c-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="53f8c-124">如果設定為 [ **關閉**]，使用者可以將工作檔案中的資訊複製到個人 app 或個人帳戶。</span><span class="sxs-lookup"><span data-stu-id="53f8c-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

