---
title: 基本行動與安全性的功能
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
ms.openlocfilehash: 41df5bfba7362d9c2b3a47deca4e4586902bbd98
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706175"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="7ab2b-103">基本行動與安全性的功能</span><span class="sxs-lookup"><span data-stu-id="7ab2b-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="7ab2b-104">基本行動性和安全性可協助您保護和管理行動裝置，例如 iphone、ipad、Androids 和 Windows 電話，以供組織中的授權 Microsoft 365 使用者使用。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="7ab2b-105">您可以建立行動裝置管理原則，其設定可協助控制存取您組織的 Microsoft 365 電子郵件和檔，以供支援的行動裝置和應用程式使用。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="7ab2b-106">如果裝置遺失或遭盜，您可以遠端清除裝置，以移除敏感的組織資訊。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="7ab2b-107">支援的裝置</span><span class="sxs-lookup"><span data-stu-id="7ab2b-107">Supported devices</span></span>

<span data-ttu-id="7ab2b-108">您可以使用基本行動性和安全性來保護和管理下列裝置。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="7ab2b-109">iOS 11.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="7ab2b-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="7ab2b-110">Android 5.0 或更新版本<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="7ab2b-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="7ab2b-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ab2b-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="7ab2b-112">Windows 8.1RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ab2b-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="7ab2b-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7ab2b-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="7ab2b-114">Windows 10 行動裝置版<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7ab2b-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="7ab2b-115"><sup>1</sup>Windows 8.1 RT 裝置的存取控制限制為 Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="7ab2b-116"><sup>2</sup>Windows 10 的存取控制需要包含 Azure AD 進階版且裝置必須加入 Azure Active Directory 的訂閱。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-116"><sup>2</sup>Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="7ab2b-117"><sup>3</sup>2020年6月之後，低於9的 Android 版本無法管理密碼設定，但在 Samsung Knox 裝置上除外。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-117"><sup>3</sup>After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="7ab2b-118">已註冊舊版作業系統的裝置仍可運作，但功能可能會變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-118">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="7ab2b-119">如果您組織中的人員使用基本行動性和安全性不支援的行動裝置，您可能想要封鎖 Microsoft 365 電子郵件的 Exchange ActiveSync 應用程式存取權，讓組織的資料更加安全。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-119">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="7ab2b-120">如需封鎖 Exchange ActiveSync 的步驟，請參閱[管理基本行動性和安全性中的裝置存取設定](manage-device-access-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-120">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="7ab2b-121">Microsoft 365 電子郵件和檔的存取控制</span><span class="sxs-lookup"><span data-stu-id="7ab2b-121">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="7ab2b-122">下表中不同類型的行動裝置支援的應用程式，會提示使用者在基本行動裝置管理原則上登錄，並在其中加入新的行動裝置管理原則，該原則會套用至使用者的裝置，而且使用者先前尚未註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-122">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="7ab2b-123">如果使用者的裝置不符合原則，視您設定原則的方式而定，使用者可能會遭到封鎖，無法存取這些應用程式中的 Microsoft 365 資源，也可能具有存取權，但 Microsoft 365 會報告原則違規。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-123">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="7ab2b-124">**產品**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-124">**Product**</span></span>|<span data-ttu-id="7ab2b-125">**iOS 10.0 或更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-125">**iOS 10.0 or later**</span></span>|<span data-ttu-id="7ab2b-126">**Android 5.0 或更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-126">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ab2b-127">**Exchange** Exchange ActiveSync 包含內建的電子郵件和協力廠商的應用程式，例如 TouchDown，使用 Exchange ActiveSync 版本14.1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-127">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="7ab2b-128">郵件</span><span class="sxs-lookup"><span data-stu-id="7ab2b-128">Mail</span></span> |<span data-ttu-id="7ab2b-129">電子郵件</span><span class="sxs-lookup"><span data-stu-id="7ab2b-129">Email</span></span> |
|<span data-ttu-id="7ab2b-130">**Office**  和  **商務用 OneDrive**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-130">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="7ab2b-131">Outlook</span><span class="sxs-lookup"><span data-stu-id="7ab2b-131">Outlook</span></span> </br><span data-ttu-id="7ab2b-132">OneDrive</span><span class="sxs-lookup"><span data-stu-id="7ab2b-132">OneDrive</span></span> </br><span data-ttu-id="7ab2b-133">Word</span><span class="sxs-lookup"><span data-stu-id="7ab2b-133">Word</span></span> </br><span data-ttu-id="7ab2b-134">Excel</span><span class="sxs-lookup"><span data-stu-id="7ab2b-134">Excel</span></span> </br><span data-ttu-id="7ab2b-135">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7ab2b-135">PowerPoint</span></span>|<span data-ttu-id="7ab2b-136">**在手機和平板電腦上**：</span><span class="sxs-lookup"><span data-stu-id="7ab2b-136">**On phones and tablets**:</span></span><br/><span data-ttu-id="7ab2b-137">Outlook</span><span class="sxs-lookup"><span data-stu-id="7ab2b-137">Outlook</span></span> <br/> <span data-ttu-id="7ab2b-138">OneDrive</span><span class="sxs-lookup"><span data-stu-id="7ab2b-138">OneDrive</span></span> <br/> <span data-ttu-id="7ab2b-139">Word</span><span class="sxs-lookup"><span data-stu-id="7ab2b-139">Word</span></span> <br/> <span data-ttu-id="7ab2b-140">Excel</span><span class="sxs-lookup"><span data-stu-id="7ab2b-140">Excel</span></span> <br/> <span data-ttu-id="7ab2b-141">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7ab2b-141">PowerPoint</span></span> <br/> <span data-ttu-id="7ab2b-142">**僅限電話：**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-142">**On phones only:**</span></span> <br/> <span data-ttu-id="7ab2b-143">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="7ab2b-143">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="7ab2b-144">支援 iOS 10.0 和更新版本包括 iPhone 和 iPad 裝置。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-144">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="7ab2b-145">基本的安全性和行動性不支援 BlackBerry OS 裝置的管理。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-145">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="7ab2b-146">使用 BlackBerry Business 雲端服務 (BBCS) 從 BlackBerry 管理 BlackBerry 作業系統裝置。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-146">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="7ab2b-147">支援執行 Android 作業系統的 Blackberry 裝置作為標準 Android 裝置</span><span class="sxs-lookup"><span data-stu-id="7ab2b-147">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="7ab2b-148">如果使用者使用行動瀏覽器來存取 Microsoft 365 SharePoint 網站、檔 Office 線上或 Outlook Web App 中的電子郵件，則不會提示使用者進行註冊，也不會對原則加以舉報。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-148">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="7ab2b-149">下圖顯示當具有新裝置的使用者利用基本行動性和安全性，登入支援存取控制的應用程式時會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-149">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="7ab2b-150">使用者在註冊其裝置之前，系統會封鎖使用者存取應用程式中的 Microsoft 365 資源。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-150">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本行動性和安全性存取控制":::

> [!NOTE]
> <span data-ttu-id="7ab2b-152">在 Microsoft 365 商務標準版基本行動性和安全性中建立的原則和存取規則，會覆寫 Exchange 系統管理中心建立 Exchange ActiveSync 行動裝置信箱原則和裝置存取規則。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-152">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="7ab2b-153">在 Microsoft 365 商務標準版的基本行動性和安全性中，裝置註冊後，就會忽略套用至裝置的任何 Exchange ActiveSync 行動裝置信箱原則或裝置存取規則。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-153">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="7ab2b-154">若要深入瞭解 Exchange ActiveSync，請參閱 [Exchange Online 中的 Exchange ActiveSync](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-154">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="7ab2b-155">行動裝置的原則設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-155">Policy settings for mobile devices</span></span>

<span data-ttu-id="7ab2b-156">如果您建立一個原則，以在開啟特定設定時封鎖存取，當您使用[Microsoft 365 電子郵件和檔的存取控制](capabilities.md)中所列的支援應用程式時，系統會封鎖使用者存取 Microsoft 365 資源。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-156">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="7ab2b-157">可以封鎖使用者存取 Microsoft 365 資源的設定包括下列各節：</span><span class="sxs-lookup"><span data-stu-id="7ab2b-157">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="7ab2b-158">安全性</span><span class="sxs-lookup"><span data-stu-id="7ab2b-158">Security</span></span>

- <span data-ttu-id="7ab2b-159">加密</span><span class="sxs-lookup"><span data-stu-id="7ab2b-159">Encryption</span></span>

- <span data-ttu-id="7ab2b-160">越獄中斷</span><span class="sxs-lookup"><span data-stu-id="7ab2b-160">Jail broken</span></span>

- <span data-ttu-id="7ab2b-161">受管理的電子郵件設定檔</span><span class="sxs-lookup"><span data-stu-id="7ab2b-161">Managed email profile</span></span>  

<span data-ttu-id="7ab2b-162">例如，下圖顯示使用已註冊裝置的使用者不符合套用至其裝置之行動裝置管理原則中的安全性設定時，會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-162">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="7ab2b-163">使用者可使用基本行動性和安全性登入支援存取控制的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-163">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="7ab2b-164">在裝置符合安全性設定之前，系統會封鎖他們存取應用程式中的 Microsoft 365 資源。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-164">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本行動及安全性合規性訊息":::

<span data-ttu-id="7ab2b-166">下列各節列出您可以用來協助保護和管理與 Microsoft 365 組織資源相連之行動裝置的原則設定。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-166">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="7ab2b-167">安全性設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-167">Security settings</span></span>

|<span data-ttu-id="7ab2b-168">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-168">**Setting name**</span></span>|<span data-ttu-id="7ab2b-169">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-169">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7ab2b-170">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-170">**Android 5 and later**</span></span>|<span data-ttu-id="7ab2b-171">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-171">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ab2b-172">需要密碼</span><span class="sxs-lookup"><span data-stu-id="7ab2b-172">Require a password</span></span>|<span data-ttu-id="7ab2b-173">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-173">Yes</span></span>|<span data-ttu-id="7ab2b-174">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-174">Yes</span></span>|<span data-ttu-id="7ab2b-175">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-175">Yes</span></span>|
|<span data-ttu-id="7ab2b-176">防止簡單密碼</span><span class="sxs-lookup"><span data-stu-id="7ab2b-176">Prevent simple password</span></span>|<span data-ttu-id="7ab2b-177">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-177">Yes</span></span>|<span data-ttu-id="7ab2b-178">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-178">No</span></span>|<span data-ttu-id="7ab2b-179">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-179">No</span></span>|
|<span data-ttu-id="7ab2b-180">需要一個數位元密碼</span><span class="sxs-lookup"><span data-stu-id="7ab2b-180">Require an alphanumeric password</span></span>|<span data-ttu-id="7ab2b-181">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-181">Yes</span></span>|<span data-ttu-id="7ab2b-182">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-182">No</span></span>|<span data-ttu-id="7ab2b-183">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-183">No</span></span>|
|<span data-ttu-id="7ab2b-184">密碼最小長度</span><span class="sxs-lookup"><span data-stu-id="7ab2b-184">Minimum password length</span></span> |<span data-ttu-id="7ab2b-185">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-185">Yes</span></span>|<span data-ttu-id="7ab2b-186">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-186">Yes</span></span>|<span data-ttu-id="7ab2b-187">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-187">Yes</span></span>|
|<span data-ttu-id="7ab2b-188">擦除裝置之前的登入失敗次數</span><span class="sxs-lookup"><span data-stu-id="7ab2b-188">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="7ab2b-189">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-189">Yes</span></span>|<span data-ttu-id="7ab2b-190">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-190">Yes</span></span>|<span data-ttu-id="7ab2b-191">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-191">Yes</span></span>|
|<span data-ttu-id="7ab2b-192">鎖定裝置之前的閒置分鐘</span><span class="sxs-lookup"><span data-stu-id="7ab2b-192">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="7ab2b-193">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-193">Yes</span></span>|<span data-ttu-id="7ab2b-194">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-194">Yes</span></span>|<span data-ttu-id="7ab2b-195">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-195">Yes</span></span>|
|<span data-ttu-id="7ab2b-196">密碼到期 (天) </span><span class="sxs-lookup"><span data-stu-id="7ab2b-196">Password expiration (days)</span></span> |<span data-ttu-id="7ab2b-197">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-197">Yes</span></span>|<span data-ttu-id="7ab2b-198">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-198">Yes</span></span>|<span data-ttu-id="7ab2b-199">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-199">Yes</span></span>|
|<span data-ttu-id="7ab2b-200">記住密碼歷程記錄，並防止重複使用</span><span class="sxs-lookup"><span data-stu-id="7ab2b-200">Remember password history and prevent reuse</span></span> |<span data-ttu-id="7ab2b-201">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-201">Yes</span></span>|<span data-ttu-id="7ab2b-202">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-202">Yes</span></span>|<span data-ttu-id="7ab2b-203">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-203">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="7ab2b-204">加密設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-204">Encryption settings</span></span>

|<span data-ttu-id="7ab2b-205">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-205">**Setting name**</span></span>|<span data-ttu-id="7ab2b-206">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-206">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7ab2b-207">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-207">**Android 5 and later**</span></span>|<span data-ttu-id="7ab2b-208">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-208">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ab2b-209">裝置<sup>1</sup>上需要資料加密</span><span class="sxs-lookup"><span data-stu-id="7ab2b-209">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="7ab2b-210">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-210">No</span></span>|<span data-ttu-id="7ab2b-211">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-211">Yes</span></span>|<span data-ttu-id="7ab2b-212">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-212">Yes</span></span>|

<span data-ttu-id="7ab2b-213"><sup>1</sup>使用 Samsung Knox，您也可以要求在儲存卡上加密。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-213"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="7ab2b-214">越獄中斷設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-214">Jail broken setting</span></span> 

|<span data-ttu-id="7ab2b-215">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-215">**Setting name**</span></span>|<span data-ttu-id="7ab2b-216">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-216">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7ab2b-217">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-217">**Android 5 and later**</span></span>|<span data-ttu-id="7ab2b-218">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-218">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ab2b-219">無法越獄中斷或根裝置</span><span class="sxs-lookup"><span data-stu-id="7ab2b-219">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="7ab2b-220">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-220">Yes</span></span>|<span data-ttu-id="7ab2b-221">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-221">Yes</span></span>|<span data-ttu-id="7ab2b-222">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-222">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="7ab2b-223">受管理的電子郵件設定檔選項</span><span class="sxs-lookup"><span data-stu-id="7ab2b-223">Managed email profile option</span></span> 

<span data-ttu-id="7ab2b-224">下列選項可以封鎖使用者在使用手動建立的電子郵件設定檔時存取其 Microsoft 365 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-224">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="7ab2b-225">IOS 裝置上的使用者必須先刪除其手動建立的電子郵件設定檔，才能存取其電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-225">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="7ab2b-226">在刪除設定檔之後，系統會自動在裝置上建立新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-226">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="7ab2b-227">如需使用者如何相容的相關指示，請參閱 [找到現有的電子郵件帳戶](/intune-user-help/existing-company-email-account-found)。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-227">For instructions on how end users can get compliant, see [An existing email account was found](/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="7ab2b-228">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-228">**Setting name**</span></span>|<span data-ttu-id="7ab2b-229">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-229">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7ab2b-230">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-230">**Android 5 and later**</span></span>|<span data-ttu-id="7ab2b-231">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-231">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ab2b-232">電子郵件設定檔已管理</span><span class="sxs-lookup"><span data-stu-id="7ab2b-232">Email profile is managed</span></span> |<span data-ttu-id="7ab2b-233">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-233">Yes</span></span>|<span data-ttu-id="7ab2b-234">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-234">No</span></span>|<span data-ttu-id="7ab2b-235">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-235">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="7ab2b-236">雲端設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-236">Cloud settings</span></span>

|<span data-ttu-id="7ab2b-237">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-237">**Setting name**</span></span>|<span data-ttu-id="7ab2b-238">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-238">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7ab2b-239">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-239">**Android 5 and later**</span></span>|<span data-ttu-id="7ab2b-240">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-240">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ab2b-241">需要加密備份</span><span class="sxs-lookup"><span data-stu-id="7ab2b-241">Require encrypted backup</span></span> |<span data-ttu-id="7ab2b-242">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-242">Yes</span></span>|<span data-ttu-id="7ab2b-243">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-243">No</span></span>|<span data-ttu-id="7ab2b-244">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-244">No</span></span>|
|<span data-ttu-id="7ab2b-245">封鎖雲端備份</span><span class="sxs-lookup"><span data-stu-id="7ab2b-245">Block cloud backup</span></span> |<span data-ttu-id="7ab2b-246">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-246">Yes</span></span>|<span data-ttu-id="7ab2b-247">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-247">No</span></span>|<span data-ttu-id="7ab2b-248">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-248">No</span></span>|
|<span data-ttu-id="7ab2b-249">封鎖檔同步處理</span><span class="sxs-lookup"><span data-stu-id="7ab2b-249">Block document synchronization</span></span> |<span data-ttu-id="7ab2b-250">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-250">Yes</span></span>|<span data-ttu-id="7ab2b-251">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-251">No</span></span>|<span data-ttu-id="7ab2b-252">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-252">No</span></span>|
|<span data-ttu-id="7ab2b-253">封鎖照片同步處理</span><span class="sxs-lookup"><span data-stu-id="7ab2b-253">Block photo synchronization</span></span>  |<span data-ttu-id="7ab2b-254">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-254">Yes</span></span>|<span data-ttu-id="7ab2b-255">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-255">No</span></span>|<span data-ttu-id="7ab2b-256">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-256">No</span></span>|
|<span data-ttu-id="7ab2b-257">允許 Google 備份</span><span class="sxs-lookup"><span data-stu-id="7ab2b-257">Allow Google backup</span></span>  |<span data-ttu-id="7ab2b-258">不適用</span><span class="sxs-lookup"><span data-stu-id="7ab2b-258">N/A</span></span>|<span data-ttu-id="7ab2b-259">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-259">No</span></span>|<span data-ttu-id="7ab2b-260">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-260">Yes</span></span>|
|<span data-ttu-id="7ab2b-261">允許 Google 帳戶自動同步處理</span><span class="sxs-lookup"><span data-stu-id="7ab2b-261">Allow Google account auto sync</span></span>  |<span data-ttu-id="7ab2b-262">不適用</span><span class="sxs-lookup"><span data-stu-id="7ab2b-262">N/A</span></span>|<span data-ttu-id="7ab2b-263">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-263">No</span></span>|<span data-ttu-id="7ab2b-264">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-264">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="7ab2b-265">系統設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-265">System settings</span></span>

|<span data-ttu-id="7ab2b-266">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-266">**Setting name**</span></span>|<span data-ttu-id="7ab2b-267">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-267">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7ab2b-268">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-268">**Android 5 and later**</span></span>|<span data-ttu-id="7ab2b-269">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-269">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ab2b-270">封鎖螢幕捕捉</span><span class="sxs-lookup"><span data-stu-id="7ab2b-270">Block screen capture</span></span> |<span data-ttu-id="7ab2b-271">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-271">Yes</span></span>|<span data-ttu-id="7ab2b-272">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-272">No</span></span>|<span data-ttu-id="7ab2b-273">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-273">Yes</span></span>|
|<span data-ttu-id="7ab2b-274">封鎖從裝置傳送診斷資料</span><span class="sxs-lookup"><span data-stu-id="7ab2b-274">Block sending diagnostic data from device</span></span> |<span data-ttu-id="7ab2b-275">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-275">Yes</span></span>|<span data-ttu-id="7ab2b-276">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-276">No</span></span>|<span data-ttu-id="7ab2b-277">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-277">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="7ab2b-278">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-278">Application settings</span></span>

|<span data-ttu-id="7ab2b-279">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-279">**Setting name**</span></span>|<span data-ttu-id="7ab2b-280">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-280">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7ab2b-281">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-281">**Android 5 and later**</span></span>|<span data-ttu-id="7ab2b-282">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-282">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ab2b-283">在裝置上封鎖影片會議</span><span class="sxs-lookup"><span data-stu-id="7ab2b-283">Block video conferences on device</span></span> |<span data-ttu-id="7ab2b-284">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-284">Yes</span></span>|<span data-ttu-id="7ab2b-285">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-285">No</span></span>|<span data-ttu-id="7ab2b-286">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-286">No</span></span>|
|<span data-ttu-id="7ab2b-287">封鎖對應用程式存放區的存取</span><span class="sxs-lookup"><span data-stu-id="7ab2b-287">Block access to application store</span></span> |<span data-ttu-id="7ab2b-288">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-288">Yes</span></span>|<span data-ttu-id="7ab2b-289">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-289">No</span></span>|<span data-ttu-id="7ab2b-290">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-290">Yes</span></span>|
|<span data-ttu-id="7ab2b-291">存取應用程式存放區時需要密碼</span><span class="sxs-lookup"><span data-stu-id="7ab2b-291">Require password when accessing application store</span></span> |<span data-ttu-id="7ab2b-292">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-292">No</span></span>|<span data-ttu-id="7ab2b-293">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-293">Yes</span></span>|<span data-ttu-id="7ab2b-294">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-294">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="7ab2b-295">裝置功能設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-295">Device capabilities settings</span></span>

|<span data-ttu-id="7ab2b-296">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-296">**Setting name**</span></span>|<span data-ttu-id="7ab2b-297">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-297">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7ab2b-298">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-298">**Android 5 and later**</span></span>|<span data-ttu-id="7ab2b-299">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-299">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ab2b-300">使用 [可移動儲存區] 封鎖連線</span><span class="sxs-lookup"><span data-stu-id="7ab2b-300">Block connection with removable storage</span></span> |<span data-ttu-id="7ab2b-301">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-301">Yes</span></span>|<span data-ttu-id="7ab2b-302">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-302">Yes</span></span>|<span data-ttu-id="7ab2b-303">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-303">No</span></span>|
|<span data-ttu-id="7ab2b-304">封鎖藍牙連接</span><span class="sxs-lookup"><span data-stu-id="7ab2b-304">Block Bluetooth connection</span></span> |<span data-ttu-id="7ab2b-305">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-305">Yes</span></span>|<span data-ttu-id="7ab2b-306">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-306">Yes</span></span>|<span data-ttu-id="7ab2b-307">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-307">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="7ab2b-308">其他設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-308">Additional settings</span></span>

<span data-ttu-id="7ab2b-309">您可以使用安全性 & 合規性中心 PowerShell Cmdlet 來設定下列其他原則設定。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-309">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="7ab2b-310">如需詳細資訊，請參閱 [安全性 & 規範中心 PowerShell](/powershell/exchange/scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-310">For more information, see [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="7ab2b-311">**設定名稱**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-311">**Setting name**</span></span>|<span data-ttu-id="7ab2b-312">**iOS 7.1 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-312">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7ab2b-313">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="7ab2b-313">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ab2b-314">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="7ab2b-314">CameraEnabled</span></span>|<span data-ttu-id="7ab2b-315">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-315">Yes</span></span>|<span data-ttu-id="7ab2b-316">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-316">Yes</span></span>|
|<span data-ttu-id="7ab2b-317">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="7ab2b-317">RegionRatings</span></span>|<span data-ttu-id="7ab2b-318">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-318">Yes</span></span>|<span data-ttu-id="7ab2b-319">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-319">No</span></span>|
|<span data-ttu-id="7ab2b-320">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="7ab2b-320">MoviesRatings</span></span>|<span data-ttu-id="7ab2b-321">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-321">Yes</span></span>|<span data-ttu-id="7ab2b-322">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-322">No</span></span>|
|<span data-ttu-id="7ab2b-323">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="7ab2b-323">TVShowsRating</span></span> |<span data-ttu-id="7ab2b-324">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-324">Yes</span></span>|<span data-ttu-id="7ab2b-325">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-325">No</span></span>|
|<span data-ttu-id="7ab2b-326">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="7ab2b-326">AppsRatings</span></span> |<span data-ttu-id="7ab2b-327">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-327">Yes</span></span>|<span data-ttu-id="7ab2b-328">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-328">No</span></span>|
|<span data-ttu-id="7ab2b-329">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="7ab2b-329">AllowVoiceDialing</span></span> |<span data-ttu-id="7ab2b-330">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-330">Yes</span></span>|<span data-ttu-id="7ab2b-331">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-331">No</span></span>|
|<span data-ttu-id="7ab2b-332">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="7ab2b-332">AllowVoiceAssistant</span></span> |<span data-ttu-id="7ab2b-333">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-333">Yes</span></span>|<span data-ttu-id="7ab2b-334">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-334">No</span></span>|
|<span data-ttu-id="7ab2b-335">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="7ab2b-335">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="7ab2b-336">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-336">Yes</span></span>|<span data-ttu-id="7ab2b-337">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-337">No</span></span>|
|<span data-ttu-id="7ab2b-338">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="7ab2b-338">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="7ab2b-339">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-339">Yes</span></span>|<span data-ttu-id="7ab2b-340">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-340">No</span></span>|
|<span data-ttu-id="7ab2b-341">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="7ab2b-341">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="7ab2b-342">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-342">Yes</span></span>|<span data-ttu-id="7ab2b-343">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-343">No</span></span>|
|<span data-ttu-id="7ab2b-344">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="7ab2b-344">PasswordQuality</span></span> |<span data-ttu-id="7ab2b-345">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-345">No</span></span>|<span data-ttu-id="7ab2b-346">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-346">Yes</span></span>|
|<span data-ttu-id="7ab2b-347">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="7ab2b-347">SystemSecurityTLS</span></span>  |<span data-ttu-id="7ab2b-348">是</span><span class="sxs-lookup"><span data-stu-id="7ab2b-348">Yes</span></span>|<span data-ttu-id="7ab2b-349">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-349">No</span></span>|
|<span data-ttu-id="7ab2b-350">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="7ab2b-350">WLANEnabled</span></span>  |<span data-ttu-id="7ab2b-351">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-351">No</span></span>|<span data-ttu-id="7ab2b-352">否</span><span class="sxs-lookup"><span data-stu-id="7ab2b-352">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="7ab2b-353">Windows 支援設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-353">Settings supported by Windows</span></span>

<span data-ttu-id="7ab2b-354">您可以將 Windows 10 裝置登記為行動裝置，以管理這些裝置。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-354">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="7ab2b-355">部署適用的原則之後，當使用者第一次使用內建的電子郵件應用程式存取其 Microsoft 365 電子郵件時，需要有 Windows 10 裝置的使用者才會註冊基本行動性和安全性 (需要 Azure AD premium 訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-355">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="7ab2b-356">以行動裝置註冊的 Windows 10 裝置支援下列設定。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-356">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="7ab2b-357">這些設定不會封鎖使用者存取 Microsoft 365 資源。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-357">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="7ab2b-358">安全性設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-358">Security settings</span></span>

- <span data-ttu-id="7ab2b-359">需要一個數位元密碼</span><span class="sxs-lookup"><span data-stu-id="7ab2b-359">Require an alphanumeric password</span></span>

- <span data-ttu-id="7ab2b-360">密碼最小長度</span><span class="sxs-lookup"><span data-stu-id="7ab2b-360">Minimum password length</span></span>

- <span data-ttu-id="7ab2b-361">擦除裝置之前的登入失敗次數</span><span class="sxs-lookup"><span data-stu-id="7ab2b-361">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="7ab2b-362">鎖定裝置之前的閒置分鐘</span><span class="sxs-lookup"><span data-stu-id="7ab2b-362">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="7ab2b-363">密碼到期 (天) </span><span class="sxs-lookup"><span data-stu-id="7ab2b-363">Password expiration (days)</span></span>

- <span data-ttu-id="7ab2b-364">記住密碼歷程記錄，並防止重複使用</span><span class="sxs-lookup"><span data-stu-id="7ab2b-364">Remember password history and prevent reuse</span></span>

>[!NOTE]
><span data-ttu-id="7ab2b-365">下列設定控制密碼只會控制本機 Windows 帳戶。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-365">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="7ab2b-366">透過「加入網域」或「Azure Active Directory」所提供的 Windows 帳戶，這些設定不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-366">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="7ab2b-367">系統設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-367">System settings</span></span>

<span data-ttu-id="7ab2b-368">封鎖從裝置發送診斷資料。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-368">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="7ab2b-369">其他設定</span><span class="sxs-lookup"><span data-stu-id="7ab2b-369">Additional settings</span></span>

<span data-ttu-id="7ab2b-370">您可以使用 PowerShell Cmdlet 來設定這些額外的原則設定：</span><span class="sxs-lookup"><span data-stu-id="7ab2b-370">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="7ab2b-371">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="7ab2b-371">AllowConvenienceLogon</span></span>

- <span data-ttu-id="7ab2b-372">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="7ab2b-372">UserAccountControlStatus</span></span>

- <span data-ttu-id="7ab2b-373">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="7ab2b-373">FirewallStatus</span></span>

- <span data-ttu-id="7ab2b-374">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="7ab2b-374">AutoUpdateStatus</span></span>

- <span data-ttu-id="7ab2b-375">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="7ab2b-375">AntiVirusStatus</span></span>

- <span data-ttu-id="7ab2b-376">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="7ab2b-376">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="7ab2b-377">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="7ab2b-377">SmartScreenEnabled</span></span>

- <span data-ttu-id="7ab2b-378">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="7ab2b-378">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="7ab2b-379">遠端清除行動裝置</span><span class="sxs-lookup"><span data-stu-id="7ab2b-379">Remotely wipe a mobile device</span></span>

<span data-ttu-id="7ab2b-380">如果裝置遺失或遭盜，您可以移除敏感的組織資料，並透過從安全性 & 相容性中心進行擦除，>**資料遺失防護**  >  **裝置管理**，來防止存取 Microsoft 365 組織資源。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-380">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="7ab2b-381">您可以進行選擇性擦除，只移除組織資料或完全清除，以刪除裝置中的所有資訊，並將其還原為出廠設定。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-381">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="7ab2b-382">如需詳細資訊，請參閱 [在基本行動及安全性中清除行動裝置](wipe-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="7ab2b-382">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="7ab2b-383">相關內容</span><span class="sxs-lookup"><span data-stu-id="7ab2b-383">Related content</span></span>

<span data-ttu-id="7ab2b-384">Microsoft 365 (篇文章[的基本行動性和安全性的概述](overview.md)) </span><span class="sxs-lookup"><span data-stu-id="7ab2b-384">[Overview of Basic Mobility and Security for Microsoft 365](overview.md) (article)</span></span>\
<span data-ttu-id="7ab2b-385">[在基本行動及安全性 (文章) 中建立裝置安全性原則](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7ab2b-385">[Create device security policies in Basic Mobility and Security](create-device-security-policies.md) (article)</span></span>