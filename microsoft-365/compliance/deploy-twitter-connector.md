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
description: 系統管理員可以設定原生的連接器，以匯入並封存 Twitter 資料到 Office 365。 此資料會匯入至 Office 365 之後，您可以使用合規性功能，例如合法持有、 內容搜尋和保留原則來管理您的組織 Twitter 資料的控管。
ms.openlocfilehash: 87faad6546d70b1e3893e2f5737af189ebb5f77b
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806146"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="6a003-104">部署封存 Twitter 資料的連接器</span><span class="sxs-lookup"><span data-stu-id="6a003-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="6a003-105">本文包含的逐步程序來部署您的組織 Twitter 帳戶的資料匯入至 Office 365 會使用 Office 365 匯入服務的連接器。</span><span class="sxs-lookup"><span data-stu-id="6a003-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="6a003-106">此程序的高階概觀與部署 Twitter 連接器所需的必要條件清單，請參閱[使用封存 Twitter 資料 Office 365 （預覽） 中的範例連接器](archive-twitter-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="6a003-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a sample connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="6a003-107">步驟 1： 下載套件</span><span class="sxs-lookup"><span data-stu-id="6a003-107">Step 1: Download the package</span></span>

<span data-ttu-id="6a003-108">從 [版本] 區段中，GitHub 儲存機制中下載預先建立的套件[https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)。</span><span class="sxs-lookup"><span data-stu-id="6a003-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="6a003-109">在 [最新版本中，下載 zip 檔名為**SampleConnector.zip**。</span><span class="sxs-lookup"><span data-stu-id="6a003-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="6a003-110">您將此 zip 檔案上傳到步驟 4 中的 Azure。</span><span class="sxs-lookup"><span data-stu-id="6a003-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="6a003-111">步驟 2： 在 Azure Active Directory 中建立的應用程式</span><span class="sxs-lookup"><span data-stu-id="6a003-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="6a003-112">移至 [<https://portal.azure.com>並使用 Office 365 全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="6a003-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![登入 Azure](media/TCimage01.png)

2. <span data-ttu-id="6a003-114">在左側的導覽窗格中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="6a003-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![移至 Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="6a003-116">在左側的導覽窗格中，按一下 [**應用程式註冊 （預覽）** ，然後按一下 [**新增註冊**。</span><span class="sxs-lookup"><span data-stu-id="6a003-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![建立新的應用程式註冊](media/TCimage03.png)

4. <span data-ttu-id="6a003-118">註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="6a003-118">Register the application.</span></span> <span data-ttu-id="6a003-119">**（選用） 的 [重新導向 URI**，選取**Web**應用程式類型] 下拉式清單中，然後輸入`https://portal.azure.com`URI] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="6a003-119">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="6a003-120">型別https://portal.azure.com的重新導向 URI</span><span class="sxs-lookup"><span data-stu-id="6a003-120">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="6a003-121">複製 **（用戶端） 的應用程式識別碼**] 及 [**目錄 （承租人） 識別碼**，並將它們儲存到文字檔或其他安全的位置。</span><span class="sxs-lookup"><span data-stu-id="6a003-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="6a003-122">您在稍後步驟使用這些識別碼。</span><span class="sxs-lookup"><span data-stu-id="6a003-122">You use these IDs in later steps.</span></span>

    ![複製並儲存應用程式識別碼] 及 [目錄識別碼](media/TCimage05.png)

6. <span data-ttu-id="6a003-124">移至**新的應用程式的憑證 & 機密資料**，並在 [**用戶端密碼**] 下按一下 [**新的用戶端密碼**。</span><span class="sxs-lookup"><span data-stu-id="6a003-124">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![建立新的用戶端密碼](media/TCimage06.png)

7. <span data-ttu-id="6a003-126">建立新的密碼。</span><span class="sxs-lookup"><span data-stu-id="6a003-126">Create a new secret.</span></span> <span data-ttu-id="6a003-127">在 [描述] 方塊中，輸入密碼，然後選擇的到期時間。</span><span class="sxs-lookup"><span data-stu-id="6a003-127">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![輸入密碼，然後選擇 [到期時間](media/TCimage08.png)

8. <span data-ttu-id="6a003-129">複製密碼的值，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6a003-129">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="6a003-130">這是您在稍後步驟使用的 AAD 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="6a003-130">This is the AAD application secret that you use in later steps.</span></span>

   ![複製並儲存密碼](media/TCimage09.png)

9. <span data-ttu-id="6a003-132">移至**資訊清單**，然後複製 identifierUris （這也稱為 AAD 應用程式的 Uri） 以反白顯示下列螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="6a003-132">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="6a003-133">複製到文字檔或其他儲存位置的 AAD 應用程式的 Uri。</span><span class="sxs-lookup"><span data-stu-id="6a003-133">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="6a003-134">您在步驟 6 中使用。</span><span class="sxs-lookup"><span data-stu-id="6a003-134">You use it in Step 6.</span></span>

    ![複製並儲存的 AAD 應用程式的 Uri](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="6a003-136">步驟 3： 建立 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="6a003-136">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="6a003-137">移至 Azure 的首頁上，為您的組織。</span><span class="sxs-lookup"><span data-stu-id="6a003-137">Go to the Azure home page for your organization.</span></span>

    ![Gi Azure 首頁](media/TCimage11.png)

2. <span data-ttu-id="6a003-139">按一下 [**建立資源**及它們在 [搜尋] 方塊中輸入**儲存體帳戶**。</span><span class="sxs-lookup"><span data-stu-id="6a003-139">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![建立儲存體帳戶資源](media/TCimage12.png)

3. <span data-ttu-id="6a003-141">按一下 [**儲存**]，然後按一下 [**儲存體帳戶**。</span><span class="sxs-lookup"><span data-stu-id="6a003-141">Click **Storage**, and then click **Storage account**.</span></span>

   ![按一下儲存，然後按一下 [儲存體帳戶](media/TCimage13.png)

4. <span data-ttu-id="6a003-143">在 [**建立儲存體帳戶**] 頁面上，在 [訂閱] 方塊中，選取**Pay-As-You-Go**或取決於哪些類型的 Azure 訂用帳戶必須**免費試用版**。</span><span class="sxs-lookup"><span data-stu-id="6a003-143">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![選擇儲存體帳戶類型](media/TCimage14.png)

5. <span data-ttu-id="6a003-145">選取或建立資源群組。</span><span class="sxs-lookup"><span data-stu-id="6a003-145">Select or create a resource group.</span></span>

   ![選取或建立資源群組](media/TCimage15.png)

6. <span data-ttu-id="6a003-147">輸入儲存體帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="6a003-147">Type a name for the storage account.</span></span>

   ![命名儲存體帳戶](media/TCimage16.png)

7. <span data-ttu-id="6a003-149">檢閱，然後按一下 [**建立**]，以建立儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="6a003-149">Review and then click **Create** to create the storage account.</span></span>

   ![檢閱設定，然後建立儲存體帳戶](media/TCimage17.png)

8. <span data-ttu-id="6a003-151">在一段時間後按一下 [**重新整理**，然後按一下 [瀏覽至儲存體帳戶的 [**移至資源**。</span><span class="sxs-lookup"><span data-stu-id="6a003-151">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![移至您剛才建立的儲存體帳戶](media/TCimage18.png)

9. <span data-ttu-id="6a003-153">在左側的導覽窗格中，按一下 [**便捷鍵**。</span><span class="sxs-lookup"><span data-stu-id="6a003-153">Click **Access keys** in the left navigation pane.</span></span>

   ![按一下 [便捷鍵](media/TCimage19.png)

10. <span data-ttu-id="6a003-155">複製**連接字串**，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6a003-155">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="6a003-156">您使用此步驟 4 中建立 web 應用程式資源時。</span><span class="sxs-lookup"><span data-stu-id="6a003-156">You use this when creating a web app resource in Step 4.</span></span>

    ![複製連接字串](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="6a003-158">步驟 4： 在 Azure 中建立新的 web 應用程式資源</span><span class="sxs-lookup"><span data-stu-id="6a003-158">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="6a003-159">在 [**首頁**] 頁面在 Azure 入口網站中，按一下 [**建立資源\>每個項目\>Web 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="6a003-159">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="6a003-160">在 [ **Web 應用程式**] 頁面上，按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="6a003-160">On the **Web app** page, click **Create**.</span></span>

   ![在 Azure 中建立 web 應用程式資源](media/TCimage21.png)

2. <span data-ttu-id="6a003-162">填入詳細資料 （如下所示），然後再建立 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="6a003-162">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="6a003-163">您在 [**應用程式名稱**] 方塊中輸入的名稱用來建立 Azure 應用程式服務的 URL;例如，twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="6a003-163">The name that you enter in the **App name** box is used to create the Azure app service URL; for example, twitterconnector.azurewebsites.net.</span></span>

   ![<span data-ttu-id="6a003-164">類型的 web 應用程式資源名稱;例如 twitterconnector.azurewebsites.net</span><span class="sxs-lookup"><span data-stu-id="6a003-164">Type name for the web app resource; for example twitterconnector.azurewebsites.net</span></span> ](media/TCimage22.png)

3. <span data-ttu-id="6a003-165">移至新建立的 web 應用程式資源並按一下 [**應用程式設定**]，請在左側的導覽窗格中。</span><span class="sxs-lookup"><span data-stu-id="6a003-165">Go to the newly created web app resource and click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="6a003-166">**應用程式設定**] 下按一下 [**新增新的設定**，並新增下列三項設定。</span><span class="sxs-lookup"><span data-stu-id="6a003-166">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="6a003-167">使用複製的值 （您到文字檔先前的步驟）：</span><span class="sxs-lookup"><span data-stu-id="6a003-167">Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="6a003-168">**APISecretKey** – 您可以為密碼輸入任何值。</span><span class="sxs-lookup"><span data-stu-id="6a003-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="6a003-169">這用來存取在步驟 7 中的連接器 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="6a003-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="6a003-170">**StorageAccountConnectionString** – 您在步驟 3 中建立 Azure 儲存體帳戶之後所複製的 Uri 的連接字串。</span><span class="sxs-lookup"><span data-stu-id="6a003-170">**StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="6a003-171">**tenantId** – 您在步驟 2 中的 Azure Active Directory 中建立 Twitter 連接器應用程式之後複製您 Office 365 組織租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="6a003-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![新增應用程式設定](media/TCimage23.png)

4. <span data-ttu-id="6a003-173">**一般設定**] 下按一下 [**上**旁**Always On**。</span><span class="sxs-lookup"><span data-stu-id="6a003-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="6a003-174">按一下 [**儲存**] 頁面的頂端儲存應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="6a003-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![開啟 web 應用程式資源，並再將它儲存](media/TCimage24.png)

5. <span data-ttu-id="6a003-176">最後一個步驟是將連接器 app 原始程式碼上傳至 Azure 中您在步驟 1 中下載。</span><span class="sxs-lookup"><span data-stu-id="6a003-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="6a003-177">在網頁瀏覽器中，移至 https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="6a003-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="6a003-178">例如，如果您的 Azure 應用程式資源 （這在本節中的步驟 2 中所命名） 的名稱是**twitterconnector**，然後您會移至https://twitterconnector.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="6a003-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="6a003-179">拖放到此頁面 SampleConnector.zip （，您在步驟 1 中下載）。</span><span class="sxs-lookup"><span data-stu-id="6a003-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="6a003-180">將檔案上傳並部署成功後，看起來類似下列的螢幕擷取畫面] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="6a003-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![將拖放到此頁面的 SampleConnector.zip 檔案](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="6a003-182">步驟 5： 建立 Twitter 應用程式</span><span class="sxs-lookup"><span data-stu-id="6a003-182">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="6a003-183">移至 [ https://developer.twitter.com，登入您的組織，開發人員帳戶使用的認證，然後按一下 [**應用程式**。</span><span class="sxs-lookup"><span data-stu-id="6a003-183">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![移至 [ https://developer.twitter.com ，然後登入](media/TCimage25-5.png)
2. <span data-ttu-id="6a003-185">按一下 [**建立應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="6a003-185">Click **Create an app**.</span></span>
   
   ![移至應用程式] 頁面上，若要建立的應用程式](media/TCimage26.png)

3. <span data-ttu-id="6a003-187">在 [**應用程式詳細資料**，新增應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6a003-187">Under **App details**, add information about the application.</span></span>

   ![輸入應用程式的相關資訊](media/TCimage27.png)

4. <span data-ttu-id="6a003-189">Twitter 開發人員儀表板上選取您剛建立的應用程式複製應用程式 ID 會顯示，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6a003-189">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="6a003-190">然後按一下 [**詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="6a003-190">Then click **Details**.</span></span>
   
   ![複製並儲存應用程式識別碼](media/TCimage28.png)

5. <span data-ttu-id="6a003-192">**索引鍵和權杖**索引標籤上，在**消費者 API 機碼**下複製 API 祕密金鑰並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6a003-192">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="6a003-193">然後按一下 [**建立**]，以產生的存取權杖及存取權杖的密碼，並複製這些文字檔案或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6a003-193">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![複製並儲存至 API 祕密金鑰](media/TCimage29.png)

   <span data-ttu-id="6a003-195">然後按一下 [**建立**]，以產生的存取權杖及存取權杖的密碼，並複製這些文字檔案或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6a003-195">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="6a003-196">按一下 [**權限**] 索引標籤，並設定權限，如下列螢幕擷取畫面所示：</span><span class="sxs-lookup"><span data-stu-id="6a003-196">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![設定權限](media/TCimage30.png)

7. <span data-ttu-id="6a003-198">儲存的權限設定之後，按一下 [**應用程式詳細資料**] 索引標籤，然後按一下 [**編輯 > 編輯詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="6a003-198">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![編輯應用程式詳細資料](media/TCimage31.png)

8. <span data-ttu-id="6a003-200">執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="6a003-200">Do the following tasks:</span></span>

   - <span data-ttu-id="6a003-201">選取核取方塊可允許登入 Twitter 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="6a003-201">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="6a003-202">新增的 OAuth 重新導向 Uri 使用下列格式： \*\* \<connectorserviceuri>/檢視/TwitterOAuth\**、 其中*connectorserviceuri\*的值是為您的組織; Azure 應用程式服務 URL例如， https://twitterconnector.azurewebsites.net/Views/TwitterOAuth。</span><span class="sxs-lookup"><span data-stu-id="6a003-202">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![允許連接器 Twitter 登入，並將新增 OAuth 重新導向 Uri 的應用程式](media/TCimage32.png)

<span data-ttu-id="6a003-204">在 Twitter 開發人員 app 現已可使用。</span><span class="sxs-lookup"><span data-stu-id="6a003-204">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="6a003-205">步驟 6： 設定連接器的 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="6a003-205">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="6a003-206">移至 https://\<AzureAppResourceName>.azurewebsites.net （其中**AzureAppResourceName**是您在步驟 4 中名為您 Azure 應用程式資源的名稱）。</span><span class="sxs-lookup"><span data-stu-id="6a003-206">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="6a003-207">例如，如果名稱為**twitterconnector**，請移至https://twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="6a003-207">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="6a003-208">應用程式的 [首頁] 頁面上看起來像下列螢幕擷取畫面中：</span><span class="sxs-lookup"><span data-stu-id="6a003-208">The home page of the app looks like the following screenshot:</span></span>

   ![移至 Azure 應用程式資源頁面](media/FBCimage41.png)

2. <span data-ttu-id="6a003-210">按一下 [**設定**] 頁面中，會顯示號。</span><span class="sxs-lookup"><span data-stu-id="6a003-210">Click **Configure** to display a sign in page.</span></span>

   ![按一下 [設定] 頁面中，會顯示號](media/FBCimage42.png)

3. <span data-ttu-id="6a003-212">在租用戶識別碼] 方塊中，輸入或貼上您的租用戶識別碼 （您在步驟 2 中所取得）。</span><span class="sxs-lookup"><span data-stu-id="6a003-212">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="6a003-213">在 [密碼] 方塊中，輸入或貼上 APISecretKey （，您在步驟 2 中所取得），，然後按一下要顯示 [**設定詳細資料**] 頁面上**設定的組態設定**。</span><span class="sxs-lookup"><span data-stu-id="6a003-213">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![使用租用戶識別碼和 API 祕密金鑰登入](media/TCimage35.png)

4. <span data-ttu-id="6a003-215">[**設定的詳細資訊**，請輸入下列組態設定</span><span class="sxs-lookup"><span data-stu-id="6a003-215">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="6a003-216">**Twitter Api 金鑰**– 您在步驟 5 中建立的 Twitter 應用程式的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="6a003-216">**Twitter Api Key** – The app ID for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="6a003-217">**Twitter Api 密碼金鑰**– 您在步驟 5 中建立的 Twitter 應用程式的 API 祕密金鑰。</span><span class="sxs-lookup"><span data-stu-id="6a003-217">**Twitter Api Secret Key** – The API secret key for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="6a003-218">**Twitter 存取 Token** – 您在步驟 5 中建立的存取權杖。</span><span class="sxs-lookup"><span data-stu-id="6a003-218">**Twitter Access Token** – The access token that you created in Step 5.</span></span>
   - <span data-ttu-id="6a003-219">**Twitter 存取 Token 密碼**– 您在步驟 5 中建立的存取權杖密碼。</span><span class="sxs-lookup"><span data-stu-id="6a003-219">**Twitter Access Token Secret** – The access token secret that you created in Step 5.</span></span>
   - <span data-ttu-id="6a003-220">**AAD 應用程式識別碼**– 您在步驟 2 中建立的 Azure Active Directory 應用程式的應用程式識別碼</span><span class="sxs-lookup"><span data-stu-id="6a003-220">**AAD Application ID** – The application ID for the Azure Active Directory app that you created in Step 2</span></span>
   - <span data-ttu-id="6a003-221">**AAD 應用程式密碼**– 您在步驟 4 中建立的 APISecretKey 密碼的值。</span><span class="sxs-lookup"><span data-stu-id="6a003-221">**AAD Application Secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="6a003-222">**AAD 應用程式的 Uri** – AAD 應用程式在步驟 2; 中所取得的 Uri例如， `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`。</span><span class="sxs-lookup"><span data-stu-id="6a003-222">**AAD Application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="6a003-223">**App 觀點檢測機碼**– 保留此方塊空白。</span><span class="sxs-lookup"><span data-stu-id="6a003-223">**App Insights Instrumentation Key** – Leave this box blank.</span></span>

5. <span data-ttu-id="6a003-224">按一下 [**儲存**] 以儲存連接器設定。</span><span class="sxs-lookup"><span data-stu-id="6a003-224">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="6a003-225">步驟 7： 設立安全性與合規性中心中的自訂連接器</span><span class="sxs-lookup"><span data-stu-id="6a003-225">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="6a003-226">移至 [ <https://protection.office.com> ，然後按一下 [**資訊控管\>匯入\>封存協力廠商資料**。</span><span class="sxs-lookup"><span data-stu-id="6a003-226">Go to <https://protection.office.com> and then click **Information governance \> Import \> Archive third-party data**.</span></span>

    ![移至安全性與合規性中心中封存協力廠商資料頁面](media/TCimage36.png)

2. <span data-ttu-id="6a003-228">按一下 [**新增連接器**]，然後按一下 [ **Twitter**。</span><span class="sxs-lookup"><span data-stu-id="6a003-228">Click **Add a connector** and then click **Twitter**.</span></span>

   ![按一下 [新增連接器]，以新增 Twitter 連接器](media/TCimage37.png)

3. <span data-ttu-id="6a003-230">在 [**新增連接器應用程式**] 頁面中，輸入下列資訊，然後按一下 [**驗證連接器**。</span><span class="sxs-lookup"><span data-stu-id="6a003-230">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="6a003-231">在第一個方塊中，輸入連接器名稱，例如**Twitter**。</span><span class="sxs-lookup"><span data-stu-id="6a003-231">In the first box, type a name for the connector, such as **Twitter**.</span></span>
    - <span data-ttu-id="6a003-232">在第二個方塊中，輸入或貼上您在步驟 4 中新增 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="6a003-232">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="6a003-233">在第三個方塊中，輸入或貼上的 Azure 應用程式服務 URL;例如， **https://twitterconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="6a003-233">In the third box, type or paste the Azure app service URL; for example, **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="6a003-234">成功驗證連接器之後，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="6a003-234">After the connector is successfully validated, click **Next**.</span></span>

   ![輸入連接器的應用程式設定](media/TCimage38.png)

4. <span data-ttu-id="6a003-236">按一下 [**登入與連接器應用程式**。</span><span class="sxs-lookup"><span data-stu-id="6a003-236">Click **Login with Connector App**.</span></span>

   ![登入連接器應用程式](media/TCimage39.png)

5. <span data-ttu-id="6a003-238">輸入或貼上 APISecretKey 一次，然後按一下 [**連接器服務的登入**。</span><span class="sxs-lookup"><span data-stu-id="6a003-238">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![若要登入連接器服務的型別 API 祕密金鑰](media/TCimage40.png)

6. <span data-ttu-id="6a003-240">按一下 [**繼續 Twitter**。</span><span class="sxs-lookup"><span data-stu-id="6a003-240">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="6a003-241">在 Twitter 登入] 頁面上，登入您的組織 Twitter 帳戶的帳戶使用的認證。</span><span class="sxs-lookup"><span data-stu-id="6a003-241">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![Twitter 帳戶登入](media/TCimage42.png)

   <span data-ttu-id="6a003-243">登入後，[Twitter] 頁面上會顯示下列訊息、 「 Twitter 連接器工作成功設定。 」</span><span class="sxs-lookup"><span data-stu-id="6a003-243">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="6a003-244">按一下 [**完成**] 以完成 Twitter 連接器設定。</span><span class="sxs-lookup"><span data-stu-id="6a003-244">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="6a003-245">在 [**設定篩選器**] 頁面中，您可以套用篩選器來匯入 （和封存） 特定天數的項目。</span><span class="sxs-lookup"><span data-stu-id="6a003-245">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="6a003-246">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a003-246">Click **Next**.</span></span>

   ![設定篩選要匯入特定天數之項目](media/TCimage44.png)

10. <span data-ttu-id="6a003-248">在 [**設定儲存體帳戶**] 頁面上，輸入 Twitter 項目將會匯入至 Office 365 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6a003-248">On the **Set Storage Account** page, type the email address of an Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![指定 Office 365 信箱匯入 Twitter 項目](media/TCimage45.png)

11. <span data-ttu-id="6a003-250">檢閱您的設定，然後按一下 [**完成**] 以完成安全性 & 規範中心的連接器設定。</span><span class="sxs-lookup"><span data-stu-id="6a003-250">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![檢閱設定，然後再按一下 [完成]](media/TCimage46.png)

    ![畫面中顯示該連接器安裝程式完成](media/TCimage47.png)

12. <span data-ttu-id="6a003-253">移至**封存協力廠商資料**頁面才能看見匯入程序的進度。</span><span class="sxs-lookup"><span data-stu-id="6a003-253">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![顯示在 [安全性與合規性中心的新連接器](media/TCimage48.png)
