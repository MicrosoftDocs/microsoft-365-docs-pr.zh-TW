---
title: 疑難排解基本行動性和安全性
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: 嘗試這些步驟來追蹤基本行動性和安全性問題
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876849"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="1c120-103">疑難排解基本行動性和安全性</span><span class="sxs-lookup"><span data-stu-id="1c120-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="1c120-104">如果您嘗試在基本行動及安全性登錄裝置時遇到問題，請嘗試在這裡的步驟來追蹤問題。</span><span class="sxs-lookup"><span data-stu-id="1c120-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="1c120-105">如果一般步驟未修正問題，請參閱其中一個後續章節，其中包含您的裝置類型的特定步驟。</span><span class="sxs-lookup"><span data-stu-id="1c120-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="1c120-106">嘗試優先的步驟</span><span class="sxs-lookup"><span data-stu-id="1c120-106">Steps to try first</span></span>

<span data-ttu-id="1c120-107">若要開始，請檢查下列各項：</span><span class="sxs-lookup"><span data-stu-id="1c120-107">To start, check the following:</span></span>

- <span data-ttu-id="1c120-108">確定裝置尚未向其他行動裝置管理提供者（例如 Intune）註冊。</span><span class="sxs-lookup"><span data-stu-id="1c120-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="1c120-109">請確定裝置已設定為正確的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="1c120-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="1c120-110">切換至裝置上的不同 WIFI 或蜂窩網路。</span><span class="sxs-lookup"><span data-stu-id="1c120-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="1c120-111">針對 Android 或 iOS 裝置，請在裝置上卸載並重新安裝 Intune 公司入口網站應用程式。</span><span class="sxs-lookup"><span data-stu-id="1c120-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="1c120-112">iOS 電話或平板電腦</span><span class="sxs-lookup"><span data-stu-id="1c120-112">iOS phone or tablet</span></span>

- <span data-ttu-id="1c120-113">請確定您已設定 APNs 憑證。</span><span class="sxs-lookup"><span data-stu-id="1c120-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="1c120-114">如需詳細資訊，請參閱 [建立 iOS 裝置的 APNs 憑證](create-an-apns-certificate-for-ios-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="1c120-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="1c120-115">在 **設定**   >  **一般**   >  **設定檔 (或裝置管理)** 中，請確定尚未安裝管理設定檔。</span><span class="sxs-lookup"><span data-stu-id="1c120-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="1c120-116">如果是，請將其移除。</span><span class="sxs-lookup"><span data-stu-id="1c120-116">If it is, remove it.</span></span>

- <span data-ttu-id="1c120-117">如果您看到錯誤訊息「裝置未能註冊，請登入 Microsoft 365，並確定已將包含 Exchange Online 的授權指派給已登入裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="1c120-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="1c120-118">如果您看到錯誤訊息「設定檔安裝失敗」，請嘗試下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="1c120-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="1c120-119">請確定 Safari 是裝置上的預設瀏覽器，而且 cookie 並未停用。</span><span class="sxs-lookup"><span data-stu-id="1c120-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="1c120-120">重新開機裝置，然後流覽至 portal.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="1c120-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="1c120-121">使用您的 Microsoft 365 使用者識別碼和密碼登入，並嘗試手動安裝設定檔。</span><span class="sxs-lookup"><span data-stu-id="1c120-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="1c120-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="1c120-122">Windows RT</span></span>

- <span data-ttu-id="1c120-123">確定您的網域已在 Microsoft 365 中設定成使用基本行動性和安全性。</span><span class="sxs-lookup"><span data-stu-id="1c120-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="1c120-124">如需詳細資訊，請參閱 [設定基本行動性和安全性](set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="1c120-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="1c120-125">請確定使用者正在選擇 [ **開啟**]，   而非選擇 [ **加入**]。</span><span class="sxs-lookup"><span data-stu-id="1c120-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="1c120-126">Windows 10Pc</span><span class="sxs-lookup"><span data-stu-id="1c120-126">Windows 10 PC</span></span>

- <span data-ttu-id="1c120-127">確定您的網域已在 Microsoft 365 中設定成使用基本行動性和安全性。</span><span class="sxs-lookup"><span data-stu-id="1c120-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="1c120-128">如需詳細資訊，請參閱 [設定基本行動性和安全性](set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="1c120-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="1c120-129">除非您有 Azure Active Directory 進階版，否則請確定使用者只選擇 [ **登錄裝置管理**]，   而不是選擇 [ **連線**]。</span><span class="sxs-lookup"><span data-stu-id="1c120-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="1c120-130">Android 手機或平板電腦</span><span class="sxs-lookup"><span data-stu-id="1c120-130">Android phone or tablet</span></span>

- <span data-ttu-id="1c120-131">請確定裝置執行的是 Android 4.4 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="1c120-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="1c120-132">請確定 Chrome 是最新的，且設定為預設瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="1c120-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="1c120-133">如果您看到錯誤訊息「無法註冊此裝置」，請登入 Microsoft 365，並確定已將包含 Exchange Online 的授權指派給登入裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="1c120-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="1c120-134">檢查裝置上的通知區域，以查看是否有任何必要的使用者動作處於擱置狀態，如果是的話，請完成動作。</span><span class="sxs-lookup"><span data-stu-id="1c120-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>