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
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>為組織中的每個人設定焦點收件匣

  如果您負責為企業中的每個人設定電子郵件的運作方式，本文就是為您準備的！ 本文說明如何為您的企業自訂或關閉焦點收件匣，以及回答[常見問題集](#faq-for-focused-inbox)。  <br/> 如果您只想要關閉自己的焦點收件匣，請參閱[關閉焦點收件匣](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2)。  
   
If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>開啟或關閉組織中的焦點收件匣

您可以使用 PowerShell 為組織中的每個人開啟或關閉焦點收件匣。 您要在 Microsoft 365 系統管理中心執行這個動作嗎？ 讓我們的工程小組知道。 **[在這裡投票！](https://go.microsoft.com/fwlink/?linkid=862489)**
  
 **關閉焦點收件匣：**
  
下列 PowerShell 範例會 **[關閉]** 組織中的焦點收件匣。 但是，它不會阻止您的使用者使用該功能。 如果使用者想要的話，他們仍然可以在每個用戶端重新啟用焦點收件匣。 
  
1. [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).
    
3. 執行 **Get-OrganizationConfig** Cmdlet。 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. 尋找 **FocusedInboxOn** 以檢視其目前的設定： 
    
    ![處於焦點收件匣狀態時的 PowerShell 回應。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. 執行下列 Cmdlet 關閉焦點收件匣。
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. 再次執行 **Get-OrganizationConfig** cmdlet ，您就會看到 FocusedInboxOn 設為 $false，這表示它已經關閉。 
    
 **開啟焦點收件匣：**
  
- 在上方步驟 5 中，執行下列 cmdlet 可開啟焦點收件匣。
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>開啟焦點收件匣之後，使用者會看見什麼？

Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.
  
![使用者第一次開啟 Outlook 網頁版時的焦點收件匣外觀影像。](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:
  
![向使用者推出焦點收件匣以及重新開啟 Outlook 時，焦點收件匣外觀的影像。](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>針對特定的使用者開啟或關閉焦點收件匣

此範例針對 Contoso 組織中的 Tim Matthews 關閉**** 焦點收件匣。 但是，它不會阻止他使用該功能。 如果他想要的話，仍然可以在每個用戶端重新啟用焦點收件匣。 
  
1. [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.
    
3. 執行 **Get-FocusedInbox** cmdlet，例如： 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. 尋找 FocusedInboxOn 以檢視其目前的設定：
    
    ![處於焦點收件匣狀態時的 PowerShell 回應。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. 執行下列 Cmdlet 關閉焦點收件匣：
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. 或者，執行下列 Cmdlet 將它開啟：
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>使用 UI 建立傳輸規則，將電子郵件導向至所有使用者的 [焦點] 檢視。

1. 移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。
    
2. 瀏覽至 **[郵件流程]** \> **[規則]**。 選取 ![[EAC 新增] 圖示](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif)，然後選取 **[建立新的規則...]**。 
    
3. 建立新的規則完成後，選取 **[儲存]** 以啟動規則。 
    
    下列影像顯示讓來自「薪資部門」的所有郵件傳送到焦點收件匣的範例。
    
    ![focusedinbox 薪資](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>使用 PowerShell 建立傳輸規則，將電子郵件導向至所有使用者的 [焦點] 檢視

1. [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).

3. 例如，執行下列命令，讓來自「薪資部門」的所有郵件傳送到焦點收件匣。
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> 在此範例中，"X-MS-Exchange-Organization-BypassFocusedInbox" 和 "true" 有區分大小寫。
> 同時，焦點收件匣會受限於略過待過濾郵件的 X 標頭，因此，如果在待過濾郵件中使用此設定，它也將用於焦點收件匣。 如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194)。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

您可以檢查電子郵件訊息標題，以查看電子郵件是否由於略過焦點收件匣傳輸規則，而在收件箱中登陸。 從組織中已套用焦點收件匣傳輸規則的信箱中，選擇一封電子郵件。 查看郵件上的標題，您應該會看到 **X-MS-Exchange-Organization-BypassFocusedInbox: true** 標題。 這表示略過正常運作。 如需如何尋找標題資訊的詳細資訊，請查看 [檢視電子郵件的網際網路標題資訊](https://go.microsoft.com/fwlink/p/?LinkId=822530) 文章。 
 
## <a name="turn-onoff-clutter"></a>開啟/關閉 [待過濾郵件]
 
We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).
 
## <a name="faq-for-focused-inbox"></a>焦點收件匣常見問題集

以下是關於焦點收件匣常見問題集的解答。 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>我是否可以控制在我的組織中推出焦點收件匣的方式？

Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>焦點收件匣功能「僅適用於」Office 2016 用戶端嗎？

是的，只有 Office 2016 的使用者會受到影響。 該功能不會回溯到 Outlook 2013 或更舊版本。
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>焦點收件匣變更需要多久時間才能在 Outlook 中生效？

一旦您開啟或關閉焦點收件匣，設定將在您的使用者關閉並重新啟動 Outlook 後生效。
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>當我開啟焦點收件匣之後，待過濾郵件會發生什麼情況？

After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.
  
請參閱 Microsoft 最有價值專家 [Tony Redmond](https://www.petri.com/author/tony-redmond) 的這篇文章： [焦點收件匣如何取代 Office 365 內部的待過濾郵件](https://www.petri.com/focused-inbox-office-365) (英文)。
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>可讓使用者各自使用待過濾郵件嗎？ Microsoft 對使用待過濾郵件與焦點收件匣的建議是什麼？

Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>如果我們要將每個人都移動到焦點收件匣，我是否應該為我的使用者停用待過濾郵件？

No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>為什麼有兩個不同的 Cmdlet 可用來管理焦點收件匣？

有兩個狀態與焦點收件匣相關聯。
  
- **組織層級**：焦點收件匣狀態，以及相關聯的最後更新時間戳記。 
    
- **信箱層級**：焦點收件匣狀態，以及相關聯的最後更新時間戳記。 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Outlook 如何決定透過這兩種狀態顯示焦點收件匣體驗？

Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>當我在組織中將焦點收件匣關閉時，為什麼 Get-FocusedInbox Cmdlet 會傳回 “true”？

There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>是否可以執行指令碼以查看誰開啟焦點收件匣？

No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.
