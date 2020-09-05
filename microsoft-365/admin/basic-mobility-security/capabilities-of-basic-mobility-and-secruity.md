---
title: 基本行動及安全性的功能
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本行動性和安全性可協助您保護和管理行動裝置。
ms.openlocfilehash: 32393f39655b81313f6592936c55e36ffe029a27
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336802"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="cdb16-103">基本行動及安全性的功能</span><span class="sxs-lookup"><span data-stu-id="cdb16-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="cdb16-104">基本行動性和安全性可協助您保護和管理行動裝置，例如 Iphone、Ipad、Androids 和 Windows phone，您的組織中已獲授權的 Microsoft 365 使用者所使用的電話。</span><span class="sxs-lookup"><span data-stu-id="cdb16-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="cdb16-105">您可以建立行動裝置管理原則，其設定可協助控制存取您組織的 Microsoft 365 電子郵件，以及支援的行動裝置和應用程式的檔。</span><span class="sxs-lookup"><span data-stu-id="cdb16-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="cdb16-106">如果裝置遺失或遭盜，您可以遠端清除裝置，以移除敏感的組織資訊。</span><span class="sxs-lookup"><span data-stu-id="cdb16-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="cdb16-107">支援的裝置</span><span class="sxs-lookup"><span data-stu-id="cdb16-107">Supported devices</span></span>

<span data-ttu-id="cdb16-108">您可以使用基本行動性和安全性來保護和管理下列裝置。</span><span class="sxs-lookup"><span data-stu-id="cdb16-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="cdb16-109">iOS 11.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="cdb16-109">iOS 11.0 or later versions</span></span>
    
- <span data-ttu-id="cdb16-110">Android 5.0 或更新版本<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="cdb16-110">Android 5.0 or later versions<sup>3</sup></span></span>
    
- <span data-ttu-id="cdb16-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cdb16-111">Windows 8.1<sup>1</sup></span></span>
    
- <span data-ttu-id="cdb16-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cdb16-112">Windows 8.1 RT<sup>1</sup></span></span>
    
- <span data-ttu-id="cdb16-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cdb16-113">Windows 10<sup>2</sup></span></span>
    
- <span data-ttu-id="cdb16-114">Windows 10 行動電話<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cdb16-114">Windows 10 Mobile<sup>2</sup></span></span>   

<span data-ttu-id="cdb16-115"><sup>1</sup>Windows 8.1 RT 裝置的存取控制限制為 Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="cdb16-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="cdb16-116"><sup>2</sup>Windows 8.1 RT 裝置的存取控制限制為 Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="cdb16-116"><sup>2</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="cdb16-117">Windows 10 的存取控制需要包含 Azure AD Premium 的訂閱，而且裝置必須加入 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="cdb16-117">Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="cdb16-118"><sup>3</sup>Windows 8.1 RT 裝置的存取控制限制為 Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="cdb16-118"><sup>3</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="cdb16-119">2020年6月之後，低於9的 Android 版本無法管理密碼設定，但在 Samsung Knox 裝置上除外。</span><span class="sxs-lookup"><span data-stu-id="cdb16-119">After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="cdb16-120">已註冊舊版作業系統的裝置仍可運作，但功能可能會變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="cdb16-120">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="cdb16-121">如果您組織中的人員使用基本行動性和安全性不支援的行動裝置，您可能想要封鎖 Exchange ActiveSync app 存取這些裝置的 Microsoft 365 電子郵件，以協助讓組織的資料更安全。</span><span class="sxs-lookup"><span data-stu-id="cdb16-121">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="cdb16-122">如需封鎖 Exchange ActiveSync 的步驟，請參閱 [管理基本行動性和安全性中的裝置存取設定](manage-device-access-settings-in-basic-mobility-and-security.md)。</span><span class="sxs-lookup"><span data-stu-id="cdb16-122">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings-in-basic-mobility-and-security.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="cdb16-123">Microsoft 365 電子郵件和檔的存取控制</span><span class="sxs-lookup"><span data-stu-id="cdb16-123">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="cdb16-124">下表中不同類型的行動裝置支援的應用程式，會提示使用者在基本行動裝置管理原則上登錄，並在其中加入新的行動裝置管理原則，該原則會套用至使用者的裝置，而且使用者先前尚未註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="cdb16-124">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="cdb16-125">如果使用者的裝置不符合原則，視您設定原則的方式而定，使用者可能會遭到封鎖，無法在這些應用程式中存取 Microsoft 365 資源，或可能有存取權，但 Microsoft 365 會報告原則違規。</span><span class="sxs-lookup"><span data-stu-id="cdb16-125">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="cdb16-126">**產品**</span><span class="sxs-lookup"><span data-stu-id="cdb16-126">**Product**</span></span>|<span data-ttu-id="cdb16-127">**iOS 10.0 或更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-127">**iOS 10.0 or later**</span></span>|<span data-ttu-id="cdb16-128">**Android 5.0 或更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-128">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cdb16-129">**Exchange** Exchange ActiveSync 包含內建的電子郵件和協力廠商的應用程式，例如 TouchDown，使用 Exchange ActiveSync 版本14.1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="cdb16-129">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="cdb16-130">郵件</span><span class="sxs-lookup"><span data-stu-id="cdb16-130">Mail</span></span> |<span data-ttu-id="cdb16-131">電子郵件</span><span class="sxs-lookup"><span data-stu-id="cdb16-131">Email</span></span> |
|<span data-ttu-id="cdb16-132">**Office**  和 **OneDrive 商務**版</span><span class="sxs-lookup"><span data-stu-id="cdb16-132">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="cdb16-133">Outlook</span><span class="sxs-lookup"><span data-stu-id="cdb16-133">Outlook</span></span> </br><span data-ttu-id="cdb16-134">OneDrive</span><span class="sxs-lookup"><span data-stu-id="cdb16-134">OneDrive</span></span> </br><span data-ttu-id="cdb16-135">Word</span><span class="sxs-lookup"><span data-stu-id="cdb16-135">Word</span></span> </br><span data-ttu-id="cdb16-136">Excel</span><span class="sxs-lookup"><span data-stu-id="cdb16-136">Excel</span></span> </br><span data-ttu-id="cdb16-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cdb16-137">PowerPoint</span></span>|<span data-ttu-id="cdb16-138">**在手機和平板電腦上**：</span><span class="sxs-lookup"><span data-stu-id="cdb16-138">**On phones and tablets**:</span></span><br/><span data-ttu-id="cdb16-139">Outlook</span><span class="sxs-lookup"><span data-stu-id="cdb16-139">Outlook</span></span> <br/> <span data-ttu-id="cdb16-140">OneDrive</span><span class="sxs-lookup"><span data-stu-id="cdb16-140">OneDrive</span></span> <br/> <span data-ttu-id="cdb16-141">Word</span><span class="sxs-lookup"><span data-stu-id="cdb16-141">Word</span></span> <br/> <span data-ttu-id="cdb16-142">Excel</span><span class="sxs-lookup"><span data-stu-id="cdb16-142">Excel</span></span> <br/> <span data-ttu-id="cdb16-143">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cdb16-143">PowerPoint</span></span> <br/> <span data-ttu-id="cdb16-144">**僅限電話：**</span><span class="sxs-lookup"><span data-stu-id="cdb16-144">**On phones only:**</span></span> <br/> <span data-ttu-id="cdb16-145">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="cdb16-145">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="cdb16-146">支援 iOS 10.0 和更新版本包含 iPhone 和 iPad 裝置。</span><span class="sxs-lookup"><span data-stu-id="cdb16-146">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="cdb16-147">Microsoft 365 的行動裝置管理不支援 BlackBerry OS 裝置的管理。</span><span class="sxs-lookup"><span data-stu-id="cdb16-147">Management of BlackBerry OS devices isn’t supported by Mobile Device Management for Microsoft 365.</span></span> <span data-ttu-id="cdb16-148">使用 BlackBerry Business 雲端服務 (BBCS) 從 BlackBerry 管理 BlackBerry 作業系統裝置。</span><span class="sxs-lookup"><span data-stu-id="cdb16-148">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="cdb16-149">支援執行 Android 作業系統的 Blackberry 裝置作為標準 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="cdb16-149">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="cdb16-150">如果使用者使用行動瀏覽器來存取 Microsoft 365 SharePoint 網站、Office Online 中的檔，或 Outlook Web App 中的電子郵件，則不會提示使用者進行註冊，也不會對原則加以舉報。</span><span class="sxs-lookup"><span data-stu-id="cdb16-150">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>
    
<span data-ttu-id="cdb16-151">下圖顯示當具有新裝置的使用者利用基本行動性和安全性，登入支援存取控制的應用程式時會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="cdb16-151">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="cdb16-152">使用者在註冊其裝置之前，系統會封鎖使用者存取應用程式中的 Microsoft 365 資源。</span><span class="sxs-lookup"><span data-stu-id="cdb16-152">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本行動性和安全性存取控制":::

<span data-ttu-id="cdb16-154">附注：在 MDM for Microsoft 365 商務 Standard 中建立的原則和存取規則，將會覆寫 exchange 系統管理中心建立的 Exchange ActiveSync 行動裝置信箱原則和裝置存取規則。</span><span class="sxs-lookup"><span data-stu-id="cdb16-154">Note:Policies and access rules created in MDM for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="cdb16-155">在 MDM 針對 Microsoft 365 商務標準註冊裝置時，會忽略任何 Exchange ActiveSync 行動裝置信箱原則或裝置存取規則套用至裝置。</span><span class="sxs-lookup"><span data-stu-id="cdb16-155">After a device is enrolled in MDM for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="cdb16-156">若要深入瞭解 Exchange ActiveSync，請參閱 exchange [Online 中的 exchange ActiveSync](https://go.microsoft.com/fwlink/p/?LinkId=524380)。</span><span class="sxs-lookup"><span data-stu-id="cdb16-156">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="cdb16-157">行動裝置的原則設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-157">Policy settings for mobile devices</span></span>

<span data-ttu-id="cdb16-158">如果您建立一個原則，以在開啟特定設定時封鎖存取，當您使用 [microsoft 365 電子郵件和檔的存取控制](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0?ui=en-us&rs=en-us&ad=us#bkmk_accesscontrol)中所列的支援應用程式時，系統會封鎖使用者存取 Microsoft 365 資源。</span><span class="sxs-lookup"><span data-stu-id="cdb16-158">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0?ui=en-us&rs=en-us&ad=us#bkmk_accesscontrol).</span></span> 

<span data-ttu-id="cdb16-159">在下列各節中，可以封鎖使用者存取 Microsoft 365 資源的設定如下：</span><span class="sxs-lookup"><span data-stu-id="cdb16-159">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="cdb16-160">安全性</span><span class="sxs-lookup"><span data-stu-id="cdb16-160">Security</span></span>
    
- <span data-ttu-id="cdb16-161">加密</span><span class="sxs-lookup"><span data-stu-id="cdb16-161">Encryption</span></span>
    
- <span data-ttu-id="cdb16-162">越獄中斷</span><span class="sxs-lookup"><span data-stu-id="cdb16-162">Jail broken</span></span>
    
- <span data-ttu-id="cdb16-163">受管理的電子郵件設定檔</span><span class="sxs-lookup"><span data-stu-id="cdb16-163">Managed email profile</span></span>  

<span data-ttu-id="cdb16-164">例如，下圖顯示使用已註冊裝置的使用者不符合套用至其裝置之行動裝置管理原則中的安全性設定時，會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="cdb16-164">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="cdb16-165">使用者可使用基本行動性和安全性登入支援存取控制的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdb16-165">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="cdb16-166">在使用者的裝置符合安全性設定之前，系統會封鎖他們存取應用程式中的 Microsoft 365 資源。</span><span class="sxs-lookup"><span data-stu-id="cdb16-166">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本行動及安全性合規性訊息":::

<span data-ttu-id="cdb16-168">下列各節列出您可以用來協助保護和管理連接至 Microsoft 365 組織資源之行動裝置的原則設定。</span><span class="sxs-lookup"><span data-stu-id="cdb16-168">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="cdb16-169">安全性設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-169">Security settings</span></span>

|<span data-ttu-id="cdb16-170">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="cdb16-170">**Setting name**</span></span>|<span data-ttu-id="cdb16-171">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-171">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cdb16-172">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-172">**Android 5 and later**</span></span>|<span data-ttu-id="cdb16-173">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cdb16-173">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cdb16-174">需要密碼</span><span class="sxs-lookup"><span data-stu-id="cdb16-174">Require a password</span></span>|<span data-ttu-id="cdb16-175">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-175">Yes</span></span>|<span data-ttu-id="cdb16-176">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-176">Yes</span></span>|<span data-ttu-id="cdb16-177">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-177">Yes</span></span>|
|<span data-ttu-id="cdb16-178">防止簡單密碼</span><span class="sxs-lookup"><span data-stu-id="cdb16-178">Prevent simple password</span></span>|<span data-ttu-id="cdb16-179">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-179">Yes</span></span>|<span data-ttu-id="cdb16-180">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-180">No</span></span>|<span data-ttu-id="cdb16-181">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-181">No</span></span>|
|<span data-ttu-id="cdb16-182">需要一個數位元密碼</span><span class="sxs-lookup"><span data-stu-id="cdb16-182">Require an alphanumeric password</span></span>|<span data-ttu-id="cdb16-183">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-183">Yes</span></span>|<span data-ttu-id="cdb16-184">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-184">No</span></span>|<span data-ttu-id="cdb16-185">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-185">No</span></span>|
|<span data-ttu-id="cdb16-186">密碼最小長度</span><span class="sxs-lookup"><span data-stu-id="cdb16-186">Minimum password length</span></span> |<span data-ttu-id="cdb16-187">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-187">Yes</span></span>|<span data-ttu-id="cdb16-188">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-188">Yes</span></span>|<span data-ttu-id="cdb16-189">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-189">Yes</span></span>|
|<span data-ttu-id="cdb16-190">擦除裝置之前的登入失敗次數</span><span class="sxs-lookup"><span data-stu-id="cdb16-190">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="cdb16-191">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-191">Yes</span></span>|<span data-ttu-id="cdb16-192">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-192">Yes</span></span>|<span data-ttu-id="cdb16-193">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-193">Yes</span></span>|
|<span data-ttu-id="cdb16-194">鎖定裝置之前的閒置分鐘</span><span class="sxs-lookup"><span data-stu-id="cdb16-194">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="cdb16-195">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-195">Yes</span></span>|<span data-ttu-id="cdb16-196">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-196">Yes</span></span>|<span data-ttu-id="cdb16-197">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-197">Yes</span></span>|
|<span data-ttu-id="cdb16-198">密碼到期 (天) </span><span class="sxs-lookup"><span data-stu-id="cdb16-198">Password expiration (days)</span></span> |<span data-ttu-id="cdb16-199">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-199">Yes</span></span>|<span data-ttu-id="cdb16-200">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-200">Yes</span></span>|<span data-ttu-id="cdb16-201">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-201">Yes</span></span>|
|<span data-ttu-id="cdb16-202">記住密碼歷程記錄，並防止重複使用</span><span class="sxs-lookup"><span data-stu-id="cdb16-202">Remember password history and prevent reuse</span></span> |<span data-ttu-id="cdb16-203">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-203">Yes</span></span>|<span data-ttu-id="cdb16-204">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-204">Yes</span></span>|<span data-ttu-id="cdb16-205">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-205">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="cdb16-206">加密設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-206">Encryption settings</span></span> 

|<span data-ttu-id="cdb16-207">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="cdb16-207">**Setting name**</span></span>|<span data-ttu-id="cdb16-208">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-208">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cdb16-209">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-209">**Android 5 and later**</span></span>|<span data-ttu-id="cdb16-210">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cdb16-210">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cdb16-211">裝置<sup>1</sup>上需要資料加密</span><span class="sxs-lookup"><span data-stu-id="cdb16-211">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="cdb16-212">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-212">No</span></span>|<span data-ttu-id="cdb16-213">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-213">Yes</span></span>|<span data-ttu-id="cdb16-214">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-214">Yes</span></span>|

<span data-ttu-id="cdb16-215"><sup>1</sup>使用 Samsung Knox，您也可以要求在儲存卡上加密。</span><span class="sxs-lookup"><span data-stu-id="cdb16-215"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="cdb16-216">越獄中斷設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-216">Jail broken setting</span></span> 

|<span data-ttu-id="cdb16-217">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="cdb16-217">**Setting name**</span></span>|<span data-ttu-id="cdb16-218">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-218">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cdb16-219">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-219">**Android 5 and later**</span></span>|<span data-ttu-id="cdb16-220">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cdb16-220">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cdb16-221">無法越獄中斷或根裝置</span><span class="sxs-lookup"><span data-stu-id="cdb16-221">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="cdb16-222">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-222">Yes</span></span>|<span data-ttu-id="cdb16-223">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-223">Yes</span></span>|<span data-ttu-id="cdb16-224">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-224">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="cdb16-225">受管理的電子郵件設定檔選項</span><span class="sxs-lookup"><span data-stu-id="cdb16-225">Managed email profile option</span></span> 

<span data-ttu-id="cdb16-226">下列選項可以封鎖使用者在使用手動建立的電子郵件設定檔時存取其 Microsoft 365 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cdb16-226">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="cdb16-227">IOS 裝置上的使用者必須先刪除其手動建立的電子郵件設定檔，才能存取其電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cdb16-227">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="cdb16-228">在刪除設定檔之後，系統會自動在裝置上建立新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="cdb16-228">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="cdb16-229">如需使用者如何相容的相關指示，請參閱 [找到現有的電子郵件帳戶](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)。</span><span class="sxs-lookup"><span data-stu-id="cdb16-229">For instructions on how end users can get compliant, see [An existing email account was found](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="cdb16-230">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="cdb16-230">**Setting name**</span></span>|<span data-ttu-id="cdb16-231">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-231">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cdb16-232">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-232">**Android 5 and later**</span></span>|<span data-ttu-id="cdb16-233">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cdb16-233">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cdb16-234">電子郵件設定檔已管理</span><span class="sxs-lookup"><span data-stu-id="cdb16-234">Email profile is managed</span></span> |<span data-ttu-id="cdb16-235">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-235">Yes</span></span>|<span data-ttu-id="cdb16-236">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-236">No</span></span>|<span data-ttu-id="cdb16-237">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-237">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="cdb16-238">雲端設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-238">Cloud settings</span></span> 

|<span data-ttu-id="cdb16-239">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="cdb16-239">**Setting name**</span></span>|<span data-ttu-id="cdb16-240">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-240">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cdb16-241">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-241">**Android 5 and later**</span></span>|<span data-ttu-id="cdb16-242">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cdb16-242">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cdb16-243">需要加密備份</span><span class="sxs-lookup"><span data-stu-id="cdb16-243">Require encrypted backup</span></span> |<span data-ttu-id="cdb16-244">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-244">Yes</span></span>|<span data-ttu-id="cdb16-245">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-245">No</span></span>|<span data-ttu-id="cdb16-246">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-246">No</span></span>|
|<span data-ttu-id="cdb16-247">封鎖雲端備份</span><span class="sxs-lookup"><span data-stu-id="cdb16-247">Block cloud backup</span></span> |<span data-ttu-id="cdb16-248">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-248">Yes</span></span>|<span data-ttu-id="cdb16-249">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-249">No</span></span>|<span data-ttu-id="cdb16-250">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-250">No</span></span>|
|<span data-ttu-id="cdb16-251">封鎖檔同步處理</span><span class="sxs-lookup"><span data-stu-id="cdb16-251">Block document synchronization</span></span> |<span data-ttu-id="cdb16-252">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-252">Yes</span></span>|<span data-ttu-id="cdb16-253">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-253">No</span></span>|<span data-ttu-id="cdb16-254">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-254">No</span></span>|
|<span data-ttu-id="cdb16-255">封鎖照片同步處理</span><span class="sxs-lookup"><span data-stu-id="cdb16-255">Block photo synchronization</span></span>  |<span data-ttu-id="cdb16-256">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-256">Yes</span></span>|<span data-ttu-id="cdb16-257">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-257">No</span></span>|<span data-ttu-id="cdb16-258">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-258">No</span></span>|
|<span data-ttu-id="cdb16-259">允許 Google 備份</span><span class="sxs-lookup"><span data-stu-id="cdb16-259">Allow Google backup</span></span>  |<span data-ttu-id="cdb16-260">不適用</span><span class="sxs-lookup"><span data-stu-id="cdb16-260">N/A</span></span>|<span data-ttu-id="cdb16-261">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-261">No</span></span>|<span data-ttu-id="cdb16-262">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-262">Yes</span></span>|
|<span data-ttu-id="cdb16-263">允許 Google 帳戶自動同步處理</span><span class="sxs-lookup"><span data-stu-id="cdb16-263">Allow Google account auto sync</span></span>  |<span data-ttu-id="cdb16-264">不適用</span><span class="sxs-lookup"><span data-stu-id="cdb16-264">N/A</span></span>|<span data-ttu-id="cdb16-265">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-265">No</span></span>|<span data-ttu-id="cdb16-266">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-266">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="cdb16-267">系統設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-267">System settings</span></span> 

|<span data-ttu-id="cdb16-268">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="cdb16-268">**Setting name**</span></span>|<span data-ttu-id="cdb16-269">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-269">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cdb16-270">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-270">**Android 5 and later**</span></span>|<span data-ttu-id="cdb16-271">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cdb16-271">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cdb16-272">封鎖螢幕捕捉</span><span class="sxs-lookup"><span data-stu-id="cdb16-272">Block screen capture</span></span> |<span data-ttu-id="cdb16-273">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-273">Yes</span></span>|<span data-ttu-id="cdb16-274">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-274">No</span></span>|<span data-ttu-id="cdb16-275">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-275">Yes</span></span>|
|<span data-ttu-id="cdb16-276">封鎖從裝置傳送診斷資料</span><span class="sxs-lookup"><span data-stu-id="cdb16-276">Block sending diagnostic data from device</span></span> |<span data-ttu-id="cdb16-277">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-277">Yes</span></span>|<span data-ttu-id="cdb16-278">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-278">No</span></span>|<span data-ttu-id="cdb16-279">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-279">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="cdb16-280">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-280">Application settings</span></span> 

|<span data-ttu-id="cdb16-281">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="cdb16-281">**Setting name**</span></span>|<span data-ttu-id="cdb16-282">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-282">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cdb16-283">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-283">**Android 5 and later**</span></span>|<span data-ttu-id="cdb16-284">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cdb16-284">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cdb16-285">在裝置上封鎖影片會議</span><span class="sxs-lookup"><span data-stu-id="cdb16-285">Block video conferences on device</span></span> |<span data-ttu-id="cdb16-286">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-286">Yes</span></span>|<span data-ttu-id="cdb16-287">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-287">No</span></span>|<span data-ttu-id="cdb16-288">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-288">No</span></span>|
|<span data-ttu-id="cdb16-289">封鎖對應用程式存放區的存取</span><span class="sxs-lookup"><span data-stu-id="cdb16-289">Block access to application store</span></span> |<span data-ttu-id="cdb16-290">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-290">Yes</span></span>|<span data-ttu-id="cdb16-291">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-291">No</span></span>|<span data-ttu-id="cdb16-292">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-292">Yes</span></span>|
|<span data-ttu-id="cdb16-293">存取應用程式存放區時需要密碼</span><span class="sxs-lookup"><span data-stu-id="cdb16-293">Require password when accessing application store</span></span> |<span data-ttu-id="cdb16-294">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-294">No</span></span>|<span data-ttu-id="cdb16-295">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-295">Yes</span></span>|<span data-ttu-id="cdb16-296">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-296">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="cdb16-297">裝置功能設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-297">Device capabilities settings</span></span> 

|<span data-ttu-id="cdb16-298">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="cdb16-298">**Setting name**</span></span>|<span data-ttu-id="cdb16-299">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-299">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cdb16-300">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-300">**Android 5 and later**</span></span>|<span data-ttu-id="cdb16-301">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cdb16-301">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cdb16-302">使用 [可移動儲存區] 封鎖連線</span><span class="sxs-lookup"><span data-stu-id="cdb16-302">Block connection with removable storage</span></span> |<span data-ttu-id="cdb16-303">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-303">Yes</span></span>|<span data-ttu-id="cdb16-304">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-304">Yes</span></span>|<span data-ttu-id="cdb16-305">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-305">No</span></span>|
|<span data-ttu-id="cdb16-306">封鎖藍牙連線</span><span class="sxs-lookup"><span data-stu-id="cdb16-306">Block Bluetooth connection</span></span> |<span data-ttu-id="cdb16-307">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-307">Yes</span></span>|<span data-ttu-id="cdb16-308">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-308">Yes</span></span>|<span data-ttu-id="cdb16-309">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-309">No</span></span>|

##  <a name="additional-settings"></a><span data-ttu-id="cdb16-310">其他設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-310">Additional settings</span></span> 

<span data-ttu-id="cdb16-311">您可以使用 PowerShell Cmdlet 來設定下列其他原則設定。</span><span class="sxs-lookup"><span data-stu-id="cdb16-311">You can set the following additional policy settings by using PowerShell cmdlets.</span></span> <span data-ttu-id="cdb16-312">如需詳細資訊，請參閱 [安全性 & 規範中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="cdb16-312">For more information, see [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

|<span data-ttu-id="cdb16-313">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="cdb16-313">**Setting name**</span></span>|<span data-ttu-id="cdb16-314">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-314">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cdb16-315">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="cdb16-315">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cdb16-316">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="cdb16-316">CameraEnabled</span></span>|<span data-ttu-id="cdb16-317">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-317">Yes</span></span>|<span data-ttu-id="cdb16-318">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-318">Yes</span></span>|
|<span data-ttu-id="cdb16-319">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="cdb16-319">RegionRatings</span></span>|<span data-ttu-id="cdb16-320">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-320">Yes</span></span>|<span data-ttu-id="cdb16-321">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-321">No</span></span>|
|<span data-ttu-id="cdb16-322">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="cdb16-322">MoviesRatings</span></span>|<span data-ttu-id="cdb16-323">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-323">Yes</span></span>|<span data-ttu-id="cdb16-324">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-324">No</span></span>|
|<span data-ttu-id="cdb16-325">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="cdb16-325">TVShowsRating</span></span> |<span data-ttu-id="cdb16-326">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-326">Yes</span></span>|<span data-ttu-id="cdb16-327">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-327">No</span></span>|
|<span data-ttu-id="cdb16-328">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="cdb16-328">AppsRatings</span></span> |<span data-ttu-id="cdb16-329">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-329">Yes</span></span>|<span data-ttu-id="cdb16-330">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-330">No</span></span>|
|<span data-ttu-id="cdb16-331">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="cdb16-331">AllowVoiceDialing</span></span> |<span data-ttu-id="cdb16-332">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-332">Yes</span></span>|<span data-ttu-id="cdb16-333">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-333">No</span></span>|
|<span data-ttu-id="cdb16-334">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="cdb16-334">AllowVoiceAssistant</span></span> |<span data-ttu-id="cdb16-335">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-335">Yes</span></span>|<span data-ttu-id="cdb16-336">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-336">No</span></span>|
|<span data-ttu-id="cdb16-337">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="cdb16-337">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="cdb16-338">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-338">Yes</span></span>|<span data-ttu-id="cdb16-339">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-339">No</span></span>|
|<span data-ttu-id="cdb16-340">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="cdb16-340">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="cdb16-341">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-341">Yes</span></span>|<span data-ttu-id="cdb16-342">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-342">No</span></span>|
|<span data-ttu-id="cdb16-343">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="cdb16-343">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="cdb16-344">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-344">Yes</span></span>|<span data-ttu-id="cdb16-345">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-345">No</span></span>|
|<span data-ttu-id="cdb16-346">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="cdb16-346">PasswordQuality</span></span> |<span data-ttu-id="cdb16-347">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-347">No</span></span>|<span data-ttu-id="cdb16-348">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-348">Yes</span></span>|
|<span data-ttu-id="cdb16-349">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="cdb16-349">SystemSecurityTLS</span></span>  |<span data-ttu-id="cdb16-350">是</span><span class="sxs-lookup"><span data-stu-id="cdb16-350">Yes</span></span>|<span data-ttu-id="cdb16-351">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-351">No</span></span>|
|<span data-ttu-id="cdb16-352">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="cdb16-352">WLANEnabled</span></span>  |<span data-ttu-id="cdb16-353">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-353">No</span></span>|<span data-ttu-id="cdb16-354">否</span><span class="sxs-lookup"><span data-stu-id="cdb16-354">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="cdb16-355">Windows 支援的設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-355">Settings supported by Windows</span></span> 

<span data-ttu-id="cdb16-356">您可以將 Windows 10 裝置登記為行動裝置，以進行管理。</span><span class="sxs-lookup"><span data-stu-id="cdb16-356">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="cdb16-357">在部署適用的原則之後，當使用者第一次使用內建的電子郵件應用程式存取其 Microsoft 365 電子郵件時，將需要使用 Windows 10 裝置的使用者才會註冊基本行動性和安全性。 (需要 Azure AD premium 訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="cdb16-357">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="cdb16-358">已註冊為行動裝置的 Windows 10 裝置可支援下列設定。</span><span class="sxs-lookup"><span data-stu-id="cdb16-358">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="cdb16-359">這些設定不會封鎖使用者存取 Microsoft 365 資源。</span><span class="sxs-lookup"><span data-stu-id="cdb16-359">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="cdb16-360">安全性設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-360">Security settings</span></span>

- <span data-ttu-id="cdb16-361">需要一個數位元密碼</span><span class="sxs-lookup"><span data-stu-id="cdb16-361">Require an alphanumeric password</span></span>

- <span data-ttu-id="cdb16-362">密碼最小長度</span><span class="sxs-lookup"><span data-stu-id="cdb16-362">Minimum password length</span></span>
    
- <span data-ttu-id="cdb16-363">擦除裝置之前的登入失敗次數</span><span class="sxs-lookup"><span data-stu-id="cdb16-363">Number of sign-in failures before device is wiped</span></span>
    
- <span data-ttu-id="cdb16-364">鎖定裝置之前的閒置分鐘</span><span class="sxs-lookup"><span data-stu-id="cdb16-364">Minutes of inactivity before device is locked</span></span>
    
- <span data-ttu-id="cdb16-365">密碼到期 (天) </span><span class="sxs-lookup"><span data-stu-id="cdb16-365">Password expiration (days)</span></span>
    
- <span data-ttu-id="cdb16-366">記住密碼歷程記錄，並防止重複使用</span><span class="sxs-lookup"><span data-stu-id="cdb16-366">Remember password history and prevent reuse</span></span>   

>[!NOTE]
><span data-ttu-id="cdb16-367">下列設定控制密碼只會控制本機 Windows 帳戶。</span><span class="sxs-lookup"><span data-stu-id="cdb16-367">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="cdb16-368">透過加入網域或 Azure Active Directory 所提供的 Windows 帳戶，不會受到這些設定的影響。</span><span class="sxs-lookup"><span data-stu-id="cdb16-368">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="cdb16-369">系統設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-369">System settings</span></span>

<span data-ttu-id="cdb16-370">封鎖從裝置發送診斷資料。</span><span class="sxs-lookup"><span data-stu-id="cdb16-370">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="cdb16-371">其他設定</span><span class="sxs-lookup"><span data-stu-id="cdb16-371">Additional settings</span></span>

<span data-ttu-id="cdb16-372">您可以使用 PowerShell Cmdlet 來設定這些額外的原則設定：</span><span class="sxs-lookup"><span data-stu-id="cdb16-372">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="cdb16-373">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="cdb16-373">AllowConvenienceLogon</span></span>
    
- <span data-ttu-id="cdb16-374">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="cdb16-374">UserAccountControlStatus</span></span>
    
- <span data-ttu-id="cdb16-375">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="cdb16-375">FirewallStatus</span></span>
    
- <span data-ttu-id="cdb16-376">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="cdb16-376">AutoUpdateStatus</span></span>
    
- <span data-ttu-id="cdb16-377">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="cdb16-377">AntiVirusStatus</span></span>   

- <span data-ttu-id="cdb16-378">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="cdb16-378">AntiVirusSignatureStatus</span></span>
    
- <span data-ttu-id="cdb16-379">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="cdb16-379">SmartScreenEnabled</span></span>
    
- <span data-ttu-id="cdb16-380">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="cdb16-380">WorkFoldersSyncUrl</span></span>
    

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="cdb16-381">遠端清除行動裝置</span><span class="sxs-lookup"><span data-stu-id="cdb16-381">Remotely wipe a mobile device</span></span>

<span data-ttu-id="cdb16-382">如果裝置遺失或遭盜，您可以移除敏感的組織資料，並透過從安全性 & 合規性中心（>**資料遺失防護**  >  **裝置管理**）進行擦除，以防止存取 Microsoft 365 組織資源。</span><span class="sxs-lookup"><span data-stu-id="cdb16-382">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="cdb16-383">您可以進行選擇性擦除，只移除組織資料或完全清除，以刪除裝置中的所有資訊，並將其還原為出廠設定。</span><span class="sxs-lookup"><span data-stu-id="cdb16-383">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="cdb16-384">如需詳細資訊，請參閱 [在基本行動及安全性中清除行動裝置](wipe-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="cdb16-384">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cdb16-385">相關主題</span><span class="sxs-lookup"><span data-stu-id="cdb16-385">Related topics</span></span>

[<span data-ttu-id="cdb16-386">Microsoft 365 的基本行動及安全性概述</span><span class="sxs-lookup"><span data-stu-id="cdb16-386">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[<span data-ttu-id="cdb16-387">在基本行動性和安全性中建立裝置安全性原則</span><span class="sxs-lookup"><span data-stu-id="cdb16-387">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies-in-basic-mmobility-and-security.md)