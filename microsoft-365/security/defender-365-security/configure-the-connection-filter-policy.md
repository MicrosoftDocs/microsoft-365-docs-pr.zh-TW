---
title: 設定預設連線篩選原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何在 Exchange Online Protection (EOP) 中設定連線篩選，以允許或封鎖電子郵件伺服器的電子郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2b940aadb4ff5f2c4676ac2411ea3e95a25c7855
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058943"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="1aa1f-103">設定連線篩選</span><span class="sxs-lookup"><span data-stu-id="1aa1f-103">Configure connection filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1aa1f-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="1aa1f-104">**Applies to**</span></span>
- [<span data-ttu-id="1aa1f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1aa1f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1aa1f-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="1aa1f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1aa1f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1aa1f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="1aa1f-108">如果您是使用 Exchange Online 中的信箱或獨立 Exchange Online Protection 的 Microsoft 365 客戶 (EOP) 客戶沒有 Exchange Online 信箱，您可以在 EOP 中使用連線篩選 (特別是，「預設連線篩選原則」) 可透過 IP 位址識別正確或不良的來源電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-108">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="1aa1f-109">預設連線篩選原則的主要元件包括：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-109">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="1aa1f-110">**IP 允許清單**：針對來自您透過 ip 位址或 ip 位址範圍所指定之來源電子郵件伺服器的所有傳入郵件，略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-110">**IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="1aa1f-111">針對來自這些來源之郵件的垃圾郵件篩選可能仍會發生的情況，請參閱本文稍後的 [篩選來自 IP 允許清單來源的郵件](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-111">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this article.</span></span> <span data-ttu-id="1aa1f-112">如需 IP 允許清單應如何符合整體安全寄件者策略的詳細資訊，請參閱 [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-112">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="1aa1f-113">**IP 封鎖清單**：從您透過 ip 位址或 ip 位址範圍所指定之來源電子郵件伺服器封鎖所有傳入的郵件。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-113">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="1aa1f-114">內送郵件會遭到拒絕，不會標示為垃圾郵件，也不會發生其他篩選。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-114">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs.</span></span> <span data-ttu-id="1aa1f-115">如需 IP 封鎖清單應如何符合整體封鎖的寄件者策略的詳細資訊，請參閱 [在 EOP 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-115">For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="1aa1f-116">**安全清單**： *安全清單* 是 Microsoft datacenter 中的動態允許清單，不需要客戶設定。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-116">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="1aa1f-117">Microsoft 會識別這些信任的電子郵件來源，以訂閱各種協力廠商清單。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-117">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="1aa1f-118">啟用或停用 [安全清單] 的使用。您無法在 [安全清單] 上設定來源電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-118">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="1aa1f-119">在 [安全清單] 上的電子郵件伺服器上，會略過傳入郵件的垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-119">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="1aa1f-120">本主題說明如何使用 Exchange Online 中的信箱，在安全性 & 合規性中心或 PowerShell (Exchange Online 365 PowerShell 中設定預設連線篩選原則;沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-120">This topic describes how to configure the default connection filter policy in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="1aa1f-121">如需 EOP 如何使用連線篩選的詳細資訊，請參閱您組織的整體反垃圾郵件設定的一部分，請參閱 [反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-121">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1aa1f-122">IP 允許清單、安全清單和 IP 封鎖清單是整體策略的一部分，可允許或封鎖您組織中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-122">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="1aa1f-123">如需詳細資訊，請參閱 [建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md) 及 [建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-123">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1aa1f-124">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="1aa1f-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1aa1f-125">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1aa1f-126">若要直接移至 [反垃圾郵件設定] 頁面，請使用 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-126">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="1aa1f-127">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-127">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1aa1f-128">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-128">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1aa1f-129">您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-129">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="1aa1f-130">若要修改預設連線篩選原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-130">To modify the default connection filter policy, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="1aa1f-131">若要對預設連線篩選原則進行唯讀存取，您必須是 **全域讀取器** 或 **安全性讀取** 器角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-131">For read-only access to the default connection filter policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="1aa1f-132">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-132">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="1aa1f-133">**附註**：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-133">**Notes**:</span></span>

  - <span data-ttu-id="1aa1f-134">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-134">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1aa1f-135">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-135">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="1aa1f-136">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-136">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="1aa1f-137">若要尋找電子郵件伺服器的來源 IP 位址 (您要允許或封鎖的寄件者) ，您可以檢查郵件頭中的 [連接 IP (**CIP**) 標頭欄位。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-137">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="1aa1f-138">若要在不同的電子郵件客戶程式中查看郵件頭，請參閱在 [Outlook 中查看網際網路郵件頭](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-138">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="1aa1f-139">IP 允許清單優先于 IP 封鎖清單 (兩個清單上的位址不會遭到封鎖) 。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-139">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="1aa1f-140">IP 允許清單和 IP 封鎖清單都支援最多1273個專案，其中一個專案是單一 IP 位址、IP 位址範圍或無類別網域間路由 (CIDR) IP。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-140">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="1aa1f-141">使用安全性 & 規範中心來修改預設連線篩選原則</span><span class="sxs-lookup"><span data-stu-id="1aa1f-141">Use the Security & Compliance Center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="1aa1f-142">在安全性 & 合規性中心，然後移至 **威脅管理** \> **原則** \> **Anti-Spam**。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-142">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="1aa1f-143">在 [**反垃圾郵件設定**] 頁面上，按一下 [展開圖示]，然後按一下 [編輯原則]，展開 [連線 **篩選原則**] ![ ](../../media/scc-expand-icon.png) 。 </span><span class="sxs-lookup"><span data-stu-id="1aa1f-143">On the **Anti-spam settings** page, expand **Connection filter policy** by clicking ![Expand icon](../../media/scc-expand-icon.png), and then click **Edit policy**.</span></span>

3. <span data-ttu-id="1aa1f-144">在出現的 **預設** 浮出視窗中，設定下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-144">In the **Default** flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="1aa1f-145">**描述**：輸入選用的描述文字。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-145">**Description**: Enter optional descriptive text.</span></span>

   - <span data-ttu-id="1aa1f-146">**IP 允許清單**：按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-146">**IP Allow List**: Click **Edit**.</span></span> <span data-ttu-id="1aa1f-147">在出現的 [ **IP 允許] 清單** 快顯視窗中，使用下列語法，在 [ **位址] 或 [位址範圍** ] 方塊中輸入 IPV4 位址：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-147">In the **IP Allow List** flyout that appears, enter an IPV4 address in the **Address or address range** box using the following syntax:</span></span>

     - <span data-ttu-id="1aa1f-148">單一 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-148">Single IP: For example, 192.168.1.1.</span></span>

     - <span data-ttu-id="1aa1f-149">IP 範圍：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-149">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

     - <span data-ttu-id="1aa1f-150">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-150">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="1aa1f-151">有效的網路遮罩值為/24 到/32。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-151">Valid network mask values are /24 through /32.</span></span> <span data-ttu-id="1aa1f-152">若要略過 CIDR IP 遮罩值的垃圾郵件篩選/1 到/23，請參閱本文稍後的 [可用範圍區段之外的 CIDR ip 的 [略過垃圾郵件篩選](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) ]。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-152">To skip spam filtering for CIDR IP mask values /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this article.</span></span>

     <span data-ttu-id="1aa1f-153">若要新增 IP 位址或位址範圍，請按一下 [ **新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-153">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1aa1f-154">若要移除專案，請選取 [ **允許的 IP 位址** ] 中的專案，然後按一下 [ **移除**] ![ ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-154">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="1aa1f-155">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-155">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="1aa1f-156">**IP 封鎖清單**：按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-156">**IP Block List**: Click **Edit**.</span></span> <span data-ttu-id="1aa1f-157">在出現的 [ **Ip 封鎖**] 快顯視窗中，在 [ **ip 允許清單**] 設定中先前所述的 [**位址] 或 [位址範圍**] 方塊中輸入單一 IP、ip 範圍或 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-157">In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.</span></span>

     <span data-ttu-id="1aa1f-158">若要新增 IP 位址或位址範圍，請按一下 [ **新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-158">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1aa1f-159">若要移除專案，請選取 [ **封鎖的 IP 位址** ] 中的專案，然後按一下 [ **移除**] ![ ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-159">To remove an entry, select the entry in **Blocked IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="1aa1f-160">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-160">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="1aa1f-161">**開啟安全清單**：啟用或停用安全清單的使用，以找出將會略過垃圾郵件篩選的已知的良好寄件者。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-161">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span>

4. <span data-ttu-id="1aa1f-162">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-162">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="1aa1f-163">使用安全性 & 規範中心來查看預設連線篩選原則</span><span class="sxs-lookup"><span data-stu-id="1aa1f-163">Use the Security & Compliance Center to view the default connection filter policy</span></span>

1. <span data-ttu-id="1aa1f-164">在安全性 & 合規性中心，然後移至 **威脅管理** \> **原則** \> **Anti-Spam**。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-164">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="1aa1f-165">在 [ **反垃圾郵件設定** ] 頁面上，按一下名為 **Connection filter policy** 之預設原則旁的下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-165">On the **Anti-spam settings** page, click the drop down next to the default policy named **Connection filter policy**.</span></span>

3. <span data-ttu-id="1aa1f-166">原則設定會顯示在開啟的下拉式功能表中。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-166">The policy settings are displayed in the drop down that opens.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="1aa1f-167">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 修改預設連線篩選原則</span><span class="sxs-lookup"><span data-stu-id="1aa1f-167">Use Exchange Online PowerShell or standalone EOP PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="1aa1f-168">使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-168">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="1aa1f-169">**附註**：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-169">**Notes**:</span></span>

- <span data-ttu-id="1aa1f-170">有效的 IP 位址或位址範圍值包括：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-170">Valid IP address or address range values are:</span></span>

  - <span data-ttu-id="1aa1f-171">單一 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-171">Single IP: For example, 192.168.1.1.</span></span>

  - <span data-ttu-id="1aa1f-172">IP 範圍：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-172">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

  - <span data-ttu-id="1aa1f-173">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-173">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="1aa1f-174">有效的網路遮罩值為/24 到/32。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-174">Valid network mask values are /24 through /32.</span></span>

- <span data-ttu-id="1aa1f-175">若要使用您指定的值 *覆寫* 任何現有的專案，請使用下列語法： `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-175">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>

- <span data-ttu-id="1aa1f-176">若要 *新增或移除* IP 位址或位址範圍，而不影響其他現有的專案，請使用下列語法： `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-176">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>

- <span data-ttu-id="1aa1f-177">若要清空 IP 允許清單或 IP 封鎖清單，請使用值 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-177">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="1aa1f-178">這個範例會設定 IP 允許清單和 IP 封鎖清單，其中包含指定的 IP 位址和位址範圍。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-178">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="1aa1f-179">本範例會從 IP 允許清單中新增及移除指定的 IP 位址和位址範圍。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-179">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="1aa1f-180">如需詳細的語法及參數資訊，請參閱 [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-180">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1aa1f-181">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="1aa1f-181">How do you know this worked?</span></span>

<span data-ttu-id="1aa1f-182">若要確認您是否已成功修改預設連線篩選原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-182">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="1aa1f-183">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> ] **Anti-Spam** \> 按一下 [連線篩選原則] 旁邊的下拉式清單， ([ **always ON**) ]，然後驗證設定。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-183">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-Spam** \> click the drop down next to **Connection filter policy (always ON**), and verify the settings.</span></span>

- <span data-ttu-id="1aa1f-184">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，執行下列命令並確認設定：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-184">In Exchange Online PowerShell or standalone EOP PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="1aa1f-185">從 IP 允許清單中的專案傳送測試郵件。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-185">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="1aa1f-186">IP 允許清單的其他考慮</span><span class="sxs-lookup"><span data-stu-id="1aa1f-186">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="1aa1f-187">下列各節會指出當您設定 IP 允許清單時，需要瞭解的其他專案。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-187">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="1aa1f-188">略過可用範圍外的 CIDR IP 的垃圾郵件篩選</span><span class="sxs-lookup"><span data-stu-id="1aa1f-188">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="1aa1f-189">如本文稍早所述，您只能在 IP 允許清單中使用具有 network mask/24 to/32 的 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-189">As described earlier in this article, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="1aa1f-190">若要在/1 到/23 範圍內略過來自來源電子郵件伺服器的郵件篩選，您必須使用 Exchange 郵件流程規則 (也稱為 transport rules) 。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-190">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="1aa1f-191">不過，如果可能的話，建議您不要這麼做，因為在任何 Microsoft 的專屬或協力廠商封鎖清單中，如果有/1 to/23 CIDR IP 範圍的 IP 位址會出現，則郵件會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-191">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="1aa1f-192">現在，您已完全瞭解潛在問題，您可以使用下列)  (設定來建立郵件流程規則，以確保這些 IP 位址的郵件會略過垃圾郵件篩選：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-192">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="1aa1f-193">規則條件： **如果** \> **寄件者** 的 \> **IP 位址在任何這些範圍中或完全相符**，則套用此規則 \> (輸入具有 a/1 to/23 網路遮罩的 CIDR IP) 。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-193">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>

- <span data-ttu-id="1aa1f-194">規則動作：**修改郵件屬性** \> **設定垃圾郵件信賴等級 (SCL)** \> **略過垃圾郵件篩選**。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-194">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="1aa1f-195">您可以審核規則、測試規則、在特定時間期間啟動規則，以及進行其他選擇。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-195">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="1aa1f-196">施行規則之前，建議先測試規則一段時間。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-196">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="1aa1f-197">如需詳細資訊，請參閱 [在 Exchange Online 中管理郵件流程規則](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-197">For more information, see [Manage mail flow rules in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="1aa1f-198">略過來自相同來源之選擇性電子郵件網域的垃圾郵件篩選</span><span class="sxs-lookup"><span data-stu-id="1aa1f-198">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="1aa1f-199">一般來說，將 IP 位址或位址範圍新增至 IP 允許清單表示您信任來自該電子郵件來源的所有傳入郵件。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-199">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="1aa1f-200">不過，如果該來源從多個網域傳送電子郵件，而您想要略過某些網域的垃圾郵件篩選功能，則該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="1aa1f-200">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="1aa1f-201">您無法只使用 IP 允許清單來執行這項作業，但是您可以搭配郵件流程規則使用 [IP 允許] 清單。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-201">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="1aa1f-202">例如，來源電子郵件伺服器192.168.1.25 會從網域 contoso.com、fabrikam.com 和 tailspintoys.com 傳送電子郵件，但您只想要對來自 fabrikam.com 中寄件者的郵件略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-202">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="1aa1f-203">若要這麼做，請使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-203">To do this, use the following steps:</span></span>

1. <span data-ttu-id="1aa1f-204">將192.168.1.25 新增至 IP 允許清單。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-204">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="1aa1f-205">使用下列設定來設定郵件流程規則 (至少) ：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-205">Configure a mail flow rule with the following settings (at a minimum):</span></span>

   - <span data-ttu-id="1aa1f-206">規則條件： **如果** \> **寄件者** \> **IP 位址位於上述任何範圍中，或完全符合** 192.168.1.25，則會套用此規則 \> 。) 中您新增至 ip 允許清單的 ip 位址或位址範圍 (相同。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-206">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>

   - <span data-ttu-id="1aa1f-207">規則動作： **修改郵件屬性** \> **設定垃圾郵件信賴等級 (SCL)** \> **0**。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-207">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>

   - <span data-ttu-id="1aa1f-208">規則例外： **寄件者** \> **網域是** \> fabrikam.com，只 (您想要略過垃圾郵件篩選) 的網域。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-208">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="1aa1f-209">仍然篩選來自 IP 允許清單來源之郵件的案例</span><span class="sxs-lookup"><span data-stu-id="1aa1f-209">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="1aa1f-210">來自 IP 允許清單中的電子郵件伺服器的郵件，在下列情況下仍會受到垃圾郵件篩選：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-210">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="1aa1f-211">您在 IP 允許清單中的 IP 位址也是在 Microsoft 365 的 *任何* 租使用者的內部部署中，以 IP 為基礎的輸入連接器進行設定。 (讓我們呼叫此租使用者 a) ， **而** 租使用者 a 和 EOP server 第一次遇到郵件，則都會發生在 microsoft 資料中心 *的相同* Active Directory 樹系中。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-211">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="1aa1f-212">在此案例中， **IPV： CAL** *會* 新增至郵件的 [反垃圾郵件郵件頭](anti-spam-message-headers.md) ， (指出郵件略過垃圾郵件篩選) ，但郵件仍受垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-212">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="1aa1f-213">您的租使用者包含 IP 允許清單和 EOP server，第一次遇到郵件時，就會發生在 Microsoft 資料中心的 *不同* Active Directory 樹系中。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-213">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="1aa1f-214">在此案例中， **IPV： CAL** *不* 會新增至郵件頭，所以郵件仍會受到垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-214">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="1aa1f-215">如果您遇到這兩種情況，您可以使用下列)  (設定來建立郵件流程規則，以確保來自有問題之 IP 位址的郵件會略過垃圾郵件篩選：</span><span class="sxs-lookup"><span data-stu-id="1aa1f-215">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="1aa1f-216">規則條件：**若為以下情況，套用這個規則** \> **寄件者** \> **IP 位址在任何這些範圍中或完全符合** \> (您的 IP 位址)。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-216">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="1aa1f-217">規則動作：**修改郵件屬性** \> **設定垃圾郵件信賴等級 (SCL)** \> **略過垃圾郵件篩選**。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-217">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="1aa1f-218">Microsoft 365 的新功能？</span><span class="sxs-lookup"><span data-stu-id="1aa1f-218">New to Microsoft 365?</span></span>

****

<span data-ttu-id="1aa1f-219">![LinkedIn 學習 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **新增至 Microsoft 365** 的簡短圖示？</span><span class="sxs-lookup"><span data-stu-id="1aa1f-219">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="1aa1f-220">探索適用于 **Microsoft 365 系統管理員和 IT 專業人員** 的免費影片課程，並 LinkedIn 的知識。</span><span class="sxs-lookup"><span data-stu-id="1aa1f-220">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>