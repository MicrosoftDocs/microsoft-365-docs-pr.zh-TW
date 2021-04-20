---
title: 從 Microsoft Cloud Deutschland 進行遷移後的遷移後活動
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：從 Microsoft Cloud 德國移 (Microsoft Cloud Deutschland) 到新德文 datacenter 區域中的 Office 365 服務後，遷移後的活動。
ms.openlocfilehash: ee8dedf7ffaf6bfc4246b1a8cc2522c15d763cd1
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899361"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="200f2-103">從 Microsoft Cloud Deutschland 進行遷移後的遷移後活動</span><span class="sxs-lookup"><span data-stu-id="200f2-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="200f2-104">下列各節會在從 Microsoft Cloud 德國 (Microsoft Cloud Deutschland) 到新德文 datacenter 區域中的 Office 365 服務後，提供多項服務的遷移後活動。</span><span class="sxs-lookup"><span data-stu-id="200f2-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="200f2-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="200f2-105">Azure AD</span></span>
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="200f2-106">Azure AD 同盟驗證與 AD FS</span><span class="sxs-lookup"><span data-stu-id="200f2-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="200f2-107">**適用于：** 所有使用同盟驗證與 AD FS 的客戶</span><span class="sxs-lookup"><span data-stu-id="200f2-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="200f2-108">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="200f2-108">Step(s)</span></span> | <span data-ttu-id="200f2-109">描述</span><span class="sxs-lookup"><span data-stu-id="200f2-109">Description</span></span> | <span data-ttu-id="200f2-110">影響</span><span class="sxs-lookup"><span data-stu-id="200f2-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="200f2-111">從 Microsoft Cloud Deutschland AD FS 移除信賴憑證者信任。</span><span class="sxs-lookup"><span data-stu-id="200f2-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="200f2-112">在完成轉換至 Azure AD 之後，該組織完全使用 Office 365 服務，而且不再連接至 Microsoft 雲端 Deutschland。</span><span class="sxs-lookup"><span data-stu-id="200f2-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="200f2-113">此時，客戶需要移除對 Microsoft Cloud Deutschland 端點的信賴憑證者信任。</span><span class="sxs-lookup"><span data-stu-id="200f2-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="200f2-114">只有在客戶的任何應用程式都指向 Microsoft Cloud Deutschland 端點時，當 Azure AD (IdP) 時，才會執行此動作。</span><span class="sxs-lookup"><span data-stu-id="200f2-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="200f2-115">同盟驗證組織</span><span class="sxs-lookup"><span data-stu-id="200f2-115">Federated Authentication organizations</span></span> | <span data-ttu-id="200f2-116">無。</span><span class="sxs-lookup"><span data-stu-id="200f2-116">None.</span></span> |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="200f2-117">群組核准</span><span class="sxs-lookup"><span data-stu-id="200f2-117">Group approvals</span></span>
<span data-ttu-id="200f2-118">**適用于：** 在遷移前30天內，未核准 Azure AD 群組核准要求的使用者</span><span class="sxs-lookup"><span data-stu-id="200f2-118">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="200f2-119">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="200f2-119">Step(s)</span></span> | <span data-ttu-id="200f2-120">描述</span><span class="sxs-lookup"><span data-stu-id="200f2-120">Description</span></span> | <span data-ttu-id="200f2-121">影響</span><span class="sxs-lookup"><span data-stu-id="200f2-121">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="200f2-122">在過去30天內加入 Azure AD 群組的要求若未獲核准原始要求，將需要重新要求遷移。</span><span class="sxs-lookup"><span data-stu-id="200f2-122">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="200f2-123">若使用者在遷移前的30天內未獲核准，使用者的客戶將需要使用「存取面板」提交要求，以加入 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="200f2-123">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="200f2-124">最終使用者：</span><span class="sxs-lookup"><span data-stu-id="200f2-124">As an end-user:</span></span> <ol><li><span data-ttu-id="200f2-125">流覽至 [Access 面板](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</span><span class="sxs-lookup"><span data-stu-id="200f2-125">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="200f2-126">尋找在遷移前30天內，成員核准已擱置的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="200f2-126">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="200f2-127">要求重新加入 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="200f2-127">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="200f2-128">在遷移後，若要求加入超過30天的群組，將無法進行核准。</span><span class="sxs-lookup"><span data-stu-id="200f2-128">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a><span data-ttu-id="200f2-129">自訂 DNS 更新</span><span class="sxs-lookup"><span data-stu-id="200f2-129">Custom DNS updates</span></span>
<span data-ttu-id="200f2-130">**適用于：**  所有客戶都管理自己的 DNS 區域</span><span class="sxs-lookup"><span data-stu-id="200f2-130">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="200f2-131">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="200f2-131">Step(s)</span></span> | <span data-ttu-id="200f2-132">描述</span><span class="sxs-lookup"><span data-stu-id="200f2-132">Description</span></span> | <span data-ttu-id="200f2-133">影響</span><span class="sxs-lookup"><span data-stu-id="200f2-133">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="200f2-134">更新 Office 365 服務端點的內部部署 DNS 服務。</span><span class="sxs-lookup"><span data-stu-id="200f2-134">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="200f2-135">客戶管理的 DNS 專案（指向 Microsoft Cloud Deutschland）必須更新，以指向 Office 365 泛型服務端點。</span><span class="sxs-lookup"><span data-stu-id="200f2-135">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> | <span data-ttu-id="200f2-136">若失敗，可能會導致服務或軟體用戶端失敗。</span><span class="sxs-lookup"><span data-stu-id="200f2-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="200f2-137">協力廠商服務</span><span class="sxs-lookup"><span data-stu-id="200f2-137">Third-party services</span></span>
<span data-ttu-id="200f2-138">**適用于：** 使用協力廠商服務的 Office 365 服務端點的客戶</span><span class="sxs-lookup"><span data-stu-id="200f2-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="200f2-139">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="200f2-139">Step(s)</span></span> | <span data-ttu-id="200f2-140">描述</span><span class="sxs-lookup"><span data-stu-id="200f2-140">Description</span></span> | <span data-ttu-id="200f2-141">影響</span><span class="sxs-lookup"><span data-stu-id="200f2-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="200f2-142">更新合作夥伴及 Office 365 服務端點的協力廠商服務。</span><span class="sxs-lookup"><span data-stu-id="200f2-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="200f2-143">指向 Office 365 德國的協力廠商服務和合作夥伴必須更新，以指向 Office 365 服務端點。</span><span class="sxs-lookup"><span data-stu-id="200f2-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="200f2-144">範例：請重新註冊，以與您的廠商和協力廠商（應用程式的畫廊應用程式版本）搭配使用（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="200f2-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="200f2-145">將所有利用 Graph API 的自訂應用程式指向 `graph.microsoft.de` `graph.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="200f2-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="200f2-146">其他含有已變更端點的 APIs 也必須更新（如果利用）。</span><span class="sxs-lookup"><span data-stu-id="200f2-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="200f2-147">變更所有非協力廠商企業應用程式，以重新導向全球端點。</span><span class="sxs-lookup"><span data-stu-id="200f2-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="200f2-148">必要的動作。</span><span class="sxs-lookup"><span data-stu-id="200f2-148">Required action.</span></span> <span data-ttu-id="200f2-149">若失敗，可能會導致服務或軟體用戶端失敗。</span><span class="sxs-lookup"><span data-stu-id="200f2-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="sharepoint-online"></a><span data-ttu-id="200f2-150">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="200f2-150">SharePoint Online</span></span>
<span data-ttu-id="200f2-151">**適用于**：使用 SharePoint 2013 工作流程的客戶</span><span class="sxs-lookup"><span data-stu-id="200f2-151">**Applies to**: Customers using SharePoint 2013 Workflows</span></span>

| <span data-ttu-id="200f2-152">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="200f2-152">Step(s)</span></span> | <span data-ttu-id="200f2-153">描述</span><span class="sxs-lookup"><span data-stu-id="200f2-153">Description</span></span> | <span data-ttu-id="200f2-154">影響</span><span class="sxs-lookup"><span data-stu-id="200f2-154">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="200f2-155">重新發佈 SharePoint 2013 工作流程。</span><span class="sxs-lookup"><span data-stu-id="200f2-155">Republish SharePoint 2013 workflows.</span></span> | <span data-ttu-id="200f2-156">在遷移前的工作中，我們減少了 SharePoint 2013 工作流程的數目。</span><span class="sxs-lookup"><span data-stu-id="200f2-156">In the pre-migration work, we reduced the number of SharePoint 2013 workflows.</span></span> <span data-ttu-id="200f2-157">現在已完成遷移，客戶便可重新發佈工作流程。</span><span class="sxs-lookup"><span data-stu-id="200f2-157">Now with migration complete, the customer can republish the workflows.</span></span> | <span data-ttu-id="200f2-158">這是必要的動作。</span><span class="sxs-lookup"><span data-stu-id="200f2-158">This is a required action.</span></span> <span data-ttu-id="200f2-159">若失敗，可能會造成使用者混淆和問訊台通話。</span><span class="sxs-lookup"><span data-stu-id="200f2-159">Failure to do so may result in user confusion and help desk calls.</span></span> |
| <span data-ttu-id="200f2-160">透過 Outlook 共用專案</span><span class="sxs-lookup"><span data-stu-id="200f2-160">Share items via Outlook</span></span> | <span data-ttu-id="200f2-161">在租使用者切換後，可在 SharePoint Online 和商務 OneDrive 中透過 Outlook 共用的專案不再運作。</span><span class="sxs-lookup"><span data-stu-id="200f2-161">Sharing items in SharePoint Online and OneDrive for Business via Outlook no longer works after tenant cutover.</span></span> |<ul><li><span data-ttu-id="200f2-162">在 SharePoint 線上和商務 OneDrive 中，您可以透過 Outlook 共用專案。</span><span class="sxs-lookup"><span data-stu-id="200f2-162">In SharePoint Online and OneDrive for Business, you can share items via Outlook.</span></span> <span data-ttu-id="200f2-163">按下 Outlook 按鈕之後，會建立可共用的連結，並將其推入至 Outlook Web App 中的新郵件。</span><span class="sxs-lookup"><span data-stu-id="200f2-163">After pressing the Outlook button, a shareable link is created and pushed into a new message in the Outlook Web App.</span></span></li><li><span data-ttu-id="200f2-164">租使用者轉換後，這種共用方法將無法運作。</span><span class="sxs-lookup"><span data-stu-id="200f2-164">After tenant cutover, this method of sharing won't work.</span></span> <span data-ttu-id="200f2-165">我們承認這是已知的問題。</span><span class="sxs-lookup"><span data-stu-id="200f2-165">We recognize this is a known issue.</span></span> <span data-ttu-id="200f2-166">不過，由於此 Outlook 功能是在被否決的路徑中，因此在完成棄用之前，不會規劃修復此問題。</span><span class="sxs-lookup"><span data-stu-id="200f2-166">However, since this Outlook feature is in the path of deprecation, fixing the issue is not planned until the deprecation is rolled out.</span></span> </li></ul>|
||||

## <a name="exchange-online"></a><span data-ttu-id="200f2-167">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="200f2-167">Exchange Online</span></span>
<span data-ttu-id="200f2-168">**適用于**：使用混合式 Exchange 設定的客戶</span><span class="sxs-lookup"><span data-stu-id="200f2-168">**Applies to**: Customers using a hybrid Exchange configuration</span></span>

| <span data-ttu-id="200f2-169">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="200f2-169">Step(s)</span></span> | <span data-ttu-id="200f2-170">描述</span><span class="sxs-lookup"><span data-stu-id="200f2-170">Description</span></span> | <span data-ttu-id="200f2-171">影響</span><span class="sxs-lookup"><span data-stu-id="200f2-171">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="200f2-172">針對 Office 365 服務，重新執行混合式設定向導 (HCW) 。</span><span class="sxs-lookup"><span data-stu-id="200f2-172">Rerun Hybrid Configuration wizard (HCW) against Office 365 services.</span></span> | <span data-ttu-id="200f2-173">現有的 HCW 設定是為了支援 Microsoft Cloud Deutschland。</span><span class="sxs-lookup"><span data-stu-id="200f2-173">The existing HCW configuration is meant to support Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="200f2-174">隨著 Exchange 服務的遷移完成，我們會將內部部署設定從 Microsoft Cloud Deutschland 中分離出來。</span><span class="sxs-lookup"><span data-stu-id="200f2-174">With migration of Exchange services complete, we decouple on-premises configuration from Microsoft Cloud Deutschland.</span></span> |<ul><li><span data-ttu-id="200f2-175">必要的動作。</span><span class="sxs-lookup"><span data-stu-id="200f2-175">Required action.</span></span> <span data-ttu-id="200f2-176">若失敗，可能會導致服務或軟體用戶端失敗。</span><span class="sxs-lookup"><span data-stu-id="200f2-176">Failure to do so may result in failure of the service or of software clients.</span></span> <span data-ttu-id="200f2-177">在 Exchange 信箱遷移開始 (，但有5天或以上的通知) ，請通知用戶端他們應該停止並刪除其信箱的任何上架或脫離移動。</span><span class="sxs-lookup"><span data-stu-id="200f2-177">Before Exchange mailbox migration begins (with 5 or more days of notice), notify clients that they should stop and delete any onboarding or offboarding moves of their mailboxes.</span></span>  <span data-ttu-id="200f2-178">如果不是，他們會在移動要求中看到錯誤。</span><span class="sxs-lookup"><span data-stu-id="200f2-178">If they don't, they'll see errors in their move requests.</span></span> </li><li><span data-ttu-id="200f2-179">Exchange 信箱遷移完成後，請通知用戶端他們可以繼續上架和脫離移動。</span><span class="sxs-lookup"><span data-stu-id="200f2-179">After Exchange mailbox migration is complete, notify clients that they can resume onboarding and offboarding moves.</span></span> <br> <span data-ttu-id="200f2-180">在從 Microsoft Cloud Deutschland 將 Exchange 遷移至 Office 365 服務時，執行 **MigrationServerAvailabiilty 指令程式**，會執行 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="200f2-180">Running **Test-MigrationServerAvailabiilty**, a PowerShell cmdlet, during migration of Exchange from Microsoft Cloud Deutschland to Office 365 services might not work.</span></span> <span data-ttu-id="200f2-181">不過，遷移完成後，它會正常運作。</span><span class="sxs-lookup"><span data-stu-id="200f2-181">However, it will work properly after migration is complete.</span></span> </li><li><span data-ttu-id="200f2-182">如果在遷移信箱之後，用戶端遇到認證或授權問題，使用者可以執行 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` ，或是使用 Exchange 控制台 (ECP) ，在遷移端點中重新輸入其內部部署系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="200f2-182">If clients run into issues with credentials or authorization after mailboxes are migrated, users can reenter their on-premises administrator credentials in the migration endpoint by running `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)`, or by setting the same by using Exchange Control Panel (ECP).</span></span> </li></ul>|
