---
title: 步驟 3： Microsoft 365 for enterprise 承租人的身分識別
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: 部署適用于 Microsoft 365 承租人的正確身分識別模型，並強制執行強使用者登入。
ms.openlocfilehash: 40ea67d9b30a385e36af45f57bd33906c10e495d
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908494"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="f989e-104">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="f989e-104">Step 3.</span></span> <span data-ttu-id="f989e-105">Microsoft 365 for enterprise 承租人的身分識別</span><span class="sxs-lookup"><span data-stu-id="f989e-105">Identity for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="f989e-106">您的 Microsoft 365 租使用者包含 Azure Active Directory (Azure AD) 租使用者管理登入的身分識別和驗證。正確設定您的身分識別基礎結構，對管理組織的 Microsoft 365 使用者存取和許可權而言是很重要的。</span><span class="sxs-lookup"><span data-stu-id="f989e-106">Your Microsoft 365 tenant includes an Azure Active Directory (Azure AD) tenant to manage identities and authentication for sign-ins. Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

## <a name="cloud-only-vs-hybrid"></a><span data-ttu-id="f989e-107">僅限雲端與混合</span><span class="sxs-lookup"><span data-stu-id="f989e-107">Cloud-only vs. hybrid</span></span>

<span data-ttu-id="f989e-108">以下是這兩種類型的身分識別模型及其最大和優點。</span><span class="sxs-lookup"><span data-stu-id="f989e-108">Here are the two types of identity models and their best fit and benefits.</span></span>


| <span data-ttu-id="f989e-109">Model</span><span class="sxs-lookup"><span data-stu-id="f989e-109">Model</span></span> | <span data-ttu-id="f989e-110">說明</span><span class="sxs-lookup"><span data-stu-id="f989e-110">Description</span></span> | <span data-ttu-id="f989e-111">Microsoft 365 如何驗證使用者認證</span><span class="sxs-lookup"><span data-stu-id="f989e-111">How Microsoft 365 authenticates user credentials</span></span> | <span data-ttu-id="f989e-112">適用</span><span class="sxs-lookup"><span data-stu-id="f989e-112">Best for</span></span> | <span data-ttu-id="f989e-113">最大好處</span><span class="sxs-lookup"><span data-stu-id="f989e-113">Greatest benefit</span></span> |
|:-------|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f989e-114">僅雲端</span><span class="sxs-lookup"><span data-stu-id="f989e-114">Cloud-only</span></span> | <span data-ttu-id="f989e-115">使用者帳戶只存在於 Microsoft 365 租使用者的 Azure AD 租使用者中。</span><span class="sxs-lookup"><span data-stu-id="f989e-115">User account only exists in the Azure AD tenant for your Microsoft 365 tenant.</span></span> | <span data-ttu-id="f989e-116">Microsoft 365 租使用者的 Azure AD 租使用者使用雲端身分識別帳戶執行驗證。</span><span class="sxs-lookup"><span data-stu-id="f989e-116">The Azure AD tenant for your Microsoft 365 tenant performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="f989e-117">不需要內部部署 AD DS 的組織。</span><span class="sxs-lookup"><span data-stu-id="f989e-117">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="f989e-118">便於使用。</span><span class="sxs-lookup"><span data-stu-id="f989e-118">Simple to use.</span></span> <span data-ttu-id="f989e-119">不需要額外的目錄工具或伺服器。</span><span class="sxs-lookup"><span data-stu-id="f989e-119">No extra directory tools or servers required.</span></span> |
| <span data-ttu-id="f989e-120">混合式</span><span class="sxs-lookup"><span data-stu-id="f989e-120">Hybrid</span></span> |  <span data-ttu-id="f989e-121">使用者帳戶存在於內部部署 Active Directory 網域服務中 (AD DS) 而且副本也位於您的 Microsoft 365 租使用者的 Azure AD 租使用者中。</span><span class="sxs-lookup"><span data-stu-id="f989e-121">User account exists in your on-premises Active Directory Domain Services (AD DS) and a copy is also in the Azure AD tenant for your Microsoft 365 tenant.</span></span> <span data-ttu-id="f989e-122">Azure AD Connect 會在內部部署伺服器上執行，以將 AD DS 變更同步處理至您的 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="f989e-122">Azure AD Connect runs on an on-premises server to synchronize AD DS changes to your Azure AD tenant.</span></span> <span data-ttu-id="f989e-123">Azure AD 中的使用者帳戶可能也包含已雜湊的 AD DS 使用者帳戶密碼的雜湊版本。</span><span class="sxs-lookup"><span data-stu-id="f989e-123">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> | <span data-ttu-id="f989e-124">Microsoft 365 租使用者的 Azure AD 租使用者可以處理驗證程式，或將使用者重新導向至另一個身分識別提供者。</span><span class="sxs-lookup"><span data-stu-id="f989e-124">The Azure AD tenant for your Microsoft 365 tenant either handles the authentication process or redirects the user to another identity provider.</span></span> | <span data-ttu-id="f989e-125">使用 AD DS 或其他身分識別提供者的組織。</span><span class="sxs-lookup"><span data-stu-id="f989e-125">Organizations using AD DS or another identity provider.</span></span> | <span data-ttu-id="f989e-126">當存取內部部署或雲端式資源時，使用者可以使用相同的認證。</span><span class="sxs-lookup"><span data-stu-id="f989e-126">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||||

<span data-ttu-id="f989e-127">以下是僅限雲端身分識別的基本元件。</span><span class="sxs-lookup"><span data-stu-id="f989e-127">Here are the basic components of cloud-only identity.</span></span>
 
![僅限雲端身分識別的基本元件](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="f989e-129">在此圖中，內部部署和遠端使用者在其 Microsoft 365 租使用者的 Azure AD 租使用者中，以帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="f989e-129">In this illustration, on-premises and remote users sign in with accounts in the Azure AD tenant of their Microsoft 365 tenant.</span></span>

<span data-ttu-id="f989e-130">以下是混合式身分識別的基本元件。</span><span class="sxs-lookup"><span data-stu-id="f989e-130">Here are the basic components of hybrid identity.</span></span>

![混合身分識別的基本元件](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="f989e-132">在此圖中，內部部署和遠端使用者登入其 Microsoft 365 租使用者，並在 Azure AD 租使用者中使用已從其內部部署 AD DS 複製的帳戶。</span><span class="sxs-lookup"><span data-stu-id="f989e-132">In this illustration, on-premises and remote users sign in to their Microsoft 365 tenant with accounts in the Azure AD tenant that have been copied from their on-premises AD DS.</span></span>

## <a name="synchronizing-your-on-premises-ad-ds"></a><span data-ttu-id="f989e-133">同步處理您的內部部署 AD DS</span><span class="sxs-lookup"><span data-stu-id="f989e-133">Synchronizing your on-premises AD DS</span></span>

<span data-ttu-id="f989e-134">根據您的業務需求和技術需求，混合式身分識別模型及目錄同步處理對於採用 Microsoft 365 的企業客戶而言是最常見的選擇。</span><span class="sxs-lookup"><span data-stu-id="f989e-134">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="f989e-135">目錄同步處理可讓您在 AD DS 中管理身分識別，並且將使用者帳戶、群組和連絡人的所有更新，同步處理至您的 Microsoft 365 租使用者的 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="f989e-135">Directory synchronization allows you to manage identities in your AD DS and all updates to user accounts, groups, and contacts are synchronized to the Azure AD tenant of your Microsoft 365 tenant.</span></span>

>[!Note]
><span data-ttu-id="f989e-136">當 AD DS 使用者帳戶第一次同步處理時，不會自動將其指派給 Microsoft 365 許可證，而且無法存取 Microsoft 365 服務，例如電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f989e-136">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="f989e-137">您必須先將其指派為使用位置。</span><span class="sxs-lookup"><span data-stu-id="f989e-137">You must first assign them a usage location.</span></span> <span data-ttu-id="f989e-138">然後，透過群組成員資格個別或動態指派授權給這些使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f989e-138">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

<span data-ttu-id="f989e-139">以下是使用混合式識別模型時的兩種驗證類型。</span><span class="sxs-lookup"><span data-stu-id="f989e-139">Here are the two types of authentication when using the hybrid identity model.</span></span>

| <span data-ttu-id="f989e-140">驗證類型</span><span class="sxs-lookup"><span data-stu-id="f989e-140">Authentication type</span></span> | <span data-ttu-id="f989e-141">說明</span><span class="sxs-lookup"><span data-stu-id="f989e-141">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="f989e-142">管理的驗證</span><span class="sxs-lookup"><span data-stu-id="f989e-142">Managed authentication</span></span> | <span data-ttu-id="f989e-143">Azure AD 會使用本機儲存的雜湊版本的密碼，或將認證傳送至內部部署 AD DS 來驗證內部部署軟體代理程式，以處理驗證程式。</span><span class="sxs-lookup"><span data-stu-id="f989e-143">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span> <br> <br>  <span data-ttu-id="f989e-144">受管理的驗證類型有兩種：密碼雜湊同步處理 (PHS) 以及透過驗證 (PTA) 。</span><span class="sxs-lookup"><span data-stu-id="f989e-144">There are two types of managed authentication: Password hash synchronization (PHS) and Pass-through authentication (PTA).</span></span> <span data-ttu-id="f989e-145">使用 PHS 時，Azure AD 會自行執行驗證。</span><span class="sxs-lookup"><span data-stu-id="f989e-145">With PHS, Azure AD performs the authentication itself.</span></span> <span data-ttu-id="f989e-146">使用 PTA 時，Azure AD 具有 AD DS 執行驗證。</span><span class="sxs-lookup"><span data-stu-id="f989e-146">With PTA, Azure AD has AD DS perform the authentication.</span></span> |
| <span data-ttu-id="f989e-147">同盟驗證</span><span class="sxs-lookup"><span data-stu-id="f989e-147">Federated authentication</span></span> | <span data-ttu-id="f989e-148">Azure AD 會將要求驗證的用戶端電腦重新導向至另一個身分識別提供者。</span><span class="sxs-lookup"><span data-stu-id="f989e-148">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span> |
|  |  |

<span data-ttu-id="f989e-149">若要深入瞭解，請參閱 [選擇正確的驗證方法](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 。</span><span class="sxs-lookup"><span data-stu-id="f989e-149">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>

## <a name="enforcing-strong-sign-ins"></a><span data-ttu-id="f989e-150">強制執行強式登入</span><span class="sxs-lookup"><span data-stu-id="f989e-150">Enforcing strong sign-ins</span></span>

<span data-ttu-id="f989e-151">若要提高使用者登入的安全性，請使用下表中的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="f989e-151">To increase the security of user sign-ins, use the features and capabilities in the following table.</span></span>

| <span data-ttu-id="f989e-152">功能</span><span class="sxs-lookup"><span data-stu-id="f989e-152">Capability</span></span> | <span data-ttu-id="f989e-153">描述</span><span class="sxs-lookup"><span data-stu-id="f989e-153">Description</span></span> | <span data-ttu-id="f989e-154">其他資訊</span><span class="sxs-lookup"><span data-stu-id="f989e-154">More information</span></span> | <span data-ttu-id="f989e-155">授權需求</span><span class="sxs-lookup"><span data-stu-id="f989e-155">Licensing requirements</span></span> |
|:-------|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f989e-156">Windows Hello 企業版</span><span class="sxs-lookup"><span data-stu-id="f989e-156">Windows Hello for Business</span></span> | <span data-ttu-id="f989e-157">在 Windows 裝置上進行簽署時，取代具有強雙因素驗證的密碼。</span><span class="sxs-lookup"><span data-stu-id="f989e-157">Replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="f989e-158">雙因素是一種新的使用者認證類型，可與裝置和生物特徵或 PIN 相繫結。</span><span class="sxs-lookup"><span data-stu-id="f989e-158">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span> | [<span data-ttu-id="f989e-159">Windows Hello 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="f989e-159">Windows Hello for Business Overview</span></span>](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | <span data-ttu-id="f989e-160">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="f989e-160">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="f989e-161">Azure AD 密碼保護</span><span class="sxs-lookup"><span data-stu-id="f989e-161">Azure AD Password Protection</span></span> | <span data-ttu-id="f989e-162">偵測並封鎖已知的弱密碼和其變種，也可以封鎖您組織特有的其他弱字詞。</span><span class="sxs-lookup"><span data-stu-id="f989e-162">Detects and blocks known weak passwords and their variants and can also block additional weak terms that are specific to your organization.</span></span> | [<span data-ttu-id="f989e-163">設定 Azure AD 密碼保護</span><span class="sxs-lookup"><span data-stu-id="f989e-163">Configure Azure AD password protection</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | <span data-ttu-id="f989e-164">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="f989e-164">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="f989e-165">使用多重要素驗證 (MFA)</span><span class="sxs-lookup"><span data-stu-id="f989e-165">Use multi-factor authentication (MFA)</span></span> | <span data-ttu-id="f989e-166">MFA 要求使用者登入除了使用者帳戶密碼以外的其他驗證，例如使用 smartphone 應用程式的驗證或傳送至 smartphone 的文字訊息。</span><span class="sxs-lookup"><span data-stu-id="f989e-166">MFA requires that user sign-ins be subject to an additional verification beyond the user account password, such as verification with a smartphone app or a text message sent to a smartphone.</span></span> <span data-ttu-id="f989e-167">如需使用者如何設定 MFA 的指示，請參閱 [這段影片](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) 。</span><span class="sxs-lookup"><span data-stu-id="f989e-167">See [this video](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) for instructions on how users set up MFA.</span></span> | [<span data-ttu-id="f989e-168">適用于企業的 Microsoft 365 MFA</span><span class="sxs-lookup"><span data-stu-id="f989e-168">MFA for Microsoft 365 for enterprise</span></span>](../enterprise/microsoft-365-secure-sign-in.md#mfa) | <span data-ttu-id="f989e-169">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="f989e-169">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="f989e-170">身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="f989e-170">Identity and device access configurations</span></span> | <span data-ttu-id="f989e-171">設定和原則，包含建議的必要條件功能及其設定，其結合了條件式存取、Intune 和 Azure AD 身分識別保護原則，可決定是否應該授與指定的存取要求，以及在哪些條件下。</span><span class="sxs-lookup"><span data-stu-id="f989e-171">Settings and policies that consist of recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span>  | [<span data-ttu-id="f989e-172">身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="f989e-172">Identity and device access configurations</span></span>](../security/office-365-security/microsoft-365-policies-configurations.md) | <span data-ttu-id="f989e-173">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="f989e-173">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="f989e-174">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f989e-174">Azure AD Identity Protection</span></span> | <span data-ttu-id="f989e-175">防護認證洩露，攻擊者會決定使用者的帳戶名稱和密碼，以取得對組織的雲端服務和資料的存取權。</span><span class="sxs-lookup"><span data-stu-id="f989e-175">Protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> | [<span data-ttu-id="f989e-176">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f989e-176">Azure AD Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | <span data-ttu-id="f989e-177">Microsoft 365 E5 或 Microsoft 365 E3，具有身分識別 & 威脅防護附加元件</span><span class="sxs-lookup"><span data-stu-id="f989e-177">Microsoft 365 E5 or Microsoft 365 E3 with the Identity & Threat Protection add-on</span></span> |
|  |  |  |



## <a name="results-of-step-3"></a><span data-ttu-id="f989e-178">步驟 3 的結果</span><span class="sxs-lookup"><span data-stu-id="f989e-178">Results of Step 3</span></span>

<span data-ttu-id="f989e-179">為了識別您的 Microsoft 365 租使用者，您已決定：</span><span class="sxs-lookup"><span data-stu-id="f989e-179">For identity for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="f989e-180">使用哪個身分識別模型。</span><span class="sxs-lookup"><span data-stu-id="f989e-180">Which identity model to use.</span></span>
- <span data-ttu-id="f989e-181">您將如何強制執行強使用者和裝置存取。</span><span class="sxs-lookup"><span data-stu-id="f989e-181">How you will enforce strong user and device access.</span></span>

<span data-ttu-id="f989e-182">以下是一個範例，其中包含新的混合身分識別元素的承租人。</span><span class="sxs-lookup"><span data-stu-id="f989e-182">Here is an example a tenant with the new hybrid identity elements highlighted.</span></span>

![承租人的混合身分識別範例](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

<span data-ttu-id="f989e-184">在此圖中，租使用者有：</span><span class="sxs-lookup"><span data-stu-id="f989e-184">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="f989e-185">使用 DirSync server 和 Azure AD Connect 與 Azure AD 租使用者同步處理的 AD DS 樹系。</span><span class="sxs-lookup"><span data-stu-id="f989e-185">An AD DS forest that is being synchronized with the Azure AD tenant using a DirSync server and Azure AD Connect.</span></span>
- <span data-ttu-id="f989e-186">Ad ds 使用者帳戶和其他物件從 AD DS 樹系的複本。</span><span class="sxs-lookup"><span data-stu-id="f989e-186">A copy of the AD DS user accounts and other objects from the AD DS forest.</span></span>
- <span data-ttu-id="f989e-187">一組條件式存取原則，可強制執行安全使用者登入，並根據使用者帳戶進行存取。</span><span class="sxs-lookup"><span data-stu-id="f989e-187">A set of Conditional Access policies to enforce secure user sign-ins and access based on the user account.</span></span> 

## <a name="ongoing-maintenance-for-identity"></a><span data-ttu-id="f989e-188">進行識別的持續維護</span><span class="sxs-lookup"><span data-stu-id="f989e-188">Ongoing maintenance for identity</span></span>

<span data-ttu-id="f989e-189">您可能需要進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="f989e-189">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="f989e-190">新增或修改使用者帳戶和群組。</span><span class="sxs-lookup"><span data-stu-id="f989e-190">Add or modify user accounts and groups.</span></span> <span data-ttu-id="f989e-191">針對僅限雲端的身分識別，您可以使用 Azure AD 工具（例如 Microsoft 365 系統管理中心或 PowerShell）來維護雲端式使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="f989e-191">For cloud-only identity, you maintain your cloud-based users and groups with Azure AD tools such as the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="f989e-192">針對混合式身分識別，您可以使用 AD DS 工具維護內部部署使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="f989e-192">For hybrid identity, you maintain your on-premises users and groups with AD DS tools.</span></span>
- <span data-ttu-id="f989e-193">新增或修改身分識別與裝置存取設定，以強制登入安全性需求。</span><span class="sxs-lookup"><span data-stu-id="f989e-193">Add or modify your identity and device access configuration to enforce sign-in security requirements.</span></span>

## <a name="next-step"></a><span data-ttu-id="f989e-194">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f989e-194">Next step</span></span>

<span data-ttu-id="f989e-195">[![步驟4。遷移您的內部部署 Office 伺服器和資料](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)</span><span class="sxs-lookup"><span data-stu-id="f989e-195">[![Step 4. Migrate your on-premises Office servers and data](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)</span></span>

<span data-ttu-id="f989e-196">繼續 [遷移](tenant-management-migration.md) ，將您的內部部署 Office 伺服器及其資料移轉至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="f989e-196">Continue with [migration](tenant-management-migration.md) to migrate your on-premises Office servers and their data to Microsoft 365.</span></span>
