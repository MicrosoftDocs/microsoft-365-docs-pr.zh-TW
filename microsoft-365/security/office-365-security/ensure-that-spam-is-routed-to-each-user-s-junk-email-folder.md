---
title: 將 EOP 設定為混合式環境中的垃圾郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何將垃圾郵件路由傳送至 Exchange Online Protection 混合式環境中的使用者垃圾郵件資料夾。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 76003f18009ebf9159f01d916cdaf38b50a213d1
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350336"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="85e83-103">設定獨立 EOP，將垃圾郵件傳遞至混合式環境中的 [垃圾郵件] 資料夾</span><span class="sxs-lookup"><span data-stu-id="85e83-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="85e83-104">本主題僅適用于混合式環境中的獨立 EOP 客戶。</span><span class="sxs-lookup"><span data-stu-id="85e83-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="85e83-105">本主題不適用於含 Exchange Online 信箱的 Microsoft 365 客戶。</span><span class="sxs-lookup"><span data-stu-id="85e83-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="85e83-106">如果您是獨立的 Exchange Online Protection (EOP) 客戶在混合式環境中，您必須設定內部部署 Exchange 組織，以辨識及翻譯 EOP 的垃圾郵件篩選 verdicts，讓內部部署信箱中的垃圾郵件規則可以將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="85e83-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="85e83-107">具體說來，您必須建立郵件流程規則 (也稱為傳輸規則) 內部部署 Exchange 組織中的條件，該組織會找到具有下列任何 EOP 反垃圾郵件標頭和值的郵件，並將這些郵件的垃圾郵件信賴等級 (SCL) 的動作設定為6：</span><span class="sxs-lookup"><span data-stu-id="85e83-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="85e83-108">`X-Forefront-Antispam-Report: SFV:SPM` (以垃圾郵件篩選標示為垃圾郵件的郵件) </span><span class="sxs-lookup"><span data-stu-id="85e83-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="85e83-109">`X-Forefront-Antispam-Report: SFV:SKS` 透過垃圾郵件過濾) 之前 EOP 中的郵件流程規則標示為垃圾郵件的郵件 (</span><span class="sxs-lookup"><span data-stu-id="85e83-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="85e83-110">`X-Forefront-Antispam-Report: SFV:SKB` 因為寄件者的電子郵件地址或電子郵件網域位於 EOP 的封鎖的寄件者清單或封鎖的網域清單，所以透過垃圾郵件篩選標示為垃圾郵件的郵件 () </span><span class="sxs-lookup"><span data-stu-id="85e83-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="85e83-111">如需這些標頭值的詳細資訊，請參閱 [反垃圾郵件郵件頭](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="85e83-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="85e83-112">本主題說明如何建立這些郵件流程規則 Exchange 系統管理中心 (EAC) 和內部部署 Exchange 組織中的 Exchange 管理命令介面 (Exchange PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="85e83-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="85e83-113">您可以在 EOP 中設定反垃圾郵件原則，以隔離 EOP 中的垃圾郵件，而不是將郵件傳遞至內部部署使用者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="85e83-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="85e83-114">如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="85e83-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="85e83-115">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="85e83-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="85e83-116">您必須在內部部署 Exchange 環境中指派許可權，才能執行這些程式。</span><span class="sxs-lookup"><span data-stu-id="85e83-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="85e83-117">具體而言，您必須被指派 **傳輸規則** 角色，預設會指派給 **組織管理**、 **規範管理**及 **記錄管理** 角色。</span><span class="sxs-lookup"><span data-stu-id="85e83-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="85e83-118">如需詳細資訊，請參閱 [將成員新增至角色群組](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)。</span><span class="sxs-lookup"><span data-stu-id="85e83-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="85e83-119">當郵件傳遞至內部部署 Exchange 組織中的 [垃圾郵件] 資料夾時，由下列設定的組合來控制：</span><span class="sxs-lookup"><span data-stu-id="85e83-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="85e83-120">Exchange 管理命令介面中[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) Cmdlet 上的_SCLJunkThreshold_參數值。</span><span class="sxs-lookup"><span data-stu-id="85e83-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="85e83-121">預設值為4，表示 SCL 上限為5或以上，則應該會將郵件傳遞至使用者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="85e83-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="85e83-122">Exchange 管理命令介面中[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) Cmdlet 上的_SCLJunkThreshold_參數值。</span><span class="sxs-lookup"><span data-stu-id="85e83-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="85e83-123">預設值為空白 ($null) ，這表示使用組織設定。</span><span class="sxs-lookup"><span data-stu-id="85e83-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="85e83-124">如需詳細資訊，請參閱 [Exchange 垃圾郵件信賴等級 (SCL) 閾值](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)。</span><span class="sxs-lookup"><span data-stu-id="85e83-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="85e83-125">是否已在信箱上啟用垃圾郵件規則 (在 Exchange 管理命令介面) 的[Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)指令程式中 $true _enabled_參數值是。</span><span class="sxs-lookup"><span data-stu-id="85e83-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="85e83-126">這是垃圾郵件規則，它會在傳送後實際將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="85e83-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="85e83-127">依預設，會在信箱上啟用垃圾郵件規則。</span><span class="sxs-lookup"><span data-stu-id="85e83-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="85e83-128">如需詳細資訊，請參閱 [設定信箱上的 Exchange 反垃圾郵件設定](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)。</span><span class="sxs-lookup"><span data-stu-id="85e83-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="85e83-129">若要在 Exchange 伺服器上開啟 EAC，請參閱 exchange [server 中的 exchange 系統管理中心](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="85e83-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="85e83-130">若要開啟 Exchange 管理命令介面，請參閱 [open The Exchange Management shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)。</span><span class="sxs-lookup"><span data-stu-id="85e83-130">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="85e83-131">如需內部部署 Exchange 中郵件流程規則的相關資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="85e83-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="85e83-132">Exchange Server 中的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="85e83-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="85e83-133">Exchange Server 中的郵件流程規則條件和例外狀況 (述詞)</span><span class="sxs-lookup"><span data-stu-id="85e83-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="85e83-134">Exchange Server 中的郵件流程規則動作</span><span class="sxs-lookup"><span data-stu-id="85e83-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="85e83-135">使用 EAC 來建立郵件流程規則，以設定 EOP 垃圾郵件訊息的 SCL</span><span class="sxs-lookup"><span data-stu-id="85e83-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="85e83-136">在 EAC 中，移至 [郵件流程]\*\*\*\* \> [規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85e83-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="85e83-137">按一下 [ **新增**新增 ![ 圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後在出現的下拉式清單中選取 [ **建立新的規則** ]。</span><span class="sxs-lookup"><span data-stu-id="85e83-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="85e83-138">在開啟的 [ **新增規則** ] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="85e83-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="85e83-139">**名稱**：輸入規則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="85e83-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="85e83-140">例如：</span><span class="sxs-lookup"><span data-stu-id="85e83-140">For example:</span></span>

     - <span data-ttu-id="85e83-141">EOP SFV： SPM 至 SCL 6</span><span class="sxs-lookup"><span data-stu-id="85e83-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="85e83-142">EOP SFV： SKS 至 SCL 6</span><span class="sxs-lookup"><span data-stu-id="85e83-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="85e83-143">EOP SFV:SKB 至 SCL 6</span><span class="sxs-lookup"><span data-stu-id="85e83-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="85e83-144">按一下 [ **更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="85e83-144">Click **More Options**.</span></span>

   - <span data-ttu-id="85e83-145">**在下列情況中套用此規則**： Select **message 標頭** \> **包含任何這些字**。</span><span class="sxs-lookup"><span data-stu-id="85e83-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="85e83-146">在 [ **輸入文字標頭包含** 會出現的輸入文字句子] 中，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="85e83-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="85e83-147">按一下 [ **輸入文字**]。</span><span class="sxs-lookup"><span data-stu-id="85e83-147">Click **Enter text**.</span></span> <span data-ttu-id="85e83-148">在出現的 [ **指定標頭名稱** ] 對話方塊中，輸入 **X-Forefront-Antispam-Report** ，然後按一下 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="85e83-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="85e83-149">按一下 [  **輸入文字**]。</span><span class="sxs-lookup"><span data-stu-id="85e83-149">Click  **Enter words**.</span></span> <span data-ttu-id="85e83-150">在出現的 [ **指定字詞或片語** ] 對話方塊中，輸入下列其中一個 EOP 的垃圾郵件標頭值 (**SFV： SPM**、 **SFV： SKS**或 **SFV:SKB**) ]，按一下 [ **新增** ![ 新增圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="85e83-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="85e83-151">**請執行下列**動作：選取 **[修改郵件**內容] \> 。 \*\* (SCL) 設定垃圾郵件信賴等級 \*\*。</span><span class="sxs-lookup"><span data-stu-id="85e83-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="85e83-152">在出現的 [ **指定 SCL** ] 對話方塊中，選取 [ **6** ] (預設值為 **5**) 。</span><span class="sxs-lookup"><span data-stu-id="85e83-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="85e83-153">完成後，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85e83-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="85e83-154">針對其餘 EOP 垃圾郵件判定值 (**SFV： SPM**、 **SFV： SKS**或 **SFV:SKB**) 重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="85e83-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="85e83-155">使用 Exchange 管理命令介面來建立郵件流程規則，以設定 EOP 垃圾郵件訊息的 SCL</span><span class="sxs-lookup"><span data-stu-id="85e83-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="85e83-156">使用下列語法來建立三個郵件流程規則：</span><span class="sxs-lookup"><span data-stu-id="85e83-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="85e83-157">例如：</span><span class="sxs-lookup"><span data-stu-id="85e83-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="85e83-158">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="85e83-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="85e83-159">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="85e83-159">How do you know this worked?</span></span>

<span data-ttu-id="85e83-160">若要確認您是否已成功將獨立 EOP 設定為將垃圾郵件傳遞至混合式環境中的 [垃圾郵件] 資料夾，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="85e83-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="85e83-161">在 EAC 中，移至 [ **郵件流程** \> **規則**]，選取規則，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-EditIcon.png) 以驗證設定。</span><span class="sxs-lookup"><span data-stu-id="85e83-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="85e83-162">在 Exchange 管理命令介面中， \<RuleName\> 以郵件流程規則的名稱取代，並 rul 下列命令來確認設定：</span><span class="sxs-lookup"><span data-stu-id="85e83-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="85e83-163">在 **沒有掃描輸出郵件的**外部電子郵件系統中，請傳送未經授權大量電子郵件 (GTUBE 的一般測試，將) 郵件傳送至受影響的收件者，並確認郵件已傳遞至其 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="85e83-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="85e83-164">GTUBE 訊息類似於歐洲反電腦病毒協會 (EICAR) 用於測試惡意程式碼設定的文字檔。</span><span class="sxs-lookup"><span data-stu-id="85e83-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="85e83-165">若要傳送 GTUBE 訊息，請在電子郵件的本文中包含下列文字，但不含任何空格或分行符號：</span><span class="sxs-lookup"><span data-stu-id="85e83-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
