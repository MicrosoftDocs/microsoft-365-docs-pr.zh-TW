---
title: 設定客戶金鑰
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 瞭解如何設定 Microsoft 365 的客戶金鑰。
ms.openlocfilehash: e187c01a355cc9b926e892cb3326b5a527c714a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344671"
---
# <a name="set-up-customer-key"></a><span data-ttu-id="509d1-103">設定客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="509d1-103">Set up Customer Key</span></span>

<span data-ttu-id="509d1-104">使用客戶金鑰，您可以控制組織的加密金鑰，然後設定 Microsoft 365，使用這些金鑰在 Microsoft 資料中心內加密您的資料。</span><span class="sxs-lookup"><span data-stu-id="509d1-104">With Customer Key, you control your organization's encryption keys and then configure Microsoft 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="509d1-105">換句話說，客戶金鑰可讓客戶新增屬於其金鑰的加密層級。</span><span class="sxs-lookup"><span data-stu-id="509d1-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span>

<span data-ttu-id="509d1-106">設定 Azure，然後才能將客戶金鑰用於 Office 365。</span><span class="sxs-lookup"><span data-stu-id="509d1-106">Set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="509d1-107">本文說明建立及設定必要 Azure 資源所需遵循的步驟，並提供在 Office 365 中設定客戶機碼的步驟。</span><span class="sxs-lookup"><span data-stu-id="509d1-107">This article describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="509d1-108">在您設定 Azure 之後，您可以決定要指派哪一個原則，以在組織中的各種 Microsoft 365 工作負載中，指派哪些機碼來加密資料。</span><span class="sxs-lookup"><span data-stu-id="509d1-108">After you set up Azure, you determine which policy, and therefore, which keys, to assign to encrypt data across various Microsoft 365 workloads in your organization.</span></span> <span data-ttu-id="509d1-109">如需客戶機碼的相關資訊，或有關一般概述，請參閱[Office 365 中的客戶金鑰服務加密](customer-key-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="509d1-109">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="509d1-110">強烈建議您遵循本文中的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="509d1-110">We strongly recommend that you follow the best practices in this article.</span></span> <span data-ttu-id="509d1-111">這些是以 **TIP** 和 **重要** 的方式呼叫。</span><span class="sxs-lookup"><span data-stu-id="509d1-111">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="509d1-112">客戶金鑰可讓您控制根加密金鑰，其範圍可以像整個組織一樣大。</span><span class="sxs-lookup"><span data-stu-id="509d1-112">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="509d1-113">這表示對這些機碼所做的錯誤可能會產生很大的影響，而且可能會導致服務中斷或資料遺失。</span><span class="sxs-lookup"><span data-stu-id="509d1-113">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="509d1-114">在您設定客戶機碼之前</span><span class="sxs-lookup"><span data-stu-id="509d1-114">Before you set up Customer Key</span></span>

<span data-ttu-id="509d1-115">開始之前，請先確定您的組織具備適當的 Azure 訂閱和授權。</span><span class="sxs-lookup"><span data-stu-id="509d1-115">Before you get started, ensure that you have the appropriate Azure subscriptions and licensing for your organization.</span></span> <span data-ttu-id="509d1-116">使用 Enterprise 合約或雲端服務提供者的付費 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="509d1-116">Use paid Azure Subscriptions using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="509d1-117">不接受信用卡支付。</span><span class="sxs-lookup"><span data-stu-id="509d1-117">Credit Card based payments are not accepted.</span></span> <span data-ttu-id="509d1-118">核准和設定發票的帳戶需求。</span><span class="sxs-lookup"><span data-stu-id="509d1-118">Approve and set up the account needs for invoicing.</span></span> <span data-ttu-id="509d1-119">您透過免費、試用、Sponsorships、MSDN 訂閱和舊版支援所提供的訂閱並無資格。</span><span class="sxs-lookup"><span data-stu-id="509d1-119">Subscriptions you got through Free, Trial, Sponsorships, MSDN Subscriptions, and those under Legacy Support are not eligible.</span></span>

<span data-ttu-id="509d1-120">Office 365E5、Microsoft 365 E5、Microsoft 365 E5 合規性及 Microsoft 365 E5 資訊保護 & 控管 SKUs 提供客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-120">Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance, and Microsoft 365 E5 Information Protection & Governance SKUs offer Customer Key.</span></span> <span data-ttu-id="509d1-121">Office 365 進階合規性SKU 已不再提供購置新的授權。</span><span class="sxs-lookup"><span data-stu-id="509d1-121">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="509d1-122">將繼續支援現有的 Office 365 進階合規性授權。</span><span class="sxs-lookup"><span data-stu-id="509d1-122">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span>

<span data-ttu-id="509d1-123">若要瞭解本文中的概念和程式，請參閱 [Azure 重要保險庫](/azure/key-vault/) 檔。</span><span class="sxs-lookup"><span data-stu-id="509d1-123">To understand the concepts and procedures in this article, review the [Azure Key Vault](/azure/key-vault/) documentation.</span></span> <span data-ttu-id="509d1-124">此外，熟悉 Azure 中使用的條款，例如 [AZURE AD 租](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)使用者。</span><span class="sxs-lookup"><span data-stu-id="509d1-124">Also, become familiar with the terms used in Azure, for example, [Azure AD tenant](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).</span></span>
  
<span data-ttu-id="509d1-125">如果您需要檔以外的其他支援，請與 Microsoft 諮詢服務 (MCS) 、Premier Field 工程 (PFE) 或 Microsoft 合作夥伴以取得協助。</span><span class="sxs-lookup"><span data-stu-id="509d1-125">If you need more support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="509d1-126">若要提供對客戶機碼的意見反應（包括檔），請將您的想法、建議和觀點傳送至 customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="509d1-126">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="509d1-127">設定客戶機碼的步驟概述</span><span class="sxs-lookup"><span data-stu-id="509d1-127">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="509d1-128">若要設定客戶機碼，請依所列順序完成這些工作。</span><span class="sxs-lookup"><span data-stu-id="509d1-128">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="509d1-129">本文的其餘部分提供每項工作的詳細指示，或連結至程式中每個步驟的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="509d1-129">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="509d1-130">**在 Azure 和 Microsoft FastTrack：**</span><span class="sxs-lookup"><span data-stu-id="509d1-130">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="509d1-131">您可以遠端連線至 Azure PowerShell，以完成大部分的工作。</span><span class="sxs-lookup"><span data-stu-id="509d1-131">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="509d1-132">為了獲得最佳結果，請使用 Azure PowerShell 版本4.4.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="509d1-132">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="509d1-133">建立兩個新的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="509d1-133">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="509d1-134">提交要求以啟用 Office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="509d1-134">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [<span data-ttu-id="509d1-135">註冊 Azure 訂閱以使用強制保留期間</span><span class="sxs-lookup"><span data-stu-id="509d1-135">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="509d1-136">註冊可以花一到五個工作日。</span><span class="sxs-lookup"><span data-stu-id="509d1-136">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="509d1-137">在每個訂閱中建立高級 Azure 金鑰 Vault</span><span class="sxs-lookup"><span data-stu-id="509d1-137">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="509d1-138">將許可權指派給每個金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="509d1-138">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="509d1-139">確定重要電子倉庫已啟用 soft delete</span><span class="sxs-lookup"><span data-stu-id="509d1-139">Make sure soft delete is enabled on your key vaults</span></span>](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [<span data-ttu-id="509d1-140">透過建立或匯入機碼，將機碼新增到每個機碼 vault</span><span class="sxs-lookup"><span data-stu-id="509d1-140">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="509d1-141">檢查機碼的恢復層級</span><span class="sxs-lookup"><span data-stu-id="509d1-141">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="509d1-142">備份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="509d1-142">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="509d1-143">驗證 Azure 金鑰 Vault 設定設定</span><span class="sxs-lookup"><span data-stu-id="509d1-143">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="509d1-144">取得每個 Azure 金鑰保存庫機碼的 URI</span><span class="sxs-lookup"><span data-stu-id="509d1-144">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="509d1-145">完成 Azure Key Vault 中的工作及客戶機碼的 Microsoft FastTrack</span><span class="sxs-lookup"><span data-stu-id="509d1-145">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="509d1-146">在 Azure Key Vault 中完成這些工作。</span><span class="sxs-lookup"><span data-stu-id="509d1-146">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="509d1-147">您必須針對所有與客戶金鑰搭配使用的 DEPs，完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="509d1-147">You'll need to complete these steps for all DEPs you use with Customer Key.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="509d1-148">建立兩個新的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="509d1-148">Create two new Azure subscriptions</span></span>

<span data-ttu-id="509d1-149">客戶金鑰需要兩個 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="509d1-149">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="509d1-150">最佳作法是 Microsoft 建議您建立新的 Azure 訂閱，以與客戶金鑰搭配使用。</span><span class="sxs-lookup"><span data-stu-id="509d1-150">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="509d1-151">Azure Key Vault 金鑰只可在相同 Azure Active Directory 中的應用程式授權 (Microsoft Azure Active Directory) 租使用者，您必須使用與 DEPs 將會指派之組織搭配使用的相同 Azure AD 租使用者來建立新的訂閱。</span><span class="sxs-lookup"><span data-stu-id="509d1-151">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned.</span></span> <span data-ttu-id="509d1-152">例如，在您的組織中使用具有全域系統管理員許可權的公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="509d1-152">For example, using your work or school account that has global administrator privileges in your organization.</span></span> <span data-ttu-id="509d1-153">如需詳細步驟，請參閱 [註冊 Azure 做為組織](/azure/active-directory/fundamentals/sign-up-organization)。</span><span class="sxs-lookup"><span data-stu-id="509d1-153">For detailed steps, see [Sign up for Azure as an organization](/azure/active-directory/fundamentals/sign-up-organization).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="509d1-154">客戶金鑰需要每個資料加密原則 (DEP) 的兩個金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-154">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="509d1-155">為了達到此目的，您必須建立兩個 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="509d1-155">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="509d1-156">建議的最佳作法是，您組織中的個別成員可以在每個訂閱中設定一個金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-156">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="509d1-157">您應只使用這些 Azure 訂閱來管理 Office 365 的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-157">You should only use these Azure subscriptions to administer encryption keys for Office 365.</span></span> <span data-ttu-id="509d1-158">這會保護您的組織，以防其中一個操作員意外、故意或惡意刪除，或 mismanages 其負責的金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-158">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="509d1-159">您可以為組織建立的 Azure 訂閱數目沒有實際的限制。</span><span class="sxs-lookup"><span data-stu-id="509d1-159">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="509d1-160">遵循這些最佳作法，可在協助管理客戶金鑰所使用的資源時，將人為錯誤所造成的影響降至最低。</span><span class="sxs-lookup"><span data-stu-id="509d1-160">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="509d1-161">提交要求以啟用 Office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="509d1-161">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="509d1-162">建立兩個新的 Azure 訂閱後，您必須在 [Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)中提交適當的客戶金鑰提供要求。</span><span class="sxs-lookup"><span data-stu-id="509d1-162">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="509d1-163">您在組織內針對授權的稱號所做的選擇，在您的組織中所做的選擇，對完成客戶金鑰註冊是很重要且必要的。</span><span class="sxs-lookup"><span data-stu-id="509d1-163">The selections that you make in the offer form about the authorized designations within your organization are critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="509d1-164">組織內所選角色中的監察官員會確定任何要求的真偽，以吊銷和銷毀所有與客戶金鑰資料加密原則搭配使用的金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-164">The officers in those selected roles within your organization ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="509d1-165">您需要針對您想要用於組織的每個客戶金鑰 DEP 類型執行一次此步驟。</span><span class="sxs-lookup"><span data-stu-id="509d1-165">You'll need to do this step once for each Customer Key DEP type that you intend to use for your organization.</span></span>

<span data-ttu-id="509d1-166">**FastTrack 小組不會向客戶金鑰提供協助。Office 365 只會使用 FastTrack 入口網站，讓您提交表單，並協助我們追蹤客戶金鑰的相關提供者。在您提交 FastTrack 要求之後，請向對應的客戶金鑰上架小組以啟動上架程式。**</span><span class="sxs-lookup"><span data-stu-id="509d1-166">**The FastTrack team doesn't provide assistance with Customer Key. Office 365 simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key. Once you've submitted the FastTrack request, reach out to the corresponding Customer Key onboarding team to start the onboarding process.**</span></span>
  
<span data-ttu-id="509d1-167">若要提交服務以啟用客戶金鑰，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="509d1-167">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="509d1-168">在您的組織中使用具有全域系統管理員許可權的公司或學校帳戶，登入 [Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="509d1-168">Using a work or school account that has global administrator permissions in your organization, sign in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="509d1-169">登入之後，請選取適當的網域。</span><span class="sxs-lookup"><span data-stu-id="509d1-169">Once you're logged in, select the appropriate domain.</span></span>

3. <span data-ttu-id="509d1-170">針對選取的網域，選擇上方導覽列中的 [ **要求服務** ]，並查看可用的提供方案清單。</span><span class="sxs-lookup"><span data-stu-id="509d1-170">For the selected domain, choose **Request services** from the top navigation bar, and review the list of available offers.</span></span>

4. <span data-ttu-id="509d1-171">選擇適用于您的優惠資訊卡片：</span><span class="sxs-lookup"><span data-stu-id="509d1-171">Choose the information card for the offer that applies to you:</span></span>

   - <span data-ttu-id="509d1-172">**多個 Microsoft 365 工作負載：** 選擇 Microsoft 365 提議的 **要求加密金鑰** 說明。</span><span class="sxs-lookup"><span data-stu-id="509d1-172">**Multiple Microsoft 365 workloads:** Choose the **Request encryption key help for Microsoft 365** offer.</span></span>

   - <span data-ttu-id="509d1-173">**Exchange Online 和商務用 Skype：** 選擇 Exchange 提議的 **要求加密金鑰** 說明。</span><span class="sxs-lookup"><span data-stu-id="509d1-173">**Exchange Online and Skype for Business:** Choose the **Request encryption key help for Exchange** offer.</span></span>

   - <span data-ttu-id="509d1-174">**SharePoint 線上、OneDrive 及 Teams 檔案：** 選擇 **SharePoint 和商務用 OneDrive 提供的要求加密金鑰** 說明。</span><span class="sxs-lookup"><span data-stu-id="509d1-174">**SharePoint Online, OneDrive, and Teams files:** Choose the **Request encryption key help for SharePoint and OneDrive for Business** offer.</span></span>

5. <span data-ttu-id="509d1-175">當您複習提供詳細資料之後，請選擇 [ **繼續] 步驟 2**。</span><span class="sxs-lookup"><span data-stu-id="509d1-175">Once you've reviewed the offer details, choose **Continue to step 2**.</span></span>

6. <span data-ttu-id="509d1-176">在 [服務] 表單上填寫所有適用的詳細資料和要求的資訊。</span><span class="sxs-lookup"><span data-stu-id="509d1-176">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="509d1-177">請特別注意您的組織中您要授權的監察官員，以核准加密金鑰和資料的永久和不可恢復的毀壞專案。</span><span class="sxs-lookup"><span data-stu-id="509d1-177">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="509d1-178">當您完成表單之後，請選擇 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="509d1-178">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="509d1-179">註冊 Azure 訂閱以使用強制保留期間</span><span class="sxs-lookup"><span data-stu-id="509d1-179">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="509d1-180">暫時或永久遺失根加密金鑰的功能可能會造成中斷，甚至可能造成資料遺失。</span><span class="sxs-lookup"><span data-stu-id="509d1-180">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="509d1-181">因此，與客戶金鑰搭配使用的資源需要加強保護。</span><span class="sxs-lookup"><span data-stu-id="509d1-181">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="509d1-182">與客戶金鑰搭配使用的所有 Azure 資源，除了預設設定之外，還提供保護機制。</span><span class="sxs-lookup"><span data-stu-id="509d1-182">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="509d1-183">您可以為 *強制保留期間* 標記或註冊 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="509d1-183">You can tag or register Azure subscriptions for a *mandatory retention period*.</span></span> <span data-ttu-id="509d1-184">強制保留期間可防止對您的 Azure 訂閱進行立即和不可撤銷的取消。</span><span class="sxs-lookup"><span data-stu-id="509d1-184">A mandatory retention period prevents immediate and irrevocable cancellation of your Azure subscription.</span></span> <span data-ttu-id="509d1-185">在必要保留期間內註冊 Azure 訂閱所需的步驟，需要與 Microsoft 365 小組共同作業。</span><span class="sxs-lookup"><span data-stu-id="509d1-185">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft 365 team.</span></span> <span data-ttu-id="509d1-186">此程式可能會花費一到五個工作日。</span><span class="sxs-lookup"><span data-stu-id="509d1-186">This process can take from one to five business days.</span></span> <span data-ttu-id="509d1-187">先前，強制保留期間有時稱為「不要取消」。</span><span class="sxs-lookup"><span data-stu-id="509d1-187">Previously, mandatory retention period was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="509d1-188">在聯繫 Microsoft 365 小組之前，您必須針對每個搭配客戶金鑰使用的 Azure 訂閱執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="509d1-188">Before contacting the Microsoft 365 team, you must do the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="509d1-189">開始之前，請確定您已安裝[Azure PowerShell Az](/powershell/azure/new-azureps-module-az)模組。</span><span class="sxs-lookup"><span data-stu-id="509d1-189">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="509d1-190">使用 Azure PowerShell 登入。</span><span class="sxs-lookup"><span data-stu-id="509d1-190">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="509d1-191">如需相關指示，請參閱[使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="509d1-191">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="509d1-192">執行 Register-AzProviderFeature Cmdlet 註冊您的訂閱，以使用強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="509d1-192">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="509d1-193">請針對每個訂閱完成此動作。</span><span class="sxs-lookup"><span data-stu-id="509d1-193">Complete this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="509d1-194">請與 Microsoft 聯繫完成此程式。</span><span class="sxs-lookup"><span data-stu-id="509d1-194">Contact Microsoft to complete the process.</span></span>

   - <span data-ttu-id="509d1-195">若要讓客戶用機碼指派 DEP 給個別的 Exchange Online 信箱，請與[exock@microsoft.com](mailto:exock@microsoft.com)聯繫。</span><span class="sxs-lookup"><span data-stu-id="509d1-195">For enabling Customer Key for assigning DEP to individual Exchange Online mailboxes, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span>

   - <span data-ttu-id="509d1-196">若要讓客戶機碼指派 DEPs 以加密 SharePoint 線上及商務用 OneDrive 內容 (包括所有租使用者的 Teams 檔案) ，請與[spock@microsoft.com](mailto:spock@microsoft.com)聯繫。</span><span class="sxs-lookup"><span data-stu-id="509d1-196">For enabling Customer Key for assigning DEPs to encrypt SharePoint Online and OneDrive for Business content (including Teams files) for all tenant users, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span>

   - <span data-ttu-id="509d1-197">若要讓客戶機碼指派 DEPs 以加密多個 Microsoft 365 工作負載的內容 (Exchange Online、Teams、MIP EDM) 針對所有租使用者，請與[m365-ck@service.microsoft.com](mailto:m365-ck@service.microsoft.com)聯繫。</span><span class="sxs-lookup"><span data-stu-id="509d1-197">For enabling Customer Key for assigning DEPs to encrypt content across multiple Microsoft 365 workloads (Exchange Online, Teams, MIP EDM) for all tenant users, contact [m365-ck@service.microsoft.com](mailto:m365-ck@service.microsoft.com).</span></span>

- <span data-ttu-id="509d1-198">在您的電子郵件中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="509d1-198">Include the following information in your email:</span></span>

   <span data-ttu-id="509d1-199">主旨 **：客戶** 金鑰\<*Your tenant's fully qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="509d1-199">**Subject**: Customer Key for \<*Your tenant's fully qualified domain name*\></span></span>

   <span data-ttu-id="509d1-200">本文 **：包括** 您要為其完成必要保留期間的訂閱 IDs，以及每個訂閱的 Get-AzProviderFeature 輸出。</span><span class="sxs-lookup"><span data-stu-id="509d1-200">**Body**:  Include the subscription IDs for which you want to complete the mandatory retention period  and the output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="509d1-201">完成此程式的服務等級協定 (SLA) 一天之後，Microsoft 會 (通知您已註冊訂閱，) 您已註冊訂閱，以使用強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="509d1-201">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="509d1-202">當您收到來自 Microsoft 的通知，表明已完成註冊後，請執行 Get-AzProviderFeature 命令，按下列方式，以確認註冊的狀態。</span><span class="sxs-lookup"><span data-stu-id="509d1-202">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="509d1-203">若驗證，Get-AzProviderFeature 命令會傳回登錄 **狀態** 屬性的 **註冊** 值。</span><span class="sxs-lookup"><span data-stu-id="509d1-203">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="509d1-204">請針對每個訂閱完成此步驟。</span><span class="sxs-lookup"><span data-stu-id="509d1-204">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="509d1-205">若要完成此程式，請執行 Register-AzResourceProvider 命令。</span><span class="sxs-lookup"><span data-stu-id="509d1-205">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="509d1-206">請針對每個訂閱完成此步驟。</span><span class="sxs-lookup"><span data-stu-id="509d1-206">Complete this step for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="509d1-207">在每個訂閱中建立高級 Azure 金鑰 Vault</span><span class="sxs-lookup"><span data-stu-id="509d1-207">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="509d1-208">建立主要 vault 的步驟會在[開始使用 Azure key vault](/azure/key-vault/general/overview)時記錄下來，可引導您完成安裝和啟動 Azure PowerShell、連線至 Azure 訂閱、建立資源群組，以及在該資源群組中建立金鑰 vault。</span><span class="sxs-lookup"><span data-stu-id="509d1-208">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="509d1-209">當您建立金鑰 vault 時，您必須選擇 SKU： [標準] 或 [進階版]。</span><span class="sxs-lookup"><span data-stu-id="509d1-209">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="509d1-210">Standard SKU 允許使用軟體來保護 Azure 金鑰保存庫金鑰-沒有硬體安全性模組 (HSM) 金鑰保護-而且進階版 SKU 允許使用 Hsm 來保護主要 Vault 金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-210">The Standard SKU allows Azure Key Vault keys to be protected with software - there's no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="509d1-211">客戶金鑰可接受使用任一 SKU 的金鑰電子倉庫，但 Microsoft 強烈建議您只使用進階版 sku。</span><span class="sxs-lookup"><span data-stu-id="509d1-211">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="509d1-212">使用任何一種類型之機碼的作業成本是相同的，所以每個受 HSM 保護的金鑰只會有每個月的成本差異。</span><span class="sxs-lookup"><span data-stu-id="509d1-212">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="509d1-213">如需詳細資訊，請參閱 [主要 Vault 定價](https://azure.microsoft.com/pricing/details/key-vault/) 。</span><span class="sxs-lookup"><span data-stu-id="509d1-213">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="509d1-214">針對實際執行資料使用進階版 SKU 金鑰保存庫和受保護金鑰的金鑰，只使用標準的 SKU 金鑰保管，以進行測試及驗證。</span><span class="sxs-lookup"><span data-stu-id="509d1-214">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="509d1-215">針對每個您要使用客戶金鑰的 Microsoft 365 服務，在您建立的兩個 Azure 訂閱中建立金鑰 vault。</span><span class="sxs-lookup"><span data-stu-id="509d1-215">For each Microsoft 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="509d1-216">例如，若要將 DEPs 用於 Exchange Online、SharePoint 線上及多工作負載案例，以啟用客戶金鑰，您將會建立三個成對的主要保存庫。</span><span class="sxs-lookup"><span data-stu-id="509d1-216">For example, to enable Customer Key to use DEPs for Exchange Online, SharePoint Online, and multi-workload scenarios, you'll create three pairs of key vaults.</span></span>
  
<span data-ttu-id="509d1-217">使用金鑰保管的命名慣例，以反映要與保存庫建立關聯的 DEP 預定用途。</span><span class="sxs-lookup"><span data-stu-id="509d1-217">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults.</span></span> <span data-ttu-id="509d1-218">如需命名慣例建議，請參閱下列最佳作法一節。</span><span class="sxs-lookup"><span data-stu-id="509d1-218">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="509d1-219">為每個資料加密原則建立一組成對的保險集。</span><span class="sxs-lookup"><span data-stu-id="509d1-219">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="509d1-220">針對 Exchange Online，當您將原則指派給信箱時，會選取資料加密原則的範圍。</span><span class="sxs-lookup"><span data-stu-id="509d1-220">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="509d1-221">信箱只會指派一個原則，而且您可以建立最多50個原則。</span><span class="sxs-lookup"><span data-stu-id="509d1-221">A mailbox can have only one policy assigned, and you can create up to 50 policies.</span></span> <span data-ttu-id="509d1-222">SharePoint 線上原則的範圍包括地理位置或 _地理_ 位置中組織內的所有資料。</span><span class="sxs-lookup"><span data-stu-id="509d1-222">The scope of a SharePoint Online policy includes all of the data within an organization in a geographic location, or _geo_.</span></span> <span data-ttu-id="509d1-223">多重工作負載原則的範圍包括所有使用者支援之工作負載中的所有資料。</span><span class="sxs-lookup"><span data-stu-id="509d1-223">The scope for a multi-workload policy includes all of the data across the supported workloads for all users.</span></span>

<span data-ttu-id="509d1-224">建立機碼 vault 也需要建立 Azure 資源群組，因為若啟用，主要電子倉庫需要儲存容量 (，) 但若啟用，也會產生儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="509d1-224">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="509d1-225">最佳作法是 Microsoft 建議使用個別的系統管理員管理每個資源群組，並將其與一組系統管理員搭配使用，以管理所有相關客戶的重要資源。</span><span class="sxs-lookup"><span data-stu-id="509d1-225">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration that's aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="509d1-226">若要使可用性最大化，請將主要存放庫放在接近 Microsoft 365 服務的區域中（例如，如果您的 Exchange Online 組織在北美，請將您的主要電子倉庫放在北美）。</span><span class="sxs-lookup"><span data-stu-id="509d1-226">To maximize availability, place your key vaults in regions close to your Microsoft 365 service For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="509d1-227">如果您的 Exchange Online 組織位於歐洲，請將主要存放庫放在歐洲。</span><span class="sxs-lookup"><span data-stu-id="509d1-227">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span>
>
> <span data-ttu-id="509d1-228">使用主要 vault 的一般前置詞，並包含主要存放區和機碼的使用和範圍的縮寫， (例如，針對存放庫在北美地區所用的 contoso SharePoint 服務，可能的一組名稱為 contoso-CK-na-na-VaultA1 和 contoso-CK--VaultA2。</span><span class="sxs-lookup"><span data-stu-id="509d1-228">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-CK-SP-NA-VaultA1 and Contoso-CK-SP-NA-VaultA2.</span></span> <span data-ttu-id="509d1-229">保存庫名稱是 Azure 內全域唯一的字串，因此，您可能需要嘗試所需名稱的變化，以防其他 Azure 客戶已索取所需的名稱。</span><span class="sxs-lookup"><span data-stu-id="509d1-229">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="509d1-230">從2017年7月的電子倉庫名稱無法變更，因此最佳作法是使用書面計畫進行安裝，然後使用第二個人驗證計畫是否正確執行。</span><span class="sxs-lookup"><span data-stu-id="509d1-230">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>
>
> <span data-ttu-id="509d1-231">如果可能，請在非成對區域中建立您的電子倉庫。</span><span class="sxs-lookup"><span data-stu-id="509d1-231">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="509d1-232">配對的 Azure 區域可提供跨服務失敗網域的高可用性。</span><span class="sxs-lookup"><span data-stu-id="509d1-232">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="509d1-233">因此，區域配對可以視為彼此的備份區域。</span><span class="sxs-lookup"><span data-stu-id="509d1-233">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="509d1-234">這表示位於某個地區的 Azure 資源會透過成對區域自動取得容錯。</span><span class="sxs-lookup"><span data-stu-id="509d1-234">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="509d1-235">基於此原因，針對在地區是成對的資料加密原則中所使用的兩個保存庫選擇地區時，只會使用兩個可用區域的可用性。</span><span class="sxs-lookup"><span data-stu-id="509d1-235">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="509d1-236">大多數地理有兩個地區，所以尚不能選取非成對區域。</span><span class="sxs-lookup"><span data-stu-id="509d1-236">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="509d1-237">如有可能，請選擇兩個不成對的區域，以用於資料加密原則的兩個保存庫。</span><span class="sxs-lookup"><span data-stu-id="509d1-237">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="509d1-238">其優點是共有四個地區的可用性。</span><span class="sxs-lookup"><span data-stu-id="509d1-238">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="509d1-239">如需詳細資訊，請參閱 [Business 持續性和嚴重損壞修復 (BCDR) ： Azure 成對區域](/azure/best-practices-availability-paired-regions) 的目前區域配對清單。</span><span class="sxs-lookup"><span data-stu-id="509d1-239">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="509d1-240">將許可權指派給每個金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="509d1-240">Assign permissions to each key vault</span></span>

<span data-ttu-id="509d1-241">根據您的實施，您必須為每個金鑰保存庫定義三組不同的許可權。</span><span class="sxs-lookup"><span data-stu-id="509d1-241">You'll need to define three separate sets of permissions for each key vault, depending on your implementation.</span></span> <span data-ttu-id="509d1-242">例如，您必須為下列各項專案定義一組許可權：</span><span class="sxs-lookup"><span data-stu-id="509d1-242">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="509d1-243">**主要 vault 管理員** ，可對您的組織進行重要 vault 的日常管理工作。</span><span class="sxs-lookup"><span data-stu-id="509d1-243">**Key vault administrators** that do day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="509d1-244">這些工作包括備份、建立、取得、匯入、清單及還原。</span><span class="sxs-lookup"><span data-stu-id="509d1-244">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="509d1-245">指派給主要 vault 管理員的許可權集不包含刪除金鑰的許可權。</span><span class="sxs-lookup"><span data-stu-id="509d1-245">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="509d1-246">這是故意和重要的作法。</span><span class="sxs-lookup"><span data-stu-id="509d1-246">This is intentional and an important practice.</span></span> <span data-ttu-id="509d1-247">刪除加密金鑰通常不會這麼做，因為這樣做會永久銷毀資料。</span><span class="sxs-lookup"><span data-stu-id="509d1-247">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="509d1-248">根據預設，請勿將此許可權授與主要 vault 管理員的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="509d1-248">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="509d1-249">相反地，針對主要 vault 投稿人保留這種情況，而且只要清楚瞭解對結果的瞭解，就只需在短期內將其指派給系統管理員。</span><span class="sxs-lookup"><span data-stu-id="509d1-249">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="509d1-250">若要將這些許可權指派給組織中的使用者，請使用 Azure PowerShell 登入您的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="509d1-250">To assign these permissions to a user in your organization, sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="509d1-251">如需相關指示，請參閱[使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="509d1-251">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="509d1-252">執行 Set-AzKeyVaultAccessPolicy Cmdlet 指派必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="509d1-252">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="509d1-253">例如：</span><span class="sxs-lookup"><span data-stu-id="509d1-253">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="509d1-254">可以變更 Azure Key Vault 自身許可權的 **主要 vault 參與者**。</span><span class="sxs-lookup"><span data-stu-id="509d1-254">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="509d1-255">您必須在員工離職或加入您的小組時，變更這些許可權。</span><span class="sxs-lookup"><span data-stu-id="509d1-255">You'll need to change these permissions as employees leave or join your team.</span></span> <span data-ttu-id="509d1-256">在極少數的情況下，主要 vault 管理員合法需要刪除或還原機碼的許可權，您也需要變更許可權。</span><span class="sxs-lookup"><span data-stu-id="509d1-256">In the rare situation that the key vault administrators legitimately need permission to delete or restore a key you'll also need to change the permissions.</span></span> <span data-ttu-id="509d1-257">這組重要的 vault 投稿人員必須授與主要 vault 上的 **投稿** 人角色。</span><span class="sxs-lookup"><span data-stu-id="509d1-257">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="509d1-258">您可以使用 Azure 資源管理員指派此角色。</span><span class="sxs-lookup"><span data-stu-id="509d1-258">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="509d1-259">如需詳細步驟，請參閱 [Use Role-Based Access Control，以管理您的 Azure 訂閱資源的存取權](/azure/active-directory/role-based-access-control-configure)。</span><span class="sxs-lookup"><span data-stu-id="509d1-259">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="509d1-260">建立訂閱的系統管理員會隱含此存取權，以及將其他管理員指派給參與者角色的能力。</span><span class="sxs-lookup"><span data-stu-id="509d1-260">The administrator who creates a subscription has this access implicitly, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="509d1-261">**Microsoft 365 應用程式的許可權**，以供客戶金鑰使用之每個主要保管區，您必須授與對應 Microsoft 365 服務主體的 wrapKey、unwrapKey 和 get 許可權。</span><span class="sxs-lookup"><span data-stu-id="509d1-261">**Permissions to Microsoft 365 applications** for every key vault that you use for Customer Key, you need to give wrapKey, unwrapKey, and get permissions to the corresponding Microsoft 365 Service Principal.</span></span> 

<span data-ttu-id="509d1-262">若要授與 Microsoft 365 服務主體的許可權，請使用下列語法執行 **AzKeyVaultAccessPolicy** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="509d1-262">To give permission to Microsoft 365 Service Principal, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="509d1-263">其中：</span><span class="sxs-lookup"><span data-stu-id="509d1-263">Where:</span></span>

   - <span data-ttu-id="509d1-264">*保存庫名稱* 是您建立的主要 vault 名稱。</span><span class="sxs-lookup"><span data-stu-id="509d1-264">*vault name* is the name of the key vault you created.</span></span>
   - <span data-ttu-id="509d1-265">若為 Exchange Online 和商務用 Skype，請將 *Office 365 appID* 取代為`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="509d1-265">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
   - <span data-ttu-id="509d1-266">如需 SharePoint 線上、商務用 OneDrive 及 Teams 檔案，請將 *Office 365 appID* 取代為`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="509d1-266">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
   - <span data-ttu-id="509d1-267">針對多工作負載原則 (Exchange、Teams、MIP EDM) 適用于所有租使用者的使用者，請將 *Office 365 appID* 取代為`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="509d1-267">For multi-workload policy (Exchange, Teams, MIP EDM) that applies to all tenant users, replace *Office 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  <span data-ttu-id="509d1-268">範例：設定 Exchange Online 和商務用 Skype 的許可權：</span><span class="sxs-lookup"><span data-stu-id="509d1-268">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="509d1-269">範例：設定 SharePoint 線上、商務用 OneDrive 及 Teams 檔案的許可權：</span><span class="sxs-lookup"><span data-stu-id="509d1-269">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a><span data-ttu-id="509d1-270">確定重要電子倉庫已啟用 soft delete</span><span class="sxs-lookup"><span data-stu-id="509d1-270">Make sure soft delete is enabled on your key vaults</span></span>

<span data-ttu-id="509d1-271">當您可以快速復原金鑰時，由於意外或惡意刪除的金鑰，您很可能會因意外或惡意刪除的金鑰而經歷長時間的服務中斷。</span><span class="sxs-lookup"><span data-stu-id="509d1-271">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="509d1-272">啟用此設定（稱為「虛刪除」），才能搭配客戶機碼使用金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-272">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="509d1-273">啟用 [虛刪除] 可讓您在刪除90天內復原金鑰或存放庫，而不需要從備份中還原。</span><span class="sxs-lookup"><span data-stu-id="509d1-273">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="509d1-274">若要在金鑰保存庫上啟用虛刪除，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="509d1-274">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="509d1-275">使用 Windows PowerShell 登入您的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="509d1-275">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="509d1-276">如需相關指示，請參閱[使用 Azure PowerShell 登入](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="509d1-276">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="509d1-277">執行 [AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="509d1-277">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="509d1-278">在此範例中， *vault 名稱* 是您要啟用 soft delete 之主要 vault 的名稱：</span><span class="sxs-lookup"><span data-stu-id="509d1-278">In this example, *vault name* is the name of the key vault for which you're enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="509d1-279">執行 **AzKeyVault** 指令程式，確認已為金鑰保存庫設定 soft delete。</span><span class="sxs-lookup"><span data-stu-id="509d1-279">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="509d1-280">如果已正確設定 key vault 的 [虛刪除]，則 _Soft Delete Enabled_ 屬性會傳回 **True** 值：</span><span class="sxs-lookup"><span data-stu-id="509d1-280">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="509d1-281">透過建立或匯入機碼，將機碼新增到每個機碼 vault</span><span class="sxs-lookup"><span data-stu-id="509d1-281">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="509d1-282">有兩種方法可以將機碼新增到 Azure Key Vault;您可以直接在 Key Vault 中建立金鑰，也可以匯入金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-282">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="509d1-283">直接在 Key Vault 中建立金鑰會變得更複雜，但匯入金鑰可讓您控制如何產生機碼的整體。</span><span class="sxs-lookup"><span data-stu-id="509d1-283">Creating a key directly in Key Vault is less complicated, but importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="509d1-284">使用 RSA 機碼。</span><span class="sxs-lookup"><span data-stu-id="509d1-284">Use the RSA keys.</span></span> <span data-ttu-id="509d1-285">Azure 金鑰 Vault 不支援使用橢圓曲線鍵進行換行及解換。</span><span class="sxs-lookup"><span data-stu-id="509d1-285">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="509d1-286">若要直接在金鑰保存庫中建立金鑰，請執行 AzKeyVaultKey 指令 [程式](/powershell/module/az.keyvault/add-azkeyvaultkey) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="509d1-286">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="509d1-287">其中：</span><span class="sxs-lookup"><span data-stu-id="509d1-287">Where:</span></span>

- <span data-ttu-id="509d1-288">*vault 名稱* 是您要在其中建立機碼的金鑰 vault 名稱。</span><span class="sxs-lookup"><span data-stu-id="509d1-288">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="509d1-289">*key name* 是您要給予新機碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="509d1-289">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="509d1-290">使用主要保險檔的上述命名慣例，以前面所述的名稱慣例命名機碼。</span><span class="sxs-lookup"><span data-stu-id="509d1-290">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="509d1-291">如此一來，在僅顯示金鑰名稱的工具中，該字串是自我描述的。</span><span class="sxs-lookup"><span data-stu-id="509d1-291">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="509d1-292">如果您想要使用 HSM 來保護機碼，請確定您將 **hsm** 指定為 _Destination_ 參數的值，否則請指定 **軟體**。</span><span class="sxs-lookup"><span data-stu-id="509d1-292">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="509d1-293">例如：</span><span class="sxs-lookup"><span data-stu-id="509d1-293">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="509d1-294">若要將機碼直接匯入到金鑰保存庫，您必須具有 nCipher nShield 硬體安全性模組。</span><span class="sxs-lookup"><span data-stu-id="509d1-294">To import a key directly into your key vault, you need to have a nCipher nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="509d1-295">有些組織喜歡使用此方法來建立其機碼的 provenance，然後此方法也會提供下列 attestations：</span><span class="sxs-lookup"><span data-stu-id="509d1-295">Some organizations prefer this approach to establish the provenance of their keys, and then this method also provides the following attestations:</span></span>
  
- <span data-ttu-id="509d1-296">用於匯入的工具組包括 nCipher 的證明，金鑰 Exchange 金鑰 (KEK) 用來加密您所產生的金鑰無法匯出，而且會在 nCipher 所生產的正版 HSM 內產生。</span><span class="sxs-lookup"><span data-stu-id="509d1-296">The toolset used for import includes attestation from nCipher that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by nCipher.</span></span>

- <span data-ttu-id="509d1-297">工具組包含從 nCipher 證明，Azure 金鑰 Vault 安全性世界也會在 nCipher 所生產的正版 HSM 上產生。</span><span class="sxs-lookup"><span data-stu-id="509d1-297">The toolset includes attestation from nCipher that the Azure Key Vault security world was also generated on a genuine HSM manufactured by nCipher.</span></span> <span data-ttu-id="509d1-298">此認證證明 Microsoft 也在使用正版 nCipher 硬體。</span><span class="sxs-lookup"><span data-stu-id="509d1-298">This attestation proves that Microsoft is also using genuine nCipher hardware.</span></span>

<span data-ttu-id="509d1-299">請與您的安全性群組核實，以判斷是否需要上述 attestations。</span><span class="sxs-lookup"><span data-stu-id="509d1-299">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="509d1-300">如需建立主要內部部署並將其匯入金鑰保存庫的詳細步驟，請參閱 how [to 針對 Azure Key vault 產生及轉移受保護性保護的金鑰](/azure/key-vault/keys/hsm-protected-keys)。</span><span class="sxs-lookup"><span data-stu-id="509d1-300">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys).</span></span> <span data-ttu-id="509d1-301">使用 Azure 指示在每個金鑰保存庫中建立金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-301">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="509d1-302">檢查機碼的恢復層級</span><span class="sxs-lookup"><span data-stu-id="509d1-302">Check the recovery level of your keys</span></span>

<span data-ttu-id="509d1-303">Microsoft 365 要求 Azure Key Vault 訂閱設定為 [請勿取消]，且客戶機碼使用的金鑰已啟用 [虛刪除]。</span><span class="sxs-lookup"><span data-stu-id="509d1-303">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="509d1-304">您可以查看您機碼上的復原層級，以確認訂閱設定。</span><span class="sxs-lookup"><span data-stu-id="509d1-304">You can confirm you subscriptions settings by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="509d1-305">若要檢查機碼的復原層級，請在 Azure PowerShell 中執行 Get-AzKeyVaultKey Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="509d1-305">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="509d1-306">若 _Recovery Level_ 屬性傳回的值不是 [可復原 **+ ProtectedSubscription**] 的值，請確定您已將訂閱置於 [不取消取消] 清單中，而且您已在每個金鑰存放庫上啟用虛刪除。</span><span class="sxs-lookup"><span data-stu-id="509d1-306">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, ensure that you have put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="509d1-307">備份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="509d1-307">Back up Azure Key Vault</span></span>

<span data-ttu-id="509d1-308">立即建立或變更索引鍵，執行備份及儲存備份的備份，不論是線上還是離線。</span><span class="sxs-lookup"><span data-stu-id="509d1-308">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="509d1-309">不要將離線副本連線到任何網路。</span><span class="sxs-lookup"><span data-stu-id="509d1-309">Don't connect offline copies to any network.</span></span> <span data-ttu-id="509d1-310">請改為將它們儲存在離線位置，例如在實體安全或商務儲存設施中。</span><span class="sxs-lookup"><span data-stu-id="509d1-310">Instead store them in an offline location, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="509d1-311">至少應有一個備份副本儲存在發生嚴重損壞時可存取的位置。</span><span class="sxs-lookup"><span data-stu-id="509d1-311">At least one copy of the backup should be stored in a location that will be accessible if a disaster occurs.</span></span> <span data-ttu-id="509d1-312">備份 blob 是一種還原重要材料的唯一方法，應永久銷毀主要 Vault 金鑰，否則無法使用。</span><span class="sxs-lookup"><span data-stu-id="509d1-312">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="509d1-313">Azure Key Vault 外部的金鑰和匯入到 Azure Key Vault 的金鑰不會做為備份，因為客戶金鑰使用金鑰所需的中繼資料並不存在於外部金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-313">Keys that are external to Azure Key Vault and imported to Azure Key Vault don't qualify as a backup because the metadata necessary for Customer Key to use the key doesn't exist with the external key.</span></span> <span data-ttu-id="509d1-314">只有從 Azure 金鑰保存庫取得的備份可用於使用客戶金鑰進行還原作業。</span><span class="sxs-lookup"><span data-stu-id="509d1-314">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="509d1-315">因此，您必須在上傳或建立金鑰之後，建立 Azure 金鑰 Vault 的備份。</span><span class="sxs-lookup"><span data-stu-id="509d1-315">Therefore, you must create a backup of Azure Key Vault after you upload or create a key.</span></span>
  
<span data-ttu-id="509d1-316">若要建立 Azure Key Vault 機碼的備份，請執行 [AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="509d1-316">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="509d1-317">確定您的輸出檔案使用尾碼 `.backup` 。</span><span class="sxs-lookup"><span data-stu-id="509d1-317">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="509d1-318">由此 Cmdlet 所產生的輸出檔已加密，且無法用於 Azure Key Vault 之外。</span><span class="sxs-lookup"><span data-stu-id="509d1-318">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="509d1-319">備份只能還原至執行備份的來源 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="509d1-319">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="509d1-320">針對輸出檔，選擇您的保存庫名稱和機碼名稱的組合。</span><span class="sxs-lookup"><span data-stu-id="509d1-320">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="509d1-321">這會使檔案名自我描述。</span><span class="sxs-lookup"><span data-stu-id="509d1-321">This will make the file name self-describing.</span></span> <span data-ttu-id="509d1-322">它也會確定備份檔案名稱不會發生衝突。</span><span class="sxs-lookup"><span data-stu-id="509d1-322">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="509d1-323">例如：</span><span class="sxs-lookup"><span data-stu-id="509d1-323">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="509d1-324">驗證 Azure 金鑰 Vault 設定設定</span><span class="sxs-lookup"><span data-stu-id="509d1-324">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="509d1-325">使用 DEP 中的金鑰之前進行驗證是選用的，但是強烈建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="509d1-325">Validating before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="509d1-326">如果您使用步驟來設定您的金鑰和電子倉庫（本文所述除外），請先驗證 Azure 金鑰 Vault 資源的健康情況，再設定客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-326">If you use steps to set up your keys and vaults other than the ones described in this article, validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="509d1-327">若要確認您的金鑰具有 `get` 、 `wrapKey` 和 `unwrapKey` 作業已啟用：</span><span class="sxs-lookup"><span data-stu-id="509d1-327">To verify that your keys have `get`, `wrapKey`, and `unwrapKey` operations enabled:</span></span>
  
<span data-ttu-id="509d1-328">執行 [AzKeyVault 指令程式](/powershell/module/az.keyvault/get-azkeyvault) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="509d1-328">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="509d1-329">在 [輸出] 中，視需要尋找存取原則及 Exchange Online 身分識別 (guid) 或 SharePoint Online 身分識別 (guid) 。</span><span class="sxs-lookup"><span data-stu-id="509d1-329">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="509d1-330">上述所有三個許可權都必須顯示在 [索引鍵的許可權] 底下。</span><span class="sxs-lookup"><span data-stu-id="509d1-330">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="509d1-331">如果存取原則設定不正確，請執行 Set-AzKeyVaultAccessPolicy Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="509d1-331">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="509d1-332">例如，針對 Exchange Online 和商務用 Skype：</span><span class="sxs-lookup"><span data-stu-id="509d1-332">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="509d1-333">例如，對於線上 SharePoint 和商務用 OneDrive：</span><span class="sxs-lookup"><span data-stu-id="509d1-333">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="509d1-334">若要確認您的機碼未設定到期日，請執行 [AzKeyVaultKey 指令程式](/powershell/module/az.keyvault/get-azkeyvault) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="509d1-334">To verify that an expiration date isn't set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="509d1-335">客戶金鑰不能使用到期金鑰。</span><span class="sxs-lookup"><span data-stu-id="509d1-335">Customer Key can't use an expired key.</span></span> <span data-ttu-id="509d1-336">使用到期金鑰所嘗試的作業會失敗，而且可能會造成服務中斷。</span><span class="sxs-lookup"><span data-stu-id="509d1-336">Operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="509d1-337">強烈建議使用與客戶金鑰搭配使用的金鑰沒有到期日。</span><span class="sxs-lookup"><span data-stu-id="509d1-337">We strongly recommend that keys used with Customer Key don't have an expiration date.</span></span> <span data-ttu-id="509d1-338">到期日一經設定，便無法移除，但可以變更為不同的日期。</span><span class="sxs-lookup"><span data-stu-id="509d1-338">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="509d1-339">如果必須使用具有到期日期設定的金鑰，請將 [到期] 值變更為12/31/9999。</span><span class="sxs-lookup"><span data-stu-id="509d1-339">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="509d1-340">到期日期設定為12/31/9999 以外的日期，將不會通過 Microsoft 365 驗證。</span><span class="sxs-lookup"><span data-stu-id="509d1-340">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="509d1-341">若要變更已設定為12/31/9999 以外任何值的到期日，請執行 AzKeyVaultKey 指令 [程式](/powershell/module/az.keyvault/update-azkeyvaultkey) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="509d1-341">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="509d1-342">請勿設定與客戶金鑰搭配使用的加密金鑰上的到期日期。</span><span class="sxs-lookup"><span data-stu-id="509d1-342">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="509d1-343">取得每個 Azure 金鑰保存庫機碼的 URI</span><span class="sxs-lookup"><span data-stu-id="509d1-343">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="509d1-344">在您設定好金鑰保存庫並新增金鑰之後，請執行下列命令，以取得每個金鑰保存庫中的金鑰 URI。</span><span class="sxs-lookup"><span data-stu-id="509d1-344">Once you've set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="509d1-345">當您稍後建立並指派每個 DEP 時，您將會使用這些 URIs，因此請將此資訊儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="509d1-345">You'll use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="509d1-346">請對每個金鑰保存庫執行一次此命令。</span><span class="sxs-lookup"><span data-stu-id="509d1-346">Run this command once for each key vault.</span></span>
  
<span data-ttu-id="509d1-347">在 Azure PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="509d1-347">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a><span data-ttu-id="509d1-348">後續步驟</span><span class="sxs-lookup"><span data-stu-id="509d1-348">Next steps</span></span>

<span data-ttu-id="509d1-349">完成本文中的步驟之後，即可建立及指派 DEPs。</span><span class="sxs-lookup"><span data-stu-id="509d1-349">Once you've completed the steps in this article, you're ready to create and assign DEPs.</span></span> <span data-ttu-id="509d1-350">如需相關指示，請參閱 [管理客戶金鑰](customer-key-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="509d1-350">For instructions, see [Manage Customer Key](customer-key-manage.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="509d1-351">相關文章</span><span class="sxs-lookup"><span data-stu-id="509d1-351">Related articles</span></span>

- [<span data-ttu-id="509d1-352">客戶金鑰服務加密</span><span class="sxs-lookup"><span data-stu-id="509d1-352">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="509d1-353">管理客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="509d1-353">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="509d1-354">滾動或旋轉客戶金鑰或可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="509d1-354">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="509d1-355">深入瞭解可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="509d1-355">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="509d1-356">服務加密</span><span class="sxs-lookup"><span data-stu-id="509d1-356">Service Encryption</span></span>](office-365-service-encryption.md)