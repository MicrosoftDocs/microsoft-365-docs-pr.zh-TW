---
title: 修正由整備評估工具發現的問題
description: 針對每個工具找到的問題所採取的詳細動作
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c342ea9f662d883883755d2f67e5c25ffabddf83
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948406"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="860b0-104">修正由整備評估工具發現的問題</span><span class="sxs-lookup"><span data-stu-id="860b0-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="860b0-105">針對每個檢查，該工具會報告下列四個可能的結果之一：</span><span class="sxs-lookup"><span data-stu-id="860b0-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="860b0-106">結果</span><span class="sxs-lookup"><span data-stu-id="860b0-106">Result</span></span>  |<span data-ttu-id="860b0-107">意義</span><span class="sxs-lookup"><span data-stu-id="860b0-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="860b0-108">就緒</span><span class="sxs-lookup"><span data-stu-id="860b0-108">Ready</span></span>     | <span data-ttu-id="860b0-109">完成註冊之前，不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="860b0-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="860b0-110">諮詢</span><span class="sxs-lookup"><span data-stu-id="860b0-110">Advisory</span></span>    | <span data-ttu-id="860b0-111">請遵循工具或本文中的步驟，以取得註冊和使用者的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="860b0-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="860b0-112">您 *可以* 完成註冊，但是必須先修正這些問題，再部署第一個裝置。</span><span class="sxs-lookup"><span data-stu-id="860b0-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="860b0-113">未就緒</span><span class="sxs-lookup"><span data-stu-id="860b0-113">Not ready</span></span> | <span data-ttu-id="860b0-114">*如果您未修正這些問題，註冊將會失敗。*</span><span class="sxs-lookup"><span data-stu-id="860b0-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="860b0-115">請遵循工具或本文中的步驟加以解決。</span><span class="sxs-lookup"><span data-stu-id="860b0-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="860b0-116">錯誤</span><span class="sxs-lookup"><span data-stu-id="860b0-116">Error</span></span> | <span data-ttu-id="860b0-117">您所使用的 Azure Active Director (AD) 角色，沒有足夠的許可權可執行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="860b0-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="860b0-118">Microsoft Intune 設定</span><span class="sxs-lookup"><span data-stu-id="860b0-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="860b0-119">Autopilot 部署設定檔</span><span class="sxs-lookup"><span data-stu-id="860b0-119">Autopilot deployment profile</span></span>

<span data-ttu-id="860b0-120">您不應該有任何現有的 Autopilot 設定檔，是 Microsoft Managed Desktop 所使用的指派或動態群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="860b0-121">Microsoft 受管理的桌面會使用 Autopilot 布建新裝置。</span><span class="sxs-lookup"><span data-stu-id="860b0-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="860b0-122">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-122">**Not ready**</span></span>

<span data-ttu-id="860b0-123">您有指派給所有裝置的 Autopilot 設定檔。</span><span class="sxs-lookup"><span data-stu-id="860b0-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="860b0-124">如需步驟，請參閱 [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="860b0-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="860b0-125">Microsoft 受管理的桌上型電腦註冊後，請將您的 Autopilot 原則設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="860b0-126">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-126">**Advisory**</span></span>

<span data-ttu-id="860b0-127">請確定您的 Autopilot 設定檔目標是指派或動態 Azure AD 群組，但不包含將在註冊時建立的 Microsoft 受管理桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="860b0-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="860b0-128">如需步驟，請參閱 [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="860b0-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="860b0-129">Microsoft 受管理的桌上型電腦註冊後，請將您的 Autopilot 原則設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="860b0-130">憑證連接器</span><span class="sxs-lookup"><span data-stu-id="860b0-130">Certificate connectors</span></span>

<span data-ttu-id="860b0-131">如果您有任何您想要在 Microsoft 受管理的電腦上登錄之裝置使用的憑證連接器，連接器就不能有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="860b0-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="860b0-132">下列其中一項諮詢只適用于您的情況，所以請務必仔細檢查。</span><span class="sxs-lookup"><span data-stu-id="860b0-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="860b0-133">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-133">**Advisory**</span></span>

<span data-ttu-id="860b0-134">不存在任何憑證連接器。</span><span class="sxs-lookup"><span data-stu-id="860b0-134">No certificate connectors are present.</span></span> <span data-ttu-id="860b0-135">您可能不需要任何連接器，但您應評估您是否需要部分網路連接至 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="860b0-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="860b0-136">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="860b0-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="860b0-137">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-137">**Advisory**</span></span>

<span data-ttu-id="860b0-138">至少有一個憑證連接器有錯誤。</span><span class="sxs-lookup"><span data-stu-id="860b0-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="860b0-139">如果您需要此連接器才能連線至 Microsoft 受管理的桌面裝置，您必須解決該錯誤。</span><span class="sxs-lookup"><span data-stu-id="860b0-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="860b0-140">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="860b0-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="860b0-141">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-141">**Advisory**</span></span>

<span data-ttu-id="860b0-142">您至少有一個憑證連接器，而且不會報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="860b0-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="860b0-143">不過，您可能需要建立設定檔，以重複使用 Microsoft 受管理的桌面裝置的連接器。</span><span class="sxs-lookup"><span data-stu-id="860b0-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="860b0-144">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="860b0-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="860b0-145">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="860b0-145">Conditional access policies</span></span>

<span data-ttu-id="860b0-146">Azure AD 組織中的條件式存取原則不得以任何 Microsoft 管理桌面使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="860b0-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="860b0-147">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-147">**Not ready**</span></span>

<span data-ttu-id="860b0-148">您有至少一個目標為所有使用者的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="860b0-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="860b0-149">將原則重設為面向不包含將在註冊時建立之 Microsoft Managed Desktop service 帳戶之 Azure AD 群組的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="860b0-150">如需步驟，請參閱 [條件式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="860b0-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="860b0-151">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-151">**Advisory**</span></span>

<span data-ttu-id="860b0-152">請確定任何條件式存取原則都排除了 **現代的 Workplace Service 帳戶** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="860b0-153">如需步驟，請參閱 [調整條件式存取](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="860b0-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="860b0-154">**新式的 Workplace Service 帳戶** Azure AD 群組是我們在您註冊時，為服務建立的動態群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="860b0-155">註冊後，您必須回到以排除此群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="860b0-156">如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="860b0-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="860b0-157">**Error**</span><span class="sxs-lookup"><span data-stu-id="860b0-157">**Error**</span></span>

<span data-ttu-id="860b0-158">Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="860b0-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="860b0-159">您也需要指派的任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="860b0-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="860b0-160">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="860b0-160">Security Reader</span></span>
- <span data-ttu-id="860b0-161">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="860b0-161">Security Administrator</span></span>
- <span data-ttu-id="860b0-162">條件式存取管理員</span><span class="sxs-lookup"><span data-stu-id="860b0-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="860b0-163">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="860b0-163">Global Reader</span></span>
- <span data-ttu-id="860b0-164">裝置管理員</span><span class="sxs-lookup"><span data-stu-id="860b0-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="860b0-165">裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="860b0-165">Device Compliance policies</span></span>

<span data-ttu-id="860b0-166">Azure AD 組織中的 Intune 裝置相容性原則不得以 Microsoft 受管理的桌面使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="860b0-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="860b0-167">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-167">**Not ready**</span></span>

<span data-ttu-id="860b0-168">您至少具有一個針對所有使用者的符合性原則。</span><span class="sxs-lookup"><span data-stu-id="860b0-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="860b0-169">將原則重設為面向不包含任何 Microsoft 受管理桌面使用者的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="860b0-170">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="860b0-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="860b0-171">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-171">**Advisory**</span></span>

<span data-ttu-id="860b0-172">請確定任何您沒有的相容性原則都包含任何 Microsoft 受管理的桌面使用者。</span><span class="sxs-lookup"><span data-stu-id="860b0-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="860b0-173">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="860b0-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="860b0-174">裝置設定原則</span><span class="sxs-lookup"><span data-stu-id="860b0-174">Device Configuration policies</span></span>

<span data-ttu-id="860b0-175">Azure AD 組織中的 Intune 裝置設定原則不得針對任何 Microsoft 管理桌面裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="860b0-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="860b0-176">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-176">**Not ready**</span></span>

<span data-ttu-id="860b0-177">您至少要有一個設定原則，針對所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="860b0-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="860b0-178">針對不包含任何 Microsoft 受管理桌面裝置的特定 Azure AD 群組，將原則重設為 [目標]。</span><span class="sxs-lookup"><span data-stu-id="860b0-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="860b0-179">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="860b0-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="860b0-180">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-180">**Advisory**</span></span>

<span data-ttu-id="860b0-181">請確定任何您沒有的相容性原則都包含任何 Microsoft 受管理的桌面裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="860b0-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="860b0-182">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="860b0-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="860b0-183">裝置類型限制</span><span class="sxs-lookup"><span data-stu-id="860b0-183">Device type restrictions</span></span>

<span data-ttu-id="860b0-184">Microsoft 受管理的桌面裝置必須能夠在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="860b0-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="860b0-185">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-185">**Not ready**</span></span>

<span data-ttu-id="860b0-186">依照 [設定註冊限制](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) 中的步驟，將設定變更為 [ **允許** ]。</span><span class="sxs-lookup"><span data-stu-id="860b0-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="860b0-187">註冊狀態頁面</span><span class="sxs-lookup"><span data-stu-id="860b0-187">Enrollment Status Page</span></span>

<span data-ttu-id="860b0-188">您目前已啟用「註冊狀態」頁面 (ESP) 。</span><span class="sxs-lookup"><span data-stu-id="860b0-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="860b0-189">如果您參與此功能的公開預覽，可以略過此專案。</span><span class="sxs-lookup"><span data-stu-id="860b0-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="860b0-190">如需詳細資訊，請參閱 [使用 Autopilot 和註冊狀態頁面的初次執行體驗](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="860b0-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="860b0-191">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-191">**Not ready**</span></span>

<span data-ttu-id="860b0-192">您已設定 ESP 預設設定檔來 **顯示應用程式和設定檔設定進度** 。</span><span class="sxs-lookup"><span data-stu-id="860b0-192">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="860b0-193">停用此設定，或遵循 [設定 [註冊狀態] 頁面](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)中的步驟，確定任何 Azure AD 群組的指派均未包含 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="860b0-193">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="860b0-194">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-194">**Advisory**</span></span>

<span data-ttu-id="860b0-195">請確定任何具有「 **顯示應用程式和設定檔設定進度** 」設定的設定檔都未指派給任何包含 Microsoft 受管理的桌面裝置的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="860b0-196">如需詳細資訊，請參閱 [設定註冊狀態頁面](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="860b0-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="860b0-197">Intune 登記</span><span class="sxs-lookup"><span data-stu-id="860b0-197">Intune enrollment</span></span>

<span data-ttu-id="860b0-198">Azure AD 組織中的 Windows 10 裝置必須在 Intune 中自動註冊。</span><span class="sxs-lookup"><span data-stu-id="860b0-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="860b0-199">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-199">**Advisory**</span></span>

<span data-ttu-id="860b0-200">確定 MDM 使用者範圍已設定為 **部分** 或 **全部** （非 **無** ）。</span><span class="sxs-lookup"><span data-stu-id="860b0-200">Make sure the MDM User scope is set to **Some** or **All** , not **None**.</span></span> <span data-ttu-id="860b0-201">如果您選擇 [ **部分** ]，請在註冊後再進行註冊，然後選取 [ **現代工作場所-** **群組** 的所有 Azure AD 群組]。</span><span class="sxs-lookup"><span data-stu-id="860b0-201">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="860b0-202">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="860b0-202">Microsoft Store for Business</span></span>

<span data-ttu-id="860b0-203">我們使用 Microsoft Store for Business，可讓您下載公司入口網站，以部署某些應用程式，例如 Microsoft Project 和 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="860b0-203">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="860b0-204">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-204">**Not ready**</span></span>

<span data-ttu-id="860b0-205">商務用 Microsoft Store 未啟用或未與 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="860b0-205">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="860b0-206">如需詳細資訊，請參閱 how [to 使用 Microsoft Intune 管理大量購買的應用程式](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) ，以及 [在裝置上安裝 Intune 公司入口網站](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="860b0-206">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="860b0-207">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="860b0-207">Multi-factor authentication</span></span>

<span data-ttu-id="860b0-208">多重要素驗證不得意外套用至 Microsoft Managed Desktop service 帳戶。</span><span class="sxs-lookup"><span data-stu-id="860b0-208">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="860b0-209">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-209">**Not ready**</span></span>

<span data-ttu-id="860b0-210">您有部分多重要素驗證 (MFA) 原則，設定為指派給所有使用者的條件式存取原則的「必要」。</span><span class="sxs-lookup"><span data-stu-id="860b0-210">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="860b0-211">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="860b0-211">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="860b0-212">如需詳細資訊，請參閱 [條件式存取原則](#conditional-access-policies) 和 [條件式存取：針對所有使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="860b0-212">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="860b0-213">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-213">**Advisory**</span></span>

<span data-ttu-id="860b0-214">請確定任何需要 MFA 的條件式存取原則排除 **新式的 Workplace-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-214">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="860b0-215">如需詳細資訊，請參閱 [條件式存取原則](#conditional-access-policies) 和 [條件式存取：針對所有使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="860b0-215">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="860b0-216">**新式的工作場所-所有** Azure AD 群組是我們在您註冊 Microsoft Managed Desktop 時所建立的動態群組，所以您必須在註冊後傳回排除此群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-216">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="860b0-217">**Error**</span><span class="sxs-lookup"><span data-stu-id="860b0-217">**Error**</span></span>

<span data-ttu-id="860b0-218">Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="860b0-218">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="860b0-219">您也需要指派的任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="860b0-219">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="860b0-220">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="860b0-220">Security Reader</span></span>
- <span data-ttu-id="860b0-221">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="860b0-221">Security Administrator</span></span>
- <span data-ttu-id="860b0-222">條件式存取管理員</span><span class="sxs-lookup"><span data-stu-id="860b0-222">Conditional Access Administrator</span></span>
- <span data-ttu-id="860b0-223">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="860b0-223">Global Reader</span></span>
- <span data-ttu-id="860b0-224">裝置管理員</span><span class="sxs-lookup"><span data-stu-id="860b0-224">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="860b0-225">PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="860b0-225">PowerShell scripts</span></span>

<span data-ttu-id="860b0-226">Windows PowerShell 腳本無法指派為以 Microsoft 受管理的桌面裝置為目標的方式。</span><span class="sxs-lookup"><span data-stu-id="860b0-226">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="860b0-227">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-227">**Advisory**</span></span>

<span data-ttu-id="860b0-228">確定您的 Azure AD 組織中的 Windows PowerShell 腳本並未以任何 Microsoft 管理桌面裝置或使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="860b0-228">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="860b0-229">請勿指派 PowerShell 腳本來設定所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="860b0-229">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="860b0-230">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="860b0-230">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="860b0-231">如需詳細資訊，請參閱在 [Intune 中使用 Windows 10 裝置上的 PowerShell 腳本](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="860b0-231">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="860b0-232">區域</span><span class="sxs-lookup"><span data-stu-id="860b0-232">Region</span></span>

<span data-ttu-id="860b0-233">您的區域必須支援 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="860b0-233">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="860b0-234">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-234">**Not ready**</span></span>

<span data-ttu-id="860b0-235">Microsoft 受管理的電腦目前不支援您的 Azure AD 組織區域。</span><span class="sxs-lookup"><span data-stu-id="860b0-235">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="860b0-236">如需詳細資訊，請參閱 [Microsoft 受管理的桌面支援的地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="860b0-236">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="860b0-237">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-237">**Advisory**</span></span>

<span data-ttu-id="860b0-238">Microsoft 受管理的電腦不支援 Azure AD 組織所在的一或多個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="860b0-238">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="860b0-239">如需詳細資訊，請參閱 [Microsoft 受管理的桌面支援的地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="860b0-239">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="860b0-240">安全性基準</span><span class="sxs-lookup"><span data-stu-id="860b0-240">Security baselines</span></span>

<span data-ttu-id="860b0-241">安全性基準原則不應該以任何 Microsoft 受管理的桌面裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="860b0-241">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="860b0-242">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-242">**Not ready**</span></span>

<span data-ttu-id="860b0-243">您有一個針對所有使用者、所有裝置或兩者的安全性基準設定檔。</span><span class="sxs-lookup"><span data-stu-id="860b0-243">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="860b0-244">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="860b0-244">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="860b0-245">如需步驟，請參閱 [使用安全性基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="860b0-245">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="860b0-246">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-246">**Advisory**</span></span>

<span data-ttu-id="860b0-247">請確定所有的安全性基準原則都排除 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="860b0-247">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="860b0-248">如需步驟，請參閱 [使用安全性基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="860b0-248">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="860b0-249">**新式的工作場所裝置-所有** Azure AD 群組是我們在您註冊 Microsoft Managed Desktop 時所建立的動態群組，所以您必須在註冊後傳回排除此群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-249">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="860b0-250">Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="860b0-250">Windows apps</span></span>

<span data-ttu-id="860b0-251">查看您要讓 Microsoft 受管理的桌面使用者擁有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="860b0-251">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="860b0-252">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-252">**Advisory**</span></span>

<span data-ttu-id="860b0-253">您應該準備要讓 Microsoft 受管理的桌面使用者擁有的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="860b0-253">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="860b0-254">請確定您可以透過 Intune 部署這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="860b0-254">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="860b0-255">如需詳細資訊，請參閱 [Microsoft Managed Desktop 中的應用程式](apps.md)。</span><span class="sxs-lookup"><span data-stu-id="860b0-255">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="860b0-256">您可以要求 Microsoft 帳戶代表在 Microsoft 端點 Configuration Manager 中查詢，以識別準備好要遷移至 Intune 或需要調整的應用程式。</span><span class="sxs-lookup"><span data-stu-id="860b0-256">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="860b0-257">Windows Hello 企業版</span><span class="sxs-lookup"><span data-stu-id="860b0-257">Windows Hello for Business</span></span>

<span data-ttu-id="860b0-258">Microsoft 受管理的桌面需要啟用 Windows Hello 企業版功能。</span><span class="sxs-lookup"><span data-stu-id="860b0-258">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="860b0-259">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-259">**Not ready**</span></span>

<span data-ttu-id="860b0-260">Windows Hello 企業版已停用。</span><span class="sxs-lookup"><span data-stu-id="860b0-260">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="860b0-261">遵循[建立 Windows Hello 企業版原則](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用</span><span class="sxs-lookup"><span data-stu-id="860b0-261">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="860b0-262">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-262">**Advisory**</span></span>

<span data-ttu-id="860b0-263">未設定 Windows Hello 企業版。</span><span class="sxs-lookup"><span data-stu-id="860b0-263">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="860b0-264">遵循 [建立 Windows Hello 企業版原則](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用它。</span><span class="sxs-lookup"><span data-stu-id="860b0-264">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="860b0-265">Windows 10 更新環</span><span class="sxs-lookup"><span data-stu-id="860b0-265">Windows 10 update rings</span></span>

<span data-ttu-id="860b0-266">Intune 中的「Windows 10 更新環路」原則不得以 Microsoft 受管理的桌面裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="860b0-266">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="860b0-267">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-267">**Not ready**</span></span>

<span data-ttu-id="860b0-268">您有一個「更新鈴聲」原則，針對所有裝置、所有使用者或兩者。</span><span class="sxs-lookup"><span data-stu-id="860b0-268">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="860b0-269">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="860b0-269">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="860b0-270">如需步驟，請參閱 [在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="860b0-270">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="860b0-271">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-271">**Advisory**</span></span>

<span data-ttu-id="860b0-272">請確定任何更新環原則您已排除現代的 **工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-272">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="860b0-273">如果您已將 Azure AD 使用者群組指派給這些原則，請確定任何更新環原則您也排除了 **新式的 Workplace-所有** 包含您的 Microsoft 受管理桌面使用者的 azure ad 群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-273">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group which includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="860b0-274">如需步驟，請參閱 [在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="860b0-274">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="860b0-275">兩個 **新式的工作場所裝置-所有** 及 **現代的工作場所-所有** Azure AD 群組都是在您註冊 Microsoft Managed Desktop 時所建立的群組，所以您必須回到註冊後再排除此群組。</span><span class="sxs-lookup"><span data-stu-id="860b0-275">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="860b0-276">Azure Active Directory 設定</span><span class="sxs-lookup"><span data-stu-id="860b0-276">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="860b0-277">專用訂閱</span><span class="sxs-lookup"><span data-stu-id="860b0-277">Ad hoc subscriptions</span></span>

<span data-ttu-id="860b0-278">建議您如何檢查設定為 "false" 的設定 () 可能會讓企業狀態漫遊無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="860b0-278">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="860b0-279">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-279">**Advisory**</span></span>

<span data-ttu-id="860b0-280">確定 **AllowAdHocSubscriptions** 設定為 **True** 。</span><span class="sxs-lookup"><span data-stu-id="860b0-280">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="860b0-281">否則，企業狀態漫遊可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="860b0-281">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="860b0-282">如需詳細資訊，請參閱 [MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="860b0-282">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="860b0-283">企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="860b0-283">Enterprise State Roaming</span></span>

<span data-ttu-id="860b0-284">應啟用企業狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="860b0-284">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="860b0-285">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-285">**Advisory**</span></span>

<span data-ttu-id="860b0-286">請確定已針對 **所有** 或 **選取** 的群組啟用企業狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="860b0-286">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="860b0-287">如需詳細資訊，請參閱 [在 Azure Active Directory 中啟用企業狀態漫遊](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="860b0-287">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="860b0-288">授權</span><span class="sxs-lookup"><span data-stu-id="860b0-288">Licenses</span></span>

<span data-ttu-id="860b0-289">使用 Microsoft 受管理的桌面需要一些授權。</span><span class="sxs-lookup"><span data-stu-id="860b0-289">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="860b0-290">**尚未準備好**</span><span class="sxs-lookup"><span data-stu-id="860b0-290">**Not Ready**</span></span>

<span data-ttu-id="860b0-291">您沒有使用 Microsoft 管理的桌面所需的所有授權。</span><span class="sxs-lookup"><span data-stu-id="860b0-291">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="860b0-292">如需詳細資訊，請參閱 [Microsoft 管理的桌面技術](../intro/technologies.md) 和 [有關授權的詳細](prerequisites.md#more-about-licenses)資訊。</span><span class="sxs-lookup"><span data-stu-id="860b0-292">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="860b0-293">安全性帳戶名稱</span><span class="sxs-lookup"><span data-stu-id="860b0-293">Security account names</span></span>

<span data-ttu-id="860b0-294">某些安全性帳戶名稱會與 Microsoft Managed Desktop 所建立的名稱相衝突。</span><span class="sxs-lookup"><span data-stu-id="860b0-294">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="860b0-295">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-295">**Not ready**</span></span>

<span data-ttu-id="860b0-296">您至少要有一個帳戶名稱會與 Microsoft Managed Desktop 所建立的帳戶名稱產生衝突。</span><span class="sxs-lookup"><span data-stu-id="860b0-296">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="860b0-297">請與您的 Microsoft 帳戶代表合作，以排除這些帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="860b0-297">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="860b0-298">安全性管理員角色</span><span class="sxs-lookup"><span data-stu-id="860b0-298">Security administrator roles</span></span>

<span data-ttu-id="860b0-299">具有特定安全性角色的使用者必須在 Microsoft Defender for Endpoint 中指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="860b0-299">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="860b0-300">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-300">**Advisory**</span></span>

<span data-ttu-id="860b0-301">如果您已在 Azure AD 組織中指派任何這些角色，請確定他們也在 Microsoft Defender for Endpoint 中指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="860b0-301">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="860b0-302">否則，具有這些角色的系統管理員將無法存取管理員入口網站。</span><span class="sxs-lookup"><span data-stu-id="860b0-302">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="860b0-303">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="860b0-303">Security Reader</span></span>
- <span data-ttu-id="860b0-304">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="860b0-304">Security Operator</span></span>
- <span data-ttu-id="860b0-305">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="860b0-305">Global Reader</span></span>

<span data-ttu-id="860b0-306">如需詳細資訊，請參閱 [建立及管理以角色為基礎的存取控制角色](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="860b0-306">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="860b0-307">安全性預設值</span><span class="sxs-lookup"><span data-stu-id="860b0-307">Security default</span></span>

<span data-ttu-id="860b0-308">在 Azure Active Directory 中的安全性預設值會使 Microsoft Managed Desktop 無法管理您的裝置。</span><span class="sxs-lookup"><span data-stu-id="860b0-308">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="860b0-309">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="860b0-309">**Not ready**</span></span>

<span data-ttu-id="860b0-310">您已開啟安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="860b0-310">You have Security defaults turned on.</span></span> <span data-ttu-id="860b0-311">關閉安全性預設值，並設定條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="860b0-311">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="860b0-312">如需詳細資訊，請參閱 [一般條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="860b0-312">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="860b0-313">自助密碼重設</span><span class="sxs-lookup"><span data-stu-id="860b0-313">Self-service Password Reset</span></span>

<span data-ttu-id="860b0-314">自助密碼重設 (SSPR) 應該針對所有不含 Microsoft Managed Desktop 服務帳戶的使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="860b0-314">Self-service Password Reset (SSPR) should be enabled for all users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="860b0-315">如需詳細資訊，請參閱 [教學課程：讓使用者可以使用 Azure Active Directory 自助密碼重設來解除鎖定帳戶或重設密碼](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="860b0-315">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="860b0-316">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-316">**Advisory**</span></span>

<span data-ttu-id="860b0-317">請確定 [SSPR **選取** ] 設定包括 Microsoft 受管理的桌面裝置，但不包括 Microsoft 受管理的桌面服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="860b0-317">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="860b0-318">SSPR 啟用時，Microsoft Managed Desktop service 帳戶無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="860b0-318">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="860b0-319">標準使用者角色</span><span class="sxs-lookup"><span data-stu-id="860b0-319">Standard user role</span></span>

<span data-ttu-id="860b0-320">除了為全域系統管理員和裝置管理員指派 Azure AD 角色的使用者以外，Microsoft 受管理的桌面使用者將是不具備本機系統管理員許可權的標準使用者。</span><span class="sxs-lookup"><span data-stu-id="860b0-320">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="860b0-321">當其他使用者啟動其 Microsoft 受管理的桌面裝置時，系統會將其指派為標準使用者角色。</span><span class="sxs-lookup"><span data-stu-id="860b0-321">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="860b0-322">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-322">**Advisory**</span></span>

<span data-ttu-id="860b0-323">Microsoft 受管理的桌面使用者在註冊後，不會對其 Microsoft 受管理的桌面裝置具有本機系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="860b0-323">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="860b0-324">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="860b0-324">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="860b0-325">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="860b0-325">OneDrive for Business</span></span>

<span data-ttu-id="860b0-326">[ **僅允許在加入特定網域的電腦上進行同步** 處理] 設定會與 Microsoft 受管理的桌面產生衝突。</span><span class="sxs-lookup"><span data-stu-id="860b0-326">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="860b0-327">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="860b0-327">**Advisory**</span></span>

<span data-ttu-id="860b0-328">您正在使用 [ **僅允許在加入特定網域的電腦上同步** 處理] 設定。</span><span class="sxs-lookup"><span data-stu-id="860b0-328">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="860b0-329">此設定不會與 Microsoft 受管理的桌面搭配使用。</span><span class="sxs-lookup"><span data-stu-id="860b0-329">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="860b0-330">停用此設定，而不是設定為商務使用條件式存取原則的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="860b0-330">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="860b0-331">請參閱 [規劃設定條件式存取部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 以取得協助。</span><span class="sxs-lookup"><span data-stu-id="860b0-331">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

