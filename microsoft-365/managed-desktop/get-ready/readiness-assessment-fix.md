---
title: 修正準備工作評估工具所找到的問題
description: 針對每個工具找到的問題所採取的詳細動作
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a6dec9473ee632b74bb79e50156cedff53a3cba3
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2020
ms.locfileid: "48795114"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="decd6-104">修正準備工作評估工具所找到的問題</span><span class="sxs-lookup"><span data-stu-id="decd6-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="decd6-105">針對每個檢查，該工具會報告下列四個可能的結果之一：</span><span class="sxs-lookup"><span data-stu-id="decd6-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="decd6-106">結果</span><span class="sxs-lookup"><span data-stu-id="decd6-106">Result</span></span>  |<span data-ttu-id="decd6-107">意義</span><span class="sxs-lookup"><span data-stu-id="decd6-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="decd6-108">就緒</span><span class="sxs-lookup"><span data-stu-id="decd6-108">Ready</span></span>     | <span data-ttu-id="decd6-109">完成註冊之前，不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="decd6-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="decd6-110">諮詢</span><span class="sxs-lookup"><span data-stu-id="decd6-110">Advisory</span></span>    | <span data-ttu-id="decd6-111">請遵循工具或本文中的步驟，以取得註冊和使用者的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="decd6-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="decd6-112">您 *可以* 完成註冊，但是必須先修正這些問題，再部署第一個裝置。</span><span class="sxs-lookup"><span data-stu-id="decd6-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="decd6-113">未就緒</span><span class="sxs-lookup"><span data-stu-id="decd6-113">Not ready</span></span> | <span data-ttu-id="decd6-114">*如果您未修正這些問題，註冊將會失敗。*</span><span class="sxs-lookup"><span data-stu-id="decd6-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="decd6-115">請遵循工具或本文中的步驟加以解決。</span><span class="sxs-lookup"><span data-stu-id="decd6-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="decd6-116">錯誤</span><span class="sxs-lookup"><span data-stu-id="decd6-116">Error</span></span> | <span data-ttu-id="decd6-117">您所使用的 Azure Active Director (AD) 角色，沒有足夠的許可權可執行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="decd6-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="decd6-118">Microsoft Intune 設定</span><span class="sxs-lookup"><span data-stu-id="decd6-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="decd6-119">Autopilot 部署設定檔</span><span class="sxs-lookup"><span data-stu-id="decd6-119">Autopilot deployment profile</span></span>

<span data-ttu-id="decd6-120">您不應該有任何現有的 Autopilot 設定檔，是 Microsoft Managed Desktop 所使用的指派或動態群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="decd6-121">Microsoft 受管理的桌面會使用 Autopilot 布建新裝置。</span><span class="sxs-lookup"><span data-stu-id="decd6-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="decd6-122">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-122">**Not ready**</span></span>

<span data-ttu-id="decd6-123">您有指派給所有裝置的 Autopilot 設定檔。</span><span class="sxs-lookup"><span data-stu-id="decd6-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="decd6-124">如需步驟，請參閱 [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="decd6-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="decd6-125">Microsoft 受管理的桌上型電腦註冊後，請將您的 Autopilot 原則設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="decd6-126">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-126">**Advisory**</span></span>

<span data-ttu-id="decd6-127">請確定您的 Autopilot 設定檔目標是指派或動態 Azure AD 群組，但不包含將在註冊時建立的 Microsoft 受管理桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="decd6-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="decd6-128">如需步驟，請參閱 [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="decd6-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="decd6-129">Microsoft 受管理的桌上型電腦註冊後，請將您的 Autopilot 原則設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="decd6-130">憑證連接器</span><span class="sxs-lookup"><span data-stu-id="decd6-130">Certificate connectors</span></span>

<span data-ttu-id="decd6-131">如果您有任何您想要在 Microsoft 受管理的電腦上登錄之裝置使用的憑證連接器，連接器就不能有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="decd6-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="decd6-132">下列其中一項諮詢只適用于您的情況，所以請務必仔細檢查。</span><span class="sxs-lookup"><span data-stu-id="decd6-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="decd6-133">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-133">**Advisory**</span></span>

<span data-ttu-id="decd6-134">不存在任何憑證連接器。</span><span class="sxs-lookup"><span data-stu-id="decd6-134">No certificate connectors are present.</span></span> <span data-ttu-id="decd6-135">您可能不需要任何連接器，但您應評估您是否需要部分網路連接至 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="decd6-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="decd6-136">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="decd6-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="decd6-137">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-137">**Advisory**</span></span>

<span data-ttu-id="decd6-138">至少有一個憑證連接器有錯誤。</span><span class="sxs-lookup"><span data-stu-id="decd6-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="decd6-139">如果您需要此連接器才能連線至 Microsoft 受管理的桌面裝置，您必須解決該錯誤。</span><span class="sxs-lookup"><span data-stu-id="decd6-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="decd6-140">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="decd6-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="decd6-141">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-141">**Advisory**</span></span>

<span data-ttu-id="decd6-142">您至少有一個憑證連接器，而且不會報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="decd6-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="decd6-143">不過，您可能需要建立設定檔，以重複使用 Microsoft 受管理的桌面裝置的連接器。</span><span class="sxs-lookup"><span data-stu-id="decd6-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="decd6-144">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="decd6-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="decd6-145">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="decd6-145">Conditional access policies</span></span>

<span data-ttu-id="decd6-146">Azure AD 組織中的條件式存取原則不得以任何 Microsoft 管理桌面使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="decd6-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="decd6-147">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-147">**Not ready**</span></span>

<span data-ttu-id="decd6-148">您有至少一個目標為所有使用者的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="decd6-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="decd6-149">將原則重設為面向不包含將在註冊時建立之 Microsoft Managed Desktop service 帳戶之 Azure AD 群組的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="decd6-150">如需步驟，請參閱 [條件式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="decd6-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="decd6-151">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-151">**Advisory**</span></span>

<span data-ttu-id="decd6-152">請確定任何條件式存取原則都排除了 **現代的 Workplace Service 帳戶** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="decd6-153">如需步驟，請參閱 [調整條件式存取](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="decd6-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="decd6-154">**新式的 Workplace Service 帳戶** Azure AD 群組是我們在您註冊時，為服務建立的動態群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="decd6-155">註冊後，您必須回到以排除此群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="decd6-156">如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="decd6-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="decd6-157">**Error**</span><span class="sxs-lookup"><span data-stu-id="decd6-157">**Error**</span></span>

<span data-ttu-id="decd6-158">Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="decd6-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="decd6-159">您也需要指派的任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="decd6-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="decd6-160">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="decd6-160">Security Reader</span></span>
- <span data-ttu-id="decd6-161">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="decd6-161">Security Administrator</span></span>
- <span data-ttu-id="decd6-162">條件式存取管理員</span><span class="sxs-lookup"><span data-stu-id="decd6-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="decd6-163">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="decd6-163">Global Reader</span></span>
- <span data-ttu-id="decd6-164">裝置管理員</span><span class="sxs-lookup"><span data-stu-id="decd6-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="decd6-165">裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="decd6-165">Device Compliance policies</span></span>

<span data-ttu-id="decd6-166">Azure AD 組織中的 Intune 裝置相容性原則不得以 Microsoft 受管理的桌面使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="decd6-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="decd6-167">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-167">**Not ready**</span></span>

<span data-ttu-id="decd6-168">您至少具有一個針對所有使用者的符合性原則。</span><span class="sxs-lookup"><span data-stu-id="decd6-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="decd6-169">將原則重設為面向不包含任何 Microsoft 受管理桌面使用者的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="decd6-170">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="decd6-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="decd6-171">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-171">**Advisory**</span></span>

<span data-ttu-id="decd6-172">請確定任何您沒有的相容性原則都包含任何 Microsoft 受管理的桌面使用者。</span><span class="sxs-lookup"><span data-stu-id="decd6-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="decd6-173">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="decd6-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="decd6-174">裝置設定原則</span><span class="sxs-lookup"><span data-stu-id="decd6-174">Device Configuration policies</span></span>

<span data-ttu-id="decd6-175">Azure AD 組織中的 Intune 裝置設定原則不得針對任何 Microsoft 管理桌面裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="decd6-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="decd6-176">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-176">**Not ready**</span></span>

<span data-ttu-id="decd6-177">您至少要有一個設定原則，針對所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="decd6-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="decd6-178">針對不包含任何 Microsoft 受管理桌面裝置的特定 Azure AD 群組，將原則重設為 [目標]。</span><span class="sxs-lookup"><span data-stu-id="decd6-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="decd6-179">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="decd6-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="decd6-180">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-180">**Advisory**</span></span>

<span data-ttu-id="decd6-181">請確定任何您沒有的相容性原則都包含任何 Microsoft 受管理的桌面裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="decd6-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="decd6-182">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="decd6-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="decd6-183">裝置類型限制</span><span class="sxs-lookup"><span data-stu-id="decd6-183">Device type restrictions</span></span>

<span data-ttu-id="decd6-184">Microsoft 受管理的桌面裝置必須能夠在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="decd6-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="decd6-185">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-185">**Not ready**</span></span>

<span data-ttu-id="decd6-186">依照 [設定註冊限制](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) 中的步驟，將設定變更為 [ **允許** ]。</span><span class="sxs-lookup"><span data-stu-id="decd6-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow** .</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="decd6-187">註冊狀態頁面</span><span class="sxs-lookup"><span data-stu-id="decd6-187">Enrollment Status Page</span></span>

<span data-ttu-id="decd6-188">您目前已啟用「註冊狀態」頁面 (ESP) 。</span><span class="sxs-lookup"><span data-stu-id="decd6-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="decd6-189">如果您參與此功能的公開預覽，可以略過此專案。</span><span class="sxs-lookup"><span data-stu-id="decd6-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="decd6-190">如需詳細資訊，請參閱 [使用 Autopilot 和註冊狀態頁面的初次執行體驗](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="decd6-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="decd6-191">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-191">**Not ready**</span></span>

<span data-ttu-id="decd6-192">您已設定 ESP 預設設定檔來 **顯示應用程式和設定檔設定進度** 。</span><span class="sxs-lookup"><span data-stu-id="decd6-192">You have the ESP default profile set to **Show app and profile configuration progress** .</span></span> <span data-ttu-id="decd6-193">請遵循 [設定 [註冊狀態] 頁面](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)中的步驟，停用此設定。</span><span class="sxs-lookup"><span data-stu-id="decd6-193">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="decd6-194">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-194">**Advisory**</span></span>

<span data-ttu-id="decd6-195">請確定任何具有「 **顯示應用程式和設定檔設定進度** 」設定的設定檔都未指派給任何包含 Microsoft 受管理的桌面裝置的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="decd6-196">如需詳細資訊，請參閱 [設定註冊狀態頁面](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="decd6-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="decd6-197">Intune 登記</span><span class="sxs-lookup"><span data-stu-id="decd6-197">Intune enrollment</span></span>

<span data-ttu-id="decd6-198">Azure AD 組織中的 Windows 10 裝置必須在 Intune 中自動註冊。</span><span class="sxs-lookup"><span data-stu-id="decd6-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="decd6-199">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-199">**Not ready**</span></span>

<span data-ttu-id="decd6-200">Azure AD 組織中的使用者不會在 Microsoft Intune 中自動註冊。</span><span class="sxs-lookup"><span data-stu-id="decd6-200">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="decd6-201">將 MDM 使用者範圍變更為 [ **部分** ] 或 [ **全部** ]。</span><span class="sxs-lookup"><span data-stu-id="decd6-201">Change the MDM User scope to **Some** or **All** .</span></span> <span data-ttu-id="decd6-202">如果您選擇 [ **部分** ]，請在註冊後再進行註冊，然後選取 [ **現代工作場所-** **群組** 的所有 Azure AD 群組]。</span><span class="sxs-lookup"><span data-stu-id="decd6-202">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** .</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="decd6-203">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="decd6-203">Microsoft Store for Business</span></span>

<span data-ttu-id="decd6-204">我們使用 Microsoft Store for Business，可讓您下載公司入口網站，以部署某些應用程式，例如 Microsoft Project 和 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="decd6-204">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="decd6-205">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-205">**Not ready**</span></span>

<span data-ttu-id="decd6-206">商務用 Microsoft Store 未啟用或未與 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="decd6-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="decd6-207">如需詳細資訊，請參閱 how [to 使用 Microsoft Intune 管理大量購買的應用程式](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) ，以及 [在裝置上安裝 Intune 公司入口網站](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="decd6-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="decd6-208">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="decd6-208">Multi-factor authentication</span></span>

<span data-ttu-id="decd6-209">多重要素驗證不得意外套用至 Microsoft Managed Desktop service 帳戶。</span><span class="sxs-lookup"><span data-stu-id="decd6-209">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="decd6-210">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-210">**Not ready**</span></span>

<span data-ttu-id="decd6-211">您有部分多重要素驗證 (MFA) 原則，設定為指派給所有使用者的條件式存取原則的「必要」。</span><span class="sxs-lookup"><span data-stu-id="decd6-211">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="decd6-212">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="decd6-212">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="decd6-213">如需詳細資訊，請參閱 [條件式存取原則](#conditional-access-policies) 和 [條件式存取：針對所有使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="decd6-213">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="decd6-214">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-214">**Advisory**</span></span>

<span data-ttu-id="decd6-215">請確定任何需要 MFA 的條件式存取原則排除 **新式的 Workplace-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-215">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="decd6-216">如需詳細資訊，請參閱 [條件式存取原則](#conditional-access-policies) 和 [條件式存取：針對所有使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="decd6-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="decd6-217">**新式的工作場所-所有** Azure AD 群組是我們在您註冊 Microsoft Managed Desktop 時所建立的動態群組，所以您必須在註冊後傳回排除此群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-217">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="decd6-218">**Error**</span><span class="sxs-lookup"><span data-stu-id="decd6-218">**Error**</span></span>

<span data-ttu-id="decd6-219">Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="decd6-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="decd6-220">您也需要指派的任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="decd6-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="decd6-221">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="decd6-221">Security Reader</span></span>
- <span data-ttu-id="decd6-222">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="decd6-222">Security Administrator</span></span>
- <span data-ttu-id="decd6-223">條件式存取管理員</span><span class="sxs-lookup"><span data-stu-id="decd6-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="decd6-224">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="decd6-224">Global Reader</span></span>
- <span data-ttu-id="decd6-225">裝置管理員</span><span class="sxs-lookup"><span data-stu-id="decd6-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="decd6-226">PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="decd6-226">PowerShell scripts</span></span>

<span data-ttu-id="decd6-227">Windows PowerShell 腳本無法指派為以 Microsoft 受管理的桌面裝置為目標的方式。</span><span class="sxs-lookup"><span data-stu-id="decd6-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="decd6-228">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-228">**Advisory**</span></span>

<span data-ttu-id="decd6-229">確定您的 Azure AD 組織中的 Windows PowerShell 腳本並未以任何 Microsoft 管理桌面裝置或使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="decd6-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="decd6-230">如需詳細資訊，請參閱在 [Intune 中使用 Windows 10 裝置上的 PowerShell 腳本](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="decd6-230">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="decd6-231">區域</span><span class="sxs-lookup"><span data-stu-id="decd6-231">Region</span></span>

<span data-ttu-id="decd6-232">您的區域必須支援 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="decd6-232">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="decd6-233">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-233">**Not ready**</span></span>

<span data-ttu-id="decd6-234">Microsoft 受管理的電腦目前不支援您的 Azure AD 組織區域。</span><span class="sxs-lookup"><span data-stu-id="decd6-234">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="decd6-235">如需詳細資訊，請參閱 [Microsoft 受管理的桌面支援的地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="decd6-235">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="decd6-236">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-236">**Advisory**</span></span>

<span data-ttu-id="decd6-237">Microsoft 受管理的電腦不支援 Azure AD 組織所在的一或多個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="decd6-237">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="decd6-238">如需詳細資訊，請參閱 [Microsoft 受管理的桌面支援的地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="decd6-238">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="decd6-239">安全性基準</span><span class="sxs-lookup"><span data-stu-id="decd6-239">Security baselines</span></span>

<span data-ttu-id="decd6-240">安全性基準原則不應該以任何 Microsoft 受管理的桌面裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="decd6-240">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="decd6-241">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-241">**Not ready**</span></span>

<span data-ttu-id="decd6-242">您有一個針對所有使用者、所有裝置或兩者的安全性基準設定檔。</span><span class="sxs-lookup"><span data-stu-id="decd6-242">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="decd6-243">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="decd6-243">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="decd6-244">如需步驟，請參閱 [使用安全性基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="decd6-244">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="decd6-245">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-245">**Advisory**</span></span>

<span data-ttu-id="decd6-246">請確定所有的安全性基準原則都排除 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="decd6-246">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="decd6-247">如需步驟，請參閱 [使用安全性基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="decd6-247">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="decd6-248">**新式的工作場所裝置-所有** Azure AD 群組是我們在您註冊 Microsoft Managed Desktop 時所建立的動態群組，所以您必須在註冊後傳回排除此群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-248">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="decd6-249">Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="decd6-249">Windows apps</span></span>

<span data-ttu-id="decd6-250">查看您要讓 Microsoft 受管理的桌面使用者擁有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="decd6-250">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="decd6-251">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-251">**Advisory**</span></span>

<span data-ttu-id="decd6-252">您應該準備要讓 Microsoft 受管理的桌面使用者擁有的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="decd6-252">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="decd6-253">請確定您可以透過 Intune 部署這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="decd6-253">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="decd6-254">如需詳細資訊，請參閱 [Microsoft Managed Desktop 中的應用程式](apps.md)。</span><span class="sxs-lookup"><span data-stu-id="decd6-254">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="decd6-255">您可以要求 Microsoft 帳戶代表在 Microsoft 端點 Configuration Manager 中查詢，以識別準備好要遷移至 Intune 或需要調整的應用程式。</span><span class="sxs-lookup"><span data-stu-id="decd6-255">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="decd6-256">Windows Hello 企業版</span><span class="sxs-lookup"><span data-stu-id="decd6-256">Windows Hello for Business</span></span>

<span data-ttu-id="decd6-257">Microsoft 受管理的桌面需要啟用 Windows Hello 企業版功能。</span><span class="sxs-lookup"><span data-stu-id="decd6-257">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="decd6-258">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-258">**Not ready**</span></span>

<span data-ttu-id="decd6-259">Windows Hello 企業版已停用。</span><span class="sxs-lookup"><span data-stu-id="decd6-259">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="decd6-260">遵循[建立 Windows Hello 企業版原則](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用</span><span class="sxs-lookup"><span data-stu-id="decd6-260">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="decd6-261">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-261">**Advisory**</span></span>

<span data-ttu-id="decd6-262">未設定 Windows Hello 企業版。</span><span class="sxs-lookup"><span data-stu-id="decd6-262">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="decd6-263">遵循 [建立 Windows Hello 企業版原則](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用它。</span><span class="sxs-lookup"><span data-stu-id="decd6-263">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="decd6-264">Windows 10 更新環</span><span class="sxs-lookup"><span data-stu-id="decd6-264">Windows 10 update rings</span></span>

<span data-ttu-id="decd6-265">Intune 中的「Windows 10 更新環路」原則不得以 Microsoft 受管理的桌面裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="decd6-265">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="decd6-266">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-266">**Not ready**</span></span>

<span data-ttu-id="decd6-267">您有一個「更新鈴聲」原則，針對所有裝置、所有使用者或兩者。</span><span class="sxs-lookup"><span data-stu-id="decd6-267">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="decd6-268">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="decd6-268">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="decd6-269">如需步驟，請參閱 [在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="decd6-269">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="decd6-270">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-270">**Advisory**</span></span>

<span data-ttu-id="decd6-271">請確定任何更新環原則您已排除現代的 **工作場所-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-271">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="decd6-272">如需步驟，請參閱 [在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="decd6-272">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="decd6-273">**新式的工作場所裝置-所有** Azure AD 群組是我們在您註冊 Microsoft Managed Desktop 時所建立的動態群組，所以您必須在註冊後傳回排除此群組。</span><span class="sxs-lookup"><span data-stu-id="decd6-273">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="decd6-274">Azure Active Directory 設定</span><span class="sxs-lookup"><span data-stu-id="decd6-274">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="decd6-275">專用訂閱</span><span class="sxs-lookup"><span data-stu-id="decd6-275">Ad hoc subscriptions</span></span>

<span data-ttu-id="decd6-276">建議您如何檢查設定為 "false" 的設定 () 可能會讓企業狀態漫遊無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="decd6-276">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="decd6-277">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-277">**Advisory**</span></span>

<span data-ttu-id="decd6-278">確定 **AllowAdHocSubscriptions** 設定為 **True** 。</span><span class="sxs-lookup"><span data-stu-id="decd6-278">Ensure that **AllowAdHocSubscriptions** is set to **True** .</span></span> <span data-ttu-id="decd6-279">否則，企業狀態漫遊可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="decd6-279">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="decd6-280">如需詳細資訊，請參閱 [MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="decd6-280">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="decd6-281">企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="decd6-281">Enterprise State Roaming</span></span>

<span data-ttu-id="decd6-282">應啟用企業狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="decd6-282">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="decd6-283">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-283">**Advisory**</span></span>

<span data-ttu-id="decd6-284">請確定已針對 **所有** 或 **選取** 的群組啟用企業狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="decd6-284">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="decd6-285">如需詳細資訊，請參閱 [在 Azure Active Directory 中啟用企業狀態漫遊](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="decd6-285">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="decd6-286">授權</span><span class="sxs-lookup"><span data-stu-id="decd6-286">Licenses</span></span>

<span data-ttu-id="decd6-287">使用 Microsoft 受管理的桌面需要一些授權。</span><span class="sxs-lookup"><span data-stu-id="decd6-287">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="decd6-288">**尚未準備好**</span><span class="sxs-lookup"><span data-stu-id="decd6-288">**Not Ready**</span></span>

<span data-ttu-id="decd6-289">您沒有使用 Microsoft 管理的桌面所需的所有授權。</span><span class="sxs-lookup"><span data-stu-id="decd6-289">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="decd6-290">如需詳細資訊，請參閱 [Microsoft 管理的桌面技術](../intro/technologies.md) 和 [有關授權的詳細](prerequisites.md#more-about-licenses)資訊。</span><span class="sxs-lookup"><span data-stu-id="decd6-290">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="decd6-291">安全性帳戶名稱</span><span class="sxs-lookup"><span data-stu-id="decd6-291">Security account names</span></span>

<span data-ttu-id="decd6-292">某些安全性帳戶名稱會與 Microsoft Managed Desktop 所建立的名稱相衝突。</span><span class="sxs-lookup"><span data-stu-id="decd6-292">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="decd6-293">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-293">**Not ready**</span></span>

<span data-ttu-id="decd6-294">您至少要有一個帳戶名稱會與 Microsoft Managed Desktop 所建立的帳戶名稱產生衝突。</span><span class="sxs-lookup"><span data-stu-id="decd6-294">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="decd6-295">請與您的 Microsoft 帳戶代表合作，以排除這些帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="decd6-295">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="decd6-296">安全性管理員角色</span><span class="sxs-lookup"><span data-stu-id="decd6-296">Security administrator roles</span></span>

<span data-ttu-id="decd6-297">具有特定安全性角色的使用者必須在 Microsoft Defender for Endpoint 中指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="decd6-297">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="decd6-298">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-298">**Advisory**</span></span>

<span data-ttu-id="decd6-299">如果您已在 Azure AD 組織中指派任何這些角色，請確定他們也在 Microsoft Defender for Endpoint 中指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="decd6-299">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="decd6-300">否則，具有這些角色的系統管理員將無法存取管理員入口網站。</span><span class="sxs-lookup"><span data-stu-id="decd6-300">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="decd6-301">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="decd6-301">Security Reader</span></span>
- <span data-ttu-id="decd6-302">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="decd6-302">Security Operator</span></span>
- <span data-ttu-id="decd6-303">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="decd6-303">Global Reader</span></span>

<span data-ttu-id="decd6-304">如需詳細資訊，請參閱 [建立及管理以角色為基礎的存取控制角色](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="decd6-304">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="decd6-305">安全性預設值</span><span class="sxs-lookup"><span data-stu-id="decd6-305">Security default</span></span>

<span data-ttu-id="decd6-306">在 Azure Active Directory 中的安全性預設值會使 Microsoft Managed Desktop 無法管理您的裝置。</span><span class="sxs-lookup"><span data-stu-id="decd6-306">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="decd6-307">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-307">**Not ready**</span></span>

<span data-ttu-id="decd6-308">您已開啟安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="decd6-308">You have Security defaults turned on.</span></span> <span data-ttu-id="decd6-309">關閉安全性預設值，並設定條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="decd6-309">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="decd6-310">如需詳細資訊，請參閱 [一般條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="decd6-310">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="decd6-311">自助密碼重設</span><span class="sxs-lookup"><span data-stu-id="decd6-311">Self-service Password Reset</span></span>

<span data-ttu-id="decd6-312">必須啟用自助密碼重設 (SSPR) 。</span><span class="sxs-lookup"><span data-stu-id="decd6-312">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="decd6-313">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="decd6-313">**Not ready**</span></span>

<span data-ttu-id="decd6-314">所有使用者都必須啟用 SSPR。</span><span class="sxs-lookup"><span data-stu-id="decd6-314">SSPR must be enabled for all users.</span></span> <span data-ttu-id="decd6-315">如果不是，則 Microsoft 管理的桌面服務帳戶無法運作。</span><span class="sxs-lookup"><span data-stu-id="decd6-315">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="decd6-316">如需詳細資訊，請參閱 [教學課程：讓使用者可以使用 Azure Active Directory 自助密碼重設來解除鎖定帳戶或重設密碼](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="decd6-316">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="decd6-317">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-317">**Advisory**</span></span>

<span data-ttu-id="decd6-318">請確定 SSPR **選取** 的設定包括 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="decd6-318">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="decd6-319">**Error**</span><span class="sxs-lookup"><span data-stu-id="decd6-319">**Error**</span></span>

<span data-ttu-id="decd6-320">Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="decd6-320">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="decd6-321">您也需要指派給執行這種檢查的「報告讀取器 Azure AD」角色。</span><span class="sxs-lookup"><span data-stu-id="decd6-321">You'll also need the Reports Reader Azure AD role assigned to run this check.</span></span>


### <a name="standard-user-role"></a><span data-ttu-id="decd6-322">標準使用者角色</span><span class="sxs-lookup"><span data-stu-id="decd6-322">Standard user role</span></span>

<span data-ttu-id="decd6-323">Microsoft 受管理的桌面使用者應是不具備本機系統管理員許可權的標準使用者。</span><span class="sxs-lookup"><span data-stu-id="decd6-323">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="decd6-324">當他們啟動 Microsoft 受管理的桌面裝置時，系統會將其指派為標準使用者角色。</span><span class="sxs-lookup"><span data-stu-id="decd6-324">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="decd6-325">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-325">**Advisory**</span></span>

<span data-ttu-id="decd6-326">Microsoft 受管理的桌面使用者在註冊之前，不應該具有本機系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="decd6-326">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="decd6-327">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="decd6-327">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="decd6-328">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="decd6-328">OneDrive for Business</span></span>

<span data-ttu-id="decd6-329">[ **僅允許在加入特定網域的電腦上進行同步** 處理] 設定會與 Microsoft 受管理的桌面產生衝突。</span><span class="sxs-lookup"><span data-stu-id="decd6-329">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="decd6-330">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="decd6-330">**Advisory**</span></span>

<span data-ttu-id="decd6-331">您正在使用 [ **僅允許在加入特定網域的電腦上同步** 處理] 設定。</span><span class="sxs-lookup"><span data-stu-id="decd6-331">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="decd6-332">此設定不會與 Microsoft 受管理的桌面搭配使用。</span><span class="sxs-lookup"><span data-stu-id="decd6-332">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="decd6-333">停用此設定，而不是設定為商務使用條件式存取原則的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="decd6-333">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="decd6-334">請參閱 [規劃設定條件式存取部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 以取得協助。</span><span class="sxs-lookup"><span data-stu-id="decd6-334">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

