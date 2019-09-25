---
title: 使用客戶金鑰控制 Office 365 中的資料
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: 了解如何为 Office 365 进行联机交换、业务 Skype、共享点联机和一个业务一个驱动器的客户密钥设置。 使用客户密钥，您可以控制组织的加密密钥，然后将 Office 365 配置为使用它们在 Microsoft 的数据中心中静态加密您的数据。
ms.openlocfilehash: 839d0b56b3748e2ab4ccecc30a084447f22131aa
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076590"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a><span data-ttu-id="3af3d-104">使用客戶金鑰控制 Office 365 中的資料</span><span class="sxs-lookup"><span data-stu-id="3af3d-104">Controlling your data in Office 365 using Customer Key</span></span>

<span data-ttu-id="3af3d-105">使用客户密钥，您可以控制组织的加密密钥，然后将 Office 365 配置为使用它们在 Microsoft 数据中心中静态加密您的数据。</span><span class="sxs-lookup"><span data-stu-id="3af3d-105">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="3af3d-106">换句话说，客户密钥允许客户使用密钥添加属于他们的加密层。</span><span class="sxs-lookup"><span data-stu-id="3af3d-106">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="3af3d-107">存放的資料包括 Exchange Online 資料和儲存在信箱的商務用 Skype 資料，以及儲存在 SharePoint Online 中和商務用 OneDrive 中的檔案。</span><span class="sxs-lookup"><span data-stu-id="3af3d-107">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="3af3d-108">必须先设置 Azure，然后才能将客户密钥用于 Office 365。</span><span class="sxs-lookup"><span data-stu-id="3af3d-108">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="3af3d-109">本主题介绍创建和配置所需的 Azure 资源所需的步骤，然后提供在 Office 365 中设置客户密钥的步骤。</span><span class="sxs-lookup"><span data-stu-id="3af3d-109">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="3af3d-110">完成 Azure 设置后，将确定要分配给组织中的邮箱和文件的策略，以及哪些密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-110">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="3af3d-111">未为其分配策略的邮箱和文件将使用由 Microsoft 控制和管理的加密策略。</span><span class="sxs-lookup"><span data-stu-id="3af3d-111">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="3af3d-112">有关客户密钥的详细信息，或有关一般概述的信息，请参阅[Office 365 常见问题解答的客户密钥](service-encryption-with-customer-key-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="3af3d-112">For more information about Customer Key, or for a general overview, see the [Customer Key for Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3af3d-113">我们强烈建议您遵循本主题中的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="3af3d-113">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="3af3d-114">这些**被称为TIP**和**重要。**</span><span class="sxs-lookup"><span data-stu-id="3af3d-114">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="3af3d-115">通过客户密钥，您可以控制根加密密钥，其范围可以与整个组织一样大。</span><span class="sxs-lookup"><span data-stu-id="3af3d-115">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="3af3d-116">这意味着使用这些密钥所犯的错误可能会产生广泛影响，并可能导致服务中断或不可撤销地丢失数据。</span><span class="sxs-lookup"><span data-stu-id="3af3d-116">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span> 
  
## <a name="before-you-begin-setting-up-customer-key"></a><span data-ttu-id="3af3d-117">在开始设置客户密钥之前</span><span class="sxs-lookup"><span data-stu-id="3af3d-117">Before you begin setting up Customer Key</span></span>
<span data-ttu-id="3af3d-118"><a name="Beforeyoustart"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-118"></span></span>

<span data-ttu-id="3af3d-119">在开始之前，请确保为您的组织获得适当的许可。</span><span class="sxs-lookup"><span data-stu-id="3af3d-119">Before you get started, be sure you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="3af3d-120">Office 365 中的客户密钥在 Office 365 E5 或高级合规性 SKU 中提供。</span><span class="sxs-lookup"><span data-stu-id="3af3d-120">Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span>
  
<span data-ttu-id="3af3d-121">然后，为了了解本主题中的概念和过程，应查看[Azure 密钥保管库](https://azure.microsoft.com/en-us/documentation/services/key-vault/)文档。</span><span class="sxs-lookup"><span data-stu-id="3af3d-121">Then, to understand the concepts and procedures in this topic, you should review the [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) documentation.</span></span> <span data-ttu-id="3af3d-122">此外，还要熟悉 Azure 中使用的术语，例如[租户](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)。</span><span class="sxs-lookup"><span data-stu-id="3af3d-122">Also, become familiar with the terms used in Azure, for example, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span></span>
  
<span data-ttu-id="3af3d-123">要提供有关客户密钥（包括文档）的反馈，请将您的想法、建议和观点发送给customerkeyfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="3af3d-123">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a><span data-ttu-id="3af3d-124">为 Office 365 设置客户密钥的概述</span><span class="sxs-lookup"><span data-stu-id="3af3d-124">Overview of setting up Customer Key for Office 365</span></span>
<span data-ttu-id="3af3d-125"><a name="Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-125"></span></span>

<span data-ttu-id="3af3d-126">要设置客户密钥，您将完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="3af3d-126">To set up Customer Key you will complete these tasks.</span></span> <span data-ttu-id="3af3d-127">本主题的其余部分提供每个任务的详细说明，或链接到流程中每个步骤的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3af3d-127">The rest of this topic provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="3af3d-128">**在 Azure 和 Microsoft 快速通道中：**</span><span class="sxs-lookup"><span data-stu-id="3af3d-128">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="3af3d-129">您将通过远程连接到 Azure PowerShell 来完成这些任务的大部分。</span><span class="sxs-lookup"><span data-stu-id="3af3d-129">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="3af3d-130">为获得最佳效果，请使用版本 4.4.0 或更高版本的 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3af3d-130">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="3af3d-131">创建新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="3af3d-131">Create two new Azure subscriptions</span></span>](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [<span data-ttu-id="3af3d-132">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="3af3d-132">Register Azure subscriptions to use a mandatory retention period</span></span>](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    <span data-ttu-id="3af3d-133">注册可能需要一到五个工作日。</span><span class="sxs-lookup"><span data-stu-id="3af3d-133">Registration can take from one to five business days.</span></span>
    
- [<span data-ttu-id="3af3d-134">提交激活 Office 365 的客户密钥的请求</span><span class="sxs-lookup"><span data-stu-id="3af3d-134">Submit a request to activate Customer Key for Office 365</span></span>](controlling-your-data-using-customer-key.md#FastTrack)
    
    <span data-ttu-id="3af3d-135">创建两个新的 Azure 订阅后，需要通过填写托管在 Microsoft FastTrack 门户中的 Web 窗体来提交相应的客户密钥产品/服务请求。</span><span class="sxs-lookup"><span data-stu-id="3af3d-135">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="3af3d-136">**FastTrack 团队不提供客户密钥方面的帮助。Office只是使用FastTrack门户，允许您提交表格，并帮助我们跟踪客户密钥的相关优惠。**</span><span class="sxs-lookup"><span data-stu-id="3af3d-136">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>
  
<span data-ttu-id="3af3d-137">提交客户密钥产品/服务后，Microsoft 会审核您的请求，并通知您何时可以继续其余设置任务。</span><span class="sxs-lookup"><span data-stu-id="3af3d-137">Once you have submitted a Customer Key offer, Microsoft reviews your request and notifies you when you can proceed with the rest of the setup tasks.</span></span> <span data-ttu-id="3af3d-138">此过程最多可能需要五个工作日。</span><span class="sxs-lookup"><span data-stu-id="3af3d-138">This process can take up to five business days.</span></span>
    
- [<span data-ttu-id="3af3d-139">在每个订阅中创建高级 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="3af3d-139">Create a premium Azure Key Vault in each subscription</span></span>](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [<span data-ttu-id="3af3d-140">为每个密钥保管库分配权限</span><span class="sxs-lookup"><span data-stu-id="3af3d-140">Assign permissions to each key vault</span></span>](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [<span data-ttu-id="3af3d-141">在密钥保管库上启用并确认软删除</span><span class="sxs-lookup"><span data-stu-id="3af3d-141">Enable and then confirm soft delete on your key vaults</span></span>](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [<span data-ttu-id="3af3d-142">通过创建或导入密钥，向每个密钥保管库添加密钥</span><span class="sxs-lookup"><span data-stu-id="3af3d-142">Add a key to each key vault either by creating or importing a key</span></span>](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [<span data-ttu-id="3af3d-143">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="3af3d-143">Check the recovery level of your keys</span></span>](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [<span data-ttu-id="3af3d-144">备份 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="3af3d-144">Backup Azure Key Vault</span></span>](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [<span data-ttu-id="3af3d-145">验证 Azure 密钥保管库配置设置</span><span class="sxs-lookup"><span data-stu-id="3af3d-145">Validate Azure Key Vault configuration settings</span></span>](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [<span data-ttu-id="3af3d-146">获取每个 Azure 密钥保管库密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="3af3d-146">Obtain the URI for each Azure Key Vault key</span></span>](controlling-your-data-using-customer-key.md#GetKeyURI)
    
<span data-ttu-id="3af3d-147">**在 Office 365 中：**</span><span class="sxs-lookup"><span data-stu-id="3af3d-147">**In Office 365:**</span></span>
  
<span data-ttu-id="3af3d-148">交换在线和 Skype 业务：</span><span class="sxs-lookup"><span data-stu-id="3af3d-148">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="3af3d-149">创建数据加密策略 （DEP），以便与 Exchange 在线和 Skype 业务一起使用</span><span class="sxs-lookup"><span data-stu-id="3af3d-149">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [<span data-ttu-id="3af3d-150">将 DEP 分配给邮箱</span><span class="sxs-lookup"><span data-stu-id="3af3d-150">Assign a DEP to a mailbox</span></span>](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [<span data-ttu-id="3af3d-151">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="3af3d-151">Validate mailbox encryption</span></span>](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
<span data-ttu-id="3af3d-152">共享点在线和一个驱动器的业务：</span><span class="sxs-lookup"><span data-stu-id="3af3d-152">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="3af3d-153">为每个共享点联机和一个业务地理创建数据加密策略 （DEP）</span><span class="sxs-lookup"><span data-stu-id="3af3d-153">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [<span data-ttu-id="3af3d-154">验证针对企业的组网站、团队网站和 OneDrive 的加密</span><span class="sxs-lookup"><span data-stu-id="3af3d-154">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="3af3d-155">在 Azure 密钥保管库和 Microsoft 客户密钥快速跟踪中完成任务</span><span class="sxs-lookup"><span data-stu-id="3af3d-155">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>
<span data-ttu-id="3af3d-156"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-156"></span></span>

<span data-ttu-id="3af3d-157">在 Azure 密钥保管库中完成这些任务，以便为 Office 365 设置客户密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-157">Complete these tasks in Azure Key Vault in order to set up Customer Key for Office 365.</span></span> <span data-ttu-id="3af3d-158">无论您打算为联机交换和 Skype 进行联机交换或共享点联机和 OneDrive 业务或 Office 365 中所有受支持的服务，您都需要完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="3af3d-158">You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or SharePoint Online and OneDrive for Business or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="3af3d-159">创建新的 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="3af3d-159">Create two new Azure subscriptions</span></span>
<span data-ttu-id="3af3d-160"><a name="Create2newsubs"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-160"></span></span>

<span data-ttu-id="3af3d-161">客户密钥需要两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3af3d-161">Two Azure subscriptions are required for Customer Key.</span></span> <span data-ttu-id="3af3d-162">最佳做法是 Microsoft 建议您创建新的 Azure 订阅，以便与客户密钥一起使用。</span><span class="sxs-lookup"><span data-stu-id="3af3d-162">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="3af3d-163">Azure 密钥保管库密钥只能为同一 Azure 活动目录 （AAD） 租户中的应用程序授权，必须使用与 Office 365 组织一起使用的相同 Azure AD 租户创建新订阅，其中将分配 IP。</span><span class="sxs-lookup"><span data-stu-id="3af3d-163">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned.</span></span> <span data-ttu-id="3af3d-164">例如，在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="3af3d-164">For example, using your work or school account that has global administrator privileges in your Office 365 organization.</span></span> <span data-ttu-id="3af3d-165">有关详细步骤，请参阅[将 Azure 注册为组织](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)。</span><span class="sxs-lookup"><span data-stu-id="3af3d-165">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3af3d-166">客户密钥需要每个数据加密策略 （DEP） 两个密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-166">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="3af3d-167">为此，必须创建两个 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3af3d-167">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="3af3d-168">最佳做法是，Microsoft 建议组织中的单独成员在每个订阅中配置一个密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-168">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="3af3d-169">此外，这些 Azure 订阅应仅用于管理 Office 365 的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-169">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="3af3d-170">这样可保护您的组织，以防您的某个操作员意外、故意或恶意删除或以其他方式错误管理他们负责的密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-170">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="3af3d-171">我们建议您设置仅用于管理 Azure 密钥保管库资源以便与客户密钥一起使用的新 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3af3d-171">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="3af3d-172">可以为组织创建的 Azure 订阅数没有实际限制。</span><span class="sxs-lookup"><span data-stu-id="3af3d-172">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="3af3d-173">遵循这些最佳实践将最大限度地减少人为错误的影响，同时帮助管理客户密钥使用的资源。</span><span class="sxs-lookup"><span data-stu-id="3af3d-173">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span> 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="3af3d-174">提交激活 Office 365 的客户密钥的请求</span><span class="sxs-lookup"><span data-stu-id="3af3d-174">Submit a request to activate Customer Key for Office 365</span></span>
<span data-ttu-id="3af3d-175"><a name="FastTrack"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-175"></span></span>

<span data-ttu-id="3af3d-176">完成 Azure 步骤后，需要在[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)中提交产品/服务请求。</span><span class="sxs-lookup"><span data-stu-id="3af3d-176">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="3af3d-177">通过 FastTrack Web 门户提交请求后，Microsoft 将验证您提供的 Azure 密钥保管库配置数据和联系信息。</span><span class="sxs-lookup"><span data-stu-id="3af3d-177">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="3af3d-178">您在产品/服务表单中针对组织授权人员做出的选择对于完成客户密钥注册至关重要且必要。</span><span class="sxs-lookup"><span data-stu-id="3af3d-178">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="3af3d-179">您在表单中选择的组织官员将用来确保撤销和销毁客户密钥数据加密策略中使用的所有密钥的任何请求的真实性。</span><span class="sxs-lookup"><span data-stu-id="3af3d-179">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="3af3d-180">您需要执行此步骤一次，以激活联机交换的客户密钥和用于业务覆盖范围的 Skype，第二次激活用于 SharePoint 联机和 OneDrive 的业务的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-180">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="3af3d-181">要提交要约以激活客户密钥，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3af3d-181">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="3af3d-182">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，登录到[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="3af3d-182">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>
    
2. <span data-ttu-id="3af3d-183">登录后，浏览到**仪表板**。</span><span class="sxs-lookup"><span data-stu-id="3af3d-183">Once you're logged in, browse to the **Dashboard**.</span></span>
    
3. <span data-ttu-id="3af3d-184">选择**优惠，** 并查看当前优惠列表。</span><span class="sxs-lookup"><span data-stu-id="3af3d-184">Choose **Offers**, and review the list of current offers.</span></span>
    
4. <span data-ttu-id="3af3d-185">选择适用于您的优惠**的更多功能：**</span><span class="sxs-lookup"><span data-stu-id="3af3d-185">Choose **Learn More** for the offer that applies to you:</span></span> 
    
  - <span data-ttu-id="3af3d-186">**交换在线和 Skype 业务：** 选择有关**交换产品/服务的客户密钥\*\*\*\*了解有关详细信息。**</span><span class="sxs-lookup"><span data-stu-id="3af3d-186">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span> 
    
  - <span data-ttu-id="3af3d-187">**共享点在线和一个驱动器的业务：** 选择了解有关**SharePoint 和 OneDrive 商业产品/服务的客户密钥\*\*\*\*的更多详细信息。**</span><span class="sxs-lookup"><span data-stu-id="3af3d-187">**SharePoint Online and OneDrive for Business:** Chose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span> 
    
5. <span data-ttu-id="3af3d-188">在"**产品/服务详细信息"** 页上，**选择"创建请求"。**</span><span class="sxs-lookup"><span data-stu-id="3af3d-188">On the **Offer details** page, choose **Create Request**.</span></span>
    
6. <span data-ttu-id="3af3d-189">填写所有适用的详细信息，并在优惠表格上提供所要求的信息。</span><span class="sxs-lookup"><span data-stu-id="3af3d-189">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="3af3d-190">特别注意您要授权组织的官员批准永久和不可逆转地销毁加密密钥和数据的选择。</span><span class="sxs-lookup"><span data-stu-id="3af3d-190">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="3af3d-191">填写完表单后，**选择"提交"。**</span><span class="sxs-lookup"><span data-stu-id="3af3d-191">Once you've completed the form, choose **Submit**.</span></span>
    
    <span data-ttu-id="3af3d-192">一旦 Microsoft 收到您的请求通知，此过程最多可能需要五个工作日。</span><span class="sxs-lookup"><span data-stu-id="3af3d-192">This process can take up to five business days once Microsoft has been notified of your request.</span></span>
    
7. <span data-ttu-id="3af3d-193">继续以下强制保留期部分。</span><span class="sxs-lookup"><span data-stu-id="3af3d-193">Continue on to the mandatory retention period section below.</span></span>
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="3af3d-194">注册 Azure 订阅以使用强制保留期</span><span class="sxs-lookup"><span data-stu-id="3af3d-194">Register Azure subscriptions to use a mandatory retention period</span></span>
<span data-ttu-id="3af3d-195"><a name="RegisterSubsforMRP"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-195"></span></span>

<span data-ttu-id="3af3d-196">根加密密钥的临时或永久丢失可能会对服务操作造成极大的干扰甚至灾难性后果，并可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="3af3d-196">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="3af3d-197">因此，客户密钥中使用的资源需要强大的保护。</span><span class="sxs-lookup"><span data-stu-id="3af3d-197">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="3af3d-198">与客户密钥一起使用的所有 Azure 资源都提供默认配置以外的保护机制。</span><span class="sxs-lookup"><span data-stu-id="3af3d-198">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="3af3d-199">Azure 订阅可以标记或注册，以防止立即取消和不可撤销。</span><span class="sxs-lookup"><span data-stu-id="3af3d-199">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="3af3d-200">这称为注册强制保留期。</span><span class="sxs-lookup"><span data-stu-id="3af3d-200">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="3af3d-201">注册 Azure 订阅以进行强制保留期所需的步骤需要与 Office 365 团队协作。</span><span class="sxs-lookup"><span data-stu-id="3af3d-201">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team.</span></span> <span data-ttu-id="3af3d-202">此过程可能需要 1 到 5 个工作日。</span><span class="sxs-lookup"><span data-stu-id="3af3d-202">This process can take from one to five business days.</span></span> <span data-ttu-id="3af3d-203">以前，这有时被称为"不取消"。</span><span class="sxs-lookup"><span data-stu-id="3af3d-203">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="3af3d-204">在联系 Office 365 团队之前，必须对与客户密钥一起使用的每个 Azure 订阅执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3af3d-204">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key:</span></span>
  
1. <span data-ttu-id="3af3d-205">使用 Azure PowerShell 登录到 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3af3d-205">Log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="3af3d-206">有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。</span><span class="sxs-lookup"><span data-stu-id="3af3d-206">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
2. <span data-ttu-id="3af3d-207">运行注册 Azure Rm 提供程序功能 cmdlet 以注册订阅以使用强制保留期。</span><span class="sxs-lookup"><span data-stu-id="3af3d-207">Run the Register-AzureRmProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span>
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. <span data-ttu-id="3af3d-208">请与 Microsoft 联系，以完成该过程。</span><span class="sxs-lookup"><span data-stu-id="3af3d-208">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="3af3d-209">对于业务团队的 SharePoint 和 OneDrive，[请联系spock@microsoft.com。](mailto:spock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3af3d-209">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="3af3d-210">如需在线交换和 Skype 业务，[请联系exock@microsoft.com。](mailto:exock@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3af3d-210">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="3af3d-211">完成此过程的服务级别协议 （SLA） 是 Microsoft 收到通知（和验证）您已注册订阅以使用强制保留期后五个工作日。</span><span class="sxs-lookup"><span data-stu-id="3af3d-211">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="3af3d-212">在电子邮件中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="3af3d-212">Include the following in your email:</span></span>
    
    <span data-ttu-id="3af3d-213">**主题**：\<*租户完全限定域名*的客户密钥\></span><span class="sxs-lookup"><span data-stu-id="3af3d-213">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span> 
    
    <span data-ttu-id="3af3d-214">**正文：** 您希望为其最终确定强制保留期的订阅 ID。</span><span class="sxs-lookup"><span data-stu-id="3af3d-214">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span> 
    
4. <span data-ttu-id="3af3d-215">收到 Microsoft 通知注册已完成后，请通过运行 Get-Azure RmProvider 功能 cmdlet 来验证注册状态，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-215">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzureRmProviderFeature cmdlet as follows:</span></span>
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. <span data-ttu-id="3af3d-216">验证 Get-AzureRmProviderFeature cmdlet 中的**注册状态**属性是否**返回"已注册"** 的值后，运行以下命令以完成此过程：</span><span class="sxs-lookup"><span data-stu-id="3af3d-216">After verifying that the **Registration State** property from the Get-AzureRmProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process:</span></span>
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="3af3d-217">在每个订阅中创建高级 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="3af3d-217">Create a premium Azure Key Vault in each subscription</span></span>
<span data-ttu-id="3af3d-218"><a name="CreateKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-218"></span></span>

<span data-ttu-id="3af3d-219">创建密钥保管库的步骤在[Azure 密钥保管库入门](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)中记录，该保管库将指导您安装和启动 Azure PowerShell、连接到 Azure 订阅、创建资源组以及创建其中的密钥保管库。资源组。</span><span class="sxs-lookup"><span data-stu-id="3af3d-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="3af3d-220">创建密钥保管库时，必须选择 SKU：标准库或高级库。</span><span class="sxs-lookup"><span data-stu-id="3af3d-220">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="3af3d-221">标准 SKU 允许使用软件保护 Azure 密钥保管库密钥 - 没有硬件安全模块 （HSM） 密钥保护 - 高级 SKU 允许使用 HSM 来保护密钥保管库密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-221">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="3af3d-222">客户密钥接受使用任一 SKU 的密钥保管库，但 Microsoft 强烈建议您仅使用高级 SKU。</span><span class="sxs-lookup"><span data-stu-id="3af3d-222">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="3af3d-223">任一类型密钥的操作成本相同，因此成本的唯一区别是每个受 HSM 保护的密钥的每月成本。</span><span class="sxs-lookup"><span data-stu-id="3af3d-223">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="3af3d-224">有关详细信息，请参阅[密钥保管库定价。](https://azure.microsoft.com/pricing/details/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="3af3d-224">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3af3d-225">将高级 SKU 密钥保管库和受 HSM 保护的密钥用于生产数据，并且仅使用标准 SKU 密钥保管库和密钥进行测试和验证。</span><span class="sxs-lookup"><span data-stu-id="3af3d-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span> 
  
<span data-ttu-id="3af3d-226">对于将使用客户密钥的每个 Office 365 服务，在创建的两个 Azure 订阅中为每个订阅创建一个密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="3af3d-226">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="3af3d-227">例如，对于仅为业务进行交换和 Skype 或仅为业务共享点和 OneDrive，您将只创建一对保管库。</span><span class="sxs-lookup"><span data-stu-id="3af3d-227">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="3af3d-228">要启用联机交换和共享点联机的客户密钥，您将创建两对密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="3af3d-228">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="3af3d-229">对密钥保管库使用命名约定，该约定反映了将关联保管库的 DEP 的预期用途。</span><span class="sxs-lookup"><span data-stu-id="3af3d-229">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults.</span></span> <span data-ttu-id="3af3d-230">有关命名约定建议，请参阅下面的最佳实践部分。</span><span class="sxs-lookup"><span data-stu-id="3af3d-230">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="3af3d-231">为每个数据加密策略创建一组单独的成对保管库。</span><span class="sxs-lookup"><span data-stu-id="3af3d-231">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="3af3d-232">对于 Exchange Online，当您将策略分配给邮箱时，您将选择数据加密策略的范围。</span><span class="sxs-lookup"><span data-stu-id="3af3d-232">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="3af3d-233">邮箱只能分配一个策略，并且您最多只能创建五十个策略。</span><span class="sxs-lookup"><span data-stu-id="3af3d-233">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="3af3d-234">对于 SharePoint Online，策略的范围是组织内地理位置或地理位置中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="3af3d-234">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or geo.</span></span>
  
<span data-ttu-id="3af3d-235">创建密钥保管库还需要创建 Azure 资源组，因为密钥保管库需要存储容量（虽然非常小），密钥保管库日志记录（如果启用）也会生成存储的数据。</span><span class="sxs-lookup"><span data-stu-id="3af3d-235">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="3af3d-236">作为最佳做法，Microsoft 建议使用单独的管理员来管理每个资源组，管理与将管理所有相关客户密钥资源的管理员集保持一致。</span><span class="sxs-lookup"><span data-stu-id="3af3d-236">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3af3d-237">为了最大限度地提高可用性，密钥保管库应位于靠近 Office 365 服务的区域。</span><span class="sxs-lookup"><span data-stu-id="3af3d-237">To maximize availability, your key vaults should be in regions close to your Office 365 service.</span></span> <span data-ttu-id="3af3d-238">例如，如果您的 Exchange 在线组织位于北美，请将密钥保管库放在北美。</span><span class="sxs-lookup"><span data-stu-id="3af3d-238">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="3af3d-239">如果您的 Exchange 在线组织位于欧洲，请将您的关键保管库放在欧洲。</span><span class="sxs-lookup"><span data-stu-id="3af3d-239">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="3af3d-240">对密钥保管库使用通用前缀，并包括密钥保管库和密钥的使用和范围的缩写（例如，对于保管库将位于北美的 Contoso SharePoint 服务，可能的名称对是 Contoso-O365SP-NA-VaultA1 和康托索-O365SP-NA-VaultA2。</span><span class="sxs-lookup"><span data-stu-id="3af3d-240">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="3af3d-241">保管库名称是 Azure 中的全局唯一字符串，因此您可能需要尝试所需名称的变体，以防其他 Azure 客户已声明所需名称。</span><span class="sxs-lookup"><span data-stu-id="3af3d-241">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="3af3d-242">自 2017 年 7 月起，无法更改保管库名称，因此最佳做法是制定书面设置计划，并使用第二个人验证计划是否正确执行。</span><span class="sxs-lookup"><span data-stu-id="3af3d-242">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="3af3d-243">如果可能，在非配对区域中创建保管库。</span><span class="sxs-lookup"><span data-stu-id="3af3d-243">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="3af3d-244">配对的 Azure 区域跨服务失败域提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="3af3d-244">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="3af3d-245">因此，区域对可以被视为彼此的备份区域。</span><span class="sxs-lookup"><span data-stu-id="3af3d-245">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="3af3d-246">这意味着放置在一个区域中的 Azure 资源通过配对区域自动获得容错能力。</span><span class="sxs-lookup"><span data-stu-id="3af3d-246">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="3af3d-247">因此，为 DEP 中使用的两个区域选择区域，其中区域已配对意味着总共只有两个可用性区域处于使用状态。</span><span class="sxs-lookup"><span data-stu-id="3af3d-247">For this reason, choosing regions for two vaults used in a DEP where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="3af3d-248">大多数地理位置只有两个区域，因此尚无法选择非配对区域。</span><span class="sxs-lookup"><span data-stu-id="3af3d-248">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="3af3d-249">如果可能，为与 DEP 一起使用的两个保管库选择两个非配对区域。</span><span class="sxs-lookup"><span data-stu-id="3af3d-249">If possible, choose two non-paired regions for the two vaults used with a DEP.</span></span> <span data-ttu-id="3af3d-250">这得益于四个可用区域。</span><span class="sxs-lookup"><span data-stu-id="3af3d-250">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="3af3d-251">有关详细信息，请参阅[业务连续性和灾难恢复 （BCDR）：](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)当前区域对列表的 Azure 配对区域。</span><span class="sxs-lookup"><span data-stu-id="3af3d-251">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span> 
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="3af3d-252">为每个密钥保管库分配权限</span><span class="sxs-lookup"><span data-stu-id="3af3d-252">Assign permissions to each key vault</span></span>
<span data-ttu-id="3af3d-253"><a name="KeyVaultPerms"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-253"></span></span>

<span data-ttu-id="3af3d-254">对于每个密钥保管库，您需要为客户密钥定义三组单独的权限，具体取决于您的实现。</span><span class="sxs-lookup"><span data-stu-id="3af3d-254">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="3af3d-255">例如，您需要为以下各项定义一组权限：</span><span class="sxs-lookup"><span data-stu-id="3af3d-255">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="3af3d-256">**关键保管库管理员，** 将执行对组织密钥保管库的日常管理。</span><span class="sxs-lookup"><span data-stu-id="3af3d-256">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="3af3d-257">这些任务包括备份、创建、获取、导入、列出和恢复。</span><span class="sxs-lookup"><span data-stu-id="3af3d-257">These tasks include backup, create, get, import, list, and restore.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="3af3d-258">分配给密钥保管库管理员的权限集不包括删除密钥的权限。</span><span class="sxs-lookup"><span data-stu-id="3af3d-258">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="3af3d-259">这是有意的，也是一项重要的做法。</span><span class="sxs-lookup"><span data-stu-id="3af3d-259">This is intentional and an important practice.</span></span> <span data-ttu-id="3af3d-260">删除加密密钥通常不会完成，因为这样做会永久销毁数据。</span><span class="sxs-lookup"><span data-stu-id="3af3d-260">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="3af3d-261">最佳做法是，默认情况下不要向密钥保管库管理员授予此权限。</span><span class="sxs-lookup"><span data-stu-id="3af3d-261">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="3af3d-262">相反，请为关键保管库参与者保留此项，并且仅在了解对后果的明确理解后，才将其短期分配给管理员。</span><span class="sxs-lookup"><span data-stu-id="3af3d-262">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span> 
  
    <span data-ttu-id="3af3d-263">要将这些权限分配给 Office 365 组织中的用户，请使用 Azure PowerShell 登录到 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3af3d-263">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="3af3d-264">有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。</span><span class="sxs-lookup"><span data-stu-id="3af3d-264">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
- <span data-ttu-id="3af3d-265">运行设置 AzureRmKeyVault 访问策略 cmdlet 以分配必要的权限。</span><span class="sxs-lookup"><span data-stu-id="3af3d-265">Run the Set-AzureRmKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  <span data-ttu-id="3af3d-266">例如：</span><span class="sxs-lookup"><span data-stu-id="3af3d-266">For example:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- <span data-ttu-id="3af3d-267">可以更改 Azure 密钥保管库本身权限**的主要保管库参与者。**</span><span class="sxs-lookup"><span data-stu-id="3af3d-267">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="3af3d-268">当员工离开或加入您的团队时，或者在密钥保管库管理员合法需要删除或还原密钥的权限的极罕见情况下，您需要更改这些权限。</span><span class="sxs-lookup"><span data-stu-id="3af3d-268">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="3af3d-269">需要授予这组密钥保管库参与者在密钥保管**库中的参与者**角色。</span><span class="sxs-lookup"><span data-stu-id="3af3d-269">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="3af3d-270">可以使用 Azure 资源管理器分配此角色。</span><span class="sxs-lookup"><span data-stu-id="3af3d-270">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="3af3d-271">有关详细步骤，请参阅[使用基于角色的访问控制来管理对 Azure 订阅资源的访问。](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)</span><span class="sxs-lookup"><span data-stu-id="3af3d-271">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="3af3d-272">创建订阅的管理员具有隐式此访问权限，以及将其他管理员分配给参与者角色的能力。</span><span class="sxs-lookup"><span data-stu-id="3af3d-272">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>
    
- <span data-ttu-id="3af3d-273">如果您打算将客户密钥与联机交换和 Skype 业务使用，则需要授予 Office 365 权限，以代表 Exchange Online 和 Skype 进行业务使用密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="3af3d-273">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="3af3d-274">同样，如果您打算将客户密钥与 SharePoint Online 和 OneDrive 用于业务，则需要添加 Office 365 的权限，以便代表 SharePoint Online 和 OneDrive 代表企业使用密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="3af3d-274">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="3af3d-275">要授予 Office 365 权限，请使用以下语法运行**Set-AzureRmKeyVault 访问策略**cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3af3d-275">To give permission to Office 365, run the **Set-AzureRmKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    <span data-ttu-id="3af3d-276">其中：</span><span class="sxs-lookup"><span data-stu-id="3af3d-276">Where:</span></span>
    
  - <span data-ttu-id="3af3d-277">*保管库名称*是您创建的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="3af3d-277">*vaultname* is the name of the key vault you created.</span></span> 
    
  - <span data-ttu-id="3af3d-278">对于联机交换和 Skype 业务，将*Office 365 应用 ID*替换为`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="3af3d-278">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
    
  - <span data-ttu-id="3af3d-279">对于共享点在线和一个驱动器业务，将*Office 365 应用 ID*替换为`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="3af3d-279">For SharePoint Online and OneDrive for Business, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
    
  <span data-ttu-id="3af3d-280">示例：为"联机交换"和"业务 Skype"设置权限：</span><span class="sxs-lookup"><span data-stu-id="3af3d-280">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  <span data-ttu-id="3af3d-281">示例：为"在线共享点"和"一个驱动器"设置业务共享点权限</span><span class="sxs-lookup"><span data-stu-id="3af3d-281">Example: Setting permissions for SharePoint Online and OneDrive for Business</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="3af3d-282">在密钥保管库上启用并确认软删除</span><span class="sxs-lookup"><span data-stu-id="3af3d-282">Enable and then confirm soft delete on your key vaults</span></span>
<span data-ttu-id="3af3d-283"><a name="SoftDelete"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-283"></span></span>

<span data-ttu-id="3af3d-284">当您可以快速恢复密钥时，由于意外或恶意删除的密钥，您不太可能遇到扩展的服务中断。</span><span class="sxs-lookup"><span data-stu-id="3af3d-284">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="3af3d-285">您需要启用此配置（称为"软删除"），然后才能将密钥与客户密钥一起使用。</span><span class="sxs-lookup"><span data-stu-id="3af3d-285">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="3af3d-286">启用软删除允许您在删除后的 90 天内恢复密钥或保管库，而无需从备份中还原它们。</span><span class="sxs-lookup"><span data-stu-id="3af3d-286">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="3af3d-287">要在密钥保管库上启用软删除，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3af3d-287">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="3af3d-288">使用 Windows 电源外壳登录到 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3af3d-288">Log in to your Azure subscription with Windows Powershell.</span></span> <span data-ttu-id="3af3d-289">有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="3af3d-289">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>
    
2. <span data-ttu-id="3af3d-290">运行[获取 Azure RmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3af3d-290">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet.</span></span> <span data-ttu-id="3af3d-291">在此示例中，*保管库名称*是启用软删除的密钥保管库的名称：</span><span class="sxs-lookup"><span data-stu-id="3af3d-291">In this example, *vaultname* is the name of the key vault for which you are enabling soft delete:</span></span> 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. <span data-ttu-id="3af3d-292">通过运行**Get-Azure RmKeyVault** cmdlet，确认为密钥保管库配置了软删除。</span><span class="sxs-lookup"><span data-stu-id="3af3d-292">Confirm soft delete is configured for the key vault by running the **Get-AzureRmKeyVault** cmdlet.</span></span> <span data-ttu-id="3af3d-293">如果为密钥保管库正确配置了软删除，则启用软删除？属性返回**的值为 True**：</span><span class="sxs-lookup"><span data-stu-id="3af3d-293">If soft delete is configured properly for the key vault, then the  Soft Delete Enabled? property returns a value of **True**:</span></span> 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="3af3d-294">通过创建或导入密钥，向每个密钥保管库添加密钥</span><span class="sxs-lookup"><span data-stu-id="3af3d-294">Add a key to each key vault either by creating or importing a key</span></span>
<span data-ttu-id="3af3d-295"><a name="AddKeystoKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-295"></span></span>

<span data-ttu-id="3af3d-296">有两种方法可以将密钥添加到 Azure 密钥保管库;例如，可通过以下方法将密钥添加到 Azure 密钥保管库。可以直接在密钥保管库中创建密钥，也可以导入密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-296">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="3af3d-297">直接在密钥保管库中创建密钥是不太复杂的方法，而导入密钥可以完全控制密钥的生成方式。</span><span class="sxs-lookup"><span data-stu-id="3af3d-297">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="3af3d-298">要直接在密钥保管库中创建密钥，请运行[Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-298">To create a key directly in your key vault, run the [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="3af3d-299">其中：</span><span class="sxs-lookup"><span data-stu-id="3af3d-299">Where:</span></span>
  
-  <span data-ttu-id="3af3d-300">*保管库名称*是要在其中创建密钥的密钥保管库的名称。</span><span class="sxs-lookup"><span data-stu-id="3af3d-300">*vaultname*  is the name of the key vault in which you want to create the key.</span></span> 
    
-  <span data-ttu-id="3af3d-301">*键名*是要为新密钥提供的名称。</span><span class="sxs-lookup"><span data-stu-id="3af3d-301">*keyname*  is the name you want to give the new key.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="3af3d-302">使用与上文所述的类似命名约定对密钥保管库命名密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-302">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="3af3d-303">这样，在仅显示键名的工具中，字符串是自描述的。</span><span class="sxs-lookup"><span data-stu-id="3af3d-303">This way, in tools that show only the key name, the string is self-describing.</span></span> 
  
- <span data-ttu-id="3af3d-304">如果要使用 HSM 保护密钥，请确保指定**HSM**作为_目标_参数的值，否则，请**指定"软件"。**</span><span class="sxs-lookup"><span data-stu-id="3af3d-304">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the  _Destination_ parameter, otherwise, specify **Software**.</span></span>
    
<span data-ttu-id="3af3d-305">For example,</span><span class="sxs-lookup"><span data-stu-id="3af3d-305">For example,</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="3af3d-306">要将密钥直接导入密钥保管库，需要具有 Thales nShield 硬件安全模块。</span><span class="sxs-lookup"><span data-stu-id="3af3d-306">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="3af3d-307">有些组织喜欢使用这种方法来确定其密钥的来源，此方法还提供以下内容：</span><span class="sxs-lookup"><span data-stu-id="3af3d-307">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="3af3d-308">用于导入的工具集包括来自 Thales 的证明，证明用于加密您生成的密钥的密钥交换密钥 （KEK） 不可导出，并且是在 Thales 制造的真实 HSM 中生成的。</span><span class="sxs-lookup"><span data-stu-id="3af3d-308">The toolset used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>
    
- <span data-ttu-id="3af3d-309">该工具集包括来自 Thales 的证明，证明 Azure 密钥保管库安全世界也是在 Thales 制造的真实 HSM 上生成的。</span><span class="sxs-lookup"><span data-stu-id="3af3d-309">The toolset includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales.</span></span> <span data-ttu-id="3af3d-310">这个证明证明你，微软也使用真正的泰雷兹硬件。</span><span class="sxs-lookup"><span data-stu-id="3af3d-310">This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>
    
<span data-ttu-id="3af3d-311">请与您的安全小组核实，以确定是否需要上述证明。</span><span class="sxs-lookup"><span data-stu-id="3af3d-311">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="3af3d-312">有关在本地创建密钥并将其导入密钥保管库的详细步骤，请参阅[如何为 Azure 密钥保管库生成和传输受 HSM 保护的密钥。](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)</span><span class="sxs-lookup"><span data-stu-id="3af3d-312">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="3af3d-313">使用 Azure 说明在每个密钥保管库中创建密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-313">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="3af3d-314">检查密钥的恢复级别</span><span class="sxs-lookup"><span data-stu-id="3af3d-314">Check the recovery level of your keys</span></span>
<span data-ttu-id="3af3d-315"><a name="CheckKeyRecoveryLevel"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-315"></span></span>

<span data-ttu-id="3af3d-316">Office 365 要求将 Azure 密钥保管库订阅设置为"不取消"，并且启用了客户密钥使用的密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-316">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="3af3d-317">您可以通过查看密钥上的恢复级别来确认这一点。</span><span class="sxs-lookup"><span data-stu-id="3af3d-317">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="3af3d-318">要检查密钥的恢复级别，请在 Azure PowerShell 中运行获取 AzureKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-318">To check the recovery level of a key, in Azure PowerShell, run the Get-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

<span data-ttu-id="3af3d-319">如果"_恢复级别"_ 属性**返回"可恢复"保护订阅**的值以外的任何内容，则需要查看本主题，并确保已执行所有步骤将订阅放在"不取消"列表上，并在每个密钥保管库上启用了软删除。</span><span class="sxs-lookup"><span data-stu-id="3af3d-319">If the  _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="backup-azure-key-vault"></a><span data-ttu-id="3af3d-320">备份 Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="3af3d-320">Backup Azure Key Vault</span></span>
<span data-ttu-id="3af3d-321"><a name="BackupAzureKeyVaultkeys"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-321"></span></span>

<span data-ttu-id="3af3d-322">在创建密钥或更改密钥后立即执行备份并存储备份副本，包括联机和脱机备份。</span><span class="sxs-lookup"><span data-stu-id="3af3d-322">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="3af3d-323">脱机副本不应连接到任何网络，例如在物理安全或商业存储设施中。</span><span class="sxs-lookup"><span data-stu-id="3af3d-323">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="3af3d-324">备份的至少一个副本应存储在发生灾难时可访问的位置。</span><span class="sxs-lookup"><span data-stu-id="3af3d-324">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="3af3d-325">如果密钥保管库密钥被永久销毁或无法操作，备份 blob 是还原密钥材料的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="3af3d-325">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="3af3d-326">Azure 密钥保管库外部并导入到 Azure 密钥保管库的密钥不符合备份条件，因为外部密钥不存在客户密钥使用密钥所需的元数据。</span><span class="sxs-lookup"><span data-stu-id="3af3d-326">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="3af3d-327">只有从 Azure 密钥保管库获取的备份可用于使用客户密钥还原操作。</span><span class="sxs-lookup"><span data-stu-id="3af3d-327">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="3af3d-328">因此，在上载或创建密钥后，必须备份 Azure 密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="3af3d-328">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="3af3d-329">要创建 Azure 密钥保管库密钥的备份，请运行[备份 Azure 密钥密钥密钥](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey)cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-329">To create a backup of an Azure Key Vault key, run the [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet as follows:</span></span>
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

<span data-ttu-id="3af3d-330">确保输出文件使用后缀`.backup`。</span><span class="sxs-lookup"><span data-stu-id="3af3d-330">Ensure that your output file uses the suffix  `.backup`.</span></span>
  
<span data-ttu-id="3af3d-331">由此生成的输出文件已加密，不能在 Azure 密钥保管库之外使用。</span><span class="sxs-lookup"><span data-stu-id="3af3d-331">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="3af3d-332">只能将备份还原到从中进行备份的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="3af3d-332">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="3af3d-333">对于输出文件，选择保管库名称和密钥名称的组合。</span><span class="sxs-lookup"><span data-stu-id="3af3d-333">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="3af3d-334">这将使文件名自描述。</span><span class="sxs-lookup"><span data-stu-id="3af3d-334">This will make the file name self-describing.</span></span> <span data-ttu-id="3af3d-335">它还将确保备份文件名不会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="3af3d-335">It will also ensure that backup file names do not collide.</span></span> 
  
<span data-ttu-id="3af3d-336">例如：</span><span class="sxs-lookup"><span data-stu-id="3af3d-336">For example:</span></span>
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="3af3d-337">验证 Azure 密钥保管库配置设置</span><span class="sxs-lookup"><span data-stu-id="3af3d-337">Validate Azure Key Vault configuration settings</span></span>
<span data-ttu-id="3af3d-338"><a name="Validateconfiguration"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-338"></span></span>

<span data-ttu-id="3af3d-339">在 DEP 中使用密钥之前执行验证是可选的，但强烈建议这样做。</span><span class="sxs-lookup"><span data-stu-id="3af3d-339">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="3af3d-340">特别是，如果使用步骤设置密钥和保管库（本主题中介绍的键和保管库）以外的步骤，则应在配置客户密钥之前验证 Azure 密钥保管库资源的运行状况。</span><span class="sxs-lookup"><span data-stu-id="3af3d-340">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="3af3d-341">要验证密钥是否已启用，请包装密钥和展开密钥操作：</span><span class="sxs-lookup"><span data-stu-id="3af3d-341">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="3af3d-342">运行[获取 AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-342">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet as follows:</span></span> 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

<span data-ttu-id="3af3d-343">在输出中，查找访问策略和 Exchange 联机标识 （GUID） 或 SharePoint 联机标识 （GUID）。</span><span class="sxs-lookup"><span data-stu-id="3af3d-343">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="3af3d-344">上述所有三个权限都必须显示在"密钥权限"下。</span><span class="sxs-lookup"><span data-stu-id="3af3d-344">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="3af3d-345">如果访问策略配置不正确，请运行 Set-AzureRmKeyVault 访问策略 cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-345">If the access policy configuration is incorrect, run the Set-AzureRmKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="3af3d-346">例如，对于联机交换和 Skype 业务：</span><span class="sxs-lookup"><span data-stu-id="3af3d-346">For example, for Exchange Online and Skype for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="3af3d-347">例如，对于共享点在线和一个驱动器的业务：</span><span class="sxs-lookup"><span data-stu-id="3af3d-347">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="3af3d-348">要验证未为密钥设置到期日期，请运行[Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-348">To verify that an expiration date is not set for your keys run the [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

<span data-ttu-id="3af3d-349">客户密钥无法使用过期密钥，使用过期密钥尝试的操作将失败，并可能导致服务中断。</span><span class="sxs-lookup"><span data-stu-id="3af3d-349">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="3af3d-350">我们强烈建议客户密钥中使用的密钥没有到期日期。</span><span class="sxs-lookup"><span data-stu-id="3af3d-350">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="3af3d-351">过期日期（一旦设置）无法删除，但可以更改为其他日期。</span><span class="sxs-lookup"><span data-stu-id="3af3d-351">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="3af3d-352">如果必须使用设置到期日期的密钥，则将过期值更改为 12/31/9999。</span><span class="sxs-lookup"><span data-stu-id="3af3d-352">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="3af3d-353">到期日期设置为 12/31/9999 日期的密钥不会通过 Office 365 验证。</span><span class="sxs-lookup"><span data-stu-id="3af3d-353">Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="3af3d-354">要更改已设置为 12/31/9999 以外的任何值的到期日期，请运行[Set-AzureKeyKey属性](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute)cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-354">To change an expiration date that has been set to any value other than 12/31/9999, run the [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet as follows:</span></span> 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="3af3d-355">不要为使用客户密钥的加密密钥设置到期日期。</span><span class="sxs-lookup"><span data-stu-id="3af3d-355">Don't set expiration dates on encryption keys you use with Customer Key.</span></span> 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="3af3d-356">获取每个 Azure 密钥保管库密钥的 URI</span><span class="sxs-lookup"><span data-stu-id="3af3d-356">Obtain the URI for each Azure Key Vault key</span></span>
<span data-ttu-id="3af3d-357"><a name="GetKeyURI"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-357"></span></span>

<span data-ttu-id="3af3d-358">完成 Azure 中设置密钥保管库并添加密钥的所有步骤后，运行以下命令以获取每个密钥保管库中的密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="3af3d-358">Once you have completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="3af3d-359">稍后创建和分配每个 DEP 时，需要使用这些 URI，因此将此信息保存在安全的地方。</span><span class="sxs-lookup"><span data-stu-id="3af3d-359">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="3af3d-360">请记住为每个密钥保管库运行此命令一次。</span><span class="sxs-lookup"><span data-stu-id="3af3d-360">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="3af3d-361">在 Azure 电源外壳中：</span><span class="sxs-lookup"><span data-stu-id="3af3d-361">In Azure PowerShell:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="3af3d-362">Office 365：为在线交换和 Skype 业务设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="3af3d-362">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>
<span data-ttu-id="3af3d-363"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-363"></span></span>

<span data-ttu-id="3af3d-364">开始之前，请确保已完成设置 Azure 密钥保管库所需的任务。</span><span class="sxs-lookup"><span data-stu-id="3af3d-364">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="3af3d-365">有关详细信息，请参阅[Azure 密钥保管库和 Microsoft 快速跟踪中有关客户密钥的完成任务。](controlling-your-data-using-customer-key.md#AzureSteps)</span><span class="sxs-lookup"><span data-stu-id="3af3d-365">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="3af3d-366">要设置联机交换客户密钥和 Skype 业务密钥，您需要通过使用 Windows PowerShell 远程连接到 Exchange Online 来执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="3af3d-366">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="3af3d-367">创建数据加密策略 （DEP），以便与 Exchange 在线和 Skype 业务一起使用</span><span class="sxs-lookup"><span data-stu-id="3af3d-367">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>
<span data-ttu-id="3af3d-368"><a name="CreateDEP4EXOSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-368"></span></span>

<span data-ttu-id="3af3d-369">DEP 与存储在 Azure 密钥保管库中的一组密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="3af3d-369">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="3af3d-370">将 DEP 分配给 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3af3d-370">You assign a DEP to a mailbox in Office 365.</span></span> <span data-ttu-id="3af3d-371">然后，Office 365 将使用策略中标识的密钥对邮箱进行加密。</span><span class="sxs-lookup"><span data-stu-id="3af3d-371">Office 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="3af3d-372">要创建 DEP，您需要之前获取的密钥保管库 URI。</span><span class="sxs-lookup"><span data-stu-id="3af3d-372">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="3af3d-373">有关[说明，请参阅获取每个 Azure 密钥保管库密钥的 URI。](controlling-your-data-using-customer-key.md#GetKeyURI)</span><span class="sxs-lookup"><span data-stu-id="3af3d-373">See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="3af3d-374">记得！</span><span class="sxs-lookup"><span data-stu-id="3af3d-374">Remember!</span></span> <span data-ttu-id="3af3d-375">创建 DEP 时，指定两个驻留在两个不同的 Azure 密钥保管库中的密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-375">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="3af3d-376">确保这些密钥位于两个单独的 Azure 区域中，以确保地理冗余。</span><span class="sxs-lookup"><span data-stu-id="3af3d-376">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="3af3d-377">要创建 DEP，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="3af3d-377">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="3af3d-378">在本地计算机上，使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，通过打开 Windows PowerShell 并运行以下命令[连接到 Exchange Online PowerShell。](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3af3d-378">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) by opening Windows PowerShell and running the following command.</span></span> 
    
   ```
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="3af3d-379">在 Windows PowerShell 凭据请求对话框中，输入您的工作或学校帐户信息，单击"**确定"，** 然后输入以下命令。</span><span class="sxs-lookup"><span data-stu-id="3af3d-379">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span> 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="3af3d-380">執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="3af3d-380">Run the following command.</span></span>
    
   ```
   Import-PSSession $Session
   ```

4. <span data-ttu-id="3af3d-381">要创建 DEP，请使用新数据加密策略 cmdlet，键入以下命令。</span><span class="sxs-lookup"><span data-stu-id="3af3d-381">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="3af3d-382">其中：</span><span class="sxs-lookup"><span data-stu-id="3af3d-382">Where:</span></span>
    
   -  <span data-ttu-id="3af3d-383">*策略名称*是要用于策略的名称。</span><span class="sxs-lookup"><span data-stu-id="3af3d-383">*PolicyName*  is the name you want to use for the policy.</span></span> <span data-ttu-id="3af3d-384">名称不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="3af3d-384">Names cannot contain spaces.</span></span> <span data-ttu-id="3af3d-385">例如，美国邮箱。</span><span class="sxs-lookup"><span data-stu-id="3af3d-385">For example, USA_mailboxes.</span></span> 
    
   -  <span data-ttu-id="3af3d-386">*策略说明*是策略的用户友好描述，可帮助您记住策略的用点。</span><span class="sxs-lookup"><span data-stu-id="3af3d-386">*PolicyDescription*  is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="3af3d-387">您可以在说明中包含空格。</span><span class="sxs-lookup"><span data-stu-id="3af3d-387">You can include spaces in the description.</span></span> <span data-ttu-id="3af3d-388">例如，美国及其区域中的邮箱的根键。</span><span class="sxs-lookup"><span data-stu-id="3af3d-388">For example, Root key for mailboxes in USA and its territories.</span></span> 
    
   -  <span data-ttu-id="3af3d-389">*KeyVaultURI1*是策略中第一个键的 URI。</span><span class="sxs-lookup"><span data-stu-id="3af3d-389">*KeyVaultURI1*  is the URI for the first key in the policy.</span></span> <span data-ttu-id="3af3d-390">例如 https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。</span><span class="sxs-lookup"><span data-stu-id="3af3d-390">For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span> 
    
   -  <span data-ttu-id="3af3d-391">*KeyVaultURI2*是策略中第二个键的 URI。</span><span class="sxs-lookup"><span data-stu-id="3af3d-391">*KeyVaultURI2*  is the URI for the second key in the policy.</span></span> <span data-ttu-id="3af3d-392">例如 https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。</span><span class="sxs-lookup"><span data-stu-id="3af3d-392">For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02.</span></span> <span data-ttu-id="3af3d-393">用逗号和空格分隔两个 URI。</span><span class="sxs-lookup"><span data-stu-id="3af3d-393">Separate the two URIs by a comma and a space.</span></span> 
    
   <span data-ttu-id="3af3d-394">範例：</span><span class="sxs-lookup"><span data-stu-id="3af3d-394">Example:</span></span>
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="3af3d-395">将 DEP 分配给邮箱</span><span class="sxs-lookup"><span data-stu-id="3af3d-395">Assign a DEP to a mailbox</span></span>
<span data-ttu-id="3af3d-396"><a name="assignDEPtomailbox"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-396"></span></span>

<span data-ttu-id="3af3d-397">使用设置邮箱 cmdlet 将 DEP 分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="3af3d-397">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="3af3d-398">分配策略后，Office 365 可以使用 DEP 中指定的密钥加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="3af3d-398">Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="3af3d-399">*邮箱Id参数*指定邮箱的位置。</span><span class="sxs-lookup"><span data-stu-id="3af3d-399">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="3af3d-400">有关设置邮箱 cmdlet 的详细信息，请参阅[设置邮箱](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3af3d-400">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="3af3d-401">验证邮箱加密</span><span class="sxs-lookup"><span data-stu-id="3af3d-401">Validate mailbox encryption</span></span>
<span data-ttu-id="3af3d-402"><a name="validatemailboxencryption"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-402"></span></span>

<span data-ttu-id="3af3d-403">加密邮箱可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="3af3d-403">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="3af3d-404">对于第一次策略分配，邮箱还必须完成从一个数据库到另一个数据库的移动，服务才能加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="3af3d-404">For first time policy assignment, the mailbox must also complete the move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="3af3d-405">我们建议您在更改 DEP 或首次将 DEP 分配给邮箱后尝试验证加密之前等待 72 小时。</span><span class="sxs-lookup"><span data-stu-id="3af3d-405">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="3af3d-406">使用获取邮箱统计信息 cmdlet 确定邮箱是否已加密。</span><span class="sxs-lookup"><span data-stu-id="3af3d-406">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="3af3d-407">如果邮箱已加密，IsEncrypted 属性返回**的值为 true;** 如果邮箱未加密，则 IsEncrypted 属性返回**的值为 false。**</span><span class="sxs-lookup"><span data-stu-id="3af3d-407">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span> 

<span data-ttu-id="3af3d-408">完成邮箱移动的时间取决于首次分配 DEP 的邮箱数以及邮箱的大小。</span><span class="sxs-lookup"><span data-stu-id="3af3d-408">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="3af3d-409">如果邮箱在分配 DEP 后一周后未加密，请使用 New-MoveRequest cmdlet 启动未加密邮箱的邮箱移动。</span><span class="sxs-lookup"><span data-stu-id="3af3d-409">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, initiate a mailbox move for the unencrypted mailboxes by using the New-MoveRequest cmdlet.</span></span>

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="3af3d-410">Office 365：为共享点在线和一个业务设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="3af3d-410">Office 365: Setting up Customer Key for SharePoint Online and OneDrive for Business</span></span>
<span data-ttu-id="3af3d-411"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-411"></span></span>

<span data-ttu-id="3af3d-412">开始之前，请确保已完成设置 Azure 密钥保管库所需的任务。</span><span class="sxs-lookup"><span data-stu-id="3af3d-412">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="3af3d-413">有关详细信息，请参阅[Azure 密钥保管库和 Microsoft 快速跟踪中有关客户密钥的完成任务。](controlling-your-data-using-customer-key.md#AzureSteps)</span><span class="sxs-lookup"><span data-stu-id="3af3d-413">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="3af3d-414">要为"共享点联机"和"企业 OneDrive"设置客户密钥，您需要通过使用 Windows PowerShell 远程连接到共享点联机来执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="3af3d-414">To set up Customer Key for SharePoint Online and OneDrive for Business, you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="3af3d-415">为每个共享点联机和一个业务地理创建数据加密策略 （DEP）</span><span class="sxs-lookup"><span data-stu-id="3af3d-415">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>
<span data-ttu-id="3af3d-416"><a name="CreateDEP4SPOODfB"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-416"></span></span>

<span data-ttu-id="3af3d-417">DEP 与存储在 Azure 密钥保管库中的一组密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="3af3d-417">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="3af3d-418">您将 DEP 应用于一个地理位置（也称为地理）中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="3af3d-418">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="3af3d-419">如果使用 Office 365 的多地理位置功能（当前处于预览版中），则可以每个地理位置创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="3af3d-419">If you use the multi-geo feature of Office 365 (currently in Preview), you can create one DEP per geo.</span></span> <span data-ttu-id="3af3d-420">如果不使用多地理位置，则可以在 Office 365 中创建一个 DEP，以便与 SharePoint Online 和 OneDrive 一起使用。</span><span class="sxs-lookup"><span data-stu-id="3af3d-420">If you are not using multi-geo, you can create one DEP in Office 365 for use with SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="3af3d-421">然后，Office 365 将使用 DEP 中标识的密钥在该地理位置中加密数据。</span><span class="sxs-lookup"><span data-stu-id="3af3d-421">Office 365 will then use the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="3af3d-422">要创建 DEP，您需要之前获取的密钥保管库 URI。</span><span class="sxs-lookup"><span data-stu-id="3af3d-422">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="3af3d-423">有关[说明，请参阅获取每个 Azure 密钥保管库密钥的 URI。](controlling-your-data-using-customer-key.md#GetKeyURI)</span><span class="sxs-lookup"><span data-stu-id="3af3d-423">See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="3af3d-424">记得！</span><span class="sxs-lookup"><span data-stu-id="3af3d-424">Remember!</span></span> <span data-ttu-id="3af3d-425">创建 DEP 时，指定两个驻留在两个不同的 Azure 密钥保管库中的密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-425">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="3af3d-426">确保这些密钥位于两个单独的 Azure 区域中，以确保地理冗余。</span><span class="sxs-lookup"><span data-stu-id="3af3d-426">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="3af3d-427">要创建 DEP，您需要使用 Windows PowerShell 远程连接到共享点联机。</span><span class="sxs-lookup"><span data-stu-id="3af3d-427">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="3af3d-428">在本地计算机上，使用 Office 365 组织中具有全局管理员权限的工作或学校帐户"连接到[SharePoint 联机电源外壳](https://technet.microsoft.com/library/fp161372.aspx)"。</span><span class="sxs-lookup"><span data-stu-id="3af3d-428">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span></span>
    
2. <span data-ttu-id="3af3d-429">在 Microsoft SharePoint 联机管理命令行中，运行[注册-SPO数据加密策略](https://technet.microsoft.com/library/mt843950.aspx)cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-429">In the Microsoft SharePoint Online Management Shell, run the [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet as follows:</span></span> 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="3af3d-430">注册 DEP 时，加密从地理数据开始。</span><span class="sxs-lookup"><span data-stu-id="3af3d-430">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="3af3d-431">这可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="3af3d-431">This can take some time.</span></span>
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a><span data-ttu-id="3af3d-432">验证针对企业的组网站、团队网站和 OneDrive 的加密</span><span class="sxs-lookup"><span data-stu-id="3af3d-432">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>
<span data-ttu-id="3af3d-433"><a name="validateencryptionSPO"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-433"></span></span>

<span data-ttu-id="3af3d-434">您可以通过运行 Get-SPOData 加密策略 cmdlet 来检查加密状态，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-434">You can check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="3af3d-435">此 cmdlet 的输出包括：</span><span class="sxs-lookup"><span data-stu-id="3af3d-435">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="3af3d-436">主键的 URI。</span><span class="sxs-lookup"><span data-stu-id="3af3d-436">The URI of the primary key.</span></span>
    
- <span data-ttu-id="3af3d-437">辅助键的 URI。</span><span class="sxs-lookup"><span data-stu-id="3af3d-437">The URI of the secondary key.</span></span>
    
- <span data-ttu-id="3af3d-438">地理的加密状态。</span><span class="sxs-lookup"><span data-stu-id="3af3d-438">The encryption status for the geo.</span></span> <span data-ttu-id="3af3d-439">可能状态包括：</span><span class="sxs-lookup"><span data-stu-id="3af3d-439">Possible states include:</span></span>
    
  - <span data-ttu-id="3af3d-440">**未注册：** 尚未应用客户密钥加密。</span><span class="sxs-lookup"><span data-stu-id="3af3d-440">**Unregistered:** Customer Key encryption has not yet been applied.</span></span> 
    
  - <span data-ttu-id="3af3d-441">**注册：** 已应用客户密钥加密，您的文件正在加密中。</span><span class="sxs-lookup"><span data-stu-id="3af3d-441">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="3af3d-442">如果您的地理位置处于此状态，则还会显示有关地理中站点已完成的百分比的信息，以便您可以监视加密进度。</span><span class="sxs-lookup"><span data-stu-id="3af3d-442">If your geo is in this state, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span> 
    
  - <span data-ttu-id="3af3d-443">**注册：** 已应用客户密钥加密，并且所有站点中的所有文件都已加密。</span><span class="sxs-lookup"><span data-stu-id="3af3d-443">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span> 
    
  - <span data-ttu-id="3af3d-444">**滚动：** 关键卷正在进行中。</span><span class="sxs-lookup"><span data-stu-id="3af3d-444">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="3af3d-445">如果您的地理位置处于此状态，则还会显示有关已完成密钥滚动操作的网站百分比的信息，以便您可以监视进度。</span><span class="sxs-lookup"><span data-stu-id="3af3d-445">If your geo is in this state, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span> 
    
## <a name="managing-customer-key-for-office-365"></a><span data-ttu-id="3af3d-446">管理 Office 365 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="3af3d-446">Managing Customer Key for Office 365</span></span>
<span data-ttu-id="3af3d-447"><a name="ManageCustomerKey"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-447"></span></span>

<span data-ttu-id="3af3d-448">为 Office 365 设置客户密钥后，可以执行这些其他管理任务。</span><span class="sxs-lookup"><span data-stu-id="3af3d-448">After you've set up Customer Key for Office 365, you can perform these additional management tasks.</span></span>
  
- [<span data-ttu-id="3af3d-449">还原 Azure 密钥保管库密钥</span><span class="sxs-lookup"><span data-stu-id="3af3d-449">Restore Azure Key Vault keys</span></span>](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [<span data-ttu-id="3af3d-450">在与客户密钥一起使用的 Azure 密钥保管库中滚动或旋转密钥</span><span class="sxs-lookup"><span data-stu-id="3af3d-450">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [<span data-ttu-id="3af3d-451">管理密钥保管库权限</span><span class="sxs-lookup"><span data-stu-id="3af3d-451">Manage key vault permissions</span></span>](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [<span data-ttu-id="3af3d-452">确定分配给邮箱的 DEP</span><span class="sxs-lookup"><span data-stu-id="3af3d-452">Determine the DEP assigned to a mailbox</span></span>](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="3af3d-453">还原 Azure 密钥保管库密钥</span><span class="sxs-lookup"><span data-stu-id="3af3d-453">Restore Azure Key Vault keys</span></span>
<span data-ttu-id="3af3d-454"><a name="RestoreAzureKeyVaultKeys"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-454"></span></span>

<span data-ttu-id="3af3d-455">在执行还原之前，请使用软删除提供的恢复功能。</span><span class="sxs-lookup"><span data-stu-id="3af3d-455">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="3af3d-456">与客户密钥一起使用的所有密钥都需要启用软删除。</span><span class="sxs-lookup"><span data-stu-id="3af3d-456">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="3af3d-457">软删除功能类似于回收站，允许恢复长达 90 天，而无需恢复。</span><span class="sxs-lookup"><span data-stu-id="3af3d-457">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="3af3d-458">只有在极端或异常情况下（例如，如果密钥或密钥保管库丢失）才需要还原。</span><span class="sxs-lookup"><span data-stu-id="3af3d-458">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="3af3d-459">如果必须还原用于客户密钥的密钥，请使用 Azure PowerShell，按如下方式运行还原 Azure KeyVaultKey cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3af3d-459">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

<span data-ttu-id="3af3d-460">例如：</span><span class="sxs-lookup"><span data-stu-id="3af3d-460">For example:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="3af3d-461">如果密钥保管库中已存在同名密钥，则还原操作将失败。</span><span class="sxs-lookup"><span data-stu-id="3af3d-461">If a key with the same name already exists in the key vault, the restore operation will fail.</span></span> <span data-ttu-id="3af3d-462">还原 AzureKeyVaultKey 还原密钥的所有密钥版本和所有元数据，包括密钥名称。</span><span class="sxs-lookup"><span data-stu-id="3af3d-462">Restore-AzureKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a><span data-ttu-id="3af3d-463">在与客户密钥一起使用的 Azure 密钥保管库中滚动或旋转密钥</span><span class="sxs-lookup"><span data-stu-id="3af3d-463">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>
<span data-ttu-id="3af3d-464"><a name="RollCKkey"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-464"></span></span>

<span data-ttu-id="3af3d-465">Azure 密钥保管库或客户密钥不需要滚动密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-465">Rolling keys is not required by either Azure Key Vault or by Customer Key.</span></span> <span data-ttu-id="3af3d-466">此外，受 HSM 保护的密钥几乎不可能泄露。</span><span class="sxs-lookup"><span data-stu-id="3af3d-466">In addition, keys that are protected with an HSM are virtually impossible to compromise.</span></span> <span data-ttu-id="3af3d-467">即使根密钥属于恶意参与者，也没有任何可行的方法来使用它来解密数据，因为只有 Office 365 代码知道如何使用它。</span><span class="sxs-lookup"><span data-stu-id="3af3d-467">Even if a root key were in the possession of a malicious actor there is no feasible means of using it to decrypt data, since only Office 365 code knows how to use it.</span></span> <span data-ttu-id="3af3d-468">但是，滚动密钥由客户密钥支持。</span><span class="sxs-lookup"><span data-stu-id="3af3d-468">However, rolling a key is supported by Customer Key.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3af3d-469">仅当存在明确的技术原因或合规性要求要求必须滚动密钥时，才滚动与客户密钥一起使用的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-469">Only roll an encryption key that you use with Customer Key when a clear technical reason exists or a compliance requirement dictates that you have to roll the key.</span></span> <span data-ttu-id="3af3d-470">此外，不要删除任何与策略关联的密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-470">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="3af3d-471">当您滚动密钥时，将会有使用以前的密钥加密的内容。</span><span class="sxs-lookup"><span data-stu-id="3af3d-471">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="3af3d-472">例如，虽然活动邮箱将频繁重新加密，但非活动、断开连接和禁用的邮箱仍可以使用以前的密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="3af3d-472">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="3af3d-473">SharePoint Online 执行内容备份以进行恢复和恢复，因此仍有可能使用旧密钥存档的内容。</span><span class="sxs-lookup"><span data-stu-id="3af3d-473">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span> <br/> <span data-ttu-id="3af3d-474">为确保数据的安全，SharePoint Online 一次只允许进行一次密钥滚动操作。</span><span class="sxs-lookup"><span data-stu-id="3af3d-474">To ensure the safety of your data, SharePoint Online will allow no more than one Key Roll operation to be in progress at a time.</span></span> <span data-ttu-id="3af3d-475">如果要在密钥保管库中滚动两个密钥，则需要等待第一个密钥滚动操作完全完成。</span><span class="sxs-lookup"><span data-stu-id="3af3d-475">If you want to roll both of the keys in a key vault, you'll need to wait for the first key roll operation to fully complete.</span></span> <span data-ttu-id="3af3d-476">我们的建议是以不同的时间间隔错开您的关键辊操作，这样这不是问题。</span><span class="sxs-lookup"><span data-stu-id="3af3d-476">Our recommendation is to stagger your key roll operations at different intervals, so that this is not an issue.</span></span> 
  
<span data-ttu-id="3af3d-477">滚动密钥时，正在请求现有密钥的新版本。</span><span class="sxs-lookup"><span data-stu-id="3af3d-477">When you roll a key, you are requesting a new version of an existing key.</span></span> <span data-ttu-id="3af3d-478">为了请求现有密钥的新版本，您可以使用相同的 cmdlet [Add-AzureKeyKey，](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)使用与最初用于创建密钥相同的语法。</span><span class="sxs-lookup"><span data-stu-id="3af3d-478">In order to request a new version of an existing key, you use the same cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), with the same syntax that you used to create the key in the first place.</span></span>
  
<span data-ttu-id="3af3d-479">例如：</span><span class="sxs-lookup"><span data-stu-id="3af3d-479">For example:</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

<span data-ttu-id="3af3d-480">在此示例中，由于名为**Contoso-O365EX-NA-VaultA1-Key001**的密钥已存在于**Contoso-O365EX-NA-VaultA1**保管库中，因此将创建新的密钥版本。</span><span class="sxs-lookup"><span data-stu-id="3af3d-480">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** already exists in the **Contoso-O365EX-NA-VaultA1** vault, a new key version will be created.</span></span> <span data-ttu-id="3af3d-481">该操作添加了一个新的密钥版本。</span><span class="sxs-lookup"><span data-stu-id="3af3d-481">The operation adds a new key version.</span></span> <span data-ttu-id="3af3d-482">此操作将保留密钥版本历史记录中的以前的密钥版本，以便以前使用该密钥加密的数据仍可以解密。</span><span class="sxs-lookup"><span data-stu-id="3af3d-482">This operation preserves the previous key versions in the key's version history, so that data previously encrypted with that key can still be decrypted.</span></span> <span data-ttu-id="3af3d-483">完成滚动与 DEP 关联的任何密钥后，必须运行另一个 cmdlet 以确保客户密钥开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-483">Once you have completed rolling any key that is associated with a DEP, you must then run an additional cmdlet to ensure Customer Key begins using the new key.</span></span> 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="3af3d-484">启用联机交换和 Skype 业务在 Azure 密钥保管库中滚动或旋转密钥后使用新密钥</span><span class="sxs-lookup"><span data-stu-id="3af3d-484">Enable Exchange Online and Skype for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="3af3d-485">当您滚动与与 Exchange Online 和 Skype 业务版使用的 DEP 关联的任一 Azure 密钥保管库密钥时，必须运行以下命令来更新 DEP 并启用 Office 365 开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-485">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must run the following command to update the DEP and enable Office 365 to start using the new key.</span></span>
  
<span data-ttu-id="3af3d-486">要指示客户密钥使用新密钥加密 Office 365 中的邮箱，请运行 Set-Data 加密策略 cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-486">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

<span data-ttu-id="3af3d-487">在 48 小时内，使用此策略加密的活动邮箱将与更新的密钥关联。</span><span class="sxs-lookup"><span data-stu-id="3af3d-487">Within 48 hours, the active mailboxes encrypted using this policy will become associated with the updated key.</span></span> <span data-ttu-id="3af3d-488">[使用"确定分配给邮箱的 DEP"](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)中的步骤检查邮箱的数据加密策略 ID 属性的值。</span><span class="sxs-lookup"><span data-stu-id="3af3d-488">Use the steps in [Determine the DEP assigned to a mailbox](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) to check the value for the DataEncryptionPolicyID property for the mailbox.</span></span> <span data-ttu-id="3af3d-489">应用更新的键后，此属性的值将更改。</span><span class="sxs-lookup"><span data-stu-id="3af3d-489">The value for this property will change once the updated key has been applied.</span></span> 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="3af3d-490">启用企业共享点联机和 OneDrive 在 Azure 密钥保管库中滚动或旋转密钥后使用新密钥</span><span class="sxs-lookup"><span data-stu-id="3af3d-490">Enable SharePoint Online and OneDrive for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="3af3d-491">当您滚动与与 SharePoint Online 和 OneDrive 业务中使用的 DEP 关联的任一个 Azure 密钥保管库密钥时，必须运行[更新 SPOData 加密策略](https://technet.microsoft.com/library/mt843948.aspx)cmdlet 以更新 DEP 并启用 Office 365 开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="3af3d-491">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must run the [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet to update the DEP and enable Office 365 to start using the new key.</span></span> 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

<span data-ttu-id="3af3d-492">这将启动 SharePoint 联机和一个业务一个驱动器的密钥滚动操作。</span><span class="sxs-lookup"><span data-stu-id="3af3d-492">This will start the key roll operation for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="3af3d-493">此操作不是立即执行的。</span><span class="sxs-lookup"><span data-stu-id="3af3d-493">This action is not immediate.</span></span> <span data-ttu-id="3af3d-494">要查看密钥滚动操作的进度，请运行获取 SPO 数据加密策略 cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af3d-494">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a><span data-ttu-id="3af3d-495">管理密钥保管库权限</span><span class="sxs-lookup"><span data-stu-id="3af3d-495">Manage key vault permissions</span></span>
<span data-ttu-id="3af3d-496"><a name="Managekeyvaultperms"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-496"></span></span>

<span data-ttu-id="3af3d-497">有几个 cmdlet 可用，使您能够查看并在必要时删除密钥保管库权限。</span><span class="sxs-lookup"><span data-stu-id="3af3d-497">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="3af3d-498">您可能需要删除权限，例如，当员工离开团队时。</span><span class="sxs-lookup"><span data-stu-id="3af3d-498">You might need to remove permissions, for example, when an employee leaves the team.</span></span>
  
<span data-ttu-id="3af3d-499">要查看密钥保管库权限，请运行获取 Azure RmKeyVault cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3af3d-499">To view key vault permissions, run the Get-AzureRmKeyVault cmdlet:</span></span>
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

<span data-ttu-id="3af3d-500">例如：</span><span class="sxs-lookup"><span data-stu-id="3af3d-500">For example:</span></span>
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="3af3d-501">要删除管理员的权限，请运行删除 AzureRmKeyVault 访问策略 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3af3d-501">To remove an administrator's permissions, run the Remove-AzureRmKeyVaultAccessPolicy cmdlet:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

<span data-ttu-id="3af3d-502">例如：</span><span class="sxs-lookup"><span data-stu-id="3af3d-502">For example:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="3af3d-503">确定分配给邮箱的 DEP</span><span class="sxs-lookup"><span data-stu-id="3af3d-503">Determine the DEP assigned to a mailbox</span></span>
<span data-ttu-id="3af3d-504"><a name="DeterminemailboxDEP"> </a></span><span class="sxs-lookup"><span data-stu-id="3af3d-504"></span></span>

<span data-ttu-id="3af3d-505">要确定分配给邮箱的 DEP，请使用获取邮箱统计信息 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3af3d-505">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="3af3d-506">cmdlet 返回唯一标识符 （GUID）。</span><span class="sxs-lookup"><span data-stu-id="3af3d-506">The cmdlet returns a unique identifier (GUID).</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

<span data-ttu-id="3af3d-507">在*其中"常规邮箱"或"邮件用户参数"* 指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="3af3d-507">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="3af3d-508">有关获取邮箱统计信息 cmdlet 的详细信息，请参阅[获取邮箱统计信息](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3af3d-508">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span></span>
  
<span data-ttu-id="3af3d-509">使用 GUID 通过运行以下 cmdlet 找出邮箱分配到的 DEP 的友好名称。</span><span class="sxs-lookup"><span data-stu-id="3af3d-509">Use the GUID to find out the friendly name of the DEP to which the mailbox is assigned by running the following cmdlet.</span></span>
  
```
Get-DataEncryptionPolicy <GUID>
```

<span data-ttu-id="3af3d-510">其中*GUID*是上一步中获取邮箱统计信息 cmdlet 返回的 GUID。</span><span class="sxs-lookup"><span data-stu-id="3af3d-510">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span> 
  

