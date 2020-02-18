---
title: 步驟 4：新增使用者帳戶
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 直接在雲端中，或透過與內部部署目錄同步處理來新增使用者帳戶和群組。
ms.openlocfilehash: 324d4662f868a4a92693b43c6bc0f75c11f20519
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067365"
---
# <a name="step-4-add-your-user-accounts"></a><span data-ttu-id="5bf52-103">步驟 4：新增使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="5bf52-103">Step 4: Add your user accounts</span></span>

![階段 2 - 身分識別](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a><span data-ttu-id="5bf52-105">為僅限雲端身分識別建立使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="5bf52-105">Create your user accounts for cloud-only identity</span></span>

<span data-ttu-id="5bf52-106">針對僅限雲端身分識別，在 Azure Active Directory (Azure AD) 中建立使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="5bf52-106">For cloud-only identity, create your users and groups in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="5bf52-107">您可以使用：</span><span class="sxs-lookup"><span data-stu-id="5bf52-107">You can use:</span></span>

- <span data-ttu-id="5bf52-108">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="5bf52-108">The Microsoft 365 admin center</span></span>
- <span data-ttu-id="5bf52-109">Azure 入口網站</span><span class="sxs-lookup"><span data-stu-id="5bf52-109">The Azure portal</span></span>
- <span data-ttu-id="5bf52-110">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bf52-110">Azure PowerShell</span></span>

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a><span data-ttu-id="5bf52-111">同步處理混合式身分識別的身分識別</span><span class="sxs-lookup"><span data-stu-id="5bf52-111">Synchronize identities for hybrid identity</span></span>

<span data-ttu-id="5bf52-112">*此為混合式環境的必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="5bf52-112">*This is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5bf52-113">在這一節中，您會將內部部署 Active Directory 網域服務 (AD DS) 與 Office 365、Microsoft Intune 和 Microsoft 365 企業版隨附的其他雲端式服務所使用的 Azure AD 租用戶同步處理。</span><span class="sxs-lookup"><span data-stu-id="5bf52-113">In this section, you'll synchronize your on-premises Active Directory Domain Services (AD DS) with the Azure AD tenant used by Office 365, Microsoft Intune, and other cloud-based services included with Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="5bf52-114">Azure AD Connect 是支援的 Microsoft 工具，可逐步引導您將單一或多個樹系 AD DS 環境之中您真正需要的身分識別，同步處理至 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="5bf52-114">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest AD DS environments to your Azure AD tenant.</span></span> <span data-ttu-id="5bf52-115">下圖顯示 Azure AD Connect 同步處理的基本程序。</span><span class="sxs-lookup"><span data-stu-id="5bf52-115">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Azure AD Connect 如何同步處理內部部署目錄與 Azure AD ](../media/identity-add-user-accounts/azure-ad-connect.png)

1. <span data-ttu-id="5bf52-117">在伺服器上執行的 Azure AD Connect 會輪詢 AD DS 以了解帳戶、群組和連絡人是否有變更。</span><span class="sxs-lookup"><span data-stu-id="5bf52-117">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="5bf52-118">Azure AD Connect 會將這些變更傳送至 Microsoft 365 月租方案的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="5bf52-118">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="5bf52-p103">混合式身分識別解決方案中的第一個決策是驗證需求。選項如下：</span><span class="sxs-lookup"><span data-stu-id="5bf52-p103">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="5bf52-p104">使用**受控驗證**，Azure AD 會處理使用者登入的驗證程序。受控驗證有兩種方法：</span><span class="sxs-lookup"><span data-stu-id="5bf52-p104">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="5bf52-123">**密碼雜湊同步處理 (PHS)** [某些進階功能的建議和必要方法]。</span><span class="sxs-lookup"><span data-stu-id="5bf52-123">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="5bf52-124">這是最簡單的方法，可為 Azure AD 中的內部部署目錄物件啟用驗證功能。</span><span class="sxs-lookup"><span data-stu-id="5bf52-124">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="5bf52-125">Azure AD Connect 會從 AD DS 擷取雜湊的密碼、對密碼雜湊進行額外的安全性處理，並將其同步處理到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="5bf52-125">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password hash, and synchronizes it to Azure AD.</span></span> <span data-ttu-id="5bf52-126">如需詳細資訊，請參閱[使用 Azure AD Connect 同步實作密碼雜湊同步處理](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="5bf52-126">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
    - <span data-ttu-id="5bf52-127">**傳遞驗證 (PTA)**，會針對以 Azure AD 為基礎的服務提供簡單的密碼驗證解決方案。</span><span class="sxs-lookup"><span data-stu-id="5bf52-127">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="5bf52-128">PTA 會使用在一或多個內部部署伺服器上執行的代理程式來直接向內部部署 AD DS 驗證使用者驗證。</span><span class="sxs-lookup"><span data-stu-id="5bf52-128">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="5bf52-129">如需詳細資訊，請參閱[使用 Azure Active Directory 傳遞驗證的使用者登入](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)。</span><span class="sxs-lookup"><span data-stu-id="5bf52-129">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="5bf52-p107">使用**同盟驗證**，在使用者登入時，會透過身分識別同盟伺服器 (例如 Active Directory 同盟服務 (AD FS))，將驗證程序重新導向到另一個身分識別提供者。身分識別提供者可以提供額外的驗證方法，例如智慧卡驗證。如需詳細資訊，請參閱[針對 Azure Active Directory 混合式身分識別解決方案選擇正確的驗證方法](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)。</span><span class="sxs-lookup"><span data-stu-id="5bf52-p107">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="5bf52-133">請觀看這段影片，以大略了解 Microsoft 365 企業版的身分識別模型和驗證。</span><span class="sxs-lookup"><span data-stu-id="5bf52-133">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="5bf52-134"><p> </p></span><span class="sxs-lookup"><span data-stu-id="5bf52-134"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="5bf52-135">在您決定混合式身分識別解決方案之後，請下載並執行 [IdFix 目錄同步處理錯誤修復工具](https://www.microsoft.com/download/details.aspx?id=36832)來分析 AD DS 的問題。</span><span class="sxs-lookup"><span data-stu-id="5bf52-135">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your AD DS for issues.</span></span>

<span data-ttu-id="5bf52-136">解決由 IdFix 工具找出的所有問題之後，請參閱[使用 Azure AD Connect 同步來實作密碼雜湊同步處理](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)，了解如何安裝 Azure AD Connect 工具、設定內部部署 AD DS 和 Microsoft 365 訂閱的 Azure AD 租用戶之間的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="5bf52-136">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises AD DS and the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="5bf52-137">開始同步處理之後，您要使用內部部署身分識別提供者 (例如 AD DS) 維護使用者帳戶和群組。</span><span class="sxs-lookup"><span data-stu-id="5bf52-137">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="5bf52-138">Microsoft 會針對[身分識別與裝置存取](microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。</span><span class="sxs-lookup"><span data-stu-id="5bf52-138">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="5bf52-139">如需混合式環境的建議需求，請參閱[必要條件](identity-access-prerequisites.md#prerequisites)中的 [Active Directory 與密碼雜湊同步處理]\*\*\*\* 資料行。</span><span class="sxs-lookup"><span data-stu-id="5bf52-139">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="5bf52-140">如需僅雲端環境的建議需求，請參閱[必要條件](identity-access-prerequisites.md#prerequisites)中的 [僅雲端]\*\*\*\* 資料行。</span><span class="sxs-lookup"><span data-stu-id="5bf52-140">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="5bf52-141">內部部署使用者和群組出現在 Azure AD 中之後，您就可以開始指派授權及使用生產力工作負載，例如商務用 OneDrive 和 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="5bf52-141">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using productivity workloads such as OneDrive for Business and Exchange Online.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5bf52-143">測試實驗室指南：密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="5bf52-143">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="5bf52-144">測試實驗室指南：傳遞驗證</span><span class="sxs-lookup"><span data-stu-id="5bf52-144">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="5bf52-145">作為過渡期的檢查點，您可以看到對應至這一節的[允出準則](identity-exit-criteria.md#crit-identity-sync)。</span><span class="sxs-lookup"><span data-stu-id="5bf52-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this section.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="5bf52-146">監控同步處理健康情況</span><span class="sxs-lookup"><span data-stu-id="5bf52-146">Monitor synchronization health</span></span>

<span data-ttu-id="5bf52-147">*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="5bf52-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="5bf52-148">在這一節中，您會在每個內部部署 AD DS 網域控制站上安裝 Azure AD Connect Health 代理程式，以監控您的身分識別基礎結構，以及由 Azure AD Connect 提供的同步處理服務。</span><span class="sxs-lookup"><span data-stu-id="5bf52-148">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="5bf52-149">監控資訊會在 Azure AD Connect Health 入口網站提供，您可以在其中檢視警訊、效能監控、使用量分析及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="5bf52-149">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Azure AD Connect Health 的元件](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

<span data-ttu-id="5bf52-151">如何使用 Azure AD Connect Health 的關鍵設計決策取決於您如何使用 Azure AD Connect：</span><span class="sxs-lookup"><span data-stu-id="5bf52-151">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="5bf52-152">如果您使用的是**受管理的驗證**選項，請先從[使用 Azure AD Connect Health 搭配同步處理](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)開始，以了解並設定 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="5bf52-152">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="5bf52-153">如果您使用**同盟驗證**搭配 Active Directory 同盟服務 (AD FS) 來同步處理帳戶及群組名稱，請先從[使用 Azure AD Connect Health 搭配 AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 開始，以了解並設定 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="5bf52-153">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="5bf52-154">完成這一節後的結果：</span><span class="sxs-lookup"><span data-stu-id="5bf52-154">When you complete this section, you’ll have:</span></span>

- <span data-ttu-id="5bf52-155">已在內部部署身分識別提供者伺服器上安裝 Azure AD Connect Health 代理程式。</span><span class="sxs-lookup"><span data-stu-id="5bf52-155">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="5bf52-156">Azure AD Connect Health 入口網站會顯示您內部部署基礎結構和同步處理活動的目前狀態以及 Microsoft 365 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="5bf52-156">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

<span data-ttu-id="5bf52-157">作為過渡期的檢查點，您可以查看這一節的[允出準則](identity-exit-criteria.md#crit-identity-sync-health)。</span><span class="sxs-lookup"><span data-stu-id="5bf52-157">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this section.</span></span>



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="5bf52-158">簡化密碼更新</span><span class="sxs-lookup"><span data-stu-id="5bf52-158">Simplify password updates</span></span>

<span data-ttu-id="5bf52-159">*此為混合式環境的選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="5bf52-159">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5bf52-160">在這一節中，您會允許使用者透過 Azure Active Directory (Azure AD) 重設其密碼，然後複製到本機 Active Directory 網域服務 (AD DS)。</span><span class="sxs-lookup"><span data-stu-id="5bf52-160">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="5bf52-161">這個程序也稱為密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="5bf52-161">This process is known as password writeback.</span></span> <span data-ttu-id="5bf52-162">使用密碼回寫，使用者不需要透過使用者帳戶與其屬性儲存在其中的內部部署 AD DS 來更新其密碼。</span><span class="sxs-lookup"><span data-stu-id="5bf52-162">With password writeback, users don’t need to update their passwords through the on-premises AD DS where user accounts and their attributes are stored.</span></span> <span data-ttu-id="5bf52-163">對於沒有內部部署網路遠端存取連線的漫遊或遠端使用者而言，這非常有用。</span><span class="sxs-lookup"><span data-stu-id="5bf52-163">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="5bf52-164">為了充分利用 Azure AD Identity Protection 功能 (例如當偵測到高風險的帳戶洩露時，要求使用者變更其內部部署密碼)，需要密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="5bf52-164">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="5bf52-165">如需詳細資訊和設定指示，請參閱 [Azure AD SSPR 密碼回寫](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)。</span><span class="sxs-lookup"><span data-stu-id="5bf52-165">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="5bf52-p111">升級至最新版的 Azure AD Connect，以確保在新版本發行後能夠使用新功能並獲得最佳體驗。如需詳細資訊，請參閱 [Azure AD Connect 的自訂安裝](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。</span><span class="sxs-lookup"><span data-stu-id="5bf52-p111">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5bf52-169">測試實驗室指南：密碼回寫</span><span class="sxs-lookup"><span data-stu-id="5bf52-169">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="5bf52-170">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pw-writeback)。</span><span class="sxs-lookup"><span data-stu-id="5bf52-170">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

|||
|:-------|:-----|
|![步驟 5](../media/stepnumbers/Step5.png)| [<span data-ttu-id="5bf52-172">使用群組進行管理</span><span class="sxs-lookup"><span data-stu-id="5bf52-172">Use groups for management</span></span>](identity-use-group-management.md) |
