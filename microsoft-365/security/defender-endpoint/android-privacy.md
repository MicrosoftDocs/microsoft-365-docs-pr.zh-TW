---
title: 適用于 Android 的 Microsoft Defender ATP-隱私權資訊
description: 隱私權控制，如何設定會影響隱私權的原則設定，以及 Microsoft Defender ATP for Android 中所收集診斷資料的相關資訊。
keywords: microsoft、defender、atp、android、隱私權、診斷
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
ms.openlocfilehash: d38d7a54aa860049e1968e5b92c801107bea0514
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687958"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="d58e9-104">Android 版上的 Microsoft Defender for Endpoint-隱私權資訊</span><span class="sxs-lookup"><span data-stu-id="d58e9-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="d58e9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d58e9-105">**Applies to:**</span></span>
- [<span data-ttu-id="d58e9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d58e9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d58e9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d58e9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d58e9-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d58e9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d58e9-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d58e9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="d58e9-110">適用于 Android 的 defender for Android 會從您設定的 Android 裝置收集資訊，並將其儲存在您擁有 Defender for Endpoint 的相同承租人中。</span><span class="sxs-lookup"><span data-stu-id="d58e9-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span>

<span data-ttu-id="d58e9-111">收集的資訊可協助您保持 Android 的 Defender 安全、更新、如期執行，以及支援服務。</span><span class="sxs-lookup"><span data-stu-id="d58e9-111">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="d58e9-112">必要資料</span><span class="sxs-lookup"><span data-stu-id="d58e9-112">Required Data</span></span> 

<span data-ttu-id="d58e9-113">必要的資料是由將 Defender 用於 Android 的端點工作如預期的情況所需的資料所組成。</span><span class="sxs-lookup"><span data-stu-id="d58e9-113">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="d58e9-114">此資料對於服務的運作很重要，而且可以包含與使用者、組織、裝置及應用程式相關的資料。</span><span class="sxs-lookup"><span data-stu-id="d58e9-114">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="d58e9-115">以下是所收集的資料類型清單：</span><span class="sxs-lookup"><span data-stu-id="d58e9-115">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="d58e9-116">應用程式資訊</span><span class="sxs-lookup"><span data-stu-id="d58e9-116">App information</span></span>

<span data-ttu-id="d58e9-117">裝置上 (APKs) 的 Android 應用程式套件相關資訊，包括</span><span class="sxs-lookup"><span data-stu-id="d58e9-117">Information about Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="d58e9-118">安裝來源</span><span class="sxs-lookup"><span data-stu-id="d58e9-118">Install source</span></span>
-  <span data-ttu-id="d58e9-119">APK 的儲存位置 (檔案路徑) </span><span class="sxs-lookup"><span data-stu-id="d58e9-119">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="d58e9-120">安裝時間，APK 和許可權的大小</span><span class="sxs-lookup"><span data-stu-id="d58e9-120">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="d58e9-121">網頁/網路資訊</span><span class="sxs-lookup"><span data-stu-id="d58e9-121">Web page / Network information</span></span>

- <span data-ttu-id="d58e9-122">支援的瀏覽器) 上的完整 URL (，當按一下時）</span><span class="sxs-lookup"><span data-stu-id="d58e9-122">Full URL (on supported browsers), when clicked</span></span>
- <span data-ttu-id="d58e9-123">連接資訊</span><span class="sxs-lookup"><span data-stu-id="d58e9-123">Connection information</span></span>
- <span data-ttu-id="d58e9-124">通訊協定類型 (例如 HTTP、HTTPS 等 ) </span><span class="sxs-lookup"><span data-stu-id="d58e9-124">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="d58e9-125">裝置和帳戶資訊</span><span class="sxs-lookup"><span data-stu-id="d58e9-125">Device and account information</span></span>

- <span data-ttu-id="d58e9-126">裝置資訊，例如日期 & time、Android 版本、OEM 模型、CPU 資訊和裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="d58e9-126">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="d58e9-127">裝置識別碼為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d58e9-127">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="d58e9-128">Wi-Fi 配接器 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="d58e9-128">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="d58e9-129">在第一次啟動裝置時， (Android 所產生的[ANDROID ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID)) </span><span class="sxs-lookup"><span data-stu-id="d58e9-129">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="d58e9-130">隨機產生的全域唯一識別碼 (GUID) </span><span class="sxs-lookup"><span data-stu-id="d58e9-130">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="d58e9-131">租使用者、裝置和使用者資訊</span><span class="sxs-lookup"><span data-stu-id="d58e9-131">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="d58e9-132">Azure Active Directory (AD) 裝置識別碼和 Azure 使用者 ID: 在 Azure Active Directory 上分別識別裝置，使用者。</span><span class="sxs-lookup"><span data-stu-id="d58e9-132">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="d58e9-133">Azure 租使用者識別碼-識別您的組織在 Azure Active Directory 中的 GUID</span><span class="sxs-lookup"><span data-stu-id="d58e9-133">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="d58e9-134">Microsoft Defender ATP org ID-與裝置所屬之企業相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d58e9-134">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="d58e9-135">可讓 Microsoft 識別問題是否會影響一組選擇的企業，以及受影響的企業數目</span><span class="sxs-lookup"><span data-stu-id="d58e9-135">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="d58e9-136">使用者主要名稱–使用者的電子郵件識別碼</span><span class="sxs-lookup"><span data-stu-id="d58e9-136">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="d58e9-137">產品和服務使用方式資料</span><span class="sxs-lookup"><span data-stu-id="d58e9-137">Product and service usage data</span></span>
-   <span data-ttu-id="d58e9-138">應用程式套件資訊，包括名稱、版本及應用程式升級狀態</span><span class="sxs-lookup"><span data-stu-id="d58e9-138">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="d58e9-139">在應用程式中執行的動作</span><span class="sxs-lookup"><span data-stu-id="d58e9-139">Actions performed in the app</span></span>

-   <span data-ttu-id="d58e9-140">威脅偵測資訊，例如威脅名稱、類別等。</span><span class="sxs-lookup"><span data-stu-id="d58e9-140">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="d58e9-141">Android 產生的崩潰報告記錄</span><span class="sxs-lookup"><span data-stu-id="d58e9-141">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="d58e9-142">選用的資料</span><span class="sxs-lookup"><span data-stu-id="d58e9-142">Optional Data</span></span>

<span data-ttu-id="d58e9-143">選用的資料包括診斷資料和意見資料。</span><span class="sxs-lookup"><span data-stu-id="d58e9-143">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="d58e9-144">選用的診斷資料為額外資料，可協助我們進行產品改善，並提供增強的資訊來協助我們偵測、診斷以及修正問題。</span><span class="sxs-lookup"><span data-stu-id="d58e9-144">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="d58e9-145">選用的診斷資料包括：</span><span class="sxs-lookup"><span data-stu-id="d58e9-145">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="d58e9-146">應用程式、CPU 及網路使用量</span><span class="sxs-lookup"><span data-stu-id="d58e9-146">App, CPU, and network usage</span></span>

-   <span data-ttu-id="d58e9-147">從應用程式視點裝置的狀態，包括掃描狀態、掃描計時、授與的應用程式許可權，以及升級狀態</span><span class="sxs-lookup"><span data-stu-id="d58e9-147">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="d58e9-148">由系統管理員設定的功能</span><span class="sxs-lookup"><span data-stu-id="d58e9-148">Features configured by the admin</span></span>

-   <span data-ttu-id="d58e9-149">裝置上瀏覽器的基本資訊</span><span class="sxs-lookup"><span data-stu-id="d58e9-149">Basic information about the browsers on the device</span></span>

<span data-ttu-id="d58e9-150">透過使用者提供的應用程式意見反應收集 **回饋資料**</span><span class="sxs-lookup"><span data-stu-id="d58e9-150">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="d58e9-151">使用者的電子郵件地址（如果使用者選擇提供）</span><span class="sxs-lookup"><span data-stu-id="d58e9-151">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="d58e9-152">意見反應類型 (微笑、frown、構思) 和使用者提交的任何意見反應批註。</span><span class="sxs-lookup"><span data-stu-id="d58e9-152">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
