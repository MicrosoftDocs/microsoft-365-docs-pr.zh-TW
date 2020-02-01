---
title: 部署封存的頁面 Facebook 商務資料的連接器
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
description: 系統管理員可以設定原生的連接器，以匯入並封存至 Microsoft 365 的 Facebook 商務頁面。 此資料會匯入至 Microsoft 365 之後，您可以使用合規性功能，例如合法持有、 內容搜尋和保留原則來管理您的組織 Facebook 資料的控管。
ms.openlocfilehash: 22810b377abf3ed30c53bab2cd27b970a5dcd62f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595298"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="49795-104">部署封存的頁面 Facebook 商務資料的連接器</span><span class="sxs-lookup"><span data-stu-id="49795-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="49795-105">本文包含部署 Facebook 商務頁面的資料匯入至 Microsoft 365 使用 Microsoft 365 匯入服務的連接器的逐步程序。</span><span class="sxs-lookup"><span data-stu-id="49795-105">This article contains the step-by-step process to deploy a connector that uses the Microsoft 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="49795-106">此程序的高階概觀與部署的 Facebook 連接器所需的必要條件清單，請參閱[設定連接器，以封存 Facebook 資料](archive-facebook-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="49795-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="49795-107">步驟 1: Azure Active Directory 中建立的應用程式</span><span class="sxs-lookup"><span data-stu-id="49795-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="49795-108">移至 [<https://portal.azure.com>並使用 Office 365 全域系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="49795-108">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![在 [AAD 中建立應用程式](media/FBCimage1.png)

2. <span data-ttu-id="49795-110">在左側的導覽窗格中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="49795-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![按一下 [Azure Active Directory](media/FBCimage2.png)

3. <span data-ttu-id="49795-112">在左側的導覽窗格中，按一下 [**應用程式註冊 （預覽）** ，然後按一下 [**新增註冊**。</span><span class="sxs-lookup"><span data-stu-id="49795-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![按一下 [\* \* 應用程式註冊 （預覽） \* *，然後按一下 [* \* 新註冊 \* \*](media/FBCimage3.png)

4. <span data-ttu-id="49795-114">註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="49795-114">Register the application.</span></span> <span data-ttu-id="49795-115">[重新導向 URI，選取 Web 應用程式類型] 下拉式清單中，然後輸入<https://portal.azure.com>URI] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="49795-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![註冊應用程式](media/FBCimage4.png)

5. <span data-ttu-id="49795-117">複製 **（用戶端） 的應用程式識別碼**] 及 [**目錄 （承租人） 識別碼**，並將它們儲存到文字檔或其他安全的位置。</span><span class="sxs-lookup"><span data-stu-id="49795-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="49795-118">您在稍後步驟使用這些識別碼。</span><span class="sxs-lookup"><span data-stu-id="49795-118">You use these IDs in later steps.</span></span>

   ![複製應用程式識別碼] 及 [目錄識別碼，並將其儲存](media/FBCimage5.png)

6. <span data-ttu-id="49795-120">移至**新的應用程式的憑證 & 機密資料**</span><span class="sxs-lookup"><span data-stu-id="49795-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![移至新的應用程式的憑證 & 機密資料](media/FBCimage6.png)

7. <span data-ttu-id="49795-122">按一下 [**新的用戶端密碼**</span><span class="sxs-lookup"><span data-stu-id="49795-122">Click **New client secret**</span></span>

   ![按一下 [新的用戶端密碼](media/FBCimage7.png)

8. <span data-ttu-id="49795-124">建立新的密碼。</span><span class="sxs-lookup"><span data-stu-id="49795-124">Create a new secret.</span></span> <span data-ttu-id="49795-125">在 [描述] 方塊中，輸入密碼，然後選擇的到期時間。</span><span class="sxs-lookup"><span data-stu-id="49795-125">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![輸入密碼，然後選擇 [的到期時間](media/FBCimage8.png)

9. <span data-ttu-id="49795-127">複製密碼的值，並將它儲存到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="49795-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="49795-128">這是您在稍後步驟使用的 AAD 應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="49795-128">This is the AAD application secret that you use in later steps.</span></span>

   ![複製密碼的值，並將它儲存](media/FBCimage9.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="49795-130">步驟 2： 部署至您的 Azure 帳戶從 GitHub 連接器 」 的 web 服務</span><span class="sxs-lookup"><span data-stu-id="49795-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="49795-131">移至[這個 GitHub 網站](https://github.com/microsoft/m365-sample-connector-csharp-aspnet)，然後按一下 [**部署至 Azure**。</span><span class="sxs-lookup"><span data-stu-id="49795-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![按一下 [部署至 Azure](media/FBCGithubApp.png)

2. <span data-ttu-id="49795-133">按一下 [**部署至 Azure**之後，您將會重新導向至自訂的範本] 頁面上使用 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="49795-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="49795-134">填入的**基本概念**和**設定**詳細資料，然後按一下 [**購買**。</span><span class="sxs-lookup"><span data-stu-id="49795-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

    - <span data-ttu-id="49795-135">**訂閱：** 選取您想要部署 Facebook 商務頁面連接器 web 服務，以您 Azure 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="49795-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>
    
    - <span data-ttu-id="49795-136">**資源群組：** 選擇或建立新的資源群組。</span><span class="sxs-lookup"><span data-stu-id="49795-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="49795-137">資源群組是保留 Azure 解決方案的相關的資源的容器。</span><span class="sxs-lookup"><span data-stu-id="49795-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="49795-138">**位置：** 選擇的位置。</span><span class="sxs-lookup"><span data-stu-id="49795-138">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="49795-139">**Web 應用程式名稱：** Web 應用程式提供連接器的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="49795-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="49795-140">對名稱必須是長度為 3 並 18 個字元之間。</span><span class="sxs-lookup"><span data-stu-id="49795-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="49795-141">此名稱用來建立 Azure 應用程式服務的 URL;例如，如果您提供**fbconnector**的 Web 應用程式名稱然後 Azure 應用程式服務的 URL 將會是**fbconnector.azurewebsites.net**。</span><span class="sxs-lookup"><span data-stu-id="49795-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="49795-142">**tenantId:** 您在步驟 1 中的 Azure Active Directory 中建立 Facebook 連接器應用程式之後複製您 Microsoft 365 組織租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="49795-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="49795-143">**APISecretKey:** 您可以為密碼輸入任何值。</span><span class="sxs-lookup"><span data-stu-id="49795-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="49795-144">這用來存取在步驟 5 中的連接器 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="49795-144">This is used to access the connector web app in Step 5.</span></span>
   
     ![按一下 [建立資源] 和 [類型儲存體帳戶](media/FBCimage12.png)

3. <span data-ttu-id="49795-146">部署成功後，看起來類似下列的螢幕擷取畫面] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="49795-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

     ![按一下儲存，然後按一下 [儲存體帳戶](media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="49795-148">步驟 3： 註冊 Facebook 應用程式</span><span class="sxs-lookup"><span data-stu-id="49795-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="49795-149">移至 [ <https://developers.facebook.com>，登入之帳戶的組織的 Facebook 商務頁面、 使用的認證，然後按一下 [**新增新的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="49795-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![新增新的應用程式的 Facebook business 頁面](media/FBCimage25.png)

2. <span data-ttu-id="49795-151">建立新的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="49795-151">Create a new app ID.</span></span>

   ![建立新的應用程式識別碼](media/FBCimage26.png)

3. <span data-ttu-id="49795-153">在左側的導覽窗格中，按一下 [**新增產品**]，然後按一下**Set Up**中 [ **Facebook 登入**] 磚。</span><span class="sxs-lookup"><span data-stu-id="49795-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![按一下 [新增產品](media/FBCimage27.png)

4. <span data-ttu-id="49795-155">在整合 Facebook 登入頁面上，按一下 [ **Web**]。</span><span class="sxs-lookup"><span data-stu-id="49795-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![按一下 [Web] 上的整合 Facebook 登入頁面](media/FBCimage28.png)

5. <span data-ttu-id="49795-157">新增 Azure 應用程式服務的 URL;例如`https://fbconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="49795-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![新增 Azure 應用程式服務 URL](media/FBCimage29.png)

6. <span data-ttu-id="49795-159">完成 [快速入門] 區段中的 Facebook 登入安裝程式。</span><span class="sxs-lookup"><span data-stu-id="49795-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![完成 [快速入門] 區段](media/FBCimage30.png)

7. <span data-ttu-id="49795-161">在左側的導覽窗格的 [ **Facebook 登入**，按一下 [**設定**]，並在**有效的 OAuth 重新導向 Uri** ] 方塊中新增的 OAuth 重新導向 URI。</span><span class="sxs-lookup"><span data-stu-id="49795-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="49795-162">使用格式**\<connectorserviceuri>/檢視/FacebookOAuth**、 其中 connectorserviceuri 的值是為您的組織; Azure 應用程式服務 URL例如， `https://fbconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="49795-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![有效的 OAuth 重新導向 Uri 方塊中新增的 OAuth 重新導向 URI](media/FBCimage31.png)

8. <span data-ttu-id="49795-164">在左側的導覽窗格中，按一下 [**新增產品**，然後按一下 [ **Webhooks。**</span><span class="sxs-lookup"><span data-stu-id="49795-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="49795-165">**頁面**下拉功能表中，按一下 [**頁面]**。</span><span class="sxs-lookup"><span data-stu-id="49795-165">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![按一下 [新增產品，然後按一下 [\* \* Webhooks](media/FBCimage32.png)

9. <span data-ttu-id="49795-167">新增 Webhooks 回呼 URL，並將確認語彙基元。</span><span class="sxs-lookup"><span data-stu-id="49795-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="49795-168">回呼的 URL，格式使用格式**<connectorserviceuri>/api/FbPageWebhook**、 其中 connectorserviceuri 的值是為您的組織; Azure 應用程式服務 URL例如`https://fbconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="49795-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span> 

    <span data-ttu-id="49795-169">驗證權杖應該類似強式密碼。</span><span class="sxs-lookup"><span data-stu-id="49795-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="49795-170">將驗證權杖複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="49795-170">Copy the verify token to a text file or other storage location.</span></span>

        ![Add the verify token](media/FBCimage33.png)

10. <span data-ttu-id="49795-171">測試和訂閱的端點摘要。</span><span class="sxs-lookup"><span data-stu-id="49795-171">Test and subscribe to the endpoint for feed.</span></span>

    ![測試及訂閱的端點](media/FBCimage34.png)

11. <span data-ttu-id="49795-173">新增隱私權 URL、 應用程式圖示和商業用途。</span><span class="sxs-lookup"><span data-stu-id="49795-173">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="49795-174">此外，將應用程式識別碼和應用程式密碼複製到文字檔或其他儲存位置。</span><span class="sxs-lookup"><span data-stu-id="49795-174">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![新增隱私權 URL、 應用程式圖示和商業用途](media/FBCimage35.png)

12. <span data-ttu-id="49795-176">將應用程式公開。</span><span class="sxs-lookup"><span data-stu-id="49795-176">Make the app public.</span></span>

    ![公開應用程式](media/FBCimage36.png)

13. <span data-ttu-id="49795-178">將使用者新增至系統管理員或測試人員角色。</span><span class="sxs-lookup"><span data-stu-id="49795-178">Add user to the admin or tester role.</span></span>

    ![將使用者新增至系統管理員或測試人員角色](media/FBCimage37.png)

14. <span data-ttu-id="49795-180">新增 [**網頁公用的內容存取**權限。</span><span class="sxs-lookup"><span data-stu-id="49795-180">Add the **Page Public Content Access** permission.</span></span>

    ![dd] 頁面上的公用內容存取權限](media/FBCimage38.png)

15. <span data-ttu-id="49795-182">新增管理頁面的權限。</span><span class="sxs-lookup"><span data-stu-id="49795-182">Add Manage Pages permission.</span></span>

    ![新增管理頁面的權限](media/FBCimage39.png)

16. <span data-ttu-id="49795-184">取得由 Facebook 檢閱應用程式。</span><span class="sxs-lookup"><span data-stu-id="49795-184">Get the application reviewed by Facebook.</span></span>

    ![取得由 Facebook 檢閱應用程式](media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="49795-186">步驟 4： 設定連接器的 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="49795-186">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="49795-187">移至 https://\<AzureAppResourceName>.azurewebsites.net （其中 AzureAppResourceName 是您在步驟 4 中名為您 Azure 應用程式資源的名稱），例如，如果名稱為**fbconnector**，請移至`https://fbconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="49795-187">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="49795-188">應用程式的 [首頁] 頁面上看起來像下列螢幕擷取畫面中：</span><span class="sxs-lookup"><span data-stu-id="49795-188">The home page of the app will look like the following screenshot:</span></span>

   ![移至您連接器 web app](media/FBCimage41.png)

2. <span data-ttu-id="49795-190">按一下 [**設定**] 頁面中，會顯示號。</span><span class="sxs-lookup"><span data-stu-id="49795-190">Click **Configure** to display a sign in page.</span></span>
 
   ![按一下 [設定] 頁面中，會顯示號](media/FBCimage42.png)

3. <span data-ttu-id="49795-192">在租用戶識別碼] 方塊中，輸入或貼上您的租用戶識別碼 （您在步驟 2 中所取得）。</span><span class="sxs-lookup"><span data-stu-id="49795-192">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="49795-193">在 [密碼] 方塊中，輸入或貼上 APISecretKey （，您在步驟 2 中所取得），，然後按一下要顯示 [組態詳細資料] 頁面上**設定的組態設定**。</span><span class="sxs-lookup"><span data-stu-id="49795-193">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![使用您的租用戶識別碼和密碼登入，然後移至設定詳細資料頁面](media/FBCimage43.png)

4. <span data-ttu-id="49795-195">輸入下列組態設定</span><span class="sxs-lookup"><span data-stu-id="49795-195">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="49795-196">**Facebook 應用程式識別碼：** 您在步驟 3 中所取得的 Facebook 應用程式的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="49795-196">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>
   
   - <span data-ttu-id="49795-197">**Facebook 應用程式密碼：** 您在步驟 3 中所取得的 Facebook 應用程式之應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="49795-197">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>
   
   - <span data-ttu-id="49795-198">**Facebook webhooks 驗證權杖：** 您在步驟 3 中建立驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="49795-198">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="49795-199">**AAD 應用程式識別碼：** 您在步驟 1 建立的 Azure Active Directory 應用程式的應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="49795-199">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>
   
   - <span data-ttu-id="49795-200">**AAD 應用程式密碼：** 您在步驟 1 建立的 APISecretKey 密碼值。</span><span class="sxs-lookup"><span data-stu-id="49795-200">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="49795-201">按一下 [**儲存**] 以儲存連接器設定。</span><span class="sxs-lookup"><span data-stu-id="49795-201">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="49795-202">步驟 5： 設定 Microsoft 365 合規性中心中的 Facebook 連接器</span><span class="sxs-lookup"><span data-stu-id="49795-202">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="49795-203">移至 [ [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然後按一下 [從左側的 [**資料連接器**</span><span class="sxs-lookup"><span data-stu-id="49795-203">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="49795-204">在 [**資料連接器 （預覽）** 頁面的 [ **Facebook 商務頁面**，按一下 [**檢視**]。</span><span class="sxs-lookup"><span data-stu-id="49795-204">On the **Data connectors (preview)** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="49795-205">在**Facebook 商務頁面**] 頁面上，按一下 [**新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="49795-205">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="49795-206">在**服務中的條款**] 頁面上，按一下 [**接受**]。</span><span class="sxs-lookup"><span data-stu-id="49795-206">On the **Terms of service** page, click **Accept**.</span></span>

5.  <span data-ttu-id="49795-207">在**您的連接器應用程式新增認證**] 頁面中，輸入下列資訊，然後按一下 [**驗證連線**。</span><span class="sxs-lookup"><span data-stu-id="49795-207">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

    ![輸入連接器應用程式的認證](media/TCimage38.png)

    - <span data-ttu-id="49795-209">在 [**名稱**] 方塊中，輸入連接器，例如**Facebook 新聞] 頁面**的名稱。</span><span class="sxs-lookup"><span data-stu-id="49795-209">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>
    
    - <span data-ttu-id="49795-210">在 [**連線 URL** ] 方塊中，輸入或貼上的 Azure 應用程式服務 URL;例如`https://fbconnector.azurewebsites.net`。</span><span class="sxs-lookup"><span data-stu-id="49795-210">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="49795-211">在 [**密碼**] 方塊中，輸入或貼上您在步驟 2 中新增 APISecretKey 的值。</span><span class="sxs-lookup"><span data-stu-id="49795-211">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>
    
    - <span data-ttu-id="49795-212">在**Azure 應用程式識別碼**] 方塊中，輸入或貼上也稱為為您在步驟 1 建立的 AAD 應用程式 ID （用戶端） 的應用程式識別碼的值。</span><span class="sxs-lookup"><span data-stu-id="49795-212">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>
 
6. <span data-ttu-id="49795-213">連線成功驗證之後，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="49795-213">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="49795-214">在 [**授權 Microsoft 365，以匯入資料**] 頁面上，輸入或貼上 APISecretKey 再次並再按一下 [**登入 web 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="49795-214">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="49795-215">在**設定 Facebook 連接器應用程式**] 頁面上，按一下 [**登入與 Facebook**和登入之帳戶的組織的 Facebook 商務頁面使用的認證。</span><span class="sxs-lookup"><span data-stu-id="49795-215">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="49795-216">請確定您指派給貴組織的 Facebook 商務頁面的管理員角色登入 Facebook 帳戶。</span><span class="sxs-lookup"><span data-stu-id="49795-216">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![登入 Facebook](media/FBCimage50.png)

9. <span data-ttu-id="49795-218">受管理的 Facebook 帳戶，登入商務頁面清單隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="49795-218">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="49795-219">選取 [頁面以封存，然後按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="49795-219">Select the page to archive and then click **Next**.</span></span>

    ![選取您想要保存組織 business 頁面](media/FBCimage52.png)

10. <span data-ttu-id="49795-221">按一下 [**繼續**] 以結束連接器服務應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="49795-221">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="49795-222">在 [**設定篩選器**] 頁面上，您可以套用篩選器，一開始匯入特定天數的項目。</span><span class="sxs-lookup"><span data-stu-id="49795-222">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="49795-223">選取 [保留天數，，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="49795-223">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="49795-224">在 [**選擇儲存位置**] 頁面上，輸入 Facebook 項目會被匯入，並再按 [**下一步**，Microsoft 365 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="49795-224">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="49795-225">在**提供系統管理員同意**，按一下**提供同意**，然後遵循的步驟。</span><span class="sxs-lookup"><span data-stu-id="49795-225">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="49795-226">您必須是全域系統管理員提供 Office 365 匯入服務來存取您的組織中資料的同意。</span><span class="sxs-lookup"><span data-stu-id="49795-226">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="49795-227">按 [**下一步**檢閱連接器設定，然後按一下 [**完成**] 以完成連接器設定。</span><span class="sxs-lookup"><span data-stu-id="49795-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="49795-228">在合規性中心] 中，移至**資料連接器**] 頁面上，然後按一下 [**連接器**] 索引標籤，若要查看匯入程序的進度。</span><span class="sxs-lookup"><span data-stu-id="49795-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
