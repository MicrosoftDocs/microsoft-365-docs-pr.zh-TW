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
ms.openlocfilehash: 75c2967037ae83abca2aaa3cd02d1f6b2ae14caa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925913"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="b231c-104">修正由整備評估工具發現的問題</span><span class="sxs-lookup"><span data-stu-id="b231c-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="b231c-105">針對每個檢查，該工具會報告下列四個可能的結果之一：</span><span class="sxs-lookup"><span data-stu-id="b231c-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="b231c-106">結果</span><span class="sxs-lookup"><span data-stu-id="b231c-106">Result</span></span>  |<span data-ttu-id="b231c-107">意義</span><span class="sxs-lookup"><span data-stu-id="b231c-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="b231c-108">就緒</span><span class="sxs-lookup"><span data-stu-id="b231c-108">Ready</span></span>     | <span data-ttu-id="b231c-109">完成註冊之前，不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="b231c-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="b231c-110">公告</span><span class="sxs-lookup"><span data-stu-id="b231c-110">Advisory</span></span>    | <span data-ttu-id="b231c-111">請遵循工具或本文中的步驟，以取得註冊和使用者的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="b231c-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="b231c-112">您 *可以* 完成註冊，但是必須先修正這些問題，再部署第一個裝置。</span><span class="sxs-lookup"><span data-stu-id="b231c-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="b231c-113">未就緒</span><span class="sxs-lookup"><span data-stu-id="b231c-113">Not ready</span></span> | <span data-ttu-id="b231c-114">*如果您未修正這些問題，註冊將會失敗。*</span><span class="sxs-lookup"><span data-stu-id="b231c-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="b231c-115">請遵循工具或本文中的步驟加以解決。</span><span class="sxs-lookup"><span data-stu-id="b231c-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="b231c-116">錯誤</span><span class="sxs-lookup"><span data-stu-id="b231c-116">Error</span></span> | <span data-ttu-id="b231c-117">您所使用的 Azure Active Directory (AD) 角色沒有足夠的許可權可執行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="b231c-117">The Azure Active Directory (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="b231c-118">此工具報告的結果會反映您的設定狀態，只會在您執行它的特定時間點反映。</span><span class="sxs-lookup"><span data-stu-id="b231c-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="b231c-119">如果您稍後對 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的原則進行任何變更，「就緒」的專案便會變成「尚未準備好」。</span><span class="sxs-lookup"><span data-stu-id="b231c-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="b231c-120">若要避免 Microsoft 受管理桌面作業的問題，請在變更任何原則之前，先檢查本文中所述的特定設定。</span><span class="sxs-lookup"><span data-stu-id="b231c-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="b231c-121">Microsoft Intune 設定</span><span class="sxs-lookup"><span data-stu-id="b231c-121">Microsoft Intune settings</span></span>

<span data-ttu-id="b231c-122">您可以在 Microsoft 端點[管理員管理中心存取 Intune 設定。](https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b231c-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="b231c-123">Autopilot 部署設定檔</span><span class="sxs-lookup"><span data-stu-id="b231c-123">Autopilot deployment profile</span></span>

<span data-ttu-id="b231c-124">您不應該有任何現有的 Autopilot 設定檔，以 Microsoft 受管理的桌面裝置為指派或動態群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b231c-125">Microsoft 受管理的桌面會使用 Autopilot 布建新裝置。</span><span class="sxs-lookup"><span data-stu-id="b231c-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="b231c-126">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-126">**Not ready**</span></span>

<span data-ttu-id="b231c-127">您有指派給所有裝置的 Autopilot 設定檔。</span><span class="sxs-lookup"><span data-stu-id="b231c-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="b231c-128">如需步驟，請參閱 [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="b231c-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="b231c-129">Microsoft 受管理的桌上型電腦註冊後，請將您的 Autopilot 原則設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="b231c-130">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-130">**Advisory**</span></span>

<span data-ttu-id="b231c-131">請確定您的 Autopilot 設定檔目標是未包含 Microsoft 受管理桌面裝置的指派或動態 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b231c-132">如需步驟，請參閱 [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="b231c-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="b231c-133">Microsoft 受管理的桌上型電腦註冊後，將您的 Autopilot 設定檔設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-133">After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="b231c-134">憑證連接器</span><span class="sxs-lookup"><span data-stu-id="b231c-134">Certificate connectors</span></span>

<span data-ttu-id="b231c-135">如果您有任何您想要在 Microsoft Managed Desktop 中註冊的裝置使用的憑證連接器，連接器應該不會有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="b231c-135">If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors should not have any errors.</span></span> <span data-ttu-id="b231c-136">下列其中一項諮詢只適用于您的情況，所以請務必仔細檢查。</span><span class="sxs-lookup"><span data-stu-id="b231c-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="b231c-137">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-137">**Advisory**</span></span>

<span data-ttu-id="b231c-138">不存在任何憑證連接器。</span><span class="sxs-lookup"><span data-stu-id="b231c-138">No certificate connectors are present.</span></span> <span data-ttu-id="b231c-139">您可能不需要任何連接器，但應評估您是否需要在 Microsoft 受管理的電腦裝置上進行部分網路連線。</span><span class="sxs-lookup"><span data-stu-id="b231c-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b231c-140">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="b231c-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="b231c-141">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-141">**Advisory**</span></span>

<span data-ttu-id="b231c-142">至少有一個憑證連接器有錯誤。</span><span class="sxs-lookup"><span data-stu-id="b231c-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="b231c-143">如果您需要此連接器提供憑證給 Microsoft 受管理的桌面裝置，您必須解決此錯誤。</span><span class="sxs-lookup"><span data-stu-id="b231c-143">If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="b231c-144">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="b231c-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="b231c-145">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-145">**Advisory**</span></span>

<span data-ttu-id="b231c-146">您至少有一個憑證連接器，而且不會報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="b231c-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="b231c-147">不過，在準備部署時，您可能需要建立設定檔，以重複使用 Microsoft 受管理桌面裝置的連接器。</span><span class="sxs-lookup"><span data-stu-id="b231c-147">However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b231c-148">如需詳細資訊，請參閱為 [Microsoft Managed Desktop 準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="b231c-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="b231c-149">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="b231c-149">Conditional access policies</span></span>

<span data-ttu-id="b231c-150">條件式存取原則不得防止 Microsoft Managed Desktop 在 Intune 和 Azure AD 中管理 Azure AD 組織 (租使用者) 。</span><span class="sxs-lookup"><span data-stu-id="b231c-150">Conditional access policies must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>

<span data-ttu-id="b231c-151">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-151">**Not ready**</span></span>

<span data-ttu-id="b231c-152">您有至少一個目標為所有使用者的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="b231c-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="b231c-153">在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft Managed Desktop service 帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。</span><span class="sxs-lookup"><span data-stu-id="b231c-153">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="b231c-154">註冊後，您可以在 Microsoft 端點管理員中查看 Microsoft 受管理的電腦條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="b231c-154">After enrollment, you can review the Microsoft Managed Desktop conditional access policy in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="b231c-155">如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="b231c-155">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="b231c-156">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-156">**Advisory**</span></span>

<span data-ttu-id="b231c-157">您有設定條件存取原則，可防止 Microsoft Managed Desktop 管理 Microsoft 受管理的桌面服務。</span><span class="sxs-lookup"><span data-stu-id="b231c-157">You have conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="b231c-158">在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft Managed Desktop service 帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。</span><span class="sxs-lookup"><span data-stu-id="b231c-158">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="b231c-159">如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="b231c-159">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="b231c-160">**錯誤**</span><span class="sxs-lookup"><span data-stu-id="b231c-160">**Error**</span></span>

<span data-ttu-id="b231c-161">Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="b231c-161">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="b231c-162">您也需要指派的任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="b231c-162">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="b231c-163">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="b231c-163">Security Reader</span></span>
- <span data-ttu-id="b231c-164">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="b231c-164">Security Administrator</span></span>
- <span data-ttu-id="b231c-165">條件式存取管理員</span><span class="sxs-lookup"><span data-stu-id="b231c-165">Conditional Access Administrator</span></span>
- <span data-ttu-id="b231c-166">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="b231c-166">Global Reader</span></span>
- <span data-ttu-id="b231c-167">裝置管理員</span><span class="sxs-lookup"><span data-stu-id="b231c-167">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="b231c-168">裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="b231c-168">Device Compliance policies</span></span>

<span data-ttu-id="b231c-169">Azure AD 組織中的 Intune 裝置相容性原則可能會影響 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="b231c-169">Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="b231c-170">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-170">**Not ready**</span></span>

<span data-ttu-id="b231c-171">您至少具有一個針對所有使用者的符合性原則。</span><span class="sxs-lookup"><span data-stu-id="b231c-171">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="b231c-172">Microsoft 受管理的桌面包含的相容性原則將會以 Microsoft 受管理的桌面裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="b231c-172">Microsoft Managed Desktop includes compliance policies that will target your Microsoft Managed Desktop devices.</span></span>  <span data-ttu-id="b231c-173">變更原則，以針對不包含任何 Microsoft 受管理桌面使用者或裝置的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-173">Change the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users or devices.</span></span> <span data-ttu-id="b231c-174">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="b231c-174">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="b231c-175">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-175">**Advisory**</span></span>

<span data-ttu-id="b231c-176">請確定任何您沒有以 Microsoft 管理的桌面使用者為目標的相容性原則。</span><span class="sxs-lookup"><span data-stu-id="b231c-176">Make sure that any compliance policies you have don't target any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="b231c-177">如需步驟，請參閱 [Create a 相容性原則 In Microsoft Intune](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="b231c-177">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-profiles"></a><span data-ttu-id="b231c-178">裝置設定檔</span><span class="sxs-lookup"><span data-stu-id="b231c-178">Device Configuration profiles</span></span>

<span data-ttu-id="b231c-179">Azure AD 組織中的 Intune 裝置設定設定檔，不得針對任何 Microsoft 管理桌面裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="b231c-179">Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="b231c-180">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-180">**Not ready**</span></span>

<span data-ttu-id="b231c-181">您至少要有一個設定設定檔，針對所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="b231c-181">You have at least one configuration profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="b231c-182">將設定檔重設為面向不包含任何 Microsoft 受管理桌面裝置的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-182">Reset the profile to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b231c-183">如需步驟，請參閱 [使用 Microsoft Intune 中的自訂設定建立設定檔](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="b231c-183">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="b231c-184">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-184">**Advisory**</span></span>

<span data-ttu-id="b231c-185">請確定任何您沒有的設定原則都包含任何 Microsoft 受管理的桌面裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="b231c-185">Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="b231c-186">如需步驟，請參閱 [使用 Microsoft Intune 中的自訂設定建立設定檔](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="b231c-186">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="b231c-187">裝置類型限制</span><span class="sxs-lookup"><span data-stu-id="b231c-187">Device type restrictions</span></span>

<span data-ttu-id="b231c-188">Microsoft 受管理的桌面裝置必須能夠在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="b231c-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="b231c-189">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-189">**Not ready**</span></span>

<span data-ttu-id="b231c-190">您目前至少已設定一個登錄限制原則，以防止 Windows 裝置在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="b231c-190">You currently have at least one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune.</span></span> <span data-ttu-id="b231c-191">請依照針對 Microsoft 受管理的桌面使用者設定的每個註冊限制原則， [設定註冊限制](/mem/intune/enrollment/enrollment-restrictions-set) 中的步驟，並將 **Windows (MDM)** 設定變更為 [ **允許**]。</span><span class="sxs-lookup"><span data-stu-id="b231c-191">Follow the steps in [Set enrollment restrictions](/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**.</span></span> <span data-ttu-id="b231c-192">不過，您可以將任何 **個人擁有** 的 **Windows (MDM)** 裝置設定為 **封鎖**。</span><span class="sxs-lookup"><span data-stu-id="b231c-192">You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**.</span></span> 


### <a name="enrollment-status-page"></a><span data-ttu-id="b231c-193">註冊狀態頁面</span><span class="sxs-lookup"><span data-stu-id="b231c-193">Enrollment Status Page</span></span>

<span data-ttu-id="b231c-194">您目前已啟用「註冊狀態」頁面 (ESP) 。</span><span class="sxs-lookup"><span data-stu-id="b231c-194">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="b231c-195">如果您想要參與 Microsoft 受管理的桌面公開預覽這項功能，您可以忽略此專案。</span><span class="sxs-lookup"><span data-stu-id="b231c-195">If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="b231c-196">如需詳細資訊，請參閱 [使用 Autopilot 和註冊狀態頁面的初次執行體驗](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="b231c-196">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="b231c-197">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-197">**Not ready**</span></span>

<span data-ttu-id="b231c-198">您已設定 ESP 預設設定檔來 **顯示應用程式和設定檔設定進度**。</span><span class="sxs-lookup"><span data-stu-id="b231c-198">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="b231c-199">停用此設定，或遵循 [設定 [註冊狀態] 頁面](/mem/intune/enrollment/windows-enrollment-status)中的步驟，確定任何 Azure AD 群組的指派均未包含 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="b231c-199">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="b231c-200">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-200">**Advisory**</span></span>

<span data-ttu-id="b231c-201">請確定任何具有「 **顯示應用程式和設定檔設定進度** 」設定的設定檔都未指派給任何包含 Microsoft 受管理的桌面裝置的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-201">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b231c-202">如需詳細資訊，請參閱 [設定註冊狀態頁面](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="b231c-202">For more information, see [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="microsoft-store-for-business"></a><span data-ttu-id="b231c-203">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b231c-203">Microsoft Store for Business</span></span>

<span data-ttu-id="b231c-204">我們使用 Microsoft Store for Business 並在 Microsoft Managed Desktop 上部署公司入口網站應用程式，讓使用者可以選擇性地安裝某些應用程式，例如 Microsoft Project 和 Microsoft Visio (（如有允許的) ）。</span><span class="sxs-lookup"><span data-stu-id="b231c-204">We use Microsoft Store for Business and deploy the Company Portal app on Microsoft Managed Desktop to allow users to optionally install some apps, such as Microsoft Project and Microsoft Visio (where permitted).</span></span>

<span data-ttu-id="b231c-205">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-205">**Not ready**</span></span>

<span data-ttu-id="b231c-206">商務用 Microsoft Store 未啟用或未與 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="b231c-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="b231c-207">如需詳細資訊，請參閱 how [to 使用 Microsoft Intune 管理大量購買的應用程式](/mem/intune/apps/windows-store-for-business) ，以及在 [裝置上安裝 Intune 公司入口網站](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="b231c-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="b231c-208">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="b231c-208">Multifactor authentication</span></span>

<span data-ttu-id="b231c-209">多重要素驗證不得防止 Microsoft Managed Desktop 在 Intune 和 Azure AD 中管理 Azure AD 組織 (租使用者) 。</span><span class="sxs-lookup"><span data-stu-id="b231c-209">Multifactor authentication must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>


<span data-ttu-id="b231c-210">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-210">**Not ready**</span></span>

<span data-ttu-id="b231c-211">針對指派給所有 **使用者的條件** 式存取原則，您可以設定某些多重要素驗證原則。</span><span class="sxs-lookup"><span data-stu-id="b231c-211">You have some multifactor authentication policies set as **required** for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="b231c-212">在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft Managed Desktop service 帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。</span><span class="sxs-lookup"><span data-stu-id="b231c-212">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="b231c-213">如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="b231c-213">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="b231c-214">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-214">**Advisory**</span></span>

<span data-ttu-id="b231c-215">您在條件式存取原則上必須進行多重驗證，使 Microsoft Managed Desktop 無法管理 Microsoft 受管理的桌面服務。</span><span class="sxs-lookup"><span data-stu-id="b231c-215">You have multifactor authentication required on conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="b231c-216">在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft Managed Desktop service 帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。</span><span class="sxs-lookup"><span data-stu-id="b231c-216">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="b231c-217">如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="b231c-217">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="b231c-218">**錯誤**</span><span class="sxs-lookup"><span data-stu-id="b231c-218">**Error**</span></span>

<span data-ttu-id="b231c-219">Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="b231c-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="b231c-220">您也需要指派的任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="b231c-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="b231c-221">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="b231c-221">Security Reader</span></span>
- <span data-ttu-id="b231c-222">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="b231c-222">Security Administrator</span></span>
- <span data-ttu-id="b231c-223">條件式存取管理員</span><span class="sxs-lookup"><span data-stu-id="b231c-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="b231c-224">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="b231c-224">Global Reader</span></span>
- <span data-ttu-id="b231c-225">裝置管理員</span><span class="sxs-lookup"><span data-stu-id="b231c-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="b231c-226">PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="b231c-226">PowerShell scripts</span></span>

<span data-ttu-id="b231c-227">Windows PowerShell 腳本無法指派為以 Microsoft 受管理的桌面裝置為目標的方式。</span><span class="sxs-lookup"><span data-stu-id="b231c-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="b231c-228">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-228">**Advisory**</span></span>

<span data-ttu-id="b231c-229">確定您的 Azure AD 組織中的 Windows PowerShell 腳本並未以任何 Microsoft 管理桌面裝置或使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="b231c-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="b231c-230">請勿指派 PowerShell 腳本來設定所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="b231c-230">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="b231c-231">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="b231c-231">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="b231c-232">如需詳細資訊，請參閱在 [Intune 中使用 Windows 10 裝置上的 PowerShell 腳本](/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="b231c-232">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="b231c-233">地區</span><span class="sxs-lookup"><span data-stu-id="b231c-233">Region</span></span>

<span data-ttu-id="b231c-234">您的區域必須支援 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="b231c-234">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="b231c-235">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-235">**Not ready**</span></span>

<span data-ttu-id="b231c-236">Microsoft 受管理的電腦目前不支援您的 Azure AD 組織區域。</span><span class="sxs-lookup"><span data-stu-id="b231c-236">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="b231c-237">如需詳細資訊，請參閱 [Microsoft 受管理的桌面支援的地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="b231c-237">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="b231c-238">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-238">**Advisory**</span></span>

<span data-ttu-id="b231c-239">Microsoft 受管理的電腦不支援 Azure AD 組織所在的一或多個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="b231c-239">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="b231c-240">如需詳細資訊，請參閱 [Microsoft 受管理的桌面支援的地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="b231c-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="b231c-241">安全性基準</span><span class="sxs-lookup"><span data-stu-id="b231c-241">Security baselines</span></span>

<span data-ttu-id="b231c-242">安全性基準原則不應該以任何 Microsoft 受管理的桌面裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="b231c-242">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="b231c-243">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-243">**Not ready**</span></span>

<span data-ttu-id="b231c-244">您有一個針對所有使用者、所有裝置或兩者的安全性基準設定檔。</span><span class="sxs-lookup"><span data-stu-id="b231c-244">You have a security baseline profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="b231c-245">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="b231c-245">Change the policy to use an assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b231c-246">如需步驟，請參閱 [使用安全性基準在 Intune 中設定 Windows 10 裝置](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="b231c-246">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="b231c-247">在註冊期間，我們會將新的安全性基準套用至所有 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="b231c-247">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b231c-248">註冊後，您可以在 Microsoft 端點管理員的 [設定 **原則** ] 區域中複查 Microsoft Managed Desktop security 基準原則。</span><span class="sxs-lookup"><span data-stu-id="b231c-248">After enrollment, you can review the Microsoft Managed Desktop security baseline policy in the **Configuration policy** area of Microsoft Endpoint Manager.</span></span>

<span data-ttu-id="b231c-249">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-249">**Advisory**</span></span>

<span data-ttu-id="b231c-250">請確定所有的安全性基準原則都排除 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="b231c-250">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b231c-251">如需步驟，請參閱 [使用安全性基準在 Intune 中設定 Windows 10 裝置](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="b231c-251">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="b231c-252">在註冊期間，我們會將新的安全性基準套用至所有 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="b231c-252">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b231c-253">**新式的工作場所裝置-所有** Azure AD 群組是我們在您註冊 Microsoft Managed Desktop 時所建立的動態群組，所以您必須在註冊後傳回排除此群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-253">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span> 


### <a name="windows-apps"></a><span data-ttu-id="b231c-254">Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="b231c-254">Windows apps</span></span>

<span data-ttu-id="b231c-255">查看您要讓 Microsoft 受管理的桌面使用者擁有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b231c-255">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="b231c-256">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-256">**Advisory**</span></span>

<span data-ttu-id="b231c-257">您應該準備要讓 Microsoft 受管理的桌面使用者擁有的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="b231c-257">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="b231c-258">由於這些應用程式必須透過 Intune 部署，因此請評估重複使用現有的 Intune 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b231c-258">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="b231c-259">考慮使用公司入口 (請參閱在裝置和註冊狀態頁面 [上安裝 Intune 公司入口網站](../get-started/company-portal.md) (ESP) ，將應用程式發佈至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="b231c-259">Consider using Company Portal (see [Install Intune Company Portal on devices](../get-started/company-portal.md) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="b231c-260">如需詳細資訊，請參閱 [Microsoft 受管理的桌面](apps.md) 和初次執行體驗中的應用程式 [與 Autopilot 和註冊狀態頁面](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="b231c-260">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="b231c-261">您可以要求 Microsoft 帳戶代表在 Microsoft 端點 Configuration Manager 中查詢，以識別準備好要遷移至 Intune 或需要調整的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b231c-261">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="b231c-262">Windows Hello 企業版</span><span class="sxs-lookup"><span data-stu-id="b231c-262">Windows Hello for Business</span></span>

<span data-ttu-id="b231c-263">Microsoft 受管理的桌面需要啟用 Windows Hello 企業版功能。</span><span class="sxs-lookup"><span data-stu-id="b231c-263">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="b231c-264">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-264">**Not ready**</span></span>

<span data-ttu-id="b231c-265">Windows Hello 企業版已停用。</span><span class="sxs-lookup"><span data-stu-id="b231c-265">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="b231c-266">遵循[建立 Windows Hello 企業版原則](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用</span><span class="sxs-lookup"><span data-stu-id="b231c-266">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="b231c-267">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-267">**Advisory**</span></span>

<span data-ttu-id="b231c-268">未設定 Windows Hello 企業版。</span><span class="sxs-lookup"><span data-stu-id="b231c-268">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="b231c-269">遵循 [建立 Windows Hello 企業版原則](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用它。</span><span class="sxs-lookup"><span data-stu-id="b231c-269">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="b231c-270">Windows 10 更新環</span><span class="sxs-lookup"><span data-stu-id="b231c-270">Windows 10 update rings</span></span>

<span data-ttu-id="b231c-271">Intune 中的「Windows 10 更新環路」原則不得以 Microsoft 受管理的桌面裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="b231c-271">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="b231c-272">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-272">**Not ready**</span></span>

<span data-ttu-id="b231c-273">您有一個「更新鈴聲」原則，針對所有裝置、所有使用者或兩者。</span><span class="sxs-lookup"><span data-stu-id="b231c-273">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="b231c-274">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，但不包括任何 Microsoft 受管理的桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="b231c-274">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b231c-275">如需步驟，請參閱 [在 Intune 中管理 Windows 10 軟體更新](/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="b231c-275">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="b231c-276">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-276">**Advisory**</span></span>

<span data-ttu-id="b231c-277">請確定任何更新環原則您已排除現代的 **工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-277">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="b231c-278">如果您已將 Azure AD 使用者群組指派給這些原則，請確定任何更新環原則您已排除現代的 **工作場所-** 您將 Microsoft 管理的桌面使用者新增至 (或同等群組) 的所有 azure ad 群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-278">If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group).</span></span> <span data-ttu-id="b231c-279">如需步驟，請參閱 [在 Intune 中管理 Windows 10 軟體更新](/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="b231c-279">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="b231c-280">兩個 **新式的工作場所裝置-所有** 及 **現代的工作場所-所有** Azure AD 群組都是您在 Microsoft 受管理的電腦中註冊時所建立的群組，所以在註冊後，您必須取回此群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-280">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="b231c-281">Azure Active Directory 設定</span><span class="sxs-lookup"><span data-stu-id="b231c-281">Azure Active Directory settings</span></span>

<span data-ttu-id="b231c-282">您可以在 [azure 入口網站](https://portal.azure.com)中存取 Azure Active Directory 設定。</span><span class="sxs-lookup"><span data-stu-id="b231c-282">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="b231c-283">Intune 登記</span><span class="sxs-lookup"><span data-stu-id="b231c-283">Intune enrollment</span></span>

<span data-ttu-id="b231c-284">Azure AD 組織中的 Windows 10 裝置必須能夠在 Intune 中自動註冊。</span><span class="sxs-lookup"><span data-stu-id="b231c-284">Windows 10 devices in your Azure AD organization must be able to automatically enroll in Intune.</span></span>

<span data-ttu-id="b231c-285">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-285">**Advisory**</span></span>

<span data-ttu-id="b231c-286">確定 **MDM 使用者範圍** 已設定為 **部分** 或 **全部**（非 **無**）。</span><span class="sxs-lookup"><span data-stu-id="b231c-286">Make sure the **MDM User scope** is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="b231c-287">如果您選擇 [ **部分**]，請在註冊後再進行註冊，然後選取 [ **新式的工作場所]-** **群組** 的所有 Azure AD 群組，或設定為所有 Microsoft 受管理的桌面使用者的同等群組。</span><span class="sxs-lookup"><span data-stu-id="b231c-287">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users.</span></span>  <span data-ttu-id="b231c-288">請參閱 [使用 Microsoft Intune 設定 Windows 裝置的註冊](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="b231c-288">See [Set up enrollment for Windows devices by using Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="b231c-289">專用訂閱</span><span class="sxs-lookup"><span data-stu-id="b231c-289">Ad hoc subscriptions</span></span>

<span data-ttu-id="b231c-290">建議您如何檢查設定為 "false" 的設定 () 可能會讓企業狀態漫遊無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="b231c-290">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="b231c-291">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-291">**Advisory**</span></span>

<span data-ttu-id="b231c-292">確定 **AllowAdHocSubscriptions** 設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="b231c-292">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="b231c-293">否則，企業狀態漫遊可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="b231c-293">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="b231c-294">如需詳細資訊，請參閱 [MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="b231c-294">For more information, see [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="b231c-295">企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="b231c-295">Enterprise State Roaming</span></span>

<span data-ttu-id="b231c-296">應啟用企業狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="b231c-296">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="b231c-297">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-297">**Advisory**</span></span>

<span data-ttu-id="b231c-298">請確定已針對 **所有** 或 **選取** 的群組啟用企業狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="b231c-298">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="b231c-299">如需詳細資訊，請參閱 [在 Azure Active Directory 中啟用企業狀態漫遊](/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="b231c-299">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="b231c-300">授權</span><span class="sxs-lookup"><span data-stu-id="b231c-300">Licenses</span></span>

<span data-ttu-id="b231c-301">使用 Microsoft 受管理的桌面需要一些授權。</span><span class="sxs-lookup"><span data-stu-id="b231c-301">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="b231c-302">**尚未準備好**</span><span class="sxs-lookup"><span data-stu-id="b231c-302">**Not Ready**</span></span>

<span data-ttu-id="b231c-303">您沒有使用 Microsoft 管理的桌面所需的所有授權。</span><span class="sxs-lookup"><span data-stu-id="b231c-303">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="b231c-304">如需詳細資訊，請參閱 [Microsoft 管理的桌面技術](../intro/technologies.md) 和 [有關授權的詳細](prerequisites.md#more-about-licenses)資訊。</span><span class="sxs-lookup"><span data-stu-id="b231c-304">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="microsoft-managed-desktop-service-accounts"></a><span data-ttu-id="b231c-305">Microsoft 受管理的桌面服務帳戶</span><span class="sxs-lookup"><span data-stu-id="b231c-305">Microsoft Managed Desktop service accounts</span></span>

<span data-ttu-id="b231c-306">某些帳戶名稱會與 Microsoft Managed Desktop 所建立的帳戶名稱衝突，以管理 Microsoft 受管理的桌面服務。</span><span class="sxs-lookup"><span data-stu-id="b231c-306">Certain account names could conflict with account names created by Microsoft Managed Desktop to manage the Microsoft Managed Desktop service.</span></span>

<span data-ttu-id="b231c-307">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-307">**Not ready**</span></span>

<span data-ttu-id="b231c-308">您至少有一個帳戶名稱會與 Microsoft Managed Desktop 所建立的帳戶名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="b231c-308">You have at least one account name that will conflict with account names created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="b231c-309">請與您的 Microsoft 帳戶代表合作，以排除這些帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="b231c-309">Work with your Microsoft account representative to exclude these account names.</span></span> <span data-ttu-id="b231c-310">我們不會向公眾列出帳戶名稱，以儘量降低安全性風險。</span><span class="sxs-lookup"><span data-stu-id="b231c-310">We don't list the account names publicly to minimize security risk.</span></span> 


### <a name="security-administrator-roles"></a><span data-ttu-id="b231c-311">安全性管理員角色</span><span class="sxs-lookup"><span data-stu-id="b231c-311">Security administrator roles</span></span>

<span data-ttu-id="b231c-312">具有特定安全性角色的使用者必須在 Microsoft Defender for Endpoint 中指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="b231c-312">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="b231c-313">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-313">**Advisory**</span></span>

<span data-ttu-id="b231c-314">如果您已將使用者指派至 Azure AD 組織中的任何角色，請確定他們也在 Microsoft Defender for Endpoint 中指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="b231c-314">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b231c-315">否則，具有這些角色的系統管理員將無法存取管理員入口網站。</span><span class="sxs-lookup"><span data-stu-id="b231c-315">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="b231c-316">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="b231c-316">Security Operator</span></span>
- <span data-ttu-id="b231c-317">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="b231c-317">Global Reader</span></span>

<span data-ttu-id="b231c-318">如需詳細資訊，請參閱 [建立及管理以角色為基礎的存取控制角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="b231c-318">For more information, see [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="b231c-319">安全性預設值</span><span class="sxs-lookup"><span data-stu-id="b231c-319">Security default</span></span>

<span data-ttu-id="b231c-320">在 Azure Active Directory 中的安全性預設值會使 Microsoft Managed Desktop 無法管理您的裝置。</span><span class="sxs-lookup"><span data-stu-id="b231c-320">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="b231c-321">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="b231c-321">**Not ready**</span></span>

<span data-ttu-id="b231c-322">您已開啟安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="b231c-322">You have Security defaults turned on.</span></span> <span data-ttu-id="b231c-323">關閉安全性預設值，並設定條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="b231c-323">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="b231c-324">如需詳細資訊，請參閱 [一般條件式存取原則](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="b231c-324">For more information, see [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="b231c-325">自助密碼重設</span><span class="sxs-lookup"><span data-stu-id="b231c-325">Self-service Password Reset</span></span>

<span data-ttu-id="b231c-326">自助密碼重設 (SSPR) 可以針對所有不含 Microsoft Managed Desktop 服務帳戶的 Microsoft 受管理的桌面使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="b231c-326">Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="b231c-327">如需詳細資訊，請參閱 [教學課程：讓使用者可以使用 Azure Active Directory 自助密碼重設來解除鎖定帳戶或重設密碼](/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="b231c-327">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="b231c-328">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-328">**Advisory**</span></span>

<span data-ttu-id="b231c-329">請確定 [SSPR **選取** ] 設定包括 Microsoft 受管理的桌面使用者，但不包括 Microsoft 受管理的桌面服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="b231c-329">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="b231c-330">SSPR 啟用時，Microsoft Managed Desktop service 帳戶無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="b231c-330">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="b231c-331">標準使用者角色</span><span class="sxs-lookup"><span data-stu-id="b231c-331">Standard user role</span></span>

<span data-ttu-id="b231c-332">除了為全域系統管理員和裝置管理員指派 Azure AD 角色的使用者以外，Microsoft 受管理的桌面使用者將是不具備本機系統管理員許可權的標準使用者。</span><span class="sxs-lookup"><span data-stu-id="b231c-332">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="b231c-333">當其他使用者啟動其 Microsoft 受管理的桌面裝置時，系統會將其指派為標準使用者角色。</span><span class="sxs-lookup"><span data-stu-id="b231c-333">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="b231c-334">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-334">**Advisory**</span></span>

<span data-ttu-id="b231c-335">Microsoft 受管理的桌面使用者在註冊後，不會對其 Microsoft 受管理的桌面裝置具有本機系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="b231c-335">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b231c-336">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="b231c-336">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="b231c-337">OneDrive</span><span class="sxs-lookup"><span data-stu-id="b231c-337">OneDrive</span></span>

<span data-ttu-id="b231c-338">[ **僅允許在加入特定網域的電腦上進行同步** 處理] 設定會與 Microsoft 受管理的桌面產生衝突。</span><span class="sxs-lookup"><span data-stu-id="b231c-338">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="b231c-339">您可以在 OneDrive 系統 [管理中心](https://admin.onedrive.com)存取 OneDrive 設定。</span><span class="sxs-lookup"><span data-stu-id="b231c-339">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="b231c-340">**公告**</span><span class="sxs-lookup"><span data-stu-id="b231c-340">**Advisory**</span></span>

<span data-ttu-id="b231c-341">您正在使用 [ **僅允許在加入特定網域的電腦上同步** 處理] 設定。</span><span class="sxs-lookup"><span data-stu-id="b231c-341">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="b231c-342">此設定不會與 Microsoft 受管理的桌面搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b231c-342">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="b231c-343">停用此設定，而不是設定 OneDrive 使用條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="b231c-343">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="b231c-344">請參閱 [規劃設定條件式存取部署](/azure/active-directory/conditional-access/plan-conditional-access) 以取得協助。</span><span class="sxs-lookup"><span data-stu-id="b231c-344">See [Plan a Conditional Access deployment](/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>