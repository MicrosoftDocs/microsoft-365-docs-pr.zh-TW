---
title: 使用郵件流程規則來查看您的使用者報告給 Microsoft 哪些內容
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用郵件流程規則 (也稱為傳輸規則) 接收使用者向 Microsoft 報告的郵件副本。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40e87fec3bfd8ed4402713ca7ec45499bb50c68e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287602"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="a9b2e-103">使用郵件流程規則來查看您的使用者報告給 Microsoft 哪些內容</span><span class="sxs-lookup"><span data-stu-id="a9b2e-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a9b2e-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="a9b2e-104">**Applies to**</span></span>
- [<span data-ttu-id="a9b2e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a9b2e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a9b2e-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="a9b2e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a9b2e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9b2e-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="a9b2e-108">在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱時，使用者可以使用多種方式，將郵件報告給 Microsoft 進行分析，如 [報表訊息和檔案至 microsoft](report-junk-email-messages-to-microsoft.md)所述。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="a9b2e-109">您可以建立郵件流程規則 (也稱為傳輸規則) ，它會尋找使用者向 Microsoft 報告的郵件，而且您可以設定密件副本收件者接收這些報告郵件的副本。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-109">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="a9b2e-110">您可以在 Exchange 系統管理中心中建立郵件流程規則 (EAC) 並 PowerShell Exchange Online 中包含信箱的 Microsoft 365 組織 (Exchange Online PowerShell;沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-110">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a9b2e-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="a9b2e-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a9b2e-112">您必須先在 Exchange Online 或 Exchange Online Protection 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-112">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="a9b2e-113">具體說來，您需要「 **傳輸規則** 」角色，該角色會指派給「 **組織管理**」、「 **合規性管理** 」 (全域系統管理員) ，並依預設 **記錄管理** 角色群組。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-113">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="a9b2e-114">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="a9b2e-114">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="a9b2e-115">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="a9b2e-115">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="a9b2e-116">獨立版 EOP 中的權限</span><span class="sxs-lookup"><span data-stu-id="a9b2e-116">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="a9b2e-117">使用 EAC 修改角色群組中的成員清單</span><span class="sxs-lookup"><span data-stu-id="a9b2e-117">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="a9b2e-118">若要在 Exchange Online 中開啟 EAC，請參閱 exchange [online 中的 exchange admin center](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-118">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="a9b2e-119">若要在獨立 EOP 中開啟 EAC，請參閱 [Exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-119">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="a9b2e-120">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a9b2e-121">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a9b2e-122">如需 Exchange Online 和獨立 EOP 中郵件流程規則的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="a9b2e-122">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="a9b2e-123">Exchange Online 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="a9b2e-123">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="a9b2e-124">Exchange Online 中的郵件流程規則條件和例外狀況 (述詞)</span><span class="sxs-lookup"><span data-stu-id="a9b2e-124">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="a9b2e-125">Exchange Online 中的郵件流程規則動作</span><span class="sxs-lookup"><span data-stu-id="a9b2e-125">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="a9b2e-126">使用 EAC 來建立郵件流程規則，以接收報告訊息的副本</span><span class="sxs-lookup"><span data-stu-id="a9b2e-126">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="a9b2e-127">在 EAC 中，移至 [郵件流程] \> [規則]。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="a9b2e-128">按一下 [ **新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後選取 [ **建立新的規則**]。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="a9b2e-129">在開啟的 [ **新增規則** ] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a9b2e-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="a9b2e-130">**名稱**：輸入規則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-130">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="a9b2e-131">例如，向 Microsoft 報告的 Bcc 郵件。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-131">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="a9b2e-132">按一下 [ **更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-132">Click **More Options**.</span></span>

   - <span data-ttu-id="a9b2e-133">在下列情況下套用 **此規則**：選取 **收件** 者 \> **位址包含下列任何文字**：在出現的 [**指定字詞或片語**] 對話方塊中，輸入下列其中一個值，按一下 [**新增**] ![ 圖示 ](../../media/ITPro-EAC-AddIcon.png) ，然後重複，直到您輸入所有值為止。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-133">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="a9b2e-134">若要編輯專案，請選取它，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="a9b2e-135">若要移除專案，請選取它，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="a9b2e-136">完成後，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-136">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="a9b2e-137">**請執行下列** 動作：選取 [將收件者 **新增** \> **至 Bcc**] 方塊。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-137">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="a9b2e-138">在出現的對話方塊中，尋找並選取您要新增的收件者。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-138">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="a9b2e-139">完成後，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-139">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="a9b2e-140">您可以進行其他選擇來審核規則、測試規則、在特定時間週期內啟動規則，以及其他設定。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-140">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="a9b2e-141">建議您先測試規則，再加以強制執行。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-141">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="a9b2e-142">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-142">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="a9b2e-143">使用 PowerShell 建立郵件流程規則，以接收報告訊息的副本</span><span class="sxs-lookup"><span data-stu-id="a9b2e-143">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="a9b2e-144">此範例會建立名為「Bcc 郵件」的新郵件流程規則，它會向 Microsoft 報告出使用本文所述方法向 Microsoft 報告的電子郵件訊息，並將使用者 laura@contoso.com 及 julia@contoso.com 新增為 Bcc 收件者。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-144">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="a9b2e-145">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-145">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a9b2e-146">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="a9b2e-146">How do you know this worked?</span></span>

<span data-ttu-id="a9b2e-147">若要驗證您是否已設定郵件流程規則以接收報告的郵件副本，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="a9b2e-147">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="a9b2e-148">在 EAC 中，移至 [ **郵件流程** \> **規則**] \> 選取規則 \> ，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) ，然後驗證設定。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-148">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="a9b2e-149">在 PowerShell 中，執行下列命令來確認設定：</span><span class="sxs-lookup"><span data-stu-id="a9b2e-149">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="a9b2e-150">傳送測試郵件至其中一個報告電子郵件地址並確認結果。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-150">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
