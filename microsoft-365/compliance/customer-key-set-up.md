---
title: 設定 Office 365 的客戶金鑰
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 瞭解如何設定適用于 Exchange Online、商務用 Skype、SharePoint 線上、商務 OneDrive 及小組檔案的 Office 365 客戶金鑰。
ms.openlocfilehash: af3ade4ed411a390d1501d3f3fe15ba3111e14d3
ms.sourcegitcommit: 7bb340f6b47378bcd1c6e770dc975931470bbc26
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/10/2020
ms.locfileid: "43225940"
---
# <a name="set-up-customer-key-for-office-365"></a><span data-ttu-id="fcaf9-103">設定 Office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="fcaf9-103">Set up Customer Key for Office 365</span></span>

<span data-ttu-id="fcaf9-104">使用客戶金鑰，您可以控制組織的加密金鑰，然後設定 Office 365，以使用這些金鑰在 Microsoft 資料中心內加密您的資料。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-104">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="fcaf9-105">換句話說，客戶金鑰可讓客戶新增屬於其金鑰的加密層級。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-105">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="fcaf9-106">存放的資料包括 Exchange Online 資料和儲存在信箱的商務用 Skype 資料，以及儲存在 SharePoint Online 中和商務用 OneDrive 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-106">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="fcaf9-107">您必須先設定 Azure，才能使用 Office 365 的客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-107">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="fcaf9-108">本主題說明建立及設定必要 Azure 資源所需遵循的步驟，並提供在 Office 365 中設定客戶機碼的步驟。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-108">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="fcaf9-109">完成 Azure 安裝之後，您可以決定要將哪些原則指派給組織中的信箱和檔案，進而決定要指派哪些機碼。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-109">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="fcaf9-110">您未指派原則的信箱和檔案會使用由 Microsoft 所控制和管理的加密原則。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-110">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="fcaf9-111">如需客戶機碼的相關資訊，或有關一般概述，請參閱[Office 365 中的客戶金鑰服務加密](customer-key-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-111">For more information about Customer Key, or for a general overview, see [Service encryption with Customer Key in Office 365](customer-key-overview.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fcaf9-112">強烈建議您遵循本主題中的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-112">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="fcaf9-113">這些是以**TIP**和**重要**的方式呼叫。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-113">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="fcaf9-114">客戶金鑰可讓您控制根加密金鑰，其範圍可以像整個組織一樣大。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-114">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="fcaf9-115">這表示對這些機碼所做的錯誤可能會產生很大的影響，而且可能會導致服務中斷或資料遺失。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-115">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span>
  
## <a name="before-you-set-up-customer-key"></a><span data-ttu-id="fcaf9-116">在您設定客戶機碼之前</span><span class="sxs-lookup"><span data-stu-id="fcaf9-116">Before you set up Customer Key</span></span>

<span data-ttu-id="fcaf9-117">開始之前，請先確定您的組織具有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-117">Before you get started, ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="fcaf9-118">從 office 365 的2020年4月1日開始，于 office 365 E5，M365 E5，M365 E5 規範，以及 M365 E5 & 控管 SKUs 中提供的資訊保護。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-118">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="fcaf9-119">Office 365 Advanced 相容性 SKU 已無法再提供購置新的授權。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-119">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="fcaf9-120">現有的 Office 365 Advanced 相容性授權會繼續受到支援。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-120">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span>

<span data-ttu-id="fcaf9-121">若要瞭解本主題中的概念和程式，請參閱[Azure Key Vault](https://docs.microsoft.com/azure/key-vault/)檔。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-121">To understand the concepts and procedures in this topic, review the [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) documentation.</span></span> <span data-ttu-id="fcaf9-122">此外，熟悉 Azure 中使用的條款，例如[AZURE AD 租](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)使用者。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-122">Also, become familiar with the terms used in Azure, for example, [Azure AD tenant](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).</span></span>

<span data-ttu-id="fcaf9-123">FastTrack 僅用於收集用於註冊客戶金鑰所需的承租人和服務設定資訊。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-123">FastTrack is only used to collect the required tenant and service configuration information used to register for Customer Key.</span></span> <span data-ttu-id="fcaf9-124">客戶金鑰提供方案是透過 FastTrack 發佈，讓您與我們的協力廠商可以方便您與我們的合作夥伴使用相同方法提交必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-124">The Customer Key Offers are published via FastTrack so that it is convenient for you and our partners to submit the required information using the same method.</span></span> <span data-ttu-id="fcaf9-125">FastTrack 也可讓您輕鬆地封存您在提供中提供的資料。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-125">FastTrack also makes it easy to archive the data that you provide in the Offer.</span></span>
  
<span data-ttu-id="fcaf9-126">如果您需要檔以外的其他支援，請與 Microsoft 諮詢服務（MCS）、Premier Field 工程學（PFE）或 Microsoft 合作夥伴取得協助。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-126">If you need additional support beyond the documentation, contact Microsoft Consulting Services (MCS), Premier Field Engineering (PFE), or a Microsoft partner for assistance.</span></span> <span data-ttu-id="fcaf9-127">若要提供對客戶機碼的意見反應（包括檔），請將您的想法、建議和觀點傳送至 customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-127">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions, and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-steps-to-set-up-customer-key"></a><span data-ttu-id="fcaf9-128">設定客戶機碼的步驟概述</span><span class="sxs-lookup"><span data-stu-id="fcaf9-128">Overview of steps to set up Customer Key</span></span>

<span data-ttu-id="fcaf9-129">若要設定客戶機碼，請依所列順序完成這些工作。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-129">To set up Customer Key, complete these tasks in the listed order.</span></span> <span data-ttu-id="fcaf9-130">本文的其餘部分提供每項工作的詳細指示，或連結至程式中每個步驟的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-130">The rest of this article provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="fcaf9-131">**在 Azure 和 Microsoft FastTrack：**</span><span class="sxs-lookup"><span data-stu-id="fcaf9-131">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="fcaf9-132">您可以遠端連線至 Azure PowerShell，以完成大部分的工作。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-132">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="fcaf9-133">為了獲得最佳結果，請使用版本4.4.0 或更新版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-133">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="fcaf9-134">建立兩個新的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="fcaf9-134">Create two new Azure subscriptions</span></span>](#create-two-new-azure-subscriptions)

- [<span data-ttu-id="fcaf9-135">註冊 Azure 訂閱以使用強制保留期間</span><span class="sxs-lookup"><span data-stu-id="fcaf9-135">Register Azure subscriptions to use a mandatory retention period</span></span>](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  <span data-ttu-id="fcaf9-136">註冊可以花一到五個工作日。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-136">Registration can take from one to five business days.</span></span>

- [<span data-ttu-id="fcaf9-137">提交要求以啟用 Office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="fcaf9-137">Submit a request to activate Customer Key for Office 365</span></span>](#submit-a-request-to-activate-customer-key-for-office-365)

<span data-ttu-id="fcaf9-138">建立兩個新的 Azure 訂閱後，您必須完成 Microsoft FastTrack 入口網站中主控的 web 表單，以提交適當的客戶金鑰提供要求。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-138">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="fcaf9-139">**FastTrack 小組不會向客戶金鑰提供協助。Office 只會使用 FastTrack 入口網站，讓您提交表單，並協助我們追蹤客戶金鑰的相關提供**者。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-139">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>

- [<span data-ttu-id="fcaf9-140">在每個訂閱中建立高級 Azure 金鑰 Vault</span><span class="sxs-lookup"><span data-stu-id="fcaf9-140">Create a premium Azure Key Vault in each subscription</span></span>](#create-a-premium-azure-key-vault-in-each-subscription)

- [<span data-ttu-id="fcaf9-141">將許可權指派給每個金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="fcaf9-141">Assign permissions to each key vault</span></span>](#assign-permissions-to-each-key-vault)

- [<span data-ttu-id="fcaf9-142">在金鑰保存庫上啟用然後確認虛刪除</span><span class="sxs-lookup"><span data-stu-id="fcaf9-142">Enable and then confirm soft delete on your key vaults</span></span>](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [<span data-ttu-id="fcaf9-143">透過建立或匯入機碼，將機碼新增到每個機碼 vault</span><span class="sxs-lookup"><span data-stu-id="fcaf9-143">Add a key to each key vault either by creating or importing a key</span></span>](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [<span data-ttu-id="fcaf9-144">檢查機碼的恢復層級</span><span class="sxs-lookup"><span data-stu-id="fcaf9-144">Check the recovery level of your keys</span></span>](#check-the-recovery-level-of-your-keys)

- [<span data-ttu-id="fcaf9-145">備份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="fcaf9-145">Back up Azure Key Vault</span></span>](#back-up-azure-key-vault)

- [<span data-ttu-id="fcaf9-146">驗證 Azure 金鑰 Vault 設定設定</span><span class="sxs-lookup"><span data-stu-id="fcaf9-146">Validate Azure Key Vault configuration settings</span></span>](#validate-azure-key-vault-configuration-settings)

- [<span data-ttu-id="fcaf9-147">取得每個 Azure 金鑰保存庫機碼的 URI</span><span class="sxs-lookup"><span data-stu-id="fcaf9-147">Obtain the URI for each Azure Key Vault key</span></span>](#obtain-the-uri-for-each-azure-key-vault-key)

<span data-ttu-id="fcaf9-148">**在 Office 365 中：**</span><span class="sxs-lookup"><span data-stu-id="fcaf9-148">**In Office 365:**</span></span>
  
<span data-ttu-id="fcaf9-149">Exchange Online 和商務用 Skype：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-149">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="fcaf9-150">建立資料加密原則（DEP）以搭配 Exchange Online 和商務用 Skype 使用</span><span class="sxs-lookup"><span data-stu-id="fcaf9-150">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [<span data-ttu-id="fcaf9-151">將 DEP 指派給信箱</span><span class="sxs-lookup"><span data-stu-id="fcaf9-151">Assign a DEP to a mailbox</span></span>](#assign-a-dep-to-a-mailbox)

- [<span data-ttu-id="fcaf9-152">驗證信箱加密</span><span class="sxs-lookup"><span data-stu-id="fcaf9-152">Validate mailbox encryption</span></span>](#validate-mailbox-encryption)

<span data-ttu-id="fcaf9-153">SharePoint 線上和商務 OneDrive：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-153">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="fcaf9-154">為商務地區的每一個 SharePoint 線上和 OneDrive 建立資料加密原則（DEP）</span><span class="sxs-lookup"><span data-stu-id="fcaf9-154">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [<span data-ttu-id="fcaf9-155">驗證 SharePoint Online、商務 OneDrive 及小組檔案的檔案加密</span><span class="sxs-lookup"><span data-stu-id="fcaf9-155">Validate file encryption for SharePoint Online, OneDrive for Business, and Teams files</span></span>](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="fcaf9-156">完成 Azure Key Vault 中的工作及客戶機碼的 Microsoft FastTrack</span><span class="sxs-lookup"><span data-stu-id="fcaf9-156">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>

<span data-ttu-id="fcaf9-157">在 Azure Key Vault 中完成這些工作。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-157">Complete these tasks in Azure Key Vault.</span></span> <span data-ttu-id="fcaf9-158">您必須完成這些步驟，不論您是否想要為 Exchange Online 和商務用 Skype、商務用 Skype OneDrive SharePoint，或是 Office 365 中的所有支援服務，都設定客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-158">You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or for SharePoint Online, OneDrive for Business, and Teams files, or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="fcaf9-159">建立兩個新的 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="fcaf9-159">Create two new Azure subscriptions</span></span>

<span data-ttu-id="fcaf9-160">客戶金鑰需要兩個 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-160">Customer Key requires two Azure subscriptions.</span></span> <span data-ttu-id="fcaf9-161">最佳作法是 Microsoft 建議您建立新的 Azure 訂閱，以與客戶金鑰搭配使用。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-161">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="fcaf9-162">Azure Key Vault 金鑰只可對相同 Azure Active Directory （AAD）租使用者中的應用程式授權，您必須使用與您的 Office 365 組織一起使用的相同 Azure AD 租使用者，來建立新的訂閱，以 DEPs 將會被指派。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-162">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned.</span></span> <span data-ttu-id="fcaf9-163">例如，在您的 Office 365 組織中使用具有全域系統管理員許可權的公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-163">For example, using your work or school account that has global administrator privileges in your Office 365 organization.</span></span> <span data-ttu-id="fcaf9-164">如需詳細步驟，請參閱[註冊 Azure 做為組織](https://azure.microsoft.com/documentation/articles/sign-up-organization/)。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-164">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fcaf9-165">客戶金鑰需要每個資料加密原則（DEP）的兩個金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-165">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="fcaf9-166">為了達到此目的，您必須建立兩個 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-166">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="fcaf9-167">建議的最佳作法是，您組織中的個別成員可以在每個訂閱中設定一個金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-167">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="fcaf9-168">此外，這些 Azure 訂閱只應該用來管理 Office 365 的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-168">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="fcaf9-169">這會保護您的組織，以防其中一個操作員意外、故意或惡意刪除，或 mismanages 其負責的金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-169">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="fcaf9-170">建議您設定只用于管理 Azure 金鑰 Vault 資源的新 Azure 訂閱，以與客戶金鑰搭配使用。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-170">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="fcaf9-171">您可以為組織建立的 Azure 訂閱數目沒有實際的限制。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-171">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="fcaf9-172">遵循這些最佳作法，可在協助管理客戶金鑰所使用的資源時，將人為錯誤所造成的影響降至最低。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-172">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="fcaf9-173">提交要求以啟用 Office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="fcaf9-173">Submit a request to activate Customer Key for Office 365</span></span>

<span data-ttu-id="fcaf9-174">當您完成 Azure 步驟之後，您必須在[Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)中提交提供要求。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-174">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="fcaf9-175">當您透過 FastTrack 網頁入口網站提交要求之後，Microsoft 會驗證 Azure 金鑰 Vault 設定資料和您所提供的連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-175">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="fcaf9-176">您在 [服務] 表單中對組織的授權官員所做的選擇，對完成客戶金鑰註冊很重要且必要。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-176">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="fcaf9-177">您在表單中所選取的組織官員將用來確保任何要求吊銷和銷毀所有與客戶金鑰資料加密原則搭配使用的金鑰的真偽。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-177">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="fcaf9-178">您必須執行此步驟一次，以啟用 Exchange Online 和商務用 Skype 覆蓋服務的客戶金鑰，以及啟用 SharePoint 線上和商務 OneDrive 之客戶金鑰的第二次。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-178">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="fcaf9-179">若要提交服務以啟用客戶金鑰，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-179">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="fcaf9-180">使用 Office 365 組織中具有全域系統管理員許可權的公司或學校帳戶登入[Microsoft FastTrack 入口網站](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-180">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>

2. <span data-ttu-id="fcaf9-181">登入之後，請流覽至**儀表板**。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-181">Once you're logged in, browse to the **Dashboard**.</span></span>

3. <span data-ttu-id="fcaf9-182">選擇 [**提供**]，並查看目前的提供方案清單。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-182">Choose **Offers**, and review the list of current offers.</span></span>

4. <span data-ttu-id="fcaf9-183">選擇 [**深入瞭解**]，以瞭解適用于您的產品：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-183">Choose **Learn More** for the offer that applies to you:</span></span>

   - <span data-ttu-id="fcaf9-184">**Exchange Online 和商務用 Skype：** 選擇 [**深入瞭解**Exchange 提供的**客戶金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-184">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span>

   - <span data-ttu-id="fcaf9-185">**SharePoint 線上、商務 OneDrive 及小組檔案：** 選擇 [**深入瞭解** **SharePoint 的客戶金鑰和商務用 OneDrive** ] 提供。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-185">**SharePoint Online, OneDrive for Business, and Teams files:** Choose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span>

5. <span data-ttu-id="fcaf9-186">在 [**提供詳細資料**] 頁面上，選擇 [**建立要求**]。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-186">On the **Offer details** page, choose **Create Request**.</span></span>

6. <span data-ttu-id="fcaf9-187">在 [服務] 表單上填寫所有適用的詳細資料和要求的資訊。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-187">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="fcaf9-188">請特別注意您的組織中您要授權的監察官員，以核准加密金鑰和資料的永久和不可恢復的毀壞專案。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-188">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="fcaf9-189">當您完成表單之後，請選擇 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-189">Once you've completed the form, choose **Submit**.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="fcaf9-190">註冊 Azure 訂閱以使用強制保留期間</span><span class="sxs-lookup"><span data-stu-id="fcaf9-190">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="fcaf9-191">暫時或永久遺失根加密金鑰可能是非常中斷或甚至是服務運作的嚴重損壞，而且可能會導致資料遺失。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-191">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="fcaf9-192">因此，與客戶金鑰搭配使用的資源需要加強保護。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-192">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="fcaf9-193">與客戶金鑰搭配使用的所有 Azure 資源，除了預設設定之外，還提供保護機制。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-193">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="fcaf9-194">您可以使用 Azure 訂閱進行標記或註冊，以防止立即和不可撤銷的取消。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-194">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="fcaf9-195">這稱為註冊強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-195">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="fcaf9-196">在必要保留期間內註冊 Azure 訂閱所需的步驟，需要與 Office 365 小組共同作業。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-196">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team.</span></span> <span data-ttu-id="fcaf9-197">此程式可能會花費一到五個工作日。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-197">This process can take from one to five business days.</span></span> <span data-ttu-id="fcaf9-198">先前，這有時候稱為「不要取消」。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-198">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="fcaf9-199">在聯繫 Office 365 小組之前，您必須針對每個用客戶金鑰使用的 Azure 訂閱執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-199">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="fcaf9-200">開始之前，請確定您已安裝[Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az)模組。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-200">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>
  
1. <span data-ttu-id="fcaf9-201">使用 Azure PowerShell 登入。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-201">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="fcaf9-202">如需相關指示，請參閱[使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-202">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="fcaf9-203">執行 AzProviderFeature 指令程式，註冊您的訂閱，以使用強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-203">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="fcaf9-204">針對每個訂閱執行此動作。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-204">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.KeyVault
   ```

3. <span data-ttu-id="fcaf9-205">請與 Microsoft 聯繫以完成流程。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-205">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="fcaf9-206">如需商務小組的 SharePoint 和 OneDrive，請與[spock@microsoft.com](mailto:spock@microsoft.com)聯繫。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-206">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="fcaf9-207">若為 Exchange Online 和商務用 Skype，請與[exock@microsoft.com](mailto:exock@microsoft.com)聯繫。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-207">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="fcaf9-208">在您的電子郵件中包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-208">Include the following in your email:</span></span>

   <span data-ttu-id="fcaf9-209">**Subject**： \<*您租使用者的完整功能變數名稱*的客戶金鑰\></span><span class="sxs-lookup"><span data-stu-id="fcaf9-209">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="fcaf9-210">**Body**：訂閱 IDs，您想要完成其強制保留期間。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-210">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="fcaf9-211">每個訂閱的 AzProviderFeature 輸出。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-211">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="fcaf9-212">完成此程式的服務等級協定（SLA）是一天之後，Microsoft 會收到（並驗證）您已註冊訂閱，以使用強制保留期間的工作。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-212">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="fcaf9-213">當您收到 Microsoft 的通知，表明已完成註冊後，請執行 AzProviderFeature 命令，以驗證註冊的狀態，如下所示。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-213">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="fcaf9-214">若驗證，AzProviderFeature 命令會傳回註冊**狀態**內容的**註冊**值。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-214">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="fcaf9-215">針對每個訂閱執行此動作。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-215">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="fcaf9-216">若要完成此程式，請執行 AzResourceProvider 命令。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-216">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="fcaf9-217">針對每個訂閱執行此動作。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-217">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="fcaf9-218">在每個訂閱中建立高級 Azure 金鑰 Vault</span><span class="sxs-lookup"><span data-stu-id="fcaf9-218">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="fcaf9-219">建立主要 vault 的步驟會在[開始使用 Azure Key vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)時記錄下來，可引導您安裝及啟動 azure PowerShell、連線至 azure 訂閱、建立資源群組，以及在該資源群組中建立金鑰 vault。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="fcaf9-220">當您建立金鑰 vault 時，您必須選擇 SKU： [標準] 或 [特優]。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-220">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="fcaf9-221">Standard SKU 允許使用軟體來保護 Azure 金鑰保存庫金鑰-沒有硬體安全性模組（HSM）金鑰保護-而且特優 SKU 允許使用 Hsm 來保護主要 Vault 金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-221">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="fcaf9-222">客戶金鑰可接受使用任一 SKU 的金鑰電子倉庫，但 Microsoft 強烈建議您只使用特優 SKU。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-222">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="fcaf9-223">使用任何一種類型之機碼的作業成本是相同的，所以每個受 HSM 保護的金鑰只會有每個月的成本差異。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-223">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="fcaf9-224">如需詳細資訊，請參閱[主要 Vault 定價](https://azure.microsoft.com/pricing/details/key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-224">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fcaf9-225">針對實際執行資料使用特優 SKU 金鑰保存庫和受版權保護的金鑰，只使用標準的 SKU 金鑰保存庫和金鑰進行測試和驗證。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>
  
<span data-ttu-id="fcaf9-226">針對每個您將使用客戶金鑰的 Office 365 服務，在您建立的兩個 Azure 訂閱中建立金鑰 vault。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-226">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="fcaf9-227">例如，僅限 Exchange Online 和商務用 Skype 或 SharePoint 線上和 OneDrive 僅供商務用，只會建立一對的保險集。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-227">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="fcaf9-228">若要同時對 Exchange Online 和 SharePoint 啟用客戶金鑰，您會建立兩組主要保險電子倉庫。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-228">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="fcaf9-229">使用金鑰保管的命名慣例，以反映用來與保存庫產生關聯之資料加密原則的預定用途。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-229">Use a naming convention for key vaults that reflects the intended use of the data encryption policy with which you will associate the vaults.</span></span> <span data-ttu-id="fcaf9-230">如需命名慣例建議，請參閱下列最佳作法一節。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-230">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="fcaf9-231">為每個資料加密原則建立一組成對的保險集。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-231">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="fcaf9-232">若為 Exchange Online，當您將原則指派給信箱時，會選取資料加密原則的範圍。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-232">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="fcaf9-233">信箱只會指派一個原則，而且您可以建立最多50個原則。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-233">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="fcaf9-234">針對 SharePoint Online，原則的範圍是地理位置或_地理_位置中組織內的所有資料。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-234">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or _geo_.</span></span>

<span data-ttu-id="fcaf9-235">建立機碼 Vault 也需要建立 Azure 資源群組，因為重要電子倉庫需要儲存容量（雖然非常小）和重要存放區記錄，如果啟用，也會產生儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-235">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="fcaf9-236">最佳作法是 Microsoft 建議使用個別的系統管理員管理每個資源群組，並將系統管理員與管理所有相關客戶金鑰資源的系統管理員對齊。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-236">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fcaf9-237">若要使可用性最大化，您的主要電子倉庫應該位於 Office 365 服務的地區附近。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-237">To maximize availability, your key vaults should be in regions close to your Office 365 service.</span></span> <span data-ttu-id="fcaf9-238">例如，如果您的 Exchange Online 組織位於北美，請將您的主要電子倉庫放在北美。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-238">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="fcaf9-239">如果您的 Exchange Online 組織在歐洲，請將您的主要存放庫放在歐洲。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-239">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="fcaf9-240">使用主要保管區的一般前置詞，並包含主要存放區和機碼的使用和範圍的縮寫（例如，存放庫在北美使用的 Contoso SharePoint 服務）、可能的名稱對為 Contoso-O365SP-NA-NA-na-na-NA-NA-NA-NA-NA。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-240">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="fcaf9-241">保存庫名稱是 Azure 內全域唯一的字串，因此，您可能需要嘗試所需名稱的變化，以防其他 Azure 客戶已索取所需的名稱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-241">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="fcaf9-242">從2017年7月的電子倉庫名稱無法變更，因此最佳作法是使用書面計畫進行安裝，然後使用第二個人驗證計畫是否正確執行。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-242">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="fcaf9-243">如果可能，請在非成對區域中建立您的電子倉庫。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-243">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="fcaf9-244">配對的 Azure 區域可提供跨服務失敗網域的高可用性。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-244">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="fcaf9-245">因此，區域配對可以視為彼此的備份區域。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-245">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="fcaf9-246">這表示位於某個地區的 Azure 資源會透過成對區域自動取得容錯。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-246">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="fcaf9-247">基於此原因，針對在地區是成對的資料加密原則中所使用的兩個保存庫選擇地區時，只會使用兩個可用區域的可用性。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-247">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="fcaf9-248">大多數地理有兩個地區，所以尚不能選取非成對區域。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-248">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="fcaf9-249">如有可能，請選擇兩個不成對的區域，以用於資料加密原則的兩個保存庫。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-249">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="fcaf9-250">其優點是共有四個地區的可用性。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-250">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="fcaf9-251">如需詳細資訊，請參閱[商務持續性和嚴重損壞修復（BCDR）：](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)目前區域配對清單的 Azure 成對區域。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-251">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="fcaf9-252">將許可權指派給每個金鑰保存庫</span><span class="sxs-lookup"><span data-stu-id="fcaf9-252">Assign permissions to each key vault</span></span>

<span data-ttu-id="fcaf9-253">針對每個金鑰保存庫，您必須根據您的實施，為客戶機碼定義三組不同的許可權。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-253">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="fcaf9-254">例如，您必須為下列各項專案定義一組許可權：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-254">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="fcaf9-255">**主要 vault 系統管理員**，會針對您的組織執行重要 vault 的日常管理。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-255">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="fcaf9-256">這些工作包括備份、建立、取得、匯入、清單及還原。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-256">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="fcaf9-257">指派給主要 vault 管理員的許可權集不包含刪除金鑰的許可權。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-257">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="fcaf9-258">這是故意和重要的作法。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-258">This is intentional and an important practice.</span></span> <span data-ttu-id="fcaf9-259">刪除加密金鑰通常不會這麼做，因為這樣做會永久銷毀資料。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-259">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="fcaf9-260">根據預設，請勿將此許可權授與主要 vault 管理員的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-260">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="fcaf9-261">相反地，針對主要 vault 投稿人保留這種情況，而且只要清楚瞭解對結果的瞭解，就只需在短期內將其指派給系統管理員。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-261">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="fcaf9-262">若要將這些許可權指派給 Office 365 組織中的使用者，請使用 Azure PowerShell 登入您的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-262">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="fcaf9-263">如需相關指示，請參閱[使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-263">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

- <span data-ttu-id="fcaf9-264">執行 AzKeyVaultAccessPolicy Cmdlet 以指派必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-264">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="fcaf9-265">例如：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-265">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="fcaf9-266">可以變更 Azure Key Vault 自身許可權的**主要 vault 參與者**。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-266">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="fcaf9-267">您必須變更這些許可權，因為員工離職或加入您的小組，或在極少的情況下，主要 vault 管理員合法需要刪除或還原金鑰的許可權。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-267">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="fcaf9-268">這組重要的 vault 投稿人員必須授與主要 vault 上的**投稿**人角色。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-268">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="fcaf9-269">您可以使用 Azure 資源管理員指派此角色。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-269">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="fcaf9-270">如需詳細步驟，請參閱[Use Role-Based Access Control，以管理您的 Azure 訂閱資源的存取權](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-270">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="fcaf9-271">建立訂閱的系統管理員會隱含此存取權，以及將其他管理員指派給參與者角色的能力。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-271">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="fcaf9-272">如果您想要使用客戶金鑰搭配 Exchange Online 和商務用 Skype，您必須授與 Office 365 的許可權，以代表 Exchange Online 和商務用 Skype 使用金鑰 vault。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-272">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="fcaf9-273">同樣地，如果您想要使用客戶金鑰與 SharePoint 線上且 OneDrive 商務用，您必須新增 Office 365 的許可權，才能代表 SharePoint 線上及 OneDrive 的商務用金鑰 vault。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-273">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="fcaf9-274">若要授與 Office 365 的許可權，請使用下列語法執行**AzKeyVaultAccessPolicy** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-274">To give permission to Office 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   <span data-ttu-id="fcaf9-275">其中：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-275">Where:</span></span>

    - <span data-ttu-id="fcaf9-276">*保存庫名稱*是您建立的主要 vault 名稱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-276">*vault name* is the name of the key vault you created.</span></span>

    - <span data-ttu-id="fcaf9-277">若為 Exchange Online 和商務用 Skype，請將*Office 365 appID*取代為`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="fcaf9-277">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>

    - <span data-ttu-id="fcaf9-278">如需 SharePoint 線上、商務和團隊檔案的 OneDrive，請將*Office 365 appID*取代為`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="fcaf9-278">For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>

  <span data-ttu-id="fcaf9-279">範例：設定 Exchange Online 和商務用 Skype 的許可權：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-279">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  <span data-ttu-id="fcaf9-280">範例：設定 SharePoint Online、商務 OneDrive 及小組檔案的許可權：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-280">Example: Setting permissions for SharePoint Online, OneDrive for Business, and Teams files:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="fcaf9-281">在金鑰保存庫上啟用然後確認虛刪除</span><span class="sxs-lookup"><span data-stu-id="fcaf9-281">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="fcaf9-282">當您可以快速復原金鑰時，由於意外或惡意刪除的金鑰，您很可能會因意外或惡意刪除的金鑰而經歷長時間的服務中斷。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-282">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="fcaf9-283">您必須啟用此設定，稱為「虛刪除」，才能使用您的金鑰與客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-283">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="fcaf9-284">啟用 [虛刪除] 可讓您在刪除90天內復原金鑰或存放庫，而不需要從備份中還原。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-284">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="fcaf9-285">若要在金鑰保存庫上啟用虛刪除，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-285">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="fcaf9-286">使用 Windows PowerShell 登入您的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-286">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="fcaf9-287">如需相關指示，請參閱[使用 Azure PowerShell 登入](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-287">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="fcaf9-288">執行[AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-288">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="fcaf9-289">在此範例中，*保存庫名稱*是您要啟用 soft delete 之主要 vault 的名稱：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-289">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="fcaf9-290">執行**AzKeyVault**指令程式，確認已為金鑰保存庫設定 soft delete。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-290">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="fcaf9-291">如果已正確設定 key vault 的 [虛刪除]，則_Soft Delete Enabled_屬性會傳回**True**值：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-291">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="fcaf9-292">透過建立或匯入機碼，將機碼新增到每個機碼 vault</span><span class="sxs-lookup"><span data-stu-id="fcaf9-292">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="fcaf9-293">有兩種方法可以將機碼新增到 Azure Key Vault;您可以直接在 Key Vault 中建立金鑰，也可以匯入金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-293">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="fcaf9-294">直接在 Key Vault 中建立金鑰是不夠複雜的方法，而匯入金鑰會提供如何產生機碼的整體控制權。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-294">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="fcaf9-295">若要直接在金鑰保存庫中建立金鑰，請執行 AzKeyVaultKey 指令[程式](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey)，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-295">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="fcaf9-296">其中：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-296">Where:</span></span>

- <span data-ttu-id="fcaf9-297">*vault 名稱*是您要在其中建立機碼的金鑰 vault 名稱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-297">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="fcaf9-298">*key name*是您要給予新機碼的名稱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-298">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="fcaf9-299">使用主要保險檔的上述命名慣例，以前面所述的名稱慣例命名機碼。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-299">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="fcaf9-300">如此一來，在僅顯示金鑰名稱的工具中，該字串是自我描述的。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-300">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
- <span data-ttu-id="fcaf9-301">如果您想要使用 HSM 來保護機碼，請確定您將**hsm**指定為_Destination_參數的值，否則請指定**軟體**。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-301">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="fcaf9-302">For example,</span><span class="sxs-lookup"><span data-stu-id="fcaf9-302">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="fcaf9-303">若要將機碼直接匯入到金鑰保存庫，您必須具有 Thales nShield 硬體安全性模組。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-303">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="fcaf9-304">有些組織喜歡使用此方法來建立其機碼的 provenance，此外，此方法也會提供下列專案：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-304">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="fcaf9-305">用於匯入的工具集包括 Thales 中的證明，用來加密您所產生之機碼的金鑰交換金鑰（KEK）不可匯出，而且會在 Thales 所生產的正版 HSM 內產生。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-305">The tool set used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>

- <span data-ttu-id="fcaf9-306">工具集包括 Thales 中的證明，該軟體會在 Thales 生產實際的 HSM 上同時產生 Azure 金鑰 Vault 安全性。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-306">The tool set includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales.</span></span> <span data-ttu-id="fcaf9-307">此認證會向您證明 Microsoft 也在使用正版 Thales 硬體。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-307">This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>

<span data-ttu-id="fcaf9-308">請與您的安全性群組核實，以判斷是否需要上述 attestations。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-308">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="fcaf9-309">如需建立主要內部部署並將其匯入金鑰保存庫的詳細步驟，請參閱 how [to 針對 Azure Key vault 產生及轉移受保護性保護的金鑰](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-309">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="fcaf9-310">使用 Azure 指示在每個金鑰保存庫中建立金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-310">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="fcaf9-311">檢查機碼的恢復層級</span><span class="sxs-lookup"><span data-stu-id="fcaf9-311">Check the recovery level of your keys</span></span>

<span data-ttu-id="fcaf9-312">Office 365 要求 Azure Key Vault 訂閱設定為 [未取消]，且客戶機碼使用的金鑰已啟用 [虛刪除]。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-312">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="fcaf9-313">您可以查看金鑰上的復原層級，確認這一點。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-313">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="fcaf9-314">若要檢查機碼的復原層級，請在 Azure PowerShell 中執行 AzKeyVaultKey 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-314">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="fcaf9-315">若_Recovery Level_屬性傳回的值不是可復原的 **+ ProtectedSubscription**，您必須複查此主題，並確定您已遵循將訂閱置於 [不取消取消] 清單中的所有步驟，而且您已在每個主要存放庫上啟用虛刪除。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-315">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="back-up-azure-key-vault"></a><span data-ttu-id="fcaf9-316">備份 Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="fcaf9-316">Back up Azure Key Vault</span></span>

<span data-ttu-id="fcaf9-317">立即建立或變更索引鍵，執行備份及儲存備份的備份，不論是線上還是離線。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-317">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="fcaf9-318">離線副本不應該連接至任何網路，例如在實體安全或商務儲存設施中。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-318">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="fcaf9-319">至少應有一個備份副本儲存在發生嚴重損壞時可存取的位置。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-319">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="fcaf9-320">備份 blob 是一種還原重要材料的唯一方法，應永久銷毀主要 Vault 金鑰，否則無法使用。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-320">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="fcaf9-321">Azure Key Vault 外部的金鑰和匯入到 Azure Key Vault 的金鑰不會做為備份，因為客戶金鑰使用金鑰所需的中繼資料不存在於外部金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-321">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="fcaf9-322">只有從 Azure 金鑰保存庫取得的備份可用於使用客戶金鑰進行還原作業。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-322">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="fcaf9-323">因此，請務必在上傳或建立金鑰時進行 Azure 金鑰 Vault 的備份。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-323">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="fcaf9-324">若要建立 Azure Key Vault 機碼的備份，請執行[AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-324">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="fcaf9-325">確定您的輸出檔案使用尾碼`.backup`。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-325">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="fcaf9-326">由此 Cmdlet 所產生的輸出檔已加密，且無法用於 Azure Key Vault 之外。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-326">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="fcaf9-327">備份只能還原至執行備份的來源 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-327">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="fcaf9-328">針對輸出檔，選擇您的保存庫名稱和機碼名稱的組合。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-328">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="fcaf9-329">這會使檔案名自我描述。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-329">This will make the file name self-describing.</span></span> <span data-ttu-id="fcaf9-330">它也會確定備份檔案名稱不會發生衝突。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-330">It will also ensure that backup file names do not collide.</span></span>
  
<span data-ttu-id="fcaf9-331">例如：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-331">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="fcaf9-332">驗證 Azure 金鑰 Vault 設定設定</span><span class="sxs-lookup"><span data-stu-id="fcaf9-332">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="fcaf9-333">在 DEP 中使用金鑰之前執行驗證是選用的，但是強烈建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-333">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="fcaf9-334">尤其是，如果您使用步驟來設定您的金鑰和保險庫（如本主題所述），您應該先驗證 Azure 金鑰 Vault 資源的健康情況，再設定客戶金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-334">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="fcaf9-335">若要確認您的機碼已啟用 get、wrapKey 及 unwrapKey 作業，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-335">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="fcaf9-336">執行[AzKeyVault 指令程式](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-336">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="fcaf9-337">在輸出中，視需要尋找存取原則和 Exchange Online 身分識別（GUID）或 SharePoint Online 身分識別（GUID）。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-337">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="fcaf9-338">上述所有三個許可權都必須顯示在 [索引鍵的許可權] 底下。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-338">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="fcaf9-339">如果存取原則設定不正確，請執行 AzKeyVaultAccessPolicy 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-339">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="fcaf9-340">例如，對於 Exchange Online 和商務用 Skype：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-340">For example, for Exchange Online and Skype for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="fcaf9-341">例如，針對 SharePoint 線上和商務 OneDrive：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-341">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="fcaf9-342">若要確認您機碼的到期日未設定，請執行[AzKeyVaultKey 指令程式](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-342">To verify that an expiration date is not set for your keys run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="fcaf9-343">已到期的金鑰無法由客戶金鑰使用，而且嘗試使用到期金鑰會失敗，而且可能會造成服務中斷。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-343">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="fcaf9-344">強烈建議使用與客戶金鑰搭配使用的金鑰沒有到期日。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-344">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="fcaf9-345">到期日一經設定，便無法移除，但可以變更為不同的日期。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-345">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="fcaf9-346">如果必須使用具有到期日期設定的金鑰，請將 [到期] 值變更為12/31/9999。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-346">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="fcaf9-347">到期日期設定為12/31/9999 以外的金鑰，將不會通過 Office 365 驗證。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-347">Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="fcaf9-348">若要變更已設定為12/31/9999 以外任何值的到期日，請執行 AzKeyVaultKey 指令[程式](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey)，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-348">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="fcaf9-349">請勿設定與客戶金鑰搭配使用的加密金鑰上的到期日期。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-349">Don't set expiration dates on encryption keys you use with Customer Key.</span></span>
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="fcaf9-350">取得每個 Azure 金鑰保存庫機碼的 URI</span><span class="sxs-lookup"><span data-stu-id="fcaf9-350">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="fcaf9-351">當您在 Azure 中完成所有步驟以設定金鑰保存庫並新增金鑰之後，請執行下列命令，以取得每個 key vault 中的金鑰的 URI。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-351">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="fcaf9-352">當您稍後建立並指派每個 DEP 時，您將需要使用這些 URIs，因此請將此資訊儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-352">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="fcaf9-353">請記得對每一個按鍵 vault 執行一次此指令。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-353">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="fcaf9-354">Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fcaf9-354">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="fcaf9-355">Office 365：設定 Exchange Online 和商務用 Skype 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="fcaf9-355">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="fcaf9-356">開始之前，請確定您已完成設定 Azure Key Vault 所需的工作。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-356">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="fcaf9-357">如需詳細資訊，請參閱[Azure Key Vault 和 Microsoft FastTrack 中的完成](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key)工作。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-357">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="fcaf9-358">若要為 Exchange Online 和商務用 Skype 設定客戶金鑰，您需要透過 Windows PowerShell 以遠端方式連線至 Exchange Online，以執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-358">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="fcaf9-359">建立資料加密原則（DEP）以搭配 Exchange Online 和商務用 Skype 使用</span><span class="sxs-lookup"><span data-stu-id="fcaf9-359">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>

<span data-ttu-id="fcaf9-360">DEP 與儲存在 Azure Key Vault 中的一組機碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-360">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="fcaf9-361">您為 Office 365 中的信箱指派 DEP。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-361">You assign a DEP to a mailbox in Office 365.</span></span> <span data-ttu-id="fcaf9-362">然後，Office 365 會使用原則中所識別的金鑰來加密信箱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-362">Office 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="fcaf9-363">若要建立 DEP，您需要有先前取得的主要 Vault URIs。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-363">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="fcaf9-364">如需相關指示，請參閱[取得每個 Azure Key Vault 金鑰的 URI](#obtain-the-uri-for-each-azure-key-vault-key) 。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-364">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="fcaf9-365">記得！</span><span class="sxs-lookup"><span data-stu-id="fcaf9-365">Remember!</span></span> <span data-ttu-id="fcaf9-366">當您建立 DEP 時，請指定位於兩個不同 Azure 金鑰電子倉庫中的兩個金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-366">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="fcaf9-367">請確定這些機碼位於兩個不同的 Azure 地區，以確保異地冗余。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-367">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="fcaf9-368">若要建立 DEP，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-368">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="fcaf9-369">在您的本機電腦上，使用 Office 365 組織中具有全域系統管理員許可權的工作或學校帳戶，以開啟 Windows PowerShell 並執行下列命令，[以連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) 。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-369">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) by opening Windows PowerShell and running the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="fcaf9-370">在 [Windows PowerShell 憑證要求] 對話方塊中，輸入您的工作或學校帳戶資訊，按一下 **[確定]**，然後輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-370">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span>

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="fcaf9-371">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-371">Run the following command.</span></span>

   ```powershell
   Import-PSSession $Session
   ```

4. <span data-ttu-id="fcaf9-372">若要建立 DEP，請輸入下列命令，以使用 DataEncryptionPolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-372">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="fcaf9-373">其中：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-373">Where:</span></span>

   - <span data-ttu-id="fcaf9-374">*PolicyName*是您要用於原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-374">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="fcaf9-375">名稱不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-375">Names cannot contain spaces.</span></span> <span data-ttu-id="fcaf9-376">例如，USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-376">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="fcaf9-377">*原則描述*是一種使用者易記的原則描述，可協助您記起原則的用途。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-377">*Policy Description* is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="fcaf9-378">您可以在描述中包含空格。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-378">You can include spaces in the description.</span></span> <span data-ttu-id="fcaf9-379">例如，「美國信箱的根鍵和其區域」。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-379">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="fcaf9-380">*KeyVaultURI1*是原則中第一個索引鍵的 URI。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-380">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="fcaf9-381">例如，https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-381">For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span>

   - <span data-ttu-id="fcaf9-382">*KeyVaultURI2*是原則中的第二個索引鍵的 URI。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-382">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="fcaf9-383">例如，https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-383">For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02.</span></span> <span data-ttu-id="fcaf9-384">以逗號和空格分隔兩個 URIs。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-384">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="fcaf9-385">範例：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-385">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="fcaf9-386">將 DEP 指派給信箱</span><span class="sxs-lookup"><span data-stu-id="fcaf9-386">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="fcaf9-387">使用 Set-Mailbox Cmdlet 將 DEP 指派給信箱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-387">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="fcaf9-388">一旦您指派原則之後，Office 365 便可使用 DEP 中指定的金鑰來加密信箱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-388">Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="fcaf9-389">其中*MailboxIdParameter*會指定信箱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-389">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="fcaf9-390">如需 Set-Mailbox Cmdlet 的詳細資訊，請參閱[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-390">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="fcaf9-391">驗證信箱加密</span><span class="sxs-lookup"><span data-stu-id="fcaf9-391">Validate mailbox encryption</span></span>

<span data-ttu-id="fcaf9-392">加密信箱可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-392">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="fcaf9-393">第一次原則指派時，信箱也必須完全從一個資料庫移至另一個資料庫，此服務才能加密信箱。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-393">For first time policy assignment, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="fcaf9-394">建議您先等候72小時，再嘗試在變更 DEP 後，或第一次將 DEP 指派給信箱之後，再嘗試驗證加密。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-394">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="fcaf9-395">使用 Get-MailboxStatistics Cmdlet 來判斷信箱是否已加密。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-395">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="fcaf9-396">如果信箱已加密，IsEncrypted 屬性會傳回**true**值，如果信箱未加密，則傳回**false**的值。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-396">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="fcaf9-397">完成信箱移動的時間取決於您第一次指派 DEP 的信箱數目，以及信箱的大小。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-397">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="fcaf9-398">如果信箱在您指派 DEP 的時間之後未從一周進行加密，請與 Microsoft 聯繫。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-398">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="fcaf9-399">Office 365：設定 SharePoint Online、商務 OneDrive 及小組檔案的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="fcaf9-399">Office 365: Setting up Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="fcaf9-400">開始之前，請確定您已完成設定 Azure Key Vault 所需的工作。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-400">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="fcaf9-401">如需詳細資訊，請參閱[Azure Key Vault 和 Microsoft FastTrack 中的完成](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key)工作。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-401">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) for information.</span></span>
  
<span data-ttu-id="fcaf9-402">若要為 SharePoint 線上、商務用 OneDrive，以及小組檔案，設定客戶機碼您將需要透過 Windows PowerShell 以遠端方式連線至 SharePoint 線上，以執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-402">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="fcaf9-403">為商務地區的每一個 SharePoint 線上和 OneDrive 建立資料加密原則（DEP）</span><span class="sxs-lookup"><span data-stu-id="fcaf9-403">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>

<span data-ttu-id="fcaf9-404">您可以將 DEP 與儲存在 Azure Key Vault 中的一組機碼產生關聯。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-404">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="fcaf9-405">您將 DEP 套用到一個地理位置（也稱為地理位置）上的所有資料。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-405">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="fcaf9-406">如果您使用 Office 365 的多地理位置功能，您可以為每個地理位置建立一個 DEP，使每個地理位置使用不同的金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-406">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="fcaf9-407">如果您不是使用多地理位置，您可以在 Office 365 組織中建立一個 DEP，以用於 SharePoint 線上、商務 OneDrive，以及小組檔案。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-407">If you are not using multi-geo, you can create one DEP in your Office 365 organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="fcaf9-408">Office 365 會使用 DEP 中識別的金鑰，以加密該地理位置的資料。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-408">Office 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="fcaf9-409">若要建立 DEP，您需要有先前取得的主要 Vault URIs。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-409">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="fcaf9-410">如需相關指示，請參閱[取得每個 Azure Key Vault 金鑰的 URI](#obtain-the-uri-for-each-azure-key-vault-key) 。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-410">See [Obtain the URI for each Azure Key Vault key](#obtain-the-uri-for-each-azure-key-vault-key) for instructions.</span></span>
  
<span data-ttu-id="fcaf9-411">記得！</span><span class="sxs-lookup"><span data-stu-id="fcaf9-411">Remember!</span></span> <span data-ttu-id="fcaf9-412">當您建立 DEP 時，請指定位於兩個不同 Azure 金鑰電子倉庫中的兩個金鑰。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-412">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="fcaf9-413">請確定這些機碼位於兩個不同的 Azure 地區，以確保異地冗余。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-413">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="fcaf9-414">若要建立 DEP，您必須使用 Windows PowerShell，以遠端方式從遠端連線至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-414">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="fcaf9-415">在您的本機電腦上，使用 Office 365 組織中具有全域系統管理員許可權的工作或學校帳戶，[連線至 SharePoint Online Powershell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-415">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

2. <span data-ttu-id="fcaf9-416">在 Microsoft SharePoint Online 管理命令介面中，執行 SPODataEncryptionPolicy 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fcaf9-416">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="fcaf9-417">當您註冊 DEP 時，加密會從 geo 中的資料開始。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-417">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="fcaf9-418">這可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-418">This can take some time.</span></span>

### <a name="validate-file-encryption"></a><span data-ttu-id="fcaf9-419">驗證檔加密</span><span class="sxs-lookup"><span data-stu-id="fcaf9-419">Validate file encryption</span></span>

 <span data-ttu-id="fcaf9-420">若要驗證 SharePoint 線上、OneDrive 商務及小組檔案的加密，請[連線至 SharePoint 線上 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)，然後使用 SPODataEncryptionPolicy 指令程式檢查您租使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-420">To validate encryption of SharePoint Online, OneDrive for Business, and Teams files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps), and then use the Get-SPODataEncryptionPolicy cmdlet to check the status of your tenant.</span></span> <span data-ttu-id="fcaf9-421">如果已啟用客戶金鑰加密，且所有網站中的所有檔案都已加密，則_State_屬性會傳回**已註冊**的值。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-421">The _State_ property returns a value of **registered** if Customer Key encryption is enabled and all files in all sites have been encrypted.</span></span> <span data-ttu-id="fcaf9-422">如果加密仍在進行中，則此 Cmdlet 會提供完成的網站百分比資訊。</span><span class="sxs-lookup"><span data-stu-id="fcaf9-422">If encryption is still in progress, this cmdlet provides information on what percentage of sites is complete.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fcaf9-423">相關文章</span><span class="sxs-lookup"><span data-stu-id="fcaf9-423">Related articles</span></span>

- [<span data-ttu-id="fcaf9-424">使用 Office 365 的客戶金鑰服務加密</span><span class="sxs-lookup"><span data-stu-id="fcaf9-424">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="fcaf9-425">管理 Office 365 的客戶金鑰</span><span class="sxs-lookup"><span data-stu-id="fcaf9-425">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="fcaf9-426">滾動或輪替客戶金鑰或可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="fcaf9-426">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="fcaf9-427">深入瞭解可用性金鑰</span><span class="sxs-lookup"><span data-stu-id="fcaf9-427">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="fcaf9-428">Office 365 服務加密</span><span class="sxs-lookup"><span data-stu-id="fcaf9-428">Office 365 Service Encryption</span></span>](office-365-service-encryption.md)
