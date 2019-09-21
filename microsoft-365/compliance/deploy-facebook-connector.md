---
title: 部署到 Office 365 中的 Facebook 資料保存的連接器
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
ms.openlocfilehash: 1f5b0f241616cc95e79e80d054a8782f97c5887b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070853"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a><span data-ttu-id="28a69-104">部署到 Office 365 中的 Facebook 資料保存的連接器</span><span class="sxs-lookup"><span data-stu-id="28a69-104">Deploy a connector to archive Facebook data in Office 365</span></span>

<span data-ttu-id="28a69-105">本文包含的逐步程序來部署使用 Office 365 匯入服務 Facebook 商務頁面的資料匯入至 Office 365 的連接器。</span><span class="sxs-lookup"><span data-stu-id="28a69-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="28a69-106">此程序的高階概觀與部署的 Facebook 連接器所需的必要條件清單，請參閱[使用 Office 365 （預覽） 中的 Facebook 資料保存的範例連接器](archive-facebook-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="28a69-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use a sample connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="28a69-107">步驟 1： 下載套件</span><span class="sxs-lookup"><span data-stu-id="28a69-107">Step 1: Download the package</span></span>

<span data-ttu-id="28a69-108">從 [版本] 區段中，GitHub 儲存機制中下載預先建立的套件<https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>。</span><span class="sxs-lookup"><span data-stu-id="28a69-108">Download the prebuilt package from the Release section in the GitHub repository at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="28a69-109">在 [最新版本中，下載 zip 檔名為**SampleConnector.zip**。</span><span class="sxs-lookup"><span data-stu-id="28a69-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="28a69-110">您將此 zip 檔案上傳到步驟 4 中的 Azure。</span><span class="sxs-lookup"><span data-stu-id="28a69-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="28a69-111">步驟 2： 在 Azure Active Directory 中建立的應用程式</span><span class="sxs-lookup"><span data-stu-id="28a69-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="28a69-112">移至 [<https://portal.azure.com>並使用 Office 365 全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="28a69-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![在 [AAD 中建立應用程式](media/FBCimage1.png)

2. <span data-ttu-id="28a69-114">在左側的導覽窗格中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="28a69-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![](media/FBCimage2.png)

3. <span data-ttu-id="28a69-115">在左側的導覽窗格中，按一下 [**應用程式註冊 （預覽）** ，然後按一下 [**新增註冊**。</span><span class="sxs-lookup"><span data-stu-id="28a69-115">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![](media/FBCimage3.png)

4. <span data-ttu-id="28a69-116">註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="28a69-116">Register the application.</span></span> <span data-ttu-id="28a69-117">[重新導向 URI，選取 Web 應用程式類型] 下拉式清單中，然後輸入<https://portal.azure.com>URI] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="28a69-117">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/FBCimage4.png)

5. <span data-ttu-id="28a69-118">複製 **（用戶端） 的應用程式識別碼**] 及 [**目錄 （承租人） 識別碼**，並將它們儲存到文字檔或其他安全的位置。</span><span class="sxs-lookup"><span data-stu-id="28a69-118">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="28a69-119">您在稍後步驟使用這些識別碼。</span><span class="sxs-lookup"><span data-stu-id="28a69-119">You use these IDs in later steps.</span></span>

   ![](media/FBCimage5.png)

6. <span data-ttu-id="28a69-120">移至**新的應用程式的憑證 & 機密資料**</span><span class="sxs-lookup"><span data-stu-id="28a69-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![](media/FBCimage6.png)

7. <span data-ttu-id="28a69-121">按一下 [**新的用戶端密碼**</span><span class="sxs-lookup"><span data-stu-id="28a69-121">Click **New client secret**</span></span>

   ![](media/FBCimage7.png)

8. <span data-ttu-id="28a69-122">建立新的密碼。</span><span class="sxs-lookup"><span data-stu-id="28a69-122">Create a new secret.</span></span> <span data-ttu-id="28a69-123">在 [描述] 方塊中，輸入密碼，然後選擇的到期時間。</span><span class="sxs-lookup"><span data-stu-id="28a69-123">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![](media/FBCimage8.png)

9. <span data-ttu-id="28a69-124">複製密碼的值，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="28a69-124">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="28a69-125">這是您在稍後步驟使用的 AAD 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="28a69-125">This is the AAD application secret that you use in later steps.</span></span>

   ![](media/FBCimage9.png)

10. <span data-ttu-id="28a69-126">移至**資訊清單**，然後複製 identifierUris （這也稱為 AAD 應用程式的 Uri） 以反白顯示下列螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="28a69-126">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="28a69-127">複製到文字檔或其他儲存位置的 AAD 應用程式的 Uri。</span><span class="sxs-lookup"><span data-stu-id="28a69-127">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="28a69-128">您在步驟 6 中使用。</span><span class="sxs-lookup"><span data-stu-id="28a69-128">You use it in Step 6.</span></span>

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="28a69-129">步驟 3： 建立 Azure 儲存體帳戶</span><span class="sxs-lookup"><span data-stu-id="28a69-129">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="28a69-130">移至 Azure 的首頁上，為您的組織。</span><span class="sxs-lookup"><span data-stu-id="28a69-130">Go to the Azure home page for your organization.</span></span>

    ![](media/FBCimage11.png)

2. <span data-ttu-id="28a69-131">按一下 [**建立資源**及它們在 [搜尋] 方塊中輸入**儲存體帳戶**。</span><span class="sxs-lookup"><span data-stu-id="28a69-131">Click **Create a resource** and they type **storage account** in the search box.</span></span>

    ![](media/FBCimage12.png)

3. <span data-ttu-id="28a69-132">按一下 [**儲存**]，然後按一下 [**儲存體帳戶**。</span><span class="sxs-lookup"><span data-stu-id="28a69-132">Click **Storage**, and then click **Storage account**.</span></span>

    ![](media/FBCimage13.png)

4. <span data-ttu-id="28a69-133">在 [**建立儲存體帳戶**] 頁面上，在 [訂閱] 方塊中，選取**Pay-As-You-Go**或取決於哪些類型的 Azure 訂用帳戶必須**免費試用版**。</span><span class="sxs-lookup"><span data-stu-id="28a69-133">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="28a69-134">然後選取或建立資源群組。</span><span class="sxs-lookup"><span data-stu-id="28a69-134">Then select or create a resource group.</span></span>

    ![](media/FBCimage14.png)

5. <span data-ttu-id="28a69-135">輸入儲存體帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="28a69-135">Type a name for the storage account.</span></span>

    ![](media/FBCimage15.png)

6. <span data-ttu-id="28a69-136">檢閱，然後按一下 [**建立**]，以建立儲存體帳戶。</span><span class="sxs-lookup"><span data-stu-id="28a69-136">Review and then click **Create** to create the storage account.</span></span>

    ![](media/FBCimage16.png)

7. <span data-ttu-id="28a69-137">在一段時間後按一下 [**重新整理**，然後按一下 [瀏覽至儲存體帳戶的 [**移至資源**。</span><span class="sxs-lookup"><span data-stu-id="28a69-137">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![](media/FBCimage17.png)

8. <span data-ttu-id="28a69-138">在左側的導覽窗格中，按一下 [**便捷鍵**。</span><span class="sxs-lookup"><span data-stu-id="28a69-138">Click **Access keys** in the left navigation pane.</span></span>

    ![](media/FBCimage18.png)

9. <span data-ttu-id="28a69-139">複製**連接字串**，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="28a69-139">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="28a69-140">您使用此建立 web 應用程式資源時。</span><span class="sxs-lookup"><span data-stu-id="28a69-140">You use this when creating a web app resource.</span></span>

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="28a69-141">步驟 4： 在 Azure 中建立新的 web 應用程式資源</span><span class="sxs-lookup"><span data-stu-id="28a69-141">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="28a69-142">在 [**首頁**] 頁面在 Azure 入口網站中，按一下 [**建立資源\>每個項目\>Web 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="28a69-142">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="28a69-143">在 [ **Web 應用程式**] 頁面上，按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="28a69-143">On the **Web app** page, click **Create**.</span></span> 

   ![](media/FBCimage20.png)

2. <span data-ttu-id="28a69-144">填入詳細資料 （如下所示），然後再建立 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="28a69-144">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="28a69-145">請注意，您在 [**應用程式名稱**] 方塊中輸入的名稱，用於建立 Azure 應用程式服務的 URL;例如，fbconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="28a69-145">Note that the name that you enter in the **App name** box is used to create the Azure app service URL; for example, fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage21.png)

3. <span data-ttu-id="28a69-146">移至新建立的 web 應用程式資源，按一下 [**應用程式設定**]，請在左側的導覽窗格中。</span><span class="sxs-lookup"><span data-stu-id="28a69-146">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="28a69-147">應用程式設定] 下按一下 [新增新的設定，新增下列三個設定： 使用的值 （從複製到文字檔先前的步驟）：</span><span class="sxs-lookup"><span data-stu-id="28a69-147">Under Application settings, click Add new setting and add the following three settings: Use the values (that you copied to the text file from the previous steps):</span></span> 

    <span data-ttu-id="28a69-148">– **APISecretKey** – 您可以為密碼輸入任何值。</span><span class="sxs-lookup"><span data-stu-id="28a69-148">– **APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="28a69-149">這用來存取在步驟 7 中的連接器 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="28a69-149">This is used to access the connector web app in Step 7.</span></span>

    <span data-ttu-id="28a69-150">– \* \* StorageAccountConnectionString-連接字串您在步驟 3 中建立 Azure 儲存體帳戶之後所複製的 Uri。</span><span class="sxs-lookup"><span data-stu-id="28a69-150">– \*\*StorageAccountConnectionString — The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    <span data-ttu-id="28a69-151">Office 365 組織，您在步驟 2 中的 Azure Active Directory 中建立 Facebook 連接器應用程式之後複製 – **tenantId** – 租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="28a69-151">– **tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/FBCimage22.png)

4. <span data-ttu-id="28a69-152">**一般設定**] 下按一下 [**上**旁**Always On**。</span><span class="sxs-lookup"><span data-stu-id="28a69-152">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="28a69-153">按一下 [**儲存**] 頁面的頂端儲存應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="28a69-153">Click **Save** at the top of the page to save application settings.</span></span>

   ![](media/FBCimage23.png)

5. <span data-ttu-id="28a69-154">最後一個步驟是將連接器 app 原始程式碼上傳至 Azure 中您在步驟 1 中下載。</span><span class="sxs-lookup"><span data-stu-id="28a69-154">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="28a69-155">在網頁瀏覽器中，移至 https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="28a69-155">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="28a69-156">例如，如果您的 Azure 應用程式資源 （這在本節中的步驟 2 中所命名） 的名稱是**fbconnector**，然後您會移至https://fbconnector.scm.azurewebsites.net/ZipDeployUi。</span><span class="sxs-lookup"><span data-stu-id="28a69-156">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="28a69-157">拖放到此頁面 SampleConnector.zip （，您在步驟 1 中下載）。</span><span class="sxs-lookup"><span data-stu-id="28a69-157">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="28a69-158">將檔案上傳並部署成功後，看起來類似下列的螢幕擷取畫面] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="28a69-158">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="28a69-159">步驟 5： 註冊 Facebook 應用程式</span><span class="sxs-lookup"><span data-stu-id="28a69-159">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="28a69-160">移至 [ <https://developers.facebook.com>，登入之帳戶的組織的 Facebook 商務頁面、 使用的認證，然後按一下 [**新增新的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="28a69-160">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![](media/FBCimage25.png)

2. <span data-ttu-id="28a69-161">建立新的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="28a69-161">Create a new app ID.</span></span>

   ![](media/FBCimage26.png)

3. <span data-ttu-id="28a69-162">在左側的導覽窗格中，按一下 [**新增產品**]，然後按一下**Set Up**中 [ **Facebook 登入**] 磚。</span><span class="sxs-lookup"><span data-stu-id="28a69-162">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![](media/FBCimage27.png)

4. <span data-ttu-id="28a69-163">在整合 Facebook 登入頁面上，按一下 [ **Web**]。</span><span class="sxs-lookup"><span data-stu-id="28a69-163">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![](media/FBCimage28.png)

5. <span data-ttu-id="28a69-164">新增 Azure 應用程式服務的 URL;例如https://fbconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="28a69-164">Add the Azure app service URL; for example https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage29.png)

6. <span data-ttu-id="28a69-165">完成 [快速入門] 區段中的 Facebook 登入安裝程式。</span><span class="sxs-lookup"><span data-stu-id="28a69-165">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![](media/FBCimage30.png)

7. <span data-ttu-id="28a69-166">在左側的導覽窗格的 [ **Facebook 登入**，按一下 [**設定**]，並在**有效的 OAuth 重新導向 Uri** ] 方塊中新增的 OAuth 重新導向 URI。</span><span class="sxs-lookup"><span data-stu-id="28a69-166">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="28a69-167">使用格式**\<connectorserviceuri>/檢視/FacebookOAuth**、 其中 connectorserviceuri 的值是為您的組織; Azure 應用程式服務 URL例如， https://fbconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="28a69-167">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage31.png)

8. <span data-ttu-id="28a69-168">在左側的導覽窗格中，按一下 [**新增產品**，然後按一下 [ **Webhooks。**</span><span class="sxs-lookup"><span data-stu-id="28a69-168">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="28a69-169">**頁面**下拉功能表中，按一下 [**頁面]**。</span><span class="sxs-lookup"><span data-stu-id="28a69-169">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![](media/FBCimage32.png)

9. <span data-ttu-id="28a69-170">新增 Webhooks 回呼 URL，並將確認語彙基元。</span><span class="sxs-lookup"><span data-stu-id="28a69-170">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="28a69-171">回呼的 URL，格式使用格式**<connectorserviceuri>/api/FbPageWebhook**、 其中 connectorserviceuri 的值是為您的組織; Azure 應用程式服務 URL例如https://fbconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="28a69-171">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example https://fbconnector.azurewebsites.net.</span></span> 

    <span data-ttu-id="28a69-172">驗證權杖應該類似強式密碼。</span><span class="sxs-lookup"><span data-stu-id="28a69-172">The verify token should similar to a strong password.</span></span> <span data-ttu-id="28a69-173">將驗證權杖複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="28a69-173">Copy the verify token to a text file or other storage location.</span></span>

     ![](media/FBCimage33.png)

10. <span data-ttu-id="28a69-174">測試和訂閱的端點摘要。</span><span class="sxs-lookup"><span data-stu-id="28a69-174">Test and subscribe to the endpoint for feed.</span></span>

    ![](media/FBCimage34.png)

11. <span data-ttu-id="28a69-175">新增隱私權 URL、 應用程式圖示和商業用途。</span><span class="sxs-lookup"><span data-stu-id="28a69-175">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="28a69-176">此外，將應用程式識別碼和應用程式密碼複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="28a69-176">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![](media/FBCimage35.png)

12. <span data-ttu-id="28a69-177">將應用程式公開。</span><span class="sxs-lookup"><span data-stu-id="28a69-177">Make the app public.</span></span>

    ![](media/FBCimage36.png)

13. <span data-ttu-id="28a69-178">將使用者新增至系統管理員或測試人員角色。</span><span class="sxs-lookup"><span data-stu-id="28a69-178">Add user to the admin or tester role.</span></span>

    ![](media/FBCimage37.png)

14. <span data-ttu-id="28a69-179">新增 [**網頁公用的內容存取**權限。</span><span class="sxs-lookup"><span data-stu-id="28a69-179">Add the **Page Public Content Access** permission.</span></span>

    ![](media/FBCimage38.png)

15. <span data-ttu-id="28a69-180">新增管理頁面的權限。</span><span class="sxs-lookup"><span data-stu-id="28a69-180">Add Manage Pages permission.</span></span>

    ![](media/FBCimage39.png)

16. <span data-ttu-id="28a69-181">取得由 Facebook 檢閱應用程式。</span><span class="sxs-lookup"><span data-stu-id="28a69-181">Get the application reviewed by Facebook.</span></span>

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="28a69-182">步驟 6： 設定連接器的 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="28a69-182">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="28a69-183">移至 https://\<AzureAppResourceName>.azurewebsites.net （其中 AzureAppResourceName 是您在步驟 4 中名為您 Azure 應用程式資源的名稱），例如，如果名稱為**fbconnector**，請移至https://fbconnector.azurewebsites.net。</span><span class="sxs-lookup"><span data-stu-id="28a69-183">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to https://fbconnector.azurewebsites.net.</span></span> <span data-ttu-id="28a69-184">應用程式的 [首頁] 頁面上看起來像下列螢幕擷取畫面中：</span><span class="sxs-lookup"><span data-stu-id="28a69-184">The home page of the app will look like the following screenshot:</span></span>


   ![](media/FBCimage41.png)

2. <span data-ttu-id="28a69-185">按一下 [**設定**] 頁面中，會顯示號。</span><span class="sxs-lookup"><span data-stu-id="28a69-185">Click **Configure** to display a sign in page.</span></span>
 
   ![](media/FBCimage42.png)

3. <span data-ttu-id="28a69-186">在租用戶識別碼] 方塊中，輸入或貼上您的租用戶識別碼 （您在步驟 2 中所取得）。</span><span class="sxs-lookup"><span data-stu-id="28a69-186">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="28a69-187">在 [密碼] 方塊中，輸入或貼上 APISecretKey （，您在步驟 2 中所取得），，然後按一下要顯示 [**設定詳細資料**] 頁面上**設定的組態設定**。</span><span class="sxs-lookup"><span data-stu-id="28a69-187">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![](media/FBCimage43.png)


4. <span data-ttu-id="28a69-188">[**設定的詳細資訊**，請輸入下列組態設定</span><span class="sxs-lookup"><span data-stu-id="28a69-188">Under **Configuration Details**, enter the following configuration settings</span></span> 

   <span data-ttu-id="28a69-189">您在步驟 5 中所取得的 Facebook 應用程式 – **Facebook 應用程式識別碼**– 應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="28a69-189">– **Facebook application ID** – The app ID for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="28a69-190">– **Facebook 應用程式密碼**– 您在步驟 5 中所取得的 Facebook 應用程式的應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="28a69-190">– **Facebook application secret** – The app secret for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="28a69-191">您在步驟 5 中建立的 – **Facebook webhooks 驗證權杖**– 驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="28a69-191">– **Facebook webhooks verify token** – The verify token that you created in Step 5.</span></span>
   <span data-ttu-id="28a69-192">您在步驟 2 中建立的 Azure Active Directory 應用程式 – **AAD 應用程式識別碼**– 應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="28a69-192">– **AAD application ID** – The application ID for the Azure Active Directory app that you created in Step 2.</span></span>
   <span data-ttu-id="28a69-193">– **AAD 應用程式密碼**– 您在步驟 4 中建立的 APISecretKey 密碼的值。</span><span class="sxs-lookup"><span data-stu-id="28a69-193">– **AAD application secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   <span data-ttu-id="28a69-194">在 [步驟 2; 的 – **AAD 應用程式的 Uri** – AAD 應用程式的 Uri 取得例如， https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213。</span><span class="sxs-lookup"><span data-stu-id="28a69-194">– **AAD application Uri** – The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   <span data-ttu-id="28a69-195">– **App 觀點檢測機碼**– 將保留此方塊空白。</span><span class="sxs-lookup"><span data-stu-id="28a69-195">– **App insights instrumentation key** – Leave this box blank.</span></span>

5. <span data-ttu-id="28a69-196">按一下 [**儲存**] 以儲存連接器設定。</span><span class="sxs-lookup"><span data-stu-id="28a69-196">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="28a69-197">步驟 7： 設立安全性 & 合規性中心中的自訂連接器</span><span class="sxs-lookup"><span data-stu-id="28a69-197">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="28a69-198">移至 [ <https://protection.office.com> ，然後按一下 [**資料控管\>匯入\>封存協力廠商資料**。</span><span class="sxs-lookup"><span data-stu-id="28a69-198">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

   ![](media/FBCimage44.png)

2.  <span data-ttu-id="28a69-199">按一下 [**新增連接器**]，然後按一下 [ **Facebook 頁面**。</span><span class="sxs-lookup"><span data-stu-id="28a69-199">Click **Add a connector** and then click **Facebook pages**.</span></span>

    ![](media/FBCimage46.png)

3.  <span data-ttu-id="28a69-200">在 [**新增連接器應用程式**] 頁面中，輸入下列資訊，然後按一下 [**驗證連接器**。</span><span class="sxs-lookup"><span data-stu-id="28a69-200">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    <span data-ttu-id="28a69-201">– 在第一個方塊中，輸入連接器名稱，例如**Facebook**。</span><span class="sxs-lookup"><span data-stu-id="28a69-201">– In the first box, type a name for the connector, such as **Facebook**.</span></span>
    <span data-ttu-id="28a69-202">– 在第二個方塊中，輸入或貼上您在步驟 4 中新增 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="28a69-202">– In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    <span data-ttu-id="28a69-203">– 在第三個方塊中，輸入或貼上的 Azure 應用程式服務 URL;例如**https://fbconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="28a69-203">– In the third box, type or paste the Azure app service URL; for example **https://fbconnector.azurewebsites.net**.</span></span>
 
    <span data-ttu-id="28a69-204">成功驗證連接器之後，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="28a69-204">After the connector is successfully validated, click **Next**.</span></span>
    
    ![](media/FBCimage47.png)

4.  <span data-ttu-id="28a69-205">按一下 [**登入與連接器應用程式**。</span><span class="sxs-lookup"><span data-stu-id="28a69-205">Click **Login with Connector App**.</span></span>

    ![](media/FBCimage45.png)

5. <span data-ttu-id="28a69-206">輸入或貼上 APISecretKey 一次，然後按一下 [**連接器服務的登入**。</span><span class="sxs-lookup"><span data-stu-id="28a69-206">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/FBCimage48.png)


6. <span data-ttu-id="28a69-207">按一下 [**與 Facebook 的登入。**</span><span class="sxs-lookup"><span data-stu-id="28a69-207">Click **Login with Facebook.**</span></span>

   ![](media/FBCimage49.png)

7. <span data-ttu-id="28a69-208">在**登入 Facebook** ] 頁面上，使用登入認證之帳戶的組織的 Facebook 商務頁面。</span><span class="sxs-lookup"><span data-stu-id="28a69-208">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="28a69-209">請確定您指派給貴組織的 Facebook 商務頁面的管理員角色登入 Facebook 帳戶</span><span class="sxs-lookup"><span data-stu-id="28a69-209">Make sure the Facebook account that you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![](media/FBCimage50.png)

8. <span data-ttu-id="28a69-210">按一下 [**選取頁面**，以選擇您想要在 Office 365 中封存的貴組織的業務頁面]。</span><span class="sxs-lookup"><span data-stu-id="28a69-210">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![](media/FBCimage51.png)

9. <span data-ttu-id="28a69-211">受管理的 Facebook 帳戶，登入商務頁面清單隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="28a69-211">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="28a69-212">選取 [封存，然後按一下 [**儲存**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="28a69-212">Select the page to archive and then click **Save**.</span></span>

    ![](media/FBCimage52.png)

10. <span data-ttu-id="28a69-213">按一下 [**準備**結束的連接器服務應用程式設定]。</span><span class="sxs-lookup"><span data-stu-id="28a69-213">Click **prepare** to exit the setup of the connector service app.</span></span>

    ![](media/FBCimage53.png)

11. <span data-ttu-id="28a69-214">在 [**設定篩選器**] 頁面中，您可以套用篩選器來匯入 （和封存） 特定天數的項目。</span><span class="sxs-lookup"><span data-stu-id="28a69-214">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="28a69-215">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28a69-215">Click **Next**.</span></span>

    ![](media/FBCimage54.png)

12. <span data-ttu-id="28a69-216">在 [**設定儲存體帳戶**] 頁面上，選取先前選取的 Facebook 商務頁面中的項目將會匯入至 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="28a69-216">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![](media/FBCimage55.png)

13. <span data-ttu-id="28a69-217">檢閱您的設定，然後按一下 [**完成**] 以完成安全性 & 規範中心的連接器設定。</span><span class="sxs-lookup"><span data-stu-id="28a69-217">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/FBCimage56.png)

14. <span data-ttu-id="28a69-218">移至**封存協力廠商資料**頁面才能看見匯入程序的進度。</span><span class="sxs-lookup"><span data-stu-id="28a69-218">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/FBCimage58.png)
