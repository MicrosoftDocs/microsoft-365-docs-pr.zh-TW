---
title: 部署連接器以封存 Twitter 資料
f1.keywords:
- NOCSH
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
description: 管理員可以設定原生連接器，以匯入和封存 Twitter 資料至 Microsoft 365。 在將資料匯入 Microsoft 365 之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理組織的 Twitter 資料的控管。
ms.openlocfilehash: 80c3ca71204b6050a1944250c20df4ff13bbd71e
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635011"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="d379b-104">部署連接器以封存 Twitter 資料</span><span class="sxs-lookup"><span data-stu-id="d379b-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="d379b-105">本文包含的逐步程式可讓您部署使用 Office 365 Import 服務的連接器，將資料從組織的 Twitter 帳戶匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d379b-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="d379b-106">如需此程式的高層次概述，以及部署 Twitter 連接器所需的必要條件清單，請參閱[Set up a connector to Archive Twitter data ](archive-twitter-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="d379b-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="d379b-107">步驟1：在 Azure Active Directory 中建立應用程式</span><span class="sxs-lookup"><span data-stu-id="d379b-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="d379b-108">移至<https://portal.azure.com>並使用 Office 365 全域管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="d379b-108">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![登入 Azure](../media/TCimage01.png)

2. <span data-ttu-id="d379b-110">在左功能窗格中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![移至 Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="d379b-112">在左功能窗格中，按一下 [**應用程式註冊（預覽）** ]，然後按一下 [**新增註冊**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![建立新的應用程式註冊](../media/TCimage03.png)

4. <span data-ttu-id="d379b-114">註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="d379b-114">Register the application.</span></span> <span data-ttu-id="d379b-115">在 [重新**導向 URI （選用）**] 下，選取 [應用程式類型] 下拉式`https://portal.azure.com`清單中的 [ **WEB** ]，然後為 URI 輸入方塊。</span><span class="sxs-lookup"><span data-stu-id="d379b-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="d379b-116">重新https://portal.azure.com導向 URI 的類型</span><span class="sxs-lookup"><span data-stu-id="d379b-116">Type https://portal.azure.com for the redirect URI</span></span> ](../media/TCimage04.png)

5. <span data-ttu-id="d379b-117">複製**應用程式（用戶端）識別碼**及**目錄（租**使用者）識別碼，並將其儲存至文字檔或其他安全的位置。</span><span class="sxs-lookup"><span data-stu-id="d379b-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="d379b-118">您可以在稍後的步驟中使用這些 IDs。</span><span class="sxs-lookup"><span data-stu-id="d379b-118">You use these IDs in later steps.</span></span>

    ![複製並儲存應用程式識別碼及目錄識別碼](../media/TCimage05.png)

6. <span data-ttu-id="d379b-120">移至**憑證 & 新應用程式的機密**及**用戶端機密**底下，按一下 [**新增用戶端密碼**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![建立新的用戶端密碼](../media/TCimage06.png)

7. <span data-ttu-id="d379b-122">建立新的機密。</span><span class="sxs-lookup"><span data-stu-id="d379b-122">Create a new secret.</span></span> <span data-ttu-id="d379b-123">在 [描述] 方塊中，輸入密碼，然後選擇到期期限。</span><span class="sxs-lookup"><span data-stu-id="d379b-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![輸入密碼，然後選擇 [到期期限]](../media/TCimage08.png)

8. <span data-ttu-id="d379b-125">複製密碼的值，並將其儲存至文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="d379b-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="d379b-126">這是您在後續步驟中使用的 AAD 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="d379b-126">This is the AAD application secret that you use in later steps.</span></span>

   ![複製並儲存該機密](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="d379b-128">步驟2：將連接器 web 服務從 GitHub 部署至您的 Azure 帳戶</span><span class="sxs-lookup"><span data-stu-id="d379b-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="d379b-129">移[至此 GitHub 網站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)，然後按一下 [**部署至 Azure**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![前往 Azure 首頁](../media/FBCimage11.png)

2. <span data-ttu-id="d379b-131">按一下 [**部署至 Azure**] 後，系統會以自訂範本頁面重新導向至 azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="d379b-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="d379b-132">填入**基本概念**和**設定**詳細資料，然後按一下 [**購買**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![按一下 [建立資源並輸入儲存體帳戶]](../media/FBCimage12.png)

    - <span data-ttu-id="d379b-134">**訂閱：** 選取您要部署 Twitter 連接器 web 服務的 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="d379b-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="d379b-135">**資源群組：** 選擇或建立新的資源群組。</span><span class="sxs-lookup"><span data-stu-id="d379b-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="d379b-136">資源群組是一個容器，可容納 Azure 解決方案的相關資源。</span><span class="sxs-lookup"><span data-stu-id="d379b-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="d379b-137">**位置：** 選擇位置。</span><span class="sxs-lookup"><span data-stu-id="d379b-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="d379b-138">**Web 應用程式名稱：** 提供連接器 web 應用程式的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="d379b-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="d379b-139">Th 名稱的長度必須介於3到18個字元之間。</span><span class="sxs-lookup"><span data-stu-id="d379b-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="d379b-140">這個名稱是用來建立 Azure app service URL;例如，如果您提供**twitterconnector**的 Web 應用程式名稱，Azure 應用程式服務 URL 會是**twitterconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="d379b-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="d379b-141">**tenantId：** 您在步驟1中建立 Azure Active Directory 中的 Facebook 連接器應用程式之後所複製之 Microsoft 365 組織的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="d379b-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="d379b-142">**APISecretKey：** 您可以輸入任何值做為密碼。</span><span class="sxs-lookup"><span data-stu-id="d379b-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="d379b-143">這是用來存取步驟5中的連接器 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d379b-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="d379b-144">部署成功之後，頁面看起來會類似下列螢幕擷取畫面：</span><span class="sxs-lookup"><span data-stu-id="d379b-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![按一下 [儲存]，然後按一下 [儲存帳戶]](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="d379b-146">步驟3：建立 Twitter 應用程式</span><span class="sxs-lookup"><span data-stu-id="d379b-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="d379b-147">移至https://developer.twitter.com，使用組織的開發人員帳戶登入，然後按一下 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![移至https://developer.twitter.com並登入](../media/TCimage25-5.png)
2. <span data-ttu-id="d379b-149">按一下 [**建立應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-149">Click **Create an app**.</span></span>
   
   ![移至 [應用程式] 頁面，以建立應用程式](../media/TCimage26.png)

3. <span data-ttu-id="d379b-151">在 [**應用程式詳細資料**] 下，新增應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d379b-151">Under **App details**, add information about the application.</span></span>

   ![輸入應用程式的相關資訊](../media/TCimage27.png)

4. <span data-ttu-id="d379b-153">在 [Twitter 開發人員儀表板] 上，選取您剛建立的應用程式，並複製所顯示的應用程式識別碼，並將其儲存至文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="d379b-153">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="d379b-154">然後按一下 [**詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-154">Then click **Details**.</span></span>
   
   ![複製並儲存應用程式識別碼](../media/TCimage28.png)

5. <span data-ttu-id="d379b-156">在 [**金鑰與標記**] 索引標籤上，在 [**使用者 api 金鑰**] 下，複製 API 金鑰並將其儲存至文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="d379b-156">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="d379b-157">然後按一下 [**建立**] 以產生存取權杖和存取權杖密碼，並將這些機密複製到文字檔或其他存放位置。</span><span class="sxs-lookup"><span data-stu-id="d379b-157">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![複製並儲存至 API 金鑰](../media/TCimage29.png)

   <span data-ttu-id="d379b-159">然後按一下 [**建立**] 以產生存取權杖和存取權杖密碼，並將這些機密複製到文字檔或其他存放位置。</span><span class="sxs-lookup"><span data-stu-id="d379b-159">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="d379b-160">按一下 [**許可權**] 索引標籤，並設定許可權，如下列螢幕擷取畫面所示：</span><span class="sxs-lookup"><span data-stu-id="d379b-160">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![設定許可權](../media/TCimage30.png)

7. <span data-ttu-id="d379b-162">儲存許可權設定後，按一下 [**應用程式詳細資料**] 索引標籤，然後按一下 [**編輯 > 編輯詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-162">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![編輯應用程式詳細資料](../media/TCimage31.png)

8. <span data-ttu-id="d379b-164">請執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="d379b-164">Do the following tasks:</span></span>

   - <span data-ttu-id="d379b-165">選取核取方塊可允許連接器應用程式登入 Twitter。</span><span class="sxs-lookup"><span data-stu-id="d379b-165">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="d379b-166">使用下列格式新增 OAuth 重新導向 Uri： \*\* \<connectorserviceuri>/views/twitteroauth\**，其中*connectorserviceuri\*的值是您組織的 Azure 應用程式服務 URL;例如， https://twitterconnector.azurewebsites.net/Views/TwitterOAuth。</span><span class="sxs-lookup"><span data-stu-id="d379b-166">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![允許連接器應用程式登入 Twitter 並新增 OAuth 重新導向 Uri](../media/TCimage32.png)

<span data-ttu-id="d379b-168">Twitter 開發人員應用程式現在已可供使用。</span><span class="sxs-lookup"><span data-stu-id="d379b-168">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="d379b-169">步驟4：設定連接器 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="d379b-169">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="d379b-170">移至 HTTPs://\<AzureAppResourceName>。 azurewebsites.net （其中**AzureAppResourceName**是您在步驟4中命名的 Azure 應用程式資源名稱）。</span><span class="sxs-lookup"><span data-stu-id="d379b-170">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="d379b-171">例如，如果名稱是**twitterconnector**，請移至https://twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="d379b-171">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="d379b-172">應用程式的首頁看起來像下列螢幕擷取畫面：</span><span class="sxs-lookup"><span data-stu-id="d379b-172">The home page of the app looks like the following screenshot:</span></span>

   ![移至 Azure 應用程式資源頁面](../media/FBCimage41.png)

2. <span data-ttu-id="d379b-174">按一下 [**設定**] 以顯示登入頁面。</span><span class="sxs-lookup"><span data-stu-id="d379b-174">Click **Configure** to display a sign in page.</span></span>

   ![按一下 [設定] 以顯示登入頁面](../media/FBCimage42.png)

3. <span data-ttu-id="d379b-176">在 [租使用者識別碼] 方塊中，輸入或貼上您在步驟2中取得的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="d379b-176">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="d379b-177">在 [密碼] 方塊中，輸入或貼上 APISecretKey （您在步驟2中取得的），然後按一下 [**設定配置設定**] 以顯示 [設定詳細資料] 頁面。</span><span class="sxs-lookup"><span data-stu-id="d379b-177">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![使用租使用者識別碼和 API 金鑰登入](../media/TCimage35.png)

4. <span data-ttu-id="d379b-179">輸入下列設定設定</span><span class="sxs-lookup"><span data-stu-id="d379b-179">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="d379b-180">**Twitter Api 金鑰：** 您在步驟3中建立之 Twitter 應用程式的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="d379b-180">**Twitter Api Key:** The app ID for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="d379b-181">**Twitter Api 秘機碼：** 您在步驟3中建立之 Twitter 應用程式的 API 金鑰。</span><span class="sxs-lookup"><span data-stu-id="d379b-181">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="d379b-182">**Twitter 存取權杖：** 您在步驟3中建立的存取權杖。</span><span class="sxs-lookup"><span data-stu-id="d379b-182">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="d379b-183">**Twitter 存取權杖密碼：** 您在步驟3中建立的存取權杖機密。</span><span class="sxs-lookup"><span data-stu-id="d379b-183">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="d379b-184">**AAD 應用程式 ID:** 您在步驟1中建立之 Azure Active Directory 應用程式的應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="d379b-184">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="d379b-185">**AAD 應用程式密碼：** 您在步驟1中建立的 APISecretKey 密碼值。</span><span class="sxs-lookup"><span data-stu-id="d379b-185">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="d379b-186">按一下 [**儲存**] 以儲存連接器設定。</span><span class="sxs-lookup"><span data-stu-id="d379b-186">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="d379b-187">步驟5：在 Microsoft 365 規範中心設定 Twitter 連接器</span><span class="sxs-lookup"><span data-stu-id="d379b-187">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="d379b-188">移至[https://compliance.microsoft.com](https://compliance.microsoft.com) ，然後按一下左側導覽中的 [**資料連線器**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-188">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d379b-189">在 [ **Twitter**] 底下的 [**資料連線器（預覽）** ] 頁面上，按一下 [ **View**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-189">On the **Data connectors (preview)** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="d379b-190">在 [ **Twitter** ] 頁面上，按一下 [**新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-190">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="d379b-191">在 [**服務條款**] 頁面上，按一下 [**接受**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-191">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="d379b-192">在 [**新增連接器應用程式的認證**] 頁面上，輸入下列資訊，然後按一下 [**驗證連接**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-192">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![輸入連接器應用程式認證](../media/TCimage38.png)

    - <span data-ttu-id="d379b-194">在 [**名稱**] 方塊中，輸入連接器的名稱，例如**Twitter help handle**。</span><span class="sxs-lookup"><span data-stu-id="d379b-194">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="d379b-195">在 [**連接器 URL** ] 方塊中，輸入或貼上 Azure app service URL;例如`https://twitterconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="d379b-195">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="d379b-196">在 [**密碼**] 方塊中，輸入或貼上您在步驟2中建立的 APISecretKey 值。</span><span class="sxs-lookup"><span data-stu-id="d379b-196">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="d379b-197">在 [ **Azure 應用程式識別碼**] 方塊中，輸入或貼上您在步驟1中取得之 Azure Application App 應用程式識別碼（也稱為「*用戶端識別碼*」）的值。</span><span class="sxs-lookup"><span data-stu-id="d379b-197">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="d379b-198">成功驗證成功後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d379b-198">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="d379b-199">在 [**授權 Microsoft 365 匯入資料**] 頁面上，再次輸入或貼上 APISecretKey，然後按一下 **[登入 web app**]。</span><span class="sxs-lookup"><span data-stu-id="d379b-199">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="d379b-200">按一下 **[以 Twitter 登**入]。</span><span class="sxs-lookup"><span data-stu-id="d379b-200">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="d379b-201">在 [Twitter 登入] 頁面上，使用您組織的 Twitter 帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="d379b-201">On the Twitter sign in page, sign in using the credentials for your organization’s Twitter account.</span></span>

   ![登入 Twitter 帳戶](../media/TCimage42.png)

   <span data-ttu-id="d379b-203">登入後，Twitter 頁面會顯示下列訊息：「Twitter Connector Job 已成功設定」。</span><span class="sxs-lookup"><span data-stu-id="d379b-203">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="d379b-204">按一下 [**繼續**]，以完成 Twitter 連接器的設定。</span><span class="sxs-lookup"><span data-stu-id="d379b-204">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="d379b-205">在 [**設定篩選**] 頁面上，您可以將篩選器最初匯入特定時期的專案。</span><span class="sxs-lookup"><span data-stu-id="d379b-205">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="d379b-206">選取 [年齡]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d379b-206">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="d379b-207">在 [**選擇儲存位置**] 頁面上，輸入要匯入 Twitter 專案的 Microsoft 365 信箱的電子郵件地址，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d379b-207">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="d379b-208">在 [**提供管理員同意**] 中，按一下 [**提供同意**]，然後依照步驟進行。</span><span class="sxs-lookup"><span data-stu-id="d379b-208">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="d379b-209">您必須是全域系統管理員，才可對您組織中的資料提供 Office 365 匯入服務的同意。</span><span class="sxs-lookup"><span data-stu-id="d379b-209">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="d379b-210">按 **[下一步]** 以查看連接器設定，然後按一下 **[完成]** 以完成連接器設定。</span><span class="sxs-lookup"><span data-stu-id="d379b-210">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="d379b-211">在 [規範中心] 中，移至 [**資料連線器**] 頁面，然後按一下 [**連接器**] 索引標籤，以查看匯入程式的進度。</span><span class="sxs-lookup"><span data-stu-id="d379b-211">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
