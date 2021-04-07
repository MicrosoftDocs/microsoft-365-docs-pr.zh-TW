---
title: 建議的 Microsoft Cloud App Security 原則 SaaS app-Microsoft 365 Enterprise |Microsoft 檔
description: 說明整合 Microsoft Cloud App Security 的建議原則。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: Admin
ms.author: bcarter
ms.date: 03/22/2021
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 61509c88ea2289509abd5ec7b6c0dcd54395d5f0
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599968"
---
# <a name="recommended-microsoft-cloud-app-security-policies-for-saas-apps"></a><span data-ttu-id="06eb7-103">SaaS 應用程式的建議 Microsoft Cloud App 安全性原則</span><span class="sxs-lookup"><span data-stu-id="06eb7-103">Recommended Microsoft Cloud App Security policies for SaaS apps</span></span>
<span data-ttu-id="06eb7-104">Microsoft Cloud App Security 組建于 Azure AD 條件式存取原則上，以啟用即時監控，並使用 SaaS 的應用程式（例如封鎖下載、上傳、複製及貼上）來控制細微動作。</span><span class="sxs-lookup"><span data-stu-id="06eb7-104">Microsoft Cloud App Security builds on Azure AD conditional access policies to enable real-time monitoring and control of granular actions with SaaS apps, such as blocking downloads, uploads, copy and paste, and printing.</span></span> <span data-ttu-id="06eb7-105">此功能會將安全性新增至具有固有風險的會話，例如從未受管理的裝置存取公司資源或來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="06eb7-105">This feature adds security to sessions that carry inherent risk, such as when corporate resources are accessed from unmanaged devices or by guest users.</span></span>

<span data-ttu-id="06eb7-106">Microsoft Cloud App Security 也會以 Microsoft 資訊保護為內部整合，提供即時內容檢查，以根據敏感資訊類型和敏感度標籤尋找敏感性資料，並採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="06eb7-106">Microsoft Cloud App Security also integrates natively with Microsoft Information Protection, providing real-time content inspection to find sensitive data based on sensitive information types and sensitivity labels and to take appropriate action.</span></span>

<span data-ttu-id="06eb7-107">本指南包含下列案例的建議：</span><span class="sxs-lookup"><span data-stu-id="06eb7-107">This guidance includes recommendations for these scenarios:</span></span>

- <span data-ttu-id="06eb7-108">將 SaaS 的應用程式引入 IT 管理</span><span class="sxs-lookup"><span data-stu-id="06eb7-108">Bring SaaS apps into IT management</span></span>
- <span data-ttu-id="06eb7-109">針對特定的 SaaS 應用程式調整保護</span><span class="sxs-lookup"><span data-stu-id="06eb7-109">Tune protection for specific SaaS apps</span></span>
- <span data-ttu-id="06eb7-110">設定資料遺失防護 (DLP) 以協助遵守資料保護法規</span><span class="sxs-lookup"><span data-stu-id="06eb7-110">Configure data loss prevention (DLP) to help comply with data protection regulations</span></span>

## <a name="bring-saas-apps-into-it-management"></a><span data-ttu-id="06eb7-111">將 SaaS 的應用程式引入 IT 管理</span><span class="sxs-lookup"><span data-stu-id="06eb7-111">Bring SaaS apps into IT management</span></span>

<span data-ttu-id="06eb7-112">使用 Microsoft Cloud App Security 管理 SaaS 應用程式的第一步，是探索這些應用程式，然後將其新增至您的 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="06eb7-112">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="06eb7-113">如果您需要探索協助，請參閱 [探索和管理您網路中的 SaaS 應用程式](/cloud-app-security/tutorial-shadow-it)。</span><span class="sxs-lookup"><span data-stu-id="06eb7-113">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="06eb7-114">在您探索應用程式之後， [將它們新增至您的 AZURE AD 租](/azure/active-directory/manage-apps/add-application-portal)使用者。</span><span class="sxs-lookup"><span data-stu-id="06eb7-114">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="06eb7-115">您可以執行下列動作來開始管理：</span><span class="sxs-lookup"><span data-stu-id="06eb7-115">You can begin to manage these by doing the following:</span></span>

1. <span data-ttu-id="06eb7-116">首先，在 Azure AD 中建立新的條件式存取原則，並將其設定為「使用條件式存取應用程式控制」。</span><span class="sxs-lookup"><span data-stu-id="06eb7-116">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="06eb7-117">這會將要求重新導向至 Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="06eb7-117">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="06eb7-118">您可以建立一個原則，並將所有 SaaS 應用程式新增至此原則。</span><span class="sxs-lookup"><span data-stu-id="06eb7-118">You can create one policy and add all SaaS apps to this policy.</span></span>
1. <span data-ttu-id="06eb7-119">接下來，在 Cloud App Security 中建立會話原則。</span><span class="sxs-lookup"><span data-stu-id="06eb7-119">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="06eb7-120">針對每個您想要套用的控制項建立一個原則。</span><span class="sxs-lookup"><span data-stu-id="06eb7-120">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="06eb7-121">SaaS 應用程式的許可權通常是以業務存取應用程式的需求為基礎。</span><span class="sxs-lookup"><span data-stu-id="06eb7-121">Permissions to SaaS apps are typically based on business need for access to the app.</span></span> <span data-ttu-id="06eb7-122">這些許可權可以是高度動態的。</span><span class="sxs-lookup"><span data-stu-id="06eb7-122">These permissions can be highly dynamic.</span></span> <span data-ttu-id="06eb7-123">使用雲端 App 安全性策略可確保對應用程式資料的保護，不論是否將使用者指派至與基線、敏感或高度管制保護相關聯的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="06eb7-123">Using Cloud App Security policies ensures protection to app data, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="06eb7-124">為了保護您的 SaaS 應用程式集合中的資料，下列圖表說明必要的 Azure AD 條件式存取原則，以及您可以在 Cloud App Security 中建立的建議原則。</span><span class="sxs-lookup"><span data-stu-id="06eb7-124">To protect data across your collection of SaaS apps, the following diagram illustrates the necessary Azure AD conditional access policy plus suggested policies you can create in Cloud App Security.</span></span> <span data-ttu-id="06eb7-125">在此範例中，Cloud App Security 中建立的原則會套用至所有所管理的 SaaS 應用程式。</span><span class="sxs-lookup"><span data-stu-id="06eb7-125">In this example, the policies created in Cloud App Security apply to all SaaS apps you are managing.</span></span> <span data-ttu-id="06eb7-126">這些設計目的是根據裝置是否受管理，以及已套用至檔案的靈敏度標籤，套用適當的控制項。</span><span class="sxs-lookup"><span data-stu-id="06eb7-126">These are designed to apply appropriate controls based on whether devices are managed as well as sensitivity labels that are already applied to files.</span></span>

![在 Cloud App Security 中管理 SaaS 應用程式的原則](../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png)

<span data-ttu-id="06eb7-128">下表列出您必須在 Azure AD 中建立的新條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="06eb7-128">The following table lists the new conditional access policy you must create in Azure AD.</span></span>

|<span data-ttu-id="06eb7-129">保護層級</span><span class="sxs-lookup"><span data-stu-id="06eb7-129">Protection level</span></span>|<span data-ttu-id="06eb7-130">原則</span><span class="sxs-lookup"><span data-stu-id="06eb7-130">Policy</span></span>|<span data-ttu-id="06eb7-131">其他資訊</span><span class="sxs-lookup"><span data-stu-id="06eb7-131">More information</span></span>|
|---|---|---|
|<span data-ttu-id="06eb7-132">所有保護層級</span><span class="sxs-lookup"><span data-stu-id="06eb7-132">All protection levels</span></span>|[<span data-ttu-id="06eb7-133">在 Cloud App Security 中使用條件式存取應用程式控制</span><span class="sxs-lookup"><span data-stu-id="06eb7-133">Use Conditional Access App Control in Cloud App Security</span></span>](/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad)|<span data-ttu-id="06eb7-134">這會將您的 IdP 設定 (Azure AD) ，以與 Cloud App Security 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="06eb7-134">This configures your IdP (Azure AD) to work with Cloud App Security.</span></span>|
||||

<span data-ttu-id="06eb7-135">下表列出您可以建立的範例原則，以保護所有的 SaaS 應用程式。</span><span class="sxs-lookup"><span data-stu-id="06eb7-135">This next table lists the example policies illustrated above that you can create to protect all SaaS apps.</span></span> <span data-ttu-id="06eb7-136">請務必評估您自己的商務、安全性和合規性目標，然後建立可為您的環境提供最適當保護的原則。</span><span class="sxs-lookup"><span data-stu-id="06eb7-136">Be sure to evaluate your own business, security, and compliance objectives and then create policies that provide the most appropriate protection for your environment.</span></span>

|<span data-ttu-id="06eb7-137">保護層級</span><span class="sxs-lookup"><span data-stu-id="06eb7-137">Protection level</span></span>|<span data-ttu-id="06eb7-138">原則</span><span class="sxs-lookup"><span data-stu-id="06eb7-138">Policy</span></span>|
|---|---|
|<span data-ttu-id="06eb7-139">基準</span><span class="sxs-lookup"><span data-stu-id="06eb7-139">Baseline</span></span>|<span data-ttu-id="06eb7-140">監視非管理裝置的流量</span><span class="sxs-lookup"><span data-stu-id="06eb7-140">Monitor traffic from unmanaged devices</span></span> <p> <span data-ttu-id="06eb7-141">從未受管理的裝置新增檔下載保護</span><span class="sxs-lookup"><span data-stu-id="06eb7-141">Add protection to file downloads from unmanaged devices</span></span>|
|<span data-ttu-id="06eb7-142">敏感性</span><span class="sxs-lookup"><span data-stu-id="06eb7-142">Sensitive</span></span>|<span data-ttu-id="06eb7-143">封鎖以敏感或分類方式從未受管理的裝置下載的檔案 (這只會提供瀏覽器的存取) </span><span class="sxs-lookup"><span data-stu-id="06eb7-143">Block download of files labeled with sensitive or classified from unmanaged devices (this provides browser only access)</span></span>|
|<span data-ttu-id="06eb7-144">高管制</span><span class="sxs-lookup"><span data-stu-id="06eb7-144">Highly regulated</span></span>|<span data-ttu-id="06eb7-145">封鎖所有裝置中標示為 [已分類的檔案] (這只會提供瀏覽器的存取) </span><span class="sxs-lookup"><span data-stu-id="06eb7-145">Block download of files labeled with classified from all devices (this provides browser only access)</span></span>|
|||

<span data-ttu-id="06eb7-146">如需設定條件式存取應用程式控制的端對端指示，請參閱 [部署特色應用程式的條件式存取應用程式控制](/cloud-app-security/proxy-deployment-aad)。</span><span class="sxs-lookup"><span data-stu-id="06eb7-146">For end-to-end instructions for setting up Conditional Access App Control, see [Deploy Conditional Access App Control for featured apps](/cloud-app-security/proxy-deployment-aad).</span></span> <span data-ttu-id="06eb7-147">本文將引導您完成在 Azure AD 中建立必要的條件式存取原則，並測試您的 SaaS 應用程式。</span><span class="sxs-lookup"><span data-stu-id="06eb7-147">This article walks you through the process of creating the necessary conditional access policy in Azure AD and testing your SaaS apps.</span></span>

<span data-ttu-id="06eb7-148">如需詳細資訊，請參閱 [使用 Microsoft Cloud App Security 條件式 Access 應用程式控制保護應用](/cloud-app-security/proxy-intro-aad)程式。</span><span class="sxs-lookup"><span data-stu-id="06eb7-148">For more information, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span>

## <a name="tune-protection-for-specific-saas-apps"></a><span data-ttu-id="06eb7-149">針對特定的 SaaS 應用程式調整保護</span><span class="sxs-lookup"><span data-stu-id="06eb7-149">Tune protection for specific SaaS apps</span></span>

<span data-ttu-id="06eb7-150">您可能想要將其他監控和控制套用至環境中的特定 SaaS 應用程式。</span><span class="sxs-lookup"><span data-stu-id="06eb7-150">You might want to apply additional monitoring and controls to specific SaaS apps in your environment.</span></span> <span data-ttu-id="06eb7-151">Cloud App Security 可讓您完成此作業。</span><span class="sxs-lookup"><span data-stu-id="06eb7-151">Cloud App Security allows you to accomplish this.</span></span> <span data-ttu-id="06eb7-152">例如，如果您環境中經常使用像像這樣的應用程式，就可以套用其他控制項。</span><span class="sxs-lookup"><span data-stu-id="06eb7-152">For example, if an app like Box is used heavily in your environment, it makes sense to apply additional controls.</span></span> <span data-ttu-id="06eb7-153">或者，如果您的法律或財務部門是針對敏感的商務資料使用特定的 SaaS 應用程式，您可以針對這些應用程式設定額外的保護。</span><span class="sxs-lookup"><span data-stu-id="06eb7-153">Or, if your legal or finance department is using a specific SaaS app for sensitive business data, you can target extra protection to these apps.</span></span>

<span data-ttu-id="06eb7-154">例如，您可以使用下列內建的反常狀況偵測原則範本，保護 Box 環境：</span><span class="sxs-lookup"><span data-stu-id="06eb7-154">For example, you can protect your Box environment with these types of built-in anomaly detection policy templates:</span></span>

- <span data-ttu-id="06eb7-155">匿名 IP 位址的活動</span><span class="sxs-lookup"><span data-stu-id="06eb7-155">Activity from anonymous IP addresses</span></span>
- <span data-ttu-id="06eb7-156">非常見國家的活動</span><span class="sxs-lookup"><span data-stu-id="06eb7-156">Activity from infrequent country</span></span>
- <span data-ttu-id="06eb7-157">可疑 IP 位址的活動</span><span class="sxs-lookup"><span data-stu-id="06eb7-157">Activity from suspicious IP addresses</span></span>
- <span data-ttu-id="06eb7-158">不可能的移動</span><span class="sxs-lookup"><span data-stu-id="06eb7-158">Impossible travel</span></span>
- <span data-ttu-id="06eb7-159">終止的使用者 (所執行的活動需要 AAD 視為 IdP) </span><span class="sxs-lookup"><span data-stu-id="06eb7-159">Activity performed by terminated user (requires AAD as IdP)</span></span>
- <span data-ttu-id="06eb7-160">惡意程式碼偵測</span><span class="sxs-lookup"><span data-stu-id="06eb7-160">Malware detection</span></span>
- <span data-ttu-id="06eb7-161">多次失敗的登入嘗試</span><span class="sxs-lookup"><span data-stu-id="06eb7-161">Multiple failed login attempts</span></span>
- <span data-ttu-id="06eb7-162">勒索軟體活動</span><span class="sxs-lookup"><span data-stu-id="06eb7-162">Ransomware activity</span></span>
- <span data-ttu-id="06eb7-163">危險的 Oauth 應用程式</span><span class="sxs-lookup"><span data-stu-id="06eb7-163">Risky Oauth App</span></span>
- <span data-ttu-id="06eb7-164">不尋常的檔案共用活動</span><span class="sxs-lookup"><span data-stu-id="06eb7-164">Unusual file share activity</span></span>

<span data-ttu-id="06eb7-165">這些都是範例。</span><span class="sxs-lookup"><span data-stu-id="06eb7-165">These are examples.</span></span> <span data-ttu-id="06eb7-166">其他原則範本會定期新增。</span><span class="sxs-lookup"><span data-stu-id="06eb7-166">Additional policy templates are added on a regular basis.</span></span> <span data-ttu-id="06eb7-167">如需如何對特定 app 套用其他保護的範例，請參閱 [保護連線的應用程式](/cloud-app-security/protect-connected-apps)。</span><span class="sxs-lookup"><span data-stu-id="06eb7-167">For examples of how to apply additional protection to specific apps, see [Protecting connected apps](/cloud-app-security/protect-connected-apps).</span></span>

<span data-ttu-id="06eb7-168">[Cloud App Security 如何協助您保護 box 環境](/cloud-app-security/protect-box) 示範的控制項類型可協助您保護 box 中的商務資料，以及其他具有敏感性資料的應用程式。</span><span class="sxs-lookup"><span data-stu-id="06eb7-168">[How Cloud App Security helps protect your Box environment](/cloud-app-security/protect-box) demonstrates the types of controls that can help you protect your business data in Box and other apps with sensitive data.</span></span>

## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a><span data-ttu-id="06eb7-169">設定資料遺失防護 (DLP) 以協助遵守資料保護法規</span><span class="sxs-lookup"><span data-stu-id="06eb7-169">Configure data loss prevention (DLP) to help comply with data protection regulations</span></span>

<span data-ttu-id="06eb7-170">Cloud App Security 可能是設定規范保護規範的一個極具價值的工具。</span><span class="sxs-lookup"><span data-stu-id="06eb7-170">Cloud App Security can be a valuable tool for configuring protection for compliance regulations.</span></span> <span data-ttu-id="06eb7-171">在此情況下，您可以建立特定的原則來尋找法規套用的特定資料，並設定每個原則採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="06eb7-171">In this case, you create specific policies to look for specific data that a regulation applies to and configure each policy to take appropriate action.</span></span>

<span data-ttu-id="06eb7-172">下列圖解和 table 提供一些原則範例，可設定這些原則，以協助遵循一般資料保護法規 (GDPR) 。</span><span class="sxs-lookup"><span data-stu-id="06eb7-172">The following illustration and table provide several examples of policies that can be configured to help comply with  the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="06eb7-173">在這些範例中，原則會尋找特定的資料。</span><span class="sxs-lookup"><span data-stu-id="06eb7-173">In these examples, policies look for specific data.</span></span> <span data-ttu-id="06eb7-174">根據資料的靈敏度，每個原則都設定為採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="06eb7-174">Based on the sensitivity of the data, each policy is configured to take appropriate action.</span></span>

![資料遺失防護範例 Cloud App Security 原則](../../media/microsoft-365-policies-configurations/mcas-dlp.png)

|<span data-ttu-id="06eb7-176">保護層級</span><span class="sxs-lookup"><span data-stu-id="06eb7-176">Protection level</span></span>|<span data-ttu-id="06eb7-177">範例原則</span><span class="sxs-lookup"><span data-stu-id="06eb7-177">Example policies</span></span>|
|---|---|
|<span data-ttu-id="06eb7-178">基準</span><span class="sxs-lookup"><span data-stu-id="06eb7-178">Baseline</span></span>|<span data-ttu-id="06eb7-179">當包含此機密資訊類型的檔案 ( 「信用卡號碼」 ) 會在組織外共用時發出警示</span><span class="sxs-lookup"><span data-stu-id="06eb7-179">Alert when files containing this sensitive information type ("Credit Card Number") are shared outside the organization</span></span> <p> <span data-ttu-id="06eb7-180">>封鎖包含此機密資訊類型的檔案下載 ( "信用卡號碼" ) 非管理裝置</span><span class="sxs-lookup"><span data-stu-id="06eb7-180">>Block downloads of files containing this sensitive information type (”Credit card number") to unmanaged devices</span></span>|
|<span data-ttu-id="06eb7-181">敏感性</span><span class="sxs-lookup"><span data-stu-id="06eb7-181">Sensitive</span></span>|<span data-ttu-id="06eb7-182">保護包含此機密資訊類型的檔案下載 ( 「信用卡號碼」 ) 受管理的裝置</span><span class="sxs-lookup"><span data-stu-id="06eb7-182">Protect downloads of files containing this sensitive information type ("Credit card number") to managed devices</span></span> <p> <span data-ttu-id="06eb7-183">封鎖包含此機密資訊類型的檔案下載 ( 「信用卡號碼」 ) 非受管理的裝置</span><span class="sxs-lookup"><span data-stu-id="06eb7-183">Block downloads of files containing this sensitive information type ("Credit card number") to unmanaged devices</span></span> <p> <span data-ttu-id="06eb7-184">當具有下列標籤的檔案上傳至 OneDrive for Business or Box (客戶資料，人力資源：薪資資料、人力資源、員工資料) </span><span class="sxs-lookup"><span data-stu-id="06eb7-184">Alert when a file with on of these labels is uploaded to OneDrive for Business or Box (Customer data, Human Resources: Salary Data,Human Resources, Employee data)</span></span>|
|<span data-ttu-id="06eb7-185">高管制</span><span class="sxs-lookup"><span data-stu-id="06eb7-185">Highly regulated</span></span>|<span data-ttu-id="06eb7-186">當具有此標籤的檔案 ( 「高分類」 ) 下載到受管理的裝置時發出警示</span><span class="sxs-lookup"><span data-stu-id="06eb7-186">Alert when files with this label ("Highly classified") are downloaded to managed devices</span></span> <p> <span data-ttu-id="06eb7-187">封鎖此標籤的下載檔案 ( 「高分類」 ) 非受管理裝置</span><span class="sxs-lookup"><span data-stu-id="06eb7-187">Block downloads of files with this label ("Highly classified") to unmanaged devices</span></span>|
|||

## <a name="next-steps"></a><span data-ttu-id="06eb7-188">後續步驟</span><span class="sxs-lookup"><span data-stu-id="06eb7-188">Next steps</span></span>

<span data-ttu-id="06eb7-189">如需使用 Cloud App Security 的詳細資訊，請參閱 [Microsoft Cloud App security 檔](//cloud-app-security/)。</span><span class="sxs-lookup"><span data-stu-id="06eb7-189">For more information about using Cloud App Security, see [Microsoft Cloud App Security documentation](//cloud-app-security/).</span></span>
