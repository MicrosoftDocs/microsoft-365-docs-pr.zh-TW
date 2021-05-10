---
title: 啟用報告訊息或報告網路釣魚增益集
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 瞭解如何為個別使用者或整個組織啟用 Outlook 和 Outlook 的報告訊息或報告網路釣魚增益集。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dc54c5b74697ac41a1d4ff0818467dba662b31f5
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295816"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="bb6bb-103">啟用報告訊息或報告網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="bb6bb-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bb6bb-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="bb6bb-104">**Applies to**</span></span>
- [<span data-ttu-id="bb6bb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bb6bb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bb6bb-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="bb6bb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bb6bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb6bb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="bb6bb-108">如果您是具有 Exchange Online 信箱的 Microsoft 365 組織中的系統管理員，建議您在安全性 & 合規性中心使用提交入口網站。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="bb6bb-109">如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="bb6bb-110">在 web 上的 Outlook 和 Outlook 的報告訊息和報告網路釣魚增益集 (以前稱為 Outlook Web App) 讓使用者可以輕鬆地報告誤報 (正確的電子郵件標記為壞的) 或 false 不利的電子郵件， (的電子郵件可供 Microsoft 及其公司的分析使用。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="bb6bb-111">Microsoft 會使用這些提交來改善電子郵件防護技術的有效性。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="bb6bb-112">例如，假設有人使用「報告網路釣魚增益集」報告許多郵件。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="bb6bb-113">此資訊會顯示在安全性儀表板及其他報告中。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="bb6bb-114">貴組織的安全性小組可以使用此資訊來表示可能需要更新防網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="bb6bb-115">您可以安裝報告訊息或報告網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="bb6bb-116">如果您想要讓使用者報告垃圾郵件和網路釣魚郵件，請在您的組織中部署報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="bb6bb-117">如需詳細資訊，請參閱 Enable the Report Message 增益集。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="bb6bb-118">報告郵件增益集提供的選項可報告垃圾郵件和網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="bb6bb-119">系統管理員可以為組織啟用「報告訊息增益集」，個別使用者可以自行自行安裝。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="bb6bb-120">報告網路釣魚增益集提供的選項可報告僅網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="bb6bb-121">系統管理員可以為組織啟用「報告網路釣魚增益集」，個別使用者可以自行自行安裝。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="bb6bb-122">如果您是個別的使用者，您可以為自己啟用增益集。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="bb6bb-123">f 您是全域系統管理員或 Exchange Online 管理員，且 Exchange 設定成使用 OAuth 驗證，您可以為組織啟用報告訊息增益集和報告網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-123">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="bb6bb-124">這兩個增益集現在均可透過 [集中式部署](../../admin/manage/centralized-deployment-of-add-ins.md)使用。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bb6bb-125">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="bb6bb-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bb6bb-126">報告訊息增益集與報告網路釣魚增益集均可搭配大多數的 Microsoft 365 訂閱及下列產品運作：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="bb6bb-127">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="bb6bb-127">Outlook on the web</span></span>
  - <span data-ttu-id="bb6bb-128">Outlook 2013 SP1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="bb6bb-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="bb6bb-129">Mac 版 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bb6bb-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="bb6bb-130">包含 Microsoft 365 Enterprise 應用程式的 Outlook</span><span class="sxs-lookup"><span data-stu-id="bb6bb-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="bb6bb-131">iOS 和 Android 的 Outlook 應用程式</span><span class="sxs-lookup"><span data-stu-id="bb6bb-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="bb6bb-132">這兩個增益集不能用於內部部署 Exchange 組織中的共用信箱或信箱。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="bb6bb-133">您的現有網頁瀏覽器應該同時搭配報告訊息和報告網路釣魚增益集。不過，如果您注意到增益集無法使用或如預期般運作，請嘗試其他瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="bb6bb-134">若為組織安裝，必須設定組織使用 OAuth 驗證。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="bb6bb-135">如需詳細資訊，請參閱 [判斷是否集中式部署的增益集可為您的組織運作](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="bb6bb-136">管理員必須是全域系統管理員角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="bb6bb-137">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="bb6bb-138">如需如何使用報告郵件功能來報告訊息的詳細資訊，請參閱[在 Outlook 中報告誤報和漏報](report-false-positives-and-false-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="bb6bb-139">取得報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="bb6bb-139">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="bb6bb-140">取得您自己的增益集</span><span class="sxs-lookup"><span data-stu-id="bb6bb-140">Get the add-in for yourself</span></span>

1. <span data-ttu-id="bb6bb-141">移至 Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> ，並搜尋報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-141">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="bb6bb-142">若要直接移至報告訊息增益集，請移至 <https://appsource.microsoft.com/product/office/wa104381180> 。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-142">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="bb6bb-143">按一下 [ **立即取得**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-143">Click **GET IT NOW**.</span></span>

   ![報告訊息 - 立即取得](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="bb6bb-145">在出現的對話方塊中，複查使用條款和隱私權原則，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-145">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="bb6bb-146">使用您的工作或學校帳戶登入 (商務用) 或您的 Microsoft 帳戶 (個人用途) 。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-146">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="bb6bb-147">安裝並啟用增益集之後，您會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-147">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="bb6bb-148">在 Outlook 中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-148">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="bb6bb-149">![Outlook 的報告訊息增益集圖示](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="bb6bb-149">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="bb6bb-150">在 Outlook 網頁版中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-150">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="bb6bb-151">![web 報表郵件增益集圖示上的 Outlook](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="bb6bb-151">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="bb6bb-152">取得組織的增益集</span><span class="sxs-lookup"><span data-stu-id="bb6bb-152">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="bb6bb-153">在您的組織中顯示增益集可能需要長達12小時。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-153">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="bb6bb-154">在 Microsoft 365 系統管理中心，移至 [前往 **設定** \> **增益集**] 頁面 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-154">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="bb6bb-155">如果您看不到 [**增益集**] 頁面，請移至 [整合式應用程式] 頁面頂端的 [**設定** \> **整合式應用程式** \> **增益集**] 連結。 </span><span class="sxs-lookup"><span data-stu-id="bb6bb-155">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="bb6bb-156">選取頁面頂端的 [ **部署增益集** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-156">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 系統管理中心的 [服務和增益集] 頁面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="bb6bb-158">在出現的 **新增益集** 浮出視窗中，複查資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-158">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="bb6bb-159">在下一個頁面上，按一下 **[從儲存區選擇**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-159">On the next page, click **Choose from the Store**.</span></span>

   ![部署新的增益集頁面](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="bb6bb-161">在出現的 [ **選取增益集** ] 頁面上，按一下 [ **搜尋** ] 方塊，輸入 **報告訊息**，然後按一下 [ **搜尋** ![ 搜尋] 圖示 ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-161">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="bb6bb-162">在結果清單中，尋找 [ **報告訊息** ]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-162">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![選取增益集搜尋結果](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="bb6bb-164">在出現的對話方塊中，複查授權和隱私權資訊，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-164">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="bb6bb-165">在出現的 [ **設定增益集** ] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-165">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="bb6bb-166">**指派的使用者**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-166">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="bb6bb-167">**所有人** (預設) </span><span class="sxs-lookup"><span data-stu-id="bb6bb-167">**Everyone** (default)</span></span>
     - <span data-ttu-id="bb6bb-168">**特定使用者/群組**</span><span class="sxs-lookup"><span data-stu-id="bb6bb-168">**Specific users / groups**</span></span>
     - <span data-ttu-id="bb6bb-169">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="bb6bb-169">**Just me**</span></span>

   - <span data-ttu-id="bb6bb-170">**部署方法**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-170">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="bb6bb-171">**Fixed (預設)**：增益集會自動部署至指定的使用者，且無法加以移除。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-171">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="bb6bb-172">**可用**：使用者可以在 **Home** \> **Get 增益集** \> **管理管理** 的位置安裝增益集。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-172">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="bb6bb-173">**選用**：增益集會自動部署至指定的使用者，但是可以選擇加以移除。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-173">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![設定增益集頁面](../../media/configure-add-in.png)

   <span data-ttu-id="bb6bb-175">當您完成時，按一下 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-175">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="bb6bb-176">在出現的 [ **部署報告郵件** ] 頁面中，您會看到進度報告，接著會出現部署增益集的確認。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-176">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="bb6bb-177">閱讀資訊後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-177">After you read the information, click **Next**.</span></span>

   ![部署報告郵件頁面](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="bb6bb-179">在出現的 **宣告增益集** 頁面上，複查資訊，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-179">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![宣告增益集頁面](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="bb6bb-181">檢閱或編輯報告訊息增益集的設定</span><span class="sxs-lookup"><span data-stu-id="bb6bb-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="bb6bb-182">在 Microsoft 365 系統管理中心，移至 [前往 **設定** \> **增益集**] 頁面 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-182">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="bb6bb-183">如果您看不到 [**增益集**] 頁面，請移至 [整合式應用程式] 頁面頂端的 [**設定** \> **整合式應用程式** \> **增益集**] 連結。 </span><span class="sxs-lookup"><span data-stu-id="bb6bb-183">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![新 Microsoft 365 系統管理中心的服務和增益集頁面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="bb6bb-185">尋找並選取 **報告訊息** 增益集。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-185">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="bb6bb-186">在顯示的 [ **編輯報告訊息** ] 浮出視窗中，視組織的需要複查及編輯設定。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-186">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="bb6bb-187">完成後，點擊 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-187">When you're finished, click **Save**.</span></span>

   ![報告訊息增益集的設定](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="bb6bb-189">取得報告網路釣魚增益集</span><span class="sxs-lookup"><span data-stu-id="bb6bb-189">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="bb6bb-190">取得您自己的增益集</span><span class="sxs-lookup"><span data-stu-id="bb6bb-190">Get the add-in for yourself</span></span>

1. <span data-ttu-id="bb6bb-191">移至 Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> ，並搜尋報表網路釣魚增益集。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-191">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="bb6bb-192">按一下 [ **立即取得**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-192">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="bb6bb-193">在出現的對話方塊中，複查使用條款和隱私權原則，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-193">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="bb6bb-194">使用您的工作或學校帳戶登入 (商務用) 或您的 Microsoft 帳戶 (個人用途) 。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-194">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="bb6bb-195">安裝並啟用增益集之後，您會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-195">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="bb6bb-196">在 Outlook 中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-196">In Outlook, the icon looks like this:</span></span>

  ![報告 Outlook 的網路釣魚增益集圖示](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="bb6bb-198">在 Outlook 網頁版中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-198">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="bb6bb-199">![網頁報告網路釣魚增益集圖示上的 Outlook](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="bb6bb-199">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="bb6bb-200">取得組織的增益集</span><span class="sxs-lookup"><span data-stu-id="bb6bb-200">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="bb6bb-201">在您的組織中顯示增益集可能需要長達12小時。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-201">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="bb6bb-202">在 Microsoft 365 系統管理中心，移至 [前往 **設定** \> **增益集**] 頁面 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-202">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="bb6bb-203">如果您看不到 [**增益集**] 頁面，請移至 [整合式應用程式] 頁面頂端的 [**設定** \> **整合式應用程式** \> **增益集**] 連結。 </span><span class="sxs-lookup"><span data-stu-id="bb6bb-203">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="bb6bb-204">選取頁面頂端的 [ **部署增益集** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-204">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 系統管理中心的 [服務和增益集] 頁面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="bb6bb-206">在出現的 **新增益集** 浮出視窗中，複查資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-206">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="bb6bb-207">在下一個頁面上，按一下 **[從儲存區選擇**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-207">On the next page, click **Choose from the Store**.</span></span>

   ![部署新的增益集頁面](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="bb6bb-209">在出現的 [ **選取增益集** ] 頁面上，按一下 [ **搜尋** ] 方塊中的 [ **報告網路釣魚**]，然後按一下 [ **搜尋** ![ 搜尋] 圖示 ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-209">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="bb6bb-210">在結果清單中，尋找 [ **報告網路釣魚** ]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-210">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="bb6bb-211">在出現的對話方塊中，複查授權和隱私權資訊，然後按一下 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-211">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="bb6bb-212">在出現的 [ **設定增益集** ] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-212">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="bb6bb-213">**指派的使用者**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-213">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="bb6bb-214">**所有人** (預設) </span><span class="sxs-lookup"><span data-stu-id="bb6bb-214">**Everyone** (default)</span></span>
     - <span data-ttu-id="bb6bb-215">**特定使用者/群組**</span><span class="sxs-lookup"><span data-stu-id="bb6bb-215">**Specific users / groups**</span></span>
     - <span data-ttu-id="bb6bb-216">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="bb6bb-216">**Just me**</span></span>

   - <span data-ttu-id="bb6bb-217">**部署方法**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="bb6bb-217">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="bb6bb-218">**Fixed (預設)**：增益集會自動部署至指定的使用者，且無法加以移除。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-218">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="bb6bb-219">**可用**：使用者可以在 **Home** \> **Get 增益集** \> **管理管理** 的位置安裝增益集。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-219">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="bb6bb-220">**選用**：增益集會自動部署至指定的使用者，但是可以選擇加以移除。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-220">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="bb6bb-221">當您完成時，按一下 [ **部署**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-221">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="bb6bb-222">在出現的 [ **部署報告網路釣魚** ] 頁面中，您會看到進度報告，接著會出現部署增益集的確認。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-222">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="bb6bb-223">閱讀資訊後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-223">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="bb6bb-224">在出現的 **宣告增益集** 頁面上，複查資訊，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-224">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="bb6bb-225">查看或編輯報表網路釣魚增益集的設定</span><span class="sxs-lookup"><span data-stu-id="bb6bb-225">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="bb6bb-226">在 Microsoft 365 系統管理中心，移至 [前往 **設定** \> **增益集**] 頁面 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-226">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="bb6bb-227">如果您看不到 [**增益集**] 頁面，請移至 [整合式應用程式] 頁面頂端的 [**設定** \> **整合式應用程式** \> **增益集**] 連結。 </span><span class="sxs-lookup"><span data-stu-id="bb6bb-227">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="bb6bb-228">尋找並選取 **報告網路釣魚** 增益集。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-228">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="bb6bb-229">在 [ **編輯報告的網路釣魚** ] 浮出控制項中，視您的組織而定，會顯示、審閱及編輯設定。</span><span class="sxs-lookup"><span data-stu-id="bb6bb-229">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="bb6bb-230">When you're finished, click **Save**.</span><span class="sxs-lookup"><span data-stu-id="bb6bb-230">When you're finished, click **Save**.</span></span>
