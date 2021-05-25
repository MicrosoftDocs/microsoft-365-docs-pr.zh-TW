---
title: Mac 上的 Microsoft Defender for Endpoint 的隱私權
description: 隱私權控制，如何設定會影響隱私權的原則設定，以及在 Mac 上為端點所收集之診斷資料的相關資訊。
keywords: microsoft、defender、Microsoft Defender for Endpoint、mac、隱私權、診斷
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2884ffc695abc1c6b4b5be9bbd7c9ad37ad05439
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651293"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="0a8a7-104">macOS 上的 Microsoft Defender for Endpoint 隱私權</span><span class="sxs-lookup"><span data-stu-id="0a8a7-104">Privacy for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0a8a7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0a8a7-105">**Applies to:**</span></span>
- [<span data-ttu-id="0a8a7-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0a8a7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0a8a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a8a7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0a8a7-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="0a8a7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0a8a7-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="0a8a7-110">Microsoft 致力於為您提供您所需的資訊和控制項，讓您選擇在 macOS 上使用 Microsoft Defender 做為端點時，如何收集和使用資料。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="0a8a7-111">本主題說明產品內可用的隱私權控制，如何使用原則設定管理這些控制項，以及收集的資料事件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="0a8a7-112">Microsoft Defender for Endpoint on macOS 的隱私權控制的概覽</span><span class="sxs-lookup"><span data-stu-id="0a8a7-112">Overview of privacy controls in Microsoft Defender for Endpoint on macOS</span></span>

<span data-ttu-id="0a8a7-113">本節說明 Microsoft Defender for Endpoint on macOS 所收集之不同資料類型的隱私權控制。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-113">This section describes the privacy controls for the different types of data collected by Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="0a8a7-114">診斷資料</span><span class="sxs-lookup"><span data-stu-id="0a8a7-114">Diagnostic data</span></span>

<span data-ttu-id="0a8a7-115">診斷資料是用來保持 Microsoft Defender 的端點安全且最新、偵測、診斷與修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-115">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="0a8a7-116">某些診斷資料為必要，而某些診斷資料為選用。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="0a8a7-117">我們可讓您選擇要透過隱私權控制 (如組織的原則設定) 向我們傳送必要或選用的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="0a8a7-118">Microsoft Defender for Endpoint client 軟體有兩個層級的診斷資料，可供您選擇：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-118">There are two levels of diagnostic data for Microsoft Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="0a8a7-119">**必要**：必要的資料，以協助保持 Microsoft Defender 在其上安裝的裝置上具有最新的端點安全、最新和執行。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-119">**Required**: The minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="0a8a7-120">**選用**：其他資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷和修正問題。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="0a8a7-121">根據預設，只會將所需的診斷資料傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="0a8a7-122">雲端已傳送保護資料</span><span class="sxs-lookup"><span data-stu-id="0a8a7-122">Cloud delivered protection data</span></span>

<span data-ttu-id="0a8a7-123">雲端提供的保護功能可讓您在存取雲端中的最新保護資料時，提供更快且更快速的保護。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="0a8a7-124">啟用雲端傳送保護服務是選用的選項，但是強烈建議您這麼做，因為它會針對您的端點和網路上的惡意程式碼提供重要防護。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="0a8a7-125">資料範例</span><span class="sxs-lookup"><span data-stu-id="0a8a7-125">Sample data</span></span>

<span data-ttu-id="0a8a7-126">範例資料是用來改善產品的保護功能，方法是傳送 Microsoft 可疑的範例，使其能夠進行分析。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="0a8a7-127">啟用自動範例提交是選用的。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="0a8a7-128">啟用此功能且收集的範例可能包含個人資訊時，系統會提示使用者同意。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-128">When this feature is enabled and the sample that is collected is likely to contain personal information, the user is prompted for consent.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="0a8a7-129">使用原則設定管理隱私權控制項</span><span class="sxs-lookup"><span data-stu-id="0a8a7-129">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="0a8a7-130">如果您是 IT 管理員，您可能會想要在企業層級設定這些控制項。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-130">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="0a8a7-131">在 [macOS 上的 Microsoft Defender For Endpoint 的 [設定偏好設定](mac-preferences.md)] 中，詳細說明上述各節所述各類資料的隱私權。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-131">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="0a8a7-132">就像任何新的原則設定一樣，您應該在有限的受控環境中仔細測試這些設定，以確保您設定的設定在您的組織中更廣泛地實施原則設定之前具有適當的效果。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-132">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="0a8a7-133">診斷資料事件</span><span class="sxs-lookup"><span data-stu-id="0a8a7-133">Diagnostic data events</span></span>

<span data-ttu-id="0a8a7-134">本節說明什麼是被視為必要的診斷資料，以及哪些專案會被視為選用的診斷資料，以及所收集的事件及欄位的描述。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-134">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="0a8a7-135">所有事件通用的資料欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-135">Data fields that are common for all events</span></span>
<span data-ttu-id="0a8a7-136">有一些事件的相關資訊是所有事件通用，而不論類別或資料子類型為何。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-136">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="0a8a7-137">下欄欄位對於所有事件都是常見的：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-137">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="0a8a7-138">欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-138">Field</span></span>                   | <span data-ttu-id="0a8a7-139">描述</span><span class="sxs-lookup"><span data-stu-id="0a8a7-139">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="0a8a7-140">平台</span><span class="sxs-lookup"><span data-stu-id="0a8a7-140">platform</span></span>                | <span data-ttu-id="0a8a7-141">應用程式執行所在平臺的廣泛分類。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-141">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="0a8a7-142">可讓 Microsoft 識別可能發生問題的平臺，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-142">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="0a8a7-143">machine_guid</span><span class="sxs-lookup"><span data-stu-id="0a8a7-143">machine_guid</span></span>            | <span data-ttu-id="0a8a7-144">與裝置相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-144">Unique identifier associated with the device.</span></span> <span data-ttu-id="0a8a7-145">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-145">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="0a8a7-146">sense_guid</span><span class="sxs-lookup"><span data-stu-id="0a8a7-146">sense_guid</span></span>              | <span data-ttu-id="0a8a7-147">與裝置相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-147">Unique identifier associated with the device.</span></span> <span data-ttu-id="0a8a7-148">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-148">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="0a8a7-149">org_id</span><span class="sxs-lookup"><span data-stu-id="0a8a7-149">org_id</span></span>                  | <span data-ttu-id="0a8a7-150">與裝置所屬之企業相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-150">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="0a8a7-151">可讓 Microsoft 識別問題是否會影響一組選擇的企業，以及受影響的企業數目。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-151">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="0a8a7-152">主機 名</span><span class="sxs-lookup"><span data-stu-id="0a8a7-152">hostname</span></span>                | <span data-ttu-id="0a8a7-153">本機裝置名稱 (，但沒有 DNS 尾碼) 。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-153">Local device name (without DNS suffix).</span></span> <span data-ttu-id="0a8a7-154">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-154">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="0a8a7-155">product_guid</span><span class="sxs-lookup"><span data-stu-id="0a8a7-155">product_guid</span></span>            | <span data-ttu-id="0a8a7-156">產品的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-156">Unique identifier of the product.</span></span> <span data-ttu-id="0a8a7-157">可讓 Microsoft 區分影響不同產品風格的問題。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-157">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="0a8a7-158">app_version</span><span class="sxs-lookup"><span data-stu-id="0a8a7-158">app_version</span></span>             | <span data-ttu-id="0a8a7-159">MacOS 應用程式上的 Microsoft Defender for Endpoint 版本。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-159">Version of the Microsoft Defender for Endpoint on macOS application.</span></span> <span data-ttu-id="0a8a7-160">可讓 Microsoft 找出顯示問題的產品版本，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-160">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="0a8a7-161">sig_version</span><span class="sxs-lookup"><span data-stu-id="0a8a7-161">sig_version</span></span>             | <span data-ttu-id="0a8a7-162">安全性情報資料庫的版本。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-162">Version of security intelligence database.</span></span> <span data-ttu-id="0a8a7-163">可讓 Microsoft 找出顯示問題的安全性情報版本，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-163">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="0a8a7-164">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="0a8a7-164">supported_compressions</span></span>  | <span data-ttu-id="0a8a7-165">例如，應用程式支援的壓縮演算法清單 `['gzip']` 。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-165">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="0a8a7-166">可讓 Microsoft 瞭解哪些類型的 compressions 可以在與應用程式通訊時使用。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-166">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="0a8a7-167">release_ring</span><span class="sxs-lookup"><span data-stu-id="0a8a7-167">release_ring</span></span>            | <span data-ttu-id="0a8a7-168">裝置與 (相關聯的環，例如，內幕人士快、內幕人士緩慢、實際執行) 。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-168">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="0a8a7-169">可讓 Microsoft 識別可能發生問題的發行環，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-169">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |


### <a name="required-diagnostic-data"></a><span data-ttu-id="0a8a7-170">必要診斷資料</span><span class="sxs-lookup"><span data-stu-id="0a8a7-170">Required diagnostic data</span></span>

<span data-ttu-id="0a8a7-171">必要的 **診斷資料** 是必要的最少資料，以協助保持 Microsoft Defender 在安裝所在裝置上的「端點安全」、「最新」和「如期」執行。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-171">**Required diagnostic data** is the minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="0a8a7-172">必要的診斷資料可協助識別可能與裝置或軟體設定有關的 Microsoft Defender 端點相關問題。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-172">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="0a8a7-173">例如，它可協助判斷在特定作業系統版本、新引進的功能，或是停用某些 Microsoft Defender for Endpoint 功能時，Microsoft Defender for Endpoint 功能是否會頻繁地崩潰。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-173">For example, it can help determine if a Microsoft Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Microsoft Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="0a8a7-174">必要的診斷資料可協助 Microsoft 偵測、診斷及修正這些問題，以加快對使用者或組織的影響。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-174">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="0a8a7-175">軟體安裝和庫存資料事件</span><span class="sxs-lookup"><span data-stu-id="0a8a7-175">Software setup and inventory data events</span></span>

<span data-ttu-id="0a8a7-176">**Microsoft Defender for Endpoint 安裝/卸載**</span><span class="sxs-lookup"><span data-stu-id="0a8a7-176">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="0a8a7-177">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-177">The following fields are collected:</span></span>

| <span data-ttu-id="0a8a7-178">欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-178">Field</span></span>            | <span data-ttu-id="0a8a7-179">描述</span><span class="sxs-lookup"><span data-stu-id="0a8a7-179">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="0a8a7-180">correlation_id</span><span class="sxs-lookup"><span data-stu-id="0a8a7-180">correlation_id</span></span>   | <span data-ttu-id="0a8a7-181">與安裝相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-181">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="0a8a7-182">版本</span><span class="sxs-lookup"><span data-stu-id="0a8a7-182">version</span></span>          | <span data-ttu-id="0a8a7-183">套件的版本。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-183">Version of the package.</span></span> |
| <span data-ttu-id="0a8a7-184">嚴重性</span><span class="sxs-lookup"><span data-stu-id="0a8a7-184">severity</span></span>         | <span data-ttu-id="0a8a7-185">郵件的嚴重性 (例如，) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-185">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="0a8a7-186">code</span><span class="sxs-lookup"><span data-stu-id="0a8a7-186">code</span></span>             | <span data-ttu-id="0a8a7-187">描述工序的程式碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-187">Code that describes the operation.</span></span> |
| <span data-ttu-id="0a8a7-188">文字</span><span class="sxs-lookup"><span data-stu-id="0a8a7-188">text</span></span>             | <span data-ttu-id="0a8a7-189">產品安裝相關的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-189">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="0a8a7-190">**適用於端點的 Microsoft Defender 設定**</span><span class="sxs-lookup"><span data-stu-id="0a8a7-190">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="0a8a7-191">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-191">The following fields are collected:</span></span>

| <span data-ttu-id="0a8a7-192">欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-192">Field</span></span>                                               | <span data-ttu-id="0a8a7-193">描述</span><span class="sxs-lookup"><span data-stu-id="0a8a7-193">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="0a8a7-194">antivirus_engine antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="0a8a7-194">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="0a8a7-195">是否已在裝置上啟用即時保護功能。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-195">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="0a8a7-196">antivirus_engine antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="0a8a7-196">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="0a8a7-197">是否已在裝置上啟用被動式模式。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-197">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="0a8a7-198">cloud_service。 enabled</span><span class="sxs-lookup"><span data-stu-id="0a8a7-198">cloud_service.enabled</span></span>                               | <span data-ttu-id="0a8a7-199">是否已在裝置上啟用雲端已傳送保護功能。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-199">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="0a8a7-200">cloud_service。超時</span><span class="sxs-lookup"><span data-stu-id="0a8a7-200">cloud_service.timeout</span></span>                               | <span data-ttu-id="0a8a7-201">當應用程式使用 Microsoft Defender for Endpoint cloud 進行通訊時超時。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-201">Time out when the application communicates with the Microsoft Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="0a8a7-202">cloud_service cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="0a8a7-202">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="0a8a7-203">產品傳送至雲端的連續心跳之間的間隔。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-203">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="0a8a7-204">cloud_service cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="0a8a7-204">cloud_service.service_uri</span></span>                           | <span data-ttu-id="0a8a7-205">用於與雲端通訊的 URI。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-205">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="0a8a7-206">cloud_service cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="0a8a7-206">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="0a8a7-207">裝置的診斷層級 (必要，選用) 。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-207">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="0a8a7-208">cloud_service cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="0a8a7-208">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="0a8a7-209">是否已開啟自動範例提交。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-209">Whether automatic sample submission is turned on or not.</span></span> |
| <span data-ttu-id="0a8a7-210">cloud_service cloud_service.automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="0a8a7-210">cloud_service.automatic_definition_update_enabled</span></span>   | <span data-ttu-id="0a8a7-211">是否已開啟自動定義更新。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-211">Whether automatic definition update is turned on or not.</span></span> |
| <span data-ttu-id="0a8a7-212">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="0a8a7-212">edr.early_preview</span></span>                                   | <span data-ttu-id="0a8a7-213">裝置是否應該執行 EDR 早期預覽功能。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-213">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="0a8a7-214">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="0a8a7-214">edr.group_id</span></span>                                        | <span data-ttu-id="0a8a7-215">偵測及回應元件所使用的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-215">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="0a8a7-216">edr 標記</span><span class="sxs-lookup"><span data-stu-id="0a8a7-216">edr.tags</span></span>                                            | <span data-ttu-id="0a8a7-217">使用者定義的標記。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-217">User-defined tags.</span></span> |
| <span data-ttu-id="0a8a7-218">功能。 \[選用功能名稱\]</span><span class="sxs-lookup"><span data-stu-id="0a8a7-218">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="0a8a7-219">預覽功能的清單，及其是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-219">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="0a8a7-220">產品和服務使用資料事件</span><span class="sxs-lookup"><span data-stu-id="0a8a7-220">Product and service usage data events</span></span>

<span data-ttu-id="0a8a7-221">**安全性智慧更新報告**</span><span class="sxs-lookup"><span data-stu-id="0a8a7-221">**Security intelligence update report**</span></span>

<span data-ttu-id="0a8a7-222">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-222">The following fields are collected:</span></span>

| <span data-ttu-id="0a8a7-223">欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-223">Field</span></span>            | <span data-ttu-id="0a8a7-224">描述</span><span class="sxs-lookup"><span data-stu-id="0a8a7-224">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="0a8a7-225">from_version</span><span class="sxs-lookup"><span data-stu-id="0a8a7-225">from_version</span></span>     | <span data-ttu-id="0a8a7-226">原始安全性智慧版本。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-226">Original security intelligence version.</span></span> |
| <span data-ttu-id="0a8a7-227">to_version</span><span class="sxs-lookup"><span data-stu-id="0a8a7-227">to_version</span></span>       | <span data-ttu-id="0a8a7-228">新的安全性智慧版本。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-228">New security intelligence version.</span></span> |
| <span data-ttu-id="0a8a7-229">地位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-229">status</span></span>           | <span data-ttu-id="0a8a7-230">表明成功或失敗之更新的狀態。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-230">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="0a8a7-231">using_proxy</span><span class="sxs-lookup"><span data-stu-id="0a8a7-231">using_proxy</span></span>      | <span data-ttu-id="0a8a7-232">是否已透過 proxy 進行更新。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-232">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="0a8a7-233">錯誤</span><span class="sxs-lookup"><span data-stu-id="0a8a7-233">error</span></span>            | <span data-ttu-id="0a8a7-234">如果更新失敗，則為錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-234">Error code if the update failed.</span></span> |
| <span data-ttu-id="0a8a7-235">reason</span><span class="sxs-lookup"><span data-stu-id="0a8a7-235">reason</span></span>           | <span data-ttu-id="0a8a7-236">更新的歸檔時的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-236">Error message if the updated filed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="0a8a7-237">產品和服務效能資料事件</span><span class="sxs-lookup"><span data-stu-id="0a8a7-237">Product and service performance data events</span></span>

<span data-ttu-id="0a8a7-238">**非預期的應用程式結束 (當機)**</span><span class="sxs-lookup"><span data-stu-id="0a8a7-238">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="0a8a7-239">在應用程式意外退出時，收集系統資訊和應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-239">Collects system information and the state of an application when an application unexpectedly exits.</span></span>

<span data-ttu-id="0a8a7-240">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-240">The following fields are collected:</span></span>

| <span data-ttu-id="0a8a7-241">欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-241">Field</span></span>                          | <span data-ttu-id="0a8a7-242">描述</span><span class="sxs-lookup"><span data-stu-id="0a8a7-242">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="0a8a7-243">v1_crash_count</span><span class="sxs-lookup"><span data-stu-id="0a8a7-243">v1_crash_count</span></span>                 | <span data-ttu-id="0a8a7-244">在用戶端電腦上，V1 引擎處理常式每小時崩潰的次數</span><span class="sxs-lookup"><span data-stu-id="0a8a7-244">Number of times V1 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="0a8a7-245">v2_crash_count</span><span class="sxs-lookup"><span data-stu-id="0a8a7-245">v2_crash_count</span></span>                 | <span data-ttu-id="0a8a7-246">在用戶端電腦上，V2 引擎處理常式每小時崩潰的次數</span><span class="sxs-lookup"><span data-stu-id="0a8a7-246">Number of times V2 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="0a8a7-247">EDR_crash_count</span><span class="sxs-lookup"><span data-stu-id="0a8a7-247">EDR_crash_count</span></span>                | <span data-ttu-id="0a8a7-248">用戶端電腦上每小時 EDR 處理常式崩潰的次數</span><span class="sxs-lookup"><span data-stu-id="0a8a7-248">Number of times EDR process crashed every hour on client machine</span></span>        |

<span data-ttu-id="0a8a7-249">**內核擴充統計資料**</span><span class="sxs-lookup"><span data-stu-id="0a8a7-249">**Kernel extension statistics**</span></span>

<span data-ttu-id="0a8a7-250">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-250">The following fields are collected:</span></span>

| <span data-ttu-id="0a8a7-251">欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-251">Field</span></span>            | <span data-ttu-id="0a8a7-252">描述</span><span class="sxs-lookup"><span data-stu-id="0a8a7-252">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="0a8a7-253">版本</span><span class="sxs-lookup"><span data-stu-id="0a8a7-253">version</span></span>          | <span data-ttu-id="0a8a7-254">MacOS 上的 Microsoft Defender for Endpoint 版本。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-254">Version of Microsoft Defender for Endpoint on macOS.</span></span> |
| <span data-ttu-id="0a8a7-255">instance_id</span><span class="sxs-lookup"><span data-stu-id="0a8a7-255">instance_id</span></span>      | <span data-ttu-id="0a8a7-256">在內核擴充啟動時產生的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-256">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="0a8a7-257">trace_level</span><span class="sxs-lookup"><span data-stu-id="0a8a7-257">trace_level</span></span>      | <span data-ttu-id="0a8a7-258">內核擴充的追蹤層級。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-258">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="0a8a7-259">子系統</span><span class="sxs-lookup"><span data-stu-id="0a8a7-259">subsystem</span></span>        | <span data-ttu-id="0a8a7-260">用於即時保護的底層子系統。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-260">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="0a8a7-261">ipc。連接</span><span class="sxs-lookup"><span data-stu-id="0a8a7-261">ipc.connects</span></span>     | <span data-ttu-id="0a8a7-262">內核擴充所接收的連線要求數目。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-262">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="0a8a7-263">ipc。拒絕</span><span class="sxs-lookup"><span data-stu-id="0a8a7-263">ipc.rejects</span></span>      | <span data-ttu-id="0a8a7-264">內核擴充所拒絕的連線要求數目。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-264">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="0a8a7-265">ipc。已連線</span><span class="sxs-lookup"><span data-stu-id="0a8a7-265">ipc.connected</span></span>    | <span data-ttu-id="0a8a7-266">是否有任何作用中連接至內核分機。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-266">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="0a8a7-267">支援資料</span><span class="sxs-lookup"><span data-stu-id="0a8a7-267">Support data</span></span>

<span data-ttu-id="0a8a7-268">**診斷記錄**</span><span class="sxs-lookup"><span data-stu-id="0a8a7-268">**Diagnostic logs**</span></span>

<span data-ttu-id="0a8a7-269">僅當使用者同意提交功能時，才會收集診斷記錄。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-269">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="0a8a7-270">下列檔案會收集為支援記錄檔的一部分：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-270">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="0a8a7-271">*/Library/Logs/Microsoft/mdatp/* 下的所有檔案</span><span class="sxs-lookup"><span data-stu-id="0a8a7-271">All files under */Library/Logs/Microsoft/mdatp/*</span></span>
- <span data-ttu-id="0a8a7-272">*/Library/Application 支援/microsoft/Defender/* （由 microsoft Defender for Endpoint on macOS 所建立及使用）下的檔案子集</span><span class="sxs-lookup"><span data-stu-id="0a8a7-272">Subset of files under */Library/Application Support/Microsoft/Defender/* that are created and used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="0a8a7-273">MacOS 上的 Microsoft Defender for Endpoint 所使用之 [ */Library/Managed 偏好* 設定] 底下的檔案子集</span><span class="sxs-lookup"><span data-stu-id="0a8a7-273">Subset of files under */Library/Managed Preferences* that are used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="0a8a7-274">/Library/Logs/Microsoft/autoupdate.log</span><span class="sxs-lookup"><span data-stu-id="0a8a7-274">/Library/Logs/Microsoft/autoupdate.log</span></span>
- <span data-ttu-id="0a8a7-275">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span><span class="sxs-lookup"><span data-stu-id="0a8a7-275">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="0a8a7-276">選擇性診斷資料</span><span class="sxs-lookup"><span data-stu-id="0a8a7-276">Optional diagnostic data</span></span>

<span data-ttu-id="0a8a7-277">**選用診斷資料** 是額外的資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷及修正問題。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-277">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="0a8a7-278">如果您選擇將選用的診斷資料傳送給我們，則也會包含必要的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-278">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="0a8a7-279">選用診斷資料的範例包括 Microsoft 收集有關產品設定 (的資料，例如，) 裝置上的排除專案數目，以及產品) 的元件效能 (匯總度量。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-279">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="0a8a7-280">軟體安裝和庫存資料事件</span><span class="sxs-lookup"><span data-stu-id="0a8a7-280">Software setup and inventory data events</span></span>

<span data-ttu-id="0a8a7-281">**適用於端點的 Microsoft Defender 設定**</span><span class="sxs-lookup"><span data-stu-id="0a8a7-281">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="0a8a7-282">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-282">The following fields are collected:</span></span>

| <span data-ttu-id="0a8a7-283">欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-283">Field</span></span>                                              | <span data-ttu-id="0a8a7-284">描述</span><span class="sxs-lookup"><span data-stu-id="0a8a7-284">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="0a8a7-285">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="0a8a7-285">connection_retry_timeout</span></span>                           | <span data-ttu-id="0a8a7-286">與雲端通訊時，連線重試超時。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-286">Connection retry time out when communication with the cloud.</span></span> |
| <span data-ttu-id="0a8a7-287">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="0a8a7-287">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="0a8a7-288">產品快取的大小。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-288">Size of the product cache.</span></span> |
| <span data-ttu-id="0a8a7-289">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="0a8a7-289">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="0a8a7-290">每天上傳的崩潰記錄檔限制。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-290">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="0a8a7-291">antivirus_engine。排除 [] .is_directory</span><span class="sxs-lookup"><span data-stu-id="0a8a7-291">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="0a8a7-292">掃描的排除是否為目錄。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-292">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="0a8a7-293">antivirus_engine。排除 [] 路徑</span><span class="sxs-lookup"><span data-stu-id="0a8a7-293">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="0a8a7-294">排除在掃描之外的路徑。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-294">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="0a8a7-295">antivirus_engine。排除 [] 副檔名</span><span class="sxs-lookup"><span data-stu-id="0a8a7-295">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="0a8a7-296">排除來自掃描的分機號碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-296">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="0a8a7-297">antivirus_engine。排除 []。名稱</span><span class="sxs-lookup"><span data-stu-id="0a8a7-297">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="0a8a7-298">排除在掃描之外的檔案名。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-298">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="0a8a7-299">antivirus_engine antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="0a8a7-299">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="0a8a7-300">產品快取的大小。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-300">Size of the product cache.</span></span> |
| <span data-ttu-id="0a8a7-301">antivirus_engine antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="0a8a7-301">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="0a8a7-302">掃描時所用的執行緒數目上限。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-302">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="0a8a7-303">antivirus_engine antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="0a8a7-303">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="0a8a7-304">在從隔離區還原的檔案之前，可再次偵測到超時。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-304">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="0a8a7-305">antivirus_engine antivirus_engine.threat_type_settings</span><span class="sxs-lookup"><span data-stu-id="0a8a7-305">antivirus_engine.threat_type_settings</span></span>              | <span data-ttu-id="0a8a7-306">產品如何處理不同威脅類型的設定。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-306">Configuration for how different threat types are handled by the product.</span></span> |
| <span data-ttu-id="0a8a7-307">filesystem_scanner filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="0a8a7-307">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="0a8a7-308">完整掃描目錄。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-308">Full scan directory.</span></span> |
| <span data-ttu-id="0a8a7-309">filesystem_scanner filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="0a8a7-309">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="0a8a7-310">快速掃描中所用的目錄清單。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-310">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="0a8a7-311">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="0a8a7-311">edr.latency_mode</span></span>                                   | <span data-ttu-id="0a8a7-312">偵測及回應元件所使用的延遲模式。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-312">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="0a8a7-313">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="0a8a7-313">edr.proxy_address</span></span>                                  | <span data-ttu-id="0a8a7-314">偵測及回應元件所使用的 Proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-314">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="0a8a7-315">**Microsoft 自動更新設定**</span><span class="sxs-lookup"><span data-stu-id="0a8a7-315">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="0a8a7-316">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-316">The following fields are collected:</span></span>

| <span data-ttu-id="0a8a7-317">欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-317">Field</span></span>                       | <span data-ttu-id="0a8a7-318">描述</span><span class="sxs-lookup"><span data-stu-id="0a8a7-318">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="0a8a7-319">how_to_check</span><span class="sxs-lookup"><span data-stu-id="0a8a7-319">how_to_check</span></span>                | <span data-ttu-id="0a8a7-320">會決定如何檢查產品更新 (例如，自動或手動) 。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-320">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="0a8a7-321">channel_name</span><span class="sxs-lookup"><span data-stu-id="0a8a7-321">channel_name</span></span>                | <span data-ttu-id="0a8a7-322">更新與裝置相關聯的通道。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-322">Update channel associated with the device.</span></span> |
| <span data-ttu-id="0a8a7-323">manifest_server</span><span class="sxs-lookup"><span data-stu-id="0a8a7-323">manifest_server</span></span>             | <span data-ttu-id="0a8a7-324">用於下載更新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-324">Server used for downloading updates.</span></span> |
| <span data-ttu-id="0a8a7-325">update_cache</span><span class="sxs-lookup"><span data-stu-id="0a8a7-325">update_cache</span></span>                | <span data-ttu-id="0a8a7-326">用來儲存更新的快取位置。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-326">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="0a8a7-327">產品和服務使用</span><span class="sxs-lookup"><span data-stu-id="0a8a7-327">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="0a8a7-328">已開始診斷記錄上載報告</span><span class="sxs-lookup"><span data-stu-id="0a8a7-328">Diagnostic log upload started report</span></span>

<span data-ttu-id="0a8a7-329">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-329">The following fields are collected:</span></span>

| <span data-ttu-id="0a8a7-330">欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-330">Field</span></span>            | <span data-ttu-id="0a8a7-331">描述</span><span class="sxs-lookup"><span data-stu-id="0a8a7-331">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="0a8a7-332">sha256</span><span class="sxs-lookup"><span data-stu-id="0a8a7-332">sha256</span></span>           | <span data-ttu-id="0a8a7-333">支援記錄檔的 SHA256 識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-333">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="0a8a7-334">Size</span><span class="sxs-lookup"><span data-stu-id="0a8a7-334">size</span></span>             | <span data-ttu-id="0a8a7-335">支援記錄檔的大小。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-335">Size of the support log.</span></span> |
| <span data-ttu-id="0a8a7-336">original_path</span><span class="sxs-lookup"><span data-stu-id="0a8a7-336">original_path</span></span>    | <span data-ttu-id="0a8a7-337">支援記錄檔的路徑 (always 低於 */Library/Application support/Microsoft/Defender/wdavdiag/*) 。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-337">Path to the support log (always under */Library/Application Support/Microsoft/Defender/wdavdiag/*).</span></span> |
| <span data-ttu-id="0a8a7-338">format</span><span class="sxs-lookup"><span data-stu-id="0a8a7-338">format</span></span>           | <span data-ttu-id="0a8a7-339">支援記錄檔的格式。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-339">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="0a8a7-340">診斷記錄上載已完成報告</span><span class="sxs-lookup"><span data-stu-id="0a8a7-340">Diagnostic log upload completed report</span></span>

<span data-ttu-id="0a8a7-341">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-341">The following fields are collected:</span></span>

| <span data-ttu-id="0a8a7-342">欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-342">Field</span></span>            | <span data-ttu-id="0a8a7-343">描述</span><span class="sxs-lookup"><span data-stu-id="0a8a7-343">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="0a8a7-344">request_id</span><span class="sxs-lookup"><span data-stu-id="0a8a7-344">request_id</span></span>       | <span data-ttu-id="0a8a7-345">支援記錄檔上載要求的相互關聯識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-345">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="0a8a7-346">sha256</span><span class="sxs-lookup"><span data-stu-id="0a8a7-346">sha256</span></span>           | <span data-ttu-id="0a8a7-347">支援記錄檔的 SHA256 識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-347">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="0a8a7-348">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="0a8a7-348">blob_sas_uri</span></span>     | <span data-ttu-id="0a8a7-349">應用程式用來上傳支援記錄的 URI。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-349">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="0a8a7-350">產品和服務效能資料事件</span><span class="sxs-lookup"><span data-stu-id="0a8a7-350">Product and service performance data events</span></span>

<span data-ttu-id="0a8a7-351">**非預期的應用程式結束 (當機)**</span><span class="sxs-lookup"><span data-stu-id="0a8a7-351">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="0a8a7-352">非預期的應用程式結束，以及在該情況下應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-352">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="0a8a7-353">**內核擴充統計資料**</span><span class="sxs-lookup"><span data-stu-id="0a8a7-353">**Kernel extension statistics**</span></span>

<span data-ttu-id="0a8a7-354">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0a8a7-354">The following fields are collected:</span></span>

| <span data-ttu-id="0a8a7-355">欄位</span><span class="sxs-lookup"><span data-stu-id="0a8a7-355">Field</span></span>                          | <span data-ttu-id="0a8a7-356">描述</span><span class="sxs-lookup"><span data-stu-id="0a8a7-356">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="0a8a7-357">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="0a8a7-357">pkt_ack_timeout</span></span>                | <span data-ttu-id="0a8a7-358">下列屬性是匯總數值，代表自內核延伸啟動之後發生的事件計數。</span><span class="sxs-lookup"><span data-stu-id="0a8a7-358">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="0a8a7-359">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="0a8a7-359">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="0a8a7-360">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="0a8a7-360">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="0a8a7-361">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="0a8a7-361">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="0a8a7-362">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="0a8a7-362">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="0a8a7-363">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="0a8a7-363">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="0a8a7-364">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="0a8a7-364">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="0a8a7-365">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="0a8a7-365">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="0a8a7-366">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="0a8a7-366">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="0a8a7-367">ipc ack。超時</span><span class="sxs-lookup"><span data-stu-id="0a8a7-367">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="0a8a7-368">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="0a8a7-368">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="0a8a7-369">ackd</span><span class="sxs-lookup"><span data-stu-id="0a8a7-369">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="0a8a7-370">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="0a8a7-370">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="0a8a7-371">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="0a8a7-371">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="0a8a7-372">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="0a8a7-372">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="0a8a7-373">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="0a8a7-373">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="0a8a7-374">kauth vnode</span><span class="sxs-lookup"><span data-stu-id="0a8a7-374">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="0a8a7-375">vnode 讀取的 kauth</span><span class="sxs-lookup"><span data-stu-id="0a8a7-375">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="0a8a7-376">kauth vnode</span><span class="sxs-lookup"><span data-stu-id="0a8a7-376">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="0a8a7-377">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="0a8a7-377">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="0a8a7-378">vnode kauth</span><span class="sxs-lookup"><span data-stu-id="0a8a7-378">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="0a8a7-379">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="0a8a7-379">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="0a8a7-380">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="0a8a7-380">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="0a8a7-381">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="0a8a7-381">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="0a8a7-382">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="0a8a7-382">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="0a8a7-383">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="0a8a7-383">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="0a8a7-384">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="0a8a7-384">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="0a8a7-385">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="0a8a7-385">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="0a8a7-386">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="0a8a7-386">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="0a8a7-387">vnode 建立 kauth</span><span class="sxs-lookup"><span data-stu-id="0a8a7-387">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="0a8a7-388">vnode 移動的 kauth</span><span class="sxs-lookup"><span data-stu-id="0a8a7-388">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="0a8a7-389">vnode 裝載 kauth</span><span class="sxs-lookup"><span data-stu-id="0a8a7-389">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="0a8a7-390">kauth 拒絕的 vnode</span><span class="sxs-lookup"><span data-stu-id="0a8a7-390">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="0a8a7-391">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="0a8a7-391">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="0a8a7-392">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="0a8a7-392">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="0a8a7-393">ipc.kauth.file_op 遮罩</span><span class="sxs-lookup"><span data-stu-id="0a8a7-393">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="0a8a7-394">ipc.kauth_file_op。開啟</span><span class="sxs-lookup"><span data-stu-id="0a8a7-394">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="0a8a7-395">ipc.kauth.file_op。關閉</span><span class="sxs-lookup"><span data-stu-id="0a8a7-395">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="0a8a7-396">ipc.kauth.file_op ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="0a8a7-396">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="0a8a7-397">ipc.kauth.file_op。移動</span><span class="sxs-lookup"><span data-stu-id="0a8a7-397">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="0a8a7-398">ipc.kauth.file_op。連結</span><span class="sxs-lookup"><span data-stu-id="0a8a7-398">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="0a8a7-399">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="0a8a7-399">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="0a8a7-400">ipc.kauth.file_op。移除</span><span class="sxs-lookup"><span data-stu-id="0a8a7-400">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="0a8a7-401">ipc.kauth.file_op。卸載</span><span class="sxs-lookup"><span data-stu-id="0a8a7-401">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="0a8a7-402">ipc.kauth.file_op 的派生</span><span class="sxs-lookup"><span data-stu-id="0a8a7-402">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="0a8a7-403">ipc.kauth.file_op。建立</span><span class="sxs-lookup"><span data-stu-id="0a8a7-403">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="0a8a7-404">資源</span><span class="sxs-lookup"><span data-stu-id="0a8a7-404">Resources</span></span>

- [<span data-ttu-id="0a8a7-405">Microsoft 中的隱私權</span><span class="sxs-lookup"><span data-stu-id="0a8a7-405">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
