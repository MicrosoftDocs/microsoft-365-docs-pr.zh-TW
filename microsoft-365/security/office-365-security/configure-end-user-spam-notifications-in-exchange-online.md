---
title: 在 Exchange Online 中設定使用者垃圾郵件通知
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: 您可以設定使用者垃圾郵件通知的預設的全公司的垃圾郵件篩選原則或是網域所套用的自訂垃圾郵件篩選原則。
ms.openlocfilehash: c8690a64e222bca2bbdc6be62d1077a9d361ae85
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341294"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="32c9b-103">在 Exchange Online 中設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="32c9b-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32c9b-104">本主題適用於保護雲端託管信箱的 Exchange Online 客戶。</span><span class="sxs-lookup"><span data-stu-id="32c9b-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="32c9b-105">保護內部部署信箱的 Exchange Online Protection (EOP) 獨立客戶應改閱讀下列主題： [EOP 中的設定使用者垃圾郵件通知](configure-end-user-spam-notifications-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="32c9b-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="32c9b-106">您可以設定使用者垃圾郵件通知的預設的全公司的垃圾郵件篩選原則或自訂垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="32c9b-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="32c9b-107">啟用使用者垃圾郵件通知訊息，可讓您管理自己被隔離的垃圾郵件、 大量和網路釣魚郵件的使用者。</span><span class="sxs-lookup"><span data-stu-id="32c9b-107">Enabling end-user spam notification messages lets your users manage their own quarantined spam, bulk, and phishing messages.</span></span>   
  
<span data-ttu-id="32c9b-p103">使用者垃圾郵件通知包含使用者在您設定的時間期間 (您可指定 1 到 15 天之間的值) 內收到，被當成垃圾郵件隔離的所有郵件清單。您也可以設定用來撰寫通知郵件的語言。</span><span class="sxs-lookup"><span data-stu-id="32c9b-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="32c9b-110">之後收到通知郵件，使用者可以選擇下列選項：</span><span class="sxs-lookup"><span data-stu-id="32c9b-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="32c9b-111">**封鎖寄件者**如果您希望 Office 365 將寄件者新增至封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="32c9b-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="32c9b-112">**版本**如果郵件不是垃圾郵件，而且您希望 Office 365 將郵件傳送至您的信箱。</span><span class="sxs-lookup"><span data-stu-id="32c9b-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="32c9b-113">如果您想要採取其他動作，例如預覽或版本，瀏覽至隔離區入口網站安全性 & 合規性中心內的**檢閱**。</span><span class="sxs-lookup"><span data-stu-id="32c9b-113">**Review** to navigate to the Quarantine Portal within the Security & Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="32c9b-114">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="32c9b-114">What do you need to know before you begin?</span></span>

<span data-ttu-id="32c9b-115">預估完成時間：2 分鐘</span><span class="sxs-lookup"><span data-stu-id="32c9b-115">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="32c9b-116">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="32c9b-116">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="32c9b-117">若要查看您需要的權限，請參閱 [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) (部分機器翻譯) 主題中的「反垃圾郵件」項目。</span><span class="sxs-lookup"><span data-stu-id="32c9b-117">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span> 
  
<span data-ttu-id="32c9b-118">如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="32c9b-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="32c9b-119">使用 EAC 來設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="32c9b-119">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="32c9b-120">在 Exchange 系統管理中心 (EAC)，瀏覽至 **[保護]** \> **[垃圾郵件篩選]**。</span><span class="sxs-lookup"><span data-stu-id="32c9b-120">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="32c9b-121">選取您要啟用使用者垃圾郵件通知 （其預設會停用） 的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="32c9b-121">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="32c9b-122">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span><span class="sxs-lookup"><span data-stu-id="32c9b-122">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="32c9b-123">在後續的對話方塊中，您可以設定下列選項：</span><span class="sxs-lookup"><span data-stu-id="32c9b-123">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="32c9b-p105">**啟用使用者垃圾郵件通知** 選取此核取方塊，以啟用此原則的使用者垃圾郵件通知。(反之，如果此原則已啟用，您可以清除此核取方塊，以停用此原則的使用者垃圾郵件通知。)</span><span class="sxs-lookup"><span data-stu-id="32c9b-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="32c9b-p106">**傳送使用者垃圾郵件通知的間隔時間 (天數)** 指定傳送使用者垃圾郵件通知的頻率。預設值為 3 天。您可以指定 1 到 15 天之間的值。例如，如果您指定 7 天，則此通知將包含在過去 7 天內對象為該使用者，卻被當成垃圾郵件隔離的所有郵件的清單。</span><span class="sxs-lookup"><span data-stu-id="32c9b-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="32c9b-130">**通知語言** 您可以使用下拉式清單，選取用來撰寫此原則之使用者垃圾郵件通知的語言。</span><span class="sxs-lookup"><span data-stu-id="32c9b-130">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="32c9b-131">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="32c9b-131">Click **Save**.</span></span> <span data-ttu-id="32c9b-132">垃圾郵件篩選原則設定，包括您使用者的垃圾郵件通知設定的摘要隨即出現在右側窗格中。</span><span class="sxs-lookup"><span data-stu-id="32c9b-132">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="32c9b-133">使用者垃圾郵件通知才會正常運作的已啟用的垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="32c9b-133">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="32c9b-134">>  每天只傳送一次使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="32c9b-134">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="32c9b-135">無法向任何特定客戶保證通知傳遞的時間，且無法加以設定。</span><span class="sxs-lookup"><span data-stu-id="32c9b-135">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="32c9b-136">**提示：** 如果您想要完全實作它們之前將它們傳送到一組有限的使用者，以測試使用者垃圾郵件通知，建立可讓使用者都位於的網域之使用者垃圾郵件通知的自訂垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="32c9b-136">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="32c9b-137">接著，在 EAC 中，[**郵件流程\>規則**，且您想要接收通知的使用者的例外狀況從 quarantine@messaging.microsoft.com （傳送通知電子郵件通訊） 建立郵件流程規則 （也稱為傳輸規則） 來封鎖郵件。</span><span class="sxs-lookup"><span data-stu-id="32c9b-137">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="32c9b-138">下圖是從網域 Contoso.com 建立兩個使用者 (SaraD 和 AlexD) 之例外狀況的範例：</span><span class="sxs-lookup"><span data-stu-id="32c9b-138">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![測試使用者垃圾郵件通知的傳輸規則](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a><span data-ttu-id="32c9b-140">使用 SCC 來設定使用者垃圾郵件通知</span><span class="sxs-lookup"><span data-stu-id="32c9b-140">Use the SCC to configure end-user spam notifications</span></span>

<span data-ttu-id="32c9b-141">您也可以使用的安全性與合規性中心 (SCC) 來設定使用者垃圾郵件通知。</span><span class="sxs-lookup"><span data-stu-id="32c9b-141">You can also use the Security and Compliance Center (SCC) to configure end-user spam notifications.</span></span> <span data-ttu-id="32c9b-142">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="32c9b-142">Follow these steps:</span></span>

1. <span data-ttu-id="32c9b-143">開啟 [安全性與合規性中心，瀏覽至**威脅管理，** \> **原則** \> **反垃圾郵件**] 或 [使用直接連結https://protection.office.com/antispam。</span><span class="sxs-lookup"><span data-stu-id="32c9b-143">Open the Security and Compliance Center, navigate to **Threat management** \> **Policy** \> **Anti-spam** or use the direct link https://protection.office.com/antispam.</span></span>

2. <span data-ttu-id="32c9b-144">按一下您要啟用使用者垃圾郵件通知的垃圾郵件篩選器原則旁的向下箭號。</span><span class="sxs-lookup"><span data-stu-id="32c9b-144">Click the down arrow next to the spam filter policy for which you want to enable end-user spam notifications.</span></span>

3. <span data-ttu-id="32c9b-145">按一下 [**設定使用者垃圾郵件通知**] 連結。</span><span class="sxs-lookup"><span data-stu-id="32c9b-145">Click on the **Configure End-user spam notifications** link.</span></span>

4. <span data-ttu-id="32c9b-146">在後續的對話方塊中，您可以設定下列選項：</span><span class="sxs-lookup"><span data-stu-id="32c9b-146">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="32c9b-p111">**啟用使用者垃圾郵件通知** 選取此核取方塊，以啟用此原則的使用者垃圾郵件通知。(反之，如果此原則已啟用，您可以清除此核取方塊，以停用此原則的使用者垃圾郵件通知。)</span><span class="sxs-lookup"><span data-stu-id="32c9b-p111">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="32c9b-p112">**傳送使用者垃圾郵件通知的間隔時間 (天數)** 指定傳送使用者垃圾郵件通知的頻率。預設值為 3 天。您可以指定 1 到 15 天之間的值。例如，如果您指定 7 天，則此通知將包含在過去 7 天內對象為該使用者，卻被當成垃圾郵件隔離的所有郵件的清單。</span><span class="sxs-lookup"><span data-stu-id="32c9b-p112">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="32c9b-153">**通知語言** 您可以使用下拉式清單，選取用來撰寫此原則之使用者垃圾郵件通知的語言。</span><span class="sxs-lookup"><span data-stu-id="32c9b-153">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="32c9b-154">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="32c9b-154">Click **Save**.</span></span> <span data-ttu-id="32c9b-155">垃圾郵件篩選原則設定，包括您使用者的垃圾郵件通知設定的摘要隨即出現在窗格中。</span><span class="sxs-lookup"><span data-stu-id="32c9b-155">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the pane.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="32c9b-156">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="32c9b-156">For more information</span></span>

[<span data-ttu-id="32c9b-157">設定您的垃圾郵件篩選原則</span><span class="sxs-lookup"><span data-stu-id="32c9b-157">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="32c9b-158">Set-hostedcontentfilterpolicy</span><span class="sxs-lookup"><span data-stu-id="32c9b-158">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)
  
