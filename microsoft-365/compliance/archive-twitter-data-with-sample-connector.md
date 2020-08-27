---
title: 設定連接器來封存 Twitter 資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 瞭解系統管理員如何設定和使用原生連接器，將 Twitter 資料匯入 Microsoft 365。
ms.openlocfilehash: 15434899eb90f26205907c474b8d2238db536948
ms.sourcegitcommit: 195172dd836e8a793e8e0c2db3323b7391bc51ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255840"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a><span data-ttu-id="28c2e-103">設定連接器以封存 Twitter 資料 (預覽) </span><span class="sxs-lookup"><span data-stu-id="28c2e-103">Set up a connector to archive Twitter data (preview)</span></span>

<span data-ttu-id="28c2e-104">使用 Microsoft 365 規範中心內的連接器，將 Twitter 中的資料匯入並封存至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="28c2e-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Twitter to Microsoft 365.</span></span> <span data-ttu-id="28c2e-105">在您設定及設定連接器之後，它會依排程的方式，連線到您組織的 Twitter 帳戶 () 、將專案內容轉換為電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="28c2e-105">After you set up and configure the connector, it connects to your organization's Twitter account (on a scheduled basis), converts the content of an item to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="28c2e-106">在匯入 Twitter 資料之後，您可以將 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋、In-Place 封存、審核和 Microsoft 365 保留原則）套用至 Twitter 資料。</span><span class="sxs-lookup"><span data-stu-id="28c2e-106">After the Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to the Twitter data.</span></span> <span data-ttu-id="28c2e-107">例如，當信箱處於訴訟暫止狀態或指派給保留原則時，將會保留 Twitter 資料。</span><span class="sxs-lookup"><span data-stu-id="28c2e-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Twitter data is preserved.</span></span> <span data-ttu-id="28c2e-108">您可以使用內容搜尋來搜尋協力廠商資料，或在高級 eDiscovery 案例中關聯 Twitter 資料與保管人儲存的信箱。</span><span class="sxs-lookup"><span data-stu-id="28c2e-108">You can search third-party data using Content Search or associate the mailbox where the Twitter data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="28c2e-109">在 Microsoft 365 中使用連接器匯入及封存 Twitter 資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="28c2e-109">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="28c2e-110">在匯入 Twitter 資料之後，您可以對儲存在信箱中的資料套用 Microsoft 365 合規性功能，例如訴訟暫止、內容搜尋、In-Place 封存、審核、通訊法規遵從性及 Microsoft 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="28c2e-110">After Twitter data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the data stored in the mailbox.</span></span> <span data-ttu-id="28c2e-111">例如，您可以使用內容搜尋來搜尋 Twitter 資料，或在高級 eDiscovery 案例中，將儲存資料的信箱與系統管理員相關聯。</span><span class="sxs-lookup"><span data-stu-id="28c2e-111">For example, you can search Twitter data using Content Search or associate the mailbox where the data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="28c2e-112">在 Microsoft 365 中使用連接器匯入及封存 Twitter 資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="28c2e-112">Using a connector to import and archive Twitter data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a><span data-ttu-id="28c2e-113">為 Twitter 設定連接器的必要條件</span><span class="sxs-lookup"><span data-stu-id="28c2e-113">Prerequisites for setting up a connector for Twitter</span></span>

<span data-ttu-id="28c2e-114">完成下列必要條件，您才能在 Microsoft 365 規範中心內安裝和設定連接器，以便從組織的 Twitter 帳戶匯入及封存資料。</span><span class="sxs-lookup"><span data-stu-id="28c2e-114">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Twitter account.</span></span>

- <span data-ttu-id="28c2e-115">您的組織需要 Twitter 帳戶;您必須在設定連接器時登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="28c2e-115">You need a Twitter account for your organization; you need to sign in to this account when setting up the connector.</span></span>

- <span data-ttu-id="28c2e-116">您的組織必須具有有效的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="28c2e-116">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="28c2e-117">如果您沒有現有的 Azure 訂閱，您可以註冊下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="28c2e-117">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="28c2e-118">註冊免費的一年 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="28c2e-118">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free) 

    - [<span data-ttu-id="28c2e-119">註冊隨付即用 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="28c2e-119">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="28c2e-120">Microsoft 365 訂閱隨附的 [免費 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md) 不支援 Security & 合規性中心內的連接器。</span><span class="sxs-lookup"><span data-stu-id="28c2e-120">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="28c2e-121">您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。</span><span class="sxs-lookup"><span data-stu-id="28c2e-121">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="28c2e-122">若要同意此要求，請移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，並以全域管理員的認證登入，然後接受要求。</span><span class="sxs-lookup"><span data-stu-id="28c2e-122">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of a global admin, and then accept the request.</span></span>

- <span data-ttu-id="28c2e-123">在步驟 5) 中設定 Microsoft 365 規範 (中心內的 Twitter 連接器的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。</span><span class="sxs-lookup"><span data-stu-id="28c2e-123">The user who sets up the Twitter connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="28c2e-124">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="28c2e-124">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="28c2e-125">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="28c2e-125">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="28c2e-126">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="28c2e-126">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="28c2e-127">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [  [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="28c2e-127">For more information, see the  [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="28c2e-128">步驟1：在 Azure Active Directory 中建立應用程式</span><span class="sxs-lookup"><span data-stu-id="28c2e-128">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="28c2e-129">第一步是在 Azure Active Directory (AAD) 中註冊新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="28c2e-129">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="28c2e-130">此應用程式會對應至您在您的 Twitter 連接器的步驟2中所執行的 web 應用程式資源。</span><span class="sxs-lookup"><span data-stu-id="28c2e-130">This app corresponds to the web app resource that you implement in Step 2 for the Twitter connector.</span></span>

<span data-ttu-id="28c2e-131">如需逐步指示，請參閱 [在 Azure Active Directory 中建立應用程式](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="28c2e-131">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="28c2e-132">在完成此步驟時 (請遵循) 的逐步指示，將下列資訊儲存至文字檔。</span><span class="sxs-lookup"><span data-stu-id="28c2e-132">During the completion of this step (by following the step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="28c2e-133">這些值將會在部署程式的後續步驟中使用。</span><span class="sxs-lookup"><span data-stu-id="28c2e-133">These values will be used in later steps in the deployment process.</span></span>

- <span data-ttu-id="28c2e-134">AAD 應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="28c2e-134">AAD application ID</span></span>

- <span data-ttu-id="28c2e-135">AAD 應用程式機密</span><span class="sxs-lookup"><span data-stu-id="28c2e-135">AAD application secret</span></span>

- <span data-ttu-id="28c2e-136">租使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="28c2e-136">Tenant Id</span></span>

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a><span data-ttu-id="28c2e-137">步驟2：將連接器 web 服務從 GitHub 存放庫部署至您的 Azure 帳戶</span><span class="sxs-lookup"><span data-stu-id="28c2e-137">Step 2: Deploy connector web service from GitHub repository to your Azure account</span></span>

<span data-ttu-id="28c2e-138">下一步是部署 Twitter 連接器應用程式的原始程式碼，該應用程式會使用 Twitter API 連線到 Twitter 帳戶並提取資料，以便您將資料匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="28c2e-138">The next step is to deploy the source code for the Twitter connector app that will use Twitter API to connect to your Twitter account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="28c2e-139">您為組織部署的 Twitter 連接器會將組織的 Twitter 帳戶中的專案上傳至此步驟中建立的 Azure 儲存體位置。</span><span class="sxs-lookup"><span data-stu-id="28c2e-139">The Twitter connector that you deploy for your organization will upload the items from your organization's Twitter account to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="28c2e-140">在 [步驟 5) ] 中的 [Microsoft 365 規範 (中心] 中建立 Twitter 連接器之後，Office 365 匯入服務會將 Twitter 資料從 Azure 存放位置複製到 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="28c2e-140">After you create a Twitter connector in the Microsoft 365 compliance center (in Step 5), the Office 365 Import service will copy the Twitter data from the Azure Storage location to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="28c2e-141">如先前在 [必要條件](#prerequisites-for-setting-up-a-connector-for-twitter) 區段中所述，您必須具備有效的 azure 訂閱，才可建立 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="28c2e-141">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-twitter) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="28c2e-142">若要部署 Twitter 連接器應用程式的原始程式碼：</span><span class="sxs-lookup"><span data-stu-id="28c2e-142">To deploy the source code for the Twitter connector app:</span></span>

1. <span data-ttu-id="28c2e-143">移 [至此 GitHub 網站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)。</span><span class="sxs-lookup"><span data-stu-id="28c2e-143">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).</span></span>

2. <span data-ttu-id="28c2e-144">按一下 [ **部署至 Azure**]。</span><span class="sxs-lookup"><span data-stu-id="28c2e-144">Click **Deploy to Azure**.</span></span>

<span data-ttu-id="28c2e-145">如需逐步指示，請參閱 [將連接器 web 服務從 GitHub 部署至您的 Azure 帳戶](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。</span><span class="sxs-lookup"><span data-stu-id="28c2e-145">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="28c2e-146">當您遵循逐步指示來完成此步驟時，您會提供下列資訊。</span><span class="sxs-lookup"><span data-stu-id="28c2e-146">While you follow the step-by-step instructions to complete this step, you provide the following information</span></span>

- <span data-ttu-id="28c2e-147">APISecretKey：完成此步驟時，您會建立此密碼。</span><span class="sxs-lookup"><span data-stu-id="28c2e-147">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="28c2e-148">它會在步驟5中使用。</span><span class="sxs-lookup"><span data-stu-id="28c2e-148">It's used in Step 5.</span></span>

- <span data-ttu-id="28c2e-149">tenantId：在步驟1中，您在 Azure Active Directory 中建立 Twitter 應用程式之後所複製之 Microsoft 365 組織的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="28c2e-149">tenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Twitter app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="28c2e-150">完成此步驟後，請務必複製 app 服務 URL (例如， `https://twitterconnector.azurewebsites.net`) 。</span><span class="sxs-lookup"><span data-stu-id="28c2e-150">After completing this step, be sure to copy the app Service URL (for example, `https://twitterconnector.azurewebsites.net`).</span></span> <span data-ttu-id="28c2e-151">您必須使用此 URL，才能完成步驟3、步驟4及步驟 5) 。</span><span class="sxs-lookup"><span data-stu-id="28c2e-151">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-create-developer-app-on-twitter"></a><span data-ttu-id="28c2e-152">步驟3：建立 Twitter 上的開發人員應用程式</span><span class="sxs-lookup"><span data-stu-id="28c2e-152">Step 3: Create developer app on Twitter</span></span>

<span data-ttu-id="28c2e-153">下一步是建立及設定 Twitter 上的開發人員應用程式。</span><span class="sxs-lookup"><span data-stu-id="28c2e-153">The next step is to create and configure a developer app on Twitter.</span></span> <span data-ttu-id="28c2e-154">您在步驟7中建立的自訂連接器會使用 Twitter 應用程式與 Twitter API 互動，以從組織的 Twitter 帳戶取得資料。</span><span class="sxs-lookup"><span data-stu-id="28c2e-154">The custom connector that you create in Step 7 uses the Twitter app to interact with the Twitter API to obtain data from your organization's Twitter account.</span></span>

<span data-ttu-id="28c2e-155">如需逐步指示，請參閱 [建立 Twitter 應用程式](deploy-twitter-connector.md#step-3-create-the-twitter-app)。</span><span class="sxs-lookup"><span data-stu-id="28c2e-155">For step-by-step instructions, see [Create the Twitter app](deploy-twitter-connector.md#step-3-create-the-twitter-app).</span></span>

<span data-ttu-id="28c2e-156">在完成此步驟時 (請遵循) 的逐步指示，將下列資訊儲存至文字檔。</span><span class="sxs-lookup"><span data-stu-id="28c2e-156">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="28c2e-157">這些值將用於設定步驟4中的 Twitter 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="28c2e-157">These values will be used to configure the Twitter connector app in Step 4.</span></span>

- <span data-ttu-id="28c2e-158">Twitter API 金鑰</span><span class="sxs-lookup"><span data-stu-id="28c2e-158">Twitter API Key</span></span>

- <span data-ttu-id="28c2e-159">Twitter API 金鑰</span><span class="sxs-lookup"><span data-stu-id="28c2e-159">Twitter API Secret Key</span></span>

- <span data-ttu-id="28c2e-160">Twitter 存取權杖</span><span class="sxs-lookup"><span data-stu-id="28c2e-160">Twitter Access Token</span></span>

- <span data-ttu-id="28c2e-161">Twitter 存取權杖機密</span><span class="sxs-lookup"><span data-stu-id="28c2e-161">Twitter Access Token Secret</span></span>

## <a name="step-4-configure-the-twitter-connector-app"></a><span data-ttu-id="28c2e-162">步驟4：設定 Twitter 連接器應用程式</span><span class="sxs-lookup"><span data-stu-id="28c2e-162">Step 4: Configure the Twitter connector app</span></span>

<span data-ttu-id="28c2e-163">下一步是將設定設定新增至您在步驟2中部署的 Twitter 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="28c2e-163">The next step is to add configurations settings to the Twitter connector app that you deployed in Step 2.</span></span> <span data-ttu-id="28c2e-164">若要執行此動作，請移至連接器應用程式的首頁並加以設定。</span><span class="sxs-lookup"><span data-stu-id="28c2e-164">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="28c2e-165">如需逐步指示，請參閱 Configure the [connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)。</span><span class="sxs-lookup"><span data-stu-id="28c2e-165">For step-by-step instructions, see [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).</span></span>

<span data-ttu-id="28c2e-166">在此步驟完成過程中 (按逐步指示) 中，您將會提供下列資訊， (在完成上述步驟) 之後，您已複製到文字檔：</span><span class="sxs-lookup"><span data-stu-id="28c2e-166">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="28c2e-167">在步驟3中取得的 Twitter API 金鑰 () </span><span class="sxs-lookup"><span data-stu-id="28c2e-167">Twitter API Key (obtained in Step 3)</span></span>

- <span data-ttu-id="28c2e-168">在步驟3中取得的 Twitter API 私密金鑰 () </span><span class="sxs-lookup"><span data-stu-id="28c2e-168">Twitter API Secret Key (obtained in Step 3)</span></span>

- <span data-ttu-id="28c2e-169">在步驟3中取得的 Twitter 存取權杖 () </span><span class="sxs-lookup"><span data-stu-id="28c2e-169">Twitter Access Token (obtained in Step 3)</span></span>

- <span data-ttu-id="28c2e-170">在步驟3中取得的 Twitter 存取權杖機密 () </span><span class="sxs-lookup"><span data-stu-id="28c2e-170">Twitter Access Token Secret (obtained in Step 3)</span></span>

- <span data-ttu-id="28c2e-171">在步驟1中取得的 AAD 應用程式識別碼 (Azure Active Directory 應用程式識別碼) </span><span class="sxs-lookup"><span data-stu-id="28c2e-171">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="28c2e-172">Azure Active Directory 應用程式機密 (步驟1中取得的 AAD 應用程式密碼) </span><span class="sxs-lookup"><span data-stu-id="28c2e-172">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="28c2e-173">步驟5：在 Microsoft 365 規範中心設定 Twitter 連接器</span><span class="sxs-lookup"><span data-stu-id="28c2e-173">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="28c2e-174">最後一個步驟是在 Microsoft 365 規範中心內設定 Twitter 連接器，將您組織的 Twitter 帳戶中的資料匯入至 Microsoft 365 中的指定信箱。</span><span class="sxs-lookup"><span data-stu-id="28c2e-174">The final step is to set up the Twitter connector in the Microsoft 365 compliance center that will import data from your organization's Twitter account to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="28c2e-175">完成此步驟後，Office 365 匯入服務將開始從您組織的 Twitter 帳戶將資料匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="28c2e-175">After you complete this step, the Office 365 Import service will start importing data from your organization's Twitter account to Microsoft 365.</span></span>

<span data-ttu-id="28c2e-176">如需逐步指示，請參閱 [在 Microsoft 365 規範中心內設定 Twitter 連接器](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="28c2e-176">For step-by-step instructions, see [Set up a Twitter connector in the Microsoft 365 compliance center](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="28c2e-177">在此步驟完成過程中 (按逐步指示) 中，您將會提供下列資訊， (在完成步驟) 之後，您已複製到文字檔。</span><span class="sxs-lookup"><span data-stu-id="28c2e-177">During the completion of this step (by following the step-by-step instructions), you'll provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="28c2e-178">在步驟2中取得的 Azure 應用程式服務 URL (;例如， `https://twitterconnector.azurewebsites.net`) </span><span class="sxs-lookup"><span data-stu-id="28c2e-178">Azure app service URL (obtained in Step 2; for example, `https://twitterconnector.azurewebsites.net`)</span></span>

- <span data-ttu-id="28c2e-179">您在步驟2中建立的 APISecretKey () </span><span class="sxs-lookup"><span data-stu-id="28c2e-179">APISecretKey (that you created in Step 2)</span></span>
