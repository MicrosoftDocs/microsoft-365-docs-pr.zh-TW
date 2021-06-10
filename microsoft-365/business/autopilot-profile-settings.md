---
title: 關於 AutoPilot 設定檔的設定
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 設定檔可協助您控制 Windows 在使用者裝置上安裝的方式。 設定檔包含略過 Cortana 安裝等預設和選用設定。
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578500"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="80a9c-104">關於 AutoPilot 設定檔的設定</span><span class="sxs-lookup"><span data-stu-id="80a9c-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="80a9c-105">AutoPilot 設定檔設定</span><span class="sxs-lookup"><span data-stu-id="80a9c-105">AutoPilot profile settings</span></span>

<span data-ttu-id="80a9c-106">您可以使用 AutoPilot 設定檔來控制如何在使用者裝置上安裝 Windows。</span><span class="sxs-lookup"><span data-stu-id="80a9c-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="80a9c-107">設定檔包含下列設定值。</span><span class="sxs-lookup"><span data-stu-id="80a9c-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="80a9c-108">**AutoPilot 預設功能 (會自動設定必要) ：**</span><span class="sxs-lookup"><span data-stu-id="80a9c-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="80a9c-109">**設定**</span><span class="sxs-lookup"><span data-stu-id="80a9c-109">**Setting**</span></span>|<span data-ttu-id="80a9c-110">**描述**</span><span class="sxs-lookup"><span data-stu-id="80a9c-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="80a9c-111">略過 Cortana、OneDrive 及 OEM 註冊</span><span class="sxs-lookup"><span data-stu-id="80a9c-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="80a9c-112">會略過安裝使用中的應用程式，例如 Cortana 和個人 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="80a9c-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="80a9c-113">只要使用者是裝置上的本機系統管理員，裝置使用者便可以安裝這些更新。</span><span class="sxs-lookup"><span data-stu-id="80a9c-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="80a9c-114">因為 Microsoft 365 商務進階版會管理裝置，所以會略過原始製造商註冊。</span><span class="sxs-lookup"><span data-stu-id="80a9c-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="80a9c-115">使用您的公司品牌登入經驗</span><span class="sxs-lookup"><span data-stu-id="80a9c-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="80a9c-116">如果貴公司已[將公司署名新增至 Microsoft 365 登入] 頁面](../admin/setup/customize-sign-in-page.md)上，裝置使用者會在登入時取得該經驗。</span><span class="sxs-lookup"><span data-stu-id="80a9c-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](../admin/setup/customize-sign-in-page.md), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="80a9c-117">MDM 使用已設定的 AAD 帳戶進行自動註冊。</span><span class="sxs-lookup"><span data-stu-id="80a9c-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="80a9c-118">Azure Active Directory 會管理使用者身分識別，使用者會以 Microsoft 365 商務進階版認證登入 Windows 和 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="80a9c-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="80a9c-119">**選用的設定：**</span><span class="sxs-lookup"><span data-stu-id="80a9c-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="80a9c-120">**設定**</span><span class="sxs-lookup"><span data-stu-id="80a9c-120">**Setting**</span></span>|<span data-ttu-id="80a9c-121">**描述**</span><span class="sxs-lookup"><span data-stu-id="80a9c-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="80a9c-122">預設會略過隱私權設定 (關閉) </span><span class="sxs-lookup"><span data-stu-id="80a9c-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="80a9c-123">如果此選項設定為 [**開啟**]，裝置使用者在第一次登入時，將不會看到裝置和 Windows 的授權合約。</span><span class="sxs-lookup"><span data-stu-id="80a9c-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="80a9c-124">不允許使用者成為本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="80a9c-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="80a9c-125">如果此選項設定為 [ **開啟**]，裝置使用者將無法安裝任何個人應用程式，例如 Cortana。</span><span class="sxs-lookup"><span data-stu-id="80a9c-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
