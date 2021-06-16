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
description: 摘要：從 microsoft cloud (德國移至 microsoft cloud Deutschland 後的後續活動：從 microsoft cloud) 到新德文 datacenter 區域中 Office 365 服務。
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930412"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="55bb5-103">從 Microsoft Cloud Deutschland 進行遷移後的遷移後活動</span><span class="sxs-lookup"><span data-stu-id="55bb5-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="55bb5-104">下列各節會在從 microsoft 雲端 (德國 Deutschland) 到新德文 datacenter 區域中的 Office 365 服務後，提供多項服務的遷移後活動。</span><span class="sxs-lookup"><span data-stu-id="55bb5-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="55bb5-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="55bb5-105">Azure AD</span></span>
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

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="55bb5-106">Azure AD 同盟驗證與 AD FS</span><span class="sxs-lookup"><span data-stu-id="55bb5-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="55bb5-107">**適用于：** 所有使用同盟驗證與 AD FS 的客戶</span><span class="sxs-lookup"><span data-stu-id="55bb5-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="55bb5-108">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="55bb5-108">Step(s)</span></span> | <span data-ttu-id="55bb5-109">描述</span><span class="sxs-lookup"><span data-stu-id="55bb5-109">Description</span></span> | <span data-ttu-id="55bb5-110">影響</span><span class="sxs-lookup"><span data-stu-id="55bb5-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="55bb5-111">從 Microsoft Cloud Deutschland AD FS 移除信賴憑證者信任。</span><span class="sxs-lookup"><span data-stu-id="55bb5-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="55bb5-112">在完成轉換至 Azure AD 後，組織會完全使用 Office 365 服務，而且不再連接至 Microsoft 雲端 Deutschland。</span><span class="sxs-lookup"><span data-stu-id="55bb5-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="55bb5-113">此時，客戶需要移除對 Microsoft Cloud Deutschland 端點的信賴憑證者信任。</span><span class="sxs-lookup"><span data-stu-id="55bb5-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="55bb5-114">只有在客戶的任何應用程式都指向 Microsoft Cloud Deutschland 端點時，當 Azure AD (IdP) 時，才會執行此動作。</span><span class="sxs-lookup"><span data-stu-id="55bb5-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="55bb5-115">同盟驗證組織</span><span class="sxs-lookup"><span data-stu-id="55bb5-115">Federated Authentication organizations</span></span> | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="55bb5-116">群組核准</span><span class="sxs-lookup"><span data-stu-id="55bb5-116">Group approvals</span></span>
<span data-ttu-id="55bb5-117">**適用于：** 在遷移前30天內，未核准 Azure AD 群組核准要求的使用者</span><span class="sxs-lookup"><span data-stu-id="55bb5-117">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="55bb5-118">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="55bb5-118">Step(s)</span></span> | <span data-ttu-id="55bb5-119">描述</span><span class="sxs-lookup"><span data-stu-id="55bb5-119">Description</span></span> | <span data-ttu-id="55bb5-120">影響</span><span class="sxs-lookup"><span data-stu-id="55bb5-120">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="55bb5-121">在過去30天內加入 Azure AD 群組的要求若未獲核准原始要求，將需要重新要求遷移。</span><span class="sxs-lookup"><span data-stu-id="55bb5-121">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="55bb5-122">若使用者在遷移前的30天內未獲核准，使用者的客戶將需要使用「存取面板」提交要求，以加入 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="55bb5-122">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="55bb5-123">最終使用者：</span><span class="sxs-lookup"><span data-stu-id="55bb5-123">As an end-user:</span></span> <ol><li><span data-ttu-id="55bb5-124">流覽至 [Access 面板](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</span><span class="sxs-lookup"><span data-stu-id="55bb5-124">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="55bb5-125">尋找在遷移前30天內，成員核准已擱置的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="55bb5-125">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="55bb5-126">要求重新加入 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="55bb5-126">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="55bb5-127">在遷移後，若要求加入超過30天的群組，將無法進行核准。</span><span class="sxs-lookup"><span data-stu-id="55bb5-127">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

## <a name="custom-dns-updates"></a><span data-ttu-id="55bb5-128">自訂 DNS 更新</span><span class="sxs-lookup"><span data-stu-id="55bb5-128">Custom DNS updates</span></span>
<span data-ttu-id="55bb5-129">**適用于：**  所有客戶都管理自己的 DNS 區域</span><span class="sxs-lookup"><span data-stu-id="55bb5-129">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="55bb5-130">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="55bb5-130">Step(s)</span></span> | <span data-ttu-id="55bb5-131">描述</span><span class="sxs-lookup"><span data-stu-id="55bb5-131">Description</span></span> | <span data-ttu-id="55bb5-132">影響</span><span class="sxs-lookup"><span data-stu-id="55bb5-132">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="55bb5-133">更新 Office 365 服務端點的內部部署 DNS 服務。</span><span class="sxs-lookup"><span data-stu-id="55bb5-133">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="55bb5-134">客戶管理的 DNS 專案（指向 Microsoft Cloud Deutschland）必須更新，以指向 Office 365 泛型服務端點。</span><span class="sxs-lookup"><span data-stu-id="55bb5-134">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> <span data-ttu-id="55bb5-135">請參閱[Microsoft 365 系統管理中心的網域](https://admin.microsoft.com/Adminportal/Home#/Domains)，並在您的 DNS 設定中套用變更。</span><span class="sxs-lookup"><span data-stu-id="55bb5-135">Please refer to [Domains in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/Domains) and apply the changes in your DNS configuration.</span></span> | <span data-ttu-id="55bb5-136">若失敗，可能會導致服務或軟體用戶端失敗。</span><span class="sxs-lookup"><span data-stu-id="55bb5-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="55bb5-137">協力廠商服務</span><span class="sxs-lookup"><span data-stu-id="55bb5-137">Third-party services</span></span>
<span data-ttu-id="55bb5-138">**適用于：** 使用協力廠商服務做為 Office 365 服務端點的客戶</span><span class="sxs-lookup"><span data-stu-id="55bb5-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="55bb5-139">步驟 (s) </span><span class="sxs-lookup"><span data-stu-id="55bb5-139">Step(s)</span></span> | <span data-ttu-id="55bb5-140">描述</span><span class="sxs-lookup"><span data-stu-id="55bb5-140">Description</span></span> | <span data-ttu-id="55bb5-141">影響</span><span class="sxs-lookup"><span data-stu-id="55bb5-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="55bb5-142">更新合作夥伴和協力廠商的 Office 365 服務端點服務。</span><span class="sxs-lookup"><span data-stu-id="55bb5-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="55bb5-143">指向 Office 365 德國的協力廠商服務和合作夥伴必須更新，以指向 Office 365 服務端點。</span><span class="sxs-lookup"><span data-stu-id="55bb5-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="55bb5-144">範例：請重新註冊，以與您的廠商和協力廠商（應用程式的畫廊應用程式版本）搭配使用（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="55bb5-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="55bb5-145">將所有利用 Graph API 的自訂應用程式指向 `graph.microsoft.de` `graph.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="55bb5-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="55bb5-146">其他含有已變更端點的 APIs 也必須更新（如果利用）。</span><span class="sxs-lookup"><span data-stu-id="55bb5-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="55bb5-147">變更所有非協力廠商企業應用程式，以重新導向全球端點。</span><span class="sxs-lookup"><span data-stu-id="55bb5-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="55bb5-148">必要的動作。</span><span class="sxs-lookup"><span data-stu-id="55bb5-148">Required action.</span></span> <span data-ttu-id="55bb5-149">若失敗，可能會導致服務或軟體用戶端失敗。</span><span class="sxs-lookup"><span data-stu-id="55bb5-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||