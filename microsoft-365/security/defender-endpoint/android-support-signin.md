---
title: 在 Android 上疑難排解 Microsoft Defender for Endpoint 上的問題
description: 在 Android 上疑難排解 Microsoft Defender for Endpoint 的問題
keywords: microsoft，defender，Microsoft Defender for Endpoint，mde，android，cloud，connectivity，通訊
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246353"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="2fbc3-104">Android 上 Microsoft Defender for Endpoint 的問題疑難排解</span><span class="sxs-lookup"><span data-stu-id="2fbc3-104">Troubleshooting issues on Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2fbc3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2fbc3-105">**Applies to:**</span></span>
- [<span data-ttu-id="2fbc3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2fbc3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2fbc3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2fbc3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2fbc3-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="2fbc3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2fbc3-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="2fbc3-110">當您上架裝置時，您可能會在安裝應用程式之後看到 [登入] 問題。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="2fbc3-111">在上架期間，您在裝置上安裝應用程式之後，您可能會遇到登入問題。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="2fbc3-112">本文提供的解決方案可協助您解決登錄問題。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="2fbc3-113">登入失敗-未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="2fbc3-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="2fbc3-114">登 \**入失敗：未\*\*\*預期的錯誤，請稍後再試*</span><span class="sxs-lookup"><span data-stu-id="2fbc3-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![[登入失敗] 錯誤的圖像意外錯誤](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="2fbc3-116">**消息：**</span><span class="sxs-lookup"><span data-stu-id="2fbc3-116">**Message:**</span></span>

<span data-ttu-id="2fbc3-117">意外錯誤，請稍後再試</span><span class="sxs-lookup"><span data-stu-id="2fbc3-117">Unexpected error, try later</span></span>

<span data-ttu-id="2fbc3-118">**原因：**</span><span class="sxs-lookup"><span data-stu-id="2fbc3-118">**Cause:**</span></span>

<span data-ttu-id="2fbc3-119">您的裝置上安裝了舊版本的「Microsoft Authenticator」應用程式。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="2fbc3-120">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="2fbc3-120">**Solution:**</span></span>

<span data-ttu-id="2fbc3-121">從 Google Play Store 安裝最新版本和[Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) ，然後再試一次</span><span class="sxs-lookup"><span data-stu-id="2fbc3-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="2fbc3-122">登入失敗-不正確授權</span><span class="sxs-lookup"><span data-stu-id="2fbc3-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="2fbc3-123">登 **入失敗：** *不正確授權，請洽詢系統管理員*</span><span class="sxs-lookup"><span data-stu-id="2fbc3-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![登入失敗的影像請洽詢系統管理員](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="2fbc3-125">**訊息：** *授權無效，請與系統管理員聯繫*</span><span class="sxs-lookup"><span data-stu-id="2fbc3-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="2fbc3-126">**原因：**</span><span class="sxs-lookup"><span data-stu-id="2fbc3-126">**Cause:**</span></span>

<span data-ttu-id="2fbc3-127">您沒有指派 Microsoft 365 授權，或您的組織沒有 Microsoft 365 企業版訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="2fbc3-128">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="2fbc3-128">**Solution:**</span></span>

<span data-ttu-id="2fbc3-129">請與您的系統管理員聯繫以取得協助。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-129">Contact your administrator for help.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="2fbc3-130">報告不安全的網站</span><span class="sxs-lookup"><span data-stu-id="2fbc3-130">Report unsafe site</span></span>

<span data-ttu-id="2fbc3-131">網路釣魚網站會為了取得您的個人或財務資訊，模仿可信的網站。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-131">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="2fbc3-132">如果您想要報告可能是網路釣魚網站的網站，請造訪 [ [提供有關網路保護的意見](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 反應] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-132">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="2fbc3-133">有些 OEM 裝置上沒有封鎖網頁網路頁面</span><span class="sxs-lookup"><span data-stu-id="2fbc3-133">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="2fbc3-134">**適用于：** 僅限特定 Oem</span><span class="sxs-lookup"><span data-stu-id="2fbc3-134">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="2fbc3-135">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="2fbc3-135">**Xiaomi**</span></span>

<span data-ttu-id="2fbc3-136">在某些 Xiaomi 裝置上，不會封鎖由 Defender for Android 的 Endpoint 所偵測到的網路釣魚和有害 web 威脅。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-136">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="2fbc3-137">下列功能在這些裝置上無法運作。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-137">The following functionality doesn't work on these devices.</span></span>

![網站的圖像報告為不安全](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="2fbc3-139">**原因：**</span><span class="sxs-lookup"><span data-stu-id="2fbc3-139">**Cause:**</span></span>

<span data-ttu-id="2fbc3-140">Xiaomi 裝置包含新的許可權模型。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-140">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="2fbc3-141">這可讓 Android 的 Defender Endpoint 在後臺執行時，不顯示快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-141">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="2fbc3-142">Xiaomi 裝置許可權：「在後臺執行時顯示快顯視窗」。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-142">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![快顯視窗的圖像設定](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="2fbc3-144">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="2fbc3-144">**Solution:**</span></span>

<span data-ttu-id="2fbc3-145">在 Xiaomi 裝置上啟用必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-145">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="2fbc3-146">在背景中執行時，顯示快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="2fbc3-146">Display pop-up windows while running in the background.</span></span>
