---
title: 從 Google Workspace 移動商務電子郵件和日曆
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何將電子郵件、連絡人和日曆從 Google Workspace 遷移到商務用 Microsoft 365。
ms.openlocfilehash: cb751b1d2f18b226021bb6f218b62f3ae426f6a4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928243"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="c4a7b-103">從 Google Workspace 移動商務電子郵件和日曆</span><span class="sxs-lookup"><span data-stu-id="c4a7b-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="c4a7b-104">您可以使用系統管理員管理方式從 Google Workspace 移往 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="c4a7b-105">您可以一次或階段地所有來電郵件。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="c4a7b-106">下列步驟將說明一次如何遷移電子郵件資料。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="c4a7b-107">詳細資訊請參閱執行 [G Suite 移移](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="c4a7b-108">移移程式需要數個步驟，而且可能需要數小時到數天的時間，視您移移的資料量決定。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="c4a7b-109">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="c4a7b-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="c4a7b-110">建立 Google 服務帳戶</span><span class="sxs-lookup"><span data-stu-id="c4a7b-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="c4a7b-111">使用 Chrome 瀏覽器，在[admin.google.com。](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="c4a7b-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="c4a7b-112">在新的分頁或視窗中，流覽至服務 [帳戶](https://console.developers.google.com/iam-admin/serviceaccounts) 頁面。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="c4a7b-113">選取 **建立專案**，命名專案 **，然後選擇建立**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="c4a7b-114">選取 **建立服務帳戶**，輸入名稱 **，選擇建立** ，然後 **完成**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="c4a7b-115">開啟動作 **功能表** ，選取 **編輯**，然後記下唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="c4a7b-116">此程式稍後會需要此識別碼。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="c4a7b-117">開啟顯示 **全網委派** 區段。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="c4a7b-118">選取 **啟用 G Suite 網域委派**，輸入同意畫面的產品名稱，**然後選擇儲存。**</span><span class="sxs-lookup"><span data-stu-id="c4a7b-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="c4a7b-119">移移程式不會使用產品名稱，但需要產品名稱才能儲存在對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="c4a7b-120">再次開啟 **動作功能表** ，然後選取建立 **鍵**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="c4a7b-121">選擇 **JSON，\*\*\*\*然後建立**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="c4a7b-122">私密金鑰會儲存到您裝置上的下載資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="c4a7b-123">選取 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="c4a7b-124">啟用專案的 API 使用方式</span><span class="sxs-lookup"><span data-stu-id="c4a7b-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="c4a7b-125">流覽至 [API 頁面](https://console.developers.google.com/apis/library)。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="c4a7b-126">在搜尋行中，輸入 **Gmail API。**</span><span class="sxs-lookup"><span data-stu-id="c4a7b-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="c4a7b-127">選取它，**然後選擇啟用。**</span><span class="sxs-lookup"><span data-stu-id="c4a7b-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="c4a7b-128">針對 Google 日曆 API 和連絡人 API 重複此程式。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="c4a7b-129">授予服務帳戶的存取權</span><span class="sxs-lookup"><span data-stu-id="c4a7b-129">Grant access to the service account</span></span>

1. <span data-ttu-id="c4a7b-130">返回 Google Workspace 系統管理主控台。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="c4a7b-131">選取 **安全性**，向下卷卷並開啟 **API 控制項**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="c4a7b-132">向下卷選並選取 **管理網域委派**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="c4a7b-133">選取 **新增** ，然後輸入您先前記下的用戶端識別碼。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="c4a7b-134">然後輸入 Google API 的 OAuth 範圍。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="c4a7b-135">這些步驟可在步驟 5 [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) 提供，並且有：</span><span class="sxs-lookup"><span data-stu-id="c4a7b-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="c4a7b-136">選擇 **授權**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="c4a7b-137">為要寄到 Microsoft 365 的郵件建立子域</span><span class="sxs-lookup"><span data-stu-id="c4a7b-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="c4a7b-138">返回 **Google Workspace 系統管理** 主控台。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="c4a7b-139">選取 **網域\*\*\*\*、管理網域**，**然後新增網域別名**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="c4a7b-140">輸入網域別名，例如 `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="c4a7b-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="c4a7b-141">然後選取 **繼續並驗證網域擁有權**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="c4a7b-142">網域驗證通常只需要幾分鐘的時間，但最多可能需要 48 小時。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="c4a7b-143">請前往 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="c4a7b-144">在 **Microsoft 365** 系統管理中心的左側 NAV中，選取顯示全部、設定、網域，然後新增 **網域。** </span><span class="sxs-lookup"><span data-stu-id="c4a7b-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="c4a7b-145">輸入您先前建立過的子域，然後選取使用 **這個網域**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="c4a7b-146">若要連接網域，請 **選取繼續**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="c4a7b-147">向下卷起並記下 MX 記錄、CNAME 記錄及 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="c4a7b-148">返回 **Google 管理主控台**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="c4a7b-149">選取 **網域**、**選取管理網域\*\*\*\*、驗證** 詳細資料，然後 **管理網域**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="c4a7b-150">在左側流覽中，選擇 **DNS** 並向下卷到 **自訂資源記錄**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="c4a7b-151">開啟記錄類型下拉式選項，然後選取 **MX，** 輸入或複製並貼上您先前提到的 MX 記錄資訊，然後選擇新增。 </span><span class="sxs-lookup"><span data-stu-id="c4a7b-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="c4a7b-152">對 CNAME 記錄和 TXT 記錄重複此程式。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="c4a7b-153">這些變更可能需要一些時間，變更生效。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="c4a7b-154">返回 Microsoft **365 系統** 管理中心您離開的地方，然後 **選取繼續**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="c4a7b-155">您的網域現在已設定好。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="c4a7b-156">在 Microsoft 365 中建立電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="c4a7b-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="c4a7b-157">在開始移轉之前，您必須使用新的子域為使用者建立電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="c4a7b-158">若要開始下一個步驟，請在Microsoft 365 系統管理中心的新增網域精靈中，選取前往 **使用中使用者。**</span><span class="sxs-lookup"><span data-stu-id="c4a7b-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="c4a7b-159">選取使用者，然後管理 **使用者名稱和電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="c4a7b-160">從網 **域下** 拉清單，選取您先前建立過的子域。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="c4a7b-161">輸入使用者名稱、 **選取新增**、 **儲存變更**，然後關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="c4a7b-162">為每個使用者重複此程式。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="c4a7b-163">開始移移程式</span><span class="sxs-lookup"><span data-stu-id="c4a7b-163">Start the migration process</span></span>

<span data-ttu-id="c4a7b-164">完成後，就可以開始進行遷移了。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="c4a7b-165">在 **Microsoft 365** 系統管理中心的左側流覽中，向下卷到系統 **管理中心**，然後選取 **Exchange。**</span><span class="sxs-lookup"><span data-stu-id="c4a7b-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="c4a7b-166">在 **收件者下\*\*\*\*，選擇** 移移 **、選取新增**、移移至 Exchange **Online、** 選擇 **G Suite** 移移，然後選擇下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="c4a7b-167">建立包含您想要遷移之信箱清單的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="c4a7b-168">請確認檔案採用此格式：</span><span class="sxs-lookup"><span data-stu-id="c4a7b-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="c4a7b-169">詳情[請參閱aka.ms/GoogleWorkspaceMigration。](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)</span><span class="sxs-lookup"><span data-stu-id="c4a7b-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="c4a7b-170">選取 **選擇檔案**，流覽至 CSV 檔案，選擇該檔案， **選取開啟**，然後選取下 **一個**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="c4a7b-171">確認您想要用於測試的系統管理員電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="c4a7b-172">選取 **選擇檔案**，流覽至您先前所建立之 JSON (通常位於您電腦的下載) ，選擇該檔案，選取開啟，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="c4a7b-173">在新的移移批次名稱 **欄位中輸入名稱**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="c4a7b-174">輸入您于目標傳遞網域欄位中所建立的子域 **，選取下** 一個，然後選取 **新**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="c4a7b-175">儲存資訊之後， **請選取確定**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="c4a7b-176">現在，您可以查看移移狀態。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="c4a7b-177">經過一段時間之後，根據您移轉的使用者數量，選取重新 **更新。**</span><span class="sxs-lookup"><span data-stu-id="c4a7b-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="c4a7b-178">一旦狀態變更為已 **同步處理，請** 選取 **完成此** 移移批次，然後 **選取是**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="c4a7b-179">完成程式後，您的狀態就會變更為 **完成**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="c4a7b-180">您可以視需要選取查看 **詳細資料** ，以進一步瞭解移移。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="c4a7b-181">選取 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-181">Select **Close**.</span></span> 
1. <span data-ttu-id="c4a7b-182">開啟 Outlook 以驗證來自 Google Workspace 的所有電子郵件已成功移移。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="c4a7b-183">您也可以對日曆專案和連絡人重複此操作。</span><span class="sxs-lookup"><span data-stu-id="c4a7b-183">You can repeat this for calendar items and contacts as well.</span></span>