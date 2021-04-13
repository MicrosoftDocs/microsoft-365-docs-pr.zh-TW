---
title: 適用于 Linux 的 Microsoft Defender ATP 隱私權
description: 隱私權控制，如何設定會影響隱私權的原則設定，以及 Microsoft Defender ATP for Linux 中所收集診斷資料的相關資訊。
keywords: microsoft、defender、atp、linux、隱私權、診斷
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aaf537c84adaba3d632367567cc569069650d21a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688354"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="987a6-104">Linux 上的 Microsoft Defender for Endpoint 的隱私權</span><span class="sxs-lookup"><span data-stu-id="987a6-104">Privacy for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="987a6-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="987a6-105">**Applies to:**</span></span>
- [<span data-ttu-id="987a6-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="987a6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="987a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="987a6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="987a6-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="987a6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="987a6-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="987a6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="987a6-110">Microsoft 致力於為您提供您所需的資訊和控制，讓您選擇如何在使用 Defender for Linux 時收集和使用資料。</span><span class="sxs-lookup"><span data-stu-id="987a6-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="987a6-111">本主題說明產品內可用的隱私權控制，如何使用原則設定管理這些控制項，以及收集的資料事件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="987a6-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="987a6-112">在 Linux 上的 Microsoft Defender for Endpoint 中取得隱私權控制的概覽</span><span class="sxs-lookup"><span data-stu-id="987a6-112">Overview of privacy controls in Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="987a6-113">本節說明用於 Linux 之 Defender for Endpoint 所收集的不同資料類型的隱私權控制。</span><span class="sxs-lookup"><span data-stu-id="987a6-113">This section describes the privacy controls for the different types of data collected by Defender for Endpoint for Linux.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="987a6-114">診斷資料</span><span class="sxs-lookup"><span data-stu-id="987a6-114">Diagnostic data</span></span>

<span data-ttu-id="987a6-115">診斷資料是用來將 Defender 設定為安全和更新、偵測、診斷和修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="987a6-115">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="987a6-116">某些診斷資料為必要，而某些診斷資料為選用。</span><span class="sxs-lookup"><span data-stu-id="987a6-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="987a6-117">我們可讓您選擇要透過隱私權控制 (如組織的原則設定) 向我們傳送必要或選用的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="987a6-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="987a6-118">您可以選擇下列兩個適用于 Defender 的 Defender 用戶端軟體層級診斷資料。</span><span class="sxs-lookup"><span data-stu-id="987a6-118">There are two levels of diagnostic data for Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="987a6-119">**必要**：必要的資料，以協助讓 Defender 保持在最新狀態，並且在安裝此裝置的裝置上如期執行。</span><span class="sxs-lookup"><span data-stu-id="987a6-119">**Required**: The minimum data necessary to help keep Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="987a6-120">**選用**：其他資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷和修正問題。</span><span class="sxs-lookup"><span data-stu-id="987a6-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="987a6-121">根據預設，只會將所需的診斷資料傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="987a6-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="987a6-122">雲端已傳送保護資料</span><span class="sxs-lookup"><span data-stu-id="987a6-122">Cloud delivered protection data</span></span>

<span data-ttu-id="987a6-123">雲端提供的保護功能可讓您在存取雲端中的最新保護資料時，提供更快且更快速的保護。</span><span class="sxs-lookup"><span data-stu-id="987a6-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="987a6-124">啟用雲端傳送保護服務是選用的選項，但是強烈建議您這麼做，因為它會針對您的端點和網路上的惡意程式碼提供重要防護。</span><span class="sxs-lookup"><span data-stu-id="987a6-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="987a6-125">資料範例</span><span class="sxs-lookup"><span data-stu-id="987a6-125">Sample data</span></span>

<span data-ttu-id="987a6-126">範例資料是用來改善產品的保護功能，方法是傳送 Microsoft 可疑的範例，使其能夠進行分析。</span><span class="sxs-lookup"><span data-stu-id="987a6-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="987a6-127">啟用自動範例提交是選用的。</span><span class="sxs-lookup"><span data-stu-id="987a6-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="987a6-128">有三個層級可用於控制範例提交：</span><span class="sxs-lookup"><span data-stu-id="987a6-128">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="987a6-129">**None**：沒有可疑的範例提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="987a6-129">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="987a6-130">**安全**：只有不含個人身分識別資訊 (PII) 的可疑範例會自動提交。</span><span class="sxs-lookup"><span data-stu-id="987a6-130">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="987a6-131">此為此設定的預設值。</span><span class="sxs-lookup"><span data-stu-id="987a6-131">This is the default value for this setting.</span></span>
- <span data-ttu-id="987a6-132">**All**：將所有可疑的範例提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="987a6-132">**All**: all suspicious samples are submitted to Microsoft.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="987a6-133">使用原則設定管理隱私權控制項</span><span class="sxs-lookup"><span data-stu-id="987a6-133">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="987a6-134">如果您是 IT 管理員，您可能會想要在企業層級設定這些控制項。</span><span class="sxs-lookup"><span data-stu-id="987a6-134">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="987a6-135">在 [設定用於 Linux 之 Defender 的首選項](linux-preferences.md)時，會詳細說明上述各節中所述的各種資料類型的隱私權控制。</span><span class="sxs-lookup"><span data-stu-id="987a6-135">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

<span data-ttu-id="987a6-136">就像任何新的原則設定一樣，您應該在有限的受控環境中仔細測試這些設定，以確保您設定的設定在您的組織中更廣泛地實施原則設定之前具有適當的效果。</span><span class="sxs-lookup"><span data-stu-id="987a6-136">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="987a6-137">診斷資料事件</span><span class="sxs-lookup"><span data-stu-id="987a6-137">Diagnostic data events</span></span>

<span data-ttu-id="987a6-138">本節說明什麼是被視為必要的診斷資料，以及哪些專案會被視為選用的診斷資料，以及所收集的事件及欄位的描述。</span><span class="sxs-lookup"><span data-stu-id="987a6-138">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="987a6-139">所有事件通用的資料欄位</span><span class="sxs-lookup"><span data-stu-id="987a6-139">Data fields that are common for all events</span></span>
<span data-ttu-id="987a6-140">有一些事件的相關資訊是所有事件通用，而不論類別或資料子類型為何。</span><span class="sxs-lookup"><span data-stu-id="987a6-140">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="987a6-141">下欄欄位對於所有事件都是常見的：</span><span class="sxs-lookup"><span data-stu-id="987a6-141">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="987a6-142">欄位</span><span class="sxs-lookup"><span data-stu-id="987a6-142">Field</span></span>                   | <span data-ttu-id="987a6-143">描述</span><span class="sxs-lookup"><span data-stu-id="987a6-143">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="987a6-144">平台</span><span class="sxs-lookup"><span data-stu-id="987a6-144">platform</span></span>                | <span data-ttu-id="987a6-145">應用程式執行所在平臺的廣泛分類。</span><span class="sxs-lookup"><span data-stu-id="987a6-145">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="987a6-146">可讓 Microsoft 識別可能發生問題的平臺，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="987a6-146">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="987a6-147">machine_guid</span><span class="sxs-lookup"><span data-stu-id="987a6-147">machine_guid</span></span>            | <span data-ttu-id="987a6-148">與裝置相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-148">Unique identifier associated with the device.</span></span> <span data-ttu-id="987a6-149">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="987a6-149">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="987a6-150">sense_guid</span><span class="sxs-lookup"><span data-stu-id="987a6-150">sense_guid</span></span>              | <span data-ttu-id="987a6-151">與裝置相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-151">Unique identifier associated with the device.</span></span> <span data-ttu-id="987a6-152">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="987a6-152">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="987a6-153">org_id</span><span class="sxs-lookup"><span data-stu-id="987a6-153">org_id</span></span>                  | <span data-ttu-id="987a6-154">與裝置所屬之企業相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-154">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="987a6-155">可讓 Microsoft 識別問題是否會影響一組選擇的企業，以及受影響的企業數目。</span><span class="sxs-lookup"><span data-stu-id="987a6-155">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="987a6-156">主機 名</span><span class="sxs-lookup"><span data-stu-id="987a6-156">hostname</span></span>                | <span data-ttu-id="987a6-157">本機裝置名稱 (，但沒有 DNS 尾碼) 。</span><span class="sxs-lookup"><span data-stu-id="987a6-157">Local device name (without DNS suffix).</span></span> <span data-ttu-id="987a6-158">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="987a6-158">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="987a6-159">product_guid</span><span class="sxs-lookup"><span data-stu-id="987a6-159">product_guid</span></span>            | <span data-ttu-id="987a6-160">產品的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-160">Unique identifier of the product.</span></span> <span data-ttu-id="987a6-161">可讓 Microsoft 區分影響不同產品風格的問題。</span><span class="sxs-lookup"><span data-stu-id="987a6-161">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="987a6-162">app_version</span><span class="sxs-lookup"><span data-stu-id="987a6-162">app_version</span></span>             | <span data-ttu-id="987a6-163">適用于 Linux 應用程式的 Defender 版本。</span><span class="sxs-lookup"><span data-stu-id="987a6-163">Version of the Defender for Endpoint for Linux application.</span></span> <span data-ttu-id="987a6-164">可讓 Microsoft 找出顯示問題的產品版本，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="987a6-164">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="987a6-165">sig_version</span><span class="sxs-lookup"><span data-stu-id="987a6-165">sig_version</span></span>             | <span data-ttu-id="987a6-166">安全性情報資料庫的版本。</span><span class="sxs-lookup"><span data-stu-id="987a6-166">Version of security intelligence database.</span></span> <span data-ttu-id="987a6-167">可讓 Microsoft 找出顯示問題的安全性情報版本，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="987a6-167">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="987a6-168">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="987a6-168">supported_compressions</span></span>  | <span data-ttu-id="987a6-169">例如，應用程式支援的壓縮演算法清單 `['gzip']` 。</span><span class="sxs-lookup"><span data-stu-id="987a6-169">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="987a6-170">可讓 Microsoft 瞭解哪些類型的 compressions 可以在與應用程式通訊時使用。</span><span class="sxs-lookup"><span data-stu-id="987a6-170">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="987a6-171">release_ring</span><span class="sxs-lookup"><span data-stu-id="987a6-171">release_ring</span></span>            | <span data-ttu-id="987a6-172">裝置與 (相關聯的環，例如，內幕人士快、內幕人士緩慢、實際執行) 。</span><span class="sxs-lookup"><span data-stu-id="987a6-172">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="987a6-173">可讓 Microsoft 識別可能發生問題的發行環，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="987a6-173">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |

### <a name="required-diagnostic-data"></a><span data-ttu-id="987a6-174">必要診斷資料</span><span class="sxs-lookup"><span data-stu-id="987a6-174">Required diagnostic data</span></span>

<span data-ttu-id="987a6-175">必要的 **診斷資料** 是必要的最少資料，以協助讓 Defender 保持在最新狀態，並且在安裝此裝置的裝置上如期執行。</span><span class="sxs-lookup"><span data-stu-id="987a6-175">**Required diagnostic data** is the minimum data necessary to help keep Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="987a6-176">必要的診斷資料可協助識別可能與裝置或軟體設定有關的 Microsoft Defender 端點相關問題。</span><span class="sxs-lookup"><span data-stu-id="987a6-176">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="987a6-177">例如，它可協助判斷在特定作業系統版本、新引進的功能，或停用特定的 Defender 功能時，是否要讓 Defender for Endpoint 功能的情況更頻繁地崩潰。</span><span class="sxs-lookup"><span data-stu-id="987a6-177">For example, it can help determine if a Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="987a6-178">必要的診斷資料可協助 Microsoft 偵測、診斷及修正這些問題，以加快對使用者或組織的影響。</span><span class="sxs-lookup"><span data-stu-id="987a6-178">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="987a6-179">軟體安裝和庫存資料事件</span><span class="sxs-lookup"><span data-stu-id="987a6-179">Software setup and inventory data events</span></span>

<span data-ttu-id="987a6-180">**Microsoft Defender for Endpoint 安裝/卸載**</span><span class="sxs-lookup"><span data-stu-id="987a6-180">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="987a6-181">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="987a6-181">The following fields are collected:</span></span>

| <span data-ttu-id="987a6-182">欄位</span><span class="sxs-lookup"><span data-stu-id="987a6-182">Field</span></span>            | <span data-ttu-id="987a6-183">描述</span><span class="sxs-lookup"><span data-stu-id="987a6-183">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="987a6-184">correlation_id</span><span class="sxs-lookup"><span data-stu-id="987a6-184">correlation_id</span></span>   | <span data-ttu-id="987a6-185">與安裝相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-185">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="987a6-186">版本</span><span class="sxs-lookup"><span data-stu-id="987a6-186">version</span></span>          | <span data-ttu-id="987a6-187">套件的版本。</span><span class="sxs-lookup"><span data-stu-id="987a6-187">Version of the package.</span></span> |
| <span data-ttu-id="987a6-188">嚴重性</span><span class="sxs-lookup"><span data-stu-id="987a6-188">severity</span></span>         | <span data-ttu-id="987a6-189">郵件的嚴重性 (例如，) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="987a6-189">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="987a6-190">code</span><span class="sxs-lookup"><span data-stu-id="987a6-190">code</span></span>             | <span data-ttu-id="987a6-191">描述工序的程式碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-191">Code that describes the operation.</span></span> |
| <span data-ttu-id="987a6-192">文字</span><span class="sxs-lookup"><span data-stu-id="987a6-192">text</span></span>             | <span data-ttu-id="987a6-193">產品安裝相關的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="987a6-193">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="987a6-194">**適用於端點的 Microsoft Defender 設定**</span><span class="sxs-lookup"><span data-stu-id="987a6-194">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="987a6-195">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="987a6-195">The following fields are collected:</span></span>

| <span data-ttu-id="987a6-196">欄位</span><span class="sxs-lookup"><span data-stu-id="987a6-196">Field</span></span>                                               | <span data-ttu-id="987a6-197">描述</span><span class="sxs-lookup"><span data-stu-id="987a6-197">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="987a6-198">antivirus_engine antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="987a6-198">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="987a6-199">是否已在裝置上啟用即時保護功能。</span><span class="sxs-lookup"><span data-stu-id="987a6-199">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="987a6-200">antivirus_engine antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="987a6-200">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="987a6-201">是否已在裝置上啟用被動式模式。</span><span class="sxs-lookup"><span data-stu-id="987a6-201">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="987a6-202">cloud_service。 enabled</span><span class="sxs-lookup"><span data-stu-id="987a6-202">cloud_service.enabled</span></span>                               | <span data-ttu-id="987a6-203">是否已在裝置上啟用雲端已傳送保護功能。</span><span class="sxs-lookup"><span data-stu-id="987a6-203">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="987a6-204">cloud_service。超時</span><span class="sxs-lookup"><span data-stu-id="987a6-204">cloud_service.timeout</span></span>                               | <span data-ttu-id="987a6-205">當應用程式與 Endpoint cloud 的 Defender 進行通訊時超時。</span><span class="sxs-lookup"><span data-stu-id="987a6-205">Time out when the application communicates with the Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="987a6-206">cloud_service cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="987a6-206">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="987a6-207">產品傳送至雲端的連續心跳之間的間隔。</span><span class="sxs-lookup"><span data-stu-id="987a6-207">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="987a6-208">cloud_service cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="987a6-208">cloud_service.service_uri</span></span>                           | <span data-ttu-id="987a6-209">用於與雲端通訊的 URI。</span><span class="sxs-lookup"><span data-stu-id="987a6-209">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="987a6-210">cloud_service cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="987a6-210">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="987a6-211">裝置的診斷層級 (必要，選用) 。</span><span class="sxs-lookup"><span data-stu-id="987a6-211">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="987a6-212">cloud_service cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="987a6-212">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="987a6-213">裝置的自動範例提交層級 (無，安全，所有) 。</span><span class="sxs-lookup"><span data-stu-id="987a6-213">Automatic sample submission level of the device (none, safe, all).</span></span> |
| <span data-ttu-id="987a6-214">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="987a6-214">edr.early_preview</span></span>                                   | <span data-ttu-id="987a6-215">裝置是否應執行「及早預覽」功能。</span><span class="sxs-lookup"><span data-stu-id="987a6-215">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="987a6-216">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="987a6-216">edr.group_id</span></span>                                        | <span data-ttu-id="987a6-217">偵測及回應元件所使用的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-217">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="987a6-218">edr 標記</span><span class="sxs-lookup"><span data-stu-id="987a6-218">edr.tags</span></span>                                            | <span data-ttu-id="987a6-219">使用者定義的標記。</span><span class="sxs-lookup"><span data-stu-id="987a6-219">User-defined tags.</span></span> |
| <span data-ttu-id="987a6-220">功能。 \[選用功能名稱\]</span><span class="sxs-lookup"><span data-stu-id="987a6-220">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="987a6-221">預覽功能的清單，及其是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="987a6-221">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="987a6-222">產品和服務使用資料事件</span><span class="sxs-lookup"><span data-stu-id="987a6-222">Product and service usage data events</span></span>

<span data-ttu-id="987a6-223">**安全性智慧更新報告**</span><span class="sxs-lookup"><span data-stu-id="987a6-223">**Security intelligence update report**</span></span>

<span data-ttu-id="987a6-224">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="987a6-224">The following fields are collected:</span></span>

| <span data-ttu-id="987a6-225">欄位</span><span class="sxs-lookup"><span data-stu-id="987a6-225">Field</span></span>            | <span data-ttu-id="987a6-226">描述</span><span class="sxs-lookup"><span data-stu-id="987a6-226">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="987a6-227">from_version</span><span class="sxs-lookup"><span data-stu-id="987a6-227">from_version</span></span>     | <span data-ttu-id="987a6-228">原始安全性智慧版本。</span><span class="sxs-lookup"><span data-stu-id="987a6-228">Original security intelligence version.</span></span> |
| <span data-ttu-id="987a6-229">to_version</span><span class="sxs-lookup"><span data-stu-id="987a6-229">to_version</span></span>       | <span data-ttu-id="987a6-230">新的安全性智慧版本。</span><span class="sxs-lookup"><span data-stu-id="987a6-230">New security intelligence version.</span></span> |
| <span data-ttu-id="987a6-231">地位</span><span class="sxs-lookup"><span data-stu-id="987a6-231">status</span></span>           | <span data-ttu-id="987a6-232">表明成功或失敗之更新的狀態。</span><span class="sxs-lookup"><span data-stu-id="987a6-232">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="987a6-233">using_proxy</span><span class="sxs-lookup"><span data-stu-id="987a6-233">using_proxy</span></span>      | <span data-ttu-id="987a6-234">是否已透過 proxy 進行更新。</span><span class="sxs-lookup"><span data-stu-id="987a6-234">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="987a6-235">錯誤</span><span class="sxs-lookup"><span data-stu-id="987a6-235">error</span></span>            | <span data-ttu-id="987a6-236">如果更新失敗，則為錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-236">Error code if the update failed.</span></span> |
| <span data-ttu-id="987a6-237">reason</span><span class="sxs-lookup"><span data-stu-id="987a6-237">reason</span></span>           | <span data-ttu-id="987a6-238">更新失敗時的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="987a6-238">Error message if the update failed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="987a6-239">產品和服務效能資料事件</span><span class="sxs-lookup"><span data-stu-id="987a6-239">Product and service performance data events</span></span>

<span data-ttu-id="987a6-240">**內核擴充統計資料**</span><span class="sxs-lookup"><span data-stu-id="987a6-240">**Kernel extension statistics**</span></span>

<span data-ttu-id="987a6-241">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="987a6-241">The following fields are collected:</span></span>

| <span data-ttu-id="987a6-242">欄位</span><span class="sxs-lookup"><span data-stu-id="987a6-242">Field</span></span>            | <span data-ttu-id="987a6-243">描述</span><span class="sxs-lookup"><span data-stu-id="987a6-243">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="987a6-244">版本</span><span class="sxs-lookup"><span data-stu-id="987a6-244">version</span></span>          | <span data-ttu-id="987a6-245">適用于 Linux 之端點的 Defender 版本。</span><span class="sxs-lookup"><span data-stu-id="987a6-245">Version of Defender for Endpoint for Linux.</span></span> |
| <span data-ttu-id="987a6-246">instance_id</span><span class="sxs-lookup"><span data-stu-id="987a6-246">instance_id</span></span>      | <span data-ttu-id="987a6-247">在內核擴充啟動時產生的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-247">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="987a6-248">trace_level</span><span class="sxs-lookup"><span data-stu-id="987a6-248">trace_level</span></span>      | <span data-ttu-id="987a6-249">內核擴充的追蹤層級。</span><span class="sxs-lookup"><span data-stu-id="987a6-249">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="987a6-250">子系統</span><span class="sxs-lookup"><span data-stu-id="987a6-250">subsystem</span></span>        | <span data-ttu-id="987a6-251">用於即時保護的底層子系統。</span><span class="sxs-lookup"><span data-stu-id="987a6-251">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="987a6-252">ipc。連接</span><span class="sxs-lookup"><span data-stu-id="987a6-252">ipc.connects</span></span>     | <span data-ttu-id="987a6-253">內核擴充所接收的連線要求數目。</span><span class="sxs-lookup"><span data-stu-id="987a6-253">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="987a6-254">ipc。拒絕</span><span class="sxs-lookup"><span data-stu-id="987a6-254">ipc.rejects</span></span>      | <span data-ttu-id="987a6-255">內核擴充所拒絕的連線要求數目。</span><span class="sxs-lookup"><span data-stu-id="987a6-255">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="987a6-256">ipc。已連線</span><span class="sxs-lookup"><span data-stu-id="987a6-256">ipc.connected</span></span>    | <span data-ttu-id="987a6-257">是否有任何作用中連接至內核分機。</span><span class="sxs-lookup"><span data-stu-id="987a6-257">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="987a6-258">支援資料</span><span class="sxs-lookup"><span data-stu-id="987a6-258">Support data</span></span>

<span data-ttu-id="987a6-259">**診斷記錄**</span><span class="sxs-lookup"><span data-stu-id="987a6-259">**Diagnostic logs**</span></span>

<span data-ttu-id="987a6-260">僅當使用者同意提交功能時，才會收集診斷記錄。</span><span class="sxs-lookup"><span data-stu-id="987a6-260">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="987a6-261">下列檔案會收集為支援記錄檔的一部分：</span><span class="sxs-lookup"><span data-stu-id="987a6-261">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="987a6-262">*/Var/log/microsoft/mdatp* 下的所有檔案</span><span class="sxs-lookup"><span data-stu-id="987a6-262">All files under */var/log/microsoft/mdatp*</span></span>
- <span data-ttu-id="987a6-263">*/Etc/opt/microsoft/mdatp* 下的檔案子集合，由 Defender for Linux 的端點所建立及使用</span><span class="sxs-lookup"><span data-stu-id="987a6-263">Subset of files under */etc/opt/microsoft/mdatp* that are created and used by Defender for Endpoint for Linux</span></span>
- <span data-ttu-id="987a6-264">*/Var/log/microsoft_mdatp_ \* .log 中的* 產品安裝和卸載記錄</span><span class="sxs-lookup"><span data-stu-id="987a6-264">Product installation and uninstallation logs under */var/log/microsoft_mdatp_\*.log*</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="987a6-265">選擇性診斷資料</span><span class="sxs-lookup"><span data-stu-id="987a6-265">Optional diagnostic data</span></span>

<span data-ttu-id="987a6-266">**選用診斷資料** 是額外的資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷及修正問題。</span><span class="sxs-lookup"><span data-stu-id="987a6-266">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="987a6-267">如果您選擇將選用的診斷資料傳送給我們，則也會包含必要的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="987a6-267">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="987a6-268">選用診斷資料的範例包括 Microsoft 收集有關產品設定 (的資料，例如，) 裝置上的排除專案數目，以及產品) 的元件效能 (匯總度量。</span><span class="sxs-lookup"><span data-stu-id="987a6-268">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="987a6-269">軟體安裝和庫存資料事件</span><span class="sxs-lookup"><span data-stu-id="987a6-269">Software setup and inventory data events</span></span>

<span data-ttu-id="987a6-270">**適用於端點的 Microsoft Defender 設定**</span><span class="sxs-lookup"><span data-stu-id="987a6-270">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="987a6-271">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="987a6-271">The following fields are collected:</span></span>

| <span data-ttu-id="987a6-272">欄位</span><span class="sxs-lookup"><span data-stu-id="987a6-272">Field</span></span>                                              | <span data-ttu-id="987a6-273">描述</span><span class="sxs-lookup"><span data-stu-id="987a6-273">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="987a6-274">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="987a6-274">connection_retry_timeout</span></span>                           | <span data-ttu-id="987a6-275">與雲端通訊時，連線重試超時。</span><span class="sxs-lookup"><span data-stu-id="987a6-275">Connection retry time-out when communication with the cloud.</span></span> |
| <span data-ttu-id="987a6-276">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="987a6-276">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="987a6-277">產品快取的大小。</span><span class="sxs-lookup"><span data-stu-id="987a6-277">Size of the product cache.</span></span> |
| <span data-ttu-id="987a6-278">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="987a6-278">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="987a6-279">每天上傳的崩潰記錄檔限制。</span><span class="sxs-lookup"><span data-stu-id="987a6-279">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="987a6-280">antivirus_engine。排除 [] .is_directory</span><span class="sxs-lookup"><span data-stu-id="987a6-280">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="987a6-281">掃描的排除是否為目錄。</span><span class="sxs-lookup"><span data-stu-id="987a6-281">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="987a6-282">antivirus_engine。排除 [] 路徑</span><span class="sxs-lookup"><span data-stu-id="987a6-282">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="987a6-283">排除在掃描之外的路徑。</span><span class="sxs-lookup"><span data-stu-id="987a6-283">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="987a6-284">antivirus_engine。排除 [] 副檔名</span><span class="sxs-lookup"><span data-stu-id="987a6-284">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="987a6-285">排除來自掃描的分機號碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-285">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="987a6-286">antivirus_engine。排除 []。名稱</span><span class="sxs-lookup"><span data-stu-id="987a6-286">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="987a6-287">排除在掃描之外的檔案名。</span><span class="sxs-lookup"><span data-stu-id="987a6-287">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="987a6-288">antivirus_engine antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="987a6-288">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="987a6-289">產品快取的大小。</span><span class="sxs-lookup"><span data-stu-id="987a6-289">Size of the product cache.</span></span> |
| <span data-ttu-id="987a6-290">antivirus_engine antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="987a6-290">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="987a6-291">掃描時所用的執行緒數目上限。</span><span class="sxs-lookup"><span data-stu-id="987a6-291">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="987a6-292">antivirus_engine antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="987a6-292">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="987a6-293">在從隔離區還原的檔案之前，可再次偵測到超時。</span><span class="sxs-lookup"><span data-stu-id="987a6-293">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="987a6-294">filesystem_scanner filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="987a6-294">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="987a6-295">完整掃描目錄。</span><span class="sxs-lookup"><span data-stu-id="987a6-295">Full scan directory.</span></span> |
| <span data-ttu-id="987a6-296">filesystem_scanner filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="987a6-296">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="987a6-297">快速掃描中所用的目錄清單。</span><span class="sxs-lookup"><span data-stu-id="987a6-297">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="987a6-298">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="987a6-298">edr.latency_mode</span></span>                                   | <span data-ttu-id="987a6-299">偵測及回應元件所使用的延遲模式。</span><span class="sxs-lookup"><span data-stu-id="987a6-299">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="987a6-300">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="987a6-300">edr.proxy_address</span></span>                                  | <span data-ttu-id="987a6-301">偵測及回應元件所使用的 Proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="987a6-301">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="987a6-302">**Microsoft 自動更新設定**</span><span class="sxs-lookup"><span data-stu-id="987a6-302">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="987a6-303">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="987a6-303">The following fields are collected:</span></span>

| <span data-ttu-id="987a6-304">欄位</span><span class="sxs-lookup"><span data-stu-id="987a6-304">Field</span></span>                       | <span data-ttu-id="987a6-305">描述</span><span class="sxs-lookup"><span data-stu-id="987a6-305">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="987a6-306">how_to_check</span><span class="sxs-lookup"><span data-stu-id="987a6-306">how_to_check</span></span>                | <span data-ttu-id="987a6-307">會決定如何檢查產品更新 (例如，自動或手動) 。</span><span class="sxs-lookup"><span data-stu-id="987a6-307">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="987a6-308">channel_name</span><span class="sxs-lookup"><span data-stu-id="987a6-308">channel_name</span></span>                | <span data-ttu-id="987a6-309">更新與裝置相關聯的通道。</span><span class="sxs-lookup"><span data-stu-id="987a6-309">Update channel associated with the device.</span></span> |
| <span data-ttu-id="987a6-310">manifest_server</span><span class="sxs-lookup"><span data-stu-id="987a6-310">manifest_server</span></span>             | <span data-ttu-id="987a6-311">用於下載更新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="987a6-311">Server used for downloading updates.</span></span> |
| <span data-ttu-id="987a6-312">update_cache</span><span class="sxs-lookup"><span data-stu-id="987a6-312">update_cache</span></span>                | <span data-ttu-id="987a6-313">用來儲存更新的快取位置。</span><span class="sxs-lookup"><span data-stu-id="987a6-313">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="987a6-314">產品和服務使用</span><span class="sxs-lookup"><span data-stu-id="987a6-314">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="987a6-315">已開始診斷記錄上載報告</span><span class="sxs-lookup"><span data-stu-id="987a6-315">Diagnostic log upload started report</span></span>

<span data-ttu-id="987a6-316">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="987a6-316">The following fields are collected:</span></span>

| <span data-ttu-id="987a6-317">欄位</span><span class="sxs-lookup"><span data-stu-id="987a6-317">Field</span></span>            | <span data-ttu-id="987a6-318">描述</span><span class="sxs-lookup"><span data-stu-id="987a6-318">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="987a6-319">sha256</span><span class="sxs-lookup"><span data-stu-id="987a6-319">sha256</span></span>           | <span data-ttu-id="987a6-320">支援記錄檔的 SHA256 識別碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-320">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="987a6-321">Size</span><span class="sxs-lookup"><span data-stu-id="987a6-321">size</span></span>             | <span data-ttu-id="987a6-322">支援記錄檔的大小。</span><span class="sxs-lookup"><span data-stu-id="987a6-322">Size of the support log.</span></span> |
| <span data-ttu-id="987a6-323">original_path</span><span class="sxs-lookup"><span data-stu-id="987a6-323">original_path</span></span>    | <span data-ttu-id="987a6-324">支援記錄檔的路徑 (always 低於 */var/opt/microsoft/mdatp/wdavdiag/*) 。</span><span class="sxs-lookup"><span data-stu-id="987a6-324">Path to the support log (always under */var/opt/microsoft/mdatp/wdavdiag/*).</span></span> |
| <span data-ttu-id="987a6-325">format</span><span class="sxs-lookup"><span data-stu-id="987a6-325">format</span></span>           | <span data-ttu-id="987a6-326">支援記錄檔的格式。</span><span class="sxs-lookup"><span data-stu-id="987a6-326">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="987a6-327">診斷記錄上載已完成報告</span><span class="sxs-lookup"><span data-stu-id="987a6-327">Diagnostic log upload completed report</span></span>

<span data-ttu-id="987a6-328">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="987a6-328">The following fields are collected:</span></span>

| <span data-ttu-id="987a6-329">欄位</span><span class="sxs-lookup"><span data-stu-id="987a6-329">Field</span></span>            | <span data-ttu-id="987a6-330">描述</span><span class="sxs-lookup"><span data-stu-id="987a6-330">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="987a6-331">request_id</span><span class="sxs-lookup"><span data-stu-id="987a6-331">request_id</span></span>       | <span data-ttu-id="987a6-332">支援記錄檔上載要求的相互關聯識別碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-332">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="987a6-333">sha256</span><span class="sxs-lookup"><span data-stu-id="987a6-333">sha256</span></span>           | <span data-ttu-id="987a6-334">支援記錄檔的 SHA256 識別碼。</span><span class="sxs-lookup"><span data-stu-id="987a6-334">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="987a6-335">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="987a6-335">blob_sas_uri</span></span>     | <span data-ttu-id="987a6-336">應用程式用來上傳支援記錄的 URI。</span><span class="sxs-lookup"><span data-stu-id="987a6-336">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="987a6-337">產品和服務效能資料事件</span><span class="sxs-lookup"><span data-stu-id="987a6-337">Product and service performance data events</span></span>

<span data-ttu-id="987a6-338">**非預期的應用程式結束 (當機)**</span><span class="sxs-lookup"><span data-stu-id="987a6-338">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="987a6-339">非預期的應用程式結束，以及在該情況下應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="987a6-339">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="987a6-340">**內核擴充統計資料**</span><span class="sxs-lookup"><span data-stu-id="987a6-340">**Kernel extension statistics**</span></span>

<span data-ttu-id="987a6-341">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="987a6-341">The following fields are collected:</span></span>

| <span data-ttu-id="987a6-342">欄位</span><span class="sxs-lookup"><span data-stu-id="987a6-342">Field</span></span>                          | <span data-ttu-id="987a6-343">描述</span><span class="sxs-lookup"><span data-stu-id="987a6-343">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="987a6-344">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="987a6-344">pkt_ack_timeout</span></span>                | <span data-ttu-id="987a6-345">下列屬性是匯總數值，代表自內核延伸啟動之後發生的事件計數。</span><span class="sxs-lookup"><span data-stu-id="987a6-345">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="987a6-346">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="987a6-346">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="987a6-347">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="987a6-347">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="987a6-348">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="987a6-348">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="987a6-349">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="987a6-349">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="987a6-350">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="987a6-350">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="987a6-351">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="987a6-351">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="987a6-352">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="987a6-352">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="987a6-353">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="987a6-353">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="987a6-354">ipc ack。超時</span><span class="sxs-lookup"><span data-stu-id="987a6-354">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="987a6-355">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="987a6-355">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="987a6-356">ackd</span><span class="sxs-lookup"><span data-stu-id="987a6-356">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="987a6-357">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="987a6-357">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="987a6-358">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="987a6-358">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="987a6-359">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="987a6-359">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="987a6-360">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="987a6-360">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="987a6-361">kauth vnode</span><span class="sxs-lookup"><span data-stu-id="987a6-361">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="987a6-362">vnode 讀取的 kauth</span><span class="sxs-lookup"><span data-stu-id="987a6-362">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="987a6-363">kauth vnode</span><span class="sxs-lookup"><span data-stu-id="987a6-363">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="987a6-364">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="987a6-364">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="987a6-365">vnode kauth</span><span class="sxs-lookup"><span data-stu-id="987a6-365">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="987a6-366">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="987a6-366">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="987a6-367">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="987a6-367">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="987a6-368">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="987a6-368">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="987a6-369">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="987a6-369">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="987a6-370">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="987a6-370">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="987a6-371">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="987a6-371">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="987a6-372">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="987a6-372">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="987a6-373">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="987a6-373">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="987a6-374">vnode 建立 kauth</span><span class="sxs-lookup"><span data-stu-id="987a6-374">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="987a6-375">vnode 移動的 kauth</span><span class="sxs-lookup"><span data-stu-id="987a6-375">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="987a6-376">vnode 裝載 kauth</span><span class="sxs-lookup"><span data-stu-id="987a6-376">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="987a6-377">kauth 拒絕的 vnode</span><span class="sxs-lookup"><span data-stu-id="987a6-377">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="987a6-378">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="987a6-378">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="987a6-379">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="987a6-379">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="987a6-380">ipc.kauth.file_op 遮罩</span><span class="sxs-lookup"><span data-stu-id="987a6-380">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="987a6-381">ipc.kauth_file_op。開啟</span><span class="sxs-lookup"><span data-stu-id="987a6-381">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="987a6-382">ipc.kauth.file_op。關閉</span><span class="sxs-lookup"><span data-stu-id="987a6-382">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="987a6-383">ipc.kauth.file_op ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="987a6-383">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="987a6-384">ipc.kauth.file_op。移動</span><span class="sxs-lookup"><span data-stu-id="987a6-384">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="987a6-385">ipc.kauth.file_op。連結</span><span class="sxs-lookup"><span data-stu-id="987a6-385">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="987a6-386">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="987a6-386">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="987a6-387">ipc.kauth.file_op。移除</span><span class="sxs-lookup"><span data-stu-id="987a6-387">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="987a6-388">ipc.kauth.file_op。卸載</span><span class="sxs-lookup"><span data-stu-id="987a6-388">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="987a6-389">ipc.kauth.file_op 的派生</span><span class="sxs-lookup"><span data-stu-id="987a6-389">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="987a6-390">ipc.kauth.file_op。建立</span><span class="sxs-lookup"><span data-stu-id="987a6-390">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="987a6-391">資源</span><span class="sxs-lookup"><span data-stu-id="987a6-391">Resources</span></span>

- [<span data-ttu-id="987a6-392">Microsoft 中的隱私權</span><span class="sxs-lookup"><span data-stu-id="987a6-392">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
