---
title: 啟用報告訊息增益集
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 03/26/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何為個別使用者或整個組織啟用 Outlook 和 Outlook 網頁版的 [報告訊息] 增益集。
ms.openlocfilehash: 77fa9c2766ee1e2392ad9ea962a43f4779238209
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599460"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="7abbb-103">啟用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="7abbb-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="7abbb-104">Outlook 和 Outlook 網頁版的 [報告訊息] 增益集與 [Outlook 垃圾郵件篩選工具](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)並不完全相同，但兩者皆可用來將電子郵件標示為垃圾郵件、非垃圾郵件或網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="7abbb-104">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt.</span></span> <span data-ttu-id="7abbb-105">差異在於 Outlook 和 Outlook 網頁版的 [報告訊息] 增益集會通知 Microsoft 有關分類錯誤的電子郵件，而 Outlook 垃圾郵件篩選工具則用來組織使用者信箱中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7abbb-105">The difference is, the Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span>

## <a name="overview"></a><span data-ttu-id="7abbb-106">概觀</span><span class="sxs-lookup"><span data-stu-id="7abbb-106">Overview</span></span>

<span data-ttu-id="7abbb-107">Outlook 和 Outlook 網頁版的 [報告訊息] 增益集可讓人員輕鬆地向 Microsoft 及其子公司報告分類錯誤的電子郵件 (無論安全或惡意)，以便進行分析。</span><span class="sxs-lookup"><span data-stu-id="7abbb-107">The Report Message add-in for Outlook and Outlook on the web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="7abbb-108">Microsoft 會使用這些提交來改善電子郵件防護技術的有效性。</span><span class="sxs-lookup"><span data-stu-id="7abbb-108">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="7abbb-109">此外，如果貴組織使用 [Office 365 進階威脅防護方案 1](office-365-atp.md) 或[方案 2](office-365-ti.md)，則 [報告訊息] 增益集會向貴組織的安全性小組提供實用資訊，以便用於檢閱及更新安全性原則。</span><span class="sxs-lookup"><span data-stu-id="7abbb-109">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="7abbb-110">例如，假設使用者將大量訊息回報為網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="7abbb-110">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="7abbb-111">此資訊會顯示在[安全性儀表板](security-dashboard.md)及其他報告中。</span><span class="sxs-lookup"><span data-stu-id="7abbb-111">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="7abbb-112">貴組織的安全性小組可以使用此資訊來表示可能需要更新防網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="7abbb-112">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="7abbb-113">或者，如果有人使用 [報告訊息] 增益集，回報大量被標示為垃圾郵件的訊息，則貴組織的安全性小組可能需要調整[反垃圾郵件原則](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7abbb-113">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

<span data-ttu-id="7abbb-114">[報告訊息] 增益集適用於您的 Office 365 訂用帳戶和下列產品：</span><span class="sxs-lookup"><span data-stu-id="7abbb-114">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="7abbb-115">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="7abbb-115">Outlook on the web</span></span>
 - <span data-ttu-id="7abbb-116">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="7abbb-116">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="7abbb-117">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7abbb-117">Outlook 2016</span></span>
 - <span data-ttu-id="7abbb-118">Mac 版 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7abbb-118">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="7abbb-119">Office 365 專業增強版隨附的 Outlook</span><span class="sxs-lookup"><span data-stu-id="7abbb-119">Outlook included with Office 365 ProPlus</span></span>

<span data-ttu-id="7abbb-120">您現有的網頁瀏覽器應足以讓 [報告訊息] 增益集運作。不過，如果您發現增益集無法使用或無法如預期般運作，請嘗試使用不同的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="7abbb-120">Your existing web browser should suffice for the Report Message add-in to work; however, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

<span data-ttu-id="7abbb-121">如果您是個人使用者，您可以[自行啟用 [報告訊息] 增益集](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="7abbb-121">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="7abbb-122">如果您是 Office 365 全域系統管理員或 Exchange Online 系統管理員，且 Exchange 已設定為使用 OAuth 驗證，您可以[為貴組織啟用 [報告訊息] 增益集](#get-and-enable-the-report-message-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="7abbb-122">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="7abbb-123">[報告訊息] 增益集現可透過[集中式部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)提供。</span><span class="sxs-lookup"><span data-stu-id="7abbb-123">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="7abbb-124">自行取得報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="7abbb-124">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="7abbb-125">在 [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps) 中，搜尋[報告訊息增益集](https://appsource.microsoft.com/product/office/wa104381180)。</span><span class="sxs-lookup"><span data-stu-id="7abbb-125">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>

2. <span data-ttu-id="7abbb-126">選擇 [立即取得]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-126">Choose **GET IT NOW**.</span></span>

   ![報告訊息 - 立即取得](../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="7abbb-128">檢閱使用條款和隱私權原則。</span><span class="sxs-lookup"><span data-stu-id="7abbb-128">Review the terms of use and privacy policy.</span></span> <span data-ttu-id="7abbb-129">然後選擇 [繼續]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-129">Then choose **Continue**.</span></span>

4. <span data-ttu-id="7abbb-130">使用您的公司或學校帳戶 (商務用途) 或您的 Microsoft 帳戶 (個人用途) 登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7abbb-130">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="7abbb-131">安裝並啟用增益集之後，您會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="7abbb-131">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="7abbb-132">在 Outlook 中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="7abbb-132">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的報告訊息增益集圖示](../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="7abbb-134">在 Outlook 網頁版 (先前為 Outlook Web 應用程式) 中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="7abbb-134">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span>

  ![Outlook 的網頁報告訊息增益集圖示](../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="7abbb-136">在下一個步驟中，了解如何[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="7abbb-136">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="7abbb-137">為貴組織取得和啟用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="7abbb-137">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7abbb-138">您必須是 Office 365 全域系統管理員或 Exchange Online 系統管理員才能完成此工作。</span><span class="sxs-lookup"><span data-stu-id="7abbb-138">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span> <span data-ttu-id="7abbb-139">此外，Exchange 必須設定為使用 OAuth 驗證。若要深入了解，請參閱 [Exchange 需求 (增益集的集中式部署)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="7abbb-139">In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

1. <span data-ttu-id="7abbb-140">移至 Microsoft 365 系統管理中心的[服務與增益集頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="7abbb-140">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![新 Microsoft 365 系統管理中心的服務和增益集頁面](../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="7abbb-142">選擇 [+ 部署增益集]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-142">Choose **+ Deploy Add-in**.</span></span>

   ![選擇部署增益集](../media/ServicesAddIns-ChooseDeployAddIn.png)

3. <span data-ttu-id="7abbb-144">在 [新增增益集]\*\*\*\* 畫面中，檢閱資訊，然後選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-144">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span>

   ![新增增益集詳細資料](../media/NewAddInScreen1.png)

4. <span data-ttu-id="7abbb-146">選取 [我想要從 Office 市集新增增益集]\*\*\*\*，然後選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-146">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span>

   ![我想要新增增益集](../media/NewAddInScreen2.png)

5. <span data-ttu-id="7abbb-148">搜尋 [報告訊息]\*\*\*\*，然後在結果清單中，選擇 [報告訊息增益集]\*\*\*\* 旁邊的 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-148">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span>

   ![搜尋 [報告訊息]，然後選擇 [新增]](../media/NewAddInScreen3.png)

6. <span data-ttu-id="7abbb-150">在 [報告訊息]\*\*\*\* 畫面上，檢閱資訊，然後選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-150">On the **Report Message** screen, review the information, and then choose **Next**.</span></span>

   ![報告訊息詳細資料](../media/ReportMessageAdd-InNewScreen4.png)

7. <span data-ttu-id="7abbb-152">指定 Outlook 的使用者預設設定，然後 選擇 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-152">Specify the user default settings for Outlook, and  then choose **Next**.</span></span>

   ![Outlook 的 [報告訊息] 預設設定](../media/ReportMessageOptionsScreen5.png)

8. <span data-ttu-id="7abbb-154">指定誰可取得 [報告訊息] 增益集，然後選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-154">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span>

   ![誰可取得 [報告訊息] 增益集](../media/ReportMessageOptionsScreen6.png)

> [!TIP]
> <span data-ttu-id="7abbb-156">我們建議[設定規則，以取得由使用者所報告的電子郵件複本](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)。</span><span class="sxs-lookup"><span data-stu-id="7abbb-156">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="7abbb-157">視您在設定增益集時 (上面步驟 7-8) 所選取的內容而定，貴組織中的人員將擁有[報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="7abbb-157">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available.</span></span> <span data-ttu-id="7abbb-158">貴組織中的人員會看到下列圖示：</span><span class="sxs-lookup"><span data-stu-id="7abbb-158">People in your organization will see the following icons:</span></span>

- <span data-ttu-id="7abbb-159">在 Outlook 中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="7abbb-159">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的報告訊息增益集圖示](../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="7abbb-161">在 Outlook 網頁版中，圖示如下所示：</span><span class="sxs-lookup"><span data-stu-id="7abbb-161">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 的網頁報告訊息增益集圖示](../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="7abbb-163">當您通知使用者關於 [報告訊息] 增益集時，請包含[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的連結。</span><span class="sxs-lookup"><span data-stu-id="7abbb-163">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="7abbb-164">設定規則，以取得由您的使用者所報告的電子郵件複本</span><span class="sxs-lookup"><span data-stu-id="7abbb-164">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7abbb-165">您必須是 Exchange Online 系統管理員才能執行此工作。</span><span class="sxs-lookup"><span data-stu-id="7abbb-165">You must be an Exchange Online Administrator to perform this task.</span></span>

<span data-ttu-id="7abbb-166">您可以設定規則，以取得貴組織中的使用者所報告的電子郵件複本。</span><span class="sxs-lookup"><span data-stu-id="7abbb-166">You can set up a rule to get a copy of email messages reported by users in your organization.</span></span> <span data-ttu-id="7abbb-167">為貴組織下載並啟用 [報告訊息] 增益集之後，您就會這麼做。</span><span class="sxs-lookup"><span data-stu-id="7abbb-167">You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>

1. <span data-ttu-id="7abbb-168">在 Exchange 系統管理中心，選擇 [郵件流程]\*\*\*\* \> [規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-168">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span>

2. <span data-ttu-id="7abbb-169">選擇 **+** \> [建立新的規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-169">Choose **+** \> **Create a new rule**.</span></span>

3. <span data-ttu-id="7abbb-170">在 [名稱]\*\*\*\* 方塊中，鍵入名稱，例如 [提交]。</span><span class="sxs-lookup"><span data-stu-id="7abbb-170">In the **Name** box, type a name, such as Submissions.</span></span>

4. <span data-ttu-id="7abbb-171">在 [如果出現下列情況，請套用這個規則]\*\*\*\* 清單中，請選擇 [收件者位址包含...]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-171">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span>

5. <span data-ttu-id="7abbb-172">在 [指定字詞或片語]\*\*\*\* 畫面中，新增 `junk@office365.microsoft.com` 和 `phish@office365.microsoft.com`，然後選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-172">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span>

   ![針對此規則指定垃圾郵件和網路釣魚電子郵件地址](../media/018c1833-f336-4333-a45c-f2e8b75cd698.png)

6. <span data-ttu-id="7abbb-174">在 [執行下列動作...]\*\*\*\* 清單中，選擇 [將此郵件以密件副本傳送到…]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-174">In the **Do the following...** list, choose **Bcc the message to...**.</span></span>

7. <span data-ttu-id="7abbb-175">新增全域系統管理員、安全性系統管理員和/或安全性讀者，他們應會收到人員向 Microsoft 回報告的每封電子郵件複本，然後選擇 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-175">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span>

   ![新增全域或安全性系統管理員，以接收每個報告郵件的複本](../media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)

8. <span data-ttu-id="7abbb-177">選取 [以嚴重性等級稽核此規則]\*\*\*\*，然後選擇 [中]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-177">Select **Audit this rule with severity level**, and choose **Medium**.</span></span>

9. <span data-ttu-id="7abbb-178">在 [選擇此規則的模式]\*\*\*\* 底下，選擇 [強制執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-178">Under **Choose a mode for this rule**, choose **Enforce**.</span></span>

   ![設定規則以取得每個報告的訊息複本](../media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)

10. <span data-ttu-id="7abbb-180">選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7abbb-180">Choose **Save**.</span></span>

<span data-ttu-id="7abbb-181">備妥此規則後，每當貴組織中的人員使用 [報告訊息] 增益集來報告電子郵件時，您的全域系統管理員、安全性系統管理員和/或安全性讀者將會收到該郵件的複本。</span><span class="sxs-lookup"><span data-stu-id="7abbb-181">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message.</span></span> <span data-ttu-id="7abbb-182">此資訊可讓您設定或調整原則，例如 [Office 365 ATP 安全連結](atp-safe-links.md)原則，或[反垃圾郵件](anti-spam-protection.md)設定。</span><span class="sxs-lookup"><span data-stu-id="7abbb-182">This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span>

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="7abbb-183">了解如何使用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="7abbb-183">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="7abbb-184">請參閱[使用報告訊息增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="7abbb-184">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="7abbb-185">檢閱或編輯報告訊息增益集的設定</span><span class="sxs-lookup"><span data-stu-id="7abbb-185">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="7abbb-186">您可以在[服務與增益集頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)上檢閱及編輯 [報告訊息] 增益集的預設設定。</span><span class="sxs-lookup"><span data-stu-id="7abbb-186">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7abbb-187">您必須是 Office 365 全域系統管理員或 Exchange Online 系統管理員才能完成此工作。</span><span class="sxs-lookup"><span data-stu-id="7abbb-187">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>

1. <span data-ttu-id="7abbb-188">移至 Microsoft 365 系統管理中心的[服務與增益集頁面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="7abbb-188">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![新 Microsoft 365 系統管理中心的服務和增益集頁面](../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="7abbb-190">尋找並選取報告訊息增益集。</span><span class="sxs-lookup"><span data-stu-id="7abbb-190">Find and select the Report Message add-in.</span></span>

   ![尋找並選取報告訊息增益集](../media/FindReportMessageAddIn.png)

3. <span data-ttu-id="7abbb-192">在 [報告訊息] 畫面上，檢閱及編輯您組織的相關設定。</span><span class="sxs-lookup"><span data-stu-id="7abbb-192">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span>

   ![報告訊息增益集的設定](../media/EditReportMessageAddIn.png)

## <a name="related-topics"></a><span data-ttu-id="7abbb-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="7abbb-194">Related topics</span></span>

[<span data-ttu-id="7abbb-195">使用報告訊息增益集</span><span class="sxs-lookup"><span data-stu-id="7abbb-195">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

[<span data-ttu-id="7abbb-196">檢視安全性與合規性中心內的電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="7abbb-196">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="7abbb-197">檢視 Office 365 進階威脅防護的報告</span><span class="sxs-lookup"><span data-stu-id="7abbb-197">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="7abbb-198">使用安全性與合規性中心的總管</span><span class="sxs-lookup"><span data-stu-id="7abbb-198">Use Explorer in the Security &amp; Compliance Center</span></span>](threat-explorer.md)
