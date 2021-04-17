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
ms.openlocfilehash: 79f8882e21f23e75d85813cde03260ef17adf246
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876106"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="7c8f1-104">Android 上適用於端點的 Microsoft Defender - 隱私權資訊</span><span class="sxs-lookup"><span data-stu-id="7c8f1-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="7c8f1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7c8f1-105">**Applies to:**</span></span>
- [<span data-ttu-id="7c8f1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7c8f1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7c8f1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7c8f1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7c8f1-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="7c8f1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7c8f1-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="7c8f1-110">適用于 Android 的 defender for Android 會從您設定的 Android 裝置收集資訊，並將其儲存在您擁有 Defender for Endpoint 的相同承租人中。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="7c8f1-111">收集此資訊有助於讓 iOS 安全、更新、如期執行，以及支援服務的情況下，取得端點的資訊。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-111">The information is collected to help keep Defender for Endpoint for iOS secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="7c8f1-112">如需資料儲存區的詳細資訊，請參閱 [Microsoft Defender Endpoint data storage and 隱私權](data-storage-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="7c8f1-113">收集的資訊可協助您保持 Android 的 Defender 安全、更新、如期執行，以及支援服務。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="7c8f1-114">必要資料</span><span class="sxs-lookup"><span data-stu-id="7c8f1-114">Required Data</span></span> 

<span data-ttu-id="7c8f1-115">必要的資料是由將 Defender 用於 Android 的端點工作如預期的情況所需的資料所組成。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-115">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="7c8f1-116">此資料對於服務的運作很重要，而且可以包含與使用者、組織、裝置及應用程式相關的資料。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-116">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="7c8f1-117">以下是所收集的資料類型清單：</span><span class="sxs-lookup"><span data-stu-id="7c8f1-117">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="7c8f1-118">應用程式資訊</span><span class="sxs-lookup"><span data-stu-id="7c8f1-118">App information</span></span>

<span data-ttu-id="7c8f1-119">裝置上 (APKs) 的 **惡意** Android 應用程式套件相關資訊，包括</span><span class="sxs-lookup"><span data-stu-id="7c8f1-119">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="7c8f1-120">安裝來源</span><span class="sxs-lookup"><span data-stu-id="7c8f1-120">Install source</span></span>
-  <span data-ttu-id="7c8f1-121">APK 的儲存位置 (檔案路徑) </span><span class="sxs-lookup"><span data-stu-id="7c8f1-121">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="7c8f1-122">安裝時間，APK 和許可權的大小</span><span class="sxs-lookup"><span data-stu-id="7c8f1-122">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="7c8f1-123">網頁/網路資訊</span><span class="sxs-lookup"><span data-stu-id="7c8f1-123">Web page / Network information</span></span>

- <span data-ttu-id="7c8f1-124">僅當偵測到惡意的連線或網頁時，才會完成網站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-124">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="7c8f1-125">連接資訊</span><span class="sxs-lookup"><span data-stu-id="7c8f1-125">Connection information</span></span>
- <span data-ttu-id="7c8f1-126">通訊協定類型 (例如 HTTP、HTTPS 等 ) </span><span class="sxs-lookup"><span data-stu-id="7c8f1-126">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="7c8f1-127">裝置和帳戶資訊</span><span class="sxs-lookup"><span data-stu-id="7c8f1-127">Device and account information</span></span>

- <span data-ttu-id="7c8f1-128">裝置資訊，例如日期 & time、Android 版本、OEM 模型、CPU 資訊和裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="7c8f1-128">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="7c8f1-129">裝置識別碼為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7c8f1-129">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="7c8f1-130">Wi-Fi 配接器 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="7c8f1-130">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="7c8f1-131">在第一次啟動裝置時， (Android 所產生的[ANDROID ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID)) </span><span class="sxs-lookup"><span data-stu-id="7c8f1-131">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="7c8f1-132">隨機產生的全域唯一識別碼 (GUID) </span><span class="sxs-lookup"><span data-stu-id="7c8f1-132">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="7c8f1-133">租使用者、裝置和使用者資訊</span><span class="sxs-lookup"><span data-stu-id="7c8f1-133">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="7c8f1-134">Azure Active Directory (AD) 裝置識別碼和 Azure 使用者 ID: 在 Azure Active Directory 上分別識別裝置，使用者。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-134">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="7c8f1-135">Azure 租使用者識別碼-識別您的組織在 Azure Active Directory 中的 GUID</span><span class="sxs-lookup"><span data-stu-id="7c8f1-135">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="7c8f1-136">Microsoft Defender ATP org ID-與裝置所屬之企業相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-136">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="7c8f1-137">可讓 Microsoft 識別問題是否會影響一組選擇的企業，以及受影響的企業數目</span><span class="sxs-lookup"><span data-stu-id="7c8f1-137">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="7c8f1-138">使用者主要名稱–使用者的電子郵件識別碼</span><span class="sxs-lookup"><span data-stu-id="7c8f1-138">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="7c8f1-139">產品和服務使用方式資料</span><span class="sxs-lookup"><span data-stu-id="7c8f1-139">Product and service usage data</span></span>

<span data-ttu-id="7c8f1-140">僅針對裝置上安裝的 Microsoft Defender for Endpoint 應用程式收集下列資訊。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-140">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="7c8f1-141">應用程式套件資訊，包括名稱、版本及應用程式升級狀態</span><span class="sxs-lookup"><span data-stu-id="7c8f1-141">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="7c8f1-142">在應用程式中執行的動作</span><span class="sxs-lookup"><span data-stu-id="7c8f1-142">Actions performed in the app</span></span>

-   <span data-ttu-id="7c8f1-143">威脅偵測資訊，例如威脅名稱、類別等。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-143">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="7c8f1-144">Android 產生的崩潰報告記錄</span><span class="sxs-lookup"><span data-stu-id="7c8f1-144">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="7c8f1-145">選用的資料</span><span class="sxs-lookup"><span data-stu-id="7c8f1-145">Optional Data</span></span>

<span data-ttu-id="7c8f1-146">選用的資料包括診斷資料和意見資料。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-146">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="7c8f1-147">選用的診斷資料為額外資料，可協助我們進行產品改善，並提供增強的資訊來協助我們偵測、診斷以及修正問題。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-147">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="7c8f1-148">選用的診斷資料包括：</span><span class="sxs-lookup"><span data-stu-id="7c8f1-148">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="7c8f1-149">應用程式、CPU 及網路使用量</span><span class="sxs-lookup"><span data-stu-id="7c8f1-149">App, CPU, and network usage</span></span>

-   <span data-ttu-id="7c8f1-150">從應用程式視點裝置的狀態，包括掃描狀態、掃描計時、授與的應用程式許可權，以及升級狀態</span><span class="sxs-lookup"><span data-stu-id="7c8f1-150">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="7c8f1-151">由系統管理員設定的功能</span><span class="sxs-lookup"><span data-stu-id="7c8f1-151">Features configured by the admin</span></span>

-   <span data-ttu-id="7c8f1-152">裝置上瀏覽器的基本資訊</span><span class="sxs-lookup"><span data-stu-id="7c8f1-152">Basic information about the browsers on the device</span></span>

<span data-ttu-id="7c8f1-153">透過使用者提供的應用程式意見反應收集 **回饋資料**</span><span class="sxs-lookup"><span data-stu-id="7c8f1-153">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="7c8f1-154">使用者的電子郵件地址（如果使用者選擇提供）</span><span class="sxs-lookup"><span data-stu-id="7c8f1-154">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="7c8f1-155">意見反應類型 (微笑、frown、構思) 和使用者提交的任何意見反應批註。</span><span class="sxs-lookup"><span data-stu-id="7c8f1-155">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
