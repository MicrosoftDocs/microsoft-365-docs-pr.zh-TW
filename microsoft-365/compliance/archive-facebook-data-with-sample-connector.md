---
title: 使用示例连接器在 Office 365（预览版）中存档 Facebook 数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器，以便从数据源（如 Facebook 商业页面、Twitter、LinkedIn公司页面和即时彭博）导入第三方数据。 这样，您就可以在 Office 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如法律保留、内容搜索和保留策略）来管理组织第三方数据的治理。
ms.openlocfilehash: 2dde58e4d3ead0064e28c1ba1bfc04485c7a25df
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076710"
---
# <a name="use-a-sample-connector-to-archive-facebook-data-in-office-365-preview"></a><span data-ttu-id="d4d10-104">使用示例连接器在 Office 365（预览版）中存档 Facebook 数据</span><span class="sxs-lookup"><span data-stu-id="d4d10-104">Use a sample connector to archive Facebook data in Office 365 (Preview)</span></span>

<span data-ttu-id="d4d10-105">在 Office 365 中存档 Facebook 数据的示例连接器功能处于预览版。</span><span class="sxs-lookup"><span data-stu-id="d4d10-105">The sample connector feature to archive Facebook data in Office 365 is in Preview.</span></span>

<span data-ttu-id="d4d10-106">使用 Office 365 中的安全&合规性中心中的示例连接器将数据从 Facebook 业务页导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d4d10-106">Use a sample connector in the Security & Compliance Center in Office 365 to import and archive data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="d4d10-107">设置和配置示例连接器后，它将连接到 Facebook 商业页面（按计划），将 Facebook 项目的内容转换为电子邮件格式，然后将这些项目导入 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="d4d10-107">After you set up and configure a sample connector, it connects to the Facebook Business page (on a scheduled basis), converts the content of Facebook items to an email message format, and then imports those items to a mailbox in Office 365.</span></span>

<span data-ttu-id="d4d10-108">导入 Facebook 数据后，您可以将 Office 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核、监督和 Office 365 保留策略）应用于 Facebook 数据。</span><span class="sxs-lookup"><span data-stu-id="d4d10-108">After the Facebook data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Supervision, and Office 365 retention policies to the Facebook data.</span></span> <span data-ttu-id="d4d10-109">例如，当邮箱被置于诉讼保留或分配给保留策略时，Facebook 数据将被保留。</span><span class="sxs-lookup"><span data-stu-id="d4d10-109">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Facebook data is preserved.</span></span> <span data-ttu-id="d4d10-110">您可以使用内容搜索搜索第三方数据，或将存储 Facebook 数据的邮箱与高级电子数据展示案例中的保管人相关联。</span><span class="sxs-lookup"><span data-stu-id="d4d10-110">You can search third-party data using Content Search or associate the mailbox where the Facebook data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="d4d10-111">使用连接器在 Office 365 中导入和存档 Facebook 数据可帮助您的组织遵守政府和监管政策。</span><span class="sxs-lookup"><span data-stu-id="d4d10-111">Using a connector to import and archive Facebook data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

> [!NOTE]
> <span data-ttu-id="d4d10-112">目前，只有 Facebook 商业页面和[Twitter](archive-twitter-data-with-sample-connector.md)的示例连接器可供预览。</span><span class="sxs-lookup"><span data-stu-id="d4d10-112">At this time, only the sample connectors for Facebook Business pages and [Twitter](archive-twitter-data-with-sample-connector.md) is available for Preview.</span></span> <span data-ttu-id="d4d10-113">更多示例连接器即将推出。</span><span class="sxs-lookup"><span data-stu-id="d4d10-113">More sample connectors are coming soon.</span></span>


## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a><span data-ttu-id="d4d10-114">为 Facebook 商业页面设置连接器的先决条件</span><span class="sxs-lookup"><span data-stu-id="d4d10-114">Prerequisites for setting up a connector for Facebook Business pages</span></span>

<span data-ttu-id="d4d10-115">您必须完成以下先决条件，然后才能在安全&合规性中心设置和配置示例连接器，以便从组织的 Facebook 业务页面导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="d4d10-115">You must complete the following prerequisites before you can set up and configure a sample connector in the Security & Compliance Center to import and archive data from your organization's Facebook Business pages.</span></span> 

- <span data-ttu-id="d4d10-116">您的组织的业务页面需要 Facebook 帐户（在设置连接器时需要登录到此帐户）。</span><span class="sxs-lookup"><span data-stu-id="d4d10-116">You need a Facebook account for your organization's business pages (you need to sign in to this account when setting up the connector).</span></span> <span data-ttu-id="d4d10-117">目前，您只能存档来自 Facebook 商业页面的数据;您无法存档来自单个 Facebook 个人资料的数据。</span><span class="sxs-lookup"><span data-stu-id="d4d10-117">Currently, you can only archive data from Facebook Business pages; you can't archive data from individual Facebook profiles.</span></span>

- <span data-ttu-id="d4d10-118">您的组织必须具有有效的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="d4d10-118">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="d4d10-119">如果没有现有的 Azure 订阅，则可以注册以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="d4d10-119">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="d4d10-120">注册免费一年 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="d4d10-120">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="d4d10-121">注册即用即付 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="d4d10-121">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="d4d10-122">Office 365 订阅中包含的[免费 Azure 活动目录订阅](use-your-free-azure-ad-subscription-in-office-365.md)不支持安全&合规性中心中的示例连接器。</span><span class="sxs-lookup"><span data-stu-id="d4d10-122">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Office 365 subscription doesn't support the sample connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="d4d10-123">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="d4d10-123">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="d4d10-124">要同意此请求，请转到[此页面，](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)使用 Office 365 全局管理员的凭据登录，然后接受该请求。</span><span class="sxs-lookup"><span data-stu-id="d4d10-124">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="d4d10-125">在"安全&合规性"中设置自定义连接器的用户（在步骤 7 中）必须在 Exchange 联机中分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="d4d10-125">The user who sets up the custom connector in the Security & Compliance (in Step 7) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d4d10-126">默认情况下，此角色不会分配给 Exchange 联机中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="d4d10-126">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="d4d10-127">您可以将邮箱导入导出角色添加到"联机交换"中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="d4d10-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d4d10-128">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="d4d10-128">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d4d10-129">有关详细信息，请参阅"在联机交换中管理角色组"一文[中的"创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色组"](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)部分。</span><span class="sxs-lookup"><span data-stu-id="d4d10-129">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a><span data-ttu-id="d4d10-130">第 1 步：从 Github 下载预构建的连接器应用包</span><span class="sxs-lookup"><span data-stu-id="d4d10-130">Step 1: Download the pre-built connector app package from Github</span></span>

<span data-ttu-id="d4d10-131">第一步是下载预构建的 Facebook 连接器应用的源代码，该应用将使用 Facebook API 连接到您的 Facebook 商业页面并提取 Facebook 数据，以便您可以将其导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d4d10-131">The first step is to download the source code for the pre-built Facebook connector app that will use a Facebook API to connect to your Facebook Business pages and extract Facebook data so you can import it to Office 365.</span></span>

1. <span data-ttu-id="d4d10-132">转到[此 GitHub 站点。](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases)</span><span class="sxs-lookup"><span data-stu-id="d4d10-132">Go to [this GitHub site](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases).</span></span> 
2. <span data-ttu-id="d4d10-133">在最新版本下，单击**示例连接器.zip**文件。</span><span class="sxs-lookup"><span data-stu-id="d4d10-133">Under the latest release, click the **SampleConnector.zip** file.</span></span>
3. <span data-ttu-id="d4d10-134">将 ZIP 文件保存到本地计算机上的位置。</span><span class="sxs-lookup"><span data-stu-id="d4d10-134">Save the ZIP file to a location on your local computer.</span></span> <span data-ttu-id="d4d10-135">在步骤 4 中将此 zip 文件上载到 Azure。</span><span class="sxs-lookup"><span data-stu-id="d4d10-135">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="d4d10-136">步骤 2：在 Azure 活动目录中创建应用</span><span class="sxs-lookup"><span data-stu-id="d4d10-136">Step 2: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="d4d10-137">下一步是在 Azure 活动目录 （AAD） 中注册新应用。</span><span class="sxs-lookup"><span data-stu-id="d4d10-137">The next step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="d4d10-138">此应用程序对应于您在步骤 4 中为 Facebook 连接器实现的 Web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="d4d10-138">This app corresponds to the web app resource that you implement in Step 4 for the Facebook connector.</span></span> 

<span data-ttu-id="d4d10-139">有关分步说明，请参阅在 Azure[活动目录中创建应用。](deploy-facebook-connector.md#step-2-create-an-app-in-azure-active-directory)</span><span class="sxs-lookup"><span data-stu-id="d4d10-139">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-2-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="d4d10-140">在完成此步骤期间（通过使用前面的分步说明），您将将以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="d4d10-140">During the completion of this step (by using the previous step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="d4d10-141">这些值在部署过程中的后续步骤中使用。</span><span class="sxs-lookup"><span data-stu-id="d4d10-141">These values are used in later steps in the deployment process.</span></span>

- <span data-ttu-id="d4d10-142">AAD 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="d4d10-142">AAD application ID</span></span>
- <span data-ttu-id="d4d10-143">AAD 应用程序机密</span><span class="sxs-lookup"><span data-stu-id="d4d10-143">AAD application secret</span></span>
- <span data-ttu-id="d4d10-144">AAD 应用程序 Uri</span><span class="sxs-lookup"><span data-stu-id="d4d10-144">AAD application Uri</span></span>
- <span data-ttu-id="d4d10-145">租户 ID</span><span class="sxs-lookup"><span data-stu-id="d4d10-145">Tenant Id</span></span>

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="d4d10-146">步骤 3：创建 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="d4d10-146">Step 3: Create an Azure Storage account</span></span>

<span data-ttu-id="d4d10-147">为组织部署的 Facebook 连接器会将项目从 Facebook 业务页面上载到您在此步骤中创建的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="d4d10-147">The Facebook Connector that you deploy for your organization will upload the items from your Facebook Business pages to the Azure storage location that you create in this step.</span></span> <span data-ttu-id="d4d10-148">在安全&合规性中心（在步骤 7 中）创建自定义连接器后，Office 365 导入服务将从 Azure 存储位置将 Facebook 数据复制到 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="d4d10-148">After you create a custom connector in the Security & Compliance Center (in Step 7), the Office 365 Import service will copy the Facebook data from the Azure storage location to a mailbox in Office 365.</span></span> <span data-ttu-id="d4d10-149">如前面[在"先决条件"](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)部分中所述，您必须具有有效的 Azure 订阅才能创建 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="d4d10-149">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="d4d10-150">有关分步说明，请参阅创建 Azure[存储帐户](deploy-facebook-connector.md#step-3-create-an-azure-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="d4d10-150">For step-by-step instructions, see [Create an Azure storage account](deploy-facebook-connector.md#step-3-create-an-azure-storage-account).</span></span>

<span data-ttu-id="d4d10-151">在此步骤完成期间（按照分步说明执行），可以保存生成的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="d4d10-151">During the completion of this step (by following the step-by-step instructions), you save the connection string Uri that is generated.</span></span> <span data-ttu-id="d4d10-152">在步骤 4 中在 Azure 中创建 Web 应用资源时使用此字符串。</span><span class="sxs-lookup"><span data-stu-id="d4d10-152">You use this string when creating a web app resource in Azure in Step 4.</span></span>

## <a name="step-4-create-a-web-app-resource-in-azure"></a><span data-ttu-id="d4d10-153">步骤 4：在 Azure 中创建 Web 应用资源</span><span class="sxs-lookup"><span data-stu-id="d4d10-153">Step 4: Create a web app resource in Azure</span></span>

<span data-ttu-id="d4d10-154">下一步是在 Azure 中为 Facebook 连接器创建 Web 应用资源。</span><span class="sxs-lookup"><span data-stu-id="d4d10-154">The next step is to create a web app resource in Azure for the Facebook Connector.</span></span> 

<span data-ttu-id="d4d10-155">有关分步说明，请参阅在 Azure[中创建新的 Web 应用资源。](deploy-facebook-connector.md#step-4-create-a-new-web-app-resource-in-azure)</span><span class="sxs-lookup"><span data-stu-id="d4d10-155">For step-by-step instructions, see [Create a new web app resource in Azure](deploy-facebook-connector.md#step-4-create-a-new-web-app-resource-in-azure).</span></span>

<span data-ttu-id="d4d10-156">在完成此步骤期间（按照分步说明执行），在创建 Web 应用资源时，您将提供以下信息（在完成上述步骤后已复制到文本文件）。</span><span class="sxs-lookup"><span data-stu-id="d4d10-156">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the previous steps) when creating the web app resource.</span></span>

- <span data-ttu-id="d4d10-157">API机密密钥 – 在完成此步骤期间创建此机密;它在步骤 7 中使用。</span><span class="sxs-lookup"><span data-stu-id="d4d10-157">APISecretKey — You create this secret during the completion of this step; it is used in Step 7.</span></span>
- <span data-ttu-id="d4d10-158">存储帐户连接字符串 – 在步骤 3 中创建 Azure 存储帐户后复制的连接字符串 Uri。</span><span class="sxs-lookup"><span data-stu-id="d4d10-158">StorageAccountConnectionString – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>
- <span data-ttu-id="d4d10-159">租户 Id = 在步骤 2 中在 Azure 活动目录中创建 Facebook 连接器应用后复制的 Office 365 组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="d4d10-159">tenantId – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

<span data-ttu-id="d4d10-160">此外，在此步骤中，您上传 SampleConnector.zip 文件（在步骤 1 中下载），以部署 Facebook 连接器应用的源代码。</span><span class="sxs-lookup"><span data-stu-id="d4d10-160">Additionally, you upload the SampleConnector.zip file (that you downloaded in Step 1) in this step to deploy the source code for the Facebook connector app.</span></span>

<span data-ttu-id="d4d10-161">完成此步骤后，请确保复制应用服务 URL（例如， https://fbconnector.azurewebsites.net)。</span><span class="sxs-lookup"><span data-stu-id="d4d10-161">After completing this step, be sure to copy the app Service URL (for example, https://fbconnector.azurewebsites.net).</span></span> <span data-ttu-id="d4d10-162">您需要使用它来完成步骤 5、步骤 6 和步骤 7）。</span><span class="sxs-lookup"><span data-stu-id="d4d10-162">You need to use this to complete Step 5, Step 6, and Step 7).</span></span>

## <a name="step-5-register-the-web-app-on-facebook"></a><span data-ttu-id="d4d10-163">第 5 步：在 Facebook 上注册 Web 应用</span><span class="sxs-lookup"><span data-stu-id="d4d10-163">Step 5: Register the web app on Facebook</span></span>

<span data-ttu-id="d4d10-164">下一步是在 Facebook 上创建和配置新应用。</span><span class="sxs-lookup"><span data-stu-id="d4d10-164">The next step is to create and configure a new app on Facebook.</span></span> <span data-ttu-id="d4d10-165">您在步骤 7 中创建的自定义连接器使用 Facebook Web 应用与 Facebook API 交互，以便从组织的 Facebook 业务页面获取数据。</span><span class="sxs-lookup"><span data-stu-id="d4d10-165">The custom connector that you create in Step 7 uses the Facebook web app to interact with the Facebook API to obtain data from your organization's Facebook Business pages.</span></span>

<span data-ttu-id="d4d10-166">有关分步说明，请参阅注册 Facebook[应用](deploy-facebook-connector.md#step-5-register-the-facebook-app)。</span><span class="sxs-lookup"><span data-stu-id="d4d10-166">For step-by-step instructions, see [Register the Facebook app](deploy-facebook-connector.md#step-5-register-the-facebook-app).</span></span>

<span data-ttu-id="d4d10-167">在完成此步骤期间（按照分步说明执行），您可以将以下信息保存到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="d4d10-167">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="d4d10-168">这些值用于在步骤 6 中配置 Facebook 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="d4d10-168">The values are used to configure the Facebook connector app in Step 6.</span></span>

- <span data-ttu-id="d4d10-169">Facebook 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="d4d10-169">Facebook application ID</span></span>
- <span data-ttu-id="d4d10-170">Facebook 应用程序机密</span><span class="sxs-lookup"><span data-stu-id="d4d10-170">Facebook application secret</span></span>
- <span data-ttu-id="d4d10-171">Facebook 网络挂钩验证令牌</span><span class="sxs-lookup"><span data-stu-id="d4d10-171">Facebook webhooks verify token</span></span>

## <a name="step-6-configure-the-facebook-connector-app"></a><span data-ttu-id="d4d10-172">第 6 步：配置 Facebook 连接器应用</span><span class="sxs-lookup"><span data-stu-id="d4d10-172">Step 6: Configure the Facebook connector app</span></span>

<span data-ttu-id="d4d10-173">下一步是向在步骤 4 中创建 Azure Web 应用资源时上传的 Facebook 连接器应用添加配置设置。</span><span class="sxs-lookup"><span data-stu-id="d4d10-173">The next step is to add configurations settings to the Facebook connector app that you uploaded when you created the Azure web app resource in Step 4.</span></span> <span data-ttu-id="d4d10-174">为此，请访问连接器应用的主页并配置它。</span><span class="sxs-lookup"><span data-stu-id="d4d10-174">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="d4d10-175">有关分步说明，请参阅[步骤 6：配置连接器 Web 应用](deploy-facebook-connector.md#step-6-configure-the-connector-web-app)。</span><span class="sxs-lookup"><span data-stu-id="d4d10-175">For step-by-step instructions, see [Step 6: Configure the connector web app](deploy-facebook-connector.md#step-6-configure-the-connector-web-app).</span></span>

<span data-ttu-id="d4d10-176">在完成此步骤期间（按照分步说明执行），您提供以下信息（在完成上述步骤后已复制到文本文件）：</span><span class="sxs-lookup"><span data-stu-id="d4d10-176">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="d4d10-177">Facebook 应用程序 ID（在步骤 5 中获取）</span><span class="sxs-lookup"><span data-stu-id="d4d10-177">Facebook application ID (obtained in Step 5)</span></span>
- <span data-ttu-id="d4d10-178">Facebook 应用程序机密（在步骤 5 中获取）</span><span class="sxs-lookup"><span data-stu-id="d4d10-178">Facebook application secret (obtained in Step 5)</span></span>
- <span data-ttu-id="d4d10-179">Facebook Webhook 验证令牌（在步骤 5 中获取）</span><span class="sxs-lookup"><span data-stu-id="d4d10-179">Facebook webhooks verify token (obtained in Step 5)</span></span>
- <span data-ttu-id="d4d10-180">Azure 活动目录应用程序 ID（步骤 2 中获取的 AAD 应用程序 ID）</span><span class="sxs-lookup"><span data-stu-id="d4d10-180">Azure Active Directory application ID (the AAD application ID obtained in Step 2)</span></span>
- <span data-ttu-id="d4d10-181">Azure 活动目录应用程序密钥（步骤 2 中获取的 AAD 应用程序密钥）</span><span class="sxs-lookup"><span data-stu-id="d4d10-181">Azure Active Directory application secret (the AAD application secret obtained in Step 2)</span></span>
- <span data-ttu-id="d4d10-182">Azure 活动目录应用程序 Uri（步骤 2 中获取的 AAD 应用程序 Uri;例如，https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span><span class="sxs-lookup"><span data-stu-id="d4d10-182">Azure Active Directory application Uri (the AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="d4d10-183">步骤 7：在安全&合规性中心设置自定义连接器</span><span class="sxs-lookup"><span data-stu-id="d4d10-183">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

<span data-ttu-id="d4d10-184">最后一步是在安全&合规性中心中设置自定义连接器，该连接器将从 Facebook 业务页面将数据导入 Office 365 中的指定邮箱。</span><span class="sxs-lookup"><span data-stu-id="d4d10-184">The final step is to set up the custom connector in the Security & Compliance Center that will import data from your Facebook Business pages to a specified mailbox in Office 365.</span></span> <span data-ttu-id="d4d10-185">完成此步骤后，Office 365 导入服务将开始将数据从 Facebook 业务页导入 Office 365 的过程。</span><span class="sxs-lookup"><span data-stu-id="d4d10-185">After you complete this step, the Office 365 Import service will start the process of importing data from your Facebook Business pages to Office 365.</span></span> 

<span data-ttu-id="d4d10-186">有关分步说明，请参阅[在安全&合规性中心中设置自定义连接器。](deploy-facebook-connector.md#step-7-set-up-a-custom-connector-in-the-security--compliance-center)</span><span class="sxs-lookup"><span data-stu-id="d4d10-186">For step-by-step instructions, see [Set up a custom connector in the Security & Compliance Center](deploy-facebook-connector.md#step-7-set-up-a-custom-connector-in-the-security--compliance-center).</span></span> 

<span data-ttu-id="d4d10-187">在完成此步骤期间（按照分步说明执行），您提供以下信息（完成这些步骤后已复制到文本文件）。</span><span class="sxs-lookup"><span data-stu-id="d4d10-187">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="d4d10-188">Azure 应用服务 URL（在步骤 4 中获取;例如，https://fbconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="d4d10-188">Azure app service URL (obtained in Step 4; for example, https://fbconnector.azurewebsites.net)</span></span>
- <span data-ttu-id="d4d10-189">API 机密密钥（您在步骤 4 中创建）</span><span class="sxs-lookup"><span data-stu-id="d4d10-189">APISecretKey (that you created in Step 4)</span></span>
