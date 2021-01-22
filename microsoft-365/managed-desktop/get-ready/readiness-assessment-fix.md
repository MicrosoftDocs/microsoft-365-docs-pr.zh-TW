---
title: 修正由整備評估工具發現的問題
description: 針對工具找到的每個問題採取的詳細動作
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f1af39a9b2a09908ecf5f5ff15b9fd6d764459d6
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921855"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="8c73f-104">修正由整備評估工具發現的問題</span><span class="sxs-lookup"><span data-stu-id="8c73f-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="8c73f-105">工具會針對每項檢查報告四種可能的結果之一：</span><span class="sxs-lookup"><span data-stu-id="8c73f-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="8c73f-106">結果</span><span class="sxs-lookup"><span data-stu-id="8c73f-106">Result</span></span>  |<span data-ttu-id="8c73f-107">意義</span><span class="sxs-lookup"><span data-stu-id="8c73f-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="8c73f-108">就緒</span><span class="sxs-lookup"><span data-stu-id="8c73f-108">Ready</span></span>     | <span data-ttu-id="8c73f-109">完成註冊之前無需執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="8c73f-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="8c73f-110">諮詢</span><span class="sxs-lookup"><span data-stu-id="8c73f-110">Advisory</span></span>    | <span data-ttu-id="8c73f-111">請遵循工具或本文中的步驟，以獲得最佳註冊和使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="8c73f-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="8c73f-112">您可以 *完成* 註冊，但必須在部署第一個裝置之前修正這些問題。</span><span class="sxs-lookup"><span data-stu-id="8c73f-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="8c73f-113">未就緒</span><span class="sxs-lookup"><span data-stu-id="8c73f-113">Not ready</span></span> | <span data-ttu-id="8c73f-114">*如果您沒有修正這些問題，註冊將會失敗。*</span><span class="sxs-lookup"><span data-stu-id="8c73f-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="8c73f-115">請遵循工具或本文中的步驟來解決問題。</span><span class="sxs-lookup"><span data-stu-id="8c73f-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="8c73f-116">錯誤</span><span class="sxs-lookup"><span data-stu-id="8c73f-116">Error</span></span> | <span data-ttu-id="8c73f-117">使用 Azure Active Director (AD) 角色沒有足夠的許可權可以執行這項檢查。</span><span class="sxs-lookup"><span data-stu-id="8c73f-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="8c73f-118">這項工具報告的結果只會在執行此工具的特定時間點反映您的設定狀態。</span><span class="sxs-lookup"><span data-stu-id="8c73f-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="8c73f-119">如果您稍後對 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略進行任何變更，之前為「就緒」的專案可能會變成「尚未就緒」。</span><span class="sxs-lookup"><span data-stu-id="8c73f-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="8c73f-120">若要避免 Microsoft 管理桌面作業發生問題，請在變更任何策略之前，檢查本文所述的特定設定。</span><span class="sxs-lookup"><span data-stu-id="8c73f-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="8c73f-121">Microsoft Intune 設定</span><span class="sxs-lookup"><span data-stu-id="8c73f-121">Microsoft Intune settings</span></span>

<span data-ttu-id="8c73f-122">您可以在 Microsoft Endpoint Manager 系統管理中心存取 Intune [設定](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="8c73f-123">Autopilot 部署設定檔</span><span class="sxs-lookup"><span data-stu-id="8c73f-123">Autopilot deployment profile</span></span>

<span data-ttu-id="8c73f-124">您不應該有任何現有的 Autopilot 設定檔以 Microsoft 受管理之桌面裝置為目標指定或動態群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8c73f-125">Microsoft Managed Desktop 會使用 Autopilot 來提供新裝置。</span><span class="sxs-lookup"><span data-stu-id="8c73f-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="8c73f-126">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-126">**Not ready**</span></span>

<span data-ttu-id="8c73f-127">您的 Autopilot 設定檔已指派給所有裝置。</span><span class="sxs-lookup"><span data-stu-id="8c73f-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="8c73f-128">有關步驟，請參閱使用 [Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)在 Intune 中註冊 Windows 裝置。</span><span class="sxs-lookup"><span data-stu-id="8c73f-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="8c73f-129">在 Microsoft 管理桌上型電腦註冊之後，設定您的 Autopilot 策略以排除新式工作場所裝置 **- 所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="8c73f-130">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-130">**Advisory**</span></span>

<span data-ttu-id="8c73f-131">請確定您的 Autopilot 設定檔的目標為不包含 Microsoft 受管理桌面裝置之已指派或動態 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8c73f-132">有關步驟，請參閱使用 [Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)在 Intune 中註冊 Windows 裝置。</span><span class="sxs-lookup"><span data-stu-id="8c73f-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="8c73f-133">在 Microsoft 管理桌上型電腦註冊之後，設定您的 Autopilot 設定檔以排除新式工作場所裝置 **-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-133">After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="8c73f-134">憑證連接器</span><span class="sxs-lookup"><span data-stu-id="8c73f-134">Certificate connectors</span></span>

<span data-ttu-id="8c73f-135">如果您想要在 Microsoft Managed Desktop 中註冊的裝置會使用任何憑證連接器，則連接器不應有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="8c73f-135">If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors should not have any errors.</span></span> <span data-ttu-id="8c73f-136">只有下列其中一個建議適用于您的情況，因此請仔細檢查。</span><span class="sxs-lookup"><span data-stu-id="8c73f-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="8c73f-137">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-137">**Advisory**</span></span>

<span data-ttu-id="8c73f-138">沒有憑證連接器存在。</span><span class="sxs-lookup"><span data-stu-id="8c73f-138">No certificate connectors are present.</span></span> <span data-ttu-id="8c73f-139">您可能不需要任何連接器，但您應評估是否需要一些在 Microsoft 管理的桌面裝置上進行網路連接。</span><span class="sxs-lookup"><span data-stu-id="8c73f-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8c73f-140">有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="8c73f-141">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-141">**Advisory**</span></span>

<span data-ttu-id="8c73f-142">至少有一個憑證連接器發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="8c73f-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="8c73f-143">如果您需要此連接器提供憑證給 Microsoft 受管理桌面裝置，您必須解決錯誤。</span><span class="sxs-lookup"><span data-stu-id="8c73f-143">If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="8c73f-144">有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="8c73f-145">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-145">**Advisory**</span></span>

<span data-ttu-id="8c73f-146">您至少有一個憑證連接器，而且沒有報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="8c73f-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="8c73f-147">不過，在準備部署時，您可能需要建立設定檔，以重複使用 Microsoft 受管理之桌面裝置上的連接器。</span><span class="sxs-lookup"><span data-stu-id="8c73f-147">However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8c73f-148">有關詳細資訊，請參閱 [準備 Microsoft Managed Desktop 的憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="8c73f-149">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="8c73f-149">Conditional access policies</span></span>

<span data-ttu-id="8c73f-150">Azure AD 組織的條件式存取策略不得以任何 Microsoft Manage Desktop 服務帳戶為目標。</span><span class="sxs-lookup"><span data-stu-id="8c73f-150">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop service accounts.</span></span>

<span data-ttu-id="8c73f-151">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-151">**Not ready**</span></span>

<span data-ttu-id="8c73f-152">您至少有一個會以所有使用者為根據的條件式存取策略。</span><span class="sxs-lookup"><span data-stu-id="8c73f-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="8c73f-153">修改該策略以鎖定不包含將在註冊中建立之 Microsoft Managed Desktop 服務帳戶的 Azure AD 群組的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-153">Modify the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="8c73f-154">有關步驟，請參閱條件 [式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-154">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="8c73f-155">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-155">**Advisory**</span></span>

<span data-ttu-id="8c73f-156">請確定您擁有的任何條件式存取策略不包含新式 **工作場所服務帳戶** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-156">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="8c73f-157">有關步驟，請參閱調整 [條件式存取](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-157">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="8c73f-158">新式 **工作場所服務帳戶** Azure AD 群組是一個動態群組，我們在您註冊時為該服務建立。</span><span class="sxs-lookup"><span data-stu-id="8c73f-158">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="8c73f-159">註冊之後，您必須返回以排除此群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-159">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="8c73f-160">有關這些服務帳戶的更多資訊，請參閱 [標準作業程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-160">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="8c73f-161">**錯誤**</span><span class="sxs-lookup"><span data-stu-id="8c73f-161">**Error**</span></span>

<span data-ttu-id="8c73f-162">Intune 系統管理員角色沒有足夠的許可權可以執行這項檢查。</span><span class="sxs-lookup"><span data-stu-id="8c73f-162">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="8c73f-163">您也需要被指派任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="8c73f-163">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="8c73f-164">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="8c73f-164">Security Reader</span></span>
- <span data-ttu-id="8c73f-165">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="8c73f-165">Security Administrator</span></span>
- <span data-ttu-id="8c73f-166">條件式存取系統管理員</span><span class="sxs-lookup"><span data-stu-id="8c73f-166">Conditional Access Administrator</span></span>
- <span data-ttu-id="8c73f-167">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="8c73f-167">Global Reader</span></span>
- <span data-ttu-id="8c73f-168">裝置系統管理員</span><span class="sxs-lookup"><span data-stu-id="8c73f-168">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="8c73f-169">裝置合規性政策</span><span class="sxs-lookup"><span data-stu-id="8c73f-169">Device Compliance policies</span></span>

<span data-ttu-id="8c73f-170">您 Azure AD 組織的 Intune 裝置合規性政策可能會影響 Microsoft Managed Desktop 裝置。</span><span class="sxs-lookup"><span data-stu-id="8c73f-170">Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="8c73f-171">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-171">**Not ready**</span></span>

<span data-ttu-id="8c73f-172">您至少有一個合規性政策會檢查所有使用者。</span><span class="sxs-lookup"><span data-stu-id="8c73f-172">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="8c73f-173">Microsoft Managed Desktop 包含以您 Microsoft 管理之桌面裝置為目標的合規性政策。</span><span class="sxs-lookup"><span data-stu-id="8c73f-173">Microsoft Managed Desktop includes compliance policies that will target your Microsoft Managed Desktop devices.</span></span>  <span data-ttu-id="8c73f-174">變更策略以鎖定不包括任何 Microsoft 受管理之桌面使用者或裝置的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-174">Change the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users or devices.</span></span> <span data-ttu-id="8c73f-175">相關步驟請參閱在 [Microsoft Intune 中建立合規性政策](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-175">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="8c73f-176">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-176">**Advisory**</span></span>

<span data-ttu-id="8c73f-177">請確定您未以任何 Microsoft 受管理之桌面使用者為目標的任何合規性政策。</span><span class="sxs-lookup"><span data-stu-id="8c73f-177">Make sure that any compliance policies you have don't target any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="8c73f-178">相關步驟請參閱在 [Microsoft Intune 中建立合規性政策](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-178">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-profiles"></a><span data-ttu-id="8c73f-179">裝置組配置設定檔</span><span class="sxs-lookup"><span data-stu-id="8c73f-179">Device Configuration profiles</span></span>

<span data-ttu-id="8c73f-180">您 Azure AD 組織的 Intune 裝置組組設定檔不得以任何 Microsoft 管理桌面裝置或使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="8c73f-180">Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="8c73f-181">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-181">**Not ready**</span></span>

<span data-ttu-id="8c73f-182">您至少有一個設定設定檔會同時針對所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="8c73f-182">You have at least one configuration profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="8c73f-183">將設定檔重設為不包括任何 Microsoft Managed Desktop 裝置的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-183">Reset the profile to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8c73f-184">有關步驟，請參閱 [使用 Microsoft Intune 中的自訂設定建立設定檔](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-184">For steps, see [Create a profile with custom settings in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="8c73f-185">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-185">**Advisory**</span></span>

<span data-ttu-id="8c73f-186">請確定您擁有的任何群組原則不包含任何 Microsoft 受管理的桌面裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="8c73f-186">Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="8c73f-187">有關步驟，請參閱 [使用 Microsoft Intune 中的自訂設定建立設定檔](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-187">For steps, see [Create a profile with custom settings in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="8c73f-188">裝置類型限制</span><span class="sxs-lookup"><span data-stu-id="8c73f-188">Device type restrictions</span></span>

<span data-ttu-id="8c73f-189">Microsoft 受管理桌面裝置必須允許在 Intune 註冊。</span><span class="sxs-lookup"><span data-stu-id="8c73f-189">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="8c73f-190">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-190">**Not ready**</span></span>

<span data-ttu-id="8c73f-191">您目前至少已針對一個註冊限制進行設置，以防止 Windows 裝置在 Intune 註冊。</span><span class="sxs-lookup"><span data-stu-id="8c73f-191">You currently have at least one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune.</span></span> <span data-ttu-id="8c73f-192">請遵循針對每個 [](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set)會以 Microsoft 管理之桌面使用者為根據的註冊限制設定註冊限制中的步驟，將 **Windows (MDM**) 設為 **允許**。</span><span class="sxs-lookup"><span data-stu-id="8c73f-192">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**.</span></span> <span data-ttu-id="8c73f-193">不過，您可以將 MDM **中個人** 擁有的任何 Windows (**設定)\*\*\*\*封鎖。**</span><span class="sxs-lookup"><span data-stu-id="8c73f-193">You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**.</span></span> 


### <a name="enrollment-status-page"></a><span data-ttu-id="8c73f-194">註冊狀態頁面</span><span class="sxs-lookup"><span data-stu-id="8c73f-194">Enrollment Status Page</span></span>

<span data-ttu-id="8c73f-195">您目前已啟用 ESP (註冊) 頁面。</span><span class="sxs-lookup"><span data-stu-id="8c73f-195">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="8c73f-196">如果您打算參與此功能的 Microsoft 受管理桌面公開預覽版，您可以忽略此專案。</span><span class="sxs-lookup"><span data-stu-id="8c73f-196">If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="8c73f-197">詳細資訊請參閱 [Autopilot 的](../get-started/esp-first-run.md)首次執行體驗及註冊狀態頁面。</span><span class="sxs-lookup"><span data-stu-id="8c73f-197">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="8c73f-198">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-198">**Not ready**</span></span>

<span data-ttu-id="8c73f-199">您將 ESP 預設設定檔設定為 **顯示 App 和設定檔設定進度**。</span><span class="sxs-lookup"><span data-stu-id="8c73f-199">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="8c73f-200">停用此設定，或遵循設定註冊狀態頁面的步驟，確定指派給任何 Azure AD 群組的工作不包含 Microsoft Managed [Desktop 裝置](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-200">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="8c73f-201">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-201">**Advisory**</span></span>

<span data-ttu-id="8c73f-202">請確定沒有將具有顯示應用程式及設定檔設定進度設定的任何設定檔指派給任何包含 Microsoft 受管理桌面裝置之 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-202">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8c73f-203">詳細資訊請參閱設定註冊狀態 [頁面](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-203">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="microsoft-store-for-business"></a><span data-ttu-id="8c73f-204">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8c73f-204">Microsoft Store for Business</span></span>

<span data-ttu-id="8c73f-205">我們使用商務用 Microsoft Store，在 Microsoft Managed Desktop 上部署公司入口網站應用程式，以允許使用者選擇性地安裝某些應用程式，例如 Microsoft Project 和 Microsoft Visio (在允許的情況下) 。</span><span class="sxs-lookup"><span data-stu-id="8c73f-205">We use Microsoft Store for Business and deploy the Company Portal app on Microsoft Managed Desktop to allow users to optionally install some apps, such as Microsoft Project and Microsoft Visio (where permitted).</span></span>

<span data-ttu-id="8c73f-206">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-206">**Not ready**</span></span>

<span data-ttu-id="8c73f-207">商務用 Microsoft Store 未啟用或未與 Intune 同步處理。</span><span class="sxs-lookup"><span data-stu-id="8c73f-207">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="8c73f-208">有關詳細資訊，請參閱 [如何使用 Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 從商務用 Microsoft Store 管理大量購買的應用程式，以及如何在裝置上安裝 [Intune 公司入口網站](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-208">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="8c73f-209">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="8c73f-209">Multifactor authentication</span></span>

<span data-ttu-id="8c73f-210">多重要素驗證不可適用于 Microsoft Managed Desktop 服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="8c73f-210">Multifactor authentication must not be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="8c73f-211">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-211">**Not ready**</span></span>

<span data-ttu-id="8c73f-212">針對指派給所有使用者的條件式存取策略，您將某些多重要素驗證策略設為必要的。</span><span class="sxs-lookup"><span data-stu-id="8c73f-212">You have some multifactor authentication policies set as **required** for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="8c73f-213">將設定變更為使用指派，以針對不包括任何 Microsoft Managed Desktop 服務帳戶的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-213">Change the policy to use an assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="8c73f-214">詳細資訊請參閱條件式[存取策略](#conditional-access-policies)和[條件式存取：所有使用者需要 MFA。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="8c73f-214">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="8c73f-215">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-215">**Advisory**</span></span>

<span data-ttu-id="8c73f-216">請確定任何需要多重要素驗證的條件式存取策略不包含新式 **工作場所 -所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-216">Make sure that any conditional access policies that require multifactor authentication exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="8c73f-217">詳細資訊請參閱條件式[存取策略](#conditional-access-policies)和[條件式存取：所有使用者需要 MFA。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="8c73f-217">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="8c73f-218">新式 **工作場所 - 所有** Azure AD 群組是一個動態群組，我們在您註冊 Microsoft Managed Desktop 時建立，因此您必須在註冊後返回排除此群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-218">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="8c73f-219">**錯誤**</span><span class="sxs-lookup"><span data-stu-id="8c73f-219">**Error**</span></span>

<span data-ttu-id="8c73f-220">Intune 系統管理員角色沒有足夠的許可權可以執行這項檢查。</span><span class="sxs-lookup"><span data-stu-id="8c73f-220">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="8c73f-221">您也需要被指派任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="8c73f-221">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="8c73f-222">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="8c73f-222">Security Reader</span></span>
- <span data-ttu-id="8c73f-223">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="8c73f-223">Security Administrator</span></span>
- <span data-ttu-id="8c73f-224">條件式存取系統管理員</span><span class="sxs-lookup"><span data-stu-id="8c73f-224">Conditional Access Administrator</span></span>
- <span data-ttu-id="8c73f-225">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="8c73f-225">Global Reader</span></span>
- <span data-ttu-id="8c73f-226">裝置系統管理員</span><span class="sxs-lookup"><span data-stu-id="8c73f-226">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="8c73f-227">PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="8c73f-227">PowerShell scripts</span></span>

<span data-ttu-id="8c73f-228">Windows PowerShell 腳本無法以 Microsoft Managed Desktop 裝置為目標的指派方式。</span><span class="sxs-lookup"><span data-stu-id="8c73f-228">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="8c73f-229">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-229">**Advisory**</span></span>

<span data-ttu-id="8c73f-230">請確定您 Azure AD 組織的 Windows PowerShell 腳本未以任何 Microsoft 管理桌面裝置或使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="8c73f-230">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="8c73f-231">請勿指派 PowerShell 腳本以鎖定所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="8c73f-231">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="8c73f-232">將群組原則變更為使用工作分派，該工作分派會針對不包括任何 Microsoft 受管理之桌面裝置或使用者的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-232">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="8c73f-233">詳細資訊請參閱 Intune 中 [Windows 10 裝置上的 PowerShell 腳本](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-233">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="8c73f-234">地區</span><span class="sxs-lookup"><span data-stu-id="8c73f-234">Region</span></span>

<span data-ttu-id="8c73f-235">您的地區必須受到 Microsoft 管理桌面的支援。</span><span class="sxs-lookup"><span data-stu-id="8c73f-235">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="8c73f-236">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-236">**Not ready**</span></span>

<span data-ttu-id="8c73f-237">Microsoft Managed Desktop 目前不支援您的 Azure AD 組織地區。</span><span class="sxs-lookup"><span data-stu-id="8c73f-237">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="8c73f-238">詳細資訊請參閱 Microsoft [受管理的桌面支援地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-238">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="8c73f-239">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-239">**Advisory**</span></span>

<span data-ttu-id="8c73f-240">Microsoft Managed Desktop 不支援您 Azure AD 組織所在的一或多個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="8c73f-240">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="8c73f-241">詳細資訊請參閱 Microsoft [受管理的桌面支援地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-241">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="8c73f-242">安全性比較基準</span><span class="sxs-lookup"><span data-stu-id="8c73f-242">Security baselines</span></span>

<span data-ttu-id="8c73f-243">安全性比較基準不應該以任何 Microsoft 管理桌面裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="8c73f-243">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="8c73f-244">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-244">**Not ready**</span></span>

<span data-ttu-id="8c73f-245">您的安全性比較基準設定檔會針對所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="8c73f-245">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="8c73f-246">將群組原則變更為使用指派，該工作分派會以不包括任何 Microsoft 受管理之桌面裝置的特定 Azure AD 群組為目標。</span><span class="sxs-lookup"><span data-stu-id="8c73f-246">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8c73f-247">有關步驟，請參閱 [使用安全性比較基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-247">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="8c73f-248">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-248">**Advisory**</span></span>

<span data-ttu-id="8c73f-249">請確定您排除 Microsoft 管理桌面裝置的任何安全性基準策略。</span><span class="sxs-lookup"><span data-stu-id="8c73f-249">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8c73f-250">有關步驟，請參閱 [使用安全性比較基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-250">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="8c73f-251">新式 **工作場所裝置 - 所有** Azure AD 群組是一個動態群組，我們在您註冊 Microsoft Managed Desktop 時建立，因此您註冊之後必須返回以排除此群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-251">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="8c73f-252">Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="8c73f-252">Windows apps</span></span>

<span data-ttu-id="8c73f-253">請審查您希望 Microsoft 管理桌面使用者擁有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8c73f-253">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="8c73f-254">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-254">**Advisory**</span></span>

<span data-ttu-id="8c73f-255">您應準備 Microsoft 管理桌面使用者擁有的應用程式庫存。</span><span class="sxs-lookup"><span data-stu-id="8c73f-255">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="8c73f-256">由於 Intune 必須部署這些應用程式，請評估是否重新使用現有的 Intune 應用程式。</span><span class="sxs-lookup"><span data-stu-id="8c73f-256">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="8c73f-257">請考慮使用公司入口 (裝置上的安裝 [Intune](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) 公司入口網站，以及 ESP (註冊狀態) 以將應用程式散發給使用者。</span><span class="sxs-lookup"><span data-stu-id="8c73f-257">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="8c73f-258">詳細資訊請參閱 Microsoft [Managed Desktop](apps.md) 中的應用程式以及 [Autopilot](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)的首次執行體驗，以及註冊狀態頁面。</span><span class="sxs-lookup"><span data-stu-id="8c73f-258">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="8c73f-259">您可以要求 Microsoft 帳戶代表在 Microsoft Endpoint Configuration Manager 中查詢，以找出那些已準備好要遷移至 Intune 或需要調整的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8c73f-259">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="8c73f-260">Windows Hello 企業版</span><span class="sxs-lookup"><span data-stu-id="8c73f-260">Windows Hello for Business</span></span>

<span data-ttu-id="8c73f-261">Microsoft Managed Desktop 需要啟用商務用 Windows Hello。</span><span class="sxs-lookup"><span data-stu-id="8c73f-261">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="8c73f-262">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-262">**Not ready**</span></span>

<span data-ttu-id="8c73f-263">已停用商務用 Windows Hello。</span><span class="sxs-lookup"><span data-stu-id="8c73f-263">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="8c73f-264">遵循建立商務用 Windows [Hello 政策中的步驟來啟用](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="8c73f-264">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="8c73f-265">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-265">**Advisory**</span></span>

<span data-ttu-id="8c73f-266">尚未設定商務用 Windows Hello。</span><span class="sxs-lookup"><span data-stu-id="8c73f-266">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="8c73f-267">請遵循建立商務用[Windows Hello 政策中的步驟來啟用。](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="8c73f-267">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="8c73f-268">Windows 10 更新環</span><span class="sxs-lookup"><span data-stu-id="8c73f-268">Windows 10 update rings</span></span>

<span data-ttu-id="8c73f-269">Intune 中的「Windows 10 更新環」策略不能以任何 Microsoft Managed Desktop 裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="8c73f-269">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="8c73f-270">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-270">**Not ready**</span></span>

<span data-ttu-id="8c73f-271">您的「更新環」策略會以所有裝置、所有使用者或兩者同時執行。</span><span class="sxs-lookup"><span data-stu-id="8c73f-271">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="8c73f-272">將群組原則變更為使用工作分派，該工作分派會以不包括任何 Microsoft 受管理之桌面裝置的特定 Azure AD 群組為物件。</span><span class="sxs-lookup"><span data-stu-id="8c73f-272">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8c73f-273">有關步驟，請參閱 [Intune 中的管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-273">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="8c73f-274">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-274">**Advisory**</span></span>

<span data-ttu-id="8c73f-275">請確定您擁有的任何更新鈴聲策略不包含新式工作場所裝置 **- 所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-275">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="8c73f-276">如果您已經將 Azure AD 使用者群組指派給這些策略，請確定您也排除所有您新增 Microsoft 受管理之桌面使用者至 (或相同群組) 的新式工作場所 **-** 所有 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-276">If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group).</span></span> <span data-ttu-id="8c73f-277">有關步驟，請參閱 [Intune 中的管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-277">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="8c73f-278">新式工作場所裝置 **-** 全部與現代化 **工作場所 - 所有** Azure AD 群組都是我們在您註冊 Microsoft Managed Desktop 時所建立群組，因此您註冊之後必須返回以排除此群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-278">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="8c73f-279">Azure Active Directory 設定</span><span class="sxs-lookup"><span data-stu-id="8c73f-279">Azure Active Directory settings</span></span>

<span data-ttu-id="8c73f-280">您可以在 Azure 入口網站存取 Azure Active Directory [設定](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-280">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="8c73f-281">Intune 註冊</span><span class="sxs-lookup"><span data-stu-id="8c73f-281">Intune enrollment</span></span>

<span data-ttu-id="8c73f-282">您 Azure AD 組織的 Windows 10 裝置必須能夠自動在 Intune 註冊。</span><span class="sxs-lookup"><span data-stu-id="8c73f-282">Windows 10 devices in your Azure AD organization must be able to automatically enroll in Intune.</span></span>

<span data-ttu-id="8c73f-283">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-283">**Advisory**</span></span>

<span data-ttu-id="8c73f-284">請確定 **MDM 使用者範圍已** 設定為部分或 **全部**，而非 **None。**</span><span class="sxs-lookup"><span data-stu-id="8c73f-284">Make sure the **MDM User scope** is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="8c73f-285">如果您選擇了一 **些**，請在註冊後返回，然後針對 **群組** 選取新式 **工作場所 -** 所有 Azure AD 群組，或以您所有 Microsoft Managed Desktop 使用者為目標的相同群組。</span><span class="sxs-lookup"><span data-stu-id="8c73f-285">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users.</span></span>  <span data-ttu-id="8c73f-286">請參閱 [使用 Microsoft Intune 設定 Windows 裝置註冊](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-286">See [Set up enrollment for Windows devices by using Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="8c73f-287">臨時訂閱</span><span class="sxs-lookup"><span data-stu-id="8c73f-287">Ad hoc subscriptions</span></span>

<span data-ttu-id="8c73f-288">建議如何檢查設定， (設定為 「false」時) 企業狀態漫遊無法正確執行。</span><span class="sxs-lookup"><span data-stu-id="8c73f-288">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="8c73f-289">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-289">**Advisory**</span></span>

<span data-ttu-id="8c73f-290">請確定 **AllowAdHocSubscriptions 已** 設為 **True。**</span><span class="sxs-lookup"><span data-stu-id="8c73f-290">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="8c73f-291">否則，企業狀態漫遊可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="8c73f-291">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="8c73f-292">詳細資訊請參閱[Set-MsolCompanySettings。](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="8c73f-292">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="8c73f-293">企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="8c73f-293">Enterprise State Roaming</span></span>

<span data-ttu-id="8c73f-294">應啟用企業狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="8c73f-294">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="8c73f-295">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-295">**Advisory**</span></span>

<span data-ttu-id="8c73f-296">確認已針對所有群組或所選群組啟用企業狀態 **漫遊**。</span><span class="sxs-lookup"><span data-stu-id="8c73f-296">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="8c73f-297">詳細資訊請參閱在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)中啟用企業狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="8c73f-297">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="8c73f-298">授權</span><span class="sxs-lookup"><span data-stu-id="8c73f-298">Licenses</span></span>

<span data-ttu-id="8c73f-299">需要許多授權才能使用 Microsoft Managed Desktop。</span><span class="sxs-lookup"><span data-stu-id="8c73f-299">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="8c73f-300">**尚未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-300">**Not Ready**</span></span>

<span data-ttu-id="8c73f-301">您沒有使用 Microsoft Managed Desktop 所需的所有授權。</span><span class="sxs-lookup"><span data-stu-id="8c73f-301">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="8c73f-302">詳細資訊請參閱 Microsoft [Managed Desktop 技術，](../intro/technologies.md) 以及 [更多授權資訊](prerequisites.md#more-about-licenses)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-302">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="8c73f-303">安全性帳戶名稱</span><span class="sxs-lookup"><span data-stu-id="8c73f-303">Security account names</span></span>

<span data-ttu-id="8c73f-304">某些安全性帳戶名稱可能會與 Microsoft Managed Desktop 建立的安全性帳戶名稱相衝突。</span><span class="sxs-lookup"><span data-stu-id="8c73f-304">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="8c73f-305">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-305">**Not ready**</span></span>

<span data-ttu-id="8c73f-306">您至少有一個帳戶名稱會與 Microsoft Managed Desktop 建立的帳戶名稱相衝突。</span><span class="sxs-lookup"><span data-stu-id="8c73f-306">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="8c73f-307">請與 Microsoft 客戶代表合作，排除這些帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="8c73f-307">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="8c73f-308">安全性系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="8c73f-308">Security administrator roles</span></span>

<span data-ttu-id="8c73f-309">具有特定安全性角色的使用者必須在 Microsoft Defender for Endpoint 中指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="8c73f-309">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="8c73f-310">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-310">**Advisory**</span></span>

<span data-ttu-id="8c73f-311">如果您的 Azure AD 組織中已指派使用者至任何這些角色，請確定他們在 Microsoft Defender for Endpoint 中也指派了這些角色。</span><span class="sxs-lookup"><span data-stu-id="8c73f-311">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8c73f-312">否則，具有這些角色的系統管理員將無法存取系統管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="8c73f-312">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="8c73f-313">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="8c73f-313">Security Operator</span></span>
- <span data-ttu-id="8c73f-314">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="8c73f-314">Global Reader</span></span>

<span data-ttu-id="8c73f-315">詳細資訊請參閱建立及 [管理角色型存取控制的角色](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-315">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="8c73f-316">安全性預設值</span><span class="sxs-lookup"><span data-stu-id="8c73f-316">Security default</span></span>

<span data-ttu-id="8c73f-317">Azure Active Directory 中的安全性預設值會防止 Microsoft 管理桌面管理您的裝置。</span><span class="sxs-lookup"><span data-stu-id="8c73f-317">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="8c73f-318">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="8c73f-318">**Not ready**</span></span>

<span data-ttu-id="8c73f-319">您開啟了安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="8c73f-319">You have Security defaults turned on.</span></span> <span data-ttu-id="8c73f-320">關閉安全性預設值並設定條件式存取策略。</span><span class="sxs-lookup"><span data-stu-id="8c73f-320">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="8c73f-321">有關詳細資訊，請參閱常見的 [條件式存取政策](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-321">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="8c73f-322">自助密碼重設</span><span class="sxs-lookup"><span data-stu-id="8c73f-322">Self-service Password Reset</span></span>

<span data-ttu-id="8c73f-323">自助密碼重設 (SSPR) 可以針對 Microsoft Managed Desktop 服務帳戶除外的所有 Microsoft Managed Desktop 使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="8c73f-323">Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="8c73f-324">有關詳細資訊，請參閱教學課程：讓使用者使用 Azure Active Directory 自助密碼重設來解除鎖定其帳戶或 [重設密碼](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-324">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="8c73f-325">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-325">**Advisory**</span></span>

<span data-ttu-id="8c73f-326">請確定 SSPR **選取** 的設定包含 Microsoft Managed Desktop 使用者，但不包含 Microsoft Managed Desktop 服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="8c73f-326">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="8c73f-327">啟用 SSPR 時，Microsoft Managed Desktop 服務帳戶無法如預期般使用。</span><span class="sxs-lookup"><span data-stu-id="8c73f-327">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="8c73f-328">標準使用者角色</span><span class="sxs-lookup"><span data-stu-id="8c73f-328">Standard user role</span></span>

<span data-ttu-id="8c73f-329">除了被指派全域系統管理員和裝置系統管理員 Azure AD 角色的使用者外，Microsoft Managed Desktop 使用者都是沒有本地系統管理員許可權的標準使用者。</span><span class="sxs-lookup"><span data-stu-id="8c73f-329">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="8c73f-330">所有其他使用者在啟動其 Microsoft Managed Desktop 裝置時，都會被指派標準使用者角色。</span><span class="sxs-lookup"><span data-stu-id="8c73f-330">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="8c73f-331">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-331">**Advisory**</span></span>

<span data-ttu-id="8c73f-332">註冊後，Microsoft 受管理桌面使用者將沒有 Microsoft 受管理桌面裝置上的系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="8c73f-332">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="8c73f-333">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="8c73f-333">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="8c73f-334">OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c73f-334">OneDrive</span></span>

<span data-ttu-id="8c73f-335">只有 **加入特定網域設定之** PC 上的允許同步處理功能會與 Microsoft Managed Desktop 衝突。</span><span class="sxs-lookup"><span data-stu-id="8c73f-335">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="8c73f-336">您可以在 OneDrive 系統管理中心存取 OneDrive [設定](https://admin.onedrive.com)。</span><span class="sxs-lookup"><span data-stu-id="8c73f-336">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="8c73f-337">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="8c73f-337">**Advisory**</span></span>

<span data-ttu-id="8c73f-338">您只在加入特定網域 **設定的電腦使用允許同步** 。</span><span class="sxs-lookup"><span data-stu-id="8c73f-338">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="8c73f-339">此設定無法與 Microsoft 管理桌上出版一同使用。</span><span class="sxs-lookup"><span data-stu-id="8c73f-339">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="8c73f-340">停用此設定，並改為設定 OneDrive 使用條件式存取策略。</span><span class="sxs-lookup"><span data-stu-id="8c73f-340">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="8c73f-341">請參閱 [規劃條件式存取部署以](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 取得協助。</span><span class="sxs-lookup"><span data-stu-id="8c73f-341">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

