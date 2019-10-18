---
title: 關於 AutoPilot 設定檔的設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 設定檔可協助您控制如何取得使用者裝置上安裝 Windows。 設定檔包含預設和選擇性的設定，例如略過 Cortana 安裝。
ms.openlocfilehash: eb0d9a95c796909d024db1d061aaeace7d07ed1b
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574571"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="f2c2b-104">關於 AutoPilot 設定檔的設定</span><span class="sxs-lookup"><span data-stu-id="f2c2b-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="f2c2b-105">AutoPilot 設定檔設定</span><span class="sxs-lookup"><span data-stu-id="f2c2b-105">AutoPilot profile settings</span></span>

<span data-ttu-id="f2c2b-106">您可以控制使用者裝置上安裝 Windows 取得方式，使用 AutoPilot 設定檔。</span><span class="sxs-lookup"><span data-stu-id="f2c2b-106">You can control how Windows gets installed on user devices by using the AutoPilot profiles.</span></span> <span data-ttu-id="f2c2b-107">設定檔包含下列設定值。</span><span class="sxs-lookup"><span data-stu-id="f2c2b-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="f2c2b-108">**AutoPilot 預設功能 （必要），就會自動設定：**</span><span class="sxs-lookup"><span data-stu-id="f2c2b-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="f2c2b-109">**設定**</span><span class="sxs-lookup"><span data-stu-id="f2c2b-109">**Setting**</span></span>|<span data-ttu-id="f2c2b-110">**描述**</span><span class="sxs-lookup"><span data-stu-id="f2c2b-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f2c2b-111">略過 Cortana、 OneDrive 及 OEM 註冊</span><span class="sxs-lookup"><span data-stu-id="f2c2b-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="f2c2b-112">略過 Cortana 與個人的 OneDrive 等消費者應用程式的安裝。</span><span class="sxs-lookup"><span data-stu-id="f2c2b-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="f2c2b-113">裝置使用者，只要他或她已在裝置上的本機系統管理員，才能安裝這些更新。</span><span class="sxs-lookup"><span data-stu-id="f2c2b-113">The device user can install these later as long as he or she is a local admin on the device.</span></span> <span data-ttu-id="f2c2b-114">因為將會由 Microsoft 365 商務版管理裝置，會略過的原始的製造商註冊。</span><span class="sxs-lookup"><span data-stu-id="f2c2b-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="f2c2b-115">登入您的公司品牌的經驗</span><span class="sxs-lookup"><span data-stu-id="f2c2b-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="f2c2b-116">如果貴公司有[新增公司商標至 Office 365 登入] 頁面上](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)，裝置使用者會收到該經驗，當登入。</span><span class="sxs-lookup"><span data-stu-id="f2c2b-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="f2c2b-117">MDM 自動註冊以設定 AAD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="f2c2b-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="f2c2b-118">將由 Azure Active directory 管理使用者身分識別和使用者使用其 Microsoft 365 商務版認證，將登入 Windows 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f2c2b-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="f2c2b-119">**選用的設定：**</span><span class="sxs-lookup"><span data-stu-id="f2c2b-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="f2c2b-120">**設定**</span><span class="sxs-lookup"><span data-stu-id="f2c2b-120">**Setting**</span></span>|<span data-ttu-id="f2c2b-121">**描述**</span><span class="sxs-lookup"><span data-stu-id="f2c2b-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f2c2b-122">略過的隱私權設定 （預設為關閉）</span><span class="sxs-lookup"><span data-stu-id="f2c2b-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="f2c2b-123">如果此選項設為**上**，裝置使用者會看到 [授權合約的裝置和 Windows 當他或她第一次登入。</span><span class="sxs-lookup"><span data-stu-id="f2c2b-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="f2c2b-124">不允許使用者成為本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="f2c2b-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="f2c2b-125">如果此選項設為 [**開啟**，裝置使用者將無法安裝任何個人的應用程式，例如 Cortana。</span><span class="sxs-lookup"><span data-stu-id="f2c2b-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
