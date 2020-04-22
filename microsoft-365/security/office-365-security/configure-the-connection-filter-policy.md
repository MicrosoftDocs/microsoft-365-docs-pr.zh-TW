---
title: 設定預設連線篩選原則、IP 允許清單、IP 封鎖清單、啟用或停用安全清單
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
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: 若要確保從您信任的人員寄送的電子郵件未遭到封鎖，您可以使用連線篩選原則來建立您信任的 IP 位址的允許清單。 您也可以建立封鎖的寄件者的 IP 封鎖清單。
ms.openlocfilehash: 54e68c79f78bb1408684ac583edff137cb687b53
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637743"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="de6da-104">設定連線篩選</span><span class="sxs-lookup"><span data-stu-id="de6da-104">Configure connection filtering</span></span>

<span data-ttu-id="de6da-105">如果您是使用 Exchange Online 中的信箱或獨立 Exchange Online Protection （EOP）客戶但沒有 Exchange Online 信箱的 Microsoft 365 客戶，您可以在 EOP （特別是預設連線篩選原則）中使用連線篩選，以根據其 IP 位址來識別正確或不良的來源電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="de6da-105">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="de6da-106">預設連線篩選原則的主要元件包括：</span><span class="sxs-lookup"><span data-stu-id="de6da-106">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="de6da-107">**IP 允許清單**：針對來自您透過 ip 位址或 ip 位址範圍所指定之來源電子郵件伺服器的所有傳入郵件，略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="de6da-107">**IP Allow List**: Skip spam filtering for for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="de6da-108">針對來自這些來源之郵件的垃圾郵件篩選可能仍會發生的情況，請參閱本主題稍後的[篩選來自 IP 允許清單來源的郵件](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered)。</span><span class="sxs-lookup"><span data-stu-id="de6da-108">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this topic.</span></span> <span data-ttu-id="de6da-109">如需 IP 允許清單應如何符合整體安全寄件者策略的詳細資訊，請參閱[在 Office 365 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="de6da-109">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="de6da-110">**IP 封鎖清單**：從您透過 ip 位址或 ip 位址範圍所指定之來源電子郵件伺服器封鎖所有傳入的郵件。</span><span class="sxs-lookup"><span data-stu-id="de6da-110">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="de6da-111">內送郵件會遭到拒絕，不會標示為垃圾郵件，也不會發生其他篩選。如需 IP 封鎖清單應如何符合整體封鎖的寄件者策略的詳細資訊，請參閱[在 Office 365 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="de6da-111">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs .For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="de6da-112">**安全清單**：*安全清單*是 Microsoft datacenter 中的動態允許清單，不需要客戶設定。</span><span class="sxs-lookup"><span data-stu-id="de6da-112">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="de6da-113">Microsoft 會識別這些信任的電子郵件來源，以訂閱各種協力廠商清單。</span><span class="sxs-lookup"><span data-stu-id="de6da-113">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="de6da-114">啟用或停用 [安全清單] 的使用。您無法在 [安全清單] 上設定來源電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="de6da-114">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="de6da-115">在 [安全清單] 上的電子郵件伺服器上，會略過傳入郵件的垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="de6da-115">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="de6da-116">本主題說明如何在安全性 & 規範中心或 PowerShell （Microsoft 365 客戶的 Exchange Online PowerShell 中）設定預設連線篩選原則。Exchange Online Protection PowerShell 適用于獨立 EOP 客戶）。</span><span class="sxs-lookup"><span data-stu-id="de6da-116">This topic describes how to configure the default connection filter policy in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span> <span data-ttu-id="de6da-117">如需 EOP 如何使用連線篩選的詳細資訊，請參閱您組織的整體反垃圾郵件設定的一部分，請參閱[反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="de6da-117">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="de6da-118">IP 允許清單、安全清單和 IP 封鎖清單是整體策略的一部分，可允許或封鎖您組織中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="de6da-118">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="de6da-119">如需詳細資訊，請參閱[建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)及[建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="de6da-119">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="de6da-120">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="de6da-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="de6da-121">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="de6da-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="de6da-122">若要直接移至 [反垃圾郵件設定]\*\*\*\* 頁面，請使用 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="de6da-122">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="de6da-123">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="de6da-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="de6da-124">若要連接至獨立版 Exchange Online Protection PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="de6da-124">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="de6da-125">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="de6da-125">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="de6da-126">若要修改預設連線篩選原則，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="de6da-126">To modify the default connection filter policy, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="de6da-127">若要對預設連線篩選原則進行唯讀存取，您必須是**Security Reader**角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="de6da-127">For read-only access to the default connection filter policy, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="de6da-128">如需安全性 & 規範中心中角色群組的詳細資訊，請參閱[安全性 & 規範中心中的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="de6da-128">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="de6da-129">若要尋找您要允許或封鎖之電子郵件伺服器（寄件者）的來源 IP 位址，您可以檢查郵件頭中的 [連接 IP （**CIP**）標頭] 欄位。</span><span class="sxs-lookup"><span data-stu-id="de6da-129">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="de6da-130">若要在不同的電子郵件客戶程式中查看郵件頭，請參閱在[Outlook 中查看網際網路郵件頭](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)。</span><span class="sxs-lookup"><span data-stu-id="de6da-130">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="de6da-131">IP 允許清單優先于 IP 封鎖清單（這兩個清單上的位址未遭到封鎖）。</span><span class="sxs-lookup"><span data-stu-id="de6da-131">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="de6da-132">IP 允許清單和 IP 封鎖清單都支援最多1273個專案，其中一個專案是單一 IP 位址、IP 位址範圍或無類別網域間路由選擇（CIDR） IP。</span><span class="sxs-lookup"><span data-stu-id="de6da-132">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="de6da-133">使用安全性 & 規範中心來修改預設連線篩選原則</span><span class="sxs-lookup"><span data-stu-id="de6da-133">Use the Security & Compliance Center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="de6da-134">在安全性 & 合規性中心，然後移至**威脅管理** \> **原則** \> **Anti-Spam**。</span><span class="sxs-lookup"><span data-stu-id="de6da-134">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="de6da-135">在 [**反垃圾郵件設定**] 頁面上， ![按一下 [展開圖示](../../media/scc-expand-icon.png)]，然後按一下 [**編輯原則**]，展開 [連線**篩選原則**]。</span><span class="sxs-lookup"><span data-stu-id="de6da-135">On the **Anti-spam settings** page, expand **Connection filter policy** by clicking ![Expand icon](../../media/scc-expand-icon.png), and then click **Edit policy**.</span></span>

3. <span data-ttu-id="de6da-136">在出現的**預設**浮出視窗中，設定下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="de6da-136">In the **Default** flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="de6da-137">**描述**：輸入選用的描述文字。</span><span class="sxs-lookup"><span data-stu-id="de6da-137">**Description**: Enter optional descriptive text.</span></span>

   - <span data-ttu-id="de6da-138">**IP 允許清單**：按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="de6da-138">**IP Allow List**: Click **Edit**.</span></span> <span data-ttu-id="de6da-139">在出現的 [ **IP 允許] 清單**快顯視窗中，使用下列語法，在 [**位址] 或 [位址範圍**] 方塊中輸入 IPV4 位址：</span><span class="sxs-lookup"><span data-stu-id="de6da-139">In the **IP Allow List** flyout that appears, enter an IPV4 address in the **Address or address range** box using the following syntax:</span></span>

     - <span data-ttu-id="de6da-140">單一 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="de6da-140">Single IP: For example, 192.168.1.1.</span></span>

     - <span data-ttu-id="de6da-141">IP 範圍：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="de6da-141">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

     - <span data-ttu-id="de6da-142">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="de6da-142">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="de6da-143">有效的網路遮罩值為/24 到/32。</span><span class="sxs-lookup"><span data-stu-id="de6da-143">Valid network mask values are /24 through /32.</span></span> <span data-ttu-id="de6da-144">若要略過 CIDR IP 遮罩值的垃圾郵件篩選，/1 到/23，請參閱本主題稍後的 [[略過垃圾郵件篩選] （適用于可用範圍區段之外的 CIDR ip](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) ）。</span><span class="sxs-lookup"><span data-stu-id="de6da-144">To skip spam filtering for CIDR IP mask values /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this topic.</span></span>

     <span data-ttu-id="de6da-145">若要新增 IP 位址或位址範圍，請**Add** ![按一下 [新增](../../media/ITPro-EAC-AddIcon.png)加入圖示]。</span><span class="sxs-lookup"><span data-stu-id="de6da-145">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="de6da-146">若要移除專案，請選取 [**允許的 IP 位址**] 中的專案，](../../media/scc-remove-icon.png)然後按一下 [**移除** ![]。</span><span class="sxs-lookup"><span data-stu-id="de6da-146">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="de6da-147">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="de6da-147">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="de6da-148">**IP 封鎖清單**：按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="de6da-148">**IP Block List**: Click **Edit**.</span></span> <span data-ttu-id="de6da-149">在出現的 [ **Ip 封鎖**] 快顯視窗中，在 [ **ip 允許清單**] 設定中先前所述的 [**位址] 或 [位址範圍**] 方塊中輸入單一 IP、ip 範圍或 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="de6da-149">In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.</span></span>

     <span data-ttu-id="de6da-150">若要新增 IP 位址或位址範圍，請**Add** ![按一下 [新增](../../media/ITPro-EAC-AddIcon.png)加入圖示]。</span><span class="sxs-lookup"><span data-stu-id="de6da-150">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="de6da-151">若要移除專案，請選取 [**封鎖的 IP 位址**] 中的專案，](../../media/scc-remove-icon.png)然後按一下 [**移除** ![]。</span><span class="sxs-lookup"><span data-stu-id="de6da-151">To remove an entry, select the entry in **Blocked IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="de6da-152">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="de6da-152">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="de6da-153">**開啟安全清單**：啟用或停用安全清單的使用，以找出將會略過垃圾郵件篩選的已知的良好寄件者。</span><span class="sxs-lookup"><span data-stu-id="de6da-153">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span>

4. <span data-ttu-id="de6da-154">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="de6da-154">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="de6da-155">使用安全性 & 規範中心來查看預設連線篩選原則</span><span class="sxs-lookup"><span data-stu-id="de6da-155">Use the Security & Compliance Center to view the default connection filter policy</span></span>

1. <span data-ttu-id="de6da-156">在安全性 & 合規性中心，然後移至**威脅管理** \> **原則** \> **Anti-Spam**。</span><span class="sxs-lookup"><span data-stu-id="de6da-156">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="de6da-157">在 [**反垃圾郵件設定**] 頁面上，按一下名為**Connection filter policy**之預設原則旁的下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="de6da-157">On the **Anti-spam settings** page, click the drop down next to the default policy named **Connection filter policy**.</span></span>

3. <span data-ttu-id="de6da-158">原則設定會顯示在開啟的下拉式功能表中。</span><span class="sxs-lookup"><span data-stu-id="de6da-158">The policy settings are displayed in the drop down that opens.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="de6da-159">使用 Exchange Online PowerShell 或獨立 Exchange Online Protection PowerShell 修改預設連線篩選原則</span><span class="sxs-lookup"><span data-stu-id="de6da-159">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="de6da-160">請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="de6da-160">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="de6da-161">**附註**：</span><span class="sxs-lookup"><span data-stu-id="de6da-161">**Notes**:</span></span>

- <span data-ttu-id="de6da-162">有效的 IP 位址或位址範圍值包括：</span><span class="sxs-lookup"><span data-stu-id="de6da-162">Valid IP address or address range values are:</span></span>

  - <span data-ttu-id="de6da-163">單一 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="de6da-163">Single IP: For example, 192.168.1.1.</span></span>

  - <span data-ttu-id="de6da-164">IP 範圍：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="de6da-164">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

  - <span data-ttu-id="de6da-165">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="de6da-165">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="de6da-166">有效的網路遮罩值為/24 到/32。</span><span class="sxs-lookup"><span data-stu-id="de6da-166">Valid network mask values are /24 through /32.</span></span>

- <span data-ttu-id="de6da-167">若要使用您指定的值*覆寫*任何現有的專案，請使用`IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`下列語法：。</span><span class="sxs-lookup"><span data-stu-id="de6da-167">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>

- <span data-ttu-id="de6da-168">若要*新增或移除*IP 位址或位址範圍，而不影響其他現有的專案，請`@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`使用下列語法：。</span><span class="sxs-lookup"><span data-stu-id="de6da-168">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>

- <span data-ttu-id="de6da-169">若要清空 IP 允許清單或 IP 封鎖清單，請使用值`$null`。</span><span class="sxs-lookup"><span data-stu-id="de6da-169">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="de6da-170">這個範例會設定 IP 允許清單和 IP 封鎖清單，其中包含指定的 IP 位址和位址範圍。</span><span class="sxs-lookup"><span data-stu-id="de6da-170">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="de6da-171">本範例會從 IP 允許清單中新增及移除指定的 IP 位址和位址範圍。</span><span class="sxs-lookup"><span data-stu-id="de6da-171">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="de6da-172">如需詳細的語法及參數資訊，請參閱[Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="de6da-172">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="de6da-173">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="de6da-173">How do you know this worked?</span></span>

<span data-ttu-id="de6da-174">若要確認您是否已成功修改預設連線篩選原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="de6da-174">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="de6da-175">在 [安全性 & 規範中心] 中，移至 [**威脅管理** \> **原則** \> ] **Anti-Spam** \>按一下 [連線**篩選原則（永不開啟**）] 旁的下拉式清單，然後驗證設定。</span><span class="sxs-lookup"><span data-stu-id="de6da-175">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-Spam** \> click the drop down next to **Connection filter policy (always ON**), and verify the settings.</span></span>

- <span data-ttu-id="de6da-176">在 Exchange Online PowerShell 或獨立 Exchange Online Protection PowerShell 中，執行下列命令並確認設定：</span><span class="sxs-lookup"><span data-stu-id="de6da-176">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="de6da-177">從 IP 允許清單中的專案傳送測試郵件。</span><span class="sxs-lookup"><span data-stu-id="de6da-177">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="de6da-178">IP 允許清單的其他考慮</span><span class="sxs-lookup"><span data-stu-id="de6da-178">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="de6da-179">下列各節會指出當您設定 IP 允許清單時，需要瞭解的其他專案。</span><span class="sxs-lookup"><span data-stu-id="de6da-179">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="de6da-180">略過可用範圍外的 CIDR IP 的垃圾郵件篩選</span><span class="sxs-lookup"><span data-stu-id="de6da-180">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="de6da-181">如本主題稍早所述，您只能在 IP 允許清單中使用具有 network mask/24 to/32 的 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="de6da-181">As described earlier in this topic, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="de6da-182">若要在/1 到/23 範圍內略過來自來源電子郵件伺服器的郵件篩選，您必須使用 Exchange 郵件流程規則（也稱為傳輸規則）。</span><span class="sxs-lookup"><span data-stu-id="de6da-182">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="de6da-183">不過，如果可能的話，建議您不要這麼做，因為在任何 Microsoft 的專屬或協力廠商封鎖清單中，如果有/1 to/23 CIDR IP 範圍的 IP 位址會出現，則郵件會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="de6da-183">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="de6da-184">現在，您完全知道潛在的問題，您可以使用下列設定建立郵件流程規則（至少），以確保來自這些 IP 位址的郵件會略過垃圾郵件篩選：</span><span class="sxs-lookup"><span data-stu-id="de6da-184">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="de6da-185">規則條件：**如果** \> **寄件者** \>的**IP 位址在任何這些範圍中，或完全符合** \> ，請套用此規則。請輸入含 a/1 to/23 網路遮罩的 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="de6da-185">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>

- <span data-ttu-id="de6da-186">規則動作：**修改郵件屬性** \> **設定垃圾郵件信賴等級 (SCL)** \> **略過垃圾郵件篩選**。</span><span class="sxs-lookup"><span data-stu-id="de6da-186">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="de6da-187">您可以審核規則、測試規則、在特定時間期間啟動規則，以及進行其他選擇。</span><span class="sxs-lookup"><span data-stu-id="de6da-187">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="de6da-188">施行規則之前，建議先測試規則一段時間。</span><span class="sxs-lookup"><span data-stu-id="de6da-188">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="de6da-189">如需詳細資訊，請參閱[在 Exchange Online 中管理郵件流程規則](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="de6da-189">For more information, see [Manage mail flow rules in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="de6da-190">略過來自相同來源之選擇性電子郵件網域的垃圾郵件篩選</span><span class="sxs-lookup"><span data-stu-id="de6da-190">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="de6da-191">一般來說，將 IP 位址或位址範圍新增至 IP 允許清單表示您信任來自該電子郵件來源的所有傳入郵件。</span><span class="sxs-lookup"><span data-stu-id="de6da-191">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="de6da-192">不過，如果該來源從多個網域傳送電子郵件，而您想要略過某些網域的垃圾郵件篩選功能，則該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="de6da-192">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="de6da-193">您無法只使用 IP 允許清單來執行這項作業，但是您可以搭配郵件流程規則使用 [IP 允許] 清單。</span><span class="sxs-lookup"><span data-stu-id="de6da-193">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="de6da-194">例如，來源電子郵件伺服器192.168.1.25 會從網域 contoso.com、fabrikam.com 和 tailspintoys.com 傳送電子郵件，但您只想要對來自 fabrikam.com 中寄件者的郵件略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="de6da-194">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="de6da-195">若要這麼做，請使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="de6da-195">To do this, use the following steps:</span></span>

1. <span data-ttu-id="de6da-196">將192.168.1.25 新增至 IP 允許清單。</span><span class="sxs-lookup"><span data-stu-id="de6da-196">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="de6da-197">設定具有下列設定的郵件流程規則（至少）：</span><span class="sxs-lookup"><span data-stu-id="de6da-197">Configure a mail flow rule with the following settings (at a minimum):</span></span>

   - <span data-ttu-id="de6da-198">規則條件：**如果** \> **寄件者** \>的**IP 位址在任何這些範圍中，或完全符合** \> 192.168.1.25 （您在上一個步驟中新增至 ip 允許清單的相同 IP 位址或位址範圍），請套用此規則。</span><span class="sxs-lookup"><span data-stu-id="de6da-198">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>

   - <span data-ttu-id="de6da-199">規則動作：**修改郵件屬性** \> **設定垃圾郵件信賴等級（SCL）** \> **0**。</span><span class="sxs-lookup"><span data-stu-id="de6da-199">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>

   - <span data-ttu-id="de6da-200">規則例外：**寄件者** \> **網域為** \> fabrikam.com （只是您想要略過垃圾郵件篩選的網域）。</span><span class="sxs-lookup"><span data-stu-id="de6da-200">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="de6da-201">仍然篩選來自 IP 允許清單來源之郵件的案例</span><span class="sxs-lookup"><span data-stu-id="de6da-201">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="de6da-202">來自 IP 允許清單中的電子郵件伺服器的郵件，在下列情況下仍會受到垃圾郵件篩選：</span><span class="sxs-lookup"><span data-stu-id="de6da-202">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="de6da-203">您的 IP 允許清單中的 IP 位址也會設定在 Microsoft 365 （我們呼叫此租使用者 A）的*任何*租使用者中的內部部署、以 IP 為基礎的輸入連接器中，**並且**第一次遇到郵件的承租人 a 和 EOP Server 都會發生在 Microsoft 資料中心*的相同*Active Directory 樹系中。</span><span class="sxs-lookup"><span data-stu-id="de6da-203">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="de6da-204">在此案例中， **IPV： CAL** *會*新增至郵件的[反垃圾郵件郵件頭](anti-spam-message-headers.md)（指出郵件略過垃圾郵件篩選），但郵件仍受垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="de6da-204">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="de6da-205">您的租使用者包含 IP 允許清單和 EOP server，第一次遇到郵件時，就會發生在 Microsoft 資料中心的*不同*Active Directory 樹系中。</span><span class="sxs-lookup"><span data-stu-id="de6da-205">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="de6da-206">在此案例中， **IPV： CAL** *不*會新增至郵件頭，所以郵件仍會受到垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="de6da-206">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="de6da-207">如果您遇到這兩種情況，您可以使用下列設定建立郵件流程規則（至少），以確保來自有問題之 IP 位址的郵件會略過垃圾郵件篩選：</span><span class="sxs-lookup"><span data-stu-id="de6da-207">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="de6da-208">規則條件：**若為以下情況，套用這個規則** \> **寄件者** \> **IP 位址在任何這些範圍中或完全符合** \> (您的 IP 位址)。</span><span class="sxs-lookup"><span data-stu-id="de6da-208">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="de6da-209">規則動作：**修改郵件屬性** \> **設定垃圾郵件信賴等級 (SCL)** \> **略過垃圾郵件篩選**。</span><span class="sxs-lookup"><span data-stu-id="de6da-209">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-office-365"></a><span data-ttu-id="de6da-210">初次使用 Office 365 嗎？</span><span class="sxs-lookup"><span data-stu-id="de6da-210">New to Office 365?</span></span>

||
|:-----|
|<span data-ttu-id="de6da-211">![LinkedIn 學習](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **新增至 Microsoft 365**的簡短圖示？</span><span class="sxs-lookup"><span data-stu-id="de6da-211">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="de6da-212">探索免費的影片課程，以供**系統管理員和 IT 專業人員**使用，LinkedIn 的知識。</span><span class="sxs-lookup"><span data-stu-id="de6da-212">Discover free video courses for **Admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
