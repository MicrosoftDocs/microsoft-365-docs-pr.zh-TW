---
title: Android 上適用於端點的 Microsoft Defender - 隱私權資訊
description: 隱私權控制，如何設定會影響隱私權的原則設定，以及在 Android 的 Microsoft Defender for Endpoint 中所收集的診斷資料資訊。
keywords: microsoft、defender、Microsoft Defender for Endpoint、android、隱私權、診斷
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c72e9491303d3f14ddb184e6a302a518643f709d
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694338"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="b13d1-104">Android 上適用於端點的 Microsoft Defender - 隱私權資訊</span><span class="sxs-lookup"><span data-stu-id="b13d1-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="b13d1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b13d1-105">**Applies to:**</span></span>
- [<span data-ttu-id="b13d1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b13d1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b13d1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b13d1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b13d1-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b13d1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b13d1-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b13d1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="b13d1-110">Android 上的 Defender for Android 會從您設定的 Android 裝置收集資訊，並將其儲存在您擁有 Defender for Endpoint 的相同承租人中。</span><span class="sxs-lookup"><span data-stu-id="b13d1-110">Defender for Endpoint on Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="b13d1-111">收集的資訊可協助您保持 Android 的 Defender 安全、更新、如期執行，以及支援服務。</span><span class="sxs-lookup"><span data-stu-id="b13d1-111">The information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="b13d1-112">如需資料儲存區的詳細資訊，請參閱 [Microsoft Defender Endpoint data storage and 隱私權](data-storage-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="b13d1-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="b13d1-113">收集的資訊可協助您保持 Android 的 Defender 安全、更新、如期執行，以及支援服務。</span><span class="sxs-lookup"><span data-stu-id="b13d1-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

<span data-ttu-id="b13d1-114">如需 Android 和 iOS 行動裝置上有關 Microsoft Defender for Endpoint 的常見隱私權問題的詳細資訊，請參閱 [Microsoft defender For endpoint 和您在 android 上的隱私權和 iOS 行動裝置](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)。</span><span class="sxs-lookup"><span data-stu-id="b13d1-114">For more information on most common privacy questions about Microsoft Defender for Endpoint on Android and iOS mobile devices, see [Microsoft Defender for Endpoint and your privacy on Android and iOS mobile devices](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a).</span></span>

## <a name="required-data"></a><span data-ttu-id="b13d1-115">必要資料</span><span class="sxs-lookup"><span data-stu-id="b13d1-115">Required Data</span></span> 

<span data-ttu-id="b13d1-116">必要的資料是由將 Defender 用於 Android 的端點工作如預期的情況所需的資料所組成。</span><span class="sxs-lookup"><span data-stu-id="b13d1-116">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="b13d1-117">此資料對於服務的運作很重要，而且可以包含與使用者、組織、裝置及應用程式相關的資料。</span><span class="sxs-lookup"><span data-stu-id="b13d1-117">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="b13d1-118">以下是所收集的資料類型清單：</span><span class="sxs-lookup"><span data-stu-id="b13d1-118">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="b13d1-119">應用程式資訊</span><span class="sxs-lookup"><span data-stu-id="b13d1-119">App information</span></span>

<span data-ttu-id="b13d1-120">裝置上 (APKs) 的 **惡意** Android 應用程式套件相關資訊，包括</span><span class="sxs-lookup"><span data-stu-id="b13d1-120">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="b13d1-121">安裝來源</span><span class="sxs-lookup"><span data-stu-id="b13d1-121">Install source</span></span>
-  <span data-ttu-id="b13d1-122">APK (檔案路徑) 的儲存體位置</span><span class="sxs-lookup"><span data-stu-id="b13d1-122">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="b13d1-123">安裝時間，APK 和許可權的大小</span><span class="sxs-lookup"><span data-stu-id="b13d1-123">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="b13d1-124">網頁/網路資訊</span><span class="sxs-lookup"><span data-stu-id="b13d1-124">Web page / Network information</span></span>

- <span data-ttu-id="b13d1-125">僅當偵測到惡意的連線或網頁時，才會完成網站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="b13d1-125">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="b13d1-126">連接資訊</span><span class="sxs-lookup"><span data-stu-id="b13d1-126">Connection information</span></span>
- <span data-ttu-id="b13d1-127">通訊協定類型 (例如 HTTP、HTTPS 等 ) </span><span class="sxs-lookup"><span data-stu-id="b13d1-127">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="b13d1-128">裝置和帳戶資訊</span><span class="sxs-lookup"><span data-stu-id="b13d1-128">Device and account information</span></span>

- <span data-ttu-id="b13d1-129">裝置資訊，例如日期 & time、Android 版本、OEM 模型、CPU 資訊和裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="b13d1-129">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="b13d1-130">裝置識別碼為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b13d1-130">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="b13d1-131">Wi-Fi 配接器 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="b13d1-131">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="b13d1-132">在第一次啟動裝置時， (Android 所產生的[ANDROID ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID)) </span><span class="sxs-lookup"><span data-stu-id="b13d1-132">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="b13d1-133">隨機產生的全域唯一識別碼 (GUID) </span><span class="sxs-lookup"><span data-stu-id="b13d1-133">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="b13d1-134">租使用者、裝置和使用者資訊</span><span class="sxs-lookup"><span data-stu-id="b13d1-134">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="b13d1-135">Azure Active Directory (AD) 裝置識別碼和 Azure 使用者 ID: 分別在 Azure Active Directory 上唯一識別裝置，使用者。</span><span class="sxs-lookup"><span data-stu-id="b13d1-135">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="b13d1-136">Azure 租使用者識別碼-識別您的組織 Azure Active Directory 內的 GUID</span><span class="sxs-lookup"><span data-stu-id="b13d1-136">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="b13d1-137">Microsoft Defender for Endpoint org ID-與裝置所屬之企業相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="b13d1-137">Microsoft Defender for Endpoint org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="b13d1-138">可讓 Microsoft 識別問題是否會影響一組選擇的企業，以及受影響的企業數目</span><span class="sxs-lookup"><span data-stu-id="b13d1-138">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="b13d1-139">使用者主要名稱–使用者的電子郵件識別碼</span><span class="sxs-lookup"><span data-stu-id="b13d1-139">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="b13d1-140">產品和服務使用方式資料</span><span class="sxs-lookup"><span data-stu-id="b13d1-140">Product and service usage data</span></span>

<span data-ttu-id="b13d1-141">僅針對裝置上安裝的 Microsoft Defender for Endpoint 應用程式收集下列資訊。</span><span class="sxs-lookup"><span data-stu-id="b13d1-141">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="b13d1-142">應用程式套件資訊，包括名稱、版本及應用程式升級狀態</span><span class="sxs-lookup"><span data-stu-id="b13d1-142">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="b13d1-143">在應用程式中執行的動作</span><span class="sxs-lookup"><span data-stu-id="b13d1-143">Actions performed in the app</span></span>

-   <span data-ttu-id="b13d1-144">威脅偵測資訊，例如威脅名稱、類別等。</span><span class="sxs-lookup"><span data-stu-id="b13d1-144">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="b13d1-145">Android 產生的崩潰報告記錄</span><span class="sxs-lookup"><span data-stu-id="b13d1-145">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="b13d1-146">選用的資料</span><span class="sxs-lookup"><span data-stu-id="b13d1-146">Optional Data</span></span>

<span data-ttu-id="b13d1-147">選用的資料包括診斷資料和意見資料。</span><span class="sxs-lookup"><span data-stu-id="b13d1-147">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="b13d1-148">選用的診斷資料為額外資料，可協助我們進行產品改善，並提供增強的資訊來協助我們偵測、診斷以及修正問題。</span><span class="sxs-lookup"><span data-stu-id="b13d1-148">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="b13d1-149">選用的診斷資料包括：</span><span class="sxs-lookup"><span data-stu-id="b13d1-149">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="b13d1-150">應用程式、CPU 及網路使用量</span><span class="sxs-lookup"><span data-stu-id="b13d1-150">App, CPU, and network usage</span></span>

-   <span data-ttu-id="b13d1-151">從應用程式視點裝置的狀態，包括掃描狀態、掃描計時、授與的應用程式許可權，以及升級狀態</span><span class="sxs-lookup"><span data-stu-id="b13d1-151">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="b13d1-152">由系統管理員設定的功能</span><span class="sxs-lookup"><span data-stu-id="b13d1-152">Features configured by the admin</span></span>

-   <span data-ttu-id="b13d1-153">裝置上瀏覽器的基本資訊</span><span class="sxs-lookup"><span data-stu-id="b13d1-153">Basic information about the browsers on the device</span></span>

<span data-ttu-id="b13d1-154">透過使用者提供的應用程式意見反應收集 **回饋資料**</span><span class="sxs-lookup"><span data-stu-id="b13d1-154">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="b13d1-155">使用者的電子郵件地址（如果使用者選擇提供）</span><span class="sxs-lookup"><span data-stu-id="b13d1-155">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="b13d1-156">意見反應類型 (微笑、frown、構思) 和使用者提交的任何意見反應批註。</span><span class="sxs-lookup"><span data-stu-id="b13d1-156">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
