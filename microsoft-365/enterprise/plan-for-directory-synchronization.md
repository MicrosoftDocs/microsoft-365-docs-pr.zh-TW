---
title: Microsoft 365 的混合式身分識別及目錄同步處理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: 說明與 Microsoft 365、Active Directory 網域服務清理和 Azure Active Directory Connect 工具的目錄同步處理。
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927541"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="0c312-103">Microsoft 365 的混合式身分識別及目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="0c312-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="0c312-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="0c312-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0c312-105">根據您的業務需求和技術需求，混合式身分識別模型及目錄同步處理對於採用 Microsoft 365 的企業客戶而言是最常見的選擇。</span><span class="sxs-lookup"><span data-stu-id="0c312-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="0c312-106">目錄同步處理可讓您在 Active Directory 網域服務 (AD DS) 中管理身分識別，並且將所有對使用者帳戶、群組和連絡人的更新，同步處理至您的 Microsoft 365 訂閱的 Azure Active Directory (Azure AD) 承租人。</span><span class="sxs-lookup"><span data-stu-id="0c312-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="0c312-107">當 AD DS 使用者帳戶第一次同步處理時，不會自動將其指派給 Microsoft 365 許可證，而且無法存取 Microsoft 365 服務，例如電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0c312-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="0c312-108">您必須先將其指派為使用位置。</span><span class="sxs-lookup"><span data-stu-id="0c312-108">You must first assign them a usage location.</span></span> <span data-ttu-id="0c312-109">然後，透過群組成員資格個別或動態指派授權給這些使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="0c312-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="0c312-110">混合式識別的驗證</span><span class="sxs-lookup"><span data-stu-id="0c312-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="0c312-111">使用混合式識別模型時，有兩種驗證類型：</span><span class="sxs-lookup"><span data-stu-id="0c312-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="0c312-112">管理的驗證</span><span class="sxs-lookup"><span data-stu-id="0c312-112">Managed authentication</span></span>

  <span data-ttu-id="0c312-113">Azure AD 會使用本機儲存的雜湊版本的密碼，或將認證傳送至內部部署 AD DS 來驗證內部部署軟體代理程式，以處理驗證程式。</span><span class="sxs-lookup"><span data-stu-id="0c312-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="0c312-114">同盟驗證</span><span class="sxs-lookup"><span data-stu-id="0c312-114">Federated authentication</span></span>

  <span data-ttu-id="0c312-115">Azure AD 會將要求驗證的用戶端電腦重新導向至另一個身分識別提供者。</span><span class="sxs-lookup"><span data-stu-id="0c312-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="0c312-116">管理的驗證</span><span class="sxs-lookup"><span data-stu-id="0c312-116">Managed authentication</span></span>

<span data-ttu-id="0c312-117">受管理的驗證類型有兩種：</span><span class="sxs-lookup"><span data-stu-id="0c312-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="0c312-118">密碼雜湊同步處理 (PHS) </span><span class="sxs-lookup"><span data-stu-id="0c312-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="0c312-119">Azure AD 會自行執行驗證。</span><span class="sxs-lookup"><span data-stu-id="0c312-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="0c312-120">傳遞驗證 (PTA)</span><span class="sxs-lookup"><span data-stu-id="0c312-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="0c312-121">Azure AD 具有 AD DS 執行驗證。</span><span class="sxs-lookup"><span data-stu-id="0c312-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="0c312-122">密碼雜湊同步處理 (PHS) </span><span class="sxs-lookup"><span data-stu-id="0c312-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="0c312-123">透過 PHS，您可以將 AD DS 使用者帳戶與 Microsoft 365 同步處理，並管理內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="0c312-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="0c312-124">使用者密碼的雜湊會從您的 AD DS 同步處理到 Azure AD，讓使用者在內部部署和雲端都有相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="0c312-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="0c312-125">這是在 Azure AD 中啟用 AD DS 身分識別驗證的最簡單方式。</span><span class="sxs-lookup"><span data-stu-id="0c312-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![密碼雜湊同步處理 (PHS) ](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="0c312-127">當密碼變更或重設為內部部署時，新的密碼雜湊會同步處理至 Azure AD，這樣您的使用者就可以在雲端資源和內部部署資源中永遠使用相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="0c312-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="0c312-128">使用者密碼永遠不會以明文形式傳送至 Azure AD 或儲存在 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="0c312-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="0c312-129">不論選取哪一種驗證方法，Azure AD 的某些精品功能（例如身分識別保護）都需要 PHS。</span><span class="sxs-lookup"><span data-stu-id="0c312-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="0c312-130">若要深入瞭解，請參閱 [選擇正確的驗證方法](/azure/active-directory/hybrid/choose-ad-authn) 。</span><span class="sxs-lookup"><span data-stu-id="0c312-130">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="0c312-131">傳遞驗證 (PTA)</span><span class="sxs-lookup"><span data-stu-id="0c312-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="0c312-132">PTA 提供使用一或多個內部部署伺服器上執行的軟體代理程式，直接向您的 AD DS 驗證使用者，以進行 Azure AD 驗證服務的簡單密碼驗證。</span><span class="sxs-lookup"><span data-stu-id="0c312-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="0c312-133">透過 PTA，您可以同步處理 AD DS 使用者帳戶與 Microsoft 365，並管理內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="0c312-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![傳遞驗證 (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="0c312-135">PTA 可讓您的使用者使用內部部署帳戶和密碼，登入內部部署和 Microsoft 365 資源及應用程式。</span><span class="sxs-lookup"><span data-stu-id="0c312-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="0c312-136">此設定會直接驗證使用者密碼與您的內部部署 AD DS，而不會在 Azure AD 中儲存密碼雜湊。</span><span class="sxs-lookup"><span data-stu-id="0c312-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="0c312-137">PTA 也適用于具有安全性需求的組織，以立即強制執行內部部署使用者帳戶狀態、密碼原則和登入時間。</span><span class="sxs-lookup"><span data-stu-id="0c312-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="0c312-138">若要深入瞭解，請參閱 [選擇正確的驗證方法](/azure/active-directory/hybrid/choose-ad-authn) 。</span><span class="sxs-lookup"><span data-stu-id="0c312-138">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="0c312-139">同盟驗證</span><span class="sxs-lookup"><span data-stu-id="0c312-139">Federated authentication</span></span>

<span data-ttu-id="0c312-140">同盟驗證主要針對大型企業組織，其驗證需求較複雜。</span><span class="sxs-lookup"><span data-stu-id="0c312-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="0c312-141">AD DS 身分識別與 Microsoft 365 同步處理，而且使用者帳戶是在內部部署管理。</span><span class="sxs-lookup"><span data-stu-id="0c312-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="0c312-142">透過同盟驗證，使用者在內部部署和雲端都有相同的密碼，而且不需要重新登入即可使用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0c312-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="0c312-143">同盟驗證可支援其他驗證需求，例如智慧卡型驗證或協力廠商的多重要素驗證，而且在組織具備 Azure AD 本身不支援的驗證需求時，通常需要使用。</span><span class="sxs-lookup"><span data-stu-id="0c312-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="0c312-144">若要深入瞭解，請參閱 [選擇正確的驗證方法](/azure/active-directory/hybrid/choose-ad-authn) 。</span><span class="sxs-lookup"><span data-stu-id="0c312-144">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="0c312-145">協力廠商驗證和身分識別提供者</span><span class="sxs-lookup"><span data-stu-id="0c312-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="0c312-146">內部部署目錄物件可能會同步處理至 Microsoft 365，而雲端資源存取主要是由協力廠商身分識別提供者 (IdP) 所管理。</span><span class="sxs-lookup"><span data-stu-id="0c312-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="0c312-147">如果您的組織使用協力廠商同盟解決方案，您可以將協力廠商同盟解決方案與 Azure AD 相容，以供 Microsoft 365 的解決方案進行登錄。</span><span class="sxs-lookup"><span data-stu-id="0c312-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="0c312-148">請參閱 [AZURE AD federation 相容性清單](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) 以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="0c312-148">See the [Azure AD federation compatibility list](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="0c312-149">AD DS 準備</span><span class="sxs-lookup"><span data-stu-id="0c312-149">AD DS Preparation</span></span>

<span data-ttu-id="0c312-150">若要協助確保透過同步處理順利轉換至 Microsoft 365，您必須先準備您的 AD DS 樹系，再開始 Microsoft 365 目錄同步部署。</span><span class="sxs-lookup"><span data-stu-id="0c312-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="0c312-151">您的目錄準備工作應該著重于下列工作：</span><span class="sxs-lookup"><span data-stu-id="0c312-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="0c312-152">移除重複的 **proxyAddress** 和 **userPrincipalName** 屬性。</span><span class="sxs-lookup"><span data-stu-id="0c312-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="0c312-153">使用有效的 **userPrincipalName** 屬性，更新空白及不正確 **userPrincipalName** 屬性。</span><span class="sxs-lookup"><span data-stu-id="0c312-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="0c312-154">移除 **givenName**、姓 ( **sn** ) 、 **sAMAccountName**、 **displayName**、 **mail**、 **proxyAddresses**、 **mailNickname** 及 **userPrincipalName** 屬性中的無效且可疑的字元。</span><span class="sxs-lookup"><span data-stu-id="0c312-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="0c312-155">如需準備屬性的詳細資訊，請參閱 [由 Azure Active Directory 同步處理工具同步處理的屬性清單](https://go.microsoft.com/fwlink/p/?LinkId=396719)。</span><span class="sxs-lookup"><span data-stu-id="0c312-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c312-156">這些是 Azure AD Connect 同步處理的相同屬性。</span><span class="sxs-lookup"><span data-stu-id="0c312-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="0c312-157">多樹系部署的考慮</span><span class="sxs-lookup"><span data-stu-id="0c312-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="0c312-158">若為多個樹系和 SSO 選項，請使用 [AZURE AD Connect 的自訂安裝](/azure/active-directory/hybrid/how-to-connect-install-custom)。</span><span class="sxs-lookup"><span data-stu-id="0c312-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>
  
<span data-ttu-id="0c312-159">如果您的組織有多個樹系用於驗證 (登入樹系) ，我們強烈建議下列事項：</span><span class="sxs-lookup"><span data-stu-id="0c312-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="0c312-160">**請考慮合併您的樹系。**</span><span class="sxs-lookup"><span data-stu-id="0c312-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="0c312-161">一般說來，維護多個樹系需要額外的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="0c312-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="0c312-162">除非您的組織有規定個別樹系需求的安全性限制，否則請考慮簡化您的內部部署環境。</span><span class="sxs-lookup"><span data-stu-id="0c312-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="0c312-163">**僅在您的主要登入樹系中使用。**</span><span class="sxs-lookup"><span data-stu-id="0c312-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="0c312-164">請考慮只在您的主要登入樹系中部署 Microsoft 365，以進行初次展示 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0c312-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="0c312-165">如果您無法合併多樹系 AD DS 部署，或正在使用其他目錄服務來管理身分識別，您可以使用 Microsoft 或協力廠商的說明同步處理這些身分識別。</span><span class="sxs-lookup"><span data-stu-id="0c312-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="0c312-166">如需詳細資訊，請參閱 [AZURE AD Connect 的拓撲](/azure/active-directory/hybrid/plan-connect-topologies) 。</span><span class="sxs-lookup"><span data-stu-id="0c312-166">See [Topologies for Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="0c312-167">依存于目錄同步處理的功能</span><span class="sxs-lookup"><span data-stu-id="0c312-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="0c312-168">下列功能需要目錄同步處理：</span><span class="sxs-lookup"><span data-stu-id="0c312-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="0c312-169"> (SSO) 的 Azure AD 無縫單一 Sign-On</span><span class="sxs-lookup"><span data-stu-id="0c312-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="0c312-170">Skype 共存</span><span class="sxs-lookup"><span data-stu-id="0c312-170">Skype coexistence</span></span>
- <span data-ttu-id="0c312-171">Exchange 混合式部署，包括：</span><span class="sxs-lookup"><span data-stu-id="0c312-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="0c312-172">在您的內部部署 Exchange 環境與 Microsoft 365 之間 (GAL) 的完全共用全域通訊清單。</span><span class="sxs-lookup"><span data-stu-id="0c312-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="0c312-173">同步處理來自不同郵件系統的 GAL 資訊。</span><span class="sxs-lookup"><span data-stu-id="0c312-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="0c312-174">可在 Microsoft 365 服務產品中新增及移除使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="0c312-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="0c312-175">這需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="0c312-175">This requires the following:</span></span>
  - <span data-ttu-id="0c312-176">在目錄同步處理設定期間，必須設定雙向同步處理。</span><span class="sxs-lookup"><span data-stu-id="0c312-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="0c312-177">根據預設，目錄同步處理工具只會將目錄資訊寫入雲端。</span><span class="sxs-lookup"><span data-stu-id="0c312-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="0c312-178">當您設定雙向同步處理時，您可以啟用寫回功能，使有限數目的物件屬性從雲端複製，然後再將其寫入您的本機 AD DS。</span><span class="sxs-lookup"><span data-stu-id="0c312-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="0c312-179">回寫也稱為 Exchange 混合模式。</span><span class="sxs-lookup"><span data-stu-id="0c312-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="0c312-180">內部部署 Exchange 混合式部署</span><span class="sxs-lookup"><span data-stu-id="0c312-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="0c312-181">將部分使用者信箱移至 Microsoft 365 的功能，同時保留其他使用者信箱的內部部署。</span><span class="sxs-lookup"><span data-stu-id="0c312-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="0c312-182">安全寄件者和封鎖的寄件者內部部署會複製到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0c312-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="0c312-183">基本委派和代理傳送電子郵件功能。</span><span class="sxs-lookup"><span data-stu-id="0c312-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="0c312-184">您有整合式內部部署智慧卡或多重要素驗證解決方案。</span><span class="sxs-lookup"><span data-stu-id="0c312-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="0c312-185">同步處理相片、縮圖、會議室及安全性群組</span><span class="sxs-lookup"><span data-stu-id="0c312-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="0c312-186">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0c312-186">Next step</span></span>

<span data-ttu-id="0c312-187">當您準備好部署混合式身分識別時，請參閱 [prepare for 目錄同步](prepare-for-directory-synchronization.md)處理。</span><span class="sxs-lookup"><span data-stu-id="0c312-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
