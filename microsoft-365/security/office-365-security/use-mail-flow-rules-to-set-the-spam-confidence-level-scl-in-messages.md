---
title: 使用郵件流程規則到郵件中的 SCL
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 瞭解如何建立郵件流程規則（傳輸規則）來識別郵件，以及在 Exchange Online Protection 中設定郵件的垃圾郵件信賴等級（SCL）。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 223e676579c99eca7db641146d3a1b6bd22f9ca2
ms.sourcegitcommit: 1f3101326e8a54b9bda4ba0324eae00fafcf5e7b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44405116"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="d3f78-103">使用郵件流程規則來設定 EOP 中郵件的垃圾郵件信賴等級（SCL）</span><span class="sxs-lookup"><span data-stu-id="d3f78-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

<span data-ttu-id="d3f78-104">在未使用 Exchange online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中使用信箱的 Microsoft 365 組織中，EOP 會使用反垃圾郵件原則（也稱為垃圾郵件篩選原則或內容篩選原則）來掃描輸入郵件中的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="d3f78-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="d3f78-105">如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d3f78-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="d3f78-106">如果您想要將特定郵件標記為垃圾郵件，然後再透過垃圾郵件篩選進行掃描，或將郵件標示為略過垃圾郵件篩選，您可以建立郵件流程規則（也稱為傳輸規則）來識別郵件，並設定垃圾郵件信賴等級（SCL）。</span><span class="sxs-lookup"><span data-stu-id="d3f78-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="d3f78-107">如需有關 SCL 的詳細資訊，請參閱[EOP 中的垃圾郵件信賴等級（SCL）](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="d3f78-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d3f78-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="d3f78-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d3f78-109">您必須先在 Exchange Online 中指派許可權，才能執行這些程式。</span><span class="sxs-lookup"><span data-stu-id="d3f78-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="d3f78-110">具體而言，您必須被指派**傳輸規則**角色，預設會指派給**組織管理**、**規範管理**及**記錄管理**角色。</span><span class="sxs-lookup"><span data-stu-id="d3f78-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="d3f78-111">如需詳細資訊，請參閱[管理 Exchange Online 中的角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="d3f78-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="d3f78-112">若要在 Exchange Online 中開啟 EAC，請參閱 exchange [online 中的 exchange admin center](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="d3f78-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="d3f78-113">如需 Exchange Online 中郵件流程規則的相關資訊，請參閱[郵件流程規則（傳輸規則） Exchange online 中的郵件流程規則（傳輸規則）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="d3f78-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="d3f78-114">使用 EAC 來建立郵件流程規則，以設定郵件的 SCL</span><span class="sxs-lookup"><span data-stu-id="d3f78-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="d3f78-115">在 EAC 中，移至 [郵件流程]\*\*\*\* \> [規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d3f78-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="d3f78-116">按一下 [**新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後選取 [**建立新的規則**]。</span><span class="sxs-lookup"><span data-stu-id="d3f78-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="d3f78-117">在開啟的 [**新增規則**] 頁面中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="d3f78-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d3f78-118">**名稱**：輸入規則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="d3f78-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="d3f78-119">按一下 [**更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="d3f78-119">Click **More Options**.</span></span>

   - <span data-ttu-id="d3f78-120">在下列情況中套用**此規則**：選取一或多個條件來識別郵件。</span><span class="sxs-lookup"><span data-stu-id="d3f78-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="d3f78-121">如需詳細資訊，請參閱[在 Exchange Online 中的郵件流程規則條件和例外狀況（謂語）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。</span><span class="sxs-lookup"><span data-stu-id="d3f78-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="d3f78-122">**請執行下列**動作：選取 [**修改郵件屬性**] \> **設定垃圾郵件信賴等級（SCL）**。</span><span class="sxs-lookup"><span data-stu-id="d3f78-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="d3f78-123">在出現的 [**指定 SCL** ] 對話方塊中，設定下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="d3f78-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="d3f78-124">**略過垃圾郵件篩選**：郵件會略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="d3f78-124">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="d3f78-125">請務必小心允許郵件略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="d3f78-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="d3f78-126">攻擊者可以利用此弱點，將網路釣魚和其他惡意郵件傳送至您的組織。</span><span class="sxs-lookup"><span data-stu-id="d3f78-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="d3f78-127">郵件流程規則需要的不僅僅是寄件者的電子郵件地址或網域。</span><span class="sxs-lookup"><span data-stu-id="d3f78-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="d3f78-128">如需詳細資訊，請參閱[在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="d3f78-128">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="d3f78-129">**0 至 4**：透過垃圾郵件篩選傳送郵件以進行其他處理。</span><span class="sxs-lookup"><span data-stu-id="d3f78-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="d3f78-130">**5 或 6**：郵件被標示為**垃圾**郵件。</span><span class="sxs-lookup"><span data-stu-id="d3f78-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="d3f78-131">您為反垃圾郵件原則中的**垃圾**郵件篩選 verdicts 設定的動作會套用至郵件（預設值為 [**將郵件移至垃圾郵件資料夾**]）。</span><span class="sxs-lookup"><span data-stu-id="d3f78-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="d3f78-132">**7 至 9**：郵件標示為**高信賴的垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="d3f78-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="d3f78-133">您為反垃圾郵件原則中已設定**高信賴度垃圾郵件**篩選 verdicts 的動作會套用至郵件（預設值為 [**將郵件移至垃圾郵件資料夾**]）。</span><span class="sxs-lookup"><span data-stu-id="d3f78-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="d3f78-134">指定規則所需的任何其他屬性。</span><span class="sxs-lookup"><span data-stu-id="d3f78-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="d3f78-135">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d3f78-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d3f78-136">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="d3f78-136">How do you know this worked?</span></span>

<span data-ttu-id="d3f78-137">若要驗證此程式是否正常運作，請將電子郵件訊息傳送給組織內部的人員，並確認對郵件執行的動作如期。</span><span class="sxs-lookup"><span data-stu-id="d3f78-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="d3f78-138">例如，如果您**將垃圾郵件信賴等級（SCL）設定**為**略過垃圾郵件篩選**，則郵件應該會傳送至指定收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="d3f78-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="d3f78-139">不過，如果您**將垃圾郵件信賴等級（SCL）設定**為**9**，且適用的反垃圾郵件原則的**高可信度垃圾郵件**動作是將郵件移至 [垃圾郵件] 資料夾，則郵件應該會傳送至指定收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d3f78-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
