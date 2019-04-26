---
title: 步驟 3：設定混合式身分識別
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解身分識別選項，並設定 Azure AD Connect 來將內部部署 Active Directory Domain Services 與 Azure AD 同步。
ms.openlocfilehash: 6e582a3e3c68b00968faac17fd60b922eaaf7121
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289591"
---
# <a name="step-3-configure-hybrid-identity"></a><span data-ttu-id="be39c-103">步驟 3：設定混合式身分識別</span><span class="sxs-lookup"><span data-stu-id="be39c-103">Step 3: Configure hybrid identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-sync"></a>
## <a name="synchronize-identities"></a><span data-ttu-id="be39c-104">同步處理身分識別</span><span class="sxs-lookup"><span data-stu-id="be39c-104">Step 7: Synchronize identities</span></span>

<span data-ttu-id="be39c-105">此為混合式環境的必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本\*\*</span><span class="sxs-lookup"><span data-stu-id="be39c-105">*This step is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="be39c-106">在這一節當中，您會將內部部署 Active Directory Domain Services (AD DS) 與 Azure Active Directory (Azure AD) 租用戶同步處理 (後者由您的 Office 365 與企業行動力 + 安全性 (EMS) 訂用帳戶使用)。</span><span class="sxs-lookup"><span data-stu-id="be39c-106">In this step, you'll synchronize your on-premises Windows Server Active Directory (AD) with the Azure Active Directory (AD) tenant used by your Office 365 and Enterprise Mobility + Security (EMS) subscriptions.</span></span>

<span data-ttu-id="be39c-107">Azure AD Connect 是支援的 Microsoft 工具，可逐步引導您將單一或多個樹系 AD DS 環境之中您真正需要的身分識別，同步處理至 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="be39c-107">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest Windows Server AD environments to your Azure AD tenant.</span></span> <span data-ttu-id="be39c-108">下圖顯示 Azure AD Connect 同步處理的基本程序。</span><span class="sxs-lookup"><span data-stu-id="be39c-108">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Azure AD Connect 如何同步處理內部部署目錄與 Azure AD ](./media/identity-azure-ad-connect/azure-ad-connect.png)

1. <span data-ttu-id="be39c-110">在伺服器上執行的 Azure AD Connect 會輪詢 AD DS 以了解帳戶、群組和連絡人是否有變更。</span><span class="sxs-lookup"><span data-stu-id="be39c-110">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="be39c-111">Azure AD Connect 會將這些變更傳送至 Microsoft 365 月租方案的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="be39c-111">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="be39c-p102">混合式身分識別解決方案中的第一個決策是驗證需求。選項如下：</span><span class="sxs-lookup"><span data-stu-id="be39c-p102">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="be39c-p103">使用**受控驗證**，Azure AD 會處理使用者登入的驗證程序。受控驗證有兩種方法：</span><span class="sxs-lookup"><span data-stu-id="be39c-p103">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="be39c-116">**密碼雜湊同步處理 (PHS)** [某些進階功能的建議和必要方法]。</span><span class="sxs-lookup"><span data-stu-id="be39c-116">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="be39c-117">這是最簡單的方法，可為 Azure AD 中的內部部署目錄物件啟用驗證功能。</span><span class="sxs-lookup"><span data-stu-id="be39c-117">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="be39c-118">Azure AD Connect 會從 AD DS 擷取雜湊的密碼、對密碼進行額外的安全性處理，並將其儲存在 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="be39c-118">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password, and saves it in Azure AD.</span></span> <span data-ttu-id="be39c-119">如需詳細資訊，請參閱[使用 Azure AD Connect 同步實作密碼雜湊同步處理](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="be39c-119">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span></span>
    - <span data-ttu-id="be39c-120">**傳遞驗證 (PTA)**，會針對以 Azure AD 為基礎的服務提供簡單的密碼驗證解決方案。</span><span class="sxs-lookup"><span data-stu-id="be39c-120">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="be39c-121">PTA 會使用在一或多個內部部署伺服器上執行的代理程式來直接向內部部署 AD DS 驗證使用者驗證。</span><span class="sxs-lookup"><span data-stu-id="be39c-121">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="be39c-122">如需詳細資訊，請參閱[使用 Azure Active Directory 傳遞驗證的使用者登入](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)。</span><span class="sxs-lookup"><span data-stu-id="be39c-122">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="be39c-p106">使用**同盟驗證**，在使用者登入時，會透過身分識別同盟伺服器 (例如 Active Directory 同盟服務 (AD FS))，將驗證程序重新導向到另一個身分識別提供者。身分識別提供者可以提供額外的驗證方法，例如智慧卡驗證。如需詳細資訊，請參閱[針對 Azure Active Directory 混合式身分識別解決方案選擇正確的驗證方法](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)。</span><span class="sxs-lookup"><span data-stu-id="be39c-p106">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="be39c-126">在您決定混合式身分識別解決方案之後，請下載並執行 [IdFix 目錄同步處理錯誤修復工具](https://www.microsoft.com/download/details.aspx?id=36832)來分析 AD DS 的問題。</span><span class="sxs-lookup"><span data-stu-id="be39c-126">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your Windows Server AD for issues.</span></span>

<span data-ttu-id="be39c-127">解決由 IdFix 工具找出的所有問題之後，請參閱[使用 Azure AD Connect 同步來實作密碼雜湊同步處理](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)，了解如何安裝 Azure AD Connect 工具、設定內部部署 AD DS 和 Office 365 與 EMS 訂用帳戶的 Azure AD 租用戶之間的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="be39c-127">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises Windows Server AD and the Azure AD tenant for your Office 365 and EMS subscriptions. After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as Windows Server AD.</span></span> <span data-ttu-id="be39c-128">開始同步處理之後，您要使用內部部署身分識別提供者 (例如 AD DS) 維護使用者帳戶和群組。</span><span class="sxs-lookup"><span data-stu-id="be39c-128">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="be39c-129">Microsoft 會針對[身分識別與裝置存取](microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。</span><span class="sxs-lookup"><span data-stu-id="be39c-129">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="be39c-130">如需混合式環境的建議需求，請參閱[必要條件](identity-access-prerequisites.md#prerequisites)中的 [Active Directory 與密碼雜湊同步處理]\*\*\*\* 資料行。</span><span class="sxs-lookup"><span data-stu-id="be39c-130">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="be39c-131">如需僅雲端環境的建議需求，請參閱[必要條件](identity-access-prerequisites.md#prerequisites)中的 [僅雲端]\*\*\*\* 資料行。</span><span class="sxs-lookup"><span data-stu-id="be39c-131">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="be39c-132">內部部署使用者和群組出現在 Azure AD 後，您就可以開始指派授權及使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="be39c-132">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using Exchange Online.</span></span> <span data-ttu-id="be39c-133">若要向使用者推行 Exchange Online，並遷移內部部署信箱，請參閱[針對 Microsoft 365 企業版部署 Exchange Online](exchangeonline-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="be39c-133">To roll out Exchange Online to your users and migrate on-premises mailboxes, see [Deploy Exchange Online for Microsoft 365 Enterprise](exchangeonline-workload.md).</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="be39c-135">測試實驗室指南：密碼雜湊同步處理</span><span class="sxs-lookup"><span data-stu-id="be39c-135">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="be39c-136">測試實驗室指南：傳遞驗證</span><span class="sxs-lookup"><span data-stu-id="be39c-136">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="be39c-137">作為過渡期的檢查點，您可以看到對應至這一節的[允出準則](identity-exit-criteria.md#crit-identity-sync)。</span><span class="sxs-lookup"><span data-stu-id="be39c-137">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this step.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="be39c-138">監控同步處理健康情況</span><span class="sxs-lookup"><span data-stu-id="be39c-138">Monitor synchronization health</span></span>

<span data-ttu-id="be39c-139">此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本\*\*</span><span class="sxs-lookup"><span data-stu-id="be39c-139">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="be39c-140">在這一節中，您會在每個內部部署身分識別伺服器上安裝 Azure AD Connect Health 代理程式，以監控您的身分識別基礎結構，以及由 Azure AD Connect 提供的同步處理服務。</span><span class="sxs-lookup"><span data-stu-id="be39c-140">In this step, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect. The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span> <span data-ttu-id="be39c-141">監控資訊會在 Azure AD Connect Health 入口網站提供，您可以在其中檢視警訊、效能監控、使用量分析及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="be39c-141">In this step, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect. The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Azure AD Connect Health 的元件](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="be39c-143">如何使用 Azure AD Connect Health 的關鍵設計決策取決於您如何使用 Azure AD Connect：</span><span class="sxs-lookup"><span data-stu-id="be39c-143">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="be39c-144">如果您使用的是**受管理的驗證**選項，請先從[使用 Azure AD Connect Health 搭配同步處理](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)開始，以了解並設定 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="be39c-144">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="be39c-145">如果您使用**同盟驗證**搭配 Active Directory 同盟服務 (AD FS) 來同步處理帳戶及群組名稱，請先從[使用 Azure AD Connect Health 搭配 AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 開始，以了解並設定 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="be39c-145">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="be39c-146">完成這一節後的結果：</span><span class="sxs-lookup"><span data-stu-id="be39c-146">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="be39c-147">已在內部部署身分識別提供者伺服器上安裝 Azure AD Connect Health 代理程式。</span><span class="sxs-lookup"><span data-stu-id="be39c-147">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="be39c-148">Azure AD Connect Health 入口網站會顯示您內部部署基礎結構和同步處理活動的目前狀態以及 Office 365 和 EMS 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="be39c-148">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="be39c-149">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-sync-health)。</span><span class="sxs-lookup"><span data-stu-id="be39c-149">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="be39c-150">下一步</span><span class="sxs-lookup"><span data-stu-id="be39c-150">Next step</span></span>

|||
|:-------|:-----|
![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="be39c-151">設定安全的使用者驗證</span><span class="sxs-lookup"><span data-stu-id="be39c-151">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md)
