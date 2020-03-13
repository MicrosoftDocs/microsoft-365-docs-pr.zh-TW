---
title: Office 365 ATP 中的攻擊模擬器
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: 使用攻擊模擬器，在您的 Office 365 E5 或 ATP 方案2組織中執行模擬網路釣魚和密碼攻擊，這可協助您識別遭到攻擊的使用者，在實際的攻擊擊中您的業務之前。
ms.openlocfilehash: 5e924ebe43a6d7fd1af460b304e862207baffb61
ms.sourcegitcommit: 9afcc63b1a7e73f6946f67207337f10b71a5d7f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2020
ms.locfileid: "42612633"
---
# <a name="attack-simulator-in-office-365-atp"></a><span data-ttu-id="a2f48-103">Office 365 ATP 中的攻擊模擬器</span><span class="sxs-lookup"><span data-stu-id="a2f48-103">Attack Simulator in Office 365 ATP</span></span>

<span data-ttu-id="a2f48-104">Office 365 中的攻擊模擬器高級威脅防護方案2（ATP 方案2）可讓您在組織中執行實際的網路釣魚網站和密碼攻擊活動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-104">Attack Simulator in Office 365 Advanced Threat Protection Plan 2 (ATP Plan 2) allows you to run realistic, but simulated phishing and password attack campaigns in your organization.</span></span> <span data-ttu-id="a2f48-105">您可以使用行銷活動的結果來識別及訓練有缺陷的使用者。</span><span class="sxs-lookup"><span data-stu-id="a2f48-105">You can use the results of campaigns to identify and train vulnerable users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a2f48-106">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="a2f48-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a2f48-107">若要開啟 Office 365 安全性 & 規範中心，請移<https://protection.office.com/>至。</span><span class="sxs-lookup"><span data-stu-id="a2f48-107">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="a2f48-108">攻擊模擬器可在**威脅管理** \> **攻擊模擬器**中取得。</span><span class="sxs-lookup"><span data-stu-id="a2f48-108">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![威脅管理-攻擊模擬器](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="a2f48-110">如需不同 Office 365 訂閱中攻擊模擬器可用性的相關資訊，請參閱[Office 365 高級威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="a2f48-110">For more information about the availability of Attack Simulator across different Office 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="a2f48-111">您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a2f48-111">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="a2f48-112">如需安全性 & 規範中心中角色群組的詳細資訊，請參閱[Office 365 安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a2f48-112">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="a2f48-113">您的帳戶必須設定為多重要素驗證（MFA）以在攻擊模擬器中建立及管理活動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-113">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="a2f48-114">如需相關指示，請參閱[設定多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="a2f48-114">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="a2f48-115">您只能在具有 Exchange Online 信箱的使用者上執行網路釣魚或密碼攻擊活動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-115">You can only run phishing or password attack campaigns on users with mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="a2f48-116">網路釣魚活動會收集事件，並處理30天的事件。</span><span class="sxs-lookup"><span data-stu-id="a2f48-116">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="a2f48-117">在您啟動市場活動之後，歷史活動資料將可長達90天。</span><span class="sxs-lookup"><span data-stu-id="a2f48-117">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="a2f48-118">攻擊模擬程式沒有對應的 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a2f48-118">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="a2f48-119">Spear 網路釣魚活動</span><span class="sxs-lookup"><span data-stu-id="a2f48-119">Spear phishing campaigns</span></span>

<span data-ttu-id="a2f48-120">*網路釣魚*是一種常見的電子郵件攻擊術語，可嘗試竊取看似來自合法或信任寄件者的郵件中的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="a2f48-120">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="a2f48-121">*Spear 網路釣魚*是一個目標網路釣魚攻擊，其使用專門為目標收件者量身定制的專門和自訂內容（通常是攻擊者在收件者上的偵測之後）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-121">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="a2f48-122">如需有關網路釣魚和 spear 網路釣魚的詳細資訊，請參閱[仿冒](https://docs.microsoft.com/windows/security/threat-protection/intelligence/phishing)。</span><span class="sxs-lookup"><span data-stu-id="a2f48-122">For more information about phishing and spear phishing, see [Phishing](https://docs.microsoft.com/windows/security/threat-protection/intelligence/phishing).</span></span>

<span data-ttu-id="a2f48-123">在攻擊模擬器中，有兩種不同類型的 spear 網路釣魚活動可供使用：</span><span class="sxs-lookup"><span data-stu-id="a2f48-123">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="a2f48-124">**Spear 網路釣魚（認證搜集）**：攻擊會嘗試說服收件者按一下郵件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="a2f48-124">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="a2f48-125">如果他們按一下連結，則會要求使用者輸入他們的認證。</span><span class="sxs-lookup"><span data-stu-id="a2f48-125">If they click the link, users are asked to enter their credentials.</span></span> <span data-ttu-id="a2f48-126">如果是的話，它們會移至下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="a2f48-126">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="a2f48-127">說明這種情況的預設頁面只是測試，並提供識別網路釣魚郵件的秘訣。</span><span class="sxs-lookup"><span data-stu-id="a2f48-127">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![使用者按一下 [網路釣魚] 連結並輸入其認證時看到的內容](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="a2f48-129">您指定的自訂頁面（URL）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-129">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="a2f48-130">**Spear 網路釣魚（附件）**：攻擊會嘗試說服收件者在郵件中開啟 .docx 或 .pdf 附件。</span><span class="sxs-lookup"><span data-stu-id="a2f48-130">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="a2f48-131">附件包含來自預設網路釣魚連結的相同內容，但是第一個句子會以 "\<顯示名稱\>，您會看到此郵件為您所開啟的最近電子郵件訊息 ..."。</span><span class="sxs-lookup"><span data-stu-id="a2f48-131">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="a2f48-132">目前，攻擊模擬器中的 spear 網路釣魚活動不會過期。</span><span class="sxs-lookup"><span data-stu-id="a2f48-132">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="a2f48-133">建立 spear 網路釣魚活動</span><span class="sxs-lookup"><span data-stu-id="a2f48-133">Create a spear phishing campaign</span></span>

<span data-ttu-id="a2f48-134">任何 spear 網路釣魚活動的重要部分是傳送給目標收件者之電子郵件的外觀與風格。</span><span class="sxs-lookup"><span data-stu-id="a2f48-134">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="a2f48-135">若要建立及設定電子郵件訊息，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="a2f48-135">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="a2f48-136">**使用內建的電子郵件範本**：有兩個內建的範本可供使用：**獎品 Giveaway**和**工資單更新**。</span><span class="sxs-lookup"><span data-stu-id="a2f48-136">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="a2f48-137">您可以在建立及啟動市場活動時，進一步自訂範本中的部分、全部或無電子郵件屬性。</span><span class="sxs-lookup"><span data-stu-id="a2f48-137">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="a2f48-138">**建立可重複使用的電子郵件範本**：在您建立及儲存電子郵件範本之後，您可以在未來 spear 網路釣魚活動中再次使用它。</span><span class="sxs-lookup"><span data-stu-id="a2f48-138">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="a2f48-139">您可以在建立及啟動市場活動時，進一步自訂範本中的部分、全部或無電子郵件屬性。</span><span class="sxs-lookup"><span data-stu-id="a2f48-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="a2f48-140">**在嚮導中建立電子郵件訊息**：當您建立及啟動 spear 網路釣魚活動時，您可以直接在嚮導中建立電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="a2f48-140">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="a2f48-141">步驟1（選用）：建立自訂的電子郵件範本</span><span class="sxs-lookup"><span data-stu-id="a2f48-141">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="a2f48-142">若要使用其中一個內建範本或直接在嚮導中建立電子郵件訊息，您可以略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="a2f48-142">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="a2f48-143">在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> ]**攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="a2f48-143">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="a2f48-144">在 [**模擬攻擊**] 頁面的 [ **Spear 網路釣魚（身分驗證）** ] 或 [ **Spear 網路釣魚（附件）** ] 區段中，按一下 [**攻擊詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="a2f48-144">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="a2f48-145">您建立範本的方式無關緊要。</span><span class="sxs-lookup"><span data-stu-id="a2f48-145">It doesn't matter where you create the template.</span></span> <span data-ttu-id="a2f48-146">範本中的可用選項與這兩種類型的網路釣魚攻擊相同。</span><span class="sxs-lookup"><span data-stu-id="a2f48-146">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="a2f48-147">在開啟的 [**攻擊詳細資料**] 頁面中，于 [**網路釣魚範本**] 區段的 [**建立範本**] 區域中，按一下 [**新增範本**]。</span><span class="sxs-lookup"><span data-stu-id="a2f48-147">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="a2f48-148">**設定網路釣魚範本**嚮導會在新飛入的視窗中啟動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-148">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="a2f48-149">在 [**開始**] 步驟中，輸入範本的唯一顯示名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a2f48-149">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="a2f48-150">在 [**設定電子郵件詳細資料**] 步驟中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a2f48-150">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="a2f48-151">**From （Name）**：郵件寄件者所用的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="a2f48-151">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="a2f48-152">寄件者 **（電子郵件）**：寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a2f48-152">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="a2f48-153">**網路釣魚登入伺服器 URL**：按一下下拉式清單，然後從清單中選取其中一個可用的 URLs。</span><span class="sxs-lookup"><span data-stu-id="a2f48-153">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="a2f48-154">這是使用者將被誘惑按一下的 URL。</span><span class="sxs-lookup"><span data-stu-id="a2f48-154">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="a2f48-155">選項包括：</span><span class="sxs-lookup"><span data-stu-id="a2f48-155">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     > <ul><li><span data-ttu-id="a2f48-156">所有的 URLs 都是特意 HTTP，而不是 HTTPs。</span><span class="sxs-lookup"><span data-stu-id="a2f48-156">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="a2f48-157">URL 信譽服務可識別一或多個 URLs 為不安全的。</span><span class="sxs-lookup"><span data-stu-id="a2f48-157">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="a2f48-158">在網路釣魚活動中使用 URL 之前，請先檢查支援的網頁瀏覽器中的 URL 可用性。</span><span class="sxs-lookup"><span data-stu-id="a2f48-158">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="a2f48-159">**自訂登陸頁面 URL**：輸入使用者在按一下 [網路釣魚] 連結並輸入其認證時所採用的選用登陸頁面。</span><span class="sxs-lookup"><span data-stu-id="a2f48-159">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="a2f48-160">此連結會取代預設登陸頁面。</span><span class="sxs-lookup"><span data-stu-id="a2f48-160">This link replaces the default landing page.</span></span> <span data-ttu-id="a2f48-161">例如，如果您有內部的知識意識訓練，您可以在這裡指定該 URL。</span><span class="sxs-lookup"><span data-stu-id="a2f48-161">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="a2f48-162">**類別**：目前未使用此設定（忽略您輸入的任何專案）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-162">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="a2f48-163">主旨 **：電子**郵件的**主旨欄位。**</span><span class="sxs-lookup"><span data-stu-id="a2f48-163">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="a2f48-164">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2f48-164">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a2f48-165">在 [**撰寫電子郵件**] 步驟中，建立電子郵件訊息的郵件內文。</span><span class="sxs-lookup"><span data-stu-id="a2f48-165">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="a2f48-166">您可以使用 [**電子郵件**] 索引標籤（豐富的 html 編輯器）或 [**來源**] 索引標籤（原始 HTML 程式碼）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-166">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="a2f48-167">HTML 格式設定可以簡單或複雜，您必須在需要時。</span><span class="sxs-lookup"><span data-stu-id="a2f48-167">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="a2f48-168">您可以插入影像和文字，以在收件者的電子郵件客戶程式中增強郵件的 believability。</span><span class="sxs-lookup"><span data-stu-id="a2f48-168">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="a2f48-169">`${username}`插入收件者的名稱。</span><span class="sxs-lookup"><span data-stu-id="a2f48-169">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="a2f48-170">`${loginserverurl}`插入上一個步驟中的**網路釣魚登入伺服器 URL**值。</span><span class="sxs-lookup"><span data-stu-id="a2f48-170">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="a2f48-171">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2f48-171">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="a2f48-172">在 [**確認**] 步驟中，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a2f48-172">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="a2f48-173">步驟2：建立及啟動 spear 網路釣魚活動</span><span class="sxs-lookup"><span data-stu-id="a2f48-173">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="a2f48-174">在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> ]**攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="a2f48-174">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="a2f48-175">在 [**模擬攻擊**] 頁面上，根據您要建立的活動類型進行下列其中一項選擇：</span><span class="sxs-lookup"><span data-stu-id="a2f48-175">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="a2f48-176">在 [ **Spear 網路釣魚（認證收集）** ] 區段中，按一下 [**啟動攻擊**] 或按一下 [**攻擊詳細資料** \> **啟動攻擊**]。</span><span class="sxs-lookup"><span data-stu-id="a2f48-176">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="a2f48-177">在 [ **Spear 網路釣魚（附件）** ] 區段中，按一下 [**啟動攻擊**] 或按一下 [**攻擊詳細資料** \> **啟動攻擊**]。</span><span class="sxs-lookup"><span data-stu-id="a2f48-177">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="a2f48-178">**設定網路釣魚攻擊**嚮導會在新飛入的視窗中啟動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-178">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="a2f48-179">在 [**開始**] 步驟中，執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="a2f48-179">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="a2f48-180">在 [**名稱**] 方塊中，輸入活動的唯一顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="a2f48-180">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="a2f48-181">請勿按一下 [**使用範本**]，因為您將在嚮導稍後建立電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="a2f48-181">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="a2f48-182">按一下 [**使用範本**]，然後選取內建或自訂的電子郵件範本。</span><span class="sxs-lookup"><span data-stu-id="a2f48-182">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="a2f48-183">選取範本之後，[**名稱**] 方塊會根據範本自動填滿，但您可以變更名稱。</span><span class="sxs-lookup"><span data-stu-id="a2f48-183">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![網路釣魚開始頁面](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="a2f48-185">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2f48-185">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a2f48-186">在 [**目標**收件者] 步驟中，執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="a2f48-186">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="a2f48-187">按一下 [**通訊錄**] 以選取市場活動的收件者（使用者或群組）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-187">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="a2f48-188">每個目標收件者都必須有 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="a2f48-188">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="a2f48-189">如果您按一下 [**篩選**] 並套用但未輸入搜尋準則，則會傳回所有收件者，**並將其**新增至市場活動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-189">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="a2f48-190">按一下 **[匯入]** ，然後匯入**檔**匯入逗號分隔值（CSV）或電子郵件地址的行分隔檔。</span><span class="sxs-lookup"><span data-stu-id="a2f48-190">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="a2f48-191">每一行都必須包含收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a2f48-191">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="a2f48-192">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2f48-192">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a2f48-193">在 [**設定電子郵件詳細資料**] 步驟中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a2f48-193">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="a2f48-194">如果您在 [**開始**] 步驟中選取了範本，則這些值中的大部分已設定好，但您可以加以變更。</span><span class="sxs-lookup"><span data-stu-id="a2f48-194">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="a2f48-195">**From （Name）**：郵件寄件者所用的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="a2f48-195">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="a2f48-196">寄件者 **（電子郵件）**：寄件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a2f48-196">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="a2f48-197">您可以從組織的電子郵件網域輸入實際或虛假的電子郵件地址，也可以輸入實際或虛假的外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a2f48-197">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="a2f48-198">您組織中的有效寄件者電子郵件地址會在收件者的電子郵件客戶程式中實際解析。</span><span class="sxs-lookup"><span data-stu-id="a2f48-198">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="a2f48-199">**網路釣魚登入伺服器 URL**：按一下下拉式清單，然後從清單中選取其中一個可用的 URLs。</span><span class="sxs-lookup"><span data-stu-id="a2f48-199">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="a2f48-200">這是使用者將被誘惑按一下的 URL。</span><span class="sxs-lookup"><span data-stu-id="a2f48-200">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="a2f48-201">選項包括：</span><span class="sxs-lookup"><span data-stu-id="a2f48-201">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     > <ul><li><span data-ttu-id="a2f48-202">所有的 URLs 都是特意 HTTP，而不是 HTTPs。</span><span class="sxs-lookup"><span data-stu-id="a2f48-202">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="a2f48-203">URL 信譽服務可識別一或多個 URLs 為不安全的。</span><span class="sxs-lookup"><span data-stu-id="a2f48-203">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="a2f48-204">在網路釣魚活動中使用 URL 之前，請先檢查支援的網頁瀏覽器中的 URL 可用性。</span><span class="sxs-lookup"><span data-stu-id="a2f48-204">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="a2f48-205">您必須選取 URL。</span><span class="sxs-lookup"><span data-stu-id="a2f48-205">You are required to select a URL.</span></span> <span data-ttu-id="a2f48-206">針對**Spear 網路釣魚（附件）** 活動，您可以在下一個步驟中移除郵件本文中的連結（否則，郵件會同時包含連結**和**附件）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-206">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span></li></ul>

   - <span data-ttu-id="a2f48-207">**附件類型**：此設定僅適用于**Spear 網路釣魚（附件）** 活動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-207">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="a2f48-208">按一下下拉式清單，然後選取 **。.DOCX**或 **。PDF**中的清單。</span><span class="sxs-lookup"><span data-stu-id="a2f48-208">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="a2f48-209">**附件名稱**：此設定僅適用于**Spear 網路釣魚（附件）** 活動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-209">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="a2f48-210">輸入 .docx 或 .pdf 附件的檔案名。</span><span class="sxs-lookup"><span data-stu-id="a2f48-210">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="a2f48-211">**自訂登陸頁面 URL**：輸入使用者在按一下 [網路釣魚] 連結並輸入其認證時所採用的選用登陸頁面。</span><span class="sxs-lookup"><span data-stu-id="a2f48-211">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="a2f48-212">此連結會取代預設登陸頁面。</span><span class="sxs-lookup"><span data-stu-id="a2f48-212">This link replaces the default landing page.</span></span> <span data-ttu-id="a2f48-213">例如，如果您有內部的知識意識訓練，您可以在這裡指定該 URL。</span><span class="sxs-lookup"><span data-stu-id="a2f48-213">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="a2f48-214">主旨 **：電子**郵件的**主旨欄位。**</span><span class="sxs-lookup"><span data-stu-id="a2f48-214">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="a2f48-215">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2f48-215">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a2f48-216">在 [**撰寫電子郵件**] 步驟中，建立電子郵件訊息的郵件內文。</span><span class="sxs-lookup"><span data-stu-id="a2f48-216">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="a2f48-217">如果您在 [**開始**] 步驟中選取了範本，則會已設定郵件內文，但您可以進行自訂。</span><span class="sxs-lookup"><span data-stu-id="a2f48-217">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="a2f48-218">您可以使用 [**電子郵件**] 索引標籤（豐富的 html 編輯器）或 [**來源**] 索引標籤（原始 HTML 程式碼）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-218">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="a2f48-219">HTML 格式設定可以簡單或複雜，您必須在需要時。</span><span class="sxs-lookup"><span data-stu-id="a2f48-219">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="a2f48-220">您可以插入影像和文字，以在收件者的電子郵件客戶程式中增強郵件的 believability。</span><span class="sxs-lookup"><span data-stu-id="a2f48-220">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="a2f48-221">`${username}`插入收件者的名稱。</span><span class="sxs-lookup"><span data-stu-id="a2f48-221">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="a2f48-222">`${loginserverurl}`插入**網路釣魚登入伺服器 URL**值。</span><span class="sxs-lookup"><span data-stu-id="a2f48-222">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="a2f48-223">針對**Spear 網路釣魚（附件）** 活動，您應該從郵件的本文中移除連結（否則，郵件會同時包含連結**和**附件，而且不會在附件活動中追蹤連結按一下）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-223">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![撰寫電子郵件內文](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="a2f48-225">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2f48-225">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="a2f48-226">在 [**確認**] 步驟中，按一下 **[完成]** 以啟動市場活動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-226">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="a2f48-227">網路釣魚郵件會傳遞給目標收件者。</span><span class="sxs-lookup"><span data-stu-id="a2f48-227">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="a2f48-228">密碼攻擊活動</span><span class="sxs-lookup"><span data-stu-id="a2f48-228">Password attack campaigns</span></span>

<span data-ttu-id="a2f48-229">*密碼攻擊*會嘗試猜測組織中使用者帳戶的密碼，通常是在攻擊者識別一或多個有效的使用者帳戶之後。</span><span class="sxs-lookup"><span data-stu-id="a2f48-229">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="a2f48-230">在攻擊模擬器中，有兩種不同類型的密碼攻擊活動可供您測試使用者密碼的複雜性：</span><span class="sxs-lookup"><span data-stu-id="a2f48-230">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="a2f48-231">**強力密碼（字典攻擊）**：*強力強制*\* 或*字典*攻擊會在使用者帳戶上使用大量的密碼字典檔案，讓您能夠使用其中一種密碼，這樣一來，您就可以使用其中一個，而不是一個帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="a2f48-231">**Brute force password (dictionary attack)**: A *brute force*\* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="a2f48-232">不正確的密碼鎖定有助於封鎖強力密碼攻擊。</span><span class="sxs-lookup"><span data-stu-id="a2f48-232">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="a2f48-233">針對字典攻擊，您可以指定一或多個密碼以嘗試（手動輸入或上傳的檔案），也可以指定一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="a2f48-233">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="a2f48-234">**密碼噴塗攻擊**：*密碼噴塗*攻擊會使用相同的使用者帳戶清單（對許多帳戶都有一個密碼）進行認真考慮的密碼。</span><span class="sxs-lookup"><span data-stu-id="a2f48-234">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="a2f48-235">密碼噴塗攻擊比強力強制密碼攻擊更難偵測（當攻擊者在數十或數百個帳戶間嘗試一個密碼時，成功的可能性也會增加，而不會造成使用者不正確的密碼鎖定的危險）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-235">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="a2f48-236">在密碼噴塗攻擊中，您只能指定一個密碼進行嘗試，也可以指定一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="a2f48-236">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="a2f48-237">攻擊模擬器中的密碼攻擊會將使用者名稱和密碼基本身分驗證要求傳遞給端點，讓使用者也可以使用其他驗證方法（AD FS、密碼雜湊同步處理、傳遞-PingFederate 等）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-237">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="a2f48-238">針對已啟用 MFA 的使用者，即使密碼攻擊嘗試其實際密碼，該嘗試總會會註冊失敗（換言之，MFA 使用者永遠不會出現在活動的**成功嘗試**計數中）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-238">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="a2f48-239">這是預期的結果。</span><span class="sxs-lookup"><span data-stu-id="a2f48-239">This is the expected result.</span></span> <span data-ttu-id="a2f48-240">MFA 是協助防護密碼攻擊的主要方法。</span><span class="sxs-lookup"><span data-stu-id="a2f48-240">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="a2f48-241">建立及啟動密碼攻擊活動</span><span class="sxs-lookup"><span data-stu-id="a2f48-241">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="a2f48-242">在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> ]**攻擊模擬器**。</span><span class="sxs-lookup"><span data-stu-id="a2f48-242">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="a2f48-243">在 [**模擬攻擊**] 頁面上，根據您要建立的活動類型進行下列其中一項選擇：</span><span class="sxs-lookup"><span data-stu-id="a2f48-243">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="a2f48-244">在 [**暴力密碼（字典攻擊）** ] 區段中，按一下 [**啟動攻擊**] 或按一下 [**攻擊詳細資料** \> **啟動攻擊**]。</span><span class="sxs-lookup"><span data-stu-id="a2f48-244">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="a2f48-245">在 [**密碼噴塗攻擊**] 區段中，按一下 [**啟動攻擊**] 或按一下 [**攻擊詳細資料** \> **啟動攻擊**]。</span><span class="sxs-lookup"><span data-stu-id="a2f48-245">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="a2f48-246">**設定密碼攻擊**嚮導會在新飛入的視窗中啟動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-246">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="a2f48-247">在 [**開始**] 步驟中，輸入活動的唯一顯示名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a2f48-247">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="a2f48-248">在 [**目標使用者**] 步驟中，執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="a2f48-248">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="a2f48-249">按一下 [**通訊錄**] 以選取市場活動的收件者（使用者或群組）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-249">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="a2f48-250">每個目標收件者都必須有 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="a2f48-250">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="a2f48-251">如果您按一下 [**篩選**] 並套用但未輸入搜尋準則，則會傳回所有收件者，**並將其**新增至市場活動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-251">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="a2f48-252">按一下 **[匯入]** ，然後匯入**檔**匯入逗號分隔值（CSV）或電子郵件地址的行分隔檔。</span><span class="sxs-lookup"><span data-stu-id="a2f48-252">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="a2f48-253">每一行都必須包含收件者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a2f48-253">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="a2f48-254">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2f48-254">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a2f48-255">在 [**選擇攻擊設定**] 步驟中，選擇根據行銷活動類型執行的動作：</span><span class="sxs-lookup"><span data-stu-id="a2f48-255">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="a2f48-256">**強力密碼（字典攻擊）**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="a2f48-256">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="a2f48-257">**手動輸入密碼**：在**按 enter 鍵以新增密碼**方塊中，輸入密碼，然後按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="a2f48-257">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="a2f48-258">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="a2f48-258">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="a2f48-259">**從字典檔案上傳密碼**：按一下 **[上傳**]，可匯入在每一行上包含一個密碼的現有文字檔，以及一個空白的最後一行。</span><span class="sxs-lookup"><span data-stu-id="a2f48-259">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="a2f48-260">文字檔的大小必須為 10 MB 或以下，而且不能包含30000個以上的密碼。</span><span class="sxs-lookup"><span data-stu-id="a2f48-260">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="a2f48-261">**密碼噴塗攻擊**：在 [**攻擊中使用的密碼**] 方塊中，輸入一個密碼。</span><span class="sxs-lookup"><span data-stu-id="a2f48-261">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="a2f48-262">完成後，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2f48-262">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a2f48-263">在 [**確認**] 步驟中，按一下 **[完成]** 以啟動市場活動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-263">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="a2f48-264">您指定的密碼會嘗試您指定的使用者。</span><span class="sxs-lookup"><span data-stu-id="a2f48-264">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="a2f48-265">查看市場活動結果</span><span class="sxs-lookup"><span data-stu-id="a2f48-265">View campaign results</span></span>

<span data-ttu-id="a2f48-266">啟動活動之後，您可以在 [主要**模擬攻擊**] 頁面上檢查進度和結果。</span><span class="sxs-lookup"><span data-stu-id="a2f48-266">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="a2f48-267">使用中的活動會顯示狀態列、完成百分比值及（全部使用者） "（已完成的使用者）" 計數。</span><span class="sxs-lookup"><span data-stu-id="a2f48-267">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="a2f48-268">按一下 [重新整理] 按鈕，會更新任何使用**中的活動**活動的進度。</span><span class="sxs-lookup"><span data-stu-id="a2f48-268">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="a2f48-269">您也可以按一下 [**終止**]，以停止使用中的活動。</span><span class="sxs-lookup"><span data-stu-id="a2f48-269">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="a2f48-270">當市場活動完成時，狀態變更為 [**攻擊已完成**]。</span><span class="sxs-lookup"><span data-stu-id="a2f48-270">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="a2f48-271">您可以執行下列其中一項動作，以查看活動的結果：</span><span class="sxs-lookup"><span data-stu-id="a2f48-271">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="a2f48-272">在 [主**模擬攻擊**] 頁面上，按一下 [活動名稱] 底下的 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="a2f48-272">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="a2f48-273">在「主要**模擬攻擊**」頁面上，按一下該攻擊類型區段中的 [**攻擊詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="a2f48-273">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="a2f48-274">在開啟的 [**攻擊詳細資料**] 頁面上，選取 [**攻擊歷程記錄**] 區段中的 [活動]。</span><span class="sxs-lookup"><span data-stu-id="a2f48-274">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="a2f48-275">上述任一項動作都會帶您前往名為 [**攻擊詳細資料**] 的頁面。</span><span class="sxs-lookup"><span data-stu-id="a2f48-275">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="a2f48-276">以下各節將說明此頁面上針對每種類型的活動所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="a2f48-276">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="a2f48-277">Spear 網路釣魚（認證收集）活動結果</span><span class="sxs-lookup"><span data-stu-id="a2f48-277">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="a2f48-278">每個活動的 [**攻擊詳細資料**] 頁面上提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a2f48-278">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="a2f48-279">市場活動的持續時間（開始日期/時間和結束日期/時間）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-279">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="a2f48-280">**目標使用者總數**</span><span class="sxs-lookup"><span data-stu-id="a2f48-280">**Total users targeted**</span></span>

- <span data-ttu-id="a2f48-281">**嘗試成功**：按一下連結的使用者人數 **，並**輸入其認證（*任何*使用者名稱和密碼值）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-281">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="a2f48-282">**整體成功率**：以**成功嘗試** / 為**目標之使用者總數**所計算的百分比。</span><span class="sxs-lookup"><span data-stu-id="a2f48-282">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="a2f48-283">**最快速按一下**：在您啟動市場活動之後，第一位使用者按一下連結所花費的時間。</span><span class="sxs-lookup"><span data-stu-id="a2f48-283">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="a2f48-284">**平均按一下**：每個人依序按一下連結所花費的時間與按一下連結的使用者數目的總和。</span><span class="sxs-lookup"><span data-stu-id="a2f48-284">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="a2f48-285">**按一下 [成功率**：所計算的百分比（即按一下連結的使用者人數]）/[**使用者總數**]。</span><span class="sxs-lookup"><span data-stu-id="a2f48-285">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="a2f48-286">**最快的認證**：在您啟動市場活動之後，第一位使用者進入其認證所需的時間。</span><span class="sxs-lookup"><span data-stu-id="a2f48-286">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="a2f48-287">**平均認證**：每個人輸入認證所花費的時間，除以輸入其認證的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="a2f48-287">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="a2f48-288">**認證成功率**：所計算的百分比（即輸入其認證的使用者人數）/**目標使用者總數**。</span><span class="sxs-lookup"><span data-stu-id="a2f48-288">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="a2f48-289">顯示**連結已按一下**的柱狀圖圖，以及每日所**提供的憑證**數量。</span><span class="sxs-lookup"><span data-stu-id="a2f48-289">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="a2f48-290">圓形圖，顯示所**按一下的連結**、**提供的認證**，以及**無**活動的百分比。</span><span class="sxs-lookup"><span data-stu-id="a2f48-290">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="a2f48-291">「已**遭破壞的使用者**」區段會列出按一下連結之使用者的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="a2f48-291">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="a2f48-292">使用者的電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="a2f48-292">The user's email address</span></span>

  - <span data-ttu-id="a2f48-293">按一下連結時的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="a2f48-293">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="a2f48-294">用戶端 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a2f48-294">The client IP address.</span></span>

  - <span data-ttu-id="a2f48-295">使用者版本的 Windows 和網頁瀏覽器的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a2f48-295">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="a2f48-296">您可以按一下 [**匯出**]，將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="a2f48-296">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="a2f48-297">Spear 網路釣魚（附件）的活動結果</span><span class="sxs-lookup"><span data-stu-id="a2f48-297">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="a2f48-298">每個活動的 [**攻擊詳細資料**] 頁面上提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a2f48-298">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="a2f48-299">市場活動的持續時間（開始日期/時間和結束日期/時間）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-299">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="a2f48-300">**目標使用者總數**</span><span class="sxs-lookup"><span data-stu-id="a2f48-300">**Total users targeted**</span></span>

- <span data-ttu-id="a2f48-301">**嘗試成功**：開啟或下載及開啟附件的使用者人數（預覽不會計數）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-301">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="a2f48-302">**整體成功率**：以**成功嘗試** / 為**目標之使用者總數**所計算的百分比。</span><span class="sxs-lookup"><span data-stu-id="a2f48-302">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="a2f48-303">**最快捷的附件開啟時間**：啟動市場活動之後，第一位使用者開啟附件所花費的時間。</span><span class="sxs-lookup"><span data-stu-id="a2f48-303">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="a2f48-304">**平均附件開啟時間**：每個人開啟附件所花費的時間除以開啟附件的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="a2f48-304">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="a2f48-305">**附件開啟成功率**：所計算的百分比（開啟附件的使用者人數）/**目標使用者總數**。</span><span class="sxs-lookup"><span data-stu-id="a2f48-305">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="a2f48-306">強力密碼（字典攻擊）活動結果</span><span class="sxs-lookup"><span data-stu-id="a2f48-306">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="a2f48-307">每個活動的 [**攻擊詳細資料**] 頁面上提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a2f48-307">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="a2f48-308">市場活動的持續時間（開始日期/時間和結束日期/時間）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-308">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="a2f48-309">**目標使用者總數**</span><span class="sxs-lookup"><span data-stu-id="a2f48-309">**Total users targeted**</span></span>

- <span data-ttu-id="a2f48-310">**嘗試成功**：發現使用其中一個指定密碼的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="a2f48-310">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="a2f48-311">**整體成功率**：以**成功嘗試** / 為**目標之使用者總數**所計算的百分比。</span><span class="sxs-lookup"><span data-stu-id="a2f48-311">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="a2f48-312">「已**遭破壞的使用者**」區段會列出受影響使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a2f48-312">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="a2f48-313">您可以按一下 [**匯出**]，將結果匯出至 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="a2f48-313">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="a2f48-314">密碼噴塗攻擊活動結果</span><span class="sxs-lookup"><span data-stu-id="a2f48-314">Password spray attack campaign results</span></span>

<span data-ttu-id="a2f48-315">每個活動的 [**攻擊詳細資料**] 頁面上提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a2f48-315">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="a2f48-316">市場活動的持續時間（開始日期/時間和結束日期/時間）。</span><span class="sxs-lookup"><span data-stu-id="a2f48-316">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="a2f48-317">**目標使用者總數**</span><span class="sxs-lookup"><span data-stu-id="a2f48-317">**Total users targeted**</span></span>

- <span data-ttu-id="a2f48-318">**嘗試成功**：找到的使用者人數是使用指定的密碼。</span><span class="sxs-lookup"><span data-stu-id="a2f48-318">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="a2f48-319">**整體成功率**：以**成功嘗試** / 為**目標之使用者總數**所計算的百分比。</span><span class="sxs-lookup"><span data-stu-id="a2f48-319">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
