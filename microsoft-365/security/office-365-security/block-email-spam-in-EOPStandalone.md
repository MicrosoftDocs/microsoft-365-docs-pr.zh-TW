---
title: 在 EOP 獨立版中封鎖垃圾郵件
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 2/25/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: da21c0b6-e8f0-4cc8-af2e-5029a9433d59
ms.collection:
- M365-security-compliance
description: EOP 獨立版系統管理員適用的文件，以協助防止垃圾郵件誤判
ms.openlocfilehash: b3b4005016d8a4192241299cac50eddf59f332d5
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895414"
---
# <a name="customize-the-office-365-anti-spam-filter-with-these-settings"></a><span data-ttu-id="b741b-103">利用這些設定來自訂 Office 365 反垃圾郵件篩選器</span><span class="sxs-lookup"><span data-stu-id="b741b-103">Customize the Office 365 anti-spam filter with these settings</span></span>

<span data-ttu-id="b741b-p101">系統管理員可以使用數個 Office 365 垃圾郵件篩選器設定，來協助防止垃圾郵件傳送到使用者收件匣。如果您使用此處所列的選項，Office 365 垃圾郵件篩選器將更能封鎖垃圾郵件，並避免誤判郵件。在此情況下，誤判指的是垃圾郵件傳送到使用者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="b741b-p101">An Admin can use several Office 365 spam filter settings to help prevent email spam from being sent to a user inbox. The Office 365 spam filter will become better able to block email spam and prevent false negative messages if you use the options listed here. In this context, a false negative refers to email spam or junk messages that are getting sent to a user inbox.</span></span>

## <a name="block-ip-addresses-with-a-connection-filter"></a><span data-ttu-id="b741b-107">利用連線篩選器封鎖 IP 位址</span><span class="sxs-lookup"><span data-stu-id="b741b-107">Block IP addresses with a connection filter</span></span>

<span data-ttu-id="b741b-108">將寄件者 IP 位址新增到連線篩選器 IP 封鎖清單，來自訂您的 Office 365 垃圾郵件篩選器：</span><span class="sxs-lookup"><span data-stu-id="b741b-108">Customize your Office 365 spam filter by adding the sender IP address to the connection filter IP block list:</span></span>

1. <span data-ttu-id="b741b-109">如 [在 Outlook 中查看網際網路郵件標題](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)所述，取得您想要在郵件用戶端 (例如 Outlook 或 Outlook 網頁版 (之前稱為 Outlook Web App)) 封鎖之郵件的標頭。</span><span class="sxs-lookup"><span data-stu-id="b741b-109">Obtain the headers for the message you want to block in your mail client such as Outlook or Outlook on the web (formerly known as Outlook Web App), as described in [View internet message headers in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

2. <span data-ttu-id="b741b-110">使用[郵件標頭分析器](https://testconnectivity.microsoft.com/?tabid=mha)或手動搜尋位在 X-Forefront-Antispam-Report 標頭中 CIP 標籤後面的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b741b-110">Search for the IP address following the CIP tag in the X-Forefront-Antispam-Report header using the [message header analyzer](https://testconnectivity.microsoft.com/?tabid=mha) or manually.</span></span>

3. <span data-ttu-id="b741b-111">遵循[設定連線篩選原則](configure-the-connection-filter-policy.md) 中「使用 EAC 來編輯預設連線篩選原則」中的步驟，將 IP 位址新增至 IP 封鎖清單。</span><span class="sxs-lookup"><span data-stu-id="b741b-111">Add the IP address to the IP Block list by following the steps in "Use the EAC to edit the default connection filter policy" in [Configure the Connection Filter Policy](configure-the-connection-filter-policy.md).</span></span>

### <a name="block-bulk-mail-with-mail-flow-rules-transport-rules-or-the-spam-filter"></a><span data-ttu-id="b741b-112">利用郵件流程規則 (傳輸規則) 或垃圾郵件篩選器封鎖大宗郵件</span><span class="sxs-lookup"><span data-stu-id="b741b-112">Block bulk mail with mail flow rules (transport rules) or the spam filter</span></span>

<span data-ttu-id="b741b-p102">垃圾郵件主要是大宗郵件，例如新聞稿或促銷活動嗎？如果您[使用郵件流程規則來設定大量電子郵件的篩選](use-transport-rules-to-configure-bulk-email-filtering.md)，或在 Office 365 垃圾郵件篩選器的[進階垃圾郵件篩選 (ASF) 設定](advanced-spam-filtering-asf-options.md)中開啟 [大宗郵件]\*\*\*\* 設定，則可以自訂 Office 365 中的垃圾郵件篩選器。在 Exchange 系統管理中心，開始按一下 [保護]\*\*\*\* \> [內容篩選器]\*\*\*\*，然後按兩下您要調整的篩選原則。按一下 [垃圾郵件和大宗郵件動作]\*\*\*\*，來調整設定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b741b-p102">Is the spam primarily bulk mail, for example, newsletters or promotions? You can customize the spam filter in Office 365 if you [Use mail flow rules to configure bulk email filtering](use-transport-rules-to-configure-bulk-email-filtering.md) or turn on the **Bulk mail** setting in your spam filter's [Advanced Spam Filter (ASF) settings in Office 365](advanced-spam-filtering-asf-options.md). In the Exchange admin center, get started by clicking **Protection** \> **Content filter** and then double click the filter policy you want to adjust. Click **Spam and bulk mail actions** to adjust the settings, as shown here.</span></span>

![在 Exchange Online 設定大宗郵件篩選器](../../media/a45095c2-269d-45b8-a76c-999b5e78da68.png)

### <a name="block-email-spam-using-spam-filter-block-lists"></a><span data-ttu-id="b741b-118">使用垃圾郵件篩選器封鎖清單封鎖電子郵件垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="b741b-118">Block email spam using spam filter block lists</span></span>

<span data-ttu-id="b741b-p103">[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)，將寄件者地址新增至封鎖的寄件者清單，或將網域新增至垃圾郵件篩選器中的封鎖網域清單。電子郵件若來自垃圾郵件篩選器封鎖清單上的寄件者或網域，即會被標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="b741b-p103">[Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md) to add the sender address to the blocked sender list or domain to the blocked domain list in the spam filter. Emails from a sender or domain on a spam filter block list will marked as spam.</span></span>

## <a name="email-users-can-also-help-ensure-that-false-negative-and-email-spam-is-blocked-with-office-365-spam-filter"></a><span data-ttu-id="b741b-121">電子郵件使用者也可以使用 Office 365 垃圾郵件篩選器，來協助確定封鎖誤判和電子郵件垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="b741b-121">Email users can also help ensure that false negative and email spam is blocked with Office 365 spam filter</span></span>

<span data-ttu-id="b741b-p104">如果您告訴使用者將垃圾郵件寄件者地址新增至其封鎖的寄件者清單 (位於 [Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) 或 [Outlook 網頁版](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) 中)，它將有助於您的 Office 365 防止誤判和垃圾郵件的反垃圾郵件工作。在 Outlook 網頁版中，按一下 [設定]\*\*\*\* \> [選項]\*\*\*\* \> [封鎖或允許]\*\*\*\*，然後將地址新增至 [封鎖的寄件者]\*\*\*\* 清單，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b741b-p104">It will help your Office 365 anti-spam efforts to prevent false negatives and junk mail if you tell your users to add the spam sender address to their blocked sender list in [Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) or [Outlook on the web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d). In Outlook on the web, get started by clicking **Settings** \> **Options** \> **Block or allow**, and then adding the address to the **Blocked senders** list, as shown here.</span></span>

![封鎖 Outlook 網頁版中的寄件者](../../media/fdf51381-2527-4819-ac2a-5dff84d2a36d.png)

> [!NOTE]
> <span data-ttu-id="b741b-125">如需安全寄件者清單的詳細資訊，請參閱[在 Office 365 中建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b741b-125">For more detailed information about safe sender lists, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="eop-only-customers-set-up-directory-synchronization"></a><span data-ttu-id="b741b-126">只使用 EOP 的客戶：設定目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="b741b-126">EOP-only customers: Set up directory synchronization</span></span>

<span data-ttu-id="b741b-p105">如果您透過目錄同步處理將使用者設定與服務同步，以確保遵守您封鎖的寄件者，它將協助您避免誤判電子郵件垃圾郵件。如需詳細資訊，請參閱「管理 EOP 中的郵件使用者」中的「使用目錄同步處理來管理郵件使用者」。</span><span class="sxs-lookup"><span data-stu-id="b741b-p105">It will help you to avoid false negative email spam if you sync user settings with the service via directory synchronization to ensure that your blocked senders are respected. For more information, see "Use directory synchronization to manage mail users" in Manage mail users in EOP.</span></span>

## <a name="eop-only-customers-who-are-not-using-directory-synchronization"></a><span data-ttu-id="b741b-129">不使用目錄同步處理的 EOP 專屬客戶</span><span class="sxs-lookup"><span data-stu-id="b741b-129">EOP-only customers who are not using directory synchronization</span></span>

<span data-ttu-id="b741b-p106">EOP 服務的設計旨在接受使用者的安全和封鎖的寄件者，如果已與此服務共用資訊的話。如果您是使用 Outlook 的 EOP 客戶，但未將目錄同步處理設定為將您的使用者同步至 Office 365 ，則仍然可以使用封鎖的寄件者，停止將郵件傳遞到您使用者的收件匣。不過，您可能必須在下列情況中設定一些 Exchange 郵件流程規則：</span><span class="sxs-lookup"><span data-stu-id="b741b-p106">The EOP service is designed to honor the user's safe and blocked senders, if the information has been shared with the service. If you are an EOP customer using Outlook, but do not have Directory Synchronization configured to sync your users to Office 365, you can still stop messages from being delivered to your users' inbox using blocked senders. However, you may have to set up some Exchange mail flow rules in the following situations:</span></span>

- <span data-ttu-id="b741b-133">如果郵件透過 EOP 進行一般垃圾郵件篩選，然後傳遞至本機內部部署 Exchange Server，而且 EOP 將垃圾郵件判決指派為 SCL 1-4 (非垃圾郵件)，則您使用者的本機封鎖的寄件者清單將會覆寫 EOP 垃圾郵件篩選判決，並將它傳遞至他們的垃圾郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="b741b-133">If a message goes through regular spam filtering through EOP and then is delivered to a local on-premises Exchange server, and EOP assigns a spam verdict of SCL 1-4 (non-spam), then your users' local blocked senders list will override the EOP spam filter verdict and deliver it to their junk email folder.</span></span>

- <span data-ttu-id="b741b-p107">如果 Exchange 郵件流程規則將 EOP 中的郵件指派為 SCL-1，或由於 IP 位址或網域是在您的允許清單中而有此指派，則系統會使用連接器將 SCL 傳播至內部部署 Exchange Server。在此情況下，系統不會強制採用您使用者的封鎖的寄件者清單。若要變更此情況，您可以建立本機郵件流程規則，將 SCL 設為 0。這將導致 Outlook 強制採用您使用者的本機封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="b741b-p107">If a message in EOP is assigned SCL -1 by an Exchange mail flow rule or because the IP address or domain is in your allow list, the SCL is propagated to the on-premises Exchange server using connectors. In this case, your user's blocked senders list will not be enforced. To change this, you can create a local mail flow rule that sets the SCL to 0. This will cause Outlook to enforce your user's local blocked senders list.</span></span>

### <a name="to-set-up-a-mail-flow-rule-to-stop-messages-from-being-delivered-to-your-users-inbox-by-using-the-blocked-senders-list"></a><span data-ttu-id="b741b-138">如何使用封鎖寄件者清單來設定郵件流程規則，避免系統將郵件送至您使用者的收件匣</span><span class="sxs-lookup"><span data-stu-id="b741b-138">To set up a mail flow rule to stop messages from being delivered to your users' inbox by using the blocked senders list</span></span>

1. <span data-ttu-id="b741b-p108">在您的內部部署伺服器上開啟 Exchange 管理命令介面。若要了解如何在您的內部部署 Exchange 組織上開啟 Exchange 管理命令介面，請參閱[開啟 Exchange 管理命令介面](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)。</span><span class="sxs-lookup"><span data-stu-id="b741b-p108">Open the Exchange Management Shell on your on-premises server. To learn how to open the Shell in your on-premises Exchange organization, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell).</span></span>

2. <span data-ttu-id="b741b-141">執行下列命令，將內容篩選的垃圾郵件路由傳送至 [垃圾郵件] 資料夾，以便更新被標示為 SCL l-1 的每一封郵件上的 SCL：</span><span class="sxs-lookup"><span data-stu-id="b741b-141">Run the following command to route content-filtered spam messages to the Junk Email folder in order to update the SCL on every message that was marked with SCL -1:</span></span>

   ```powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SCL:-1" -SetSCL 0
   ```

   <span data-ttu-id="b741b-p109">因為在您的內部部署 Exchange Server 中，SCL 為 0，所以非垃圾郵件將會傳遞到您使用者的收件匣，但仍允許使用者的本機封鎖的寄件者清單將它們傳送到垃圾郵件。如果您使用的是 EOP 中的垃圾郵件隔離，則在您使用者的安全清單上的寄件者仍將有可能被識別為垃圾郵件，並傳送至隔離區。不過，如果您使用的是本機信箱中的 [垃圾郵件] 資料夾，這將允許傳遞到安全寄件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="b741b-p109">Because the SCL is 0 in your on-premises Exchange server, non-spam will be delivered to your users' inboxes but still allow for users' local blocked senders list to send them to junk email. If you are using spam quarantine in EOP, it is still possible that senders who are on your user's safe list will be identified as spam and sent to quarantine. If you are using the Junk Mail Folder in your local mailbox, however, this will allow delivery to the Inbox for safe senders.</span></span>

> [!WARNING]
> <span data-ttu-id="b741b-p110">如果您使用郵件流程規則，將 SCL 值變更為 0 (或 -1 以外的任何值)，則所有 Outlook 垃圾郵件選項將套用到郵件。這表示將接受封鎖和安全清單，同時也表示，沒有來自封鎖或安全清單之地址的郵件可能會被客戶端垃圾郵件篩選處理作業標示為垃圾郵件。如果您想要讓 Outlook 處理封鎖和安全清單，但不使用客戶端垃圾郵件篩選器，則您必須在 Outlook 垃圾郵件選項中將選項設為「不自動篩選」。「不自動篩選」是最新 Outlook 版本中的預設選項，但您應該確認此設定適當，以確保客戶端垃圾郵件篩選器不會套用至郵件。身為系統管理員，您可以遵循 [Outlook：停用垃圾郵件 UI 與篩選機制的原則設定](https://support.microsoft.com/kb/2180568) 中的指示，來強制停用 Outlook 垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="b741b-p110">If you use a mail flow rule to change the SCL value to 0 (or any value other than -1), then all of the Outlook junk mail options will apply to the message. This means that blocked and safe lists will be honored, but also means that messages that do not have addresses from the blocked or safe lists will potentially be marked as junk by the client side junk mail filter processing. If you want to have Outlook process the blocked and safe lists, but not use the client side junk mail filter, you must set the option to "No Automatic Filtering" in Outlook Junk Mail Options. "No Automatic Filtering" is the default option in the latest versions of Outlook, but you should confirm that the this setting is in place to ensure the client side junk mail filter is not applied to the messages. As an administrator, you can enforce disabling the Outlook Junk Email filtering by following the instructions in [Outlook: Policy setting to disable the Junk E-mail UI and filtering mechanism](https://support.microsoft.com/kb/2180568).</span></span>

## <a name="see-also"></a><span data-ttu-id="b741b-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b741b-150">See Also</span></span>

[<span data-ttu-id="b741b-151">Office 365 電子郵件的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="b741b-151">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
