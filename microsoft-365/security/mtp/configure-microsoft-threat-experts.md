---
title: 透過 Microsoft 365 Defender 設定及管理 Microsoft 威脅專家功能
description: 透過 Microsoft 365 Defender 訂閱 Microsoft 威脅專家，以在您的日常安全性作業和安全性管理工作中設定、管理及使用該功能。
keywords: Microsoft 威脅專家、受管理的威脅搜尋服務、MTE、Microsoft managed 搜尋服務
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
localization_priority: normal
manager: dansimp
audience: ITPro
ms.topic: article
ms.openlocfilehash: 38bf768f1a5603fa3da0d7a3acc8f409ed6372de
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765524"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a><span data-ttu-id="a93ef-104">透過 Microsoft 365 Defender 設定及管理 Microsoft 威脅專家功能</span><span class="sxs-lookup"><span data-stu-id="a93ef-104">Configure and manage Microsoft Threat Experts capabilities through Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a93ef-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a93ef-105">**Applies to:**</span></span>

- [<span data-ttu-id="a93ef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a93ef-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="a93ef-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a93ef-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="a93ef-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="a93ef-108">Before you begin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a93ef-109">在您套用之前，請務必與您的 Microsoft 技術服務提供者和客戶團隊討論 Microsoft 威脅專家的資格需求–目標攻擊通知受管理的威脅搜尋服務。</span><span class="sxs-lookup"><span data-stu-id="a93ef-109">Before you apply, make sure to discuss the eligibility requirements for the Microsoft Threat Experts – Targeted Attack Notifications managed threat hunting service with your Microsoft Technical Service provider and account team.</span></span>

<span data-ttu-id="a93ef-110">若要接收已設定目標的攻擊通知，您需要在已註冊的裝置中部署 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="a93ef-110">To receive targeted attack notifications, you'll need to have Microsoft 365 Defender deployed with devices enrolled.</span></span> <span data-ttu-id="a93ef-111">然後，透過 M365 入口網站提交應用程式，以取得 Microsoft 威脅專家目標的攻擊通知。</span><span class="sxs-lookup"><span data-stu-id="a93ef-111">Then, submit an application through the M365 portal for Microsoft Threat Experts - Targeted Attack Notifications.</span></span>

<span data-ttu-id="a93ef-112">請與您的帳戶小組或 Microsoft 代表聯繫，以訂閱 Microsoft 威脅專家-點播的專家。</span><span class="sxs-lookup"><span data-stu-id="a93ef-112">Contact your account team or Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span> <span data-ttu-id="a93ef-113">需求專家可讓您向我們的威脅專家請教如何保護您的組織，避免相關的偵測和敵人。</span><span class="sxs-lookup"><span data-stu-id="a93ef-113">Experts on Demand lets you consult with our threat experts on how to protect your organization from relevant detections and adversaries.</span></span>

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a><span data-ttu-id="a93ef-114">適用于 Microsoft 威脅專家-目標攻擊通知服務</span><span class="sxs-lookup"><span data-stu-id="a93ef-114">Apply for Microsoft Threat Experts - Targeted Attack Notifications service</span></span>

<span data-ttu-id="a93ef-115">如果您已有 Microsoft Defender for Endpoint 和 Microsoft 365 Defender，您可以套用 microsoft 威脅專家–透過其 Microsoft 365 Defender 入口網站的目標攻擊通知。</span><span class="sxs-lookup"><span data-stu-id="a93ef-115">If you already have Microsoft Defender for Endpoint and Microsoft 365 Defender, you can apply for Microsoft Threat Experts – Targeted Attack Notifications through their Microsoft 365 Defender portal.</span></span>  <span data-ttu-id="a93ef-116">目標攻擊通知會授與您特殊的洞察力和分析，以協助您識別組織的最重要威脅，讓您能快速回應這些威脅。</span><span class="sxs-lookup"><span data-stu-id="a93ef-116">Targeted attack notifications grant you special insight and analysis to help identify the most critical threats to your organization, so you can respond to them quickly.</span></span>

1. <span data-ttu-id="a93ef-117">從功能窗格中，移至 [ **設定] > 端點] > 一般 > 高級功能 > Microsoft 威脅專家-已設定目標攻擊通知**。</span><span class="sxs-lookup"><span data-stu-id="a93ef-117">From the navigation pane, go to **Settings > Endpoints > General > Advanced features > Microsoft Threat Experts - Targeted Attack Notifications**.</span></span>

2. <span data-ttu-id="a93ef-118">選取 **套用**。</span><span class="sxs-lookup"><span data-stu-id="a93ef-118">Select **Apply**.</span></span>

    ![Microsoft 威脅專家設定的影像](../../media/mte/mte-collaboratewithmte.png)

3. <span data-ttu-id="a93ef-120">輸入您的名稱和電子郵件地址，讓 Microsoft 可與您聯繫您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a93ef-120">Enter your name and email address so that Microsoft can contact you about your application.</span></span>

    ![Microsoft 威脅專家應用程式的影像](../../media/mte/mte-apply.png)

4. <span data-ttu-id="a93ef-122">閱讀 [隱私權聲明](https://privacy.microsoft.com/en-us/privacystatement)，然後在完成時選取 [ **提交** ]。</span><span class="sxs-lookup"><span data-stu-id="a93ef-122">Read the [privacy statement](https://privacy.microsoft.com/en-us/privacystatement), then select **Submit** when you're done.</span></span> <span data-ttu-id="a93ef-123">您的應用程式經過核准後，您就會收到歡迎電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a93ef-123">You'll receive a welcome email once your application is approved.</span></span>

    ![Microsoft 威脅專家應用程式確認的影像](../../media/mte/mte-applicationconfirmation.png)

5. <span data-ttu-id="a93ef-125">當您收到歡迎電子郵件之後，您將會自動開始接收已設定目標的攻擊通知。</span><span class="sxs-lookup"><span data-stu-id="a93ef-125">After you receive your welcome email, you'll automatically start receiving targeted attack notifications.</span></span>

6. <span data-ttu-id="a93ef-126">您可以透過將 **設定 > 端點 > 一般 > 高級功能** 來驗證您的狀態。</span><span class="sxs-lookup"><span data-stu-id="a93ef-126">You can verify your status by visiting **Settings > Endpoints > General > Advanced features**.</span></span> <span data-ttu-id="a93ef-127">核准後， **Microsoft 威脅專家即會顯示並開啟 Microsoft 威脅專家目標的攻擊通知\*\*\*\*切換。**</span><span class="sxs-lookup"><span data-stu-id="a93ef-127">Once approved, the **Microsoft Threat Experts - Targeted Attack Notification** toggle will be visible and switched **On**.</span></span>

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a><span data-ttu-id="a93ef-128">您會看到 Microsoft 威脅專家對目標的攻擊通知</span><span class="sxs-lookup"><span data-stu-id="a93ef-128">Where you'll see the targeted attack notifications from Microsoft Threat Experts</span></span>

<span data-ttu-id="a93ef-129">您可以透過下列媒介接收來自 Microsoft 威脅專家的目標攻擊通知：</span><span class="sxs-lookup"><span data-stu-id="a93ef-129">You can receive targeted attack notification from Microsoft Threat Experts through the following mediums:</span></span>

- <span data-ttu-id="a93ef-130">Microsoft 365 Defender 入口網站的 **事件** 頁面</span><span class="sxs-lookup"><span data-stu-id="a93ef-130">The Microsoft 365 Defender portal's **Incidents** page</span></span>
- <span data-ttu-id="a93ef-131">Microsoft 365 Defender 入口網站的 **警示** 儀表板</span><span class="sxs-lookup"><span data-stu-id="a93ef-131">The Microsoft 365 Defender portal's **Alerts** dashboard</span></span>
- <span data-ttu-id="a93ef-132">OData 警示 [api](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) 和 [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span><span class="sxs-lookup"><span data-stu-id="a93ef-132">OData alerting [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) and [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span></span>
- <span data-ttu-id="a93ef-133">高級搜尋中的[DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table)表格</span><span class="sxs-lookup"><span data-stu-id="a93ef-133">[DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) table in Advanced hunting</span></span>
- <span data-ttu-id="a93ef-134">您的收件匣，如果您選擇透過電子郵件傳送目標攻擊通知給您。</span><span class="sxs-lookup"><span data-stu-id="a93ef-134">Your inbox, if you choose to have targeted attack notifications sent to you via email.</span></span> <span data-ttu-id="a93ef-135">請參閱 [Create a email notification rule](#create-an-email-notification-rule) 。</span><span class="sxs-lookup"><span data-stu-id="a93ef-135">See [Create an email notification rule](#create-an-email-notification-rule) below.</span></span>

### <a name="create-an-email-notification-rule"></a><span data-ttu-id="a93ef-136">建立電子郵件通知規則</span><span class="sxs-lookup"><span data-stu-id="a93ef-136">Create an email notification rule</span></span>

<span data-ttu-id="a93ef-137">您可以建立規則來傳送通知收件者的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="a93ef-137">You can create rules to send email notifications for notification recipients.</span></span> <span data-ttu-id="a93ef-138">如需完整的詳細資料，請參閱  [設定警示通知](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) 以建立、編輯、刪除或疑難排解電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="a93ef-138">For full details, see  [Configure alert notifications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) to create, edit, delete, or troubleshoot email notification.</span></span>

## <a name="view-targeted-attack-notifications"></a><span data-ttu-id="a93ef-139">查看已設定目標的攻擊通知</span><span class="sxs-lookup"><span data-stu-id="a93ef-139">View targeted attack notifications</span></span>

<span data-ttu-id="a93ef-140">在您將系統設定為接收電子郵件通知之後，您將開始從電子郵件中的 Microsoft 威脅專家接收目標攻擊通知。</span><span class="sxs-lookup"><span data-stu-id="a93ef-140">You'll start receiving targeted attack notification from Microsoft Threat Experts in your email after you have configured your system to receive email notification.</span></span>

1. <span data-ttu-id="a93ef-141">選取電子郵件中的連結，以移至以 **威脅專家** 標記的儀表板中對應的警示內容。</span><span class="sxs-lookup"><span data-stu-id="a93ef-141">Select the link in the email to go to the corresponding alert context in the dashboard tagged with **Threat experts**.</span></span>

2. <span data-ttu-id="a93ef-142">在 [ **提醒** ] 頁面上，選取您在電子郵件中收到的警示主題，以查看進一步的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a93ef-142">From the **Alerts** page, select the same alert topic as the one you received in the email, to view further details.</span></span>

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="a93ef-143">訂閱 Microsoft 威脅專家-點播的專家</span><span class="sxs-lookup"><span data-stu-id="a93ef-143">Subscribe to Microsoft Threat Experts - Experts on Demand</span></span>

<span data-ttu-id="a93ef-144">如果您已經是 Microsoft Defender for Endpoint 客戶，您可以聯繫您的 Microsoft 代表，以訂閱 Microsoft 威脅專家-按需求的專家。</span><span class="sxs-lookup"><span data-stu-id="a93ef-144">If you're already a Microsoft Defender for Endpoint customer, you can contact your Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span>

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a><span data-ttu-id="a93ef-145">請參閱 Microsoft 威脅專家關於您組織中的可疑 cybersecurity 活動</span><span class="sxs-lookup"><span data-stu-id="a93ef-145">Consult a Microsoft threat expert about suspicious cybersecurity activities in your organization</span></span>

<span data-ttu-id="a93ef-146">您可以從 Microsoft 365 Defender 入口網站中與 Microsoft 威脅專家聯繫。</span><span class="sxs-lookup"><span data-stu-id="a93ef-146">You can contact Microsoft Threat Experts from inside the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="a93ef-147">專家可協助您瞭解複雜威脅及目標攻擊通知。</span><span class="sxs-lookup"><span data-stu-id="a93ef-147">Experts can help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="a93ef-148">與專家合作，以取得有關警示和事件的詳細資訊，或有關如何處理遭到損害的建議。</span><span class="sxs-lookup"><span data-stu-id="a93ef-148">Partner with experts for further details about alerts and incidents, or advice on handling compromise.</span></span> <span data-ttu-id="a93ef-149">深入瞭解入口網站儀表板所述的威脅情報內容。</span><span class="sxs-lookup"><span data-stu-id="a93ef-149">Gain insight into the threat intelligence context described by your portal dashboard.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="a93ef-150">目前不支援與貴組織的自訂威脅智慧資料相關的警示查詢。</span><span class="sxs-lookup"><span data-stu-id="a93ef-150">Alert inquiries related to your organization's customized threat intelligence data are not currently supported.</span></span> <span data-ttu-id="a93ef-151">如需詳細資訊，請參閱安全性作業或事件回應小組。</span><span class="sxs-lookup"><span data-stu-id="a93ef-151">Consult with your security operations or incident response team for details.</span></span>
> - <span data-ttu-id="a93ef-152">您必須具有 Microsoft 365 Defender 入口網站中的 [ **管理安全性中心的安全性設定** ] 許可權，才可透過 [ **諮詢威脅專家** ] 表單提交查詢。</span><span class="sxs-lookup"><span data-stu-id="a93ef-152">You need to have the **Manage security settings in Security Center** permission in the Microsoft 365 Defender portal to submit an inquiry through the **Consult a threat expert** form.</span></span>

1. <span data-ttu-id="a93ef-153">流覽至與您想要調查之資訊相關的入口網站頁面：例如， **裝置**、 **警示** 或 **事件**。</span><span class="sxs-lookup"><span data-stu-id="a93ef-153">Navigate to the portal page related to the information that you'd like to investigate: for example, **Device**, **Alert**, or **Incident**.</span></span> <span data-ttu-id="a93ef-154">在您傳送調查要求之前，請確定與您查詢相關的入口網站頁面已在視圖中。</span><span class="sxs-lookup"><span data-stu-id="a93ef-154">Make sure that the portal page related to your inquiry is in view before you send an investigation request.</span></span>

2. <span data-ttu-id="a93ef-155">從上方的功能表中，選取 **？請參閱威脅專家**。</span><span class="sxs-lookup"><span data-stu-id="a93ef-155">From the top menu, select **? Consult a threat expert**.</span></span>

    ![來自功能表之要求的 Microsoft 威脅專家專家影像](../../media/mte/incidents-action-mte-highlighted.png)

    <span data-ttu-id="a93ef-157">隨即會開啟彈出畫面。</span><span class="sxs-lookup"><span data-stu-id="a93ef-157">A flyout screen will open.</span></span>

    <span data-ttu-id="a93ef-158">標頭會指出您是在試用訂閱上，還是完整的 Microsoft 威脅專家-點播訂閱。</span><span class="sxs-lookup"><span data-stu-id="a93ef-158">The header will indicate if you are on a trial subscription, or a full Microsoft Threat Experts - Experts on-Demand subscription.</span></span>

    ![Microsoft 威脅專家應需試用訂閱畫面的專家圖像](../../media/mte/mte-trial.png)

    <span data-ttu-id="a93ef-160">「 **調查主題** 」欄位將會填入您要求之相關頁面的連結。</span><span class="sxs-lookup"><span data-stu-id="a93ef-160">The **Investigation topic** field will already be populated with the link to the relevant page for your request.</span></span>

3. <span data-ttu-id="a93ef-161">在下一個欄位中，提供足夠的資訊，讓 Microsoft 威脅專家有足夠的內容來開始調查。</span><span class="sxs-lookup"><span data-stu-id="a93ef-161">In the next field, provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span></span>

4. <span data-ttu-id="a93ef-162">輸入您想要用來對應 Microsoft 威脅專家的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a93ef-162">Enter the email address that you'd like to use to correspond with Microsoft Threat Experts.</span></span>

> [!NOTE]
> <span data-ttu-id="a93ef-163">如果您想要透過 Microsoft Services Hub 追蹤專家對需求案例的狀態，請與您的技術客戶經理聯繫。</span><span class="sxs-lookup"><span data-stu-id="a93ef-163">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your technical account manager.</span></span>

<span data-ttu-id="a93ef-164">觀賞這段影片，以快速流覽 Microsoft Services 中樞。</span><span class="sxs-lookup"><span data-stu-id="a93ef-164">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a><span data-ttu-id="a93ef-165">範例調查主題</span><span class="sxs-lookup"><span data-stu-id="a93ef-165">Sample investigation topics</span></span>

### <a name="alert-information"></a><span data-ttu-id="a93ef-166">警示資訊</span><span class="sxs-lookup"><span data-stu-id="a93ef-166">Alert information</span></span>

- <span data-ttu-id="a93ef-167">我們看到一種新的警示類型，以用於非 land 的二進位。</span><span class="sxs-lookup"><span data-stu-id="a93ef-167">We saw a new type of alert for a living-off-the-land binary.</span></span> <span data-ttu-id="a93ef-168">我們可以提供警示識別碼。</span><span class="sxs-lookup"><span data-stu-id="a93ef-168">We can provide the alert ID.</span></span> <span data-ttu-id="a93ef-169">您可以告訴我們更多有關此提醒的資訊，以及我們可以進一步調查的方式嗎？</span><span class="sxs-lookup"><span data-stu-id="a93ef-169">Can you tell us more about this alert and how we can investigate it further?</span></span>
- <span data-ttu-id="a93ef-170">我們已觀察到兩個類似的攻擊，這會嘗試執行惡意 PowerShell 腳本，但會產生不同的警示。</span><span class="sxs-lookup"><span data-stu-id="a93ef-170">We've observed two similar attacks, which both try to execute malicious PowerShell scripts but generate different alerts.</span></span> <span data-ttu-id="a93ef-171">一個是「可疑 PowerShell 命令列」，另一個是「根據 O365 所提供的指示偵測到惡意檔案」。</span><span class="sxs-lookup"><span data-stu-id="a93ef-171">One is "Suspicious PowerShell command line" and the other is "A malicious file was detected based on indication provided by O365".</span></span> <span data-ttu-id="a93ef-172">有何差異？</span><span class="sxs-lookup"><span data-stu-id="a93ef-172">What is the difference?</span></span>
- <span data-ttu-id="a93ef-173">我們收到有關來自高設定檔使用者裝置的失敗登入錯誤數目的奇怪警示。</span><span class="sxs-lookup"><span data-stu-id="a93ef-173">We received an odd alert today about an abnormal number of failed logins from a high profile user’s device.</span></span> <span data-ttu-id="a93ef-174">我們無法找到這些嘗試的進一步證據。</span><span class="sxs-lookup"><span data-stu-id="a93ef-174">We can't find any further evidence for these attempts.</span></span> <span data-ttu-id="a93ef-175">Microsoft 365 Defender 如何才能看到這些嘗試？</span><span class="sxs-lookup"><span data-stu-id="a93ef-175">How can Microsoft 365 Defender see these attempts?</span></span> <span data-ttu-id="a93ef-176">受監視的登入類型為何？</span><span class="sxs-lookup"><span data-stu-id="a93ef-176">What type of logins are being monitored?</span></span>
- <span data-ttu-id="a93ef-177">您可以提供更多關於警示的內容或洞察力，「系統公用程式已觀察到可疑行為」？</span><span class="sxs-lookup"><span data-stu-id="a93ef-177">Can you give more context or insight about the alert, "Suspicious behavior by a system utility was observed"?</span></span>
- <span data-ttu-id="a93ef-178">已觀察到「建立轉寄/重新導向規則」標題的警示。</span><span class="sxs-lookup"><span data-stu-id="a93ef-178">I observed an alert titled "Creation of forwarding/redirect rule".</span></span> <span data-ttu-id="a93ef-179">我相信活動是良性的。</span><span class="sxs-lookup"><span data-stu-id="a93ef-179">I believe the activity is benign.</span></span> <span data-ttu-id="a93ef-180">您可以告訴我為什麼收到警示？</span><span class="sxs-lookup"><span data-stu-id="a93ef-180">Can you tell me why I received an alert?</span></span>

### <a name="possible-machine-compromise"></a><span data-ttu-id="a93ef-181">可能危害的機器</span><span class="sxs-lookup"><span data-stu-id="a93ef-181">Possible machine compromise</span></span>

- <span data-ttu-id="a93ef-182">您可以協助說明為什麼我們在組織中的許多裝置上看到「已觀測未知程式」的訊息或警示？</span><span class="sxs-lookup"><span data-stu-id="a93ef-182">Can you help explain why we see a message or alert for "Unknown process observed" on many devices in our organization?</span></span> <span data-ttu-id="a93ef-183">我們非常感謝任何輸入，以澄清此郵件或警示是否與惡意活動有關。</span><span class="sxs-lookup"><span data-stu-id="a93ef-183">We appreciate any input to clarify whether this message or alert is related to malicious activity.</span></span>
- <span data-ttu-id="a93ef-184">您可以從過去一周的 dating，協助驗證下列系統上可能的損損？</span><span class="sxs-lookup"><span data-stu-id="a93ef-184">Can you help validate a possible compromise on the following system, dating from last week?</span></span> <span data-ttu-id="a93ef-185">其行為類似于在六個月前的同一個系統上進行惡意程式碼偵測。</span><span class="sxs-lookup"><span data-stu-id="a93ef-185">It's behaving similarly as a previous malware detection on the same system six months ago.</span></span>

### <a name="threat-intelligence-details"></a><span data-ttu-id="a93ef-186">威脅智慧詳細資料</span><span class="sxs-lookup"><span data-stu-id="a93ef-186">Threat intelligence details</span></span>

- <span data-ttu-id="a93ef-187">我們偵測到網路釣魚電子郵件，將惡意的 Word 檔傳遞給使用者。</span><span class="sxs-lookup"><span data-stu-id="a93ef-187">We detected a phishing email that delivered a malicious Word document to a user.</span></span> <span data-ttu-id="a93ef-188">檔導致一系列的可疑事件，這些事件會觸發針對特定惡意程式碼系列的多個警示。</span><span class="sxs-lookup"><span data-stu-id="a93ef-188">The document caused a series of suspicious events, which triggered multiple alerts for a particular malware family.</span></span> <span data-ttu-id="a93ef-189">您是否有這種惡意程式碼的資訊？</span><span class="sxs-lookup"><span data-stu-id="a93ef-189">Do you have any information on this malware?</span></span> <span data-ttu-id="a93ef-190">如果是，您可以將連結傳送給我們嗎？</span><span class="sxs-lookup"><span data-stu-id="a93ef-190">If yes, can you send us a link?</span></span>
- <span data-ttu-id="a93ef-191">我們最近看到的是以我們為行業之威脅為目標的博客文章。</span><span class="sxs-lookup"><span data-stu-id="a93ef-191">We recently saw a blog post about a threat that is targeting our industry.</span></span> <span data-ttu-id="a93ef-192">您可以協助我們瞭解 Microsoft 365 Defender 針對此威脅的內容提供什麼保護？</span><span class="sxs-lookup"><span data-stu-id="a93ef-192">Can you help us understand what protection Microsoft 365 Defender provides against this threat actor?</span></span>
- <span data-ttu-id="a93ef-193">我們最近觀察到我們對我們組織進行的網路釣魚活動。</span><span class="sxs-lookup"><span data-stu-id="a93ef-193">We recently observed a phishing campaign conducted against our organization.</span></span> <span data-ttu-id="a93ef-194">您可以告訴我們我們是否特別針對公司或縱向？</span><span class="sxs-lookup"><span data-stu-id="a93ef-194">Can you tell us if this was targeted specifically to our company or vertical?</span></span>

### <a name="microsoft-threat-experts-alert-communications"></a><span data-ttu-id="a93ef-195">Microsoft 威脅專家的警示通訊</span><span class="sxs-lookup"><span data-stu-id="a93ef-195">Microsoft Threat Experts’ alert communications</span></span>

- <span data-ttu-id="a93ef-196">您的事件回應小組可以協助我們解決我們所收到的目標攻擊通知嗎？</span><span class="sxs-lookup"><span data-stu-id="a93ef-196">Can your incident response team help us address the targeted attack notification that we got?</span></span>
- <span data-ttu-id="a93ef-197">我們收到來自 Microsoft 威脅專家的此目標攻擊通知。</span><span class="sxs-lookup"><span data-stu-id="a93ef-197">We received this targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="a93ef-198">我們沒有自己的事件回應小組。</span><span class="sxs-lookup"><span data-stu-id="a93ef-198">We don’t have our own incident response team.</span></span> <span data-ttu-id="a93ef-199">我們現在可以做什麼，以及如何包含該事件？</span><span class="sxs-lookup"><span data-stu-id="a93ef-199">What can we do now, and how can we contain the incident?</span></span>
- <span data-ttu-id="a93ef-200">我們收到來自 Microsoft 威脅專家的目標攻擊通知。</span><span class="sxs-lookup"><span data-stu-id="a93ef-200">We received a targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="a93ef-201">您可以為我們提供哪些資料，讓我們能夠傳遞給我們的事件回應小組？</span><span class="sxs-lookup"><span data-stu-id="a93ef-201">What data can you provide to us that we can pass on to our incident response team?</span></span>

> [!NOTE]
> <span data-ttu-id="a93ef-202">Microsoft 威脅專家是受管理的威脅搜尋服務，不是事件回應服務。</span><span class="sxs-lookup"><span data-stu-id="a93ef-202">Microsoft Threat Experts is a managed threat hunting service and not an incident response service.</span></span> <span data-ttu-id="a93ef-203">不過，當必要時，專家可將調查順利轉換至 Microsoft Cybersecurity 解決方案群組 (CSG) 的偵測和回應小組 (DART) 服務。</span><span class="sxs-lookup"><span data-stu-id="a93ef-203">However, the experts can seamlessly transition the investigation to Microsoft Cybersecurity Solutions Group (CSG)'s Detection and Response Team (DART) services, when necessary.</span></span> <span data-ttu-id="a93ef-204">您也可以選擇與您自己的事件回應小組合作，以解決需要事件回應的問題。</span><span class="sxs-lookup"><span data-stu-id="a93ef-204">You can also opt to engage with your own incident response team to address issues that requires an incident response.</span></span>

## <a name="scenario"></a><span data-ttu-id="a93ef-205">案例</span><span class="sxs-lookup"><span data-stu-id="a93ef-205">Scenario</span></span>

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a><span data-ttu-id="a93ef-206">接收受管理搜尋查詢的進度報告</span><span class="sxs-lookup"><span data-stu-id="a93ef-206">Receive a progress report about your managed hunting inquiry</span></span>

<span data-ttu-id="a93ef-207">Microsoft 威脅專家的回應會隨著您的查詢而異。</span><span class="sxs-lookup"><span data-stu-id="a93ef-207">The response from Microsoft Threat Experts will vary according to your inquiry.</span></span> <span data-ttu-id="a93ef-208">您通常會收到下列其中一項回應：</span><span class="sxs-lookup"><span data-stu-id="a93ef-208">You'll generally receive one of the following responses:</span></span>

- <span data-ttu-id="a93ef-209">需要有其他資訊才能繼續進行調查</span><span class="sxs-lookup"><span data-stu-id="a93ef-209">More information is needed to continue with the investigation</span></span>
- <span data-ttu-id="a93ef-210">需要有一個或多個檔案範例，以判斷技術內容</span><span class="sxs-lookup"><span data-stu-id="a93ef-210">A file or several file samples are needed to determine the technical context</span></span>
- <span data-ttu-id="a93ef-211">調查需要更多時間</span><span class="sxs-lookup"><span data-stu-id="a93ef-211">Investigation requires more time</span></span>
- <span data-ttu-id="a93ef-212">最初的資訊足以結束調查</span><span class="sxs-lookup"><span data-stu-id="a93ef-212">Initial information was enough to conclude the investigation</span></span>

<span data-ttu-id="a93ef-213">如果專家要求更多資訊或檔案範例，請快速回應，以繼續進行調查的移動。</span><span class="sxs-lookup"><span data-stu-id="a93ef-213">If an expert requests more information or file samples, it's crucial to respond quickly to keep the investigation moving.</span></span>

## <a name="see-also"></a><span data-ttu-id="a93ef-214">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a93ef-214">See also</span></span>

- [<span data-ttu-id="a93ef-215">Microsoft 威脅專家概觀</span><span class="sxs-lookup"><span data-stu-id="a93ef-215">Microsoft Threat Experts overview</span></span>](microsoft-threat-experts.md)
