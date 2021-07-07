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
audience: Admin
ms.openlocfilehash: 866d1a2de820fca4c66537583dc5f55098149931
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327008"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="de4e5-104">修正由整備評估工具發現的問題</span><span class="sxs-lookup"><span data-stu-id="de4e5-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="de4e5-105">針對每個檢查，該工具會報告下列四個可能的結果之一：</span><span class="sxs-lookup"><span data-stu-id="de4e5-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="de4e5-106">結果</span><span class="sxs-lookup"><span data-stu-id="de4e5-106">Result</span></span>  |<span data-ttu-id="de4e5-107">意義</span><span class="sxs-lookup"><span data-stu-id="de4e5-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="de4e5-108">就緒</span><span class="sxs-lookup"><span data-stu-id="de4e5-108">Ready</span></span>     | <span data-ttu-id="de4e5-109">完成註冊之前，不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="de4e5-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="de4e5-110">公告</span><span class="sxs-lookup"><span data-stu-id="de4e5-110">Advisory</span></span>    | <span data-ttu-id="de4e5-111">請遵循工具或本文中的步驟，以取得註冊和使用者的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="de4e5-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="de4e5-112">您 *可以* 完成註冊，但是必須先修正這些問題，再部署第一個裝置。</span><span class="sxs-lookup"><span data-stu-id="de4e5-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="de4e5-113">未就緒</span><span class="sxs-lookup"><span data-stu-id="de4e5-113">Not ready</span></span> | <span data-ttu-id="de4e5-114">*如果您未修正這些問題，註冊將會失敗。*</span><span class="sxs-lookup"><span data-stu-id="de4e5-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="de4e5-115">請遵循工具或本文中的步驟加以解決。</span><span class="sxs-lookup"><span data-stu-id="de4e5-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="de4e5-116">錯誤</span><span class="sxs-lookup"><span data-stu-id="de4e5-116">Error</span></span> | <span data-ttu-id="de4e5-117">您所使用的 Azure Active Directory (AD) 角色的許可權不足，無法執行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="de4e5-117">The Azure Active Directory (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="de4e5-118">此工具報告的結果會反映您的設定狀態，只會在您執行它的特定時間點反映。</span><span class="sxs-lookup"><span data-stu-id="de4e5-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="de4e5-119">如果您稍後對 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的原則進行任何變更，「就緒」的專案可能會變成「尚未準備好」。</span><span class="sxs-lookup"><span data-stu-id="de4e5-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="de4e5-120">若要避免 Microsoft 受管理的電腦作業的問題，請在變更任何原則之前，先檢查本文所述的特定設定。</span><span class="sxs-lookup"><span data-stu-id="de4e5-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="de4e5-121">Microsoft Intune 設定</span><span class="sxs-lookup"><span data-stu-id="de4e5-121">Microsoft Intune settings</span></span>

<span data-ttu-id="de4e5-122">您可以在 Microsoft 端點管理員系統[管理中心](https://endpoint.microsoft.com)存取 Intune 設定。</span><span class="sxs-lookup"><span data-stu-id="de4e5-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="de4e5-123">Autopilot 部署設定檔</span><span class="sxs-lookup"><span data-stu-id="de4e5-123">Autopilot deployment profile</span></span>

<span data-ttu-id="de4e5-124">您不應該有任何現有的 Autopilot 設定檔，可將指派或動態群組設定為 Microsoft 受管理的電腦裝置。</span><span class="sxs-lookup"><span data-stu-id="de4e5-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="de4e5-125">Microsoft 受管理的電腦會使用 Autopilot 布建新裝置。</span><span class="sxs-lookup"><span data-stu-id="de4e5-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="de4e5-126">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-126">**Not ready**</span></span>

<span data-ttu-id="de4e5-127">您有指派給所有裝置的 Autopilot 設定檔。</span><span class="sxs-lookup"><span data-stu-id="de4e5-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="de4e5-128">如需步驟，請參閱[使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="de4e5-129">Microsoft 受管理的電腦註冊後，請將您的 Autopilot 原則設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="de4e5-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="de4e5-130">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-130">**Advisory**</span></span>

<span data-ttu-id="de4e5-131">請確定您的 Autopilot 設定檔目標是指派或動態 Azure AD 群組，但不包括 Microsoft 受管理的電腦裝置。</span><span class="sxs-lookup"><span data-stu-id="de4e5-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="de4e5-132">如需步驟，請參閱[使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="de4e5-133">Microsoft 受管理的電腦註冊後，請將您的 Autopilot 設定檔設定為排除 **現代的工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="de4e5-133">After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="de4e5-134">憑證連接器</span><span class="sxs-lookup"><span data-stu-id="de4e5-134">Certificate connectors</span></span>

<span data-ttu-id="de4e5-135">如果您有任何您想要在 Microsoft 受管理的電腦中註冊之裝置使用的憑證連接器，連接器不應該有任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="de4e5-135">If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors should not have any errors.</span></span> <span data-ttu-id="de4e5-136">下列其中一項諮詢只適用于您的情況，所以請務必仔細檢查。</span><span class="sxs-lookup"><span data-stu-id="de4e5-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="de4e5-137">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-137">**Advisory**</span></span>

<span data-ttu-id="de4e5-138">不存在任何憑證連接器。</span><span class="sxs-lookup"><span data-stu-id="de4e5-138">No certificate connectors are present.</span></span> <span data-ttu-id="de4e5-139">您可能不需要任何連接器，但您應評估您的 Microsoft 受管理的電腦裝置上是否需要一些網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="de4e5-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="de4e5-140">如需詳細資訊，請參閱[為 Microsoft 受管理的電腦準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="de4e5-141">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-141">**Advisory**</span></span>

<span data-ttu-id="de4e5-142">至少有一個憑證連接器有錯誤。</span><span class="sxs-lookup"><span data-stu-id="de4e5-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="de4e5-143">如果您需要此連接器為 Microsoft 受管理的電腦裝置提供憑證，則必須解決此錯誤。</span><span class="sxs-lookup"><span data-stu-id="de4e5-143">If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="de4e5-144">如需詳細資訊，請參閱[為 Microsoft 受管理的電腦準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="de4e5-145">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-145">**Advisory**</span></span>

<span data-ttu-id="de4e5-146">您至少有一個憑證連接器，而且不會報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="de4e5-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="de4e5-147">不過，在準備部署時，您可能需要建立設定檔，以重複使用 Microsoft 受管理的電腦裝置的連接器。</span><span class="sxs-lookup"><span data-stu-id="de4e5-147">However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="de4e5-148">如需詳細資訊，請參閱[為 Microsoft 受管理的電腦準備憑證和網路設定檔](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

### <a name="company-portal"></a><span data-ttu-id="de4e5-149">公司入口網站</span><span class="sxs-lookup"><span data-stu-id="de4e5-149">Company Portal</span></span>

<span data-ttu-id="de4e5-150">Microsoft 受管理的電腦需要 IT 管理員為其具有 Microsoft 受管理的電腦裝置的使用者安裝 Intune 公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="de4e5-150">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="de4e5-151">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-151">**Not ready**</span></span>

<span data-ttu-id="de4e5-152">您沒有為使用者安裝公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="de4e5-152">You do not have Company Portal installed for your users.</span></span> <span data-ttu-id="de4e5-153">購買公司入口網站，並強制在 Intune 與商務用 Microsoft Store 之間進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="de4e5-153">Purchase Company Portal and force a sync between Intune and Microsoft Store for Business.</span></span> <span data-ttu-id="de4e5-154">如需詳細資訊，請參閱[在裝置上安裝 Intune 公司入口網站](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-154">For more information, see [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="de4e5-155">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="de4e5-155">Conditional access policies</span></span>

<span data-ttu-id="de4e5-156">條件式存取原則不得阻止 Microsoft 受管理的電腦在 Intune 和 Azure ad 中管理 Azure ad 組織 (承租人) 。</span><span class="sxs-lookup"><span data-stu-id="de4e5-156">Conditional access policies must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>

<span data-ttu-id="de4e5-157">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-157">**Not ready**</span></span>

<span data-ttu-id="de4e5-158">您有至少一個目標為所有使用者的條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="de4e5-158">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="de4e5-159">在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft 受管理的電腦服務帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。</span><span class="sxs-lookup"><span data-stu-id="de4e5-159">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="de4e5-160">註冊後，您可以在 Microsoft 端點管理員中查看 Microsoft 受管理的電腦條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="de4e5-160">After enrollment, you can review the Microsoft Managed Desktop conditional access policy in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="de4e5-161">如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-161">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="de4e5-162">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-162">**Advisory**</span></span>

<span data-ttu-id="de4e5-163">您有條件式存取原則可以避免 Microsoft 受管理的電腦管理 Microsoft 受管理的電腦服務。</span><span class="sxs-lookup"><span data-stu-id="de4e5-163">You have conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="de4e5-164">在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft 受管理的電腦服務帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。</span><span class="sxs-lookup"><span data-stu-id="de4e5-164">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="de4e5-165">如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-165">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="de4e5-166">**Error**</span><span class="sxs-lookup"><span data-stu-id="de4e5-166">**Error**</span></span>

<span data-ttu-id="de4e5-167">Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="de4e5-167">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="de4e5-168">您也需要指派的任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="de4e5-168">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="de4e5-169">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="de4e5-169">Security Reader</span></span>
- <span data-ttu-id="de4e5-170">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="de4e5-170">Security Administrator</span></span>
- <span data-ttu-id="de4e5-171">條件式存取管理員</span><span class="sxs-lookup"><span data-stu-id="de4e5-171">Conditional Access Administrator</span></span>
- <span data-ttu-id="de4e5-172">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="de4e5-172">Global Reader</span></span>
- <span data-ttu-id="de4e5-173">裝置管理員</span><span class="sxs-lookup"><span data-stu-id="de4e5-173">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="de4e5-174">裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="de4e5-174">Device Compliance policies</span></span>

<span data-ttu-id="de4e5-175">Azure AD 組織中的 Intune 裝置相容性原則可能會影響 Microsoft 受管理的電腦裝置。</span><span class="sxs-lookup"><span data-stu-id="de4e5-175">Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="de4e5-176">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-176">**Not ready**</span></span>

<span data-ttu-id="de4e5-177">您至少具有一個針對所有使用者的符合性原則。</span><span class="sxs-lookup"><span data-stu-id="de4e5-177">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="de4e5-178">Microsoft 受管理的電腦包含將會以 Microsoft 受管理的電腦裝置為目標的相容性原則。</span><span class="sxs-lookup"><span data-stu-id="de4e5-178">Microsoft Managed Desktop includes compliance policies that will target your Microsoft Managed Desktop devices.</span></span>  <span data-ttu-id="de4e5-179">變更原則，以針對不包含任何 Microsoft 受管理的電腦使用者或裝置的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="de4e5-179">Change the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users or devices.</span></span> <span data-ttu-id="de4e5-180">如需步驟，請參閱[Create a 合規性原則 in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-180">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="de4e5-181">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-181">**Advisory**</span></span>

<span data-ttu-id="de4e5-182">請確定您沒有以任何 Microsoft 受管理的電腦使用者為目標的任何規範原則。</span><span class="sxs-lookup"><span data-stu-id="de4e5-182">Make sure that any compliance policies you have don't target any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="de4e5-183">如需步驟，請參閱[Create a 合規性原則 in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-183">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-profiles"></a><span data-ttu-id="de4e5-184">裝置設定檔</span><span class="sxs-lookup"><span data-stu-id="de4e5-184">Device Configuration profiles</span></span>

<span data-ttu-id="de4e5-185">Azure AD 組織中的 Intune 裝置設定設定檔，不得針對任何 Microsoft 管理桌面裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="de4e5-185">Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="de4e5-186">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-186">**Not ready**</span></span>

<span data-ttu-id="de4e5-187">您至少要有一個設定設定檔，針對所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="de4e5-187">You have at least one configuration profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="de4e5-188">將設定檔重設為面向不包含任何 Microsoft 受管理的電腦裝置的特定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="de4e5-188">Reset the profile to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="de4e5-189">如需步驟，請參閱[使用中的自訂設定建立設定檔 Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-189">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="de4e5-190">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-190">**Advisory**</span></span>

<span data-ttu-id="de4e5-191">請確定任何您沒有的設定原則都包含任何 Microsoft 受管理的電腦裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="de4e5-191">Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="de4e5-192">如需步驟，請參閱[使用中的自訂設定建立設定檔 Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-192">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="de4e5-193">裝置類型限制</span><span class="sxs-lookup"><span data-stu-id="de4e5-193">Device type restrictions</span></span>

<span data-ttu-id="de4e5-194">Microsoft 受管理的電腦裝置必須允許在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="de4e5-194">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="de4e5-195">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-195">**Not ready**</span></span>

<span data-ttu-id="de4e5-196">您目前至少已設定一個登錄限制原則，以避免 Windows 裝置在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="de4e5-196">You currently have at least one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune.</span></span> <span data-ttu-id="de4e5-197">請遵循針對針對 Microsoft 受管理的電腦使用者之每個註冊限制原則 [設定註冊限制](/mem/intune/enrollment/enrollment-restrictions-set)的步驟，並將 **Windows (MDM)** 設定為 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="de4e5-197">Follow the steps in [Set enrollment restrictions](/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**.</span></span> <span data-ttu-id="de4e5-198">不過，您可以將任何 **屬於個人** 的 **Windows (MDM)** 裝置設定為 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="de4e5-198">You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**.</span></span> 


### <a name="enrollment-status-page"></a><span data-ttu-id="de4e5-199">註冊狀態頁面</span><span class="sxs-lookup"><span data-stu-id="de4e5-199">Enrollment Status Page</span></span>

<span data-ttu-id="de4e5-200">您目前已啟用「註冊狀態」頁面 (ESP) 。</span><span class="sxs-lookup"><span data-stu-id="de4e5-200">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="de4e5-201">如果您想要參與此功能的 Microsoft 受管理的電腦公開預覽，可以略過此專案。</span><span class="sxs-lookup"><span data-stu-id="de4e5-201">If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="de4e5-202">如需詳細資訊，請參閱 [使用 Autopilot 和註冊狀態頁面的初次執行體驗](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-202">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="de4e5-203">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-203">**Not ready**</span></span>

<span data-ttu-id="de4e5-204">您已設定 ESP 預設設定檔來 **顯示應用程式和設定檔設定進度**。</span><span class="sxs-lookup"><span data-stu-id="de4e5-204">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="de4e5-205">停用此設定，或遵循[設定 [註冊狀態] 頁面](/mem/intune/enrollment/windows-enrollment-status)中的步驟，確定任何 Azure AD 群組的指派都不包括 Microsoft 受管理的電腦裝置。</span><span class="sxs-lookup"><span data-stu-id="de4e5-205">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="de4e5-206">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-206">**Advisory**</span></span>

<span data-ttu-id="de4e5-207">請確定任何具有「**顯示應用程式和設定檔設定進度**」設定的設定檔都未指派給包含 Microsoft 受管理的電腦裝置的任何 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="de4e5-207">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="de4e5-208">如需詳細資訊，請參閱 [設定註冊狀態頁面](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-208">For more information, see [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="microsoft-store-for-business"></a><span data-ttu-id="de4e5-209">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="de4e5-209">Microsoft Store for Business</span></span>

<span data-ttu-id="de4e5-210">我們使用商務用 Microsoft Store 和部署 Microsoft 受管理的電腦上的公司入口網站應用程式，讓使用者可以選擇性地安裝某些應用程式，例如 Microsoft Project 和 Microsoft Visio (允許) 的位置。</span><span class="sxs-lookup"><span data-stu-id="de4e5-210">We use Microsoft Store for Business and deploy the Company Portal app on Microsoft Managed Desktop to allow users to optionally install some apps, such as Microsoft Project and Microsoft Visio (where permitted).</span></span>

<span data-ttu-id="de4e5-211">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-211">**Not ready**</span></span>

<span data-ttu-id="de4e5-212">商務用 Microsoft Store 未啟用或未與 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="de4e5-212">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="de4e5-213">如需詳細資訊，請參閱 how [to 使用 Microsoft Intune 商務用 Microsoft Store 管理大量購買的應用程式](/mem/intune/apps/windows-store-for-business)，並[在裝置上安裝 Intune 公司入口網站](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-213">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="de4e5-214">多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="de4e5-214">Multifactor authentication</span></span>

<span data-ttu-id="de4e5-215">多重要素驗證不得阻止 Microsoft 受管理的電腦在 Intune 和 Azure ad 中管理 Azure ad 組織 (承租人) 。</span><span class="sxs-lookup"><span data-stu-id="de4e5-215">Multifactor authentication must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>


<span data-ttu-id="de4e5-216">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-216">**Not ready**</span></span>

<span data-ttu-id="de4e5-217">針對指派給所有 **使用者的條件** 式存取原則，您可以設定某些多重要素驗證原則。</span><span class="sxs-lookup"><span data-stu-id="de4e5-217">You have some multifactor authentication policies set as **required** for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="de4e5-218">在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft 受管理的電腦服務帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。</span><span class="sxs-lookup"><span data-stu-id="de4e5-218">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="de4e5-219">如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-219">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="de4e5-220">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-220">**Advisory**</span></span>

<span data-ttu-id="de4e5-221">您在有條件存取原則上必須進行多重驗證，以防止 Microsoft 受管理的電腦管理 Microsoft 受管理的電腦服務。</span><span class="sxs-lookup"><span data-stu-id="de4e5-221">You have multifactor authentication required on conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="de4e5-222">在註冊期間，我們會從相關的條件式存取原則中排除 Microsoft 受管理的電腦服務帳戶，並套用新的條件式存取原則，以限制對這些帳戶的存取。</span><span class="sxs-lookup"><span data-stu-id="de4e5-222">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="de4e5-223">如需這些服務帳戶的詳細資訊，請參閱 [標準運作程式](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-223">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="de4e5-224">**Error**</span><span class="sxs-lookup"><span data-stu-id="de4e5-224">**Error**</span></span>

<span data-ttu-id="de4e5-225">Intune 系統管理員角色沒有足夠的許可權可進行這種檢查。</span><span class="sxs-lookup"><span data-stu-id="de4e5-225">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="de4e5-226">您也需要指派的任何 Azure AD 角色，以執行這項檢查：</span><span class="sxs-lookup"><span data-stu-id="de4e5-226">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="de4e5-227">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="de4e5-227">Security Reader</span></span>
- <span data-ttu-id="de4e5-228">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="de4e5-228">Security Administrator</span></span>
- <span data-ttu-id="de4e5-229">條件式存取管理員</span><span class="sxs-lookup"><span data-stu-id="de4e5-229">Conditional Access Administrator</span></span>
- <span data-ttu-id="de4e5-230">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="de4e5-230">Global Reader</span></span>
- <span data-ttu-id="de4e5-231">裝置管理員</span><span class="sxs-lookup"><span data-stu-id="de4e5-231">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="de4e5-232">PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="de4e5-232">PowerShell scripts</span></span>

<span data-ttu-id="de4e5-233">Windows PowerShell 腳本無法以目標 Microsoft 受管理的電腦裝置的方式指派。</span><span class="sxs-lookup"><span data-stu-id="de4e5-233">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="de4e5-234">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-234">**Advisory**</span></span>

<span data-ttu-id="de4e5-235">請確定您的 Azure AD 組織中的 Windows PowerShell 腳本不會以任何 Microsoft 管理桌面裝置或使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="de4e5-235">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="de4e5-236">請勿指派 PowerShell 腳本來設定所有使用者、所有裝置或兩者。</span><span class="sxs-lookup"><span data-stu-id="de4e5-236">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="de4e5-237">變更原則，以使用以特定 Azure AD 群組為目標的工作分派，不包含任何 Microsoft 受管理的電腦裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="de4e5-237">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="de4e5-238">如需詳細資訊，請參閱[在 Intune 中使用 Windows 10 裝置上的 PowerShell 腳本](/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-238">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="de4e5-239">區域</span><span class="sxs-lookup"><span data-stu-id="de4e5-239">Region</span></span>

<span data-ttu-id="de4e5-240">您的地區必須 Microsoft 受管理的電腦支援。</span><span class="sxs-lookup"><span data-stu-id="de4e5-240">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="de4e5-241">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-241">**Not ready**</span></span>

<span data-ttu-id="de4e5-242">目前不支援您的 Azure AD 組織區域 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="de4e5-242">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="de4e5-243">如需詳細資訊，請參閱[Microsoft 受管理的電腦支援的地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-243">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="de4e5-244">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-244">**Advisory**</span></span>

<span data-ttu-id="de4e5-245">Microsoft 受管理的電腦不支援 Azure AD 組織所在的一或多個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="de4e5-245">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="de4e5-246">如需詳細資訊，請參閱[Microsoft 受管理的電腦支援的地區和語言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-246">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="de4e5-247">安全性基準</span><span class="sxs-lookup"><span data-stu-id="de4e5-247">Security baselines</span></span>

<span data-ttu-id="de4e5-248">安全性基準原則不應該以任何 Microsoft 受管理的電腦裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="de4e5-248">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="de4e5-249">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-249">**Not ready**</span></span>

<span data-ttu-id="de4e5-250">您有一個針對所有使用者、所有裝置或兩者的安全性基準設定檔。</span><span class="sxs-lookup"><span data-stu-id="de4e5-250">You have a security baseline profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="de4e5-251">變更原則，以使用面向不包含任何 Microsoft 受管理的電腦裝置之特定 Azure AD 群組的工作分派。</span><span class="sxs-lookup"><span data-stu-id="de4e5-251">Change the policy to use an assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="de4e5-252">如需步驟，請參閱[Use security 基線 to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-252">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="de4e5-253">在註冊期間，我們會將新的安全性基準套用到所有的 Microsoft 受管理的電腦裝置。</span><span class="sxs-lookup"><span data-stu-id="de4e5-253">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="de4e5-254">註冊後，您可以在 Microsoft 端點管理員的 [設定 **原則**] 區域中，複查 Microsoft 受管理的電腦安全性基準原則。</span><span class="sxs-lookup"><span data-stu-id="de4e5-254">After enrollment, you can review the Microsoft Managed Desktop security baseline policy in the **Configuration policy** area of Microsoft Endpoint Manager.</span></span>

<span data-ttu-id="de4e5-255">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-255">**Advisory**</span></span>

<span data-ttu-id="de4e5-256">請確定任何已排除 Microsoft 受管理的電腦裝置的安全性基準原則。</span><span class="sxs-lookup"><span data-stu-id="de4e5-256">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="de4e5-257">如需步驟，請參閱[Use security 基線 to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-257">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="de4e5-258">在註冊期間，我們會將新的安全性基準套用到所有的 Microsoft 受管理的電腦裝置。</span><span class="sxs-lookup"><span data-stu-id="de4e5-258">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="de4e5-259">**新式的工作場所裝置-所有** Azure AD 群組是我們在 Microsoft 受管理的電腦中註冊時所建立的動態群組，所以在註冊後，您必須傳回此群組以排除此群組。</span><span class="sxs-lookup"><span data-stu-id="de4e5-259">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span> 

### <a name="unlicensed-admins"></a><span data-ttu-id="de4e5-260">未經許可的系統管理員</span><span class="sxs-lookup"><span data-stu-id="de4e5-260">Unlicensed admins</span></span>

<span data-ttu-id="de4e5-261">當我們與您的 Azure AD 組織互動時，必須啟用此設定，以避免出現「沒有許可權」的錯誤。</span><span class="sxs-lookup"><span data-stu-id="de4e5-261">This setting must be enabled to avoid a "lack of permissions" error when we interact with your Azure AD organization.</span></span> 

<span data-ttu-id="de4e5-262">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-262">**Not ready**</span></span>

<span data-ttu-id="de4e5-263">[**允許存取未授權的系統管理員**] 應已啟用。</span><span class="sxs-lookup"><span data-stu-id="de4e5-263">**Allow access to unlicensed admins** should be enabled.</span></span> <span data-ttu-id="de4e5-264">如需步驟，請參閱 [來賓帳戶的必要條件](/microsoft-365/managed-desktop/get-ready/guest-accounts)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-264">For steps, see [Prerequisites for guest accounts](/microsoft-365/managed-desktop/get-ready/guest-accounts).</span></span>

### <a name="windows-apps"></a><span data-ttu-id="de4e5-265">Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="de4e5-265">Windows apps</span></span>

<span data-ttu-id="de4e5-266">查看您的 Microsoft 受管理的電腦使用者所需的應用程式。</span><span class="sxs-lookup"><span data-stu-id="de4e5-266">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="de4e5-267">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-267">**Advisory**</span></span>

<span data-ttu-id="de4e5-268">您應該準備要讓 Microsoft 受管理的電腦使用者擁有的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="de4e5-268">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="de4e5-269">由於這些應用程式必須透過 Intune 部署，因此請評估重複使用現有的 Intune 應用程式。</span><span class="sxs-lookup"><span data-stu-id="de4e5-269">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="de4e5-270">請考慮使用公司入口網站 (請參閱在裝置和註冊狀態頁面[上安裝 Intune 公司入口網站](../get-started/company-portal.md) (ESP) ，將應用程式發佈至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="de4e5-270">Consider using Company Portal (see [Install Intune Company Portal on devices](../get-started/company-portal.md) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="de4e5-271">如需詳細資訊，請參閱使用 Autopilot 的[應用 Microsoft 受管理的電腦程式](apps.md)和[初次執行體驗和註冊狀態頁面](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-271">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="de4e5-272">您可以向您的 Microsoft 帳戶代表尋求 Microsoft Endpoint Configuration Manager 中的查詢，以識別準備好要遷移至 Intune 或需要調整的應用程式。</span><span class="sxs-lookup"><span data-stu-id="de4e5-272">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="de4e5-273">Windows Hello 企業版</span><span class="sxs-lookup"><span data-stu-id="de4e5-273">Windows Hello for Business</span></span>

<span data-ttu-id="de4e5-274">Microsoft 受管理的電腦需要啟用商務 Windows Hello。</span><span class="sxs-lookup"><span data-stu-id="de4e5-274">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="de4e5-275">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-275">**Not ready**</span></span>

<span data-ttu-id="de4e5-276">已停用商務用 Windows Hello。</span><span class="sxs-lookup"><span data-stu-id="de4e5-276">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="de4e5-277">遵循[建立商務用 Windows Hello 原則](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用</span><span class="sxs-lookup"><span data-stu-id="de4e5-277">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="de4e5-278">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-278">**Advisory**</span></span>

<span data-ttu-id="de4e5-279">未設定商務用 Windows Hello。</span><span class="sxs-lookup"><span data-stu-id="de4e5-279">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="de4e5-280">遵循 [[建立商務用 Windows Hello] 原則](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步驟來啟用。</span><span class="sxs-lookup"><span data-stu-id="de4e5-280">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="de4e5-281">Windows 10 更新振鈴</span><span class="sxs-lookup"><span data-stu-id="de4e5-281">Windows 10 update rings</span></span>

<span data-ttu-id="de4e5-282">Intune 中的「Windows 10 更新環路」原則不得以任何 Microsoft 受管理的電腦裝置為目標。</span><span class="sxs-lookup"><span data-stu-id="de4e5-282">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="de4e5-283">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-283">**Not ready**</span></span>

<span data-ttu-id="de4e5-284">您有一個「更新鈴聲」原則，針對所有裝置、所有使用者或兩者。</span><span class="sxs-lookup"><span data-stu-id="de4e5-284">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="de4e5-285">變更原則，以使用面向不包含任何 Microsoft 受管理的電腦裝置之特定 Azure AD 群組的工作分派。</span><span class="sxs-lookup"><span data-stu-id="de4e5-285">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="de4e5-286">如需步驟，請參閱[管理 Intune 中的 Windows 10 軟體更新](/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-286">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="de4e5-287">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-287">**Advisory**</span></span>

<span data-ttu-id="de4e5-288">請確定任何更新環原則您已排除現代的 **工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="de4e5-288">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="de4e5-289">如果您已將 Azure AD 使用者群組指派給這些原則，請確定任何更新環原則您已排除現代的 **工作場所-所有** 您新增 Microsoft 受管理的電腦使用者的 azure ad 群組，或)  (或同等群組。</span><span class="sxs-lookup"><span data-stu-id="de4e5-289">If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group).</span></span> <span data-ttu-id="de4e5-290">如需步驟，請參閱[管理 Intune 中的 Windows 10 軟體更新](/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-290">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="de4e5-291">現代的 **工作場所裝置（多功能**）和 **現代的工作場所-所有** Azure AD 群組都是您在 Microsoft 受管理的電腦註冊時所建立的群組，所以您必須在註冊後傳回排除此群組。</span><span class="sxs-lookup"><span data-stu-id="de4e5-291">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="de4e5-292">Azure Active Directory 設定</span><span class="sxs-lookup"><span data-stu-id="de4e5-292">Azure Active Directory settings</span></span>

<span data-ttu-id="de4e5-293">您可以在[Azure 入口網站](https://portal.azure.com)中存取 Azure Active Directory 設定。</span><span class="sxs-lookup"><span data-stu-id="de4e5-293">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="de4e5-294">Intune 登記</span><span class="sxs-lookup"><span data-stu-id="de4e5-294">Intune enrollment</span></span>

<span data-ttu-id="de4e5-295">您的 Azure AD 組織中的 Windows 10 裝置必須能夠在 Intune 中自動註冊。</span><span class="sxs-lookup"><span data-stu-id="de4e5-295">Windows 10 devices in your Azure AD organization must be able to automatically enroll in Intune.</span></span>

<span data-ttu-id="de4e5-296">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-296">**Advisory**</span></span>

<span data-ttu-id="de4e5-297">確定 **MDM 使用者範圍** 已設定為 **部分** 或 **全部**（非 **無**）。</span><span class="sxs-lookup"><span data-stu-id="de4e5-297">Make sure the **MDM User scope** is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="de4e5-298">如果您選擇 [**部分**]，請在註冊後再進行註冊，然後選取 [**新式的工作場所]-** **群組** 的所有 Azure AD 群組，或針對所有 Microsoft 受管理的電腦使用者的同等群組。</span><span class="sxs-lookup"><span data-stu-id="de4e5-298">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users.</span></span>  <span data-ttu-id="de4e5-299">請參閱[使用 Microsoft Intune 設定 Windows 裝置的註冊](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-299">See [Set up enrollment for Windows devices by using Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>

### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="de4e5-300">專用訂閱</span><span class="sxs-lookup"><span data-stu-id="de4e5-300">Ad hoc subscriptions</span></span>

<span data-ttu-id="de4e5-301">建議您如何檢查 (如果設定為 "false" 的設定 ) 可能會導致 Enterprise 狀態漫遊無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="de4e5-301">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="de4e5-302">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-302">**Advisory**</span></span>

<span data-ttu-id="de4e5-303">確定 **AllowAdHocSubscriptions** 設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="de4e5-303">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="de4e5-304">否則，Enterprise 狀態漫遊可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="de4e5-304">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="de4e5-305">如需詳細資訊，請參閱 [MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-305">For more information, see [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="de4e5-306">企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="de4e5-306">Enterprise State Roaming</span></span>

<span data-ttu-id="de4e5-307">Enterprise應啟用狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="de4e5-307">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="de4e5-308">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-308">**Advisory**</span></span>

<span data-ttu-id="de4e5-309">確定已針對 **所有** 或 **選取** 的群組啟用 Enterprise 狀態漫遊。</span><span class="sxs-lookup"><span data-stu-id="de4e5-309">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="de4e5-310">如需詳細資訊，請參閱[Enable Enterprise State 漫遊 in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-310">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="de4e5-311">授權</span><span class="sxs-lookup"><span data-stu-id="de4e5-311">Licenses</span></span>

<span data-ttu-id="de4e5-312">需要有許多授權才能使用 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="de4e5-312">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="de4e5-313">**尚未準備好**</span><span class="sxs-lookup"><span data-stu-id="de4e5-313">**Not Ready**</span></span>

<span data-ttu-id="de4e5-314">您沒有所有需要使用 Microsoft 受管理的電腦的授權。</span><span class="sxs-lookup"><span data-stu-id="de4e5-314">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="de4e5-315">如需詳細資訊，請參閱[Microsoft 受管理的電腦技術](../intro/technologies.md)和[有關授權的詳細](prerequisites.md#more-about-licenses)資訊。</span><span class="sxs-lookup"><span data-stu-id="de4e5-315">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="microsoft-managed-desktop-service-accounts"></a><span data-ttu-id="de4e5-316">Microsoft 受管理的電腦服務帳戶</span><span class="sxs-lookup"><span data-stu-id="de4e5-316">Microsoft Managed Desktop service accounts</span></span>

<span data-ttu-id="de4e5-317">某些帳戶名稱可能與 Microsoft 受管理的電腦所建立的帳戶名稱相衝突，以管理 Microsoft 受管理的電腦服務。</span><span class="sxs-lookup"><span data-stu-id="de4e5-317">Certain account names could conflict with account names created by Microsoft Managed Desktop to manage the Microsoft Managed Desktop service.</span></span>

<span data-ttu-id="de4e5-318">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-318">**Not ready**</span></span>

<span data-ttu-id="de4e5-319">您至少要有一個帳戶名稱與 Microsoft 受管理的電腦所建立的帳戶名稱產生衝突。</span><span class="sxs-lookup"><span data-stu-id="de4e5-319">You have at least one account name that will conflict with account names created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="de4e5-320">請與您的 Microsoft 帳戶代表合作，以排除這些帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="de4e5-320">Work with your Microsoft account representative to exclude these account names.</span></span> <span data-ttu-id="de4e5-321">我們不會向公眾列出帳戶名稱，以儘量降低安全性風險。</span><span class="sxs-lookup"><span data-stu-id="de4e5-321">We don't list the account names publicly to minimize security risk.</span></span> 


### <a name="security-administrator-roles"></a><span data-ttu-id="de4e5-322">安全性管理員角色</span><span class="sxs-lookup"><span data-stu-id="de4e5-322">Security administrator roles</span></span>

<span data-ttu-id="de4e5-323">具有特定安全性角色的使用者必須在 Microsoft Defender for Endpoint 中指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="de4e5-323">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="de4e5-324">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-324">**Advisory**</span></span>

<span data-ttu-id="de4e5-325">如果您已將使用者指派至 Azure AD 組織中的任何角色，請確定他們也在 Microsoft Defender for Endpoint 中指派這些角色。</span><span class="sxs-lookup"><span data-stu-id="de4e5-325">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="de4e5-326">否則，具有這些角色的系統管理員將無法存取管理員入口網站。</span><span class="sxs-lookup"><span data-stu-id="de4e5-326">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="de4e5-327">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="de4e5-327">Security Operator</span></span>
- <span data-ttu-id="de4e5-328">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="de4e5-328">Global Reader</span></span>

<span data-ttu-id="de4e5-329">如需詳細資訊，請參閱 [建立及管理以角色為基礎的存取控制角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-329">For more information, see [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="de4e5-330">安全性預設值</span><span class="sxs-lookup"><span data-stu-id="de4e5-330">Security default</span></span>

<span data-ttu-id="de4e5-331">Azure Active Directory 中的安全性預設值會防止 Microsoft 受管理的電腦管理裝置。</span><span class="sxs-lookup"><span data-stu-id="de4e5-331">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="de4e5-332">**未就緒**</span><span class="sxs-lookup"><span data-stu-id="de4e5-332">**Not ready**</span></span>

<span data-ttu-id="de4e5-333">您已開啟安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="de4e5-333">You have Security defaults turned on.</span></span> <span data-ttu-id="de4e5-334">關閉安全性預設值，並設定條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="de4e5-334">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="de4e5-335">如需詳細資訊，請參閱 [一般條件式存取原則](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-335">For more information, see [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="de4e5-336">自助密碼重設</span><span class="sxs-lookup"><span data-stu-id="de4e5-336">Self-service Password Reset</span></span>

<span data-ttu-id="de4e5-337">自助密碼重設 (SSPR) 可以針對所有 Microsoft 受管理的電腦使用者以外的 Microsoft 受管理的電腦服務帳戶啟用。</span><span class="sxs-lookup"><span data-stu-id="de4e5-337">Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="de4e5-338">如需詳細資訊，請參閱[教學課程：讓使用者能夠使用 Azure Active Directory 自助密碼重設來解除鎖定帳戶或重設密碼](/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="de4e5-338">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="de4e5-339">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-339">**Advisory**</span></span>

<span data-ttu-id="de4e5-340">請確定 SSPR **選取** 的設定包括 Microsoft 受管理的電腦使用者，但不包括 Microsoft 受管理的電腦服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="de4e5-340">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="de4e5-341">SSPR 啟用時，Microsoft 受管理的電腦服務帳戶無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="de4e5-341">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="de4e5-342">標準使用者角色</span><span class="sxs-lookup"><span data-stu-id="de4e5-342">Standard user role</span></span>

<span data-ttu-id="de4e5-343">除了為全域系統管理員和裝置管理員指派 Azure AD 角色的使用者以外，Microsoft 受管理的電腦使用者將是不具備本機系統管理員許可權的標準使用者。</span><span class="sxs-lookup"><span data-stu-id="de4e5-343">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="de4e5-344">當其他使用者啟動其 Microsoft 受管理的電腦裝置時，系統會將其指派為標準使用者角色。</span><span class="sxs-lookup"><span data-stu-id="de4e5-344">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="de4e5-345">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-345">**Advisory**</span></span>

<span data-ttu-id="de4e5-346">Microsoft 受管理的電腦使用者將不會在註冊後，在其 Microsoft 受管理的電腦裝置上具有本機系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="de4e5-346">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="de4e5-347">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="de4e5-347">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="de4e5-348">OneDrive</span><span class="sxs-lookup"><span data-stu-id="de4e5-348">OneDrive</span></span>

<span data-ttu-id="de4e5-349">[**僅允許在加入特定網域的 pc 上進行同步** 處理] 設定會與 Microsoft 受管理的電腦產生衝突。</span><span class="sxs-lookup"><span data-stu-id="de4e5-349">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="de4e5-350">您可以在 OneDrive 系統[管理中心](https://admin.onedrive.com)存取 OneDrive 設定。</span><span class="sxs-lookup"><span data-stu-id="de4e5-350">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="de4e5-351">**公告**</span><span class="sxs-lookup"><span data-stu-id="de4e5-351">**Advisory**</span></span>

<span data-ttu-id="de4e5-352">您正在使用 [ **僅允許在加入特定網域的電腦上同步** 處理] 設定。</span><span class="sxs-lookup"><span data-stu-id="de4e5-352">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="de4e5-353">此設定不會搭配 Microsoft 受管理的電腦使用。</span><span class="sxs-lookup"><span data-stu-id="de4e5-353">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="de4e5-354">停用此設定，而不是設定 OneDrive 使用條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="de4e5-354">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="de4e5-355">請參閱 [規劃設定條件式存取部署](/azure/active-directory/conditional-access/plan-conditional-access) 以取得協助。</span><span class="sxs-lookup"><span data-stu-id="de4e5-355">See [Plan a Conditional Access deployment](/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>
