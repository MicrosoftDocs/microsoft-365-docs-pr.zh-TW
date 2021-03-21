---
title: 設定連接器來封存 Facebook 資料
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
description: 瞭解如何設定 & 使用 Microsoft 365 規範中心內的連接器，將 & 封存資料從 Facebook 商務版頁面匯入至 Microsoft 365。
ms.openlocfilehash: 616466a3af83c1558184526aa463f68c10ef9e70
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921733"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a><span data-ttu-id="c9c74-103">設定連接器以封存 Facebook 資料 (預覽) </span><span class="sxs-lookup"><span data-stu-id="c9c74-103">Set up a connector to archive Facebook data (preview)</span></span>

<span data-ttu-id="c9c74-104">使用 Microsoft 365 規範中心內的連接器，將 Facebook 商務版頁面上的資料匯入並封存至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c9c74-104">Use a connector in the Microsoft 365 compliance center to import and archive data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="c9c74-105">在您設定及設定連接器之後，它會以排程的方式) 連線到 Facebook 商務頁面 (，將 Facebook 專案的內容轉換成電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的信箱。</span><span class="sxs-lookup"><span data-stu-id="c9c74-105">After you set up and configure the connector, it connects to the Facebook Business page (on a scheduled basis), converts the content of Facebook items to an email message format, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="c9c74-106">在匯入 Facebook 資料後，您可以將 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋、In-Place 封存、審核、通訊法規遵從性）和 Microsoft 365 保留原則套用到 Facebook 資料。</span><span class="sxs-lookup"><span data-stu-id="c9c74-106">After the Facebook data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to the Facebook data.</span></span> <span data-ttu-id="c9c74-107">例如，當信箱處於訴訟暫止狀態或指派給保留原則時，就會保留 Facebook 資料。</span><span class="sxs-lookup"><span data-stu-id="c9c74-107">For example, when a mailbox is placed on Litigation Hold or assigned to a retention policy, the Facebook data is preserved.</span></span> <span data-ttu-id="c9c74-108">您可以使用內容搜尋來搜尋協力廠商資料，或關聯在高級 eDiscovery 案例中，與系統管理員一起儲存 Facebook 資料的信箱。</span><span class="sxs-lookup"><span data-stu-id="c9c74-108">You can search third-party data using Content Search or associate the mailbox where the Facebook data is stored with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="c9c74-109">在 Microsoft 365 中使用連接器匯入和封存 Facebook 資料，可協助您的組織遵守政府和法規原則。</span><span class="sxs-lookup"><span data-stu-id="c9c74-109">Using a connector to import and archive Facebook data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a><span data-ttu-id="c9c74-110">設定 Facebook 商務版網頁連接器的必要條件</span><span class="sxs-lookup"><span data-stu-id="c9c74-110">Prerequisites for setting up a connector for Facebook Business pages</span></span>

<span data-ttu-id="c9c74-111">完成下列先決條件之前，您可以在 Microsoft 365 規範中心內安裝和設定連接器，以便從組織的 Facebook 商務頁面匯入及封存資料。</span><span class="sxs-lookup"><span data-stu-id="c9c74-111">Complete the following prerequisites before you can set up and configure a connector in the Microsoft 365 compliance center to import and archive data from your organization's Facebook Business pages.</span></span> 

- <span data-ttu-id="c9c74-112">您的組織的商務頁面需要 Facebook 帳戶 (您必須在設定連接器) 時登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="c9c74-112">You need a Facebook account for your organization's business pages (you need to sign in to this account when setting up the connector).</span></span> <span data-ttu-id="c9c74-113">目前，您只能從 Facebook 商務版頁面封存資料;您無法封存個別 Facebook 設定檔中的資料。</span><span class="sxs-lookup"><span data-stu-id="c9c74-113">Currently, you can only archive data from Facebook Business pages; you can't archive data from individual Facebook profiles.</span></span>

- <span data-ttu-id="c9c74-114">您的組織必須具有有效的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="c9c74-114">Your organization must have a valid Azure subscription.</span></span> <span data-ttu-id="c9c74-115">如果您沒有現有的 Azure 訂閱，您可以註冊下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="c9c74-115">If you don't have an existing Azure subscription, you can sign up for one of these options:</span></span>

    - [<span data-ttu-id="c9c74-116">註冊免費的一年 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="c9c74-116">Sign up for a free one year Azure subscription</span></span>](https://azure.microsoft.com/free)

    - [<span data-ttu-id="c9c74-117">註冊隨付即用 Azure 訂閱</span><span class="sxs-lookup"><span data-stu-id="c9c74-117">Sign up for a Pay-As-You-Go Azure subscription</span></span>](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > <span data-ttu-id="c9c74-118">Microsoft 365 訂閱隨附的 [免費 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md) 不支援 Security & 合規性中心內的連接器。</span><span class="sxs-lookup"><span data-stu-id="c9c74-118">The [free Azure Active Directory subscription](use-your-free-azure-ad-subscription-in-office-365.md) that's included with your Microsoft 365 subscription doesn't support the connectors in the Security & Compliance Center.</span></span>

- <span data-ttu-id="c9c74-119">Facebook 商務頁面的連接器可以一天內匯入200000項總計。</span><span class="sxs-lookup"><span data-stu-id="c9c74-119">The connector for Facebook Business pages can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="c9c74-120">如果一天內有超過200000的 Facebook 商務專案，將不會將這些專案匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c9c74-120">If there are more than 200,000 Facebook Business items in a day, none of those items will be imported to Microsoft 365.</span></span>

- <span data-ttu-id="c9c74-121">在步驟 5) 中，設定 Microsoft 365 規範中心 (中的自訂連接器的使用者，必須在 Exchange Online 中指派信箱匯入匯出角色。</span><span class="sxs-lookup"><span data-stu-id="c9c74-121">The user who sets up the custom connector in the Microsoft 365 compliance center (in Step 5) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="c9c74-122">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="c9c74-122">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="c9c74-123">您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。</span><span class="sxs-lookup"><span data-stu-id="c9c74-123">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="c9c74-124">或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。</span><span class="sxs-lookup"><span data-stu-id="c9c74-124">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="c9c74-125">如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [  [建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="c9c74-125">For more information, see the  [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="c9c74-126">步驟1：在 Azure Active Directory 中建立應用程式</span><span class="sxs-lookup"><span data-stu-id="c9c74-126">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="c9c74-127">第一步是在 Azure Active Directory (AAD) 中註冊新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c9c74-127">The first step is to register a new app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="c9c74-128">此應用程式對應到您在步驟4中所執行的 web 應用程式資源，以及 Facebook 連接器的步驟5。</span><span class="sxs-lookup"><span data-stu-id="c9c74-128">This app corresponds to the web app resource that you implement in Step 4 and Step 5 for the Facebook connector.</span></span> 

<span data-ttu-id="c9c74-129">如需逐步指示，請參閱 [在 Azure Active Directory 中建立應用程式](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="c9c74-129">For step-by-step instructions, see [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).</span></span>

<span data-ttu-id="c9c74-130">在完成此步驟 (，請使用上述逐步指示) ，將下列資訊儲存至文字檔。</span><span class="sxs-lookup"><span data-stu-id="c9c74-130">During the completion of this step (by using the previous step-by-step instructions), you'll save the following information to a text file.</span></span> <span data-ttu-id="c9c74-131">這些值會在部署程式的後續步驟中使用。</span><span class="sxs-lookup"><span data-stu-id="c9c74-131">These values are used in later steps in the deployment process.</span></span>

- <span data-ttu-id="c9c74-132">AAD 應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="c9c74-132">AAD application ID</span></span>

- <span data-ttu-id="c9c74-133">AAD 應用程式機密</span><span class="sxs-lookup"><span data-stu-id="c9c74-133">AAD application secret</span></span>

- <span data-ttu-id="c9c74-134">租使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="c9c74-134">Tenant Id</span></span>

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="c9c74-135">步驟2：將連接器 web 服務從 GitHub 部署至您的 Azure 帳戶</span><span class="sxs-lookup"><span data-stu-id="c9c74-135">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

<span data-ttu-id="c9c74-136">下一步是部署 Facebook Business pages connector 應用程式的原始程式碼，該應用程式會使用 Facebook API 來連線到 Facebook 帳戶並提取資料，以便您可以將資料匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c9c74-136">The next step is to deploy the source code for the Facebook Business pages connector app that will use the Facebook API to connect to your Facebook account and extract data so you can import it to Microsoft 365.</span></span> <span data-ttu-id="c9c74-137">您為組織部署的 Facebook 連接器會將 Facebook 商務頁面上的專案上傳至此步驟中建立的 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="c9c74-137">The Facebook connector that you deploy for your organization will upload the items from your Facebook Business pages to the Azure Storage location that is created in this step.</span></span> <span data-ttu-id="c9c74-138">在 [步驟 5) ] 中建立 Microsoft 365 規範中心內的 Facebook 商務頁面連接器之後 (，匯入服務會將 Facebook 商務頁面資料從 Azure 存放位置複製到您的 Microsoft 365 組織中的信箱。</span><span class="sxs-lookup"><span data-stu-id="c9c74-138">After you create a Facebook business pages connector in the Microsoft 365 compliance center (in Step 5), the Import service will copy the Facebook business pages data from the Azure Storage location to a mailbox in your Microsoft 365 organization.</span></span> <span data-ttu-id="c9c74-139">如先前在 [必要條件](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) 區段中所述，您必須具備有效的 azure 訂閱，才可建立 Azure 儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="c9c74-139">As previous explained in the [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) section, you must have a valid Azure subscription to create an Azure Storage account.</span></span>

<span data-ttu-id="c9c74-140">如需逐步指示，請參閱 [將連接器 web 服務從 GitHub 部署至您的 Azure 帳戶](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。</span><span class="sxs-lookup"><span data-stu-id="c9c74-140">For step-by-step instructions, see [Deploy the connector web service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).</span></span>

<span data-ttu-id="c9c74-141">在完成此步驟的逐步指示中，您將會提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c9c74-141">In the step-by-step instructions to complete this step, you'll provide the following information:</span></span>

- <span data-ttu-id="c9c74-142">APISecretKey：完成此步驟時，您會建立此密碼。</span><span class="sxs-lookup"><span data-stu-id="c9c74-142">APISecretKey: You create this secret during the completion of this step.</span></span> <span data-ttu-id="c9c74-143">它會在步驟5中使用。</span><span class="sxs-lookup"><span data-stu-id="c9c74-143">It's used in Step 5.</span></span>

- <span data-ttu-id="c9c74-144">TenantId：在步驟1中建立 Azure Active Directory 中的 Facebook 連接器應用程式之後，所複製之 Microsoft 365 組織的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="c9c74-144">TenantId: The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

<span data-ttu-id="c9c74-145">完成此步驟後，請務必複製 Azure 應用程式服務 URL (例如， https://fbconnector.azurewebsites.net) 。</span><span class="sxs-lookup"><span data-stu-id="c9c74-145">After completing this step, be sure to copy the Azure app service URL (for example, https://fbconnector.azurewebsites.net).</span></span> <span data-ttu-id="c9c74-146">您必須使用此 URL，才能完成步驟3、步驟4及步驟 5) 。</span><span class="sxs-lookup"><span data-stu-id="c9c74-146">You need to use this URL to complete Step 3, Step 4, and Step 5).</span></span>

## <a name="step-3-register-the-web-app-on-facebook"></a><span data-ttu-id="c9c74-147">步驟3：在 Facebook 上註冊 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="c9c74-147">Step 3: Register the web app on Facebook</span></span>

<span data-ttu-id="c9c74-148">下一步是在 Facebook 上建立及設定新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c9c74-148">The next step is to create and configure a new app on Facebook.</span></span> <span data-ttu-id="c9c74-149">您在步驟5中建立的 Facebook 商務頁面連接器會使用 Facebook web app 與 Facebook API 互動，以從組織的 Facebook 商務版頁面中取得資料。</span><span class="sxs-lookup"><span data-stu-id="c9c74-149">The Facebook business pages connector that you create in Step 5 uses the Facebook web app to interact with the Facebook API to obtain data from your organization's Facebook Business pages.</span></span>

<span data-ttu-id="c9c74-150">如需逐步指示，請參閱 [註冊 Facebook 應用程式](deploy-facebook-connector.md#step-3-register-the-facebook-app)。</span><span class="sxs-lookup"><span data-stu-id="c9c74-150">For step-by-step instructions, see [Register the Facebook app](deploy-facebook-connector.md#step-3-register-the-facebook-app).</span></span>

<span data-ttu-id="c9c74-151">在完成此步驟時 (請遵循) 的逐步指示，將下列資訊儲存至文字檔。</span><span class="sxs-lookup"><span data-stu-id="c9c74-151">During the completion of this step (by following the step-by-step instructions), you save the following information to a text file.</span></span> <span data-ttu-id="c9c74-152">這些值是用來在步驟4中設定 Facebook 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="c9c74-152">These values are used to configure the Facebook connector app in Step 4.</span></span>

- <span data-ttu-id="c9c74-153">Facebook 應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="c9c74-153">Facebook application ID</span></span>

- <span data-ttu-id="c9c74-154">Facebook 應用程式機密</span><span class="sxs-lookup"><span data-stu-id="c9c74-154">Facebook application secret</span></span>

- <span data-ttu-id="c9c74-155">Facebook webhooks verify token</span><span class="sxs-lookup"><span data-stu-id="c9c74-155">Facebook webhooks verify token</span></span>

## <a name="step-4-configure-the-facebook-connector-app"></a><span data-ttu-id="c9c74-156">步驟4：設定 Facebook 連接器應用程式</span><span class="sxs-lookup"><span data-stu-id="c9c74-156">Step 4: Configure the Facebook connector app</span></span>

<span data-ttu-id="c9c74-157">下一步是將設定設定新增至您在步驟1中建立 Azure web app 資源時所上傳的 Facebook 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="c9c74-157">The next step is to add configuration settings to the Facebook connector app that you uploaded when you created the Azure web app resource in Step 1.</span></span> <span data-ttu-id="c9c74-158">若要執行此動作，請移至連接器應用程式的首頁並加以設定。</span><span class="sxs-lookup"><span data-stu-id="c9c74-158">You do this by going to the home page of your connector app and configuring it.</span></span>

<span data-ttu-id="c9c74-159">如需逐步指示，請參閱 Configure the [Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)。</span><span class="sxs-lookup"><span data-stu-id="c9c74-159">For step-by-step instructions, see [Configure the Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).</span></span>

<span data-ttu-id="c9c74-160">在此步驟完成過程中 (按逐步指示) ，提供下列資訊， (您在完成上述步驟之後，您已複製到文字檔) ：</span><span class="sxs-lookup"><span data-stu-id="c9c74-160">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the previous steps):</span></span>

- <span data-ttu-id="c9c74-161">在步驟3中取得的 Facebook 應用程式識別碼 () </span><span class="sxs-lookup"><span data-stu-id="c9c74-161">Facebook application ID (obtained in Step 3)</span></span>

- <span data-ttu-id="c9c74-162">在步驟3中取得的 Facebook 應用程式機密 () </span><span class="sxs-lookup"><span data-stu-id="c9c74-162">Facebook application secret (obtained in Step 3)</span></span>

- <span data-ttu-id="c9c74-163">Facebook webhooks 驗證在步驟3中取得的 token () </span><span class="sxs-lookup"><span data-stu-id="c9c74-163">Facebook webhooks verify token (obtained in Step 3)</span></span>

- <span data-ttu-id="c9c74-164">在步驟1中取得的 AAD 應用程式識別碼 (Azure Active Directory 應用程式識別碼) </span><span class="sxs-lookup"><span data-stu-id="c9c74-164">Azure Active Directory application ID (the AAD application ID obtained in Step 1)</span></span>

- <span data-ttu-id="c9c74-165">Azure Active Directory 應用程式機密 (步驟1中取得的 AAD 應用程式密碼) </span><span class="sxs-lookup"><span data-stu-id="c9c74-165">Azure Active Directory application secret (the AAD application secret obtained in Step 1)</span></span>

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="c9c74-166">步驟5：設定 Microsoft 365 規範中心內的 Facebook 商務頁面連接器</span><span class="sxs-lookup"><span data-stu-id="c9c74-166">Step 5: Set up a Facebook Business pages connector in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="c9c74-167">最後一個步驟是在 Microsoft 365 規範中心內設定連接器，將您的 Facebook 商務版頁面中的資料匯入至 Microsoft 365 中的指定信箱。</span><span class="sxs-lookup"><span data-stu-id="c9c74-167">The final step is to set up the connector in the Microsoft 365 compliance center that will import data from your Facebook Business pages to a specified mailbox in Microsoft 365.</span></span> <span data-ttu-id="c9c74-168">完成此步驟之後，Microsoft 365 匯入服務將開始從您的 Facebook 商務版頁面將資料匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c9c74-168">After you complete this step, the Microsoft 365 Import service will start importing data from your Facebook Business pages to Microsoft 365.</span></span>

<span data-ttu-id="c9c74-169">如需逐步指示，請參閱 [Microsoft 365 規範中心的「步驟5：設定 Facebook 連接器](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)」。</span><span class="sxs-lookup"><span data-stu-id="c9c74-169">For step-by-step instructions, see [Step 5: Set up a Facebook connector in the Microsoft 365 compliance center](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center).</span></span> 

<span data-ttu-id="c9c74-170">在此步驟完成過程中 (按逐步指示) 中，您會提供下列資訊， (在完成步驟) 之後，您已複製到文字檔。</span><span class="sxs-lookup"><span data-stu-id="c9c74-170">During the completion of this step (by following the step-by-step instructions), you provide the following information (that you've copied to a text file after completing the steps).</span></span>

- <span data-ttu-id="c9c74-171">在步驟1中取得的 AAD 應用程式識別碼 () </span><span class="sxs-lookup"><span data-stu-id="c9c74-171">AAD application ID (obtained in Step 1)</span></span>

- <span data-ttu-id="c9c74-172">在步驟1中取得的 Azure 應用程式服務 URL (;例如， https://fbconnector.azurewebsites.net)</span><span class="sxs-lookup"><span data-stu-id="c9c74-172">Azure app service URL (obtained in Step 1; for example, https://fbconnector.azurewebsites.net)</span></span>

- <span data-ttu-id="c9c74-173">您在步驟2中建立的 APISecretKey () </span><span class="sxs-lookup"><span data-stu-id="c9c74-173">APISecretKey (that you created in Step 2)</span></span>