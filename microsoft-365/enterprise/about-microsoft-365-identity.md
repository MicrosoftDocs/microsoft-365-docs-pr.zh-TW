---
title: Microsoft 365 身分識別模型和 Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 06/09/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: 瞭解如何使用僅限雲端或混合式身分識別模型，在 Microsoft 365 中管理 Azure AD 使用者身分識別服務。
ms.openlocfilehash: d91e14f678e487365805b024e4025e9a39db0c2c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688836"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="c7cba-103">Microsoft 365 身分識別模型和 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c7cba-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="c7cba-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="c7cba-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c7cba-105">Microsoft 365 使用 Azure Active Directory (Azure AD) （包含在您的 Microsoft 365 訂閱中的雲端架構使用者身分識別和驗證服務）來管理 Microsoft 365 的身分識別和驗證。</span><span class="sxs-lookup"><span data-stu-id="c7cba-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="c7cba-106">正確設定您的身分識別基礎結構，對管理組織的 Microsoft 365 使用者存取和許可權而言是很重要的。</span><span class="sxs-lookup"><span data-stu-id="c7cba-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="c7cba-107">開始之前，請觀看這段影片，以大略了解身分識別模型和 Microsoft 365 的驗證。</span><span class="sxs-lookup"><span data-stu-id="c7cba-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="c7cba-108">您第一次規劃選擇是 Microsoft 365 身分識別模型。</span><span class="sxs-lookup"><span data-stu-id="c7cba-108">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="c7cba-109">Microsoft 365 身分識別模型</span><span class="sxs-lookup"><span data-stu-id="c7cba-109">Microsoft 365 identity models</span></span>

<span data-ttu-id="c7cba-110">若要規劃使用者帳戶，您必須先瞭解 Microsoft 365 中的兩個身分識別模型。</span><span class="sxs-lookup"><span data-stu-id="c7cba-110">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="c7cba-111">您只能在雲端維護組織的身分識別，也可以維護內部部署 Active Directory 網域服務 (AD DS) 身分識別，並在使用者存取 Microsoft 365 雲端服務時，使用這些身分驗證。</span><span class="sxs-lookup"><span data-stu-id="c7cba-111">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="c7cba-112">以下是兩種身分識別類型及其最大和優點。</span><span class="sxs-lookup"><span data-stu-id="c7cba-112">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="c7cba-113">屬性</span><span class="sxs-lookup"><span data-stu-id="c7cba-113">Attribute</span></span> | <span data-ttu-id="c7cba-114">僅雲端身分識別</span><span class="sxs-lookup"><span data-stu-id="c7cba-114">Cloud-only identity</span></span> | <span data-ttu-id="c7cba-115">混合式身分識別</span><span class="sxs-lookup"><span data-stu-id="c7cba-115">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="c7cba-116">**定義**</span><span class="sxs-lookup"><span data-stu-id="c7cba-116">**Definition**</span></span> | <span data-ttu-id="c7cba-117">使用者帳戶只存在於 Microsoft 365 訂閱的 Azure AD 租使用者中。</span><span class="sxs-lookup"><span data-stu-id="c7cba-117">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="c7cba-118">使用者帳戶存在於 AD DS 中，而且副本也位於您的 Microsoft 365 訂閱的 Azure AD 租使用者中。</span><span class="sxs-lookup"><span data-stu-id="c7cba-118">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="c7cba-119">Azure AD 中的使用者帳戶可能也包含已雜湊的 AD DS 使用者帳戶密碼的雜湊版本。</span><span class="sxs-lookup"><span data-stu-id="c7cba-119">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="c7cba-120">**Microsoft 365 如何驗證使用者認證**</span><span class="sxs-lookup"><span data-stu-id="c7cba-120">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="c7cba-121">Microsoft 365 訂閱的 Azure AD 租使用者使用雲端身分識別帳戶來執行驗證。</span><span class="sxs-lookup"><span data-stu-id="c7cba-121">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="c7cba-122">Microsoft 365 訂閱的 Azure AD 租使用者可以處理驗證程式，也可以將使用者重新導向至另一個身分識別提供者。</span><span class="sxs-lookup"><span data-stu-id="c7cba-122">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="c7cba-123">**適用**</span><span class="sxs-lookup"><span data-stu-id="c7cba-123">**Best for**</span></span> | <span data-ttu-id="c7cba-124">不需要內部部署 AD DS 的組織。</span><span class="sxs-lookup"><span data-stu-id="c7cba-124">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="c7cba-125">使用 AD DS 或其他身分識別提供者的組織。</span><span class="sxs-lookup"><span data-stu-id="c7cba-125">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="c7cba-126">**最大好處**</span><span class="sxs-lookup"><span data-stu-id="c7cba-126">**Greatest benefit**</span></span> | <span data-ttu-id="c7cba-127">便於使用。</span><span class="sxs-lookup"><span data-stu-id="c7cba-127">Simple to use.</span></span> <span data-ttu-id="c7cba-128">不需要額外的目錄工具或伺服器。</span><span class="sxs-lookup"><span data-stu-id="c7cba-128">No extra directory tools or servers required.</span></span> | <span data-ttu-id="c7cba-129">當存取內部部署或雲端式資源時，使用者可以使用相同的認證。</span><span class="sxs-lookup"><span data-stu-id="c7cba-129">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="c7cba-130">僅雲端身分識別</span><span class="sxs-lookup"><span data-stu-id="c7cba-130">Cloud-only identity</span></span>

<span data-ttu-id="c7cba-131">僅限雲端的身分識別只會使用存在於 Azure AD 中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c7cba-131">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="c7cba-132">雲端身分識別通常是由沒有內部部署伺服器的小型組織使用，或是不使用 AD DS 來管理本機身分識別。</span><span class="sxs-lookup"><span data-stu-id="c7cba-132">Cloud identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="c7cba-133">以下是僅限雲端身分識別的基本元件。</span><span class="sxs-lookup"><span data-stu-id="c7cba-133">Here are the basic components of cloud-only identity.</span></span>
 
![僅限雲端身分識別的基本元件](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="c7cba-135">內部部署和遠端 (線上) 使用者可以使用其 Azure AD 使用者帳戶和密碼來存取 Microsoft 365 雲端服務。</span><span class="sxs-lookup"><span data-stu-id="c7cba-135">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="c7cba-136">Azure AD 會根據其儲存的使用者帳戶和密碼驗證使用者認證。</span><span class="sxs-lookup"><span data-stu-id="c7cba-136">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="c7cba-137">系統管理</span><span class="sxs-lookup"><span data-stu-id="c7cba-137">Administration</span></span>
<span data-ttu-id="c7cba-138">因為使用者帳戶只會儲存在 Azure AD 中，您可以使用 [Microsoft 365 系統管理中心](https://admin.microsoft.com) 和 [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)之類的工具來管理雲端身分識別。</span><span class="sxs-lookup"><span data-stu-id="c7cba-138">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](https://admin.microsoft.com) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="c7cba-139">混合式身分識別</span><span class="sxs-lookup"><span data-stu-id="c7cba-139">Hybrid identity</span></span>

<span data-ttu-id="c7cba-140">混合式身分識別使用內部部署 AD DS 中的帳戶，並在 Microsoft 365 訂閱的 Azure AD 租使用者中擁有複本。</span><span class="sxs-lookup"><span data-stu-id="c7cba-140">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="c7cba-141">不過，大部分的變更只流向單一方式。</span><span class="sxs-lookup"><span data-stu-id="c7cba-141">However, most changes only flow one way.</span></span> <span data-ttu-id="c7cba-142">您對 AD DS 使用者帳戶所做的變更會同步處理至其 Azure AD 中的副本。</span><span class="sxs-lookup"><span data-stu-id="c7cba-142">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="c7cba-143">但是，在 Azure AD 中對雲端型帳戶所做的變更（例如新的使用者帳戶）不會與 AD DS 同步。</span><span class="sxs-lookup"><span data-stu-id="c7cba-143">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="c7cba-144">Azure AD Connect 提供進行中的帳戶同步處理。</span><span class="sxs-lookup"><span data-stu-id="c7cba-144">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="c7cba-145">它會在內部部署伺服器上執行，檢查 AD DS 中的變更，並將這些變更轉送到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="c7cba-145">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="c7cba-146">Azure AD Connect 可讓您篩選要同步處理的帳戶，以及是否同步處理已雜湊的版本的使用者密碼，稱為密碼雜湊同步處理 (PHS) 。</span><span class="sxs-lookup"><span data-stu-id="c7cba-146">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="c7cba-147">當您執行混合式身分識別時，您的內部部署 AD DS 是帳戶資訊的授權來源。</span><span class="sxs-lookup"><span data-stu-id="c7cba-147">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="c7cba-148">這表示您執行大部分內部部署的管理工作，然後同步處理到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="c7cba-148">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="c7cba-149">以下是混合式身分識別的元件。</span><span class="sxs-lookup"><span data-stu-id="c7cba-149">Here are the components of hybrid identity.</span></span>

![混合身分識別的元件](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="c7cba-151">Azure AD 租使用者具有 AD DS 帳戶的副本。</span><span class="sxs-lookup"><span data-stu-id="c7cba-151">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="c7cba-152">在此設定中，內部部署和遠端使用者都會存取 Microsoft 365 雲端服務，以針對 Azure AD 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c7cba-152">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="c7cba-153">您永遠需要使用 Azure AD Connect，以同步處理混合身分識別的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c7cba-153">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="c7cba-154">您需要 Azure AD 中已同步處理的使用者帳戶，以執行授權指派和群組管理、設定許可權，以及其他涉及使用者帳戶的系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="c7cba-154">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="c7cba-155">系統管理</span><span class="sxs-lookup"><span data-stu-id="c7cba-155">Administration</span></span>

<span data-ttu-id="c7cba-156">由於原始和權威性的使用者帳戶是儲存在內部部署 AD DS 中，因此您可以使用與 AD DS 相同的工具（例如 Active Directory 使用者和電腦工具）來管理您的身分識別。</span><span class="sxs-lookup"><span data-stu-id="c7cba-156">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as AD DS, such as the Active Directory Users and Computers tool.</span></span> 

<span data-ttu-id="c7cba-157">您不會使用 Microsoft 365 系統管理中心或 Microsoft 365 的 PowerShell 來管理 Azure AD 中已同步的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c7cba-157">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="c7cba-158">下一步</span><span class="sxs-lookup"><span data-stu-id="c7cba-158">Next step</span></span>

<span data-ttu-id="c7cba-159">如果您需要僅限雲端的身分識別模型，請參閱 [僅限雲端身分識別](cloud-only-identities.md)。</span><span class="sxs-lookup"><span data-stu-id="c7cba-159">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="c7cba-160">如果您需要混合式身分識別模型，請參閱 [混合身分識別](plan-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="c7cba-160">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="c7cba-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c7cba-161">See also</span></span>

[<span data-ttu-id="c7cba-162">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="c7cba-162">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)