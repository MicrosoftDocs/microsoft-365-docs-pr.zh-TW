---
title: 部署封存 Facebook 資料的連接器
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
description: 系統管理員可以設定原生的連接器，以匯入並封存至 Office 365 的 Facebook 商務頁面。 此資料會匯入至 Office 365 之後，您可以使用合規性功能，例如合法持有、 內容搜尋和保留原則來管理您的組織 Facebook 資料的控管。
ms.openlocfilehash: bb348c6e08151d63e92973d3f262704357e40814
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247476"
---
# <a name="deploy-a-connector-to-archive-facebook-data"></a><span data-ttu-id="1b857-104">部署封存 Facebook 資料的連接器</span><span class="sxs-lookup"><span data-stu-id="1b857-104">Deploy a connector to archive Facebook data</span></span>

<span data-ttu-id="1b857-105">本文包含的逐步程序來部署使用 Office 365 匯入服務 Facebook 商務頁面的資料匯入至 Office 365 的連接器。</span><span class="sxs-lookup"><span data-stu-id="1b857-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="1b857-106">此程序的高階概觀與部署的 Facebook 連接器所需的必要條件清單，請參閱[使用連接器來封存 Facebook Office 365 （預覽） 中的資料](archive-facebook-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="1b857-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use a connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="1b857-107">步驟 1： 下載套件</span><span class="sxs-lookup"><span data-stu-id="1b857-107">Step 1: Download the package</span></span>

<span data-ttu-id="1b857-108">從 [版本] 區段中，GitHub 儲存機制中下載預先建立的套件<https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>。</span><span class="sxs-lookup"><span data-stu-id="1b857-108">Download the prebuilt package from the Release section in the GitHub repository at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="1b857-109">在 [最新版本中，下載 zip 檔名為**SampleConnector.zip**。</span><span class="sxs-lookup"><span data-stu-id="1b857-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="1b857-110">您將此 zip 檔案上傳到步驟 4 中的 Azure。</span><span class="sxs-lookup"><span data-stu-id="1b857-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="1b857-111">步驟 2： 在 Azure Active Directory 中建立的應用程式</span><span class="sxs-lookup"><span data-stu-id="1b857-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="1b857-112">移至 [<https://portal.azure.com>並使用 Office 365 全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="1b857-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![在 [AAD 中建立應用程式](media/FBCimage1.png)

2. <span data-ttu-id="1b857-114">在左側的導覽窗格中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="1b857-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![按一下 [Azure Active Directory](media/FBCimage2.png)

3. <span data-ttu-id="1b857-116">在左側的導覽窗格中，按一下 [**應用程式註冊 （預覽）** ，然後按一下 [**新增註冊**。</span><span class="sxs-lookup"><span data-stu-id="1b857-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![按一下 [\* \* 應用程式註冊 （預覽） \* *，然後按一下 [* \* 新註冊 \* \*](media/FBCimage3.png)

4. <span data-ttu-id="1b857-118">註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="1b857-118">Register the application.</span></span> <span data-ttu-id="1b857-119">[重新導向 URI，選取 Web 應用程式類型] 下拉式清單中，然後輸入<https://portal.azure.com>URI] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="1b857-119">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![註冊應用程式](media/FBCimage4.png)

5. <span data-ttu-id="1b857-121">複製 **（用戶端） 的應用程式識別碼**] 及 [**目錄 （承租人） 識別碼**，並將它們儲存到文字檔或其他安全的位置。</span><span class="sxs-lookup"><span data-stu-id="1b857-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="1b857-122">您在稍後步驟使用這些識別碼。</span><span class="sxs-lookup"><span data-stu-id="1b857-122">You use these IDs in later steps.</span></span>

   ![複製應用程式識別碼] 及 [目錄識別碼，並將其儲存](media/FBCimage5.png)

6. <span data-ttu-id="1b857-124">移至**新的應用程式的憑證 & 機密資料**</span><span class="sxs-lookup"><span data-stu-id="1b857-124">Go to **Certificates & secrets for the new app.**</span></span>

   ![移至新的應用程式的憑證 & 機密資料](media/FBCimage6.png)

7. <span data-ttu-id="1b857-126">按一下 [**新的用戶端密碼**</span><span class="sxs-lookup"><span data-stu-id="1b857-126">Click **New client secret**</span></span>

   ![按一下 [新的用戶端密碼](media/FBCimage7.png)

8. <span data-ttu-id="1b857-128">建立新的密碼。</span><span class="sxs-lookup"><span data-stu-id="1b857-128">Create a new secret.</span></span> <span data-ttu-id="1b857-129">在 [描述] 方塊中，輸入密碼，然後選擇的到期時間。</span><span class="sxs-lookup"><span data-stu-id="1b857-129">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![輸入密碼，然後選擇 [的到期時間](media/FBCimage8.png)

9. <span data-ttu-id="1b857-131">複製密碼的值，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="1b857-131">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="1b857-132">這是您在稍後步驟使用的 AAD 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="1b857-132">This is the AAD application secret that you use in later steps.</span></span>

   ![複製密碼的值，並將它儲存](media/FBCimage9.png)

10. <span data-ttu-id="1b857-134">移至**資訊清單**，然後複製 identifierUris （這也稱為 AAD 應用程式的 Uri） 以反白顯示下列螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="1b857-134">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="1b857-135">複製到文字檔或其他儲存位置的 AAD 應用程式的 Uri。</span><span class="sxs-lookup"><span data-stu-id="1b857-135">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="1b857-136">您在步驟 6 中使用。</span><span class="sxs-lookup"><span data-stu-id="1b857-136">You use it in Step 6.</span></span>

   ![移至資訊清單，並將複製的 AAD 應用程式的 Uri](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="1b857-138">步驟 3： 建立 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="1b857-138">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="1b857-139">移至 Azure 的首頁上，為您的組織。</span><span class="sxs-lookup"><span data-stu-id="1b857-139">Go to the Azure home page for your organization.</span></span>

    ![移至 Azure 的 [首頁] 頁面](media/FBCimage11.png)

2. <span data-ttu-id="1b857-141">按一下 [**建立資源**，然後在 [搜尋] 方塊中輸入**儲存體帳戶**。</span><span class="sxs-lookup"><span data-stu-id="1b857-141">Click **Create a resource** and then type **storage account** in the search box.</span></span>

    ![按一下 [建立資源] 和 [類型儲存體帳戶](media/FBCimage12.png)

3. <span data-ttu-id="1b857-143">按一下 [**儲存**]，然後按一下 [**儲存體帳戶**。</span><span class="sxs-lookup"><span data-stu-id="1b857-143">Click **Storage**, and then click **Storage account**.</span></span>

    ![按一下儲存，然後按一下 [儲存體帳戶](media/FBCimage13.png)

4. <span data-ttu-id="1b857-145">在 [**建立儲存體帳戶**] 頁面上，在 [訂閱] 方塊中，選取**Pay-As-You-Go**或取決於哪些類型的 Azure 訂用帳戶必須**免費試用版**。</span><span class="sxs-lookup"><span data-stu-id="1b857-145">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="1b857-146">然後選取或建立資源群組。</span><span class="sxs-lookup"><span data-stu-id="1b857-146">Then select or create a resource group.</span></span>

    ![選取 [預付或免費試用版](media/FBCimage14.png)

5. <span data-ttu-id="1b857-148">輸入儲存體帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="1b857-148">Type a name for the storage account.</span></span>

    ![輸入儲存體帳戶的名稱](media/FBCimage15.png)

6. <span data-ttu-id="1b857-150">檢閱，然後按一下 [**建立**]，以建立儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="1b857-150">Review and then click **Create** to create the storage account.</span></span>

    ![建立儲存體帳戶](media/FBCimage16.png)

7. <span data-ttu-id="1b857-152">在一段時間後按一下 [**重新整理**，然後按一下 [瀏覽至儲存體帳戶的 [**移至資源**。</span><span class="sxs-lookup"><span data-stu-id="1b857-152">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![瀏覽至儲存體帳戶](media/FBCimage17.png)

8. <span data-ttu-id="1b857-154">在左側的導覽窗格中，按一下 [**便捷鍵**。</span><span class="sxs-lookup"><span data-stu-id="1b857-154">Click **Access keys** in the left navigation pane.</span></span>

    ![按一下 [便捷鍵](media/FBCimage18.png)

9. <span data-ttu-id="1b857-156">複製**連接字串**，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="1b857-156">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="1b857-157">您使用此建立 web 應用程式資源時。</span><span class="sxs-lookup"><span data-stu-id="1b857-157">You use this when creating a web app resource.</span></span>

    ![複製連接字串，並將它儲存](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="1b857-159">步驟 4： 在 Azure 中建立新的 web 應用程式資源</span><span class="sxs-lookup"><span data-stu-id="1b857-159">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="1b857-160">在 [**首頁**] 頁面在 Azure 入口網站中，按一下 [**建立資源\>每個項目\>Web 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1b857-160">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="1b857-161">在 [ **Web 應用程式**] 頁面上，按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="1b857-161">On the **Web app** page, click **Create**.</span></span> 

   ![建立新的 web 應用程式資源](media/FBCimage20.png)

2. <span data-ttu-id="1b857-163">填入詳細資料 （如下所示），然後再建立 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="1b857-163">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="1b857-164">請注意，您在 [**應用程式名稱**] 方塊中輸入的名稱，用於建立 Azure 應用程式服務的 URL;例如，fbconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="1b857-164">Note that the name that you enter in the **App name** box is used to create the Azure app service URL; for example, fbconnector.azurewebsites.net.</span></span>

   ![填入詳細資料，然後再建立 Web 應用程式](media/FBCimage21.png)

3. <span data-ttu-id="1b857-166">移至新建立的 web 應用程式資源，按一下 [**應用程式設定**]，請在左側的導覽窗格中。</span><span class="sxs-lookup"><span data-stu-id="1b857-166">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="1b857-167">應用程式設定] 下按一下 [新增新的設定，新增下列三個設定： 使用的值 （從複製到文字檔先前的步驟）：</span><span class="sxs-lookup"><span data-stu-id="1b857-167">Under Application settings, click Add new setting and add the following three settings: Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="1b857-168">**APISecretKey** – 您可以為密碼輸入任何值。</span><span class="sxs-lookup"><span data-stu-id="1b857-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="1b857-169">這用來存取在步驟 7 中的連接器 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="1b857-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="1b857-170">**StorageAccountConnectionString** -連接字串您在步驟 3 中建立 Azure 儲存體帳戶之後所複製的 Uri。</span><span class="sxs-lookup"><span data-stu-id="1b857-170">**StorageAccountConnectionString** — The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="1b857-171">**tenantId** – 您在步驟 2 中的 Azure Active Directory 中建立 Facebook 連接器應用程式之後複製您 Office 365 組織租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="1b857-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![輸入應用程式設定](media/FBCimage22.png)

4. <span data-ttu-id="1b857-173">**一般設定**] 下按一下 [**上**旁**Always On**。</span><span class="sxs-lookup"><span data-stu-id="1b857-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="1b857-174">按一下 [**儲存**] 頁面的頂端儲存應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="1b857-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![儲存應用程式設定](media/FBCimage23.png)

5. <span data-ttu-id="1b857-176">最後一個步驟是將連接器 app 原始程式碼上傳至 Azure 中您在步驟 1 中下載。</span><span class="sxs-lookup"><span data-stu-id="1b857-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="1b857-177">在網頁瀏覽器中，移至 https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="1b857-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="1b857-178">例如，如果您的 Azure 應用程式資源 （這在本節中的步驟 2 中所命名） 的名稱是**fbconnector**，然後您會移至https://fbconnector.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="1b857-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="1b857-179">拖放到此頁面 SampleConnector.zip （，您在步驟 1 中下載）。</span><span class="sxs-lookup"><span data-stu-id="1b857-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="1b857-180">將檔案上傳並部署成功後，看起來類似下列的螢幕擷取畫面] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="1b857-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![將拖放到此頁面 SampleConnector.zip](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="1b857-182">步驟 5： 註冊 Facebook 應用程式</span><span class="sxs-lookup"><span data-stu-id="1b857-182">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="1b857-183">移至 [ <https://developers.facebook.com>，登入之帳戶的組織的 Facebook 商務頁面、 使用的認證，然後按一下 [**新增新的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1b857-183">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![新增新的應用程式的 Facebook business 頁面](media/FBCimage25.png)

2. <span data-ttu-id="1b857-185">建立新的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="1b857-185">Create a new app ID.</span></span>

   ![建立新的應用程式識別碼](media/FBCimage26.png)

3. <span data-ttu-id="1b857-187">在左側的導覽窗格中，按一下 [**新增產品**]，然後按一下**Set Up**中 [ **Facebook 登入**] 磚。</span><span class="sxs-lookup"><span data-stu-id="1b857-187">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![按一下 [新增產品](media/FBCimage27.png)

4. <span data-ttu-id="1b857-189">在整合 Facebook 登入頁面上，按一下 [ **Web**]。</span><span class="sxs-lookup"><span data-stu-id="1b857-189">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![按一下 [Web] 上的整合 Facebook 登入頁面](media/FBCimage28.png)

5. <span data-ttu-id="1b857-191">新增 Azure 應用程式服務的 URL;例如`https://fbconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="1b857-191">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![新增 Azure 應用程式服務 URL](media/FBCimage29.png)

6. <span data-ttu-id="1b857-193">完成 [快速入門] 區段中的 Facebook 登入安裝程式。</span><span class="sxs-lookup"><span data-stu-id="1b857-193">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![完成 [快速入門] 區段](media/FBCimage30.png)

7. <span data-ttu-id="1b857-195">在左側的導覽窗格的 [ **Facebook 登入**，按一下 [**設定**]，並在**有效的 OAuth 重新導向 Uri** ] 方塊中新增的 OAuth 重新導向 URI。</span><span class="sxs-lookup"><span data-stu-id="1b857-195">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="1b857-196">使用格式**\<connectorserviceuri>/檢視/FacebookOAuth**、 其中 connectorserviceuri 的值是為您的組織; Azure 應用程式服務 URL例如， `https://fbconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="1b857-196">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![有效的 OAuth 重新導向 Uri 方塊中新增的 OAuth 重新導向 URI](media/FBCimage31.png)

8. <span data-ttu-id="1b857-198">在左側的導覽窗格中，按一下 [**新增產品**，然後按一下 [ **Webhooks。**</span><span class="sxs-lookup"><span data-stu-id="1b857-198">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="1b857-199">**頁面**下拉功能表中，按一下 [**頁面]**。</span><span class="sxs-lookup"><span data-stu-id="1b857-199">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![按一下 [新增產品，然後按一下 [\* \* Webhooks](media/FBCimage32.png)

9. <span data-ttu-id="1b857-201">新增 Webhooks 回呼 URL，並將確認語彙基元。</span><span class="sxs-lookup"><span data-stu-id="1b857-201">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="1b857-202">回呼的 URL，格式使用格式**<connectorserviceuri>/api/FbPageWebhook**、 其中 connectorserviceuri 的值是為您的組織; Azure 應用程式服務 URL例如`https://fbconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="1b857-202">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span> 

    <span data-ttu-id="1b857-203">驗證權杖應該類似強式密碼。</span><span class="sxs-lookup"><span data-stu-id="1b857-203">The verify token should similar to a strong password.</span></span> <span data-ttu-id="1b857-204">將驗證權杖複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="1b857-204">Copy the verify token to a text file or other storage location.</span></span>

        ![Add the verify token](media/FBCimage33.png)

10. <span data-ttu-id="1b857-205">測試和訂閱的端點摘要。</span><span class="sxs-lookup"><span data-stu-id="1b857-205">Test and subscribe to the endpoint for feed.</span></span>

    ![測試及訂閱的端點](media/FBCimage34.png)

11. <span data-ttu-id="1b857-207">新增隱私權 URL、 應用程式圖示和商業用途。</span><span class="sxs-lookup"><span data-stu-id="1b857-207">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="1b857-208">此外，將應用程式識別碼和應用程式密碼複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="1b857-208">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![新增隱私權 URL、 應用程式圖示和商業用途](media/FBCimage35.png)

12. <span data-ttu-id="1b857-210">將應用程式公開。</span><span class="sxs-lookup"><span data-stu-id="1b857-210">Make the app public.</span></span>

    ![公開應用程式](media/FBCimage36.png)

13. <span data-ttu-id="1b857-212">將使用者新增至系統管理員或測試人員角色。</span><span class="sxs-lookup"><span data-stu-id="1b857-212">Add user to the admin or tester role.</span></span>

    ![將使用者新增至系統管理員或測試人員角色](media/FBCimage37.png)

14. <span data-ttu-id="1b857-214">新增 [**網頁公用的內容存取**權限。</span><span class="sxs-lookup"><span data-stu-id="1b857-214">Add the **Page Public Content Access** permission.</span></span>

    ![dd] 頁面上的公用內容存取權限](media/FBCimage38.png)

15. <span data-ttu-id="1b857-216">新增管理頁面的權限。</span><span class="sxs-lookup"><span data-stu-id="1b857-216">Add Manage Pages permission.</span></span>

    ![新增管理頁面的權限](media/FBCimage39.png)

16. <span data-ttu-id="1b857-218">取得由 Facebook 檢閱應用程式。</span><span class="sxs-lookup"><span data-stu-id="1b857-218">Get the application reviewed by Facebook.</span></span>

    ![取得由 Facebook 檢閱應用程式](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="1b857-220">步驟 6： 設定連接器的 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="1b857-220">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="1b857-221">移至 https://\<AzureAppResourceName>.azurewebsites.net （其中 AzureAppResourceName 是您在步驟 4 中名為您 Azure 應用程式資源的名稱），例如，如果名稱為**fbconnector**，請移至`https://fbconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="1b857-221">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="1b857-222">應用程式的 [首頁] 頁面上看起來像下列螢幕擷取畫面中：</span><span class="sxs-lookup"><span data-stu-id="1b857-222">The home page of the app will look like the following screenshot:</span></span>

   ![移至您連接器 web app](media/FBCimage41.png)

2. <span data-ttu-id="1b857-224">按一下 [**設定**] 頁面中，會顯示號。</span><span class="sxs-lookup"><span data-stu-id="1b857-224">Click **Configure** to display a sign in page.</span></span>
 
   ![按一下 [設定] 頁面中，會顯示號](media/FBCimage42.png)

3. <span data-ttu-id="1b857-226">在租用戶識別碼] 方塊中，輸入或貼上您的租用戶識別碼 （您在步驟 2 中所取得）。</span><span class="sxs-lookup"><span data-stu-id="1b857-226">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="1b857-227">在 [密碼] 方塊中，輸入或貼上 APISecretKey （，您在步驟 2 中所取得），，然後按一下要顯示 [**設定詳細資料**] 頁面上**設定的組態設定**。</span><span class="sxs-lookup"><span data-stu-id="1b857-227">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![使用您的租用戶識別碼和密碼登入，然後移至設定詳細資料頁面](media/FBCimage43.png)

4. <span data-ttu-id="1b857-229">[**設定的詳細資訊**，請輸入下列組態設定</span><span class="sxs-lookup"><span data-stu-id="1b857-229">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="1b857-230">**Facebook 應用程式識別碼**– 您在步驟 5 中所取得的 Facebook 應用程式的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="1b857-230">**Facebook application ID** – The app ID for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="1b857-231">**Facebook 應用程式密碼**– 您在步驟 5 中所取得的 Facebook 應用程式的應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="1b857-231">**Facebook application secret** – The app secret for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="1b857-232">**Facebook webhooks 驗證權杖**– 您在步驟 5 中建立的驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="1b857-232">**Facebook webhooks verify token** – The verify token that you created in Step 5.</span></span>
   - <span data-ttu-id="1b857-233">**AAD 應用程式識別碼**– 您在步驟 2 中建立的 Azure Active Directory 應用程式的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="1b857-233">**AAD application ID** – The application ID for the Azure Active Directory app that you created in Step 2.</span></span>
   - <span data-ttu-id="1b857-234">**AAD 應用程式密碼**– 您在步驟 4 中建立的 APISecretKey 密碼的值。</span><span class="sxs-lookup"><span data-stu-id="1b857-234">**AAD application secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="1b857-235">**AAD 應用程式的 Uri** – AAD 應用程式在步驟 2; 中所取得的 Uri例如， `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`。</span><span class="sxs-lookup"><span data-stu-id="1b857-235">**AAD application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="1b857-236">**App 觀點檢測機碼**– 保留此方塊空白。</span><span class="sxs-lookup"><span data-stu-id="1b857-236">**App insights instrumentation key** – Leave this box blank.</span></span>

5. <span data-ttu-id="1b857-237">按一下 [**儲存**] 以儲存連接器設定。</span><span class="sxs-lookup"><span data-stu-id="1b857-237">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="1b857-238">步驟 7： 設立安全性 & 合規性中心中的自訂連接器</span><span class="sxs-lookup"><span data-stu-id="1b857-238">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="1b857-239">移至 [ <https://protection.office.com> ，然後按一下 [**資訊控管\>匯入\>封存協力廠商資料**。</span><span class="sxs-lookup"><span data-stu-id="1b857-239">Go to <https://protection.office.com> and then click **Information governance \> Import \> Archive third-party data**.</span></span>

   ![移至安全性與合規性中心，按一下 [控管 > 匯入 > 封存協力廠商資料的資訊](media/FBCimage44.png)

2.  <span data-ttu-id="1b857-241">按一下 [**新增連接器**]，然後按一下 [ **Facebook 頁面**。</span><span class="sxs-lookup"><span data-stu-id="1b857-241">Click **Add a connector** and then click **Facebook pages**.</span></span>

    ![新增 Facebook 連接器設定連接器](media/FBCimage46.png)

3.  <span data-ttu-id="1b857-243">在 [**新增連接器應用程式**] 頁面中，輸入下列資訊，然後按一下 [**驗證連接器**。</span><span class="sxs-lookup"><span data-stu-id="1b857-243">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="1b857-244">在第一個方塊中，輸入連接器名稱，例如**Facebook**。</span><span class="sxs-lookup"><span data-stu-id="1b857-244">In the first box, type a name for the connector, such as **Facebook**.</span></span>
    - <span data-ttu-id="1b857-245">在第二個方塊中，輸入或貼上您在步驟 4 中新增 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="1b857-245">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="1b857-246">在第三個方塊中，輸入或貼上的 Azure 應用程式服務 URL;例如`https://fbconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="1b857-246">In the third box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>
 
    <span data-ttu-id="1b857-247">成功驗證連接器之後，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="1b857-247">After the connector is successfully validated, click **Next**.</span></span>
    
    ![在成功驗證連接器之後，按 [下一步]](media/FBCimage47.png)

4.  <span data-ttu-id="1b857-249">按一下 [**登入與連接器應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1b857-249">Click **Login with Connector App**.</span></span>

    ![按一下 [登入與連接器應用程式](media/FBCimage45.png)

5. <span data-ttu-id="1b857-251">輸入或貼上 APISecretKey 一次，然後按一下 [**連接器服務的登入**。</span><span class="sxs-lookup"><span data-stu-id="1b857-251">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![輸入或貼上 APISecretKey，然後按一下 [登入] 按鈕](media/FBCimage48.png)

6. <span data-ttu-id="1b857-253">按一下 [**登入與 Facebook**。</span><span class="sxs-lookup"><span data-stu-id="1b857-253">Click **Login with Facebook**.</span></span>

   ![按一下 [\* \* 與 Facebook 的登入](media/FBCimage49.png)

7. <span data-ttu-id="1b857-255">在**登入 Facebook** ] 頁面上，使用登入認證之帳戶的組織的 Facebook 商務頁面。</span><span class="sxs-lookup"><span data-stu-id="1b857-255">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="1b857-256">請確定您指派給貴組織的 Facebook 商務頁面的管理員角色登入 Facebook 帳戶</span><span class="sxs-lookup"><span data-stu-id="1b857-256">Make sure the Facebook account that you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![登入 Facebook](media/FBCimage50.png)

8. <span data-ttu-id="1b857-258">按一下 [**選取頁面**，以選擇您想要在 Office 365 中封存的貴組織的業務頁面]。</span><span class="sxs-lookup"><span data-stu-id="1b857-258">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![按一下 [選取頁面，以顯示貴組織的業務頁面](media/FBCimage51.png)

9. <span data-ttu-id="1b857-260">受管理的 Facebook 帳戶，登入商務頁面清單隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="1b857-260">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="1b857-261">選取 [封存，然後按一下 [**儲存**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="1b857-261">Select the page to archive and then click **Save**.</span></span>

    ![選取您想要保存組織 business 頁面](media/FBCimage52.png)

10. <span data-ttu-id="1b857-263">按一下 [**完成**] 結束安裝程式的連接器服務應用程式]。</span><span class="sxs-lookup"><span data-stu-id="1b857-263">Click **Finish** to exit the setup of the connector service app.</span></span>

    ![按一下 [完成] 結束連接器服務應用程式](media/FBCimage53.png)

11. <span data-ttu-id="1b857-265">在 [**設定篩選器**] 頁面中，您可以套用篩選器來匯入 （和封存） 特定天數的項目。</span><span class="sxs-lookup"><span data-stu-id="1b857-265">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="1b857-266">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1b857-266">Click **Next**.</span></span>

    ![套用篩選器來匯入特定天數的項目](media/FBCimage54.png)

12. <span data-ttu-id="1b857-268">在 [**設定儲存體帳戶**] 頁面上，選取先前選取的 Facebook 商務頁面中的項目將會匯入至 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="1b857-268">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![指定 Office 365 信箱項目從 Facebook 匯入封存](media/FBCimage55.png)

13. <span data-ttu-id="1b857-270">檢閱您的設定，然後按一下 [**完成**] 以完成安全性 & 規範中心的連接器設定。</span><span class="sxs-lookup"><span data-stu-id="1b857-270">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![檢閱連接器設定](media/FBCimage56.png)

14. <span data-ttu-id="1b857-272">移至**封存協力廠商資料**頁面才能看見匯入程序的進度。</span><span class="sxs-lookup"><span data-stu-id="1b857-272">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![移至封存協力廠商資料] 頁面上，以追蹤匯入程序](media/FBCimage58.png)
