---
title: 在獨立版 EOP 中管理郵件使用者
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 瞭解如何在 Exchange Online Protection (EOP) 中管理郵件使用者，包括使用目錄同步處理、EAC 和 PowerShell 來管理使用者。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203437"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="f2abb-103">在獨立版 EOP 中管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="f2abb-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f2abb-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="f2abb-104">**Applies to**</span></span>
-  [<span data-ttu-id="f2abb-105">Exchange Online Protection 獨立</span><span class="sxs-lookup"><span data-stu-id="f2abb-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="f2abb-106">在獨立 Exchange Online Protection (EOP 中) 沒有 Exchange Online 信箱的組織，郵件使用者是使用者帳戶的基本類型。</span><span class="sxs-lookup"><span data-stu-id="f2abb-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="f2abb-107">郵件使用者在獨立 EOP 組織中具有帳號憑證，而且可以存取) 具有指派許可權的資源 (。</span><span class="sxs-lookup"><span data-stu-id="f2abb-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="f2abb-108">郵件使用者的電子郵件地址為外部 (例如，在您的內部部署電子郵件環境) 中。</span><span class="sxs-lookup"><span data-stu-id="f2abb-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="f2abb-109">當您建立郵件使用者時，可在 Microsoft 365 系統管理中心使用對應的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f2abb-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f2abb-110">當您在 Microsoft 365 系統管理中心中建立使用者帳戶時，將無法使用該帳戶來建立郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="f2abb-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="f2abb-111">在獨立 EOP 中建立及管理郵件使用者的建議方法是使用目錄同步處理，如本文稍後的 [使用目錄同步處理來管理郵件使用者](#use-directory-synchronization-to-manage-mail-users) 一節所述。</span><span class="sxs-lookup"><span data-stu-id="f2abb-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="f2abb-112">針對具有少量使用者的獨立 EOP 組織，您可以在 Exchange 系統管理中心中新增及管理郵件使用者 (EAC) 或獨立 EOP PowerShell （如本文所述）。</span><span class="sxs-lookup"><span data-stu-id="f2abb-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f2abb-113">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="f2abb-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f2abb-114">若要 (EAC) 開啟 Exchange 系統管理中心，請參閱 [exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="f2abb-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="f2abb-115">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f2abb-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f2abb-116">當您在 EOP PowerShell 中建立郵件使用者時，可能會遇到節流。</span><span class="sxs-lookup"><span data-stu-id="f2abb-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="f2abb-117">此外，EOP PowerShell Cmdlet 使用的批次處理方法，可導致幾分鐘的傳播延遲，使命令的結果看得見。</span><span class="sxs-lookup"><span data-stu-id="f2abb-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="f2abb-118">您必須先在 Exchange Online Protection 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="f2abb-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="f2abb-119">具體而言，您需要建立 **郵件收件** 者 (建立) 和 **郵件** 收件者， (修改) 角色，預設會指派給 **組織管理** (全域系統管理員) 和 **收件者管理** 角色群組。</span><span class="sxs-lookup"><span data-stu-id="f2abb-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="f2abb-120">如需詳細資訊，請參閱 [獨立 EOP 中的許可權](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色群組中的成員清單](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="f2abb-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="f2abb-121">如需適用于本文中程式的鍵盤快速鍵的詳細資訊，請參閱 exchange [Online 中 exchange 系統管理中心的鍵盤快速鍵](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="f2abb-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="f2abb-122">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="f2abb-122">Having problems?</span></span> <span data-ttu-id="f2abb-123">在 Exchange 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="f2abb-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="f2abb-124">請造訪 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 論壇。</span><span class="sxs-lookup"><span data-stu-id="f2abb-124">Visit the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="f2abb-125">使用 Exchange 系統管理中心管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="f2abb-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="f2abb-126">使用 EAC 來建立郵件使用者</span><span class="sxs-lookup"><span data-stu-id="f2abb-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="f2abb-127">在 EAC 中，**移至 [** 收件者] [ \> **連絡人**]</span><span class="sxs-lookup"><span data-stu-id="f2abb-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="f2abb-128">按一下 [ **新增** ![ 新圖示] ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="f2abb-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="f2abb-129">在開啟的 [ **新增郵件使用者** ] 頁面中，設定下列設定。</span><span class="sxs-lookup"><span data-stu-id="f2abb-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="f2abb-130">以必要標出的設定 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="f2abb-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="f2abb-131">**名字**   使用此方塊輸入使用者的名字。</span><span class="sxs-lookup"><span data-stu-id="f2abb-131">**First name**</span></span>

   - <span data-ttu-id="f2abb-132">**縮寫**：人員的中間名首字母。</span><span class="sxs-lookup"><span data-stu-id="f2abb-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="f2abb-133">**姓氏**   使用此方塊輸入使用者的姓氏。</span><span class="sxs-lookup"><span data-stu-id="f2abb-133">**Last name**</span></span>

   - <span data-ttu-id="f2abb-134"><sup>\*</sup>**顯示名稱**：根據預設，此方塊會顯示 [ **名字**]、[ **縮寫**] 和 [ **姓氏** ] 方塊中的值。</span><span class="sxs-lookup"><span data-stu-id="f2abb-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="f2abb-135">您可以接受此值或加以變更。</span><span class="sxs-lookup"><span data-stu-id="f2abb-135">You can accept this value or change it.</span></span> <span data-ttu-id="f2abb-136">該值應該是唯一的，且長度上限為64個字元。</span><span class="sxs-lookup"><span data-stu-id="f2abb-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="f2abb-137"><sup>\*</sup>**Alias**：針對使用者輸入唯一的別名，使用最多64個字元。</span><span class="sxs-lookup"><span data-stu-id="f2abb-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="f2abb-138">**外部電子郵件地址**：輸入使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f2abb-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="f2abb-139">網域應該位於雲端架構組織的外部。</span><span class="sxs-lookup"><span data-stu-id="f2abb-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="f2abb-140"><sup>\*</sup>**使用者識別碼**：輸入人員將用來登入服務的帳戶。</span><span class="sxs-lookup"><span data-stu-id="f2abb-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="f2abb-141">使用者識別碼包含在 ( @ ) 符號 ( @ ) 左邊的使用者名稱，以及右側的網域。</span><span class="sxs-lookup"><span data-stu-id="f2abb-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="f2abb-142"><sup>\*</sup>**新增密碼** 和 <sup>\*</sup> **確認密碼**：輸入並重新輸入帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="f2abb-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="f2abb-143">請確認密碼符合您組織的密碼長度、複雜性和歷程記錄需求。</span><span class="sxs-lookup"><span data-stu-id="f2abb-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="f2abb-144">完成作業後，按一下 [ **儲存** ] 以建立郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="f2abb-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="f2abb-145">使用 EAC 修改郵件使用者</span><span class="sxs-lookup"><span data-stu-id="f2abb-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="f2abb-146">In the EAC, go to **Recipients** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="f2abb-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="f2abb-147">選取您要修改的郵件使用者，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="f2abb-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="f2abb-148">在開啟的 [郵件使用者屬性] 頁面上，按一下下列其中一個索引標籤以查看或變更屬性。</span><span class="sxs-lookup"><span data-stu-id="f2abb-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="f2abb-149">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="f2abb-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="f2abb-150">一般</span><span class="sxs-lookup"><span data-stu-id="f2abb-150">General</span></span>

<span data-ttu-id="f2abb-151">使用 [ **一般** ] 索引標籤可查看或變更郵件使用者的基本資訊。</span><span class="sxs-lookup"><span data-stu-id="f2abb-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="f2abb-152">**名字**   使用此方塊輸入使用者的名字。</span><span class="sxs-lookup"><span data-stu-id="f2abb-152">**First name**</span></span>

- <span data-ttu-id="f2abb-153">**縮寫**</span><span class="sxs-lookup"><span data-stu-id="f2abb-153">**Initials**</span></span>

- <span data-ttu-id="f2abb-154">**姓氏**   使用此方塊輸入使用者的姓氏。</span><span class="sxs-lookup"><span data-stu-id="f2abb-154">**Last name**</span></span>

- <span data-ttu-id="f2abb-155">**顯示名稱**：這個名稱會出現在組織的通訊錄、電子郵件中的 [To：] 和 [寄件者：] 行，以及 EAC 中的連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="f2abb-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="f2abb-156">這個顯示名稱前後不可包含空格。</span><span class="sxs-lookup"><span data-stu-id="f2abb-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="f2abb-157">**使用者識別碼**：這是 Microsoft 365 中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f2abb-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="f2abb-158">您無法在這裡修改此值。</span><span class="sxs-lookup"><span data-stu-id="f2abb-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="f2abb-159">連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="f2abb-159">Contact information</span></span>

<span data-ttu-id="f2abb-160">使用 [ **連絡人資訊** ] 索引標籤來查看或變更使用者的連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="f2abb-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="f2abb-161">此頁的資訊顯示於通訊錄中。</span><span class="sxs-lookup"><span data-stu-id="f2abb-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="f2abb-162">**街**</span><span class="sxs-lookup"><span data-stu-id="f2abb-162">**Street**</span></span>
- <span data-ttu-id="f2abb-163">**City**</span><span class="sxs-lookup"><span data-stu-id="f2abb-163">**City**</span></span>
- <span data-ttu-id="f2abb-164">**縣/市**</span><span class="sxs-lookup"><span data-stu-id="f2abb-164">**State/Province**</span></span>
- <span data-ttu-id="f2abb-165">**郵遞區號**</span><span class="sxs-lookup"><span data-stu-id="f2abb-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="f2abb-166">**國家/地區**</span><span class="sxs-lookup"><span data-stu-id="f2abb-166">**Country/Region**</span></span>
- <span data-ttu-id="f2abb-167">**公司電話**</span><span class="sxs-lookup"><span data-stu-id="f2abb-167">**Work phone**</span></span>
- <span data-ttu-id="f2abb-168">**行動電話**</span><span class="sxs-lookup"><span data-stu-id="f2abb-168">**Mobile phone**</span></span>
- <span data-ttu-id="f2abb-169">**傳真**</span><span class="sxs-lookup"><span data-stu-id="f2abb-169">**Fax**</span></span>
- <span data-ttu-id="f2abb-170">**更多選項**</span><span class="sxs-lookup"><span data-stu-id="f2abb-170">**More options**</span></span>

  - <span data-ttu-id="f2abb-171">**Office**</span><span class="sxs-lookup"><span data-stu-id="f2abb-171">**Office**</span></span>
  - <span data-ttu-id="f2abb-172">**住家電話**</span><span class="sxs-lookup"><span data-stu-id="f2abb-172">**Home phone**</span></span>
  - <span data-ttu-id="f2abb-173">**網頁**</span><span class="sxs-lookup"><span data-stu-id="f2abb-173">**Web page**</span></span>
  - <span data-ttu-id="f2abb-174">**附註**</span><span class="sxs-lookup"><span data-stu-id="f2abb-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="f2abb-175">組織</span><span class="sxs-lookup"><span data-stu-id="f2abb-175">Organization</span></span>

<span data-ttu-id="f2abb-176">使用 [ **組織** ] 索引標籤，記錄組織中使用者角色的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f2abb-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="f2abb-177">**Title**</span><span class="sxs-lookup"><span data-stu-id="f2abb-177">**Title**</span></span>
- <span data-ttu-id="f2abb-178">**Department**</span><span class="sxs-lookup"><span data-stu-id="f2abb-178">**Department**</span></span>
- <span data-ttu-id="f2abb-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="f2abb-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="f2abb-180">使用 EAC 來移除郵件使用者</span><span class="sxs-lookup"><span data-stu-id="f2abb-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="f2abb-181">In the EAC, go to **Recipients** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="f2abb-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="f2abb-182">選取您要移除的郵件使用者，然後按一下 [ **移除** ![ 移除圖示] ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="f2abb-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="f2abb-183">使用 PowerShell 管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="f2abb-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="f2abb-184">使用獨立 EOP PowerShell 來查看郵件使用者</span><span class="sxs-lookup"><span data-stu-id="f2abb-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="f2abb-185">若要傳回獨立 EOP PowerShell 中所有郵件使用者的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f2abb-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="f2abb-186">若要查看特定郵件使用者的詳細資訊，請 \<MailUserIdentity\> 以郵件使用者的名稱、別名或帳戶名稱取代，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f2abb-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="f2abb-187">如需詳細的語法及參數資訊，請參閱 [Get-Recipient](/powershell/module/exchange/get-recipient) 和 [Get-User](/powershell/module/exchange/get-user)。</span><span class="sxs-lookup"><span data-stu-id="f2abb-187">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User](/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="f2abb-188">使用獨立 EOP PowerShell 建立郵件使用者</span><span class="sxs-lookup"><span data-stu-id="f2abb-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="f2abb-189">若要在獨立 EOP PowerShell 中建立郵件使用者，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f2abb-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="f2abb-190">**附註**：</span><span class="sxs-lookup"><span data-stu-id="f2abb-190">**Notes**:</span></span>

- <span data-ttu-id="f2abb-191">_Name_ 參數是必要的，最大長度為64個字元，且必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f2abb-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="f2abb-192">如果您未使用 _DisplayName_ 參數，則 _Name_ 參數的值會用於顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="f2abb-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="f2abb-193">如果您未使用 _alias_ 參數，則會使用 _MicrosoftOnlineServicesID_ 參數的左側作為別名。</span><span class="sxs-lookup"><span data-stu-id="f2abb-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="f2abb-194">如果您未使用 _ExternalEmailAddress_ 參數， _MicrosoftOnlineServicesID_ 值會用於外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f2abb-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="f2abb-195">本範例會建立具有下列設定的郵件使用者：</span><span class="sxs-lookup"><span data-stu-id="f2abb-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="f2abb-196">名稱為 JeffreyZeng，顯示名稱為 Jeffrey Zeng。</span><span class="sxs-lookup"><span data-stu-id="f2abb-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="f2abb-197">名字為 Jeffrey，姓氏為 Zeng。</span><span class="sxs-lookup"><span data-stu-id="f2abb-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="f2abb-198">別名為 jeffreyz。</span><span class="sxs-lookup"><span data-stu-id="f2abb-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="f2abb-199">外部電子郵件地址為 jzeng@tailspintoys.com。</span><span class="sxs-lookup"><span data-stu-id="f2abb-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="f2abb-200">帳戶名稱是 jeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="f2abb-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="f2abb-201">密碼為 Pa$$word1。</span><span class="sxs-lookup"><span data-stu-id="f2abb-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="f2abb-202">如需詳細的語法及參數資訊，請參閱 [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="f2abb-202">For detailed syntax and parameter information, see [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="f2abb-203">使用獨立 EOP PowerShell 修改郵件使用者</span><span class="sxs-lookup"><span data-stu-id="f2abb-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="f2abb-204">若要在獨立 EOP PowerShell 中修改現有的郵件使用者，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="f2abb-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="f2abb-205">此範例會設定 Pilar Pinilla 的外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f2abb-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="f2abb-206">此範例會將所有郵件使用者的 [公司] 內容設定為 [Contoso]。</span><span class="sxs-lookup"><span data-stu-id="f2abb-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="f2abb-207">如需詳細的語法及參數資訊，請參閱 [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="f2abb-207">For detailed syntax and parameter information, see [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="f2abb-208">使用獨立 EOP PowerShell 移除郵件使用者</span><span class="sxs-lookup"><span data-stu-id="f2abb-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="f2abb-209">若要在獨立 EOP PowerShell 中移除郵件使用者，請以 \<MailUserIdentity\> 郵件使用者的名稱、別名或帳戶名稱取代，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f2abb-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="f2abb-210">此範例會移除 Jeffrey Zeng 的郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="f2abb-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="f2abb-211">如需詳細的語法及參數資訊，請參閱 [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="f2abb-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f2abb-212">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="f2abb-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="f2abb-213">若要確認您是否已在獨立 EOP 中成功建立、修改或移除郵件使用者，請使用下列任一程式：</span><span class="sxs-lookup"><span data-stu-id="f2abb-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="f2abb-214">In the EAC, go to **Recipients** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="f2abb-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="f2abb-215">請確認郵件使用者已列出 (或未列出) 。</span><span class="sxs-lookup"><span data-stu-id="f2abb-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="f2abb-216">選取郵件使用者，然後在詳細資料窗格中查看資訊，或按一下 [ **編輯** ![ 編輯圖示] ](../../media/ITPro-EAC-AddIcon.png) 以查看設定。</span><span class="sxs-lookup"><span data-stu-id="f2abb-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="f2abb-217">在 [獨立 EOP PowerShell] 中，執行下列命令來確認郵件使用者已列出 (或未列出) ：</span><span class="sxs-lookup"><span data-stu-id="f2abb-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="f2abb-218">\<MailUserIdentity\>以郵件使用者的名稱、別名或帳戶名稱取代，並執行下列命令來確認設定：</span><span class="sxs-lookup"><span data-stu-id="f2abb-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="f2abb-219">使用目錄同步處理來管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="f2abb-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="f2abb-220">在獨立 EOP 中，具有內部部署 Active Directory 的客戶可以使用目錄同步作業。</span><span class="sxs-lookup"><span data-stu-id="f2abb-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="f2abb-221">您可以將這些帳戶同步處理至 Azure Active Directory (Azure AD) ，以將帳戶副本儲存在雲端中。</span><span class="sxs-lookup"><span data-stu-id="f2abb-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="f2abb-222">當您將現有的使用者帳戶同步處理至 Azure Active Directory 時，您可以在 Exchange 系統管理中心的 [收件 **者] 窗格** 中， (EAC) 或獨立 EOP PowerShell 中查看那些使用者。</span><span class="sxs-lookup"><span data-stu-id="f2abb-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="f2abb-223">**附註**：</span><span class="sxs-lookup"><span data-stu-id="f2abb-223">**Notes**:</span></span>

- <span data-ttu-id="f2abb-224">如果您使用目錄同步處理來管理收件者，您仍然可以新增及管理 Microsoft 365 系統管理中心中的使用者，但不會與您的內部部署 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="f2abb-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="f2abb-225">這是因為目錄同步作業只會從內部部署 Active Directory 同步收件者至雲端。</span><span class="sxs-lookup"><span data-stu-id="f2abb-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="f2abb-226">建議搭配下列功能一起使用目錄同步處理：</span><span class="sxs-lookup"><span data-stu-id="f2abb-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="f2abb-227">**Outlook 安全寄件者清單和封鎖的寄件者清單**：同步處理至服務時，這些清單將優先于服務中的垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="f2abb-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="f2abb-228">這可讓使用者管理其個人的安全寄件者清單和封鎖的寄件者清單和個別寄件者和網域專案。</span><span class="sxs-lookup"><span data-stu-id="f2abb-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="f2abb-229">如需詳細資訊，請參閱[設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="f2abb-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="f2abb-230">**目錄架構邊緣封鎖 (DBEB)**：如需 DBEB 的詳細資訊，請參閱 [使用目錄架構邊緣封鎖以拒絕傳送至無效收件](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)者的郵件。</span><span class="sxs-lookup"><span data-stu-id="f2abb-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="f2abb-231">**使用者存取隔離**：若要存取隔離的郵件，收件者的服務中必須具有有效的使用者識別碼和密碼。</span><span class="sxs-lookup"><span data-stu-id="f2abb-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="f2abb-232">如需隔離的詳細資訊，請參閱 [尋找及發行隔離的郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="f2abb-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="f2abb-233">**郵件流程規則 (也稱為傳輸規則)**：使用目錄同步處理時，您現有的 Active directory 使用者和群組會自動上傳至雲端，您也可以建立特定使用者和/或群組的郵件流程規則，而不必手動將其新增至服務中。</span><span class="sxs-lookup"><span data-stu-id="f2abb-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="f2abb-234">請注意， [動態通訊群組](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)無法透過目錄同步作業進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="f2abb-234">Note that [dynamic distribution groups](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="f2abb-235">取得必要的許可權並準備目錄同步處理，如 [與 Azure Active directory 混合身分識別的功能](/azure/active-directory/hybrid/whatis-hybrid-identity)所述。</span><span class="sxs-lookup"><span data-stu-id="f2abb-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="f2abb-236">同步處理目錄與 Azure Active Directory Connect (AAD Connect) </span><span class="sxs-lookup"><span data-stu-id="f2abb-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="f2abb-237">啟動目錄同步處理，如 [AZURE AD Connect sync 中所述：瞭解及自訂同步](/azure/active-directory/hybrid/how-to-connect-sync-whatis)處理。</span><span class="sxs-lookup"><span data-stu-id="f2abb-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="f2abb-238">依照 [AZURE AD Connect 先決條件](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)中所述，安裝及設定內部部署電腦以執行 AAD connect。</span><span class="sxs-lookup"><span data-stu-id="f2abb-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="f2abb-239">[選取要用於 AZURE AD Connect 的安裝類型](/azure/active-directory/hybrid/how-to-connect-install-select-installation)：</span><span class="sxs-lookup"><span data-stu-id="f2abb-239">[Select which installation type to use for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="f2abb-240">Express</span><span class="sxs-lookup"><span data-stu-id="f2abb-240">Express</span></span>](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="f2abb-241">自訂</span><span class="sxs-lookup"><span data-stu-id="f2abb-241">Custom</span></span>](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="f2abb-242">傳遞驗證</span><span class="sxs-lookup"><span data-stu-id="f2abb-242">Pass-through authentication</span></span>](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="f2abb-p121">完成 Azure Active Directory 同步處理工具設定精靈 之後，您的 Active Directory 樹系中會建立 **MSOL_AD_SYNC** 帳戶。此帳戶將用來讀取和同步處理您的內部部署 Active Directory 資訊。為了讓目錄同步作業能夠正確運作，請確定有開啟您的本機目錄同步作業伺服器上的 TCP 443。</span><span class="sxs-lookup"><span data-stu-id="f2abb-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="f2abb-246">在設定同步處理之後，請務必確認 AAD 連線已正確同步處理。</span><span class="sxs-lookup"><span data-stu-id="f2abb-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="f2abb-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span><span class="sxs-lookup"><span data-stu-id="f2abb-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>