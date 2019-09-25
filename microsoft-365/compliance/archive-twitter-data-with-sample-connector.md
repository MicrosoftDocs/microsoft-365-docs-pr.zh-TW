---
title: 使用示例连接器在 Office 365（预览版）中存档 Twitter 数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器，将 Twitter 数据导入 Office 365。 这样，您就可以在 Office 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如法律保留、内容搜索和保留策略）来管理组织第三方数据的治理。
ms.openlocfilehash: 6780e3fbb53e2326994e03815403c1e5ae0d0616
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076704"
---
# <a name="use-a-sample-connector-to-archive-twitter-data-in-office-365-preview"></a><span data-ttu-id="8c6aa-104">使用示例连接器在 Office 365（预览版）中存档 Twitter 数据</span><span class="sxs-lookup"><span data-stu-id="8c6aa-104">Use a sample connector to archive Twitter data in Office 365 (Preview)</span></span>

<span data-ttu-id="8c6aa-105">用于在 Office 365 中存档 Twitter 数据的示例连接器功能处于预览版。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-105">The sample connector feature to archive Twitter data in Office 365 is in Preview.</span></span>

<span data-ttu-id="8c6aa-106">在 Office 365 中的安全&合规性中心中使用示例连接器从 Twitter 导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-106">Use a sample connector in the Security & Compliance Center in Office 365 to import and archive data from Twitter.</span></span> <span data-ttu-id="8c6aa-107">设置和配置示例连接器后，它将连接到组织的 Twitter 帐户（按计划），将项目的内容转换为电子邮件格式，然后将这些项目导入 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-107">After you set up and configure a sample connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="8c6aa-108">导入 Twitter 数据后，您可以将 Office 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核、监督和 Office 365 保留策略）应用于存储在邮箱中的数据。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-108">After Twitter data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Supervision, and Office 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="8c6aa-109">例如，您可以使用内容搜索搜索 Twitter 数据，或者将存储数据的邮箱与高级电子数据展示案例中的保管人相关联。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-109">For example, you can search Twitter data using Content Search or associate the mailbox where the data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="8c6aa-110">使用示例连接器在 Office 365 中导入和存档 Twitter 数据可以帮助您的组织遵守政府和监管策略。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-110">Using a sample connectors to import and archive Twitter data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

> [!NOTE]
> <span data-ttu-id="8c6aa-111">目前，只有 Twitter 和[Facebook 商业页面](archive-facebook-data-with-sample-connector.md)的示例连接器可用于预览。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-111">Currently, only the sample connectors for Twitter and [Facebook Business pages](archive-facebook-data-with-sample-connector.md) are available for Preview.</span></span> <span data-ttu-id="8c6aa-112">更多示例连接器即将推出。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-112">More sample connectors are coming soon.</span></span>


## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a><span data-ttu-id="8c6aa-113">为 Twitter 设置连接器的先决条件</span><span class="sxs-lookup"><span data-stu-id="8c6aa-113">Prerequisites for setting up a connector for Twitter</span></span>

<span data-ttu-id="8c6aa-114">必须先完成以下先决条件，然后才能在安全&合规性中心中设置和配置示例连接器，以便从组织的 Twitter 帐户导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-114">You must complete the following prerequisites before you can set up and configure a sample connector in the Security & Compliance Center to import and archive data from your organization's Twitter account.</span></span> 

- <span data-ttu-id="8c6aa-115">您的组织需要一个 Twitter 帐户;设置连接器时需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-115">You need a Twitter account for your organization; you need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="8c6aa-116">您的组织必须具有有效的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-116">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="8c6aa-117">如果没有现有的 Azure 订阅，则可以注册以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="8c6aa-117">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="8c6aa-118">注册免费 1 年 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="8c6aa-118">Sign up for a free 1 year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="8c6aa-119">注册即用即付 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="8c6aa-119">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="8c6aa-120">Office 365 订阅中包含的[免费 Azure 活动目录订阅](use-your-free-azure-ad-subscription-in-office-365.md)不支持安全&合规性中心中的示例连接器。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-120">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Office 365 subscription doesn't support the sample connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="8c6aa-121">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-121">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="8c6aa-122">要同意此请求，请转到[此页面，](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)使用 Office 365 全局管理员的凭据登录，然后接受该请求。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-122">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="8c6aa-123">在"安全&合规性"中设置自定义连接器的用户（在步骤 7 中）必须在 Exchange 联机中分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-123">The user who sets up the custom connector in the Security & Compliance (in Step 7) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="8c6aa-124">默认情况下，此角色不会分配给 Exchange 联机中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-124">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="8c6aa-125">您可以将邮箱导入导出角色添加到"联机交换"中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-125">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="8c6aa-126">或者，您可以创建一个新的角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-126">Or you can create a new role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="8c6aa-127">有关详细信息，请参阅"在联机交换中管理角色组"一文[中的"创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色组"](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)部分。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-127">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a><span data-ttu-id="8c6aa-128">第 1 步：从 Github 下载预构建的连接器应用包</span><span class="sxs-lookup"><span data-stu-id="8c6aa-128">Step 1: Download the pre-built connector app package from Github</span></span>

<span data-ttu-id="8c6aa-129">第一步是下载 Twitter 示例连接器应用的源代码，该应用程序将使用 Twitter API 连接到您的 Twitter 帐户并提取数据，以便将其导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-129">The first step is to download the source code for the Twitter sample connector app that will use a Twitter API to connect to your Twitter account and extract data so you can import it to Office 365.</span></span>

1. <span data-ttu-id="8c6aa-130">转到[此 GitHub 站点。](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)</span><span class="sxs-lookup"><span data-stu-id="8c6aa-130">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> 
2. <span data-ttu-id="8c6aa-131">在最新版本下，单击**示例连接器.zip**文件。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-131">Under the latest release, click the **SampleConnector.zip** file.</span></span>
3. <span data-ttu-id="8c6aa-132">将 ZIP 文件保存到本地计算机上的位置。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-132">Save the ZIP file to a location on your local computer.</span></span> <span data-ttu-id="8c6aa-133">在步骤 4 中将此 zip 文件上载到 Azure。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-133">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="8c6aa-134">步骤 2：在 Azure 活动目录中创建应用</span><span class="sxs-lookup"><span data-stu-id="8c6aa-134">Step 2: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="8c6aa-135">下一步是在 Azure 活动目录 （AAD） 中注册新应用。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-135">The next step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="8c6aa-136">此应用程序对应于您在步骤 4 中为 Twitter 连接器实现的 Web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-136">This app corresponds to the web app resource that you implement in Step 4 for the Twitter connector.</span></span> 

<span data-ttu-id="8c6aa-137">有关分步说明，请参阅[步骤 2：在 Azure 活动目录中创建应用。](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory)</span><span class="sxs-lookup"><span data-stu-id="8c6aa-137">For step-by-step instructions, see [Step 2: Create an app in Azure Active Directory](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="8c6aa-138">在完成此步骤期间（按照分步说明执行），您将将以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-138">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="8c6aa-139">这些值将在部署过程中的后续步骤中使用。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-139">The values for these will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="8c6aa-140">AAD 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="8c6aa-140">AAD application ID</span></span>
- <span data-ttu-id="8c6aa-141">AAD 应用程序机密</span><span class="sxs-lookup"><span data-stu-id="8c6aa-141">AAD application secret</span></span>
- <span data-ttu-id="8c6aa-142">AAD 应用程序 Uri</span><span class="sxs-lookup"><span data-stu-id="8c6aa-142">AAD application Uri</span></span>
- <span data-ttu-id="8c6aa-143">租户 ID</span><span class="sxs-lookup"><span data-stu-id="8c6aa-143">Tenant Id</span></span>

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="8c6aa-144">步骤 3：创建 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="8c6aa-144">Step 3: Create an Azure storage account</span></span>

<span data-ttu-id="8c6aa-145">为组织部署的 Twitter 连接器将项目从 Twitter 上载到您在此步骤中创建的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-145">The Twitter connector that you deploy for your organization uploads the items from Twitter to the Azure storage location that you create in this step.</span></span> <span data-ttu-id="8c6aa-146">在安全&合规性中心（在步骤 7 中）创建自定义连接器后，Office 365 导入服务将从 Azure 存储位置将 Twitter 数据复制到 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-146">After you create a custom connector in the Security & Compliance Center (in Step 7), the Office 365 Import service will copy the Twitter data from the Azure storage location to a mailbox in Office 365.</span></span> <span data-ttu-id="8c6aa-147">如前面[在"先决条件"](#prerequisites-for-setting-up-a-connector-for-twitter)部分中所述，您必须具有有效的 Azure 订阅才能创建 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-147">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-twitter) section, you must have a valid Azure subscription to create an Azure storage account.</span></span>

<span data-ttu-id="8c6aa-148">有关分步说明，请参阅[步骤 3：创建 Azure 存储帐户](deploy-twitter-connector.md#step-3-create-an-azure-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-148">For step-by-step instructions, see [Step 3: Create an Azure storage account](deploy-twitter-connector.md#step-3-create-an-azure-storage-account).</span></span>

<span data-ttu-id="8c6aa-149">在完成此步骤（按照分步说明执行）期间，可以保存生成的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-149">During the completion of this step (by following the step-by-step instructions) you save the connection string Uri that is generated.</span></span> <span data-ttu-id="8c6aa-150">在步骤 4 中在 Azure 中创建 Web 应用资源时使用此字符串。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-150">You use this string when creating a web app resource in Azure in Step 4.</span></span>

## <a name="step-4-create-a-web-app-resource-in-azure"></a><span data-ttu-id="8c6aa-151">步骤 4：在 Azure 中创建 Web 应用资源</span><span class="sxs-lookup"><span data-stu-id="8c6aa-151">Step 4: Create a web app resource in Azure</span></span>

<span data-ttu-id="8c6aa-152">下一步是在 Azure 中为 Twitter 连接器创建 Web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-152">The next step is to create a web app resource in Azure for the Twitter connector.</span></span> 

<span data-ttu-id="8c6aa-153">有关分步说明，请参阅[步骤 4：在 Azure 中创建新的 Web 应用资源。](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure)</span><span class="sxs-lookup"><span data-stu-id="8c6aa-153">For step-by-step instructions, see [Step 4: Create a new web app resource in Azure](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure).</span></span>

<span data-ttu-id="8c6aa-154">在完成此步骤期间（按照分步说明执行），您将在创建 Web 应用资源时提供以下信息（在完成上述步骤后已复制到文本文件）。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-154">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps) when creating the web app resource.</span></span>

- <span data-ttu-id="8c6aa-155">API机密密钥 – 在完成此步骤期间，您创建此机密;它在步骤 7 中使用。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-155">APISecretKey – You create this secret during the completion of this step; it's used in Step 7.</span></span>
- <span data-ttu-id="8c6aa-156">存储帐户连接字符串 – 在步骤 3 中创建 Azure 存储帐户后复制的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-156">StorageAccountConnectionString – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>
- <span data-ttu-id="8c6aa-157">租户 Id = 在步骤 2 中在 Azure 活动目录中创建 Twitter 连接器应用后复制的 Office 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-157">tenantId – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

<span data-ttu-id="8c6aa-158">此外，在此步骤中，您还会上传 SampleConnector.zip 文件（在步骤 1 中下载的文件），以部署 Twitter 连接器应用的源代码。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-158">Also, you upload the SampleConnector.zip file (that you downloaded in Step 1) in this step to deploy the source code for the Twitter connector app.</span></span>

<span data-ttu-id="8c6aa-159">完成此步骤后，请确保复制 Azure 应用服务 URL（例如。 https://twitterconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="8c6aa-159">After completing this step, be sure to copy the Azure app service URL (for example, https://twitterconnector.azurewebsites.net).</span></span> <span data-ttu-id="8c6aa-160">您需要使用它来完成步骤 5、步骤 6 和步骤 7）。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-160">You need to use this to complete Step 5, Step 6, and Step 7).</span></span>

## <a name="step-5-create-developer-app-on-twitter"></a><span data-ttu-id="8c6aa-161">第 5 步：在 Twitter 上创建开发人员应用程序</span><span class="sxs-lookup"><span data-stu-id="8c6aa-161">Step 5: Create developer app on Twitter</span></span>

<span data-ttu-id="8c6aa-162">下一步是在 Twitter 上创建和配置开发人员应用。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-162">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="8c6aa-163">您在步骤 7 中创建的自定义连接器使用 Twitter 应用与 Twitter API 交互，以便从组织的 Twitter 帐户获取数据。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-163">The custom connector that you create in Step 7 uses the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="8c6aa-164">有关分步说明，请参阅[步骤 5：创建 Twitter 应用](deploy-twitter-connector.md#step-5-create-the-twitter-app)。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-164">For step-by-step instructions, see [Step 5: Create the Twitter app](deploy-twitter-connector.md#step-5-create-the-twitter-app).</span></span>

<span data-ttu-id="8c6aa-165">在完成此步骤期间（按照分步说明执行），您可以将以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-165">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="8c6aa-166">这些值将用于在步骤 6 中配置 Twitter 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-166">The values for these will be used to configure the Twitter connector app in Step 6.</span></span>

- <span data-ttu-id="8c6aa-167">推特API密钥</span><span class="sxs-lookup"><span data-stu-id="8c6aa-167">Twitter API Key</span></span>
- <span data-ttu-id="8c6aa-168">推特API密钥</span><span class="sxs-lookup"><span data-stu-id="8c6aa-168">Twitter API Secret Key</span></span>
- <span data-ttu-id="8c6aa-169">推特访问令牌</span><span class="sxs-lookup"><span data-stu-id="8c6aa-169">Twitter Access Token</span></span>
- <span data-ttu-id="8c6aa-170">推特访问令牌秘密</span><span class="sxs-lookup"><span data-stu-id="8c6aa-170">Twitter Access Token Secret</span></span>

## <a name="step-6-configure-the-twitter-connector-app"></a><span data-ttu-id="8c6aa-171">第 6 步：配置 Twitter 连接器应用</span><span class="sxs-lookup"><span data-stu-id="8c6aa-171">Step 6: Configure the Twitter connector app</span></span>

<span data-ttu-id="8c6aa-172">下一步是向在步骤 4 中创建 Azure Web 应用资源时上传的 Twitter 连接器应用添加配置设置。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-172">The next step is to add configurations settings to the Twitter connector app that you uploaded when you created the Azure web app resource in Step 4.</span></span> <span data-ttu-id="8c6aa-173">为此，请访问连接器应用的主页并配置它。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-173">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="8c6aa-174">有关分步说明，请参阅[步骤 6：配置连接器 Web 应用](deploy-twitter-connector.md#step-6-configure-the-connector-web-app)。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-174">For step-by-step instructions, see [Step 6: Configure the connector web app](deploy-twitter-connector.md#step-6-configure-the-connector-web-app).</span></span>

<span data-ttu-id="8c6aa-175">在完成此步骤期间（按照分步说明执行），您将提供以下信息（在完成上述步骤后已复制到文本文件）：</span><span class="sxs-lookup"><span data-stu-id="8c6aa-175">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="8c6aa-176">推特 API 密钥（在步骤 5 中获得）</span><span class="sxs-lookup"><span data-stu-id="8c6aa-176">Twitter API Key (obtained in Step 5)</span></span>
- <span data-ttu-id="8c6aa-177">推特 API 密钥（在步骤 5 中获得）</span><span class="sxs-lookup"><span data-stu-id="8c6aa-177">Twitter API Secret Key (obtained in Step 5)</span></span>
- <span data-ttu-id="8c6aa-178">推特访问令牌（在步骤 5 中获得）</span><span class="sxs-lookup"><span data-stu-id="8c6aa-178">Twitter Access Token (obtained in Step 5)</span></span>
- <span data-ttu-id="8c6aa-179">Twitter 访问令牌机密（在步骤 5 中获取）</span><span class="sxs-lookup"><span data-stu-id="8c6aa-179">Twitter Access Token Secret (obtained in Step 5)</span></span>
- <span data-ttu-id="8c6aa-180">Azure 活动目录应用程序 ID（步骤 2 中获取的 AAD 应用程序 ID）</span><span class="sxs-lookup"><span data-stu-id="8c6aa-180">Azure Active Directory application ID (the AAD application ID obtained in Step 2)</span></span>
- <span data-ttu-id="8c6aa-181">Azure 活动目录应用程序密钥（步骤 2 中获取的 AAD 应用程序密钥）</span><span class="sxs-lookup"><span data-stu-id="8c6aa-181">Azure Active Directory application secret (the AAD application secret obtained in Step 2)</span></span>
- <span data-ttu-id="8c6aa-182">Azure 活动目录应用程序 Uri（步骤 2 中获取的 AAD 应用程序 Uri;例如，https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span><span class="sxs-lookup"><span data-stu-id="8c6aa-182">Azure Active Directory application Uri (the AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="8c6aa-183">步骤 7：在安全&合规性中心设置自定义连接器</span><span class="sxs-lookup"><span data-stu-id="8c6aa-183">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

<span data-ttu-id="8c6aa-184">最后一步是在安全&合规性中心中设置自定义连接器，该连接器将数据从组织的 Twitter 帐户导入 Office 365 中的指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-184">The final step is to set up the custom connector in the Security & Compliance Center that imports data from your organization's Twitter account to a specified mailbox in Office 365.</span></span> <span data-ttu-id="8c6aa-185">成功完成此步骤后，Office 365 导入服务将开始将数据从 Twitter 导入 Office 365 的过程。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-185">After you successfully complete this step, the Office 365 Import service will start the process of importing data from Twitter to Office 365.</span></span> 

<span data-ttu-id="8c6aa-186">有关分步说明，请参阅[步骤 7：在安全和合规性中心中设置自定义连接器。](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="8c6aa-186">For step-by-step instructions, see [Step 7: Set up a custom connector in the security and compliance center](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center).</span></span> 

<span data-ttu-id="8c6aa-187">在完成此步骤期间（按照分步说明执行），您将提供以下信息（完成这些步骤后已复制到文本文件）。</span><span class="sxs-lookup"><span data-stu-id="8c6aa-187">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="8c6aa-188">Azure 应用服务 URL（在步骤 4 中获取;例如，https://twitterconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="8c6aa-188">Azure app service URL (obtained in Step 4; for example, https://twitterconnector.azurewebsites.net)</span></span>
- <span data-ttu-id="8c6aa-189">API 机密密钥（您在步骤 4 中创建）</span><span class="sxs-lookup"><span data-stu-id="8c6aa-189">APISecretKey (that you created in Step 4)</span></span>
