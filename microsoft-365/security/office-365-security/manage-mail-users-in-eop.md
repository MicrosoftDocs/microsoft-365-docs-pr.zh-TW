---
title: 管理 EOP 中的郵件使用者
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 定義郵件使用者是管理 Exchange Online Protection (EOP) 的重要環節。
ms.openlocfilehash: bdbc3cd54901d53b4a7d01bcf513a9b9a0df1c01
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633791"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="ad51d-103">管理 EOP 中的郵件使用者</span><span class="sxs-lookup"><span data-stu-id="ad51d-103">Manage mail users in EOP</span></span>

<span data-ttu-id="ad51d-p101">定義郵件使用者是管理 Exchange Online Protection (EOP) 的重要環節。在 EOP 中，您可以透過數種方式來管理使用者：</span><span class="sxs-lookup"><span data-stu-id="ad51d-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>

- <span data-ttu-id="ad51d-p102">**使用目錄同步處理來管理郵件使用者**：如果您的公司在內部部署 Active Directory 環境中有現有的使用者帳戶，您可將這些帳戶同步處理至 Azure Active Directory (AD)，此工具會將這些帳戶的複本儲存至雲端。將現有的使用者帳戶同步處理至 Azure Active Directory 時，您可以在 Exchange 系統管理中心 (EAC) 的 [**收件者**] 窗格中檢視這些使用者。建議使用目錄同步作業。</span><span class="sxs-lookup"><span data-stu-id="ad51d-p102">**Use directory synchronization to manage mail users**: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud. When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC). Using directory synchronization is recommended.</span></span>

- <span data-ttu-id="ad51d-p103">**使用 EAC 管理郵件使用者**：在 EAC 中直接新增及管理郵件使用者。這是新增郵件使用者最簡單的方法，也很適合一次新增一位使用者。</span><span class="sxs-lookup"><span data-stu-id="ad51d-p103">**Use the EAC to manage mail users**: Add and manage mail users directly in the EAC. This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>

- <span data-ttu-id="ad51d-111">**使用 PowerShell 管理郵件使用者**：在 Exchange Online Protection PowerShell 中新增及管理郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="ad51d-111">**Use PowerShell to manage mail users**: Add and manage mail users by in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="ad51d-112">這個方法適合用來新增多筆記錄和建立指令碼。</span><span class="sxs-lookup"><span data-stu-id="ad51d-112">This method is useful for adding multiple records and creating scripts.</span></span>

> [!NOTE]
> <span data-ttu-id="ad51d-113">您可以在 Microsoft 365 系統管理中心新增使用者，但是這些使用者不能做為郵件收件者使用。</span><span class="sxs-lookup"><span data-stu-id="ad51d-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ad51d-114">開始之前</span><span class="sxs-lookup"><span data-stu-id="ad51d-114">Before you begin</span></span>

- <span data-ttu-id="ad51d-115">若要開啟 Exchange 系統管理中心，請參閱 exchange [Online Protection 中的 exchange 系統管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="ad51d-115">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="ad51d-p105">您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)中的「使用者、連絡人和角色群組」項目。</span><span class="sxs-lookup"><span data-stu-id="ad51d-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="ad51d-118">請注意，使用 Exchange Online Protection PowerShell Cmdlet 建立郵件使用者時，您可能會遇到節流。</span><span class="sxs-lookup"><span data-stu-id="ad51d-118">Be aware that when creating mail users by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="ad51d-119">本主題中的 PowerShell 命令使用的批次處理方法，可導致幾分鐘的傳播延遲，使命令的結果看得見。</span><span class="sxs-lookup"><span data-stu-id="ad51d-119">The PowerShell commands in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="ad51d-120">若要了解如何使用 Windows PowerShell 來連接至 Exchange Online Protection，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ad51d-120">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ad51d-121">如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="ad51d-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="ad51d-122">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="ad51d-122">Having problems?</span></span> <span data-ttu-id="ad51d-123">在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="ad51d-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="ad51d-124">使用目錄同步處理來管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="ad51d-124">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="ad51d-125">本節提供使用目錄同步處理來管理電子郵件使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad51d-125">This section provides information about managing email users by using directory synchronization.</span></span>

<span data-ttu-id="ad51d-126">**附註**：</span><span class="sxs-lookup"><span data-stu-id="ad51d-126">**Notes**:</span></span>

- <span data-ttu-id="ad51d-127">如果您使用目錄同步處理來管理收件者，您仍然可以新增及管理 Microsoft 365 系統管理中心中的使用者，但不會與您的內部部署 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="ad51d-127">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="ad51d-128">這是因為目錄同步處理只會將內部部署 Active Directory 中的收**件**者同步處理**至**雲端。</span><span class="sxs-lookup"><span data-stu-id="ad51d-128">This is because directory synchronization only syncs recipients **from** your on-premises Active Directory **to** the cloud.</span></span>

- <span data-ttu-id="ad51d-129">建議使用目錄同步處理，以搭配下列功能使用：</span><span class="sxs-lookup"><span data-stu-id="ad51d-129">Directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="ad51d-130">**Outlook 安全寄件者和封鎖的寄件者清單**：同步處理至服務時，這些清單將優先于服務中的垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="ad51d-130">**Outlook safe sender and blocked sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="ad51d-131">這可讓使用者針對個別使用者或個別網域，管理他們自己的安全寄件者和封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="ad51d-131">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span>

  - <span data-ttu-id="ad51d-132">**目錄架構邊緣封鎖（DBEB）**：如需 DBEB 的詳細資訊，請參閱[使用目錄架構邊緣封鎖以拒絕傳送至無效收件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)者的郵件。</span><span class="sxs-lookup"><span data-stu-id="ad51d-132">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="ad51d-133">**使用者垃圾郵件隔離**：若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。</span><span class="sxs-lookup"><span data-stu-id="ad51d-133">**End user spam quarantine**: In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="ad51d-134">保護內部部署信箱的 EOP 客戶必須是有效的電子郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="ad51d-134">EOP customers protecting on-premises mailboxes must be valid email users.</span></span>

  - <span data-ttu-id="ad51d-135">**郵件流程規則**：當您使用目錄同步處理時，您現有的 Active directory 使用者和群組會自動上傳至雲端，然後您可以建立郵件流程規則（也稱為傳輸規則），該規則會以特定使用者和/或群組為目標，而不需要透過 EAC 或 Exchange Online Protection PowerShell 手動新增。</span><span class="sxs-lookup"><span data-stu-id="ad51d-135">**Mail flow rules**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="ad51d-136">請注意， [動態通訊群組](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)無法透過目錄同步作業進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="ad51d-136">Note that [dynamic distribution groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="ad51d-137">取得必要的許可權並準備目錄同步處理，如[與 Azure Active directory 混合身分識別的功能](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)所述。</span><span class="sxs-lookup"><span data-stu-id="ad51d-137">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="ad51d-138">使用 Azure Active Directory Connect （AAD 連接）同步使用者目錄</span><span class="sxs-lookup"><span data-stu-id="ad51d-138">To synchronize user directories with Azure Active Directory Connect (AAD Connect)</span></span>

<span data-ttu-id="ad51d-139">若要將使用者同步處理至 Azure Active Directory （AAD），您必須先**啟用目錄同步**處理，如[Azure AD Connect 同步中所述：瞭解和自訂同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)處理。</span><span class="sxs-lookup"><span data-stu-id="ad51d-139">To synchronize users to Azure Active Directory (AAD) you first have to **activate directory synchronization**, as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="ad51d-140">接下來是安裝和設定內部部署電腦的安裝及設定，以執行 AAD 連線（如果您還沒有必要的預先檢查的話）。</span><span class="sxs-lookup"><span data-stu-id="ad51d-140">Next is the installation and configuration of an on-premises computer to run AAD Connect (if you don't already have one -- something worth checking ahead of time).</span></span> <span data-ttu-id="ad51d-141">[設定 Aad connect，直通方法](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)會告訴您如何設定您的帳戶，並將您的帳戶從內部部署與使用 AAD Connect 的 Azure AD 同步處理。</span><span class="sxs-lookup"><span data-stu-id="ad51d-141">The [Setting up AAD Connect, the express way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) topic tells you how to setup and synchronize your accounts from on-premises to Azure AD with AAD Connect.</span></span>

<span data-ttu-id="ad51d-142">但在執行這項作業之前，請確定[您符合必要條件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)，然後[選擇安裝類型](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)。</span><span class="sxs-lookup"><span data-stu-id="ad51d-142">But before you do that work, make certain [you meet prerequisites](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), and [choose your installation type](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span></span> <span data-ttu-id="ad51d-143">較舊的連結是快速安裝的簡短文章。</span><span class="sxs-lookup"><span data-stu-id="ad51d-143">The earlier link is to a short article for express installs.</span></span> <span data-ttu-id="ad51d-144">您也可以在 [[自訂安裝](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)] 或 [必要時[傳遞驗證](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)] 中尋找文章。</span><span class="sxs-lookup"><span data-stu-id="ad51d-144">You can also find articles on [custom installations](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom), or [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) if they're needed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad51d-p113">完成 Azure Active Directory 同步處理工具設定精靈 之後，您的 Active Directory 樹系中會建立 **MSOL_AD_SYNC** 帳戶。此帳戶將用來讀取和同步處理您的內部部署 Active Directory 資訊。為了讓目錄同步作業能夠正確運作，請確定有開啟您的本機目錄同步作業伺服器上的 TCP 443。</span><span class="sxs-lookup"><span data-stu-id="ad51d-p113">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="ad51d-148">在設定同步處理之後，請務必確認 EOP 已正確地進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="ad51d-148">After configuring your sync, be sure to verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="ad51d-149">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span><span class="sxs-lookup"><span data-stu-id="ad51d-149">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>

## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="ad51d-150">使用 EAC 管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="ad51d-150">Use the EAC to manage mail users</span></span>

<span data-ttu-id="ad51d-151">本節提供直接在 EAC 中新增及管理電子郵件使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad51d-151">This section provides information about adding and managing email users directly in the EAC.</span></span>

### <a name="use-the-eac-to-add-a-mail-user"></a><span data-ttu-id="ad51d-152">使用 EAC 新增郵件使用者</span><span class="sxs-lookup"><span data-stu-id="ad51d-152">Use the EAC to add a mail user</span></span>

1. <span data-ttu-id="ad51d-153">移至 EAC 中的 [ **收件者**] \> [ **連絡人**]，然後按一下 [ **新增 +**]，以建立電子郵件使用者。</span><span class="sxs-lookup"><span data-stu-id="ad51d-153">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>

2. <span data-ttu-id="ad51d-154">在 [ **新增郵件使用者**] 頁面上，輸入使用者的資訊，包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="ad51d-154">On the **New mail user** page, enter the user's information, including the following:</span></span>

   ****

   |<span data-ttu-id="ad51d-155">**郵件使用者內容**</span><span class="sxs-lookup"><span data-stu-id="ad51d-155">**Mail user property**</span></span>|<span data-ttu-id="ad51d-156">**描述**</span><span class="sxs-lookup"><span data-stu-id="ad51d-156">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="ad51d-157">**名字**、 **縮寫**和 **姓氏**</span><span class="sxs-lookup"><span data-stu-id="ad51d-157">**First name**, **Initials**, and **Last name**</span></span>|<span data-ttu-id="ad51d-158">在適當的方塊中輸入使用者的完整名稱。</span><span class="sxs-lookup"><span data-stu-id="ad51d-158">Type the user's full name in the appropriate boxes.</span></span>|
   |<span data-ttu-id="ad51d-159">**顯示名稱**</span><span class="sxs-lookup"><span data-stu-id="ad51d-159">**Display name**</span></span>|<span data-ttu-id="ad51d-p115">輸入名稱，最多 64 個字元。根據預設，此方塊會顯示 [**名字**]、[**縮寫**] 和 [**姓氏**] 方塊中的名稱 (如果有的話)。顯示名稱是必要項目。  </span><span class="sxs-lookup"><span data-stu-id="ad51d-p115">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.</span></span>|
   |<span data-ttu-id="ad51d-163">**別名**</span><span class="sxs-lookup"><span data-stu-id="ad51d-163">**Alias**</span></span>|<span data-ttu-id="ad51d-p116">輸入使用者的唯一別名，最多 64 個字元。別名是必要項目。</span><span class="sxs-lookup"><span data-stu-id="ad51d-p116">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>|
   |<span data-ttu-id="ad51d-166">**外部電子郵件地址**</span><span class="sxs-lookup"><span data-stu-id="ad51d-166">**External email address**</span></span>|<span data-ttu-id="ad51d-167">輸入使用者的外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ad51d-167">Type the external email address of the user.</span></span>|
   |<span data-ttu-id="ad51d-168">**使用者識別碼**</span><span class="sxs-lookup"><span data-stu-id="ad51d-168">**User id**</span></span>|<span data-ttu-id="ad51d-p117">輸入郵件使用者將用來登入服務的名稱。使用者登入名稱由 @ 符號左側的使用者名稱和右側的尾碼所組成。一般來說，尾碼是使用者帳戶所在的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="ad51d-p117">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>|
   |<span data-ttu-id="ad51d-172">**新密碼**</span><span class="sxs-lookup"><span data-stu-id="ad51d-172">**New password**</span></span>|<span data-ttu-id="ad51d-p118">輸入郵件使用者將用來登入服務的密碼。請確定您提供的密碼符合您正在其中建立使用者帳戶之網域的密碼長度、複雜性和歷程記錄需求。</span><span class="sxs-lookup"><span data-stu-id="ad51d-p118">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>|
   |<span data-ttu-id="ad51d-175">**確認密碼**</span><span class="sxs-lookup"><span data-stu-id="ad51d-175">**Confirm password**</span></span>|<span data-ttu-id="ad51d-176">重新輸入密碼加以確認。</span><span class="sxs-lookup"><span data-stu-id="ad51d-176">Retype the password to confirm it.</span></span>|

3. <span data-ttu-id="ad51d-p119">按一下 [ **儲存**]，以建立新的郵件使用者。新的使用者應會出現在使用者清單中。</span><span class="sxs-lookup"><span data-stu-id="ad51d-p119">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span>

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a><span data-ttu-id="ad51d-179">使用 EAC 來編輯或移除郵件使用者</span><span class="sxs-lookup"><span data-stu-id="ad51d-179">Use the EAC to edit or remove a mail user</span></span>

- <span data-ttu-id="ad51d-180">In the EAC, go to **Recipients** \> **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="ad51d-180">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="ad51d-181">在使用者清單中，按一下您要查看或變更的使用者，然後選取 [**編輯** ![編輯圖示](../../media/ITPro-EAC-EditIcon.gif) ] 以根據需要更新使用者設定。</span><span class="sxs-lookup"><span data-stu-id="ad51d-181">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="ad51d-182">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span><span class="sxs-lookup"><span data-stu-id="ad51d-182">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="ad51d-183">您也可以選取使用者，然後選擇 [**移除** ![移除]](../../media/ITPro-EAC-RemoveIcon.gif)圖示加以刪除。</span><span class="sxs-lookup"><span data-stu-id="ad51d-183">You can also select a user and then choose **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span>

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a><span data-ttu-id="ad51d-184">使用 Exchange Online Protection PowerShell 管理郵件使用者</span><span class="sxs-lookup"><span data-stu-id="ad51d-184">Use Exchange Online Protection PowerShell to manage mail users</span></span>

<span data-ttu-id="ad51d-185">本節提供使用遠端 Windows PowerShell 來新增和管理郵件使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad51d-185">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>

### <a name="use-eop-powershell-to-add-a-mail-user"></a><span data-ttu-id="ad51d-186">使用 EOP PowerShell 新增郵件使用者</span><span class="sxs-lookup"><span data-stu-id="ad51d-186">Use EOP PowerShell to add a mail user</span></span>

<span data-ttu-id="ad51d-187">此範例使用 [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) 在 EOP 中為 Jeffrey Zeng 建立具有郵件功能的使用者帳戶，詳細資料如下：</span><span class="sxs-lookup"><span data-stu-id="ad51d-187">This example uses the [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span>

- <span data-ttu-id="ad51d-188">名字為 Jeffrey，姓氏為 Zeng。</span><span class="sxs-lookup"><span data-stu-id="ad51d-188">The first name is Jeffrey and the last name is Zeng.</span></span>

- <span data-ttu-id="ad51d-189">名稱是 Jeffrey，而顯示名稱是 Jeffrey Zeng。</span><span class="sxs-lookup"><span data-stu-id="ad51d-189">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>

- <span data-ttu-id="ad51d-190">別名為 jeffreyz。</span><span class="sxs-lookup"><span data-stu-id="ad51d-190">The alias is jeffreyz.</span></span>

- <span data-ttu-id="ad51d-191">外部電子郵件地址為 jzeng@tailspintoys.com。</span><span class="sxs-lookup"><span data-stu-id="ad51d-191">The external email address is jzeng@tailspintoys.com.</span></span>

- <span data-ttu-id="ad51d-192">Office 365 登入名稱是 jeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ad51d-192">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>

- <span data-ttu-id="ad51d-193">密碼為 Pa$$word1。</span><span class="sxs-lookup"><span data-stu-id="ad51d-193">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

<span data-ttu-id="ad51d-194">若要確認這是否正常運作，請執行下列命令，以顯示新郵件使用者 Jeffrey Zeng 的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="ad51d-194">To verify that this worked, run the following command to display information about new mail user Jeffrey Zeng:</span></span>

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

<span data-ttu-id="ad51d-195">如需詳細的語法及參數資訊，請參閱[Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)。</span><span class="sxs-lookup"><span data-stu-id="ad51d-195">For detailed syntax and parameter information, see [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span></span>

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a><span data-ttu-id="ad51d-196">使用 EOP PowerShell 編輯郵件使用者的屬性</span><span class="sxs-lookup"><span data-stu-id="ad51d-196">Use EOP PowerShell to edit the properties of a mail user</span></span>

<span data-ttu-id="ad51d-197">使用 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) 和 [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) 指令程式來檢視或變更郵件使用者的屬性。</span><span class="sxs-lookup"><span data-stu-id="ad51d-197">Use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) cmdlets to view or change properties for mail users.</span></span>

<span data-ttu-id="ad51d-198">此範例會設定 Pilar Pinilla 的外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ad51d-198">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="ad51d-199">此範例會將所有郵件使用者的 [公司] 內容設定為 [Contoso]。</span><span class="sxs-lookup"><span data-stu-id="ad51d-199">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="ad51d-200">若要確認這是否正常運作，請使用[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) Cmdlet 來驗證變更。</span><span class="sxs-lookup"><span data-stu-id="ad51d-200">To verify that this worked, use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify the changes.</span></span> <span data-ttu-id="ad51d-201">（請注意，您可以為多個郵件連絡人查看多個屬性。）</span><span class="sxs-lookup"><span data-stu-id="ad51d-201">(Note that you can view multiple properties for multiple mail contacts.)</span></span>

```PowerShell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

<span data-ttu-id="ad51d-202">在上述範例中，所有郵件使用者的 [公司] 屬性設為 [Contoso]，請執行下列命令來驗證變更：</span><span class="sxs-lookup"><span data-stu-id="ad51d-202">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>

```PowerShell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="ad51d-203">此指令程式採用批次處理方法，因此導致幾分鐘的傳播延遲，然後才能看到指令程式的結果。</span><span class="sxs-lookup"><span data-stu-id="ad51d-203">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>

### <a name="use-eop-powershell-to-remove-a-mail-user"></a><span data-ttu-id="ad51d-204">使用 EOP PowerShell 移除郵件使用者</span><span class="sxs-lookup"><span data-stu-id="ad51d-204">Use EOP PowerShell to remove a mail user</span></span>

<span data-ttu-id="ad51d-205">此範例使用 [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) 指令程式來刪除使用者 Jeffrey Zeng：</span><span class="sxs-lookup"><span data-stu-id="ad51d-205">This example uses the [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) cmdlet to delete user Jeffrey Zeng:</span></span>

```PowerShell
Remove-EOPMailUser -Identity Jeffrey
```
<span data-ttu-id="ad51d-206">若要確認這是否正常運作，請執行[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) Cmdlet，以確認郵件使用者已不存在。</span><span class="sxs-lookup"><span data-stu-id="ad51d-206">To verify that this worked, run the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify that the mail user no longer exists.</span></span>

```PowerShell
Get-Recipient Jeffrey | Format-List
```
