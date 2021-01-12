---
title: 從 Google Workspace 遷移商務電子郵件和行事曆
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何將電子郵件、連絡人及行事曆從 Google Workspace 遷移至 Microsoft 365 for business。
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794604"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="b0afb-103">從 Google Workspace 遷移商務電子郵件和行事曆</span><span class="sxs-lookup"><span data-stu-id="b0afb-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="b0afb-104">您可以從 Google Workspace 使用管理員執行的遷移至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b0afb-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="b0afb-105">您可以一次或分階段遷移郵件。</span><span class="sxs-lookup"><span data-stu-id="b0afb-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="b0afb-106">下列步驟顯示如何一次遷移電子郵件資料。</span><span class="sxs-lookup"><span data-stu-id="b0afb-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="b0afb-107">如需詳細資訊，請參閱 [執行 a G Suite 遷移](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)。</span><span class="sxs-lookup"><span data-stu-id="b0afb-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="b0afb-108">遷移程式需要數個步驟，而且可能需要數小時到數天內，視您要遷移的資料量而定。</span><span class="sxs-lookup"><span data-stu-id="b0afb-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="b0afb-109">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="b0afb-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="b0afb-110">建立 Google 服務帳戶</span><span class="sxs-lookup"><span data-stu-id="b0afb-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="b0afb-111">使用 Chrome 瀏覽器，在 [admin.google.com](https://admin.google.com)登入 Google Workspace 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="b0afb-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="b0afb-112">在新的索引標籤或視窗中，流覽至 [ [服務帳戶](https://console.developers.google.com/iam-admin/serviceaccounts) ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b0afb-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="b0afb-113">選取 [ **建立專案**]，為專案命名，然後選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="b0afb-114">選取 [**建立服務帳戶**]，輸入名稱，然後選擇 [建立]，然後選擇 [**建立** **]。**</span><span class="sxs-lookup"><span data-stu-id="b0afb-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="b0afb-115">開啟 [ **動作** ] 功能表，選取 [ **編輯**]，並記下唯一的識別碼。</span><span class="sxs-lookup"><span data-stu-id="b0afb-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="b0afb-116">您將在此程式中稍後需要這個識別碼。</span><span class="sxs-lookup"><span data-stu-id="b0afb-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="b0afb-117">開啟 [ **顯示全網域委派** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="b0afb-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="b0afb-118">選取 [ **啟用 G Suite 全域的委派**]，輸入同意畫面的產品名稱，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="b0afb-119">遷移程式不會使用產品名稱，但需要在對話方塊中進行儲存。</span><span class="sxs-lookup"><span data-stu-id="b0afb-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="b0afb-120">再次開啟 [ **動作** ] 功能表，然後選取 [ **建立機碼**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="b0afb-121">選擇 [ **JSON**]，然後 **建立**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="b0afb-122">私密金鑰會儲存至裝置上的下載資料夾。</span><span class="sxs-lookup"><span data-stu-id="b0afb-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="b0afb-123">選取 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="b0afb-124">啟用專案的 API 使用方式</span><span class="sxs-lookup"><span data-stu-id="b0afb-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="b0afb-125">流覽至 [ [APIs] 頁面](https://console.developers.google.com/apis/library)。</span><span class="sxs-lookup"><span data-stu-id="b0afb-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="b0afb-126">在搜尋列中，輸入 **GMAIL API**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="b0afb-127">選取它，然後選擇 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="b0afb-128">針對 Google Calendar API 和 Contacts API 重複此程式。</span><span class="sxs-lookup"><span data-stu-id="b0afb-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="b0afb-129">授與服務帳戶的存取權</span><span class="sxs-lookup"><span data-stu-id="b0afb-129">Grant access to the service account</span></span>

1. <span data-ttu-id="b0afb-130">回到 Google Workspace 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="b0afb-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="b0afb-131">選取 [ **安全性**]，向下並向下並開啟 **API 控制項**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="b0afb-132">向外按，然後選取 [ **管理全網域委派**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="b0afb-133">選取 [ **新增** ]，然後輸入您在先前所做的用戶端識別碼。</span><span class="sxs-lookup"><span data-stu-id="b0afb-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="b0afb-134">然後輸入 Google APIs 的 OAuth 範圍。</span><span class="sxs-lookup"><span data-stu-id="b0afb-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="b0afb-135">這些是在步驟5的 [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) 中提供，也就是：</span><span class="sxs-lookup"><span data-stu-id="b0afb-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="b0afb-136">選擇 [ **授權**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="b0afb-137">針對移至 Microsoft 365 的郵件建立子域</span><span class="sxs-lookup"><span data-stu-id="b0afb-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="b0afb-138">回到 **Google Workspace 管理** 主控台。</span><span class="sxs-lookup"><span data-stu-id="b0afb-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="b0afb-139">選取 [ **網域**]、[ **管理網域**]，然後 **新增網域別名**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="b0afb-140">輸入類似的域別名 `m365.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="b0afb-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="b0afb-141">然後選取 [ **繼續]，然後確認網域擁有權**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="b0afb-142">網域驗證通常只需要幾分鐘的時間，但可能需要長達48小時。</span><span class="sxs-lookup"><span data-stu-id="b0afb-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="b0afb-143">移至 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b0afb-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="b0afb-144">在 **Microsoft 365 系統管理中心** 的左側導覽中，選取 [ **全部顯示**]、[ **設定**]、[ **網域**]，然後 **新增網域**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="b0afb-145">輸入您先前建立的子域，然後選取 [ **使用此網域**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="b0afb-146">若要連接網域，請選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="b0afb-147">向下滾動並記下 MX 記錄、CNAME 記錄和 TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="b0afb-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="b0afb-148">回到 Google 系統 **管理主控台**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="b0afb-149">選取 [ **網域**]，選取 [ **管理網域**]， **確認詳細資料** ，然後 **管理網域**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="b0afb-150">在左側導覽中，選擇 [ **DNS** ]，然後向下滾動至 [ **自訂資源記錄**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="b0afb-151">開啟 [記錄類型] 下拉式清單，然後選取 [ **mx**]，輸入或複製並貼上您先前記下的 mx 記錄資訊，然後選擇 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="b0afb-152">重複 CNAME 記錄和 TXT 記錄的處理常式。</span><span class="sxs-lookup"><span data-stu-id="b0afb-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="b0afb-153">可能需要一些時間，這些變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="b0afb-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="b0afb-154">回到您在 **Microsoft 365 系統管理中心** 中離開的位置，然後選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="b0afb-155">您的網域現在已設定好。</span><span class="sxs-lookup"><span data-stu-id="b0afb-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="b0afb-156">在 Microsoft 365 中建立電子郵件別名</span><span class="sxs-lookup"><span data-stu-id="b0afb-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="b0afb-157">在遷移開始之前，您必須使用新的子域建立使用者的電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="b0afb-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="b0afb-158">若要開始下一個步驟，請在 Microsoft 365 系統管理中心的 [ **新增網域** ] 嚮導中，選取 [ **移至** 作用中使用者]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="b0afb-159">選取使用者，然後管理使用者 **名稱和電子郵件**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="b0afb-160">從 [ **網域** ] 下拉式清單中，選取您先前建立的子域。</span><span class="sxs-lookup"><span data-stu-id="b0afb-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="b0afb-161">輸入使用者名稱，然後選取 [ **新增**]、[ **儲存變更**]，然後關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="b0afb-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="b0afb-162">針對每個使用者重複此程式。</span><span class="sxs-lookup"><span data-stu-id="b0afb-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="b0afb-163">啟動遷移程式</span><span class="sxs-lookup"><span data-stu-id="b0afb-163">Start the migration process</span></span>

<span data-ttu-id="b0afb-164">完成後，您就可以遷移。</span><span class="sxs-lookup"><span data-stu-id="b0afb-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="b0afb-165">在 **Microsoft 365 系統管理中心** 的左側導覽中，向下滾動至 [系統 **管理中心**]，然後選取 [ **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="b0afb-166">在 [收件者] **底下，選擇**[ **遷移**]，選取 [ **新增**]， **遷移至 Exchange Online**，然後選擇 [ **G Suite 遷移** **]**，然後再</span><span class="sxs-lookup"><span data-stu-id="b0afb-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="b0afb-167">使用您要遷移的信箱清單建立 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="b0afb-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="b0afb-168">請確定檔案遵循下列格式：</span><span class="sxs-lookup"><span data-stu-id="b0afb-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="b0afb-169">如需詳細資訊，請參閱 [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)。</span><span class="sxs-lookup"><span data-stu-id="b0afb-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="b0afb-170">選取 **[選擇** 檔案]，流覽至 CSV 檔案，然後選取 [ **開啟**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="b0afb-171">確認您要用來測試的系統管理員電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b0afb-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="b0afb-172">選取 **[選擇** 檔案]，流覽至您先前建立的 JSON 檔案 (通常是在電腦上的 [下載] 資料夾中) 選取它，然後選取 [ **開啟**]，再按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="b0afb-173">在 [ **新增遷移批次名稱] 欄位** 中輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="b0afb-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="b0afb-174">在 [ **目標傳遞網域** ] 欄位中，輸入您建立的子域，選取 **[下一步]**，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="b0afb-175">儲存資訊後，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="b0afb-176">您現在可以查看遷移的狀態。</span><span class="sxs-lookup"><span data-stu-id="b0afb-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="b0afb-177">經過一段時間之後，視您要遷移的使用者人數而定， **選取 [** 重新整理]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="b0afb-178">一旦狀態變更為 [已 **同步** 處理]，請選取 [ **完成此遷移批次**]，然後選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="b0afb-179">完成此程式之後，您的狀態會變更為 [ **已完成**]。</span><span class="sxs-lookup"><span data-stu-id="b0afb-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="b0afb-180">如有需要，您可以選取 [ **查看詳細** 資訊] 以取得有關遷移的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b0afb-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="b0afb-181">選取 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="b0afb-181">Select **Close**.</span></span> 
1. <span data-ttu-id="b0afb-182">開啟 Outlook 以確認已順利遷移 Google Workspace 中的所有電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b0afb-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="b0afb-183">您也可以為行事曆專案和連絡人重複此專案。</span><span class="sxs-lookup"><span data-stu-id="b0afb-183">You can repeat this for calendar items and contacts as well.</span></span>