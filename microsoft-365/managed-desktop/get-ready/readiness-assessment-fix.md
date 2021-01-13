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
ms.openlocfilehash: ada6bb8ef66e3414a375a151b45d4871e306e825
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841061"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="192fd-104">修正由整備評估工具發現的問題</span><span class="sxs-lookup"><span data-stu-id="192fd-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="192fd-105">針對每個檢查，該工具會報告下列四個可能的結果之一：</span><span class="sxs-lookup"><span data-stu-id="192fd-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="192fd-106">結果</span><span class="sxs-lookup"><span data-stu-id="192fd-106">Result</span></span>  |<span data-ttu-id="192fd-107">意義</span><span class="sxs-lookup"><span data-stu-id="192fd-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="192fd-108">就緒</span><span class="sxs-lookup"><span data-stu-id="192fd-108">Ready</span></span>     | <span data-ttu-id="192fd-109">完成註冊之前，不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="192fd-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="192fd-110">諮詢</span><span class="sxs-lookup"><span data-stu-id="192fd-110">Advisory</span></span>    | <span data-ttu-id="192fd-111">請遵循工具或本文中的步驟，以取得註冊和使用者的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="192fd-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="192fd-112">您 *可以* 完成註冊，但是必須先修正這些問題，再部署第一個裝置。</span><span class="sxs-lookup"><span data-stu-id="192fd-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="192fd-113">未就緒</span><span class="sxs-lookup"><span data-stu-id="192fd-113">Not ready</span></span> | <span data-ttu-id="192fd-114">*如果您未修正這些問題，註冊將會失敗。*</span><span class="sxs-lookup"><span data-stu-id="192fd-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="192fd-115">請遵循工具或本文中的步驟加以解決。</span><span class="sxs-lookup"><span data-stu-id="192fd-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="192fd-116">錯誤</span><span class="sxs-lookup"><span data-stu-id="192fd-116">Error</span></span> | <span data-ttu-id="192fd-117">您所使用的 Azure Active Director (AD) 角色，沒有足夠的許可權可執行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="192fd-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="192fd-118">此工具報告的結果會反映您的設定狀態，只會在您執行它的特定時間點反映。</span><span class="sxs-lookup"><span data-stu-id="192fd-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="192fd-119">如果您稍後對 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的原則進行任何變更，「就緒」的專案便會變成「尚未準備好」。</span><span class="sxs-lookup"><span data-stu-id="192fd-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="192fd-120">若要避免 Microsoft 受管理桌面作業的問題，請在變更任何原則之前，先檢查本文中所述的特定設定。</span><span class="sxs-lookup"><span data-stu-id="192fd-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="192fd-121">Microsoft Intune 設定</span><span class="sxs-lookup"><span data-stu-id="192fd-121">Microsoft Intune settings</span></span>

<span data-ttu-id="192fd-122">您可以在 Microsoft 端點[管理員管理中心存取 Intune 設定。](https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="192fd-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="192fd-123">Autopilot 部署設定檔</span><span class="sxs-lookup"><span data-stu-id="192fd-123">Autopilot deployment profile</span></span>

<span data-ttu-id="192fd-124">您不應該有任何現有的 Autopilot 設定檔，是 Microsoft Managed Desktop 所使用的指派或動態群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="192fd-125">Microsoft 受管理的桌面會使用 Autopilot 布建新裝置。</span><span class="sxs-lookup"><span data-stu-id="192fd-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="192fd-126">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-126">**Not ready**</span></span>

<span data-ttu-id="192fd-127">您有指派給所有裝置的 Autopilot 設定檔。</span><span class="sxs-lookup"><span data-stu-id="192fd-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="192fd-128">如需步驟，請參閱 [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="192fd-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="192fd-129">Microsoft 受管理的桌上型電腦註冊後，請將您的 Autopilot 原則設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="192fd-130">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-130">**Advisory**</span></span>

<span data-ttu-id="192fd-131">請確定您的 Autopilot 設定檔目標是指派或動態 Azure AD 群組，但不包含將在註冊時建立的 Microsoft 受管理桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="192fd-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="192fd-132">如需步驟，請參閱 [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="192fd-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="192fd-133">Microsoft 受管理的桌上型電腦註冊後，請將您的 Autopilot 原則設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-133">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="192fd-134">憑證連接器</span><span class="sxs-lookup"><span data-stu-id="192fd-134">Certificate connectors</span></span>

<span data-ttu-id="192fd-135">如果您有任何您想要在 Microsoft 受管理的電腦上登錄之裝置使用的憑證連接器，連接器就不能有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="192fd-135">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="192fd-136">下列其中一項諮詢只適用于您的情況，所以請務必仔細檢查。</span><span class="sxs-lookup"><span data-stu-id="192fd-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="192fd-137">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-137">**Advisory**</span></span>

<span data-ttu-id="192fd-138">不存在任何憑證連接器。</span><span class="sxs-lookup"><span data-stu-id="192fd-138">No certificate connectors are present.</span></span> <span data-ttu-id="192fd-139">您可能不需要任何連接器，但您應評估您是否需要部分網路連接至 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="192fd-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="192fd-140">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="192fd-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="192fd-141">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-141">**Advisory**</span></span>

<span data-ttu-id="192fd-142">至少有一個憑證連接器有錯誤。</span><span class="sxs-lookup"><span data-stu-id="192fd-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="192fd-143">如果您需要此連接器才能連線至 Microsoft 受管理的桌面裝置，您必須解決該錯誤。</span><span class="sxs-lookup"><span data-stu-id="192fd-143">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="192fd-144">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="192fd-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="192fd-145">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-145">**Advisory**</span></span>

<span data-ttu-id="192fd-146">您至少有一個憑證連接器，而且不會報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="192fd-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="192fd-147">不過，您可能需要建立設定檔，以重複使用 Microsoft 受管理的桌面裝置的連接器。</span><span class="sxs-lookup"><span data-stu-id="192fd-147">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="192fd-148">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="192fd-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="192fd-149">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="192fd-149">Conditional access policies</span></span>

<span data-ttu-id="192fd-150">Azure AD 組織中的條件式存取原則不得以任何 Microsoft 管理桌面使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="192fd-150">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="192fd-151">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-151">**Not ready**</span></span>

<span data-ttu-id="192fd-152">您有至少一個目標為所有使用者的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="192fd-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="192fd-153">將原則重設為面向不包含將在註冊時建立之 Microsoft Managed Desktop service 帳戶之 Azure AD 群組的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-153">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="192fd-154">如需步驟，請參閱 [條件式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="192fd-154">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="192fd-155">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-155">**Advisory**</span></span>

<span data-ttu-id="192fd-156">請確定任何條件式存取原則都排除了 **現代的 Workplace Service 帳戶** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-156">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="192fd-157">如需步驟，請參閱 [調整條件式存取](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="192fd-157">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="192fd-158">**新式的 Workplace Service 帳戶** Azure AD 群組是我們在您註冊時，為服務建立的動態群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-158">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="192fd-159">註冊後，您必須回到以排除此群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-159">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="192fd-160">如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="192fd-160">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="192fd-161">**錯誤**</span><span class="sxs-lookup"><span data-stu-id="192fd-161">**Error**</span></span>

<span data-ttu-id="192fd-162">Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="192fd-162">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="192fd-163">您也需要指派的任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="192fd-163">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="192fd-164">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="192fd-164">Security Reader</span></span>
- <span data-ttu-id="192fd-165">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="192fd-165">Security Administrator</span></span>
- <span data-ttu-id="192fd-166">條件式存取管理員</span><span class="sxs-lookup"><span data-stu-id="192fd-166">Conditional Access Administrator</span></span>
- <span data-ttu-id="192fd-167">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="192fd-167">Global Reader</span></span>
- <span data-ttu-id="192fd-168">裝置管理員</span><span class="sxs-lookup"><span data-stu-id="192fd-168">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="192fd-169">裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="192fd-169">Device Compliance policies</span></span>

<span data-ttu-id="192fd-170">Azure AD 組織中的 Intune 裝置相容性原則不得以 Microsoft 受管理的桌面使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="192fd-170">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="192fd-171">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-171">**Not ready**</span></span>

<span data-ttu-id="192fd-172">您至少具有一個針對所有使用者的符合性原則。</span><span class="sxs-lookup"><span data-stu-id="192fd-172">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="192fd-173">將原則重設為面向不包含任何 Microsoft 受管理桌面使用者的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-173">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="192fd-174">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="192fd-174">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="192fd-175">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-175">**Advisory**</span></span>

<span data-ttu-id="192fd-176">請確定任何您沒有的相容性原則都包含任何 Microsoft 受管理的桌面使用者。</span><span class="sxs-lookup"><span data-stu-id="192fd-176">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="192fd-177">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="192fd-177">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="192fd-178">裝置設定原則</span><span class="sxs-lookup"><span data-stu-id="192fd-178">Device Configuration policies</span></span>

<span data-ttu-id="192fd-179">Azure AD 組織中的 Intune 裝置設定原則不得針對任何 Microsoft 管理桌面裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="192fd-179">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="192fd-180">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-180">**Not ready**</span></span>

<span data-ttu-id="192fd-181">您至少要有一個設定原則，針對所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="192fd-181">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="192fd-182">針對不包含任何 Microsoft 受管理桌面裝置的特定 Azure AD 群組，將原則重設為 [目標]。</span><span class="sxs-lookup"><span data-stu-id="192fd-182">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="192fd-183">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="192fd-183">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="192fd-184">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-184">**Advisory**</span></span>

<span data-ttu-id="192fd-185">請確定任何您沒有的相容性原則都包含任何 Microsoft 受管理的桌面裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="192fd-185">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="192fd-186">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="192fd-186">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="192fd-187">裝置類型限制</span><span class="sxs-lookup"><span data-stu-id="192fd-187">Device type restrictions</span></span>

<span data-ttu-id="192fd-188">Microsoft 受管理的桌面裝置必須能夠在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="192fd-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="192fd-189">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-189">**Not ready**</span></span>

<span data-ttu-id="192fd-190">依照 [設定註冊限制](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) 中的步驟，將設定變更為 [ **允許**]。</span><span class="sxs-lookup"><span data-stu-id="192fd-190">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="192fd-191">註冊狀態頁面</span><span class="sxs-lookup"><span data-stu-id="192fd-191">Enrollment Status Page</span></span>

<span data-ttu-id="192fd-192">您目前已啟用「註冊狀態」頁面 (ESP) 。</span><span class="sxs-lookup"><span data-stu-id="192fd-192">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="192fd-193">如果您參與此功能的公開預覽，可以略過此專案。</span><span class="sxs-lookup"><span data-stu-id="192fd-193">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="192fd-194">如需詳細資訊，請參閱 [使用 Autopilot 和註冊狀態頁面的初次執行體驗](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="192fd-194">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="192fd-195">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-195">**Not ready**</span></span>

<span data-ttu-id="192fd-196">您已設定 ESP 預設設定檔來 **顯示應用程式和設定檔設定進度**。</span><span class="sxs-lookup"><span data-stu-id="192fd-196">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="192fd-197">停用此設定，或遵循 [設定 [註冊狀態] 頁面](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)中的步驟，確定任何 Azure AD 群組的指派均未包含 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="192fd-197">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="192fd-198">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-198">**Advisory**</span></span>

<span data-ttu-id="192fd-199">請確定任何具有「 **顯示應用程式和設定檔設定進度** 」設定的設定檔都未指派給任何包含 Microsoft 受管理的桌面裝置的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-199">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="192fd-200">如需詳細資訊，請參閱 [設定註冊狀態頁面](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="192fd-200">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="192fd-201">Intune 登記</span><span class="sxs-lookup"><span data-stu-id="192fd-201">Intune enrollment</span></span>

<span data-ttu-id="192fd-202">Azure AD 組織中的 Windows 10 裝置必須在 Intune 中自動註冊。</span><span class="sxs-lookup"><span data-stu-id="192fd-202">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="192fd-203">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-203">**Advisory**</span></span>

<span data-ttu-id="192fd-204">確定 MDM 使用者範圍已設定為 **部分** 或 **全部**（非 **無**）。</span><span class="sxs-lookup"><span data-stu-id="192fd-204">Make sure the MDM User scope is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="192fd-205">如果您選擇 [ **部分**]，請在註冊後再進行註冊，然後選取 [ **現代工作場所-** **群組** 的所有 Azure AD 群組]。</span><span class="sxs-lookup"><span data-stu-id="192fd-205">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="192fd-206">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="192fd-206">Microsoft Store for Business</span></span>

<span data-ttu-id="192fd-207">我們使用 Microsoft Store for Business，可讓您下載公司入口網站，以部署某些應用程式，例如 Microsoft Project 和 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="192fd-207">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="192fd-208">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-208">**Not ready**</span></span>

<span data-ttu-id="192fd-209">商務用 Microsoft Store 未啟用或未與 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="192fd-209">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="192fd-210">如需詳細資訊，請參閱 how [to 使用 Microsoft Intune 管理大量購買的應用程式](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) ，以及 [在裝置上安裝 Intune 公司入口網站](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="192fd-210">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="192fd-211">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="192fd-211">Multifactor authentication</span></span>

<span data-ttu-id="192fd-212">多重要素驗證不得意外套用至 Microsoft Managed Desktop service 帳戶。</span><span class="sxs-lookup"><span data-stu-id="192fd-212">Multifactor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="192fd-213">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-213">**Not ready**</span></span>

<span data-ttu-id="192fd-214">您對指派給所有使用者的條件式存取原則，將 MFA) 原則設定為「必要」，以進行某些多重要素驗證 (。</span><span class="sxs-lookup"><span data-stu-id="192fd-214">You have some multifactor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="192fd-215">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="192fd-215">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="192fd-216">如需詳細資訊，請參閱 [條件式存取原則](#conditional-access-policies) 和 [條件式存取：針對所有使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="192fd-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="192fd-217">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-217">**Advisory**</span></span>

<span data-ttu-id="192fd-218">請確定任何需要 MFA 的條件式存取原則排除 **新式的 Workplace-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-218">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="192fd-219">如需詳細資訊，請參閱 [條件式存取原則](#conditional-access-policies) 和 [條件式存取：針對所有使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="192fd-219">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="192fd-220">**新式的工作場所-所有** Azure AD 群組是我們在您註冊 Microsoft Managed Desktop 時所建立的動態群組，所以您必須在註冊後傳回排除此群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-220">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="192fd-221">**錯誤**</span><span class="sxs-lookup"><span data-stu-id="192fd-221">**Error**</span></span>

<span data-ttu-id="192fd-222">Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="192fd-222">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="192fd-223">您也需要指派的任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="192fd-223">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="192fd-224">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="192fd-224">Security Reader</span></span>
- <span data-ttu-id="192fd-225">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="192fd-225">Security Administrator</span></span>
- <span data-ttu-id="192fd-226">條件式存取管理員</span><span class="sxs-lookup"><span data-stu-id="192fd-226">Conditional Access Administrator</span></span>
- <span data-ttu-id="192fd-227">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="192fd-227">Global Reader</span></span>
- <span data-ttu-id="192fd-228">裝置管理員</span><span class="sxs-lookup"><span data-stu-id="192fd-228">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="192fd-229">PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="192fd-229">PowerShell scripts</span></span>

<span data-ttu-id="192fd-230">Windows PowerShell 腳本無法指派為以 Microsoft 受管理的桌面裝置為目標的方式。</span><span class="sxs-lookup"><span data-stu-id="192fd-230">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="192fd-231">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-231">**Advisory**</span></span>

<span data-ttu-id="192fd-232">確定您的 Azure AD 組織中的 Windows PowerShell 腳本並未以任何 Microsoft 管理桌面裝置或使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="192fd-232">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="192fd-233">請勿指派 PowerShell 腳本來設定所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="192fd-233">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="192fd-234">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="192fd-234">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="192fd-235">如需詳細資訊，請參閱在 [Intune 中使用 Windows 10 裝置上的 PowerShell 腳本](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="192fd-235">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="192fd-236">地區</span><span class="sxs-lookup"><span data-stu-id="192fd-236">Region</span></span>

<span data-ttu-id="192fd-237">您的區域必須支援 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="192fd-237">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="192fd-238">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-238">**Not ready**</span></span>

<span data-ttu-id="192fd-239">Microsoft 受管理的電腦目前不支援您的 Azure AD 組織區域。</span><span class="sxs-lookup"><span data-stu-id="192fd-239">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="192fd-240">如需詳細資訊，請參閱 [Microsoft 受管理的桌面支援的地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="192fd-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="192fd-241">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-241">**Advisory**</span></span>

<span data-ttu-id="192fd-242">Microsoft 受管理的電腦不支援 Azure AD 組織所在的一或多個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="192fd-242">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="192fd-243">如需詳細資訊，請參閱 [Microsoft 受管理的桌面支援的地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="192fd-243">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="192fd-244">安全性基準</span><span class="sxs-lookup"><span data-stu-id="192fd-244">Security baselines</span></span>

<span data-ttu-id="192fd-245">安全性基準原則不應該以任何 Microsoft 受管理的桌面裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="192fd-245">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="192fd-246">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-246">**Not ready**</span></span>

<span data-ttu-id="192fd-247">您有一個針對所有使用者、所有裝置或兩者的安全性基準設定檔。</span><span class="sxs-lookup"><span data-stu-id="192fd-247">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="192fd-248">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="192fd-248">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="192fd-249">如需步驟，請參閱 [使用安全性基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="192fd-249">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="192fd-250">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-250">**Advisory**</span></span>

<span data-ttu-id="192fd-251">請確定所有的安全性基準原則都排除 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="192fd-251">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="192fd-252">如需步驟，請參閱 [使用安全性基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="192fd-252">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="192fd-253">**新式的工作場所裝置-所有** Azure AD 群組是我們在您註冊 Microsoft Managed Desktop 時所建立的動態群組，所以您必須在註冊後傳回排除此群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-253">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="192fd-254">Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="192fd-254">Windows apps</span></span>

<span data-ttu-id="192fd-255">查看您要讓 Microsoft 受管理的桌面使用者擁有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="192fd-255">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="192fd-256">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-256">**Advisory**</span></span>

<span data-ttu-id="192fd-257">您應該準備要讓 Microsoft 受管理的桌面使用者擁有的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="192fd-257">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="192fd-258">由於這些應用程式必須透過 Intune 部署，因此請評估重複使用現有的 Intune 應用程式。</span><span class="sxs-lookup"><span data-stu-id="192fd-258">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="192fd-259">考慮使用公司入口 (請參閱在裝置和註冊狀態頁面 [上安裝 Intune 公司入口網站](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) (ESP) ，將應用程式發佈至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="192fd-259">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="192fd-260">如需詳細資訊，請參閱 [Microsoft 受管理的桌面](apps.md) 和初次執行體驗中的應用程式 [與 Autopilot 和註冊狀態頁面](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)。</span><span class="sxs-lookup"><span data-stu-id="192fd-260">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="192fd-261">您可以要求 Microsoft 帳戶代表在 Microsoft 端點 Configuration Manager 中查詢，以識別準備好要遷移至 Intune 或需要調整的應用程式。</span><span class="sxs-lookup"><span data-stu-id="192fd-261">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="192fd-262">Windows Hello 企業版</span><span class="sxs-lookup"><span data-stu-id="192fd-262">Windows Hello for Business</span></span>

<span data-ttu-id="192fd-263">Microsoft 受管理的桌面需要啟用 Windows Hello 企業版功能。</span><span class="sxs-lookup"><span data-stu-id="192fd-263">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="192fd-264">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-264">**Not ready**</span></span>

<span data-ttu-id="192fd-265">Windows Hello 企業版已停用。</span><span class="sxs-lookup"><span data-stu-id="192fd-265">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="192fd-266">遵循[建立 Windows Hello 企業版原則](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用</span><span class="sxs-lookup"><span data-stu-id="192fd-266">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="192fd-267">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-267">**Advisory**</span></span>

<span data-ttu-id="192fd-268">未設定 Windows Hello 企業版。</span><span class="sxs-lookup"><span data-stu-id="192fd-268">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="192fd-269">遵循 [建立 Windows Hello 企業版原則](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用它。</span><span class="sxs-lookup"><span data-stu-id="192fd-269">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="192fd-270">Windows 10 更新環</span><span class="sxs-lookup"><span data-stu-id="192fd-270">Windows 10 update rings</span></span>

<span data-ttu-id="192fd-271">Intune 中的「Windows 10 更新環路」原則不得以 Microsoft 受管理的桌面裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="192fd-271">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="192fd-272">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-272">**Not ready**</span></span>

<span data-ttu-id="192fd-273">您有一個「更新鈴聲」原則，針對所有裝置、所有使用者或兩者。</span><span class="sxs-lookup"><span data-stu-id="192fd-273">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="192fd-274">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="192fd-274">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="192fd-275">如需步驟，請參閱 [在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="192fd-275">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="192fd-276">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-276">**Advisory**</span></span>

<span data-ttu-id="192fd-277">請確定任何更新環原則您已排除現代的 **工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-277">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="192fd-278">如果您已將 Azure AD 使用者群組指派給這些原則，請確定任何更新環原則您已排除現代的 **工作場所-所有** 包含您的 Microsoft 受管理桌面使用者的 azure ad 群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-278">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="192fd-279">如需步驟，請參閱 [在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="192fd-279">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="192fd-280">兩個 **新式的工作場所裝置-所有** 及 **現代的工作場所-所有** Azure AD 群組都是在您註冊 Microsoft Managed Desktop 時所建立的群組，所以您必須回到註冊後再排除此群組。</span><span class="sxs-lookup"><span data-stu-id="192fd-280">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="192fd-281">Azure Active Directory 設定</span><span class="sxs-lookup"><span data-stu-id="192fd-281">Azure Active Directory settings</span></span>

<span data-ttu-id="192fd-282">您可以在 [azure 入口網站](https://portal.azure.com)中存取 Azure Active Directory 設定。</span><span class="sxs-lookup"><span data-stu-id="192fd-282">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="192fd-283">專用訂閱</span><span class="sxs-lookup"><span data-stu-id="192fd-283">Ad hoc subscriptions</span></span>

<span data-ttu-id="192fd-284">建議您如何檢查設定為 "false" 的設定 () 可能會讓企業狀態漫遊無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="192fd-284">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="192fd-285">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-285">**Advisory**</span></span>

<span data-ttu-id="192fd-286">確定 **AllowAdHocSubscriptions** 設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="192fd-286">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="192fd-287">否則，企業狀態漫遊可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="192fd-287">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="192fd-288">如需詳細資訊，請參閱 [MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="192fd-288">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="192fd-289">企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="192fd-289">Enterprise State Roaming</span></span>

<span data-ttu-id="192fd-290">應啟用企業狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="192fd-290">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="192fd-291">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-291">**Advisory**</span></span>

<span data-ttu-id="192fd-292">請確定已針對 **所有** 或 **選取** 的群組啟用企業狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="192fd-292">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="192fd-293">如需詳細資訊，請參閱 [在 Azure Active Directory 中啟用企業狀態漫遊](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="192fd-293">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="192fd-294">授權</span><span class="sxs-lookup"><span data-stu-id="192fd-294">Licenses</span></span>

<span data-ttu-id="192fd-295">使用 Microsoft 受管理的桌面需要一些授權。</span><span class="sxs-lookup"><span data-stu-id="192fd-295">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="192fd-296">**尚未準備好**</span><span class="sxs-lookup"><span data-stu-id="192fd-296">**Not Ready**</span></span>

<span data-ttu-id="192fd-297">您沒有使用 Microsoft 管理的桌面所需的所有授權。</span><span class="sxs-lookup"><span data-stu-id="192fd-297">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="192fd-298">如需詳細資訊，請參閱 [Microsoft 管理的桌面技術](../intro/technologies.md) 和 [有關授權的詳細](prerequisites.md#more-about-licenses)資訊。</span><span class="sxs-lookup"><span data-stu-id="192fd-298">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="192fd-299">安全性帳戶名稱</span><span class="sxs-lookup"><span data-stu-id="192fd-299">Security account names</span></span>

<span data-ttu-id="192fd-300">某些安全性帳戶名稱會與 Microsoft Managed Desktop 所建立的名稱相衝突。</span><span class="sxs-lookup"><span data-stu-id="192fd-300">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="192fd-301">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-301">**Not ready**</span></span>

<span data-ttu-id="192fd-302">您至少要有一個帳戶名稱會與 Microsoft Managed Desktop 所建立的帳戶名稱產生衝突。</span><span class="sxs-lookup"><span data-stu-id="192fd-302">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="192fd-303">請與您的 Microsoft 帳戶代表合作，以排除這些帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="192fd-303">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="192fd-304">安全性管理員角色</span><span class="sxs-lookup"><span data-stu-id="192fd-304">Security administrator roles</span></span>

<span data-ttu-id="192fd-305">具有特定安全性角色的使用者必須在 Microsoft Defender for Endpoint 中指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="192fd-305">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="192fd-306">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-306">**Advisory**</span></span>

<span data-ttu-id="192fd-307">如果您已將使用者指派至 Azure AD 組織中的任何角色，請確定他們也在 Microsoft Defender for Endpoint 中指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="192fd-307">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="192fd-308">否則，具有這些角色的系統管理員將無法存取管理員入口網站。</span><span class="sxs-lookup"><span data-stu-id="192fd-308">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="192fd-309">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="192fd-309">Security Operator</span></span>
- <span data-ttu-id="192fd-310">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="192fd-310">Global Reader</span></span>

<span data-ttu-id="192fd-311">如需詳細資訊，請參閱 [建立及管理以角色為基礎的存取控制角色](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="192fd-311">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="192fd-312">安全性預設值</span><span class="sxs-lookup"><span data-stu-id="192fd-312">Security default</span></span>

<span data-ttu-id="192fd-313">在 Azure Active Directory 中的安全性預設值會使 Microsoft Managed Desktop 無法管理您的裝置。</span><span class="sxs-lookup"><span data-stu-id="192fd-313">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="192fd-314">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="192fd-314">**Not ready**</span></span>

<span data-ttu-id="192fd-315">您已開啟安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="192fd-315">You have Security defaults turned on.</span></span> <span data-ttu-id="192fd-316">關閉安全性預設值，並設定條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="192fd-316">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="192fd-317">如需詳細資訊，請參閱 [一般條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="192fd-317">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="192fd-318">自助密碼重設</span><span class="sxs-lookup"><span data-stu-id="192fd-318">Self-service Password Reset</span></span>

<span data-ttu-id="192fd-319">自助密碼重設 (SSPR) 應該針對所有不含 Microsoft Managed Desktop 服務帳戶的 Microsoft 受管理的桌面使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="192fd-319">Self-service Password Reset (SSPR) should be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="192fd-320">如需詳細資訊，請參閱 [教學課程：讓使用者可以使用 Azure Active Directory 自助密碼重設來解除鎖定帳戶或重設密碼](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="192fd-320">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="192fd-321">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-321">**Advisory**</span></span>

<span data-ttu-id="192fd-322">請確定 [SSPR **選取** ] 設定包括 Microsoft 受管理的桌面裝置，但不包括 Microsoft 受管理的桌面服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="192fd-322">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="192fd-323">SSPR 啟用時，Microsoft Managed Desktop service 帳戶無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="192fd-323">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="192fd-324">標準使用者角色</span><span class="sxs-lookup"><span data-stu-id="192fd-324">Standard user role</span></span>

<span data-ttu-id="192fd-325">除了為全域系統管理員和裝置管理員指派 Azure AD 角色的使用者以外，Microsoft 受管理的桌面使用者將是不具備本機系統管理員許可權的標準使用者。</span><span class="sxs-lookup"><span data-stu-id="192fd-325">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="192fd-326">當其他使用者啟動其 Microsoft 受管理的桌面裝置時，系統會將其指派為標準使用者角色。</span><span class="sxs-lookup"><span data-stu-id="192fd-326">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="192fd-327">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-327">**Advisory**</span></span>

<span data-ttu-id="192fd-328">Microsoft 受管理的桌面使用者在註冊後，不會對其 Microsoft 受管理的桌面裝置具有本機系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="192fd-328">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="192fd-329">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="192fd-329">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="192fd-330">OneDrive</span><span class="sxs-lookup"><span data-stu-id="192fd-330">OneDrive</span></span>

<span data-ttu-id="192fd-331">[ **僅允許在加入特定網域的電腦上進行同步** 處理] 設定會與 Microsoft 受管理的桌面產生衝突。</span><span class="sxs-lookup"><span data-stu-id="192fd-331">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="192fd-332">您可以在 OneDrive 系統 [管理中心](https://admin.onedrive.com)存取 OneDrive 設定。</span><span class="sxs-lookup"><span data-stu-id="192fd-332">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="192fd-333">**諮詢**</span><span class="sxs-lookup"><span data-stu-id="192fd-333">**Advisory**</span></span>

<span data-ttu-id="192fd-334">您正在使用 [ **僅允許在加入特定網域的電腦上同步** 處理] 設定。</span><span class="sxs-lookup"><span data-stu-id="192fd-334">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="192fd-335">此設定不會與 Microsoft 受管理的桌面搭配使用。</span><span class="sxs-lookup"><span data-stu-id="192fd-335">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="192fd-336">停用此設定，而不是設定 OneDrive 使用條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="192fd-336">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="192fd-337">請參閱 [規劃設定條件式存取部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 以取得協助。</span><span class="sxs-lookup"><span data-stu-id="192fd-337">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

