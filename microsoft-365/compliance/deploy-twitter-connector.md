---
title: 部署封存 Twitter 資料 Office 365 中的連接器
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
ms.openlocfilehash: c3c5af0fc42057d9fc2e8b8e67423398d6ed0ddf
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070227"
---
# <a name="deploy-a-connector-to-archive-twitter-data-in-office-365"></a><span data-ttu-id="3c438-104">部署封存 Twitter 資料 Office 365 中的連接器</span><span class="sxs-lookup"><span data-stu-id="3c438-104">Deploy a connector to archive Twitter data in Office 365</span></span>

<span data-ttu-id="3c438-105">本文包含的逐步程序來部署您的組織 Twitter 帳戶的資料匯入至 Office 365 會使用 Office 365 匯入服務的連接器。</span><span class="sxs-lookup"><span data-stu-id="3c438-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="3c438-106">此程序的高階概觀與部署 Twitter 連接器所需的必要條件清單，請參閱[使用封存 Twitter 資料 Office 365 （預覽） 中的範例連接器](archive-twitter-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="3c438-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a sample connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="3c438-107">步驟 1： 下載套件</span><span class="sxs-lookup"><span data-stu-id="3c438-107">Step 1: Download the package</span></span>

<span data-ttu-id="3c438-108">從 [版本] 區段中，GitHub 儲存機制中下載預先建立的套件[https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)。</span><span class="sxs-lookup"><span data-stu-id="3c438-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="3c438-109">在 [最新版本中，下載 zip 檔名為**SampleConnector.zip**。</span><span class="sxs-lookup"><span data-stu-id="3c438-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="3c438-110">您將此 zip 檔案上傳到步驟 4 中的 Azure。</span><span class="sxs-lookup"><span data-stu-id="3c438-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="3c438-111">步驟 2： 在 Azure Active Directory 中建立的應用程式</span><span class="sxs-lookup"><span data-stu-id="3c438-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="3c438-112">移至 [<https://portal.azure.com>並使用 Office 365 全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="3c438-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![](media/TCimage01.png)

2. <span data-ttu-id="3c438-113">在左側的導覽窗格中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="3c438-113">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![](media/TCimage02.png)

3. <span data-ttu-id="3c438-114">在左側的導覽窗格中，按一下 [**應用程式註冊 （預覽）** ，然後按一下 [**新增註冊**。</span><span class="sxs-lookup"><span data-stu-id="3c438-114">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![](media/TCimage03.png)

4. <span data-ttu-id="3c438-115">註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="3c438-115">Register the application.</span></span> <span data-ttu-id="3c438-116">**（選用） 的 [重新導向 URI**，選取 Web 應用程式類型] 下拉式清單中，然後輸入<https://portal.azure.com>URI] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="3c438-116">Under **Redirect URI (optional)**, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/TCimage04.png)

5. <span data-ttu-id="3c438-117">複製 **（用戶端） 的應用程式識別碼**] 及 [**目錄 （承租人） 識別碼**，並將它們儲存到文字檔或其他安全的位置。</span><span class="sxs-lookup"><span data-stu-id="3c438-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="3c438-118">您在稍後步驟使用這些識別碼。</span><span class="sxs-lookup"><span data-stu-id="3c438-118">You use these IDs in later steps.</span></span>

    ![](media/TCimage05.png)

6. <span data-ttu-id="3c438-119">移至**新的應用程式的憑證 & 機密資料**，並在 [**用戶端密碼**] 下按一下 [**新的用戶端密碼**。</span><span class="sxs-lookup"><span data-stu-id="3c438-119">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![](media/TCimage06.png)

7. <span data-ttu-id="3c438-120">建立新的密碼。</span><span class="sxs-lookup"><span data-stu-id="3c438-120">Create a new secret.</span></span> <span data-ttu-id="3c438-121">在 [描述] 方塊中，輸入密碼，然後選擇的到期時間。</span><span class="sxs-lookup"><span data-stu-id="3c438-121">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![](media/TCimage08.png)

8. <span data-ttu-id="3c438-122">複製密碼的值，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="3c438-122">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="3c438-123">這是您在稍後步驟使用的 AAD 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="3c438-123">This is the AAD application secret that you use in later steps.</span></span>

   ![](media/TCimage09.png)

9. <span data-ttu-id="3c438-124">移至**資訊清單**，然後複製 identifierUris （這也稱為 AAD 應用程式的 Uri） 以反白顯示下列螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="3c438-124">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="3c438-125">複製到文字檔或其他儲存位置的 AAD 應用程式的 Uri。</span><span class="sxs-lookup"><span data-stu-id="3c438-125">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="3c438-126">您在步驟 6 中使用。</span><span class="sxs-lookup"><span data-stu-id="3c438-126">You use it in Step 6.</span></span>

    ![](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="3c438-127">步驟 3： 建立 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="3c438-127">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="3c438-128">移至 Azure 的首頁上，為您的組織。</span><span class="sxs-lookup"><span data-stu-id="3c438-128">Go to the Azure home page for your organization.</span></span>

    ![](media/TCimage11.png)

2. <span data-ttu-id="3c438-129">按一下 [**建立資源**及它們在 [搜尋] 方塊中輸入**儲存體帳戶**。</span><span class="sxs-lookup"><span data-stu-id="3c438-129">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![](media/TCimage12.png)

3. <span data-ttu-id="3c438-130">按一下 [**儲存**]，然後按一下 [**儲存體帳戶**。</span><span class="sxs-lookup"><span data-stu-id="3c438-130">Click **Storage**, and then click **Storage account**.</span></span>

   ![](media/TCimage13.png)

4. <span data-ttu-id="3c438-131">在 [**建立儲存體帳戶**] 頁面上，在 [訂閱] 方塊中，選取**Pay-As-You-Go**或取決於哪些類型的 Azure 訂用帳戶必須**免費試用版**。</span><span class="sxs-lookup"><span data-stu-id="3c438-131">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![](media/TCimage14.png)

5. <span data-ttu-id="3c438-132">選取或建立資源群組。</span><span class="sxs-lookup"><span data-stu-id="3c438-132">Select or create a resource group.</span></span>

   ![](media/TCimage15.png)

6. <span data-ttu-id="3c438-133">輸入儲存體帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="3c438-133">Type a name for the storage account.</span></span>

   ![](media/TCimage16.png)

7. <span data-ttu-id="3c438-134">檢閱，然後按一下 [**建立**]，以建立儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="3c438-134">Review and then click **Create** to create the storage account.</span></span>

   ![](media/TCimage17.png)

8. <span data-ttu-id="3c438-135">在一段時間後按一下 [**重新整理**，然後按一下 [瀏覽至儲存體帳戶的 [**移至資源**。</span><span class="sxs-lookup"><span data-stu-id="3c438-135">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![](media/TCimage18.png)

9. <span data-ttu-id="3c438-136">在左側的導覽窗格中，按一下 [**便捷鍵**。</span><span class="sxs-lookup"><span data-stu-id="3c438-136">Click **Access keys** in the left navigation pane.</span></span>

   ![](media/TCimage19.png)

10. <span data-ttu-id="3c438-137">複製**連接字串**，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="3c438-137">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="3c438-138">您使用此步驟 4 中建立 web 應用程式資源時。</span><span class="sxs-lookup"><span data-stu-id="3c438-138">You use this when creating a web app resource in Step 4.</span></span>

    ![](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="3c438-139">步驟 4： 在 Azure 中建立新的 web 應用程式資源</span><span class="sxs-lookup"><span data-stu-id="3c438-139">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="3c438-140">在 [**首頁**] 頁面在 Azure 入口網站中，按一下 [**建立資源\>每個項目\>Web 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="3c438-140">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="3c438-141">在 [ **Web 應用程式**] 頁面上，按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="3c438-141">On the **Web app** page, click **Create**.</span></span>

   ![](media/TCimage21.png)

2. <span data-ttu-id="3c438-142">填入詳細資料 （如下所示），然後再建立 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="3c438-142">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="3c438-143">您在 [**應用程式名稱**] 方塊中輸入的名稱用來建立 Azure 應用程式服務的 URL;例如，twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="3c438-143">The name that you enter in the **App name** box is used to create the Azure app service URL; for example, twitterconnector.azurewebsites.net.</span></span>

   ![](media/TCimage22.png)

3. <span data-ttu-id="3c438-144">移至新建立的 web 應用程式資源並按一下 [**應用程式設定**]，請在左側的導覽窗格中。</span><span class="sxs-lookup"><span data-stu-id="3c438-144">Go to the newly created web app resource and click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="3c438-145">**應用程式設定**] 下按一下 [**新增新的設定**，並新增下列三項設定。</span><span class="sxs-lookup"><span data-stu-id="3c438-145">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="3c438-146">使用複製的值 （您到文字檔先前的步驟）：</span><span class="sxs-lookup"><span data-stu-id="3c438-146">Use the values (that you copied to the text file from the previous steps):</span></span> 

    <span data-ttu-id="3c438-147">– \* \* APISecretKey-您可以為密碼輸入任何值。</span><span class="sxs-lookup"><span data-stu-id="3c438-147">– \*\*APISecretKey — You can type any value as the secret.</span></span> <span data-ttu-id="3c438-148">這用來存取在步驟 7 中的連接器 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="3c438-148">This is used to access the connector web app in Step 7.</span></span>

    <span data-ttu-id="3c438-149">– **StorageAccountConnectionString** – 連接字串，您在步驟 3 中建立 Azure 儲存體帳戶之後所複製的 Uri。</span><span class="sxs-lookup"><span data-stu-id="3c438-149">– **StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    <span data-ttu-id="3c438-150">Office 365 組織，您在步驟 2 中的 Azure Active Directory 中建立 Twitter 連接器應用程式之後所複製 – **tenantId** – 租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="3c438-150">– **tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/TCimage23.png)

4. <span data-ttu-id="3c438-151">**一般設定**] 下按一下 [**上**旁**Always On**。</span><span class="sxs-lookup"><span data-stu-id="3c438-151">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="3c438-152">按一下 [**儲存**] 頁面的頂端儲存應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="3c438-152">Click **Save** at the top of the page to save the application settings.</span></span>

   ![](media/TCimage24.png)

5. <span data-ttu-id="3c438-153">最後一個步驟是將連接器 app 原始程式碼上傳至 Azure 中您在步驟 1 中下載。</span><span class="sxs-lookup"><span data-stu-id="3c438-153">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="3c438-154">在網頁瀏覽器中，移至 https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="3c438-154">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="3c438-155">例如，如果您的 Azure 應用程式資源 （這在本節中的步驟 2 中所命名） 的名稱是**twitterconnector**，然後您會移至https://twitterconnector.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="3c438-155">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="3c438-156">拖放到此頁面 SampleConnector.zip （，您在步驟 1 中下載）。</span><span class="sxs-lookup"><span data-stu-id="3c438-156">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="3c438-157">將檔案上傳並部署成功後，看起來類似下列的螢幕擷取畫面] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="3c438-157">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="3c438-158">步驟 5： 建立 Twitter 應用程式</span><span class="sxs-lookup"><span data-stu-id="3c438-158">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="3c438-159">移至 [ https://developer.twitter.com，登入您的組織，開發人員帳戶使用的認證，然後按一下 [**應用程式**。</span><span class="sxs-lookup"><span data-stu-id="3c438-159">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![TCimage25 5.png](media/TCimage25-5.png)
2. <span data-ttu-id="3c438-161">按一下 [**建立應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="3c438-161">Click **Create an app**.</span></span>
   
   ![](media/TCimage26.png)

3. <span data-ttu-id="3c438-162">在 [**應用程式詳細資料**，新增應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3c438-162">Under **App details**, add information about the application.</span></span>

   ![](media/TCimage27.png)

4. <span data-ttu-id="3c438-163">Twitter 開發人員儀表板上選取您剛建立的應用程式複製應用程式 ID 會顯示，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="3c438-163">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="3c438-164">然後按一下 [**詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="3c438-164">Then click **Details**.</span></span>
   
   ![](media/TCimage28.png)

5. <span data-ttu-id="3c438-165">**索引鍵和權杖**索引標籤上，在**消費者 API 機碼**下複製 API 祕密金鑰並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="3c438-165">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="3c438-166">然後按一下 [**建立**]，以產生的存取權杖及存取權杖的密碼，並複製這些文字檔案或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="3c438-166">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![](media/TCimage29.png)

   <span data-ttu-id="3c438-167">然後按一下 [**建立**]，以產生的存取權杖及存取權杖的密碼，並複製這些文字檔案或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="3c438-167">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="3c438-168">按一下 [**權限**] 索引標籤，並設定權限，如下列螢幕擷取畫面所示：</span><span class="sxs-lookup"><span data-stu-id="3c438-168">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![](media/TCimage30.png)

7. <span data-ttu-id="3c438-169">儲存的權限設定之後，按一下 [**應用程式詳細資料**] 索引標籤，然後按一下 [**編輯 > 編輯詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="3c438-169">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![](media/TCimage31.png)

8. <span data-ttu-id="3c438-170">執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="3c438-170">Do the following tasks:</span></span>

   <span data-ttu-id="3c438-171">– 選取核取方塊可允許登入 Twitter 連接器應用程式。</span><span class="sxs-lookup"><span data-stu-id="3c438-171">– Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   <span data-ttu-id="3c438-172">– 新增的 OAuth 重新導向 Uri 使用下列格式： \*\* \<connectorserviceuri>/檢視/TwitterOAuth\**、 其中*connectorserviceuri\*的值是為您的組織; Azure 應用程式服務 URL例如， https://twitterconnector.azurewebsites.net/Views/TwitterOAuth。</span><span class="sxs-lookup"><span data-stu-id="3c438-172">– Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

   ![](media/TCimage32.png)

<span data-ttu-id="3c438-173">在 Twitter 開發人員 app 現已可使用。</span><span class="sxs-lookup"><span data-stu-id="3c438-173">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="3c438-174">步驟 6： 設定連接器的 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="3c438-174">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="3c438-175">移至 https://\<AzureAppResourceName>.azurewebsites.net （其中**AzureAppResourceName**是您在步驟 4 中名為您 Azure 應用程式資源的名稱）。</span><span class="sxs-lookup"><span data-stu-id="3c438-175">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="3c438-176">例如，如果名稱為**twitterconnector**，請移至https://twitterconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="3c438-176">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="3c438-177">應用程式的 [首頁] 頁面上看起來像下列螢幕擷取畫面中：</span><span class="sxs-lookup"><span data-stu-id="3c438-177">The home page of the app looks like the following screenshot:</span></span>

   ![](media/FBCimage41.png)

2. <span data-ttu-id="3c438-178">按一下 [**設定**] 頁面中，會顯示號。</span><span class="sxs-lookup"><span data-stu-id="3c438-178">Click **Configure** to display a sign in page.</span></span>

   ![](media/FBCimage42.png)

3. <span data-ttu-id="3c438-179">在租用戶識別碼] 方塊中，輸入或貼上您的租用戶識別碼 （您在步驟 2 中所取得）。</span><span class="sxs-lookup"><span data-stu-id="3c438-179">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="3c438-180">在 [密碼] 方塊中，輸入或貼上 APISecretKey （，您在步驟 2 中所取得），，然後按一下要顯示 [**設定詳細資料**] 頁面上**設定的組態設定**。</span><span class="sxs-lookup"><span data-stu-id="3c438-180">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![](media/TCimage35.png)

4. <span data-ttu-id="3c438-181">[**設定的詳細資訊**，請輸入下列組態設定</span><span class="sxs-lookup"><span data-stu-id="3c438-181">Under **Configuration Details**, enter the following configuration settings</span></span> 

   <span data-ttu-id="3c438-182">您在步驟 5 中建立的 Twitter 應用程式 – **Twitter Api 金鑰**– 應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="3c438-182">– **Twitter Api Key** – The app ID for the Twitter application that you created in Step 5.</span></span>
   <span data-ttu-id="3c438-183">您在步驟 5 中建立的 Twitter 應用程式 – **Twitter Api 密碼金鑰**– API 祕密金鑰。</span><span class="sxs-lookup"><span data-stu-id="3c438-183">– **Twitter Api Secret Key** – The API secret key for the Twitter application that you created in Step 5.</span></span>
   <span data-ttu-id="3c438-184">您在步驟 5 中建立的 – **Twitter 存取 Token** – 存取權杖。</span><span class="sxs-lookup"><span data-stu-id="3c438-184">– **Twitter Access Token** – The access token that you created in Step 5.</span></span>
   <span data-ttu-id="3c438-185">– **Twitter 存取 Token 密碼**– 您在步驟 5 中建立的存取權杖密碼。</span><span class="sxs-lookup"><span data-stu-id="3c438-185">– **Twitter Access Token Secret** – The access token secret that you created in Step 5.</span></span>
   <span data-ttu-id="3c438-186">您在步驟 2 建立 – **AAD 應用程式密碼**– 您在步驟 4 中建立的 APISecretKey 密碼值的 Azure Active Directory 應用程式 – **AAD 應用程式識別碼**– 應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="3c438-186">– **AAD Application ID** – The application ID for the Azure Active Directory app that you created in Step 2 – **AAD Application Secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   <span data-ttu-id="3c438-187">在 [步驟 2; 的 – **AAD 應用程式的 Uri** – AAD 應用程式的 Uri 取得例如， https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213。</span><span class="sxs-lookup"><span data-stu-id="3c438-187">– **AAD Application Uri** – The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   <span data-ttu-id="3c438-188">– **App 觀點檢測機碼**– 將保留此方塊空白。</span><span class="sxs-lookup"><span data-stu-id="3c438-188">– **App Insights Instrumentation Key** – Leave this box blank.</span></span>

5. <span data-ttu-id="3c438-189">按一下 [**儲存**] 以儲存連接器設定。</span><span class="sxs-lookup"><span data-stu-id="3c438-189">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="3c438-190">步驟 7： 設立安全性與合規性中心中的自訂連接器</span><span class="sxs-lookup"><span data-stu-id="3c438-190">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="3c438-191">移至 [ <https://protection.office.com> ，然後按一下 [**資料控管\>匯入\>封存協力廠商資料**。</span><span class="sxs-lookup"><span data-stu-id="3c438-191">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

    ![](media/TCimage36.png)

2. <span data-ttu-id="3c438-192">按一下 [**新增連接器**]，然後按一下 [ **Twitter**。</span><span class="sxs-lookup"><span data-stu-id="3c438-192">Click **Add a connector** and then click **Twitter**.</span></span>

   ![](media/TCimage37.png)

3. <span data-ttu-id="3c438-193">在 [**新增連接器應用程式**] 頁面中，輸入下列資訊，然後按一下 [**驗證連接器**。</span><span class="sxs-lookup"><span data-stu-id="3c438-193">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    <span data-ttu-id="3c438-194">– 在第一個方塊中，輸入連接器名稱，例如**Twitter**。</span><span class="sxs-lookup"><span data-stu-id="3c438-194">– In the first box, type a name for the connector, such as **Twitter**.</span></span>
    <span data-ttu-id="3c438-195">– 在第二個方塊中，輸入或貼上您在步驟 4 中新增 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="3c438-195">– In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    <span data-ttu-id="3c438-196">– 在第三個方塊中，輸入或貼上的 Azure 應用程式服務 URL;例如， **https://twitterconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="3c438-196">– In the third box, type or paste the Azure app service URL; for example, **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="3c438-197">成功驗證連接器之後，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="3c438-197">After the connector is successfully validated, click **Next**.</span></span>

   ![](media/TCimage38.png)

4. <span data-ttu-id="3c438-198">按一下 [**登入與連接器應用程式**。</span><span class="sxs-lookup"><span data-stu-id="3c438-198">Click **Login with Connector App**.</span></span>

   ![](media/TCimage39.png)

5. <span data-ttu-id="3c438-199">輸入或貼上 APISecretKey 一次，然後按一下 [**連接器服務的登入**。</span><span class="sxs-lookup"><span data-stu-id="3c438-199">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/TCimage40.png)


6. <span data-ttu-id="3c438-200">按一下 [**繼續 Twitter**。</span><span class="sxs-lookup"><span data-stu-id="3c438-200">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="3c438-201">在 Twitter 登入] 頁面上，登入您的組織 Twitter 帳戶的帳戶使用的認證。</span><span class="sxs-lookup"><span data-stu-id="3c438-201">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![](media/TCimage42.png)

   <span data-ttu-id="3c438-202">登入後，[Twitter] 頁面上會顯示下列訊息、 「 Twitter 連接器工作成功設定。 」</span><span class="sxs-lookup"><span data-stu-id="3c438-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="3c438-203">按一下 [**完成**] 以完成 Twitter 連接器設定。</span><span class="sxs-lookup"><span data-stu-id="3c438-203">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="3c438-204">在 [**設定篩選器**] 頁面中，您可以套用篩選器來匯入 （和封存） 特定天數的項目。</span><span class="sxs-lookup"><span data-stu-id="3c438-204">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="3c438-205">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3c438-205">Click **Next**.</span></span>

   ![](media/TCimage44.png)

10. <span data-ttu-id="3c438-206">在 [**設定儲存體帳戶**] 頁面上，輸入 Twitter 項目將會匯入至 Office 365 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3c438-206">On the **Set Storage Account** page, type the email address of an Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![](media/TCimage45.png)

11. <span data-ttu-id="3c438-207">檢閱您的設定，然後按一下 [**完成**] 以完成安全性 & 規範中心的連接器設定。</span><span class="sxs-lookup"><span data-stu-id="3c438-207">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/TCimage46.png)

    ![](media/TCimage47.png)

12. <span data-ttu-id="3c438-208">移至**封存協力廠商資料**頁面才能看見匯入程序的進度。</span><span class="sxs-lookup"><span data-stu-id="3c438-208">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/TCimage48.png)
