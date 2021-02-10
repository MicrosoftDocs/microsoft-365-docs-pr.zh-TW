---
title: 管理 EOP 中的群組
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Admins in 獨立 Exchange Online Protection (EOP) 組織可以瞭解如何建立、修改及移除 Exchange 系統管理中心內的通訊群組和擁有郵件功能的安全性群組 (EAC) 和獨立 Exchange Online Protection (EOP) PowerShell。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01fe5c6ab1555749d38f9c092b05aca9befb67fe
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166960"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="8bdf3-103">管理 EOP 中的群組</span><span class="sxs-lookup"><span data-stu-id="8bdf3-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8bdf3-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="8bdf3-104">**Applies to**</span></span>
-  [<span data-ttu-id="8bdf3-105">Exchange Online Protection 獨立</span><span class="sxs-lookup"><span data-stu-id="8bdf3-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="8bdf3-106">在獨立 Exchange Online Protection (EOP 中) 沒有 Exchange Online 信箱的組織，您可以建立、修改及移除下列類型的群組：</span><span class="sxs-lookup"><span data-stu-id="8bdf3-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="8bdf3-107">**通訊群組**：郵件使用者或其他通訊群組的集合。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="8bdf3-108">例如，小組或其他需要在感興趣的常見區域接收或傳送電子郵件的群組。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="8bdf3-109">通訊群組專門用來散佈電子郵件，而不是安全主體 (他們不能) 指派許可權。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="8bdf3-110">擁有 **郵件功能的安全性群組**：郵件使用者的集合，以及需要系統管理員角色存取許可權的其他安全性群組。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="8bdf3-111">例如，您可能想要授與特定群組的使用者系統管理員許可權，讓他們可以設定反垃圾郵件和反惡意程式碼設定。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="8bdf3-112">根據預設，啟用郵件功能的新安全性群組會拒絕來自外部 (未驗證) 寄件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="8bdf3-113">不要將通訊群組新增至擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="8bdf3-114">您可以在 Exchange 系統管理中心管理群組 (EAC) 和獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8bdf3-115">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="8bdf3-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8bdf3-116">若要開啟 Exchange 系統管理中心，請參閱 [exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="8bdf3-117">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8bdf3-118">當您在獨立 EOP PowerShell 中管理群組時，可能會遇到節流。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="8bdf3-119">本文中的 PowerShell 程式使用的批次處理方法，可導致幾分鐘的傳播延遲，使命令的結果看得見。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="8bdf3-120">您必須先在 Exchange Online Protection 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="8bdf3-121">具體說來，您需要 **通訊群組** 角色，預設會指派給 **組織管理** 和 **收件者管理** 角色群組。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="8bdf3-122">如需詳細資訊，請參閱 [獨立 EOP 中的許可權](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="8bdf3-123">如需適用于本文中程式的鍵盤快速鍵的詳細資訊，請參閱 exchange [Online 中 exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="8bdf3-124">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="8bdf3-124">Having problems?</span></span> <span data-ttu-id="8bdf3-125">在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-125">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="8bdf3-126">使用 Exchange 系統管理中心來管理通訊群組</span><span class="sxs-lookup"><span data-stu-id="8bdf3-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="8bdf3-127">使用 EAC 來建立群組</span><span class="sxs-lookup"><span data-stu-id="8bdf3-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="8bdf3-128">在 EAC 中， **移至 [** 收件者 \> **群組**]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="8bdf3-129">按一下 ![ [新增新圖示] ](../../media/ITPro-EAC-AddIcon.png) ，然後選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="8bdf3-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="8bdf3-130">**通訊群組**</span><span class="sxs-lookup"><span data-stu-id="8bdf3-130">**Distribution group**</span></span>

   - <span data-ttu-id="8bdf3-131">**擁有郵件功能的安全性群組**</span><span class="sxs-lookup"><span data-stu-id="8bdf3-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="8bdf3-132">在開啟的 [新增群組] 頁面中，設定下列設定。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="8bdf3-133">以必要標出的設定 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="8bdf3-134"><sup>\*</sup>**顯示名稱**：此名稱會出現在組織的通訊錄、電子郵件傳送至此群組的 [收件者] 行，以及 EAC 的 [ **群組** ] 清單中。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="8bdf3-135">顯示名稱是必要的，必須是唯一的，而且應該是方便使用的，讓人員能夠辨識其內容。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="8bdf3-136"><sup>\*</sup>**別名**：使用此方塊可輸入群組的別名名稱。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="8bdf3-137">別名不得超過64個字元，且必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="8bdf3-138">當使用者在電子郵件的 [我的那一行] 中輸入別名時，它會解析為群組的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="8bdf3-139"><sup>\*</sup>**電子郵件地址**：電子郵件地址是由位於 ( @ ) 符號之左側的別名，以及右側的網域所組成。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="8bdf3-140">預設會 **使用 alias 的** 值作為別名值，但您可以變更它。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="8bdf3-141">在 [網域] 值中，按一下下拉清單，然後選取組織中的 [已接受的網域]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="8bdf3-142">**描述**：此描述會顯示在通訊錄和 EAC 中的 [詳細資料] 窗格中。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="8bdf3-143"><sup>\*</sup>**擁有** 者：群組擁有者可以管理群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="8bdf3-144">依預設，建立群組的人員為擁有者。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="8bdf3-145">所有群組都必須至少一個擁有者。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="8bdf3-146">若要新增擁有者，請按一下 [ **新增** ![ 新增] 圖示 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="8bdf3-147">在出現的對話方塊中，尋找並選取收件者或群組，然後按一下 [ **載入 >**]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="8bdf3-148">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8bdf3-149">完成後，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="8bdf3-150">若要移除擁有者，請選取擁有者，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="8bdf3-151">**成員**：新增和移除群組成員。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="8bdf3-152">若要新增成員，請按一下 [ **新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="8bdf3-153">在出現的對話方塊中，尋找並選取收件者或群組，然後按一下 [ **載入 >**]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="8bdf3-154">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8bdf3-155">完成後，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="8bdf3-156">若要移除成員，請選取成員，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="8bdf3-157">完成作業後，按一下 [ **儲存** ] 以建立通訊群組。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="8bdf3-158">使用 EAC 修改通訊群組</span><span class="sxs-lookup"><span data-stu-id="8bdf3-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="8bdf3-159">在 EAC 中， **移至 [** 收件者 \> **群組**]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="8bdf3-160">在群組清單中，選取您要修改的通訊群組或擁有郵件功能的安全性群組，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="8bdf3-161">在開啟的 [通訊群組內容] 頁面上，按一下下列其中一個索引標籤，以查看或變更屬性。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="8bdf3-162">完成後，按一下 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="8bdf3-163">一般</span><span class="sxs-lookup"><span data-stu-id="8bdf3-163">General</span></span>

<span data-ttu-id="8bdf3-164">使用此索引標籤可查看或變更群組的基本資訊。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="8bdf3-165">**顯示名稱**：此名稱會出現在通訊錄、電子郵件傳送至此群組的 [收件者] 行，以及 [ **群組] 清單** 中。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="8bdf3-166">顯示名稱是必要的，且應該是方便使用的，讓人員能夠辨識其內容。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="8bdf3-167">在您的網域中也必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="8bdf3-168">如果您已實現群組命名原則，則顯示名稱必須符合原則所定義的命名格式。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="8bdf3-169">**別名**：這是電子郵件地址的一部分，出現在 ( @ ) 符號的左側。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="8bdf3-170">如果您變更別名，群組的主要 SMTP 位址也會變更，而且會包含新的別名。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="8bdf3-171">此外，具有先前別名的電子郵件地址會保留為群組的 proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="8bdf3-172">**電子郵件地址**：電子郵件地址是由位於 ( @ ) 符號之左側的別名，以及右側的網域所組成。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="8bdf3-173">預設會 **使用 alias 的** 值作為別名值，但您可以變更它。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="8bdf3-174">在 [網域] 值中，按一下下拉清單，然後選取組織中的 [已接受的網域]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="8bdf3-175">**描述**：此描述會顯示在通訊錄和 EAC 中的 [詳細資料] 窗格中。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="8bdf3-176">擁有權</span><span class="sxs-lookup"><span data-stu-id="8bdf3-176">Ownership</span></span>

<span data-ttu-id="8bdf3-177">使用此索引標籤可指派群組擁有者。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="8bdf3-178">群組擁有者可以管理群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-178">A group owner can manage group membership.</span></span> <span data-ttu-id="8bdf3-179">依預設，建立群組的人員為擁有者。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="8bdf3-180">所有群組都必須至少一個擁有者。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="8bdf3-181">若要新增擁有者，請按一下 [ **新增** ![ 新增] 圖示 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="8bdf3-182">在出現的對話方塊中，尋找並選取收件者，然後按一下 [ **載入 >**]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="8bdf3-183">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8bdf3-184">完成後，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="8bdf3-185">若要移除擁有者，請選取擁有者，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="8bdf3-186">[成員資格]</span><span class="sxs-lookup"><span data-stu-id="8bdf3-186">Membership</span></span>

<span data-ttu-id="8bdf3-187">使用此索引標籤可以新增或移除群組成員。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="8bdf3-188">群組擁有者不需要是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="8bdf3-189">若要新增成員，請按一下 [ **新增** ![ 加入圖示] ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="8bdf3-190">在出現的對話方塊中，尋找並選取收件者或群組，然後按一下 [ **載入 >**]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="8bdf3-191">視需要重複此步驟多次。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8bdf3-192">完成後，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="8bdf3-193">若要移除成員，請選取成員，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="8bdf3-194">使用 EAC 移除群組</span><span class="sxs-lookup"><span data-stu-id="8bdf3-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="8bdf3-195">在 EAC 中， **移至 [** 收件者 \> **群組**]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="8bdf3-196">在群組清單中，選取您要移除的通訊群組，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="8bdf3-197">使用 PowerShell 管理群組</span><span class="sxs-lookup"><span data-stu-id="8bdf3-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="8bdf3-198">使用獨立 EOP PowerShell 來查看群組</span><span class="sxs-lookup"><span data-stu-id="8bdf3-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="8bdf3-199">若要在獨立 EOP PowerShell 中傳回所有通訊群組和擁有郵件功能的安全性群組的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8bdf3-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="8bdf3-200">若要傳回群組成員的清單，請 \<GroupIdentity\> 使用群組的名稱、別名或電子郵件地址加以取代，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8bdf3-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="8bdf3-201">如需詳細的語法及參數資訊，請參閱 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) 和 [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-201">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="8bdf3-202">使用獨立 EOP PowerShell 建立群組</span><span class="sxs-lookup"><span data-stu-id="8bdf3-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="8bdf3-203">若要在獨立 EOP PowerShell 中建立通訊群組或擁有郵件功能的安全性群組，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8bdf3-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="8bdf3-204">**附註**：</span><span class="sxs-lookup"><span data-stu-id="8bdf3-204">**Notes**:</span></span>

- <span data-ttu-id="8bdf3-205">_Name_ 參數是必要的，最大長度為64個字元，且必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="8bdf3-206">如果您未使用 _DisplayName_ 參數，則 _Name_ 參數的值會用於顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="8bdf3-207">如果您未使用 _alias_ 參數， _Name_ 參數會用於別名值。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="8bdf3-208">移除空格，且不支援的字元會轉換成問號 (？ ) 。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="8bdf3-209">如果您未使用 _PrimarySmtpAddress_ 參數，則會在 _PrimarySmtpAddress_ 參數中使用 alias 值。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="8bdf3-210">如果您未使用 _Type_ 參數，則預設值為「分配」。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="8bdf3-211">此範例會使用指定的屬性，建立名為 IT 管理員的通訊群組。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="8bdf3-212">如需詳細的語法及參數資訊，請參閱 [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="8bdf3-213">使用獨立 EOP PowerShell 修改群組</span><span class="sxs-lookup"><span data-stu-id="8bdf3-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="8bdf3-214">若要修改獨立 EOP PowerShell 中的群組，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8bdf3-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="8bdf3-215">本範例會使用變更主要 SMTP 位址 (也稱為「西雅圖員工」群組的回復位址) ，以供 sea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="8bdf3-216">此範例會將安全小組群組的目前成員取代為 Kitty Petersen and Tyson Fawcett。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="8bdf3-217">此範例會將名為 Tyson Fawcett 的新使用者新增至名為 Security Team 的群組，同時保留群組的目前成員。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="8bdf3-218">如需詳細的語法及參數資訊，請參閱 [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) 和 [EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="8bdf3-219">使用遠端 Windows PowerShell 移除群組</span><span class="sxs-lookup"><span data-stu-id="8bdf3-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="8bdf3-220">本範例會使用移除名為 IT 管理員的通訊群組。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="8bdf3-221">如需詳細的語法及參數資訊，請參閱 [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="8bdf3-222">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="8bdf3-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="8bdf3-223">若要確認您是否已成功建立、修改或移除通訊群組或已啟用郵件功能的安全性群組，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="8bdf3-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="8bdf3-224">在 EAC 中， **移至 [** 收件者 \> **群組**]。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="8bdf3-225">請確認群組已列出 (或未列出) ，並確認 [ **群組類型** ] 值。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="8bdf3-226">選取群組，然後在詳細資料窗格中查看資訊，或按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-AddIcon.png) 以查看設定。</span><span class="sxs-lookup"><span data-stu-id="8bdf3-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="8bdf3-227">在 [獨立 EOP PowerShell] 中，執行下列命令，確認群組已列出 (或未列出) ：</span><span class="sxs-lookup"><span data-stu-id="8bdf3-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="8bdf3-228">更換 \<GroupIdentity\> 為群組的名稱、別名或電子郵件地址，並執行下列命令來確認設定：</span><span class="sxs-lookup"><span data-stu-id="8bdf3-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="8bdf3-229">若要查看群組成員，請 \<GroupIdentity\> 使用群組的名稱、別名或電子郵件地址加以取代，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8bdf3-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
