---
title: 部署封存 Twitter 資料的連接器
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 系統管理員可以設定原生的連接器，以匯入並封存至 Microsoft 365 Twitter 資料。 此資料會匯入至 Microsoft 365 之後，您可以使用合規性功能，例如合法持有、 內容搜尋和保留原則來管理您的組織 Twitter 資料的控管。
ms.openlocfilehash: 9bf0be8684eb18fbc022f4eefa798c5c9265b3d7
ms.sourcegitcommit: e872676ec98036a50d3a0cb5071109ea5f5a7ae5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2020
ms.locfileid: "41515694"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="60d4c-104">部署封存 Twitter 資料的連接器</span><span class="sxs-lookup"><span data-stu-id="60d4c-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="60d4c-105">本文包含的逐步程序來部署您的組織 Twitter 帳戶的資料匯入至 Microsoft 365 使用 Office 365 匯入服務的連接器。</span><span class="sxs-lookup"><span data-stu-id="60d4c-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="60d4c-106">此程序的高階概觀與部署 Twitter 連接器所需的必要條件清單，請參閱[設定連接器，以封存 Twitter 資料](archive-twitter-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="60d4c-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="60d4c-107">步驟 1: Azure Active Directory 中建立的應用程式</span><span class="sxs-lookup"><span data-stu-id="60d4c-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="60d4c-108">移至 [<https://portal.azure.com>並使用 Office 365 全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="60d4c-108">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![登入 Azure](media/TCimage01.png)

2. <span data-ttu-id="60d4c-110">在左側的導覽窗格中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="60d4c-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![移至 Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="60d4c-112">在左側的導覽窗格中，按一下 [**應用程式註冊 （預覽）** ，然後按一下 [**新增註冊**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![建立新的應用程式註冊](media/TCimage03.png)

4. <span data-ttu-id="60d4c-114">註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="60d4c-114">Register the application.</span></span> <span data-ttu-id="60d4c-115">**（選用） 的 [重新導向 URI**，選取**Web**應用程式類型] 下拉式清單中，然後輸入`https://portal.azure.com`URI] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="60d4c-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="60d4c-116">型別https://portal.azure.com的重新導向 URI</span><span class="sxs-lookup"><span data-stu-id="60d4c-116">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="60d4c-117">複製 **（用戶端） 的應用程式識別碼**] 及 [**目錄 （承租人） 識別碼**，並將它們儲存到文字檔或其他安全的位置。</span><span class="sxs-lookup"><span data-stu-id="60d4c-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="60d4c-118">您在稍後步驟使用這些識別碼。</span><span class="sxs-lookup"><span data-stu-id="60d4c-118">You use these IDs in later steps.</span></span>

    ![複製並儲存應用程式識別碼] 及 [目錄識別碼](media/TCimage05.png)

6. <span data-ttu-id="60d4c-120">移至**新的應用程式的憑證 & 機密資料**，並在 [**用戶端密碼**] 下按一下 [**新的用戶端密碼**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![建立新的用戶端密碼](media/TCimage06.png)

7. <span data-ttu-id="60d4c-122">建立新的密碼。</span><span class="sxs-lookup"><span data-stu-id="60d4c-122">Create a new secret.</span></span> <span data-ttu-id="60d4c-123">在 [描述] 方塊中，輸入密碼，然後選擇的到期時間。</span><span class="sxs-lookup"><span data-stu-id="60d4c-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![輸入密碼，然後選擇 [到期時間](media/TCimage08.png)

8. <span data-ttu-id="60d4c-125">複製密碼的值，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="60d4c-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="60d4c-126">這是您在稍後步驟使用的 AAD 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="60d4c-126">This is the AAD application secret that you use in later steps.</span></span>

   ![複製並儲存密碼](media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="60d4c-128">步驟 2： 部署至您的 Azure 帳戶從 GitHub 連接器 」 的 web 服務</span><span class="sxs-lookup"><span data-stu-id="60d4c-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="60d4c-129">移至[這個 GitHub 網站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)，然後按一下 [**部署至 Azure**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![移至 Azure 的 [首頁] 頁面](media/FBCimage11.png)

2. <span data-ttu-id="60d4c-131">按一下 [**部署至 Azure**之後，您將會重新導向至自訂的範本] 頁面上使用 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="60d4c-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="60d4c-132">填入的**基本概念**和**設定**詳細資料，然後按一下 [**購買**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![按一下 [建立資源] 和 [類型儲存體帳戶](media/FBCimage12.png)

    - <span data-ttu-id="60d4c-134">**訂閱：** 選取您想要部署 Twitter 連接器 web 服務，以您 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="60d4c-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="60d4c-135">**資源群組：** 選擇或建立新的資源群組。</span><span class="sxs-lookup"><span data-stu-id="60d4c-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="60d4c-136">資源群組是保留 Azure 解決方案的相關的資源的容器。</span><span class="sxs-lookup"><span data-stu-id="60d4c-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="60d4c-137">**位置：** 選擇的位置。</span><span class="sxs-lookup"><span data-stu-id="60d4c-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="60d4c-138">**Web 應用程式名稱：** Web 應用程式提供連接器的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="60d4c-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="60d4c-139">對名稱必須是長度為 3 並 18 個字元之間。</span><span class="sxs-lookup"><span data-stu-id="60d4c-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="60d4c-140">此名稱用來建立 Azure 應用程式服務的 URL;例如，如果您提供**twitterconnector**的 Web 應用程式名稱然後 Azure 應用程式服務的 URL 將會是**twitterconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="60d4c-141">**tenantId:** 您在步驟 1 中的 Azure Active Directory 中建立 Facebook 連接器應用程式之後複製您 Microsoft 365 組織租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="60d4c-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="60d4c-142">**APISecretKey:** 您可以為密碼輸入任何值。</span><span class="sxs-lookup"><span data-stu-id="60d4c-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="60d4c-143">這用來存取在步驟 5 中的連接器 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="60d4c-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="60d4c-144">部署成功後，看起來類似下列的螢幕擷取畫面] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="60d4c-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![按一下儲存，然後按一下 [儲存體帳戶](media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="60d4c-146">步驟 3： 建立 Twitter 應用程式</span><span class="sxs-lookup"><span data-stu-id="60d4c-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="60d4c-147">移至 [ https://developer.twitter.com，登入您的組織，開發人員帳戶使用的認證，然後按一下 [**應用程式**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![移至 [ https://developer.twitter.com ，然後登入](media/TCimage25-5.png)
2. <span data-ttu-id="60d4c-149">按一下 [**建立應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="60d4c-149">Click **Create an app**.</span></span>
   
   ![移至應用程式] 頁面上，若要建立的應用程式](media/TCimage26.png)

3. <span data-ttu-id="60d4c-151">在 [**應用程式詳細資料**，新增應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="60d4c-151">Under **App details**, add information about the application.</span></span>

   ![輸入應用程式的相關資訊](media/TCimage27.png)

4. <span data-ttu-id="60d4c-153">Twitter 開發人員儀表板上選取您剛建立的應用程式複製應用程式 ID 會顯示，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="60d4c-153">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="60d4c-154">然後按一下 [**詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-154">Then click **Details**.</span></span>
   
   ![複製並儲存應用程式識別碼](media/TCimage28.png)

5. <span data-ttu-id="60d4c-156">**索引鍵和權杖**索引標籤上，在**消費者 API 機碼**下複製 API 祕密金鑰並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="60d4c-156">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="60d4c-157">然後按一下 [**建立**]，以產生的存取權杖及存取權杖的密碼，並複製這些文字檔案或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="60d4c-157">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![複製並儲存至 API 祕密金鑰](media/TCimage29.png)

   <span data-ttu-id="60d4c-159">然後按一下 [**建立**]，以產生的存取權杖及存取權杖的密碼，並複製這些文字檔案或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="60d4c-159">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="60d4c-160">按一下 [**權限**] 索引標籤，並設定權限，如下列螢幕擷取畫面所示：</span><span class="sxs-lookup"><span data-stu-id="60d4c-160">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![設定權限](media/TCimage30.png)

7. <span data-ttu-id="60d4c-162">儲存的權限設定之後，按一下 [**應用程式詳細資料**] 索引標籤，然後按一下 [**編輯 > 編輯詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-162">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![編輯應用程式詳細資料](media/TCimage31.png)

8. <span data-ttu-id="60d4c-164">執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="60d4c-164">Do the following tasks:</span></span>

   - <span data-ttu-id="60d4c-165">選取核取方塊可允許登入 Twitter 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="60d4c-165">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="60d4c-166">新增的 OAuth 重新導向 Uri 使用下列格式： \*\* \<connectorserviceuri>/檢視/TwitterOAuth\**、 其中*connectorserviceuri\*的值是為您的組織; Azure 應用程式服務 URL例如， https://twitterconnector.azurewebsites.net/Views/TwitterOAuth。</span><span class="sxs-lookup"><span data-stu-id="60d4c-166">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![允許連接器 Twitter 登入，並將新增 OAuth 重新導向 Uri 的應用程式](media/TCimage32.png)

<span data-ttu-id="60d4c-168">在 Twitter 開發人員 app 現已可使用。</span><span class="sxs-lookup"><span data-stu-id="60d4c-168">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="60d4c-169">步驟 4： 設定連接器的 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="60d4c-169">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="60d4c-170">移至 https://\<AzureAppResourceName>.azurewebsites.net （其中**AzureAppResourceName**是您在步驟 4 中名為您 Azure 應用程式資源的名稱）。</span><span class="sxs-lookup"><span data-stu-id="60d4c-170">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="60d4c-171">例如，如果名稱為**twitterconnector**，請移至https://twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="60d4c-171">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="60d4c-172">應用程式的 [首頁] 頁面上看起來像下列螢幕擷取畫面中：</span><span class="sxs-lookup"><span data-stu-id="60d4c-172">The home page of the app looks like the following screenshot:</span></span>

   ![移至 Azure 應用程式資源頁面](media/FBCimage41.png)

2. <span data-ttu-id="60d4c-174">按一下 [**設定**] 頁面中，會顯示號。</span><span class="sxs-lookup"><span data-stu-id="60d4c-174">Click **Configure** to display a sign in page.</span></span>

   ![按一下 [設定] 頁面中，會顯示號](media/FBCimage42.png)

3. <span data-ttu-id="60d4c-176">在租用戶識別碼] 方塊中，輸入或貼上您的租用戶識別碼 （您在步驟 2 中所取得）。</span><span class="sxs-lookup"><span data-stu-id="60d4c-176">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="60d4c-177">在 [密碼] 方塊中，輸入或貼上 APISecretKey （，您在步驟 2 中所取得），，然後按一下要顯示 [組態詳細資料] 頁面上**設定的組態設定**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-177">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![使用租用戶識別碼和 API 祕密金鑰登入](media/TCimage35.png)

4. <span data-ttu-id="60d4c-179">輸入下列組態設定</span><span class="sxs-lookup"><span data-stu-id="60d4c-179">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="60d4c-180">**Twitter Api 機碼：** 您在步驟 3 中建立的 Twitter 應用程式的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="60d4c-180">**Twitter Api Key:** The app ID for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="60d4c-181">**Twitter Api 密碼機碼：** 您在步驟 3 中建立的 Twitter 應用程式 API 祕密金鑰。</span><span class="sxs-lookup"><span data-stu-id="60d4c-181">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="60d4c-182">**Twitter 存取權杖：** 您在步驟 3 中建立存取權杖。</span><span class="sxs-lookup"><span data-stu-id="60d4c-182">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="60d4c-183">**Twitter 存取 Token 密碼：** 您在步驟 3 中建立的存取權杖的密碼。</span><span class="sxs-lookup"><span data-stu-id="60d4c-183">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="60d4c-184">**AAD 應用程式識別碼：** 您在步驟 1 建立的 Azure Active Directory 應用程式的應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="60d4c-184">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="60d4c-185">**AAD 應用程式密碼：** 您在步驟 1 建立的 APISecretKey 密碼值。</span><span class="sxs-lookup"><span data-stu-id="60d4c-185">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="60d4c-186">按一下 [**儲存**] 以儲存連接器設定。</span><span class="sxs-lookup"><span data-stu-id="60d4c-186">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="60d4c-187">步驟 5： 設定 Microsoft 365 合規性中心中的 Twitter 連接器</span><span class="sxs-lookup"><span data-stu-id="60d4c-187">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="60d4c-188">移至 [ [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然後按一下 [從左側的 [**資料連接器**</span><span class="sxs-lookup"><span data-stu-id="60d4c-188">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="60d4c-189">在 [ **Twitter\*\*\*\*資料連接器 （預覽）** ] 頁面上，按一下 [**檢視**]。</span><span class="sxs-lookup"><span data-stu-id="60d4c-189">On the **Data connectors (preview)** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="60d4c-190">在**Twitter** ] 頁面上，按一下 [**新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="60d4c-190">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="60d4c-191">在**服務中的條款**] 頁面上，按一下 [**接受**]。</span><span class="sxs-lookup"><span data-stu-id="60d4c-191">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="60d4c-192">在**您的連接器應用程式新增認證**] 頁面中，輸入下列資訊，然後按一下 [**驗證連線**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-192">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![輸入連接器應用程式的認證](media/TCimage38.png)

    - <span data-ttu-id="60d4c-194">在 [**名稱**] 方塊中，輸入連接器，例如**Twitter 說明控點**的名稱。</span><span class="sxs-lookup"><span data-stu-id="60d4c-194">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="60d4c-195">在**連接器 URL** ] 方塊中，輸入或貼上的 Azure 應用程式服務 URL;例如`https://twitterconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="60d4c-195">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="60d4c-196">在 [**密碼**] 方塊中，輸入或貼上您在步驟 2 中建立 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="60d4c-196">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="60d4c-197">在 [ **Azure 應用程式識別碼**] 方塊中，輸入或貼上的 Azure 應用程式應用程式 Id （也稱為*用戶端識別碼*） 值，您在步驟 1 中所取得。</span><span class="sxs-lookup"><span data-stu-id="60d4c-197">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="60d4c-198">連線成功驗證之後，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="60d4c-198">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="60d4c-199">在 [**授權 Microsoft 365，以匯入資料**] 頁面上，輸入或貼上 APISecretKey 再次並再按一下 [**登入 web 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-199">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="60d4c-200">按一下 [**登入與 Twitter**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-200">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="60d4c-201">在 Twitter 登入] 頁面上，登入您的組織 Twitter 帳戶使用的認證。</span><span class="sxs-lookup"><span data-stu-id="60d4c-201">On the Twitter sign in page, sign in using the credentials for your organization’s Twitter account.</span></span>

   ![Twitter 帳戶登入](media/TCimage42.png)

   <span data-ttu-id="60d4c-203">登入後，[Twitter] 頁面上會顯示下列訊息、 「 Twitter 連接器工作成功設定。 」</span><span class="sxs-lookup"><span data-stu-id="60d4c-203">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="60d4c-204">按一下 [**繼續**] 以完成 Twitter 連接器設定。</span><span class="sxs-lookup"><span data-stu-id="60d4c-204">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="60d4c-205">在 [**設定篩選器**] 頁面上，您可以套用篩選器，一開始匯入特定天數的項目。</span><span class="sxs-lookup"><span data-stu-id="60d4c-205">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="60d4c-206">選取 [保留天數，，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="60d4c-206">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="60d4c-207">在 [**選擇儲存位置**] 頁面上，輸入 Twitter 項目會被匯入，並再按 [**下一步**，Microsoft 365 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="60d4c-207">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="60d4c-208">在**提供系統管理員同意**，按一下**提供同意**，然後遵循的步驟。</span><span class="sxs-lookup"><span data-stu-id="60d4c-208">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="60d4c-209">您必須是全域系統管理員提供 Office 365 匯入服務來存取您的組織中資料的同意。</span><span class="sxs-lookup"><span data-stu-id="60d4c-209">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="60d4c-210">按 [**下一步**檢閱連接器設定，然後按一下 [**完成**] 以完成連接器設定。</span><span class="sxs-lookup"><span data-stu-id="60d4c-210">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="60d4c-211">在合規性中心] 中，移至**資料連接器**] 頁面上，然後按一下 [**連接器**] 索引標籤，若要查看匯入程序的進度。</span><span class="sxs-lookup"><span data-stu-id="60d4c-211">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
