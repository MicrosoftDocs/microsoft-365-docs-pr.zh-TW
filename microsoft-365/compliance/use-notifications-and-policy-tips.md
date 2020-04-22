---
title: 針對 DLP 原則傳送電子郵件通知並顯示原則提示
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: '原則提示是指當有人使用與 DLP 原則衝突的內容時所顯示的通知或警告。 您可以使用電子郵件通知和原則提示來增加知名度，協助教育組織的原則。 您也可以讓使用者選擇覆寫原則，以便在有有效的業務需求或原則偵測到誤報時，不會封鎖這些原則。 '
ms.openlocfilehash: fd6c7a33f8c75615019cca32797008a8fa4753ed
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626399"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a><span data-ttu-id="f525c-105">針對 DLP 原則傳送電子郵件通知並顯示原則提示</span><span class="sxs-lookup"><span data-stu-id="f525c-105">Send email notifications and show policy tips for DLP policies</span></span>

<span data-ttu-id="f525c-106">您可以使用資料遺失防護（DLP）原則，識別、監視和保護 Office 365 中的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="f525c-106">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365.</span></span> <span data-ttu-id="f525c-107">您想要使用此機密資訊的組織中的人員保持與 DLP 原則的相容性，但是您不想要將它們封鎖，而不需要讓他們完成工作。</span><span class="sxs-lookup"><span data-stu-id="f525c-107">You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done.</span></span> <span data-ttu-id="f525c-108">這是電子郵件通知和原則提示可助您做的地方。</span><span class="sxs-lookup"><span data-stu-id="f525c-108">This is where email notifications and policy tips can help.</span></span>
  
![訊息列會顯示 Excel 2016 中的原則提示](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="f525c-110">原則提示是指當有人使用與 DLP 原則衝突的內容時所顯示的通知或警告，例如，Excel 活頁簿位於包含個人身分識別資訊（PII）且與外部使用者共用的 OneDrive 商務網站上的內容。</span><span class="sxs-lookup"><span data-stu-id="f525c-110">A policy tip is a notification or warning that appears when someone is working with content that conflicts with a DLP policy—for example, content like an Excel workbook on a OneDrive for Business site that contains personally identifiable information (PII) and is shared with an external user.</span></span>
  
<span data-ttu-id="f525c-111">您可以使用電子郵件通知和原則提示來增加知名度，協助教育組織的原則。</span><span class="sxs-lookup"><span data-stu-id="f525c-111">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies.</span></span> <span data-ttu-id="f525c-112">您也可以讓使用者選擇覆寫原則，以便在有有效的業務需求或原則偵測到誤報時，不會封鎖這些原則。</span><span class="sxs-lookup"><span data-stu-id="f525c-112">You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span></span>
  
<span data-ttu-id="f525c-113">在安全性&amp;與合規性中心中，當您建立 DLP 原則時，您可以將使用者通知設定為：</span><span class="sxs-lookup"><span data-stu-id="f525c-113">In the Security &amp; Compliance Center, when you create a DLP policy, you can configure the user notifications to:</span></span>
  
- <span data-ttu-id="f525c-114">傳送電子郵件通知給您選擇的描述問題的人員。</span><span class="sxs-lookup"><span data-stu-id="f525c-114">Send an email notification to the people you choose that describes the issue.</span></span>
    
- <span data-ttu-id="f525c-115">顯示與 DLP 原則衝突之內容的原則提示：</span><span class="sxs-lookup"><span data-stu-id="f525c-115">Display a policy tip for content that conflicts with the DLP policy:</span></span>
    
  - <span data-ttu-id="f525c-116">針對 Outlook 網頁版和 Outlook 2013 和更新版本中的電子郵件，原則提示會出現在撰寫郵件的收件者上方的郵件上方。</span><span class="sxs-lookup"><span data-stu-id="f525c-116">For email in Outlook on the web and Outlook 2013 and later, the policy tip appears at the top of a message above the recipients while the message is being composed.</span></span>
    
  - <span data-ttu-id="f525c-117">對於商務用 OneDrive 的商務帳戶或 SharePoint 線上網站，原則提示會以顯示在專案上的警告圖示表示。</span><span class="sxs-lookup"><span data-stu-id="f525c-117">For documents in a OneDrive for Business account or SharePoint Online site, the policy tip is indicated by a warning icon that appears on the item.</span></span> <span data-ttu-id="f525c-118">若要查看詳細資訊，您可以選取專案，然後選擇**Information** ![頁面右上角的](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) [資訊資訊窗格] 圖示，以開啟 [詳細資料] 窗格。</span><span class="sxs-lookup"><span data-stu-id="f525c-118">To view more information, you can select an item and then choose **Information** ![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane.</span></span> 
    
  - <span data-ttu-id="f525c-119">針對儲存在 OneDrive for Business site or SharePoint Online 網站（包含在 DLP 原則中）的 Excel、PowerPoint 和 Word 檔，原則提示會出現在訊息列和 Backstage**視圖（[** 檔案] 功能表\> **資訊**）。</span><span class="sxs-lookup"><span data-stu-id="f525c-119">For Excel, PowerPoint, and Word documents that are stored on a OneDrive for Business site or SharePoint Online site that's included in the DLP policy, the policy tip appears on the Message Bar and the Backstage view ( **File** menu \> **Info**).</span></span>
    
## <a name="add-user-notifications-to-a-dlp-policy"></a><span data-ttu-id="f525c-120">將使用者通知新增至 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="f525c-120">Add user notifications to a DLP policy</span></span>

<span data-ttu-id="f525c-121">當您建立 DLP 原則時，您可以啟用**使用者通知**。</span><span class="sxs-lookup"><span data-stu-id="f525c-121">When you create a DLP policy, you can enable **User notifications**.</span></span> <span data-ttu-id="f525c-122">啟用使用者通知時，Microsoft 365 會同時傳送電子郵件通知和原則提示。</span><span class="sxs-lookup"><span data-stu-id="f525c-122">When user notifications are enabled, Microsoft 365 sends out both email notifications and policy tips.</span></span> <span data-ttu-id="f525c-123">您可以自訂傳送通知電子郵件的寄件者、電子郵件文字和原則提示文字。</span><span class="sxs-lookup"><span data-stu-id="f525c-123">You can customize who notification emails are sent to, the email text and the policy tip text.</span></span>
  
1. <span data-ttu-id="f525c-124">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="f525c-124">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="f525c-125">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="f525c-125">Sign in using your work or school account.</span></span> <span data-ttu-id="f525c-126">現在您已在安全性&amp;與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="f525c-126">You're now in the Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="f525c-127">在 [安全性&amp;與合規\>性中心\> ] 左側導覽**資料遺失防護** \> **原則** \>中，**建立原則**。</span><span class="sxs-lookup"><span data-stu-id="f525c-127">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![建立原則按鈕](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="f525c-129">選擇 DLP 原則範本，以保護您\> **下一步**所需的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="f525c-129">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="f525c-130">若要從空白範本開始，請**選擇** \> **Custom policy** \> **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f525c-130">To start with an empty template, choose **Custom** \> **Custom policy** \> **Next**.</span></span>
    
5. <span data-ttu-id="f525c-131">將原則\>命名為 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f525c-131">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="f525c-132">若要選擇您想要 DLP 原則保護的位置，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="f525c-132">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
   - <span data-ttu-id="f525c-133">在\> **[下一步]\*\*\*\*中選擇 Office 365 的所有位置**。</span><span class="sxs-lookup"><span data-stu-id="f525c-133">Choose **All locations in Office 365** \> **Next**.</span></span>
    
   - <span data-ttu-id="f525c-134">選擇 [**讓我選擇特定位置** \> **] [下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f525c-134">Choose **Let me choose specific locations** \> **Next**.</span></span>
    
   <span data-ttu-id="f525c-135">若要包含或排除整個位置（例如所有 Exchange 電子郵件或所有 OneDrive 帳戶），請切換該位置的**狀態**。</span><span class="sxs-lookup"><span data-stu-id="f525c-135">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
   <span data-ttu-id="f525c-136">若只要包含特定的 SharePoint 網站或 OneDrive 帳戶，請將**狀態**切換為 [開啟]，然後按一下 [**包含**] 底下的連結，選擇特定的網站或帳戶。</span><span class="sxs-lookup"><span data-stu-id="f525c-136">To include only specific SharePoint sites or OneDrive accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span> 
    
7. <span data-ttu-id="f525c-137">選擇 [**使用高級設定** \> **] [下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f525c-137">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="f525c-138">選擇 [ **+ 新規則**]。</span><span class="sxs-lookup"><span data-stu-id="f525c-138">Choose **+ New rule**.</span></span>
    
9. <span data-ttu-id="f525c-139">在規則編輯器的 [**使用者通知**] 下，切換狀態 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="f525c-139">In the rule editor, under **User notifications**, switch the status on.</span></span>
    
    ![規則編輯器的使用者通知區段](../media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> <span data-ttu-id="f525c-141">DLP 原則適用于符合原則的所有檔，不論這些檔是新的或現有的。</span><span class="sxs-lookup"><span data-stu-id="f525c-141">DLP policies apply to all documents that match the policy, whether those documents are new or existing.</span></span> <span data-ttu-id="f525c-142">不過，只有當新內容符合現有的 DLP 原則時，才會產生電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="f525c-142">However, an email notification is only generated when new content matches an existing DLP policy.</span></span> <span data-ttu-id="f525c-143">現有內容受到保護，但不會透過電子郵件產生使用者通知。</span><span class="sxs-lookup"><span data-stu-id="f525c-143">Existing content is protected, but will not generate a user notification via email.</span></span>
  
## <a name="options-for-configuring-email-notifications"></a><span data-ttu-id="f525c-144">設定電子郵件通知的選項</span><span class="sxs-lookup"><span data-stu-id="f525c-144">Options for configuring email notifications</span></span>

<span data-ttu-id="f525c-145">針對 DLP 原則中的每個規則，您可以：</span><span class="sxs-lookup"><span data-stu-id="f525c-145">For each rule in a DLP policy, you can:</span></span>
  
- <span data-ttu-id="f525c-146">將通知傳送給您所選擇的人員。</span><span class="sxs-lookup"><span data-stu-id="f525c-146">Send the notification to the people you choose.</span></span> <span data-ttu-id="f525c-147">這些人員可以包含內容的擁有者、上次修改內容的人員、內容儲存所在網站的擁有者，或特定使用者。</span><span class="sxs-lookup"><span data-stu-id="f525c-147">These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span></span>
    
- <span data-ttu-id="f525c-148">使用 HTML 或標記自訂通知中所包含的文字。</span><span class="sxs-lookup"><span data-stu-id="f525c-148">Customize the text that's included in the notification by using HTML or tokens.</span></span> <span data-ttu-id="f525c-149">詳細資訊請參閱下一小節。</span><span class="sxs-lookup"><span data-stu-id="f525c-149">See the section below for more information.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="f525c-150">電子郵件通知只能傳送給個別收件者，而不能傳送至群組或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="f525c-150">Email notifications can be sent only to individual recipients—not groups or distribution lists.</span></span> <span data-ttu-id="f525c-151">只有新的內容會觸發電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="f525c-151">Only new content will trigger an email notification.</span></span> <span data-ttu-id="f525c-152">編輯現有內容將會觸發原則秘訣，但不會觸發電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="f525c-152">Editing existing content will trigger policy tips, but not an email notification.</span></span> 
  
![電子郵件通知選項](../media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a><span data-ttu-id="f525c-154">預設電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="f525c-154">Default email notification</span></span>

<span data-ttu-id="f525c-155">通知有一個以所採取動作為開頭的主旨行，例如「通知」、「郵件封鎖」（表示電子郵件），或是檔的「拒絕存取」。</span><span class="sxs-lookup"><span data-stu-id="f525c-155">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents.</span></span> <span data-ttu-id="f525c-156">如果通知與檔有關，通知訊息內文會包含連結，讓您前往儲存檔的網站，並開啟檔的原則提示，您可以在其中解決任何問題（請參閱下列有關原則提示的章節）。</span><span class="sxs-lookup"><span data-stu-id="f525c-156">If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips).</span></span> <span data-ttu-id="f525c-157">如果通知是關於郵件的通知，則通知會將符合 DLP 原則的郵件包含為附件。</span><span class="sxs-lookup"><span data-stu-id="f525c-157">If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span></span>
  
![通知訊息](../media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
<span data-ttu-id="f525c-159">根據預設，通知會顯示網站上專案類似下列的文字。</span><span class="sxs-lookup"><span data-stu-id="f525c-159">By default, notifications display text similar to the following for an item on a site.</span></span> <span data-ttu-id="f525c-160">通知文字會個別針對每個規則進行設定，因此顯示的文字會隨相符的規則而有所不同。</span><span class="sxs-lookup"><span data-stu-id="f525c-160">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="f525c-161">**如果 DLP 原則規則執行此動作 .。。**</span><span class="sxs-lookup"><span data-stu-id="f525c-161">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="f525c-162">**否則，SharePoint 或 OneDrive 商務檔的預設通知即會指出 .。。**</span><span class="sxs-lookup"><span data-stu-id="f525c-162">**Then the default notification for SharePoint or OneDrive for Business documents says this…**</span></span>|<span data-ttu-id="f525c-163">**否則，Outlook 郵件的預設通知就會指出 .。。**</span><span class="sxs-lookup"><span data-stu-id="f525c-163">**Then the default notification for Outlook messages says this…**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f525c-164">傳送通知但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="f525c-164">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="f525c-165">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-165">This item conflicts with a policy in your organization.</span></span>  <br/> |<span data-ttu-id="f525c-166">您的電子郵件與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-166">Your email message conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="f525c-167">封鎖存取、傳送通知及允許覆寫</span><span class="sxs-lookup"><span data-stu-id="f525c-167">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="f525c-168">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-168">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="f525c-169">如果您未解決此衝突，則可能會封鎖對此檔案的存取。</span><span class="sxs-lookup"><span data-stu-id="f525c-169">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |<span data-ttu-id="f525c-170">您的電子郵件與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-170">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="f525c-171">郵件未傳遞給所有收件者。</span><span class="sxs-lookup"><span data-stu-id="f525c-171">The message wasn't delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="f525c-172">封鎖存取及傳送通知</span><span class="sxs-lookup"><span data-stu-id="f525c-172">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="f525c-173">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-173">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="f525c-174">除了其擁有者、最後一個修改者及主要網站集合管理員之外，還會封鎖所有使用者對此專案的存取。</span><span class="sxs-lookup"><span data-stu-id="f525c-174">Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |<span data-ttu-id="f525c-175">您的電子郵件與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-175">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="f525c-176">郵件未傳遞給所有收件者。</span><span class="sxs-lookup"><span data-stu-id="f525c-176">The message wasn't delivered to all recipients.</span></span>  <br/> |
   
### <a name="custom-email-notification"></a><span data-ttu-id="f525c-177">自訂電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="f525c-177">Custom email notification</span></span>

<span data-ttu-id="f525c-178">您可以建立自訂的電子郵件通知，而不是傳送預設的電子郵件通知給您的使用者或系統管理員。</span><span class="sxs-lookup"><span data-stu-id="f525c-178">You can create a custom email notification instead of sending the default email notification to your end users or admins.</span></span> <span data-ttu-id="f525c-179">自訂電子郵件通知支援 HTML，且具有5000個字元的限制。</span><span class="sxs-lookup"><span data-stu-id="f525c-179">The custom email notification supports HTML and has a 5,000-character limit.</span></span> <span data-ttu-id="f525c-180">您可以使用 HTML，在通知中包含影像、格式及其他商標。</span><span class="sxs-lookup"><span data-stu-id="f525c-180">You can use HTML to include images, formatting, and other branding in the notification.</span></span>
  
<span data-ttu-id="f525c-181">您也可以使用下列標記，協助自訂電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="f525c-181">You can also use the following tokens to help customize the email notification.</span></span> <span data-ttu-id="f525c-182">這些標記是以傳送之通知中的特定資訊所取代的變數。</span><span class="sxs-lookup"><span data-stu-id="f525c-182">These tokens are variables that are replaced by specific information in the notification that's sent.</span></span>

|<span data-ttu-id="f525c-183">**令 牌**</span><span class="sxs-lookup"><span data-stu-id="f525c-183">**Token**</span></span>|<span data-ttu-id="f525c-184">**描述**</span><span class="sxs-lookup"><span data-stu-id="f525c-184">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f525c-185">%%AppliedActions%%</span><span class="sxs-lookup"><span data-stu-id="f525c-185">%%AppliedActions%%</span></span>  <br/> |<span data-ttu-id="f525c-186">套用至內容的動作。</span><span class="sxs-lookup"><span data-stu-id="f525c-186">The actions applied to the content.</span></span>  <br/> |
|<span data-ttu-id="f525c-187">%%ContentURL%%</span><span class="sxs-lookup"><span data-stu-id="f525c-187">%%ContentURL%%</span></span>  <br/> |<span data-ttu-id="f525c-188">SharePoint Online 網站上的檔或商務用 OneDrive 的網站 URL。</span><span class="sxs-lookup"><span data-stu-id="f525c-188">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>  <br/> |
|<span data-ttu-id="f525c-189">%%MatchedConditions%%</span><span class="sxs-lookup"><span data-stu-id="f525c-189">%%MatchedConditions%%</span></span>  <br/> |<span data-ttu-id="f525c-190">內容所符合的條件。</span><span class="sxs-lookup"><span data-stu-id="f525c-190">The conditions that were matched by the content.</span></span> <span data-ttu-id="f525c-191">使用此權杖，向人員告知內容可能的問題。</span><span class="sxs-lookup"><span data-stu-id="f525c-191">Use this token to inform people of possible issues with the content.</span></span>  <br/> |
   
![顯示標記顯示位置的通知訊息](../media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a><span data-ttu-id="f525c-193">設定原則提示的選項</span><span class="sxs-lookup"><span data-stu-id="f525c-193">Options for configuring policy tips</span></span>

<span data-ttu-id="f525c-194">針對 DLP 原則中的每個規則，您可以將原則提示設定為：</span><span class="sxs-lookup"><span data-stu-id="f525c-194">For each rule in a DLP policy, you can configure policy tips to:</span></span>
  
- <span data-ttu-id="f525c-195">只要通知人員該內容與 DLP 原則衝突，就可以採取動作來解決衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-195">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict.</span></span> <span data-ttu-id="f525c-196">您可以使用預設文字（請參閱下表）或輸入有關組織特定原則的自訂文字。</span><span class="sxs-lookup"><span data-stu-id="f525c-196">You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span></span>
    
- <span data-ttu-id="f525c-197">允許人員覆寫 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="f525c-197">Allow the person to override the DLP policy.</span></span> <span data-ttu-id="f525c-198">您也可以：</span><span class="sxs-lookup"><span data-stu-id="f525c-198">Optionally, you can:</span></span>
    
  - <span data-ttu-id="f525c-199">要求人員輸入用於覆寫原則的業務理由。</span><span class="sxs-lookup"><span data-stu-id="f525c-199">Require the person to enter a business justification for overriding the policy.</span></span> <span data-ttu-id="f525c-200">這項資訊會記錄下來，您可以在安全性&amp;與合規性中心的 [**報告**] 區段中的 [DLP 報告] 中查看。</span><span class="sxs-lookup"><span data-stu-id="f525c-200">This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span></span> 
    
  - <span data-ttu-id="f525c-201">允許人員報告誤報，並覆寫 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="f525c-201">Allow the person to report a false positive and override the DLP policy.</span></span> <span data-ttu-id="f525c-202">此資訊也會記錄報告，所以您可以使用誤報來微調您的規則。</span><span class="sxs-lookup"><span data-stu-id="f525c-202">This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span></span>
    
![原則提示選項](../media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
<span data-ttu-id="f525c-204">例如，您可以針對偵測個人身分識別資訊（PII）的商務網站套用一個 DLP 原則 OneDrive，而這個原則有三個規則：</span><span class="sxs-lookup"><span data-stu-id="f525c-204">For example, you may have a DLP policy applied to OneDrive for Business sites that detects personally identifiable information (PII), and this policy has three rules:</span></span>
  
1. <span data-ttu-id="f525c-205">第一個規則：如果在檔中偵測到此敏感資訊的實例少於五個，且該檔與組織內的人員共用，則 [**傳送通知**] 動作會顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="f525c-205">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip.</span></span> <span data-ttu-id="f525c-206">針對原則提示，不需要覆寫選項，因為此規則只是通知人員，而不會封鎖存取。</span><span class="sxs-lookup"><span data-stu-id="f525c-206">For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span></span> 
    
2. <span data-ttu-id="f525c-207">第二個規則：如果在檔中偵測到此機密資訊有五個以上的實例，且該檔與組織內的人員共用，則 [**封鎖存取內容**] 動作會限制檔案的許可權，而 [**傳送通知**] 動作可讓使用者透過提供業務理由，以覆寫此規則中的動作。</span><span class="sxs-lookup"><span data-stu-id="f525c-207">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification.</span></span> <span data-ttu-id="f525c-208">貴組織的業務有時候會要求內部人員共用 PII 資料，而您不想讓 DLP 原則封鎖這種工作。</span><span class="sxs-lookup"><span data-stu-id="f525c-208">Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span></span> 
    
3. <span data-ttu-id="f525c-209">第三個規則：如果在檔中偵測到此機密資訊有五個以上的實例，且該檔與組織外部的人員共用，則 [**封鎖存取內容**] 動作會限制檔案的許可權，而 [**傳送通知**] 動作不允許使用者覆寫此規則中的動作，因為該資訊是從外部共用。</span><span class="sxs-lookup"><span data-stu-id="f525c-209">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally.</span></span> <span data-ttu-id="f525c-210">在任何情況下，您組織中的人員都不應該允許在組織外共用 PII 資料。</span><span class="sxs-lookup"><span data-stu-id="f525c-210">Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span></span> 
    
<span data-ttu-id="f525c-211">以下是瞭解如何使用原則提示來覆寫規則的一些細微點：</span><span class="sxs-lookup"><span data-stu-id="f525c-211">Here are some fine points to understand about using a policy tip to override a rule:</span></span>
  
- <span data-ttu-id="f525c-212">覆寫的選項是依據規則，它會覆寫規則中的所有動作（傳送通知，但不能覆寫）。</span><span class="sxs-lookup"><span data-stu-id="f525c-212">The option to override is per rule, and it overrides all of the actions in the rule (except sending a notification, which can't be overridden).</span></span>
    
- <span data-ttu-id="f525c-213">您可以將內容與 DLP 原則中的數個規則相符，但是只會顯示來自最具限制性的最高優先順序規則的原則提示。</span><span class="sxs-lookup"><span data-stu-id="f525c-213">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown.</span></span> <span data-ttu-id="f525c-214">例如，會封鎖內容存取權的規則與僅傳送通知的規則，只會顯示前者的原則提示。</span><span class="sxs-lookup"><span data-stu-id="f525c-214">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="f525c-215">這樣可避免使用者看到重疊顯示的原則提示。</span><span class="sxs-lookup"><span data-stu-id="f525c-215">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="f525c-216">如果最嚴格規則中的原則提示允許人員覆寫規則，則覆寫此規則也將會覆寫內容符合的任何其他規則。</span><span class="sxs-lookup"><span data-stu-id="f525c-216">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a><span data-ttu-id="f525c-217">商務網站 OneDrive 和 SharePoint Online 網站的原則提示</span><span class="sxs-lookup"><span data-stu-id="f525c-217">Policy tips on OneDrive for Business sites and SharePoint Online sites</span></span>

<span data-ttu-id="f525c-218">當商務用 OneDrive 或 SharePoint Online 網站上的檔符合 DLP 原則中的規則，且該規則使用原則提示時，原則提示會在檔上顯示特殊的圖示：</span><span class="sxs-lookup"><span data-stu-id="f525c-218">When a document on a OneDrive for Business site or SharePoint Online site matches a rule in a DLP policy, and that rule uses policy tips, the policy tips display special icons on the document:</span></span>
  
1. <span data-ttu-id="f525c-219">如果規則傳送有關檔案的通知，就會顯示警告圖示。</span><span class="sxs-lookup"><span data-stu-id="f525c-219">If the rule sends a notification about the file, the warning icon appears.</span></span>
    
2. <span data-ttu-id="f525c-220">如果規則封鎖對檔的存取，便會顯示封鎖的圖示。</span><span class="sxs-lookup"><span data-stu-id="f525c-220">If the rule blocks access to the document, the blocked icon appears.</span></span>
    
   ![OneDrive 帳戶中的檔的原則提示圖示](../media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
<span data-ttu-id="f525c-222">若要對檔採取動作，您可以選取\>專案在頁面的右上角選擇 [**資訊** ![資訊] 窗格圖示](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) ，以開啟 [詳細資料] 窗格\>的 [詳細資料] 窗格的 [**顯示原則提示**]。</span><span class="sxs-lookup"><span data-stu-id="f525c-222">To take action on a document, you can select an item \> choose **Information** ![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane \> **View policy tip**.</span></span>
  
<span data-ttu-id="f525c-223">原則提示會列出內容的問題，而且如果使用這些選項設定原則提示，您可以選擇 [**解決**]，然後覆**寫**原則提示或**報告**誤報。</span><span class="sxs-lookup"><span data-stu-id="f525c-223">The policy tip lists the issues with the content, and if the policy tips are configured with these options, you can choose **Resolve**, and then **Override** the policy tip or **Report** a false positive.</span></span> 
  
![顯示原則提示的資訊窗格](../media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![具有覆寫選項的原則提示](../media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
<span data-ttu-id="f525c-226">DLP 原則同步處理至網站，而且會定期及非同步評估 contented，因此您建立 DLP 原則的時間與開始查看原則提示的時間之間可能會有短暫的延遲。</span><span class="sxs-lookup"><span data-stu-id="f525c-226">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips.</span></span> <span data-ttu-id="f525c-227">當您解決或覆寫網站上的檔圖示時，可能會有類似的延遲。</span><span class="sxs-lookup"><span data-stu-id="f525c-227">There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span></span>
  
### <a name="default-text-for-policy-tips-on-sites"></a><span data-ttu-id="f525c-228">網站上原則提示的預設文字</span><span class="sxs-lookup"><span data-stu-id="f525c-228">Default text for policy tips on sites</span></span>

<span data-ttu-id="f525c-229">原則提示預設會針對網站上的專案，顯示類似下列的文字。</span><span class="sxs-lookup"><span data-stu-id="f525c-229">By default, policy tips display text similar to the following for an item on a site.</span></span> <span data-ttu-id="f525c-230">通知文字會個別針對每個規則進行設定，因此顯示的文字會隨相符的規則而有所不同。</span><span class="sxs-lookup"><span data-stu-id="f525c-230">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="f525c-231">**如果 DLP 原則規則執行此動作 .。。**</span><span class="sxs-lookup"><span data-stu-id="f525c-231">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="f525c-232">**預設原則提示會說 .。。**</span><span class="sxs-lookup"><span data-stu-id="f525c-232">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f525c-233">傳送通知但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="f525c-233">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="f525c-234">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-234">This item conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="f525c-235">封鎖存取、傳送通知及允許覆寫</span><span class="sxs-lookup"><span data-stu-id="f525c-235">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="f525c-236">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-236">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="f525c-237">如果您未解決此衝突，則可能會封鎖對此檔案的存取。</span><span class="sxs-lookup"><span data-stu-id="f525c-237">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |
|<span data-ttu-id="f525c-238">封鎖存取及傳送通知</span><span class="sxs-lookup"><span data-stu-id="f525c-238">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="f525c-239">此專案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-239">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="f525c-240">除了其擁有者、最後一個修改者及主要網站集合管理員之外，還會封鎖所有使用者對此專案的存取。</span><span class="sxs-lookup"><span data-stu-id="f525c-240">Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a><span data-ttu-id="f525c-241">網站上的原則提示的自訂文字</span><span class="sxs-lookup"><span data-stu-id="f525c-241">Custom text for policy tips on sites</span></span>

<span data-ttu-id="f525c-242">您可以從電子郵件通知中單獨自訂原則提示的文字。</span><span class="sxs-lookup"><span data-stu-id="f525c-242">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="f525c-243">與電子郵件通知的自訂文字（請參閱上一節）不同的是原則提示的自訂文字不接受 HTML 或標記。</span><span class="sxs-lookup"><span data-stu-id="f525c-243">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="f525c-244">相反地，[原則提示] 的自訂文字只會以256個字元的限制顯示純文字。</span><span class="sxs-lookup"><span data-stu-id="f525c-244">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a><span data-ttu-id="f525c-245">Outlook 網頁版和 Outlook 2013 和更新版本中的原則提示</span><span class="sxs-lookup"><span data-stu-id="f525c-245">Policy tips in Outlook on the web and Outlook 2013 and later</span></span>

<span data-ttu-id="f525c-246">當您在 web 和 Outlook 2013 和更新版本的 Outlook 中撰寫新的電子郵件時，如果您在 DLP 原則中新增符合規則的內容，則會看到原則提示，而且該規則會使用原則提示。</span><span class="sxs-lookup"><span data-stu-id="f525c-246">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips.</span></span> <span data-ttu-id="f525c-247">原則提示會出現在郵件上方，收件者的上方，郵件會撰寫中。</span><span class="sxs-lookup"><span data-stu-id="f525c-247">The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span></span>
  
![撰寫郵件頂端的原則提示](../media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
<span data-ttu-id="f525c-249">原則提示會在郵件內文、主旨行或郵件附件中顯示機密資訊，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f525c-249">Policy tips work whether the sensitive information appears in the message body, subject line, or even a message attachment as shown here.</span></span>
  
![原則提示，顯示附件與 DLP 原則衝突](../media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
<span data-ttu-id="f525c-251">若原則提示設定為允許**覆寫，** \>您可以選擇 [**顯示詳細資料** \> ]。請輸入業務理由或報告誤報\> **。**</span><span class="sxs-lookup"><span data-stu-id="f525c-251">If the policy tips are configured to allow override, you can choose **Show Details** \> **Override** \> enter a business justification or report a false positive \> **Override**.</span></span>
  
![已展開郵件中的原則提示以顯示覆寫選項](../media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![[原則提示] 對話方塊，您可以在其中覆寫原則提示](../media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
<span data-ttu-id="f525c-254">請注意，當您將敏感資訊新增至電子郵件時，新增敏感資訊和顯示原則提示之間可能會有延遲。</span><span class="sxs-lookup"><span data-stu-id="f525c-254">Note that when you add sensitive information to an email, there may be latency between when the sensitive information is added and when the policy tip appears.</span></span>

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a><span data-ttu-id="f525c-255">Outlook 2013 和更新版本支援只顯示某些條件的原則提示</span><span class="sxs-lookup"><span data-stu-id="f525c-255">Outlook 2013 and later supports showing policy tips for only some conditions</span></span>

<span data-ttu-id="f525c-256">目前，Outlook 2013 和更新版本支援只顯示這些狀況的原則提示：</span><span class="sxs-lookup"><span data-stu-id="f525c-256">Currently, Outlook 2013 and later supports showing policy tips only for these conditions:</span></span>

- <span data-ttu-id="f525c-257">內容包含</span><span class="sxs-lookup"><span data-stu-id="f525c-257">Content contains</span></span>
- <span data-ttu-id="f525c-258">內容已共用</span><span class="sxs-lookup"><span data-stu-id="f525c-258">Content is shared</span></span>

<span data-ttu-id="f525c-259">請注意，所有這些條件都是在 Outlook 中運作，其將會符合內容，並強制執行內容的保護動作。</span><span class="sxs-lookup"><span data-stu-id="f525c-259">Note that all of these conditions work in Outlook, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="f525c-260">但尚未支援使用者顯示原則提示。</span><span class="sxs-lookup"><span data-stu-id="f525c-260">But showing policy tips to users is not yet supported.</span></span>
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-security-amp-compliance-center"></a><span data-ttu-id="f525c-261">Exchange 系統管理中心與安全性&amp;與合規性中心的原則提示</span><span class="sxs-lookup"><span data-stu-id="f525c-261">Policy tips in the Exchange admin center vs. the Security &amp; Compliance Center</span></span>

<span data-ttu-id="f525c-262">原則秘訣可以搭配在 Exchange 系統管理中心中建立的 DLP 原則和郵件流程規則，或是在安全性&amp;與合規性中心建立的 dlp 原則使用，但不能同時使用這兩者。</span><span class="sxs-lookup"><span data-stu-id="f525c-262">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security &amp; Compliance Center, but not both.</span></span> <span data-ttu-id="f525c-263">這是因為這些原則儲存在不同的位置，但是原則秘訣只能從單一位置進行繪製。</span><span class="sxs-lookup"><span data-stu-id="f525c-263">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="f525c-264">如果您已在 Exchange 系統管理中心中設定原則提示，在 [安全性&amp;與合規性中心] 中所設定的任何原則提示，都不會顯示在網頁和 outlook 2013 和更新版本中 outlook 的使用者，直到您關閉 Exchange 系統管理中心中的秘訣。</span><span class="sxs-lookup"><span data-stu-id="f525c-264">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="f525c-265">這可確保您目前的 Exchange 郵件流程規則（也稱為傳輸規則）可以繼續運作，直到您選擇切換到 [安全性&amp;與合規性中心] 為止。</span><span class="sxs-lookup"><span data-stu-id="f525c-265">This ensures that your current Exchange mail flow rules (also known as transport rules) will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="f525c-266">請注意，當原則提示只能從單一位置繪製時，系統會永遠傳送電子郵件通知，即使您同時在安全性&amp;與合規性中心和 Exchange 系統管理中心中使用 DLP 原則也是一樣。</span><span class="sxs-lookup"><span data-stu-id="f525c-266">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange admin center.</span></span>
  
### <a name="default-text-for-policy-tips-in-email"></a><span data-ttu-id="f525c-267">電子郵件中原則提示的預設文字</span><span class="sxs-lookup"><span data-stu-id="f525c-267">Default text for policy tips in email</span></span>

<span data-ttu-id="f525c-268">原則提示預設會針對電子郵件顯示類似下列的文字。</span><span class="sxs-lookup"><span data-stu-id="f525c-268">By default, policy tips display text similar to the following for email.</span></span>

|<span data-ttu-id="f525c-269">**如果 DLP 原則規則執行此動作 .。。**</span><span class="sxs-lookup"><span data-stu-id="f525c-269">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="f525c-270">**預設原則提示會說 .。。**</span><span class="sxs-lookup"><span data-stu-id="f525c-270">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f525c-271">傳送通知但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="f525c-271">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="f525c-272">您的電子郵件與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-272">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="f525c-273">封鎖存取、傳送通知及允許覆寫</span><span class="sxs-lookup"><span data-stu-id="f525c-273">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="f525c-274">您的電子郵件與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-274">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="f525c-275">封鎖存取及傳送通知</span><span class="sxs-lookup"><span data-stu-id="f525c-275">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="f525c-276">您的電子郵件與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-276">Your email conflicts with a policy in your organization.</span></span>  <br/> |
   
## <a name="policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="f525c-277">Excel、PowerPoint 及 Word 中的原則提示</span><span class="sxs-lookup"><span data-stu-id="f525c-277">Policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="f525c-278">當人員使用 Excel 的桌上出版本中的機密內容，PowerPoint 和 Word 時，原則秘訣可以即時通知內容與 DLP 原則衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-278">When people work with sensitive content in the desktop versions of Excel, PowerPoint, and Word, policy tips can notify them in real time that the content conflicts with a DLP policy.</span></span> <span data-ttu-id="f525c-279">這需要：</span><span class="sxs-lookup"><span data-stu-id="f525c-279">This requires that:</span></span>
  
- <span data-ttu-id="f525c-280">Office 檔儲存在商務網站的 OneDrive 或 SharePoint 線上網站上。</span><span class="sxs-lookup"><span data-stu-id="f525c-280">The Office document is stored on a OneDrive for Business site or SharePoint Online site.</span></span>
    
- <span data-ttu-id="f525c-281">此網站包含在設定為使用原則提示的 DLP 原則中。</span><span class="sxs-lookup"><span data-stu-id="f525c-281">The site is included in a DLP policy that's configured to use policy tips.</span></span>
    
<span data-ttu-id="f525c-282">Office 桌面程式會直接從 Office 365 自動同步處理 DLP 原則，然後掃描檔，以確保它們不會與您的 DLP 原則和即時顯示原則提示產生衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-282">Office desktop programs automatically sync DLP policies directly from Office 365, and then scan your documents to ensure that they don't conflict with your DLP policies and display policy tips in real time.</span></span>
  
<span data-ttu-id="f525c-283">根據您設定 DLP 原則中原則提示的方式，使用者可以選擇乾脆忽略原則提示、覆寫具有或沒有業務理由的原則，或報告誤報。</span><span class="sxs-lookup"><span data-stu-id="f525c-283">Depending on how you configure the policy tips in the DLP policy, people can choose to simply ignore the policy tip, override the policy with or without a business justification, or report a false positive.</span></span>
  
<span data-ttu-id="f525c-284">原則提示會出現在訊息欄上。</span><span class="sxs-lookup"><span data-stu-id="f525c-284">Policy tips appear on the Message Bar.</span></span>
  
![訊息列會顯示 Excel 2016 中的原則提示](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="f525c-286">原則提示也會出現在 Backstage 檢視中 **（在 [檔案] 索引**標籤上）。</span><span class="sxs-lookup"><span data-stu-id="f525c-286">And policy tips also appear in the Backstage view (on the **File** tab).</span></span> 
  
![Backstage 會顯示 Excel 2016 中的原則提示](../media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
<span data-ttu-id="f525c-288">如果已使用這些選項設定 DLP 原則中的原則提示，您可以選擇 [**解決**]，以覆**寫**原則提示或**報告**誤報。</span><span class="sxs-lookup"><span data-stu-id="f525c-288">If policy tips in the DLP policy are configured with these options, you can choose **Resolve** to **Override** a policy tip or **Report** a false positive.</span></span> 
  
![Excel 2016 的 Backstage 中的原則提示選項](../media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
<span data-ttu-id="f525c-290">在每個 Office 桌面程式中，使用者都可以選擇關閉原則提示。</span><span class="sxs-lookup"><span data-stu-id="f525c-290">In each of these Office desktop programs, people can choose to turn off policy tips.</span></span> <span data-ttu-id="f525c-291">關閉時，簡單通知的原則提示不會出現在訊息列或 Backstage 檢視（[檔案] 索引卷**標上）** 。</span><span class="sxs-lookup"><span data-stu-id="f525c-291">If turned off, policy tips that are simple notifications will not appear on the Message Bar or Backstage view (on the **File** tab).</span></span> <span data-ttu-id="f525c-292">不過，有關封鎖和覆寫的原則秘訣仍會出現，而且他們仍會收到電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="f525c-292">However, policy tips about blocking and overriding will still appear, and they will still receive the email notification.</span></span> <span data-ttu-id="f525c-293">此外，關閉原則提示不會從套用的任何 DLP 原則中免除檔。</span><span class="sxs-lookup"><span data-stu-id="f525c-293">In addition, turning off policy tips does not exempt the document from any DLP policies that have been applied to it.</span></span> 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="f525c-294">Excel 2016、PowerPoint 2016 及 Word 2016 中原則提示的預設文字</span><span class="sxs-lookup"><span data-stu-id="f525c-294">Default text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="f525c-295">原則提示預設會在已開啟檔的郵件列和 Backstage 檢視上顯示類似下列的文字。</span><span class="sxs-lookup"><span data-stu-id="f525c-295">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document.</span></span> <span data-ttu-id="f525c-296">通知文字會個別針對每個規則進行設定，因此顯示的文字會隨相符的規則而有所不同。</span><span class="sxs-lookup"><span data-stu-id="f525c-296">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="f525c-297">**如果 DLP 原則規則執行此動作 .。。**</span><span class="sxs-lookup"><span data-stu-id="f525c-297">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="f525c-298">**預設原則提示會說 .。。**</span><span class="sxs-lookup"><span data-stu-id="f525c-298">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f525c-299">傳送通知但不允許覆寫</span><span class="sxs-lookup"><span data-stu-id="f525c-299">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="f525c-300">此檔案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-300">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="f525c-301">移**至 [檔案**] 功能表以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f525c-301">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="f525c-302">封鎖存取、傳送通知及允許覆寫</span><span class="sxs-lookup"><span data-stu-id="f525c-302">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="f525c-303">此檔案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-303">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="f525c-304">如果您未解決此衝突，則可能會封鎖對此檔案的存取。</span><span class="sxs-lookup"><span data-stu-id="f525c-304">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="f525c-305">移**至 [檔案**] 功能表以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f525c-305">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="f525c-306">封鎖存取及傳送通知</span><span class="sxs-lookup"><span data-stu-id="f525c-306">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="f525c-307">此檔案與您組織中的原則相衝突。</span><span class="sxs-lookup"><span data-stu-id="f525c-307">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="f525c-308">如果您未解決此衝突，則可能會封鎖對此檔案的存取。</span><span class="sxs-lookup"><span data-stu-id="f525c-308">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="f525c-309">移**至 [檔案**] 功能表以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f525c-309">Go to the **File** menu for more information.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="f525c-310">Excel、PowerPoint 及 Word 中的原則提示的自訂文字</span><span class="sxs-lookup"><span data-stu-id="f525c-310">Custom text for policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="f525c-311">您可以從電子郵件通知中單獨自訂原則提示的文字。</span><span class="sxs-lookup"><span data-stu-id="f525c-311">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="f525c-312">與電子郵件通知的自訂文字（請參閱上一節）不同的是原則提示的自訂文字不接受 HTML 或標記。</span><span class="sxs-lookup"><span data-stu-id="f525c-312">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="f525c-313">相反地，[原則提示] 的自訂文字只會以256個字元的限制顯示純文字。</span><span class="sxs-lookup"><span data-stu-id="f525c-313">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="f525c-314">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="f525c-314">More information</span></span>

- [<span data-ttu-id="f525c-315">資料外洩防護原則概觀</span><span class="sxs-lookup"><span data-stu-id="f525c-315">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="f525c-316">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="f525c-316">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="f525c-317">建立 DLP 原則來保護具有 FCI 或其他屬性的文件</span><span class="sxs-lookup"><span data-stu-id="f525c-317">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="f525c-318">DLP 原則範本包含哪些內容</span><span class="sxs-lookup"><span data-stu-id="f525c-318">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="f525c-319">敏感性資訊類型在找什麼</span><span class="sxs-lookup"><span data-stu-id="f525c-319">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
