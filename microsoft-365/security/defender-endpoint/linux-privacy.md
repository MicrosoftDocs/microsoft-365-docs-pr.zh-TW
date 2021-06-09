---
title: Linux 上的 Microsoft Defender for Endpoint 的隱私權
description: 隱私權控制，如何設定會影響隱私權的原則設定，以及在 Linux 上為端點所收集之診斷資料的相關資訊。
keywords: microsoft、defender、Microsoft Defender for Endpoint、linux、隱私權、診斷
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
ms.openlocfilehash: 4be0960e8ba868df2acb313b171a08f667c287a7
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651329"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="0c68c-104">Linux 上的 Microsoft Defender for Endpoint 的隱私權</span><span class="sxs-lookup"><span data-stu-id="0c68c-104">Privacy for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0c68c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0c68c-105">**Applies to:**</span></span>
- [<span data-ttu-id="0c68c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0c68c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0c68c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c68c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0c68c-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="0c68c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0c68c-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="0c68c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="0c68c-110">Microsoft 致力於為您提供您所需的資訊和控制，讓您選擇如何在 Linux 上使用 Defender for Endpoint 時收集和使用資料。</span><span class="sxs-lookup"><span data-stu-id="0c68c-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="0c68c-111">本主題說明產品內可用的隱私權控制，如何使用原則設定管理這些控制項，以及收集的資料事件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0c68c-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="0c68c-112">在 Linux 上的 Microsoft Defender for Endpoint 中取得隱私權控制的概覽</span><span class="sxs-lookup"><span data-stu-id="0c68c-112">Overview of privacy controls in Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="0c68c-113">本節說明在 Linux 上的 Defender for Endpoint 所收集的不同資料類型的隱私權控制。</span><span class="sxs-lookup"><span data-stu-id="0c68c-113">This section describes the privacy controls for the different types of data collected by Defender for Endpoint on Linux.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="0c68c-114">診斷資料</span><span class="sxs-lookup"><span data-stu-id="0c68c-114">Diagnostic data</span></span>

<span data-ttu-id="0c68c-115">診斷資料是用來將 Defender 設定為安全和更新、偵測、診斷和修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="0c68c-115">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="0c68c-116">某些診斷資料為必要，而某些診斷資料為選用。</span><span class="sxs-lookup"><span data-stu-id="0c68c-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="0c68c-117">我們可讓您選擇要透過隱私權控制 (如組織的原則設定) 向我們傳送必要或選用的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="0c68c-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="0c68c-118">您可以選擇下列兩個適用于 Defender 的 Defender 用戶端軟體層級診斷資料。</span><span class="sxs-lookup"><span data-stu-id="0c68c-118">There are two levels of diagnostic data for Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="0c68c-119">**必要**：必要的資料，以協助讓 Defender 保持在最新狀態，並且在安裝此裝置的裝置上如期執行。</span><span class="sxs-lookup"><span data-stu-id="0c68c-119">**Required**: The minimum data necessary to help keep Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="0c68c-120">**選用**：其他資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷和修正問題。</span><span class="sxs-lookup"><span data-stu-id="0c68c-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="0c68c-121">根據預設，只會將所需的診斷資料傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="0c68c-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="0c68c-122">雲端已傳送保護資料</span><span class="sxs-lookup"><span data-stu-id="0c68c-122">Cloud delivered protection data</span></span>

<span data-ttu-id="0c68c-123">雲端提供的保護功能可讓您在存取雲端中的最新保護資料時，提供更快且更快速的保護。</span><span class="sxs-lookup"><span data-stu-id="0c68c-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="0c68c-124">啟用雲端傳送保護服務是選用的選項，但是強烈建議您這麼做，因為它會針對您的端點和網路上的惡意程式碼提供重要防護。</span><span class="sxs-lookup"><span data-stu-id="0c68c-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="0c68c-125">資料範例</span><span class="sxs-lookup"><span data-stu-id="0c68c-125">Sample data</span></span>

<span data-ttu-id="0c68c-126">範例資料是用來改善產品的保護功能，方法是傳送 Microsoft 可疑的範例，使其能夠進行分析。</span><span class="sxs-lookup"><span data-stu-id="0c68c-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="0c68c-127">啟用自動範例提交是選用的。</span><span class="sxs-lookup"><span data-stu-id="0c68c-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="0c68c-128">有三個層級可用於控制範例提交：</span><span class="sxs-lookup"><span data-stu-id="0c68c-128">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="0c68c-129">**None**：沒有可疑的範例提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="0c68c-129">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="0c68c-130">**安全**：只有不含個人身分識別資訊 (PII) 的可疑範例會自動提交。</span><span class="sxs-lookup"><span data-stu-id="0c68c-130">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="0c68c-131">此為此設定的預設值。</span><span class="sxs-lookup"><span data-stu-id="0c68c-131">This is the default value for this setting.</span></span>
- <span data-ttu-id="0c68c-132">**All**：將所有可疑的範例提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="0c68c-132">**All**: all suspicious samples are submitted to Microsoft.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="0c68c-133">使用原則設定管理隱私權控制項</span><span class="sxs-lookup"><span data-stu-id="0c68c-133">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="0c68c-134">如果您是 IT 管理員，您可能會想要在企業層級設定這些控制項。</span><span class="sxs-lookup"><span data-stu-id="0c68c-134">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="0c68c-135">在 [Linux 上的 Defender For Endpoint 的 [設定偏好設定](linux-preferences.md)] 中，詳細說明上述各節所述各類資料的隱私權。</span><span class="sxs-lookup"><span data-stu-id="0c68c-135">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

<span data-ttu-id="0c68c-136">就像任何新的原則設定一樣，您應該在有限的受控環境中仔細測試這些設定，以確保您設定的設定在您的組織中更廣泛地實施原則設定之前具有適當的效果。</span><span class="sxs-lookup"><span data-stu-id="0c68c-136">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="0c68c-137">診斷資料事件</span><span class="sxs-lookup"><span data-stu-id="0c68c-137">Diagnostic data events</span></span>

<span data-ttu-id="0c68c-138">本節說明什麼是被視為必要的診斷資料，以及哪些專案會被視為選用的診斷資料，以及所收集的事件及欄位的描述。</span><span class="sxs-lookup"><span data-stu-id="0c68c-138">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="0c68c-139">所有事件通用的資料欄位</span><span class="sxs-lookup"><span data-stu-id="0c68c-139">Data fields that are common for all events</span></span>
<span data-ttu-id="0c68c-140">有一些事件的相關資訊是所有事件通用，而不論類別或資料子類型為何。</span><span class="sxs-lookup"><span data-stu-id="0c68c-140">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="0c68c-141">下欄欄位對於所有事件都是常見的：</span><span class="sxs-lookup"><span data-stu-id="0c68c-141">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="0c68c-142">欄位</span><span class="sxs-lookup"><span data-stu-id="0c68c-142">Field</span></span>                   | <span data-ttu-id="0c68c-143">描述</span><span class="sxs-lookup"><span data-stu-id="0c68c-143">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="0c68c-144">平台</span><span class="sxs-lookup"><span data-stu-id="0c68c-144">platform</span></span>                | <span data-ttu-id="0c68c-145">應用程式執行所在平臺的廣泛分類。</span><span class="sxs-lookup"><span data-stu-id="0c68c-145">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="0c68c-146">可讓 Microsoft 識別可能發生問題的平臺，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="0c68c-146">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="0c68c-147">machine_guid</span><span class="sxs-lookup"><span data-stu-id="0c68c-147">machine_guid</span></span>            | <span data-ttu-id="0c68c-148">與裝置相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-148">Unique identifier associated with the device.</span></span> <span data-ttu-id="0c68c-149">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="0c68c-149">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="0c68c-150">sense_guid</span><span class="sxs-lookup"><span data-stu-id="0c68c-150">sense_guid</span></span>              | <span data-ttu-id="0c68c-151">與裝置相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-151">Unique identifier associated with the device.</span></span> <span data-ttu-id="0c68c-152">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="0c68c-152">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="0c68c-153">org_id</span><span class="sxs-lookup"><span data-stu-id="0c68c-153">org_id</span></span>                  | <span data-ttu-id="0c68c-154">與裝置所屬之企業相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-154">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="0c68c-155">可讓 Microsoft 識別問題是否會影響一組選擇的企業，以及受影響的企業數目。</span><span class="sxs-lookup"><span data-stu-id="0c68c-155">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="0c68c-156">主機 名</span><span class="sxs-lookup"><span data-stu-id="0c68c-156">hostname</span></span>                | <span data-ttu-id="0c68c-157">本機裝置名稱 (，但沒有 DNS 尾碼) 。</span><span class="sxs-lookup"><span data-stu-id="0c68c-157">Local device name (without DNS suffix).</span></span> <span data-ttu-id="0c68c-158">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="0c68c-158">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="0c68c-159">product_guid</span><span class="sxs-lookup"><span data-stu-id="0c68c-159">product_guid</span></span>            | <span data-ttu-id="0c68c-160">產品的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-160">Unique identifier of the product.</span></span> <span data-ttu-id="0c68c-161">可讓 Microsoft 區分影響不同產品風格的問題。</span><span class="sxs-lookup"><span data-stu-id="0c68c-161">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="0c68c-162">app_version</span><span class="sxs-lookup"><span data-stu-id="0c68c-162">app_version</span></span>             | <span data-ttu-id="0c68c-163">Linux 應用程式的 Defender for Endpoint 版本。</span><span class="sxs-lookup"><span data-stu-id="0c68c-163">Version of the Defender for Endpoint on Linux application.</span></span> <span data-ttu-id="0c68c-164">可讓 Microsoft 找出顯示問題的產品版本，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="0c68c-164">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="0c68c-165">sig_version</span><span class="sxs-lookup"><span data-stu-id="0c68c-165">sig_version</span></span>             | <span data-ttu-id="0c68c-166">安全性情報資料庫的版本。</span><span class="sxs-lookup"><span data-stu-id="0c68c-166">Version of security intelligence database.</span></span> <span data-ttu-id="0c68c-167">可讓 Microsoft 找出顯示問題的安全性情報版本，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="0c68c-167">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="0c68c-168">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="0c68c-168">supported_compressions</span></span>  | <span data-ttu-id="0c68c-169">例如，應用程式支援的壓縮演算法清單 `['gzip']` 。</span><span class="sxs-lookup"><span data-stu-id="0c68c-169">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="0c68c-170">可讓 Microsoft 瞭解哪些類型的 compressions 可以在與應用程式通訊時使用。</span><span class="sxs-lookup"><span data-stu-id="0c68c-170">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="0c68c-171">release_ring</span><span class="sxs-lookup"><span data-stu-id="0c68c-171">release_ring</span></span>            | <span data-ttu-id="0c68c-172">裝置與 (相關聯的環，例如，內幕人士快、內幕人士緩慢、實際執行) 。</span><span class="sxs-lookup"><span data-stu-id="0c68c-172">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="0c68c-173">可讓 Microsoft 識別可能發生問題的發行環，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="0c68c-173">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |

### <a name="required-diagnostic-data"></a><span data-ttu-id="0c68c-174">必要診斷資料</span><span class="sxs-lookup"><span data-stu-id="0c68c-174">Required diagnostic data</span></span>

<span data-ttu-id="0c68c-175">必要的 **診斷資料** 是必要的最少資料，以協助讓 Defender 保持在最新狀態，並且在安裝此裝置的裝置上如期執行。</span><span class="sxs-lookup"><span data-stu-id="0c68c-175">**Required diagnostic data** is the minimum data necessary to help keep Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="0c68c-176">必要的診斷資料可協助識別可能與裝置或軟體設定有關的 Microsoft Defender 端點相關問題。</span><span class="sxs-lookup"><span data-stu-id="0c68c-176">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="0c68c-177">例如，它可協助判斷在特定作業系統版本、新引進的功能，或停用特定的 Defender 功能時，是否要讓 Defender for Endpoint 功能的情況更頻繁地崩潰。</span><span class="sxs-lookup"><span data-stu-id="0c68c-177">For example, it can help determine if a Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="0c68c-178">必要的診斷資料可協助 Microsoft 偵測、診斷及修正這些問題，以加快對使用者或組織的影響。</span><span class="sxs-lookup"><span data-stu-id="0c68c-178">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="0c68c-179">軟體安裝和庫存資料事件</span><span class="sxs-lookup"><span data-stu-id="0c68c-179">Software setup and inventory data events</span></span>

<span data-ttu-id="0c68c-180">**Microsoft Defender for Endpoint 安裝/卸載**</span><span class="sxs-lookup"><span data-stu-id="0c68c-180">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="0c68c-181">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0c68c-181">The following fields are collected:</span></span>

| <span data-ttu-id="0c68c-182">欄位</span><span class="sxs-lookup"><span data-stu-id="0c68c-182">Field</span></span>            | <span data-ttu-id="0c68c-183">描述</span><span class="sxs-lookup"><span data-stu-id="0c68c-183">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="0c68c-184">correlation_id</span><span class="sxs-lookup"><span data-stu-id="0c68c-184">correlation_id</span></span>   | <span data-ttu-id="0c68c-185">與安裝相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-185">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="0c68c-186">版本</span><span class="sxs-lookup"><span data-stu-id="0c68c-186">version</span></span>          | <span data-ttu-id="0c68c-187">套件的版本。</span><span class="sxs-lookup"><span data-stu-id="0c68c-187">Version of the package.</span></span> |
| <span data-ttu-id="0c68c-188">嚴重性</span><span class="sxs-lookup"><span data-stu-id="0c68c-188">severity</span></span>         | <span data-ttu-id="0c68c-189">郵件的嚴重性 (例如，) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="0c68c-189">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="0c68c-190">code</span><span class="sxs-lookup"><span data-stu-id="0c68c-190">code</span></span>             | <span data-ttu-id="0c68c-191">描述工序的程式碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-191">Code that describes the operation.</span></span> |
| <span data-ttu-id="0c68c-192">文字</span><span class="sxs-lookup"><span data-stu-id="0c68c-192">text</span></span>             | <span data-ttu-id="0c68c-193">產品安裝相關的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="0c68c-193">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="0c68c-194">**適用於端點的 Microsoft Defender 設定**</span><span class="sxs-lookup"><span data-stu-id="0c68c-194">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="0c68c-195">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0c68c-195">The following fields are collected:</span></span>

| <span data-ttu-id="0c68c-196">欄位</span><span class="sxs-lookup"><span data-stu-id="0c68c-196">Field</span></span>                                               | <span data-ttu-id="0c68c-197">描述</span><span class="sxs-lookup"><span data-stu-id="0c68c-197">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="0c68c-198">antivirus_engine antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="0c68c-198">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="0c68c-199">是否已在裝置上啟用即時保護功能。</span><span class="sxs-lookup"><span data-stu-id="0c68c-199">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="0c68c-200">antivirus_engine antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="0c68c-200">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="0c68c-201">是否已在裝置上啟用被動式模式。</span><span class="sxs-lookup"><span data-stu-id="0c68c-201">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="0c68c-202">cloud_service。 enabled</span><span class="sxs-lookup"><span data-stu-id="0c68c-202">cloud_service.enabled</span></span>                               | <span data-ttu-id="0c68c-203">是否已在裝置上啟用雲端已傳送保護功能。</span><span class="sxs-lookup"><span data-stu-id="0c68c-203">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="0c68c-204">cloud_service。超時</span><span class="sxs-lookup"><span data-stu-id="0c68c-204">cloud_service.timeout</span></span>                               | <span data-ttu-id="0c68c-205">當應用程式與 Endpoint cloud 的 Defender 進行通訊時超時。</span><span class="sxs-lookup"><span data-stu-id="0c68c-205">Time out when the application communicates with the Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="0c68c-206">cloud_service cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="0c68c-206">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="0c68c-207">產品傳送至雲端的連續心跳之間的間隔。</span><span class="sxs-lookup"><span data-stu-id="0c68c-207">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="0c68c-208">cloud_service cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="0c68c-208">cloud_service.service_uri</span></span>                           | <span data-ttu-id="0c68c-209">用於與雲端通訊的 URI。</span><span class="sxs-lookup"><span data-stu-id="0c68c-209">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="0c68c-210">cloud_service cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="0c68c-210">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="0c68c-211">裝置的診斷層級 (必要，選用) 。</span><span class="sxs-lookup"><span data-stu-id="0c68c-211">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="0c68c-212">cloud_service cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="0c68c-212">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="0c68c-213">裝置的自動範例提交層級 (無，安全，所有) 。</span><span class="sxs-lookup"><span data-stu-id="0c68c-213">Automatic sample submission level of the device (none, safe, all).</span></span> |
| <span data-ttu-id="0c68c-214">cloud_service cloud_service.automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="0c68c-214">cloud_service.automatic_definition_update_enabled</span></span>   | <span data-ttu-id="0c68c-215">是否已開啟自動定義更新。</span><span class="sxs-lookup"><span data-stu-id="0c68c-215">Whether automatic definition update is turned on or not.</span></span> |
| <span data-ttu-id="0c68c-216">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="0c68c-216">edr.early_preview</span></span>                                   | <span data-ttu-id="0c68c-217">裝置是否應該執行 EDR 早期預覽功能。</span><span class="sxs-lookup"><span data-stu-id="0c68c-217">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="0c68c-218">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="0c68c-218">edr.group_id</span></span>                                        | <span data-ttu-id="0c68c-219">偵測及回應元件所使用的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-219">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="0c68c-220">edr 標記</span><span class="sxs-lookup"><span data-stu-id="0c68c-220">edr.tags</span></span>                                            | <span data-ttu-id="0c68c-221">使用者定義的標記。</span><span class="sxs-lookup"><span data-stu-id="0c68c-221">User-defined tags.</span></span> |
| <span data-ttu-id="0c68c-222">功能。 \[選用功能名稱\]</span><span class="sxs-lookup"><span data-stu-id="0c68c-222">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="0c68c-223">預覽功能的清單，及其是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="0c68c-223">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="0c68c-224">產品和服務使用資料事件</span><span class="sxs-lookup"><span data-stu-id="0c68c-224">Product and service usage data events</span></span>

<span data-ttu-id="0c68c-225">**安全性智慧更新報告**</span><span class="sxs-lookup"><span data-stu-id="0c68c-225">**Security intelligence update report**</span></span>

<span data-ttu-id="0c68c-226">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0c68c-226">The following fields are collected:</span></span>

| <span data-ttu-id="0c68c-227">欄位</span><span class="sxs-lookup"><span data-stu-id="0c68c-227">Field</span></span>            | <span data-ttu-id="0c68c-228">描述</span><span class="sxs-lookup"><span data-stu-id="0c68c-228">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="0c68c-229">from_version</span><span class="sxs-lookup"><span data-stu-id="0c68c-229">from_version</span></span>     | <span data-ttu-id="0c68c-230">原始安全性智慧版本。</span><span class="sxs-lookup"><span data-stu-id="0c68c-230">Original security intelligence version.</span></span> |
| <span data-ttu-id="0c68c-231">to_version</span><span class="sxs-lookup"><span data-stu-id="0c68c-231">to_version</span></span>       | <span data-ttu-id="0c68c-232">新的安全性智慧版本。</span><span class="sxs-lookup"><span data-stu-id="0c68c-232">New security intelligence version.</span></span> |
| <span data-ttu-id="0c68c-233">地位</span><span class="sxs-lookup"><span data-stu-id="0c68c-233">status</span></span>           | <span data-ttu-id="0c68c-234">表明成功或失敗之更新的狀態。</span><span class="sxs-lookup"><span data-stu-id="0c68c-234">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="0c68c-235">using_proxy</span><span class="sxs-lookup"><span data-stu-id="0c68c-235">using_proxy</span></span>      | <span data-ttu-id="0c68c-236">是否已透過 proxy 進行更新。</span><span class="sxs-lookup"><span data-stu-id="0c68c-236">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="0c68c-237">錯誤</span><span class="sxs-lookup"><span data-stu-id="0c68c-237">error</span></span>            | <span data-ttu-id="0c68c-238">如果更新失敗，則為錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-238">Error code if the update failed.</span></span> |
| <span data-ttu-id="0c68c-239">reason</span><span class="sxs-lookup"><span data-stu-id="0c68c-239">reason</span></span>           | <span data-ttu-id="0c68c-240">更新失敗時的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="0c68c-240">Error message if the update failed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="0c68c-241">產品和服務效能資料事件</span><span class="sxs-lookup"><span data-stu-id="0c68c-241">Product and service performance data events</span></span>

<span data-ttu-id="0c68c-242">**內核擴充統計資料**</span><span class="sxs-lookup"><span data-stu-id="0c68c-242">**Kernel extension statistics**</span></span>

<span data-ttu-id="0c68c-243">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0c68c-243">The following fields are collected:</span></span>

| <span data-ttu-id="0c68c-244">欄位</span><span class="sxs-lookup"><span data-stu-id="0c68c-244">Field</span></span>            | <span data-ttu-id="0c68c-245">描述</span><span class="sxs-lookup"><span data-stu-id="0c68c-245">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="0c68c-246">版本</span><span class="sxs-lookup"><span data-stu-id="0c68c-246">version</span></span>          | <span data-ttu-id="0c68c-247">Linux 上端點的版本。</span><span class="sxs-lookup"><span data-stu-id="0c68c-247">Version of Defender for Endpoint on Linux.</span></span> |
| <span data-ttu-id="0c68c-248">instance_id</span><span class="sxs-lookup"><span data-stu-id="0c68c-248">instance_id</span></span>      | <span data-ttu-id="0c68c-249">在內核擴充啟動時產生的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-249">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="0c68c-250">trace_level</span><span class="sxs-lookup"><span data-stu-id="0c68c-250">trace_level</span></span>      | <span data-ttu-id="0c68c-251">內核擴充的追蹤層級。</span><span class="sxs-lookup"><span data-stu-id="0c68c-251">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="0c68c-252">子系統</span><span class="sxs-lookup"><span data-stu-id="0c68c-252">subsystem</span></span>        | <span data-ttu-id="0c68c-253">用於即時保護的底層子系統。</span><span class="sxs-lookup"><span data-stu-id="0c68c-253">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="0c68c-254">ipc。連接</span><span class="sxs-lookup"><span data-stu-id="0c68c-254">ipc.connects</span></span>     | <span data-ttu-id="0c68c-255">內核擴充所接收的連線要求數目。</span><span class="sxs-lookup"><span data-stu-id="0c68c-255">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="0c68c-256">ipc。拒絕</span><span class="sxs-lookup"><span data-stu-id="0c68c-256">ipc.rejects</span></span>      | <span data-ttu-id="0c68c-257">內核擴充所拒絕的連線要求數目。</span><span class="sxs-lookup"><span data-stu-id="0c68c-257">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="0c68c-258">ipc。已連線</span><span class="sxs-lookup"><span data-stu-id="0c68c-258">ipc.connected</span></span>    | <span data-ttu-id="0c68c-259">是否有任何作用中連接至內核分機。</span><span class="sxs-lookup"><span data-stu-id="0c68c-259">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="0c68c-260">支援資料</span><span class="sxs-lookup"><span data-stu-id="0c68c-260">Support data</span></span>

<span data-ttu-id="0c68c-261">**診斷記錄**</span><span class="sxs-lookup"><span data-stu-id="0c68c-261">**Diagnostic logs**</span></span>

<span data-ttu-id="0c68c-262">僅當使用者同意提交功能時，才會收集診斷記錄。</span><span class="sxs-lookup"><span data-stu-id="0c68c-262">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="0c68c-263">下列檔案會收集為支援記錄檔的一部分：</span><span class="sxs-lookup"><span data-stu-id="0c68c-263">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="0c68c-264">*/Var/log/microsoft/mdatp* 下的所有檔案</span><span class="sxs-lookup"><span data-stu-id="0c68c-264">All files under */var/log/microsoft/mdatp*</span></span>
- <span data-ttu-id="0c68c-265">由 Linux 上的 Defender for Endpoint 所建立及使用之 */etc/opt/microsoft/mdatp* 底下的檔案子集</span><span class="sxs-lookup"><span data-stu-id="0c68c-265">Subset of files under */etc/opt/microsoft/mdatp* that are created and used by Defender for Endpoint on Linux</span></span>
- <span data-ttu-id="0c68c-266">*/Var/log/microsoft_mdatp_ \* .log 中的* 產品安裝和卸載記錄</span><span class="sxs-lookup"><span data-stu-id="0c68c-266">Product installation and uninstallation logs under */var/log/microsoft_mdatp_\*.log*</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="0c68c-267">選擇性診斷資料</span><span class="sxs-lookup"><span data-stu-id="0c68c-267">Optional diagnostic data</span></span>

<span data-ttu-id="0c68c-268">**選用診斷資料** 是額外的資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷及修正問題。</span><span class="sxs-lookup"><span data-stu-id="0c68c-268">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="0c68c-269">如果您選擇將選用的診斷資料傳送給我們，則也會包含必要的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="0c68c-269">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="0c68c-270">選用診斷資料的範例包括 Microsoft 收集有關產品設定 (的資料，例如，) 裝置上的排除專案數目，以及產品) 的元件效能 (匯總度量。</span><span class="sxs-lookup"><span data-stu-id="0c68c-270">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="0c68c-271">軟體安裝和庫存資料事件</span><span class="sxs-lookup"><span data-stu-id="0c68c-271">Software setup and inventory data events</span></span>

<span data-ttu-id="0c68c-272">**適用於端點的 Microsoft Defender 設定**</span><span class="sxs-lookup"><span data-stu-id="0c68c-272">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="0c68c-273">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0c68c-273">The following fields are collected:</span></span>

| <span data-ttu-id="0c68c-274">欄位</span><span class="sxs-lookup"><span data-stu-id="0c68c-274">Field</span></span>                                              | <span data-ttu-id="0c68c-275">描述</span><span class="sxs-lookup"><span data-stu-id="0c68c-275">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="0c68c-276">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="0c68c-276">connection_retry_timeout</span></span>                           | <span data-ttu-id="0c68c-277">與雲端通訊時，連線重試超時。</span><span class="sxs-lookup"><span data-stu-id="0c68c-277">Connection retry time-out when communication with the cloud.</span></span> |
| <span data-ttu-id="0c68c-278">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="0c68c-278">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="0c68c-279">產品快取的大小。</span><span class="sxs-lookup"><span data-stu-id="0c68c-279">Size of the product cache.</span></span> |
| <span data-ttu-id="0c68c-280">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="0c68c-280">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="0c68c-281">每天上傳的崩潰記錄檔限制。</span><span class="sxs-lookup"><span data-stu-id="0c68c-281">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="0c68c-282">antivirus_engine。排除 [] .is_directory</span><span class="sxs-lookup"><span data-stu-id="0c68c-282">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="0c68c-283">掃描的排除是否為目錄。</span><span class="sxs-lookup"><span data-stu-id="0c68c-283">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="0c68c-284">antivirus_engine。排除 [] 路徑</span><span class="sxs-lookup"><span data-stu-id="0c68c-284">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="0c68c-285">排除在掃描之外的路徑。</span><span class="sxs-lookup"><span data-stu-id="0c68c-285">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="0c68c-286">antivirus_engine。排除 [] 副檔名</span><span class="sxs-lookup"><span data-stu-id="0c68c-286">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="0c68c-287">排除來自掃描的分機號碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-287">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="0c68c-288">antivirus_engine。排除 []。名稱</span><span class="sxs-lookup"><span data-stu-id="0c68c-288">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="0c68c-289">排除在掃描之外的檔案名。</span><span class="sxs-lookup"><span data-stu-id="0c68c-289">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="0c68c-290">antivirus_engine antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="0c68c-290">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="0c68c-291">產品快取的大小。</span><span class="sxs-lookup"><span data-stu-id="0c68c-291">Size of the product cache.</span></span> |
| <span data-ttu-id="0c68c-292">antivirus_engine antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="0c68c-292">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="0c68c-293">掃描時所用的執行緒數目上限。</span><span class="sxs-lookup"><span data-stu-id="0c68c-293">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="0c68c-294">antivirus_engine antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="0c68c-294">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="0c68c-295">在從隔離區還原的檔案之前，可再次偵測到超時。</span><span class="sxs-lookup"><span data-stu-id="0c68c-295">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="0c68c-296">antivirus_engine antivirus_engine.threat_type_settings</span><span class="sxs-lookup"><span data-stu-id="0c68c-296">antivirus_engine.threat_type_settings</span></span>              | <span data-ttu-id="0c68c-297">產品如何處理不同威脅類型的設定。</span><span class="sxs-lookup"><span data-stu-id="0c68c-297">Configuration for how different threat types are handled by the product.</span></span> |
| <span data-ttu-id="0c68c-298">filesystem_scanner filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="0c68c-298">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="0c68c-299">完整掃描目錄。</span><span class="sxs-lookup"><span data-stu-id="0c68c-299">Full scan directory.</span></span> |
| <span data-ttu-id="0c68c-300">filesystem_scanner filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="0c68c-300">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="0c68c-301">快速掃描中所用的目錄清單。</span><span class="sxs-lookup"><span data-stu-id="0c68c-301">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="0c68c-302">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="0c68c-302">edr.latency_mode</span></span>                                   | <span data-ttu-id="0c68c-303">偵測及回應元件所使用的延遲模式。</span><span class="sxs-lookup"><span data-stu-id="0c68c-303">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="0c68c-304">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="0c68c-304">edr.proxy_address</span></span>                                  | <span data-ttu-id="0c68c-305">偵測及回應元件所使用的 Proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="0c68c-305">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="0c68c-306">**Microsoft 自動更新設定**</span><span class="sxs-lookup"><span data-stu-id="0c68c-306">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="0c68c-307">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0c68c-307">The following fields are collected:</span></span>

| <span data-ttu-id="0c68c-308">欄位</span><span class="sxs-lookup"><span data-stu-id="0c68c-308">Field</span></span>                       | <span data-ttu-id="0c68c-309">描述</span><span class="sxs-lookup"><span data-stu-id="0c68c-309">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="0c68c-310">how_to_check</span><span class="sxs-lookup"><span data-stu-id="0c68c-310">how_to_check</span></span>                | <span data-ttu-id="0c68c-311">會決定如何檢查產品更新 (例如，自動或手動) 。</span><span class="sxs-lookup"><span data-stu-id="0c68c-311">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="0c68c-312">channel_name</span><span class="sxs-lookup"><span data-stu-id="0c68c-312">channel_name</span></span>                | <span data-ttu-id="0c68c-313">更新與裝置相關聯的通道。</span><span class="sxs-lookup"><span data-stu-id="0c68c-313">Update channel associated with the device.</span></span> |
| <span data-ttu-id="0c68c-314">manifest_server</span><span class="sxs-lookup"><span data-stu-id="0c68c-314">manifest_server</span></span>             | <span data-ttu-id="0c68c-315">用於下載更新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0c68c-315">Server used for downloading updates.</span></span> |
| <span data-ttu-id="0c68c-316">update_cache</span><span class="sxs-lookup"><span data-stu-id="0c68c-316">update_cache</span></span>                | <span data-ttu-id="0c68c-317">用來儲存更新的快取位置。</span><span class="sxs-lookup"><span data-stu-id="0c68c-317">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="0c68c-318">產品和服務使用</span><span class="sxs-lookup"><span data-stu-id="0c68c-318">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="0c68c-319">已開始診斷記錄上載報告</span><span class="sxs-lookup"><span data-stu-id="0c68c-319">Diagnostic log upload started report</span></span>

<span data-ttu-id="0c68c-320">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0c68c-320">The following fields are collected:</span></span>

| <span data-ttu-id="0c68c-321">欄位</span><span class="sxs-lookup"><span data-stu-id="0c68c-321">Field</span></span>            | <span data-ttu-id="0c68c-322">描述</span><span class="sxs-lookup"><span data-stu-id="0c68c-322">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="0c68c-323">sha256</span><span class="sxs-lookup"><span data-stu-id="0c68c-323">sha256</span></span>           | <span data-ttu-id="0c68c-324">支援記錄檔的 SHA256 識別碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-324">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="0c68c-325">Size</span><span class="sxs-lookup"><span data-stu-id="0c68c-325">size</span></span>             | <span data-ttu-id="0c68c-326">支援記錄檔的大小。</span><span class="sxs-lookup"><span data-stu-id="0c68c-326">Size of the support log.</span></span> |
| <span data-ttu-id="0c68c-327">original_path</span><span class="sxs-lookup"><span data-stu-id="0c68c-327">original_path</span></span>    | <span data-ttu-id="0c68c-328">支援記錄檔的路徑 (always 低於 */var/opt/microsoft/mdatp/wdavdiag/*) 。</span><span class="sxs-lookup"><span data-stu-id="0c68c-328">Path to the support log (always under */var/opt/microsoft/mdatp/wdavdiag/*).</span></span> |
| <span data-ttu-id="0c68c-329">format</span><span class="sxs-lookup"><span data-stu-id="0c68c-329">format</span></span>           | <span data-ttu-id="0c68c-330">支援記錄檔的格式。</span><span class="sxs-lookup"><span data-stu-id="0c68c-330">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="0c68c-331">診斷記錄上載已完成報告</span><span class="sxs-lookup"><span data-stu-id="0c68c-331">Diagnostic log upload completed report</span></span>

<span data-ttu-id="0c68c-332">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0c68c-332">The following fields are collected:</span></span>

| <span data-ttu-id="0c68c-333">欄位</span><span class="sxs-lookup"><span data-stu-id="0c68c-333">Field</span></span>            | <span data-ttu-id="0c68c-334">描述</span><span class="sxs-lookup"><span data-stu-id="0c68c-334">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="0c68c-335">request_id</span><span class="sxs-lookup"><span data-stu-id="0c68c-335">request_id</span></span>       | <span data-ttu-id="0c68c-336">支援記錄檔上載要求的相互關聯識別碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-336">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="0c68c-337">sha256</span><span class="sxs-lookup"><span data-stu-id="0c68c-337">sha256</span></span>           | <span data-ttu-id="0c68c-338">支援記錄檔的 SHA256 識別碼。</span><span class="sxs-lookup"><span data-stu-id="0c68c-338">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="0c68c-339">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="0c68c-339">blob_sas_uri</span></span>     | <span data-ttu-id="0c68c-340">應用程式用來上傳支援記錄的 URI。</span><span class="sxs-lookup"><span data-stu-id="0c68c-340">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="0c68c-341">產品和服務效能資料事件</span><span class="sxs-lookup"><span data-stu-id="0c68c-341">Product and service performance data events</span></span>

<span data-ttu-id="0c68c-342">**非預期的應用程式結束 (當機)**</span><span class="sxs-lookup"><span data-stu-id="0c68c-342">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="0c68c-343">非預期的應用程式結束，以及在該情況下應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="0c68c-343">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="0c68c-344">**內核擴充統計資料**</span><span class="sxs-lookup"><span data-stu-id="0c68c-344">**Kernel extension statistics**</span></span>

<span data-ttu-id="0c68c-345">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="0c68c-345">The following fields are collected:</span></span>

| <span data-ttu-id="0c68c-346">欄位</span><span class="sxs-lookup"><span data-stu-id="0c68c-346">Field</span></span>                          | <span data-ttu-id="0c68c-347">描述</span><span class="sxs-lookup"><span data-stu-id="0c68c-347">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="0c68c-348">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="0c68c-348">pkt_ack_timeout</span></span>                | <span data-ttu-id="0c68c-349">下列屬性是匯總數值，代表自內核延伸啟動之後發生的事件計數。</span><span class="sxs-lookup"><span data-stu-id="0c68c-349">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="0c68c-350">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="0c68c-350">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="0c68c-351">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="0c68c-351">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="0c68c-352">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="0c68c-352">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="0c68c-353">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="0c68c-353">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="0c68c-354">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="0c68c-354">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="0c68c-355">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="0c68c-355">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="0c68c-356">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="0c68c-356">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="0c68c-357">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="0c68c-357">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="0c68c-358">ipc ack。超時</span><span class="sxs-lookup"><span data-stu-id="0c68c-358">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="0c68c-359">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="0c68c-359">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="0c68c-360">ackd</span><span class="sxs-lookup"><span data-stu-id="0c68c-360">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="0c68c-361">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="0c68c-361">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="0c68c-362">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="0c68c-362">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="0c68c-363">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="0c68c-363">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="0c68c-364">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="0c68c-364">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="0c68c-365">kauth vnode</span><span class="sxs-lookup"><span data-stu-id="0c68c-365">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="0c68c-366">vnode 讀取的 kauth</span><span class="sxs-lookup"><span data-stu-id="0c68c-366">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="0c68c-367">kauth vnode</span><span class="sxs-lookup"><span data-stu-id="0c68c-367">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="0c68c-368">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="0c68c-368">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="0c68c-369">vnode kauth</span><span class="sxs-lookup"><span data-stu-id="0c68c-369">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="0c68c-370">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="0c68c-370">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="0c68c-371">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="0c68c-371">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="0c68c-372">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="0c68c-372">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="0c68c-373">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="0c68c-373">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="0c68c-374">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="0c68c-374">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="0c68c-375">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="0c68c-375">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="0c68c-376">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="0c68c-376">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="0c68c-377">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="0c68c-377">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="0c68c-378">vnode 建立 kauth</span><span class="sxs-lookup"><span data-stu-id="0c68c-378">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="0c68c-379">vnode 移動的 kauth</span><span class="sxs-lookup"><span data-stu-id="0c68c-379">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="0c68c-380">vnode 裝載 kauth</span><span class="sxs-lookup"><span data-stu-id="0c68c-380">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="0c68c-381">kauth 拒絕的 vnode</span><span class="sxs-lookup"><span data-stu-id="0c68c-381">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="0c68c-382">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="0c68c-382">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="0c68c-383">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="0c68c-383">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="0c68c-384">ipc.kauth.file_op 遮罩</span><span class="sxs-lookup"><span data-stu-id="0c68c-384">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="0c68c-385">ipc.kauth_file_op。開啟</span><span class="sxs-lookup"><span data-stu-id="0c68c-385">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="0c68c-386">ipc.kauth.file_op。關閉</span><span class="sxs-lookup"><span data-stu-id="0c68c-386">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="0c68c-387">ipc.kauth.file_op ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="0c68c-387">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="0c68c-388">ipc.kauth.file_op。移動</span><span class="sxs-lookup"><span data-stu-id="0c68c-388">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="0c68c-389">ipc.kauth.file_op。連結</span><span class="sxs-lookup"><span data-stu-id="0c68c-389">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="0c68c-390">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="0c68c-390">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="0c68c-391">ipc.kauth.file_op。移除</span><span class="sxs-lookup"><span data-stu-id="0c68c-391">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="0c68c-392">ipc.kauth.file_op。卸載</span><span class="sxs-lookup"><span data-stu-id="0c68c-392">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="0c68c-393">ipc.kauth.file_op 的派生</span><span class="sxs-lookup"><span data-stu-id="0c68c-393">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="0c68c-394">ipc.kauth.file_op。建立</span><span class="sxs-lookup"><span data-stu-id="0c68c-394">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="0c68c-395">資源</span><span class="sxs-lookup"><span data-stu-id="0c68c-395">Resources</span></span>

- [<span data-ttu-id="0c68c-396">Microsoft 中的隱私權</span><span class="sxs-lookup"><span data-stu-id="0c68c-396">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
