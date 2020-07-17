---
title: 為組織中的每個人設定焦點收件匣
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: '了解如何為貴組織的所有或特定使用者設定焦點收件匣。 '
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779926"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a><span data-ttu-id="ae1de-103">為組織中的每個人設定焦點收件匣</span><span class="sxs-lookup"><span data-stu-id="ae1de-103">Configure Focused Inbox for everyone in your organization</span></span>

  <span data-ttu-id="ae1de-104">如果您負責為企業中的每個人設定電子郵件的運作方式，本文就是為您準備的！</span><span class="sxs-lookup"><span data-stu-id="ae1de-104">If you're responsible for configuring how email works for EVERYONE in a business this article is for you!</span></span> <span data-ttu-id="ae1de-105">本文說明如何為您的企業自訂或關閉焦點收件匣，以及回答[常見問題集](#faq-for-focused-inbox)。</span><span class="sxs-lookup"><span data-stu-id="ae1de-105">It explains how to customize it or turn it off for your business, and answers [frequently asked questions](#faq-for-focused-inbox).</span></span>  <br/> <span data-ttu-id="ae1de-106">如果您只想要關閉自己的焦點收件匣，請參閱[關閉焦點收件匣](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2)。</span><span class="sxs-lookup"><span data-stu-id="ae1de-106">If you would like to turn off Focused Inbox for just yourself, please see [Turn off Focused Inbox](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span></span>  
   
<span data-ttu-id="ae1de-p102">如果您想要確認您的使用者接收特定商務電子郵件訊息 (例如 HR 或薪資資料)，您可以設定焦點收件匣，讓這些訊息可送往 [焦點] 檢視。您也可以控制您組織中的使用者是否會在信箱中看到焦點收件匣。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p102">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a><span data-ttu-id="ae1de-109">開啟或關閉組織中的焦點收件匣</span><span class="sxs-lookup"><span data-stu-id="ae1de-109">Turn Focused Inbox On or Off in your organization</span></span>

<span data-ttu-id="ae1de-110">您可以使用 PowerShell 為組織中的每個人開啟或關閉焦點收件匣。</span><span class="sxs-lookup"><span data-stu-id="ae1de-110">You use PowerShell to turn Focused Inbox on or off for everyone in your organization.</span></span> <span data-ttu-id="ae1de-111">您要在 Microsoft 365 系統管理中心執行這個動作嗎？</span><span class="sxs-lookup"><span data-stu-id="ae1de-111">Do you want to do this in the Microsoft 365 admin center?</span></span> <span data-ttu-id="ae1de-112">讓我們的工程小組知道。</span><span class="sxs-lookup"><span data-stu-id="ae1de-112">Let our Engineering team know.</span></span> <span data-ttu-id="ae1de-113">**[在這裡投票！](https://go.microsoft.com/fwlink/?linkid=862489)**</span><span class="sxs-lookup"><span data-stu-id="ae1de-113">**[Vote here!](https://go.microsoft.com/fwlink/?linkid=862489)**</span></span>
  
 <span data-ttu-id="ae1de-114">**關閉焦點收件匣：**</span><span class="sxs-lookup"><span data-stu-id="ae1de-114">**To turn off Focused Inbox:**</span></span>
  
<span data-ttu-id="ae1de-115">下列 PowerShell 範例會 **[關閉]** 組織中的焦點收件匣。</span><span class="sxs-lookup"><span data-stu-id="ae1de-115">The following PowerShell example turns Focused Inbox **Off** in your organization.</span></span> <span data-ttu-id="ae1de-116">但是，它不會阻止您的使用者使用該功能。</span><span class="sxs-lookup"><span data-stu-id="ae1de-116">However, it doesn't block the availability of the feature for your users.</span></span> <span data-ttu-id="ae1de-117">如果使用者想要的話，他們仍然可以在每個用戶端重新啟用焦點收件匣。</span><span class="sxs-lookup"><span data-stu-id="ae1de-117">If they want, they can still re-enable Focused Inbox again on each of their clients.</span></span> 
  
1. <span data-ttu-id="ae1de-118">[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="ae1de-118">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="ae1de-p105">您需要先獲指派權限，才能執行此程序或各個程序。若要查看您需要哪些權限，請參閱[訊息原則與合規性權限](https://go.microsoft.com/fwlink/p/?LinkId=829796) 中的「傳輸規則」項目。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>
    
3. <span data-ttu-id="ae1de-121">執行 **Get-OrganizationConfig** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae1de-121">Run the **Get-OrganizationConfig** cmdlet.</span></span> 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. <span data-ttu-id="ae1de-122">尋找 **FocusedInboxOn** 以檢視其目前的設定：</span><span class="sxs-lookup"><span data-stu-id="ae1de-122">Look for **FocusedInboxOn** to view its current setting:</span></span> 
    
    ![處於焦點收件匣狀態時的 PowerShell 回應。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="ae1de-124">執行下列 Cmdlet 關閉焦點收件匣。</span><span class="sxs-lookup"><span data-stu-id="ae1de-124">Run the following cmdlet to turn Focused Inbox off.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. <span data-ttu-id="ae1de-125">再次執行 **Get-OrganizationConfig** cmdlet ，您就會看到 FocusedInboxOn 設為 $false，這表示它已經關閉。</span><span class="sxs-lookup"><span data-stu-id="ae1de-125">Run the **Get-OrganizationConfig** cmdlet again and you'll see that FocusedInboxOn is set to $false, which means it's been turned off.</span></span> 
    
 <span data-ttu-id="ae1de-126">**開啟焦點收件匣：**</span><span class="sxs-lookup"><span data-stu-id="ae1de-126">**To turn on Focused Inbox:**</span></span>
  
- <span data-ttu-id="ae1de-127">在上方步驟 5 中，執行下列 cmdlet 可開啟焦點收件匣。</span><span class="sxs-lookup"><span data-stu-id="ae1de-127">In Step 5 above, run the following cmdlet to turn Focused Inbox on.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a><span data-ttu-id="ae1de-128">開啟焦點收件匣之後，使用者會看見什麼？</span><span class="sxs-lookup"><span data-stu-id="ae1de-128">What do users see after I turn on Focused Inbox?</span></span>

<span data-ttu-id="ae1de-p106">當使用者關閉並重新啟動 Outlook 之後，只會看到 [焦點] 檢視。當他們重新啟動 Outlook 後，就會在 Outlook 使用者介面看見一則提示，提供他們使用新焦點收件匣的選項。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p106">Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span></span>
  
![使用者第一次開啟 Outlook 網頁版時的焦點收件匣外觀影像。](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
<span data-ttu-id="ae1de-p107">如果您從 [待過濾郵件] 切換至 [焦點收件匣]，他們能決定要啟用 ([試用]) 或是關閉該功能。如果使用者有多個 (受支援的) 用戶端，他們能個別啟用/停用其 [焦點收件匣]。提示看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="ae1de-p107">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:</span></span>
  
![向使用者推出焦點收件匣以及重新開啟 Outlook 時，焦點收件匣外觀的影像。](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
<span data-ttu-id="ae1de-p108">當使用者決定要開始使用 [焦點收件匣] 時，[待過濾郵件] 便會自動停用。該 [待過濾郵件] 資料夾會轉換成一般的資料夾，讓使用者能重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p108">When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a><span data-ttu-id="ae1de-138">針對特定的使用者開啟或關閉焦點收件匣</span><span class="sxs-lookup"><span data-stu-id="ae1de-138">Turn Focused Inbox On or Off for specific users</span></span>

<span data-ttu-id="ae1de-139">此範例針對 Contoso 組織中的 Tim Matthews 關閉\*\*\*\* 焦點收件匣。</span><span class="sxs-lookup"><span data-stu-id="ae1de-139">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization.</span></span> <span data-ttu-id="ae1de-140">但是，它不會阻止他使用該功能。</span><span class="sxs-lookup"><span data-stu-id="ae1de-140">However, it doesn't block the availability of the feature to him.</span></span> <span data-ttu-id="ae1de-141">如果他想要的話，仍然可以在每個用戶端重新啟用焦點收件匣。</span><span class="sxs-lookup"><span data-stu-id="ae1de-141">If his wants, he can still re-enable Focused Inbox again on each of his clients.</span></span> 
  
1. <span data-ttu-id="ae1de-142">[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="ae1de-142">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="ae1de-p110">需要先指派權限，您才能執行此程序或各個程序。若要查看您需要哪些權限，請參閱訊息原則與合規性權限主題中的「傳輸規則」項目。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p110">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span></span>
    
3. <span data-ttu-id="ae1de-145">執行 **Get-FocusedInbox** cmdlet，例如：</span><span class="sxs-lookup"><span data-stu-id="ae1de-145">Run the **Get-FocusedInbox** cmdlet, for example:</span></span> 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. <span data-ttu-id="ae1de-146">尋找 FocusedInboxOn 以檢視其目前的設定：</span><span class="sxs-lookup"><span data-stu-id="ae1de-146">Look for FocusedInboxOn to view its current setting:</span></span>
    
    ![處於焦點收件匣狀態時的 PowerShell 回應。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="ae1de-148">執行下列 Cmdlet 關閉焦點收件匣：</span><span class="sxs-lookup"><span data-stu-id="ae1de-148">Run the following cmdlet to turn Focused Inbox off:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. <span data-ttu-id="ae1de-149">或者，執行下列 Cmdlet 將它開啟：</span><span class="sxs-lookup"><span data-stu-id="ae1de-149">OR, run the following cmdlet to turn it on:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="ae1de-150">使用 UI 建立傳輸規則，將電子郵件導向至所有使用者的 [焦點] 檢視。</span><span class="sxs-lookup"><span data-stu-id="ae1de-150">Use the UI to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="ae1de-151">移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="ae1de-151">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="ae1de-152">瀏覽至 **[郵件流程]** \> **[規則]**。</span><span class="sxs-lookup"><span data-stu-id="ae1de-152">Navigate to **mail flow** \> **Rules**.</span></span> <span data-ttu-id="ae1de-153">選取 ![[EAC 新增] 圖示](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif)，然後選取 **[建立新的規則...]**。</span><span class="sxs-lookup"><span data-stu-id="ae1de-153">Select ![EAC Add icon](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) and then select **Create a new rule...**.</span></span> 
    
3. <span data-ttu-id="ae1de-154">建立新的規則完成後，選取 **[儲存]** 以啟動規則。</span><span class="sxs-lookup"><span data-stu-id="ae1de-154">After you're done creating the new rule, select **Save** to start the rule.</span></span> 
    
    <span data-ttu-id="ae1de-155">下列影像顯示讓來自「薪資部門」的所有郵件傳送到焦點收件匣的範例。</span><span class="sxs-lookup"><span data-stu-id="ae1de-155">The following image shows an example where all messages From "Payroll Department" are to be delivered to the Focused Inbox.</span></span>
    
    ![focusedinbox 薪資](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="ae1de-157">使用 PowerShell 建立傳輸規則，將電子郵件導向至所有使用者的 [焦點] 檢視</span><span class="sxs-lookup"><span data-stu-id="ae1de-157">Use PowerShell to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="ae1de-158">[使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="ae1de-158">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="ae1de-p112">您需要先獲指派權限，才能執行此程序或各個程序。若要查看您需要哪些權限，請參閱[訊息原則與合規性權限](https://go.microsoft.com/fwlink/p/?LinkId=829796) 中的「傳輸規則」項目。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p112">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>

3. <span data-ttu-id="ae1de-161">例如，執行下列命令，讓來自「薪資部門」的所有郵件傳送到焦點收件匣。</span><span class="sxs-lookup"><span data-stu-id="ae1de-161">Run the following command to allow all messages from "Payroll Department," for example, to be delivered to the Focused Inbox.</span></span>
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> <span data-ttu-id="ae1de-162">在此範例中，"X-MS-Exchange-Organization-BypassFocusedInbox" 和 "true" 有區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="ae1de-162">In this example, both "X-MS-Exchange-Organization-BypassFocusedInbox" and "true" are case sensitive.</span></span>
> <span data-ttu-id="ae1de-163">同時，焦點收件匣會受限於略過待過濾郵件的 X 標頭，因此，如果在待過濾郵件中使用此設定，它也將用於焦點收件匣。</span><span class="sxs-lookup"><span data-stu-id="ae1de-163">Also, Focused Inbox will honor the X-header that bypasses Clutter, so if you use this setting in Clutter, it will be used in Focused Inbox.</span></span> <span data-ttu-id="ae1de-164">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194)。</span><span class="sxs-lookup"><span data-stu-id="ae1de-164">For detailed syntax and parameter information, see [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ae1de-165">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="ae1de-165">How do you know this worked?</span></span>

<span data-ttu-id="ae1de-166">您可以檢查電子郵件訊息標題，以查看電子郵件是否由於略過焦點收件匣傳輸規則，而在收件箱中登陸。</span><span class="sxs-lookup"><span data-stu-id="ae1de-166">You can check email message headers to see if the email messages are landing in the Inbox due to the Focused Inbox transport rule bypass.</span></span> <span data-ttu-id="ae1de-167">從組織中已套用焦點收件匣傳輸規則的信箱中，選擇一封電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ae1de-167">Pick an email message from a mailbox in your organization that has the Focused Inbox transport rule applied.</span></span> <span data-ttu-id="ae1de-168">查看郵件上的標題，您應該會看到 **X-MS-Exchange-Organization-BypassFocusedInbox: true** 標題。</span><span class="sxs-lookup"><span data-stu-id="ae1de-168">Look at the headers stamped on the message, and you should see the **X-MS-Exchange-Organization-BypassFocusedInbox: true** header.</span></span> <span data-ttu-id="ae1de-169">這表示略過正常運作。</span><span class="sxs-lookup"><span data-stu-id="ae1de-169">This means the bypass is working.</span></span> <span data-ttu-id="ae1de-170">如需如何尋找標題資訊的詳細資訊，請查看 [檢視電子郵件的網際網路標題資訊](https://go.microsoft.com/fwlink/p/?LinkId=822530) 文章。</span><span class="sxs-lookup"><span data-stu-id="ae1de-170">Check out the [View the Internet header information for an email message](https://go.microsoft.com/fwlink/p/?LinkId=822530) article for info on how to find the header information.</span></span> 
 
## <a name="turn-onoff-clutter"></a><span data-ttu-id="ae1de-171">開啟/關閉 [待過濾郵件]</span><span class="sxs-lookup"><span data-stu-id="ae1de-171">Turn on/off Clutter</span></span>
 
<span data-ttu-id="ae1de-p115">我們收到的報告指出，部分使用者的 [待過濾郵件] 會突然停止運作。如果發生這種情況，您可以為特定的使用者重新啟用。請參閱[為貴組織設定待過濾郵件](../email/configure-clutter.md)。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p115">We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).</span></span>
 
## <a name="faq-for-focused-inbox"></a><span data-ttu-id="ae1de-175">焦點收件匣常見問題集</span><span class="sxs-lookup"><span data-stu-id="ae1de-175">FAQ for Focused Inbox</span></span>

<span data-ttu-id="ae1de-176">以下是關於焦點收件匣常見問題集的解答。</span><span class="sxs-lookup"><span data-stu-id="ae1de-176">Here are answers to Frequently Asked Questions about Focused Inbox.</span></span> 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a><span data-ttu-id="ae1de-177">我是否可以控制在我的組織中推出焦點收件匣的方式？</span><span class="sxs-lookup"><span data-stu-id="ae1de-177">Can I control how I roll out Focused Inbox in my organization?</span></span>

<span data-ttu-id="ae1de-p116">是。您可以針對整個組織開啟或關閉焦點收件匣，也可以針對指定的使用者開啟或關閉該功能。請參閱上述內容。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p116">Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.</span></span>
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a><span data-ttu-id="ae1de-181">焦點收件匣功能「僅適用於」Office 2016 用戶端嗎？</span><span class="sxs-lookup"><span data-stu-id="ae1de-181">Is the Focused Inbox feature ONLY available for Office 2016 clients?</span></span>

<span data-ttu-id="ae1de-182">是的，只有 Office 2016 的使用者會受到影響。</span><span class="sxs-lookup"><span data-stu-id="ae1de-182">Yes, only users with Office 2016 are affected.</span></span> <span data-ttu-id="ae1de-183">該功能不會回溯到 Outlook 2013 或更舊版本。</span><span class="sxs-lookup"><span data-stu-id="ae1de-183">The feature is not going to be backported to Outlook 2013 or earlier.</span></span>
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a><span data-ttu-id="ae1de-184">焦點收件匣變更需要多久時間才能在 Outlook 中生效？</span><span class="sxs-lookup"><span data-stu-id="ae1de-184">How long does it take for Focused Inbox changes to take place in Outlook?</span></span>

<span data-ttu-id="ae1de-185">一旦您開啟或關閉焦點收件匣，設定將在您的使用者關閉並重新啟動 Outlook 後生效。</span><span class="sxs-lookup"><span data-stu-id="ae1de-185">Once you turn on or turn off Focused Inbox, the settings will take effect once your users close and restart Outlook.</span></span>
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a><span data-ttu-id="ae1de-186">當我開啟焦點收件匣之後，待過濾郵件會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="ae1de-186">What happens to Clutter once I turn on Focused Inbox?</span></span>

<span data-ttu-id="ae1de-p118">切換之後，您的 [待過濾郵件] 資料夾就不會再收到可執行的電子郵件。電子郵件將改為分類至收件匣的 [焦點] 及 [其他] 索引標籤中。用來將郵件移至 [待過濾郵件] 資料夾的相同演算法現在改用來實現焦點收件匣功能，也就是說以前設定為移至 [待過濾郵件] 的任何電子郵件，現在都會移至 [其他]。已經在 [待過濾郵件] 資料夾中的任何郵件仍會留在該資料夾中，直到您決定刪除或移動它們為止。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p118">After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span></span>
  
<span data-ttu-id="ae1de-191">請參閱 Microsoft 最有價值專家 [Tony Redmond](https://www.petri.com/author/tony-redmond) 的這篇文章： [焦點收件匣如何取代 Office 365 內部的待過濾郵件](https://www.petri.com/focused-inbox-office-365) (英文)。</span><span class="sxs-lookup"><span data-stu-id="ae1de-191">Check out this post by [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span></span>
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a><span data-ttu-id="ae1de-192">可讓使用者各自使用待過濾郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="ae1de-192">Can I keep users on Clutter?</span></span> <span data-ttu-id="ae1de-193">Microsoft 對使用待過濾郵件與焦點收件匣的建議是什麼？</span><span class="sxs-lookup"><span data-stu-id="ae1de-193">What is Microsoft's recommendation when it comes to using Clutter vs Focused Inbox?</span></span>

<span data-ttu-id="ae1de-p120">是，您可以讓使用者使用待過濾郵件功能，並停用焦點收件匣，但最終焦點收件匣會完全取代待過濾郵件，因此，Microsoft 建議您立即移動至焦點收件匣。若要深入了解搭配 Exchange Online 使用待過濾郵件的時機，請參閱此部落格文章：[焦點收件匣和待過濾郵件計劃的更新](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p120">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span></span>
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a><span data-ttu-id="ae1de-196">如果我們要將每個人都移動到焦點收件匣，我是否應該為我的使用者停用待過濾郵件？</span><span class="sxs-lookup"><span data-stu-id="ae1de-196">Should I disable Clutter for my end users if we are going to move everyone to Focused Inbox?</span></span>

<span data-ttu-id="ae1de-p121">否。可以透過執行 Set-Clutter Cmdlet 針對信箱明確停用待過濾郵件。但是，如果您這麼做，信箱擁有者會看到先前已重新導向到 [待過濾郵件] 資料夾的郵件保留在收件匣中，且他們必須處理這些郵件，直到他們的用戶端升級為支援焦點收件匣的版本。因此，在可以使用升級的用戶端之前，不建議停用待過濾郵件。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p121">No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.</span></span>
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a><span data-ttu-id="ae1de-201">為什麼有兩個不同的 Cmdlet 可用來管理焦點收件匣？</span><span class="sxs-lookup"><span data-stu-id="ae1de-201">Why are there two different cmdlets for managing Focused Inbox?</span></span>

<span data-ttu-id="ae1de-202">有兩個狀態與焦點收件匣相關聯。</span><span class="sxs-lookup"><span data-stu-id="ae1de-202">There are two states associated with Focused Inbox.</span></span>
  
- <span data-ttu-id="ae1de-203">**組織層級**：焦點收件匣狀態，以及相關聯的最後更新時間戳記。</span><span class="sxs-lookup"><span data-stu-id="ae1de-203">**Organization Level**: Focused Inbox state, and an associated last update time-stamp.</span></span> 
    
- <span data-ttu-id="ae1de-204">**信箱層級**：焦點收件匣狀態，以及相關聯的最後更新時間戳記。</span><span class="sxs-lookup"><span data-stu-id="ae1de-204">**Mailbox Level**: Focused Inbox state, and an associated last update time-stamp</span></span> 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a><span data-ttu-id="ae1de-205">Outlook 如何決定透過這兩種狀態顯示焦點收件匣體驗？</span><span class="sxs-lookup"><span data-stu-id="ae1de-205">How does Outlook decide to show the Focused Inbox experience with these two states?</span></span>

<span data-ttu-id="ae1de-p122">Outlook 會透過選擇具有最新時間戳記的 Cmdlet 來顯示體驗。根據預設，這兩個時間戳記都是 "null"，在此情況下會啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p122">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.</span></span>
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a><span data-ttu-id="ae1de-208">當我在組織中將焦點收件匣關閉時，為什麼 Get-FocusedInbox Cmdlet 會傳回 “true”？</span><span class="sxs-lookup"><span data-stu-id="ae1de-208">Why does the Get-FocusedInbox cmdlet return "true", when I've turned Focused Inbox off in my organization?</span></span>

<span data-ttu-id="ae1de-p123">有兩個用於控制焦點收件匣的 Cmdlet。當您針對信箱執行 Get-FocusedInbox 時，它會傳回功能的信箱層級狀態。Outlook 中的體驗是根據前次修改的 Cmdlet 狀態來選擇的。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p123">There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.</span></span>
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a><span data-ttu-id="ae1de-212">是否可以執行指令碼以查看誰開啟焦點收件匣？</span><span class="sxs-lookup"><span data-stu-id="ae1de-212">Can I run a script to see who has turned on Focused Inbox?</span></span>

<span data-ttu-id="ae1de-p124">否，這是預設的設計。焦點收件匣啟用為用戶端設定，因此 Cmdlet 只能告訴您使用者的信箱是否符合用戶端體驗的資格。有可能發生某些用戶端啟用焦點收件匣，但某些用戶端停用這項功能的情況，比方說，在 Outlook App 啟用焦點收件匣，但在 Outlook 網頁版停用此功能。</span><span class="sxs-lookup"><span data-stu-id="ae1de-p124">No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span></span>
