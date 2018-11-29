---
title: 關於 AutoPilot 設定檔的設定
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
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
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: 自動駕駛儀上設定檔可協助您控制 Windows 取得安裝在使用者裝置上的方式。設定檔包含預設和選用設定 like 略過 Cortana 安裝。
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866145"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="fa800-104">關於 AutoPilot 設定檔的設定</span><span class="sxs-lookup"><span data-stu-id="fa800-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="fa800-105">自動駕駛儀上設定檔設定</span><span class="sxs-lookup"><span data-stu-id="fa800-105">AutoPilot profile settings</span></span>

<span data-ttu-id="fa800-p102">您可以控制如何 Windows 取得安裝在使用者裝置上使用自動駕駛儀上設定檔。設定檔包含下列設定值。</span><span class="sxs-lookup"><span data-stu-id="fa800-p102">You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="fa800-108">**自動駕駛儀上預設 （必要） 的功能會自動設定：**</span><span class="sxs-lookup"><span data-stu-id="fa800-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="fa800-109">**設定**</span><span class="sxs-lookup"><span data-stu-id="fa800-109">**Setting**</span></span>|<span data-ttu-id="fa800-110">**描述**</span><span class="sxs-lookup"><span data-stu-id="fa800-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fa800-111">略過 Cortana、 OneDrive 及 OEM 註冊</span><span class="sxs-lookup"><span data-stu-id="fa800-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="fa800-p103">會略過 Cortana 和個人 OneDrive 的用戶應用程式的安裝。只要他就是在裝置上的本機系統管理員裝置使用者可以安裝這些更新。原始的製造商註冊會略過裝置將變成由 Microsoft 365 Business。</span><span class="sxs-lookup"><span data-stu-id="fa800-p103">Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="fa800-115">登入經驗與公司品牌</span><span class="sxs-lookup"><span data-stu-id="fa800-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="fa800-116">如果您的公司具有[新增您的公司品牌 Office 365 登入] 頁面上](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)，裝置使用者會取得該經驗時登入。</span><span class="sxs-lookup"><span data-stu-id="fa800-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="fa800-117">MDM 自動註冊具有設定 AAD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="fa800-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="fa800-118">使用者身分識別將變成由 Azure Active directory、 及使用者將會使用其 Microsoft 365 商務認證簽署至 Windows 與 Office 365。</span><span class="sxs-lookup"><span data-stu-id="fa800-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="fa800-119">**選用的設定：**</span><span class="sxs-lookup"><span data-stu-id="fa800-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="fa800-120">**設定**</span><span class="sxs-lookup"><span data-stu-id="fa800-120">**Setting**</span></span>|<span data-ttu-id="fa800-121">**描述**</span><span class="sxs-lookup"><span data-stu-id="fa800-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fa800-122">略過隱私權設定 （預設為關閉）</span><span class="sxs-lookup"><span data-stu-id="fa800-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="fa800-123">如果此選項設為**在**裝置使用者不會看到裝置和 Windows 授權的合約時一次第一次登入。</span><span class="sxs-lookup"><span data-stu-id="fa800-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="fa800-124">不允許使用者可以成為本機管理員</span><span class="sxs-lookup"><span data-stu-id="fa800-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="fa800-125">如果此選項設為**在**、 裝置使用者將無法安裝任何個人的應用程式，例如 Cortana。</span><span class="sxs-lookup"><span data-stu-id="fa800-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
