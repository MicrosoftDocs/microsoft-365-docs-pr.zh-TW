---
title: 步驟 1：適用於使用者與群組的方案
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 適用於您組織之使用者和群組的方案。
ms.openlocfilehash: ac7f5e56bae882e01c31cacee856f73b0ead772f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071632"
---
# <a name="step-1-plan-for-users-and-groups"></a><span data-ttu-id="526fc-103">步驟 1：適用於使用者與群組的方案</span><span class="sxs-lookup"><span data-stu-id="526fc-103">Step 1: Plan for users and groups</span></span>

<span data-ttu-id="526fc-104">*此為必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="526fc-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="526fc-p101">在此步驟中，您將建立身分識別基礎結構，其會結合使用者、群組和群組成員資格與正確設定中的安全性功能。這可讓您：</span><span class="sxs-lookup"><span data-stu-id="526fc-p101">In this step, you'll create your identity infrastructure that combines users, groups, and group membership with security features in the correct configuration. This allows you to:</span></span>

- <span data-ttu-id="526fc-107">持續控制誰擁有對您環境中資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="526fc-107">Maintain control over who has access to resources in your environment.</span></span>
- <span data-ttu-id="526fc-108">透過可強烈確保身分識別之控制項 (使用者的身分即為他們宣稱的身分) 與來自安全裝置的存取權來保護存取權。</span><span class="sxs-lookup"><span data-stu-id="526fc-108">Secure access with controls that ensure strong assurances of identity (users are who they say they are) and access from safe devices.</span></span>
- <span data-ttu-id="526fc-109">使用適當的權限來在環境中佈建資源，以降低損害與資料外洩的可能性。</span><span class="sxs-lookup"><span data-stu-id="526fc-109">Provision resources in your environment with appropriate permissions to reduce the potential for harm and data leakage.</span></span> 
- <span data-ttu-id="526fc-110">監控您的環境，確認是否有異常使用者行為，並自動採取行動。</span><span class="sxs-lookup"><span data-stu-id="526fc-110">Monitor your environment for anomalous user behavior and automatically taking action.</span></span>

## <a name="plan-your-primary-identity-provider"></a><span data-ttu-id="526fc-111">規劃您的主要身分識別提供者</span><span class="sxs-lookup"><span data-stu-id="526fc-111">Plan your primary identity provider</span></span>

<span data-ttu-id="526fc-p102">若要建立您的身分識別基礎結構，您將指定主要身分識別提供者。這個服務會儲存使用者帳戶與其屬性、群組和其成員資格，並支援其進行中的管理。</span><span class="sxs-lookup"><span data-stu-id="526fc-p102">To create your identity infrastructure, you'll designate a primary identity provider. This service stores user accounts and their attributes, groups and their memberships, and supports their ongoing administration.</span></span>

<span data-ttu-id="526fc-114">當貴組織採用 Microsoft 365 企業版時，您主要的身分識別提供者是以下其中一項：</span><span class="sxs-lookup"><span data-stu-id="526fc-114">When your organization adopts Microsoft 365 Enterprise, your primary identity provider is either:</span></span>

- <span data-ttu-id="526fc-115">**Active Directory 網域服務 (AD DS)**，是裝載於執行 Windows Server 的電腦上的內部網路身分識別提供者。</span><span class="sxs-lookup"><span data-stu-id="526fc-115">**Active Directory Domain Services (AD DS)**, an intranet identity provider hosted on computers running Windows Server.</span></span> <span data-ttu-id="526fc-116">一般使用對象為具有現有內部部署身分識別提供者的組織。</span><span class="sxs-lookup"><span data-stu-id="526fc-116">This is typically used by organizations that have an existing on-premises identity provider.</span></span>
- <span data-ttu-id="526fc-117">**Azure Active Directory (Azure AD**)，為以雲端為基礎的身份認證即服務 (IDaaS)，提供管理及保護環境的各種功能。</span><span class="sxs-lookup"><span data-stu-id="526fc-117">**Azure Active Directory (Azure AD)**, a cloud-based Identity as a Service (IDaaS) that provides a broad range of capabilities for managing and protecting your environment.</span></span> <span data-ttu-id="526fc-118">一般使用對象為不具現有內部部署基礎結構的組織。</span><span class="sxs-lookup"><span data-stu-id="526fc-118">This is typically used by organizations that have no existing on-premises infrastructure.</span></span>

<span data-ttu-id="526fc-119">如果您的組織有現有的內部部署身分識別提供者，您需要將來自 AD DS 的使用者帳戶與群組同步處理至 Azure AD，以提供更多 Microsoft 365 Enterprise 雲端服務的無縫存取。</span><span class="sxs-lookup"><span data-stu-id="526fc-119">If your organization has an existing on-premises identity provider, you need to synchronize your user accounts and groups from AD DS to Azure AD to provide more seamless access to the cloud-based services of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="526fc-120">您也可以使用 Azure AD 來建立及管理只存在於 Microsoft 雲端中的群組。</span><span class="sxs-lookup"><span data-stu-id="526fc-120">You can also use Azure AD to create and manage groups that exist only in the Microsoft cloud.</span></span>

<span data-ttu-id="526fc-121">在使用者和群組都位於 Azure AD 中後，您可以：</span><span class="sxs-lookup"><span data-stu-id="526fc-121">After you have your users and groups in Azure AD, you can:</span></span>

- <span data-ttu-id="526fc-122">為所有雲端應用程式管理 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="526fc-122">Manage all the Azure AD accounts for all your cloud applications.</span></span> 
- <span data-ttu-id="526fc-123">使用一組相同的控制項來保護您環境中對應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="526fc-123">Use the same set of controls to protect access to applications across your environment.</span></span>
- <span data-ttu-id="526fc-124">與外部合作夥伴共同作業。</span><span class="sxs-lookup"><span data-stu-id="526fc-124">Collaborate with external partners.</span></span>
- <span data-ttu-id="526fc-125">監控異常帳戶行為 (例如可疑登入嘗試)，並自動採取行動。</span><span class="sxs-lookup"><span data-stu-id="526fc-125">Monitor anomalous account behavior, such as suspicious sign-in attempts, and automatically act.</span></span>

<span data-ttu-id="526fc-126">請依照下列兩個區段中的指示來規劃並實作您的使用者帳戶和群組。</span><span class="sxs-lookup"><span data-stu-id="526fc-126">Follow the instructions in the next two sections to plan for and implement your user accounts and groups.</span></span>

## <a name="categorize-your-users"></a><span data-ttu-id="526fc-127">分類使用者</span><span class="sxs-lookup"><span data-stu-id="526fc-127">Categorize your users</span></span>
<span data-ttu-id="526fc-p106">可以使用多種方式來分類組織中的使用者。比方說，有些是員工並具有永久性狀態。有些是狀態是暫時性的廠商、承包商或合作夥伴。有些是外部使用者，他們沒有使用者帳戶，但仍必須獲予特定服務和資源的存取權，以支援互動與共同作業。例如：</span><span class="sxs-lookup"><span data-stu-id="526fc-p106">Users in organizations can be categorized in a number of ways. For example, some are employees and have a permanent status. Some are vendors, contractors, or partners that have a temporary status. Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration. For example:</span></span>

- <span data-ttu-id="526fc-133">租用戶帳戶代表您為雲端服務授權之組織內的使用者</span><span class="sxs-lookup"><span data-stu-id="526fc-133">Tenant accounts represent users within your organization that you license for cloud services</span></span>
- <span data-ttu-id="526fc-134">企業對企業 (B2B) 帳戶代表不屬於您邀請參與共同作業之組織的使用者</span><span class="sxs-lookup"><span data-stu-id="526fc-134">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="526fc-p107">請仔細審查貴組織的使用者類型。什麼是群組？比方說，您可以依高層級的功能和用途將使用者分組至您的組織。</span><span class="sxs-lookup"><span data-stu-id="526fc-p107">Take stock of the types of users to your organization. What are the groupings? For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="526fc-p108">此外，某些雲端服務可以與組織外的使用者共用，而不需使用任何使用者帳戶。您也必須識別使用者的這些群組。</span><span class="sxs-lookup"><span data-stu-id="526fc-p108">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a><span data-ttu-id="526fc-140">規劃 AD DS 和 Azure AD 群組</span><span class="sxs-lookup"><span data-stu-id="526fc-140">Plan for AD DS and Azure AD groups</span></span>

<span data-ttu-id="526fc-p109">您可以使用 Azure AD 中的群組，以實現簡化雲端環境管理的多個目的。例如，針對 Azure AD 群組，您可以：</span><span class="sxs-lookup"><span data-stu-id="526fc-p109">You can use groups in Azure AD for several purposes that simplify management of your cloud environment. For example, for Azure AD groups, you can:</span></span>

- <span data-ttu-id="526fc-143">使用以群組為基礎的授權，以在 Azure AD 中新增您的使用者帳戶或從 AD DS 進行同步處理後，立即將授權自動指派給將這些使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="526fc-143">Use group-based licensing to assign licenses for Office 365 and Enterprise Mobility + Security (EMS) to your user accounts automatically as soon as they are added in Azure AD or synchronized from AD DS.</span></span> 
- <span data-ttu-id="526fc-144">根據使用者帳戶屬性 (例如部門) 以動態方式將使用者帳戶新增至特定群組。</span><span class="sxs-lookup"><span data-stu-id="526fc-144">Add user accounts to specific groups dynamically based on user account attributes, such as department.</span></span>  
- <span data-ttu-id="526fc-145">為軟體即服務 (SaaS) 應用程式自動佈建使用者，並透過多重要素驗證和其他條件式存取規則來保護對這些應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="526fc-145">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication and other conditional access rules.</span></span>
- <span data-ttu-id="526fc-p110">佈建 SharePoint Online 小組網站的權限和存取層級。Azure AD 群組也可與敏感度或 Azure 資訊保護標籤一起使用來透過加密和權限保護檔案。</span><span class="sxs-lookup"><span data-stu-id="526fc-p110">Provision permissions and levels of access for SharePoint Online team sites. Azure AD groups can also be used with scoped Azure Information Protection policies to protect files with encryption and permissions.</span></span> 

## <a name="results"></a><span data-ttu-id="526fc-148">結果</span><span class="sxs-lookup"><span data-stu-id="526fc-148">Results</span></span>

<span data-ttu-id="526fc-149">完成此步驟後的結果：</span><span class="sxs-lookup"><span data-stu-id="526fc-149">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="526fc-150">在 Azure AD 中的使用者帳戶清單，其與貴組織的員工和與貴組織合作的廠商、承包商及外部夥伴相對應。</span><span class="sxs-lookup"><span data-stu-id="526fc-150">A list of user accounts in Azure AD that correspond to the employees in your organization and the vendors, contractors, and external partners that work for or with your organization.</span></span>
- <span data-ttu-id="526fc-151">Azure AD 中一組群組和其成員反映的使用者帳戶和其他群組的邏輯集合，適用於為 Microsoft 雲端服務的安全性設定佈建進行自動授權。</span><span class="sxs-lookup"><span data-stu-id="526fc-151">A set of groups and their membership in Azure AD that reflect logical sets of user accounts and other groups for automatic licensing provisioning of security settings for Microsoft cloud services.</span></span>

<span data-ttu-id="526fc-152">Azure AD 使用者和群組建立之後，您就可以開始指派授權及使用生產力工作負載，例如商務用 OneDrive 或 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="526fc-152">Once your Azure AD users and groups are created, you can start assigning licenses and using Exchange Online.</span></span>

## <a name="next-step"></a><span data-ttu-id="526fc-153">下一步</span><span class="sxs-lookup"><span data-stu-id="526fc-153">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="526fc-154">保護您的特殊權限身分識別</span><span class="sxs-lookup"><span data-stu-id="526fc-154">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |

