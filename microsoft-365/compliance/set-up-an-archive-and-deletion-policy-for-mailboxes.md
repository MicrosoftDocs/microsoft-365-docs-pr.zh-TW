---
title: 設定組織中的信箱封存和刪除原則
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
ms.custom: seo-marvel-apr2020
description: 瞭解如何在 Microsoft 365 中建立封存和刪除原則，以自動將專案移至使用者的封存信箱。
ms.openlocfilehash: ae48335203968b25a00fda61bfe65ffde85649ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919529"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a><span data-ttu-id="e41b9-103">設定組織中的信箱封存和刪除原則</span><span class="sxs-lookup"><span data-stu-id="e41b9-103">Set up an archive and deletion policy for mailboxes in your organization</span></span>

<span data-ttu-id="e41b9-104">在 Microsoft 365 中，系統管理員可以建立封存和刪除原則，以自動將專案移至使用者的封存信箱，並自動刪除信箱中的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-104">In Microsoft 365, admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span> <span data-ttu-id="e41b9-105">系統管理員會建立指派給信箱的保留原則，並在一段時間後將專案移至使用者的封存信箱，並在達到特定保留時限後，刪除信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="e41b9-105">The admin does this by creating a retention policy that's assigned to mailboxes, and moves items to a user's archive mailbox after a certain period of time and that also deletes items from the mailbox after they reach a certain age limit.</span></span> <span data-ttu-id="e41b9-106">決定要移動或刪除哪些專案，以及發生該問題的實際規則稱為保留標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-106">The actual rules that determine what items are moved or deleted and when that happens are called retention tags.</span></span> <span data-ttu-id="e41b9-107">保留標記會連結到保留原則，而該保留原則又會指派給使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-107">Retention tags are linked to a retention policy, that in turn is assigned to a user's mailbox.</span></span> <span data-ttu-id="e41b9-108">保留標記會將保留設定套用至使用者信箱中的個別郵件和資料夾。</span><span class="sxs-lookup"><span data-stu-id="e41b9-108">A retention tag applies retention settings to individual messages and folders in a user's mailbox.</span></span> <span data-ttu-id="e41b9-109">它會定義郵件保留在信箱中的時間長度，以及當郵件達到指定的保留時間時採取的動作。</span><span class="sxs-lookup"><span data-stu-id="e41b9-109">It defines how long a message remains in the mailbox and what action is taken when the message reaches the specified retention age.</span></span> <span data-ttu-id="e41b9-110">當郵件到達保留天數時，它會移至使用者的封存信箱，或已被刪除。</span><span class="sxs-lookup"><span data-stu-id="e41b9-110">When a message reaches its retention age, it's either moved to the user's archive mailbox or it's deleted.</span></span>
  
<span data-ttu-id="e41b9-111">本文中的步驟會針對名為高山房屋的虛擬組織，設定封存和保留原則。</span><span class="sxs-lookup"><span data-stu-id="e41b9-111">The steps in this article will set up an archiving and retention policy for a fictitious organization named Alpine House.</span></span> <span data-ttu-id="e41b9-112">設定此原則包含下列工作：</span><span class="sxs-lookup"><span data-stu-id="e41b9-112">Setting up this policy includes the following tasks:</span></span>
  
- <span data-ttu-id="e41b9-113">為組織中的每位使用者啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-113">Enabling an archive mailbox for every user in the organization.</span></span> <span data-ttu-id="e41b9-114">這為使用者提供額外的信箱儲存空間，而且必須讓保留原則能夠將專案移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-114">This gives users additional mailbox storage, and is required so that a retention policy can move items to the archive mailbox.</span></span> <span data-ttu-id="e41b9-115">它也可讓使用者將專案移至封存信箱，以儲存封存資訊。</span><span class="sxs-lookup"><span data-stu-id="e41b9-115">It also lets a user store archival information by moving items to their archive mailbox.</span></span>

- <span data-ttu-id="e41b9-116">建立三個執行下列動作的自訂保留標記：</span><span class="sxs-lookup"><span data-stu-id="e41b9-116">Creating three custom retention tags that do the following:</span></span>

  - <span data-ttu-id="e41b9-117">自動將3年以前的專案移至使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-117">Automatically moves items that are 3 years old to the user's archive mailbox.</span></span> <span data-ttu-id="e41b9-118">將專案移至封存信箱可釋放使用者主要信箱中的空間。</span><span class="sxs-lookup"><span data-stu-id="e41b9-118">Moving items to the archive mailbox frees up space in a user's primary mailbox.</span></span>

  - <span data-ttu-id="e41b9-119">會自動從 [刪除的郵件] 資料夾中刪除5年以前的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-119">Automatically deletes items that are 5 years old from the Deleted Items folder.</span></span> <span data-ttu-id="e41b9-120">這樣也可釋放使用者主要信箱中的空間。</span><span class="sxs-lookup"><span data-stu-id="e41b9-120">This also frees up space in the user's primary mailbox.</span></span> <span data-ttu-id="e41b9-121">若有必要，使用者將有機會復原這些專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-121">User's will have the opportunity to recover these items if necessary.</span></span> <span data-ttu-id="e41b9-122">如需詳細資訊，請參閱 [more information](#more-information) 一節中的註腳。</span><span class="sxs-lookup"><span data-stu-id="e41b9-122">See the footnote in the [More information](#more-information) section for more details.</span></span> 

  - <span data-ttu-id="e41b9-123">自動 (和永久) 會從主要和封存信箱中刪除7年以前的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-123">Automatically (and permanently) deletes items that are 7 years old from both the primary and archive mailbox.</span></span> <span data-ttu-id="e41b9-124">由於法規遵從性規定，某些組織必須在一段時間內保留電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e41b9-124">Because of compliance regulations, some organization's are required to retain email for a certain period of time.</span></span> <span data-ttu-id="e41b9-125">這個時段到期後，組織可能會想要永久移除這些專案使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-125">After this time period expires, an organization might want to permanently remove these items user mailboxes.</span></span>

- <span data-ttu-id="e41b9-126">建立新的保留原則，並將新的自訂保留標記新增至其中。</span><span class="sxs-lookup"><span data-stu-id="e41b9-126">Creating a new retention policy and adding the new custom retention tags to it.</span></span> <span data-ttu-id="e41b9-127">此外，您也會將內建保留標記新增至新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="e41b9-127">Additionally, you'll also add built-in retention tags to the new retention policy.</span></span> <span data-ttu-id="e41b9-128">這包括使用者可指派給其信箱中的專案的個人標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-128">This includes personal tags that users can assign to items in their mailbox.</span></span> <span data-ttu-id="e41b9-129">您也會新增保留標記，將使用者主要信箱中 [可復原的專案] 資料夾中的專案，移至其封存信箱中的 [可復原的專案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e41b9-129">You'll also add a retention tag that moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="e41b9-130">這有助於在使用者的信箱處於保留狀態時，釋放使用者的 [可復原的專案] 資料夾中的空間。</span><span class="sxs-lookup"><span data-stu-id="e41b9-130">This helps free up space in a user's Recoverable Items folder when their mailbox is placed on hold.</span></span>

<span data-ttu-id="e41b9-131">您可以遵循本文中的部分或所有步驟，為您自己組織中的信箱設定封存和刪除原則。</span><span class="sxs-lookup"><span data-stu-id="e41b9-131">You can follow some or all of the steps in this article to set up an archive and deletion policy for mailboxes in your own organization.</span></span> <span data-ttu-id="e41b9-132">建議您先在一些信箱上測試此程式，然後再對組織中的所有信箱執行這項程式。</span><span class="sxs-lookup"><span data-stu-id="e41b9-132">We recommend that you test this process on a few mailboxes before implementing it on all mailboxes in your organization.</span></span>
  
## <a name="before-you-set-up-an-archive-and-deletion-policy"></a><span data-ttu-id="e41b9-133">在您設定封存與刪除原則之前</span><span class="sxs-lookup"><span data-stu-id="e41b9-133">Before you set up an archive and deletion policy</span></span>

- <span data-ttu-id="e41b9-134">您必須是組織中的全域系統管理員，才可執行本主題中的步驟。</span><span class="sxs-lookup"><span data-stu-id="e41b9-134">You have to be a global administrator in your organization to perform the steps in this topic.</span></span> 

- <span data-ttu-id="e41b9-135">當您建立新的使用者帳戶，並將 Exchange Online 授權指派給使用者時，會自動為使用者建立信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-135">When you create a new user account and assign the user an Exchange Online license, a mailbox is automatically created for the user.</span></span> <span data-ttu-id="e41b9-136">建立信箱時，會自動將其指派為預設保留原則，名稱為 [預設 MRM 原則]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-136">When the mailbox is created, it's automatically assigned a default retention policy, named Default MRM Policy.</span></span> <span data-ttu-id="e41b9-137">在本文中，您將建立新的保留原則，然後將其指派給使用者信箱，取代預設的 MRM 原則。</span><span class="sxs-lookup"><span data-stu-id="e41b9-137">In this article, you will create a new retention policy and then assign it to user mailboxes, replacing the Default MRM policy.</span></span> <span data-ttu-id="e41b9-138">一個信箱一次只能有一個指派給它的保留原則。</span><span class="sxs-lookup"><span data-stu-id="e41b9-138">A mailbox can have only one retention policy assigned to it at any one time.</span></span>

- <span data-ttu-id="e41b9-139">若要深入瞭解 Exchange Online 中的保留標記和保留原則，請參閱[保留標記和保留原則](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)。</span><span class="sxs-lookup"><span data-stu-id="e41b9-139">To learn more about retention tags and retention policies in Exchange Online, see [Retention tags and retention policies](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies).</span></span>

## <a name="step-1-enable-archive-mailboxes-for-users"></a><span data-ttu-id="e41b9-140">步驟1：啟用使用者的封存信箱</span><span class="sxs-lookup"><span data-stu-id="e41b9-140">Step 1: Enable archive mailboxes for users</span></span>

<span data-ttu-id="e41b9-141">第一步是為組織中的每位使用者啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-141">The first step is to enable the archive mailbox for each user in your organization.</span></span> <span data-ttu-id="e41b9-142">必須啟用使用者的封存信箱，這樣，具有「移至封存」保留動作的保留標記可以在保留天數到期後移動專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-142">A user's archive mailbox has to be enabled so that a retention tag with a "Move to Archive" retention action can move the item after the retention age expires.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e41b9-143">在此程式中，您可以隨時啟用封存信箱，只要在您完成此程式之前已經啟用封存信箱即可。</span><span class="sxs-lookup"><span data-stu-id="e41b9-143">You can enable archive mailboxes any time during this process, just as long as they're enabled at some point before you complete the process.</span></span> <span data-ttu-id="e41b9-144">如果未啟用封存信箱，則不會對任何已指派封存或刪除原則的專案採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="e41b9-144">If an archive mailbox isn't enabled, no action is taken on any items that have an archive or deletion policy assigned to it.</span></span>
  
1. <span data-ttu-id="e41b9-145">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e41b9-145">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="e41b9-146">使用您的全域系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="e41b9-146">Sign in using your global administrator account.</span></span>
    
3. <span data-ttu-id="e41b9-147">在 [安全性 & 規範中心] 中，移至 [ **資訊管理**] 封存 \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e41b9-147">In the Security & Compliance Center, go to **Information governance** \> **Archive**.</span></span>

    <span data-ttu-id="e41b9-148">您組織中的信箱清單會顯示，以及對應的封存信箱是啟用還是停用。</span><span class="sxs-lookup"><span data-stu-id="e41b9-148">A list of the mailboxes in your organization is displayed and whether the corresponding archive mailbox is enabled or disabled.</span></span>

4. <span data-ttu-id="e41b9-149">按一下清單中的第一個信箱，按住 **Shift** 鍵，然後按一下清單中的最後一個，以選取所有信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-149">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span>

    > [!TIP]
    > <span data-ttu-id="e41b9-150">這個步驟假設未啟用任何封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-150">This step assumes that no archive mailboxes are enabled.</span></span> <span data-ttu-id="e41b9-151">如果您有任何信箱啟用封存，請按住 **Ctrl** 鍵，然後按一下每個具有已停用封存信箱的信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-151">If you have any mailboxes with the archive enabled, hold down the **Ctrl** key and click each mailbox that has a disabled archive mailbox.</span></span> <span data-ttu-id="e41b9-152">或者，您可以按一下 [封存 **信箱** ] 欄標頭，根據是否已啟用或停用封存信箱，來排序列，以簡化選取信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-152">Or you can click the **Archive mailbox** column header to sort the rows based on whether the archive mailbox is enabled or disabled to make it easier to select mailboxes.</span></span>
  
5. <span data-ttu-id="e41b9-153">在 [詳細資料] 窗格的 [ **大量編輯**] 下，按一下 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-153">In the details pane, under **Bulk Edit**, click **Enable**.</span></span>

    <span data-ttu-id="e41b9-154">隨即顯示一則警告，指出超過兩年的專案會移至新的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-154">A warning is displayed saying that items that are older than two years will be moved to the new archive mailbox.</span></span> <span data-ttu-id="e41b9-155">這是因為建立新使用者信箱的預設保留原則，具有保留天數為2年的封存預設原則標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-155">This is because the default retention policy that's assigned a new user mailbox when it's created has an archive default policy tag that has a retention age of 2 years.</span></span> <span data-ttu-id="e41b9-156">您將在步驟2中建立的自訂封存預設原則標記的保留天數為3年。</span><span class="sxs-lookup"><span data-stu-id="e41b9-156">The custom archive default policy tag that you'll create in Step 2 has a retention age of 3 years.</span></span> <span data-ttu-id="e41b9-157">這表示3年或更舊的專案會移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-157">That means items that are 3 years or older will be moved to the archive mailbox.</span></span>

6. <span data-ttu-id="e41b9-158">按一下 **[是]** 以關閉警告訊息，並啟動此程式以啟用每個所選信箱的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-158">Click **Yes** to close the warning message and start the process to enable the archive mailbox for each selected mailbox.</span></span>

7. <span data-ttu-id="e41b9-159">當程式完成時 **，按一下**[重新整理] ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) 以更新 [封存] 頁面上的清單。</span><span class="sxs-lookup"><span data-stu-id="e41b9-159">When the process is complete, click **Refresh** ![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the list on the **Archive** page.</span></span>

    <span data-ttu-id="e41b9-160">組織中的所有使用者都可以啟用封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-160">The archive mailbox is enabled for all user's in your organization.</span></span>

    ![已啟用封存信箱的信箱清單](../media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a><span data-ttu-id="e41b9-162">步驟2：建立封存和刪除原則的新保留標記</span><span class="sxs-lookup"><span data-stu-id="e41b9-162">Step 2: Create new retention tags for the archive and deletion policies</span></span>

<span data-ttu-id="e41b9-163">在這個步驟中，您將建立先前所述的三個自訂保留標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-163">In this step, you'll create the three custom retention tags that were previously described.</span></span>
  
- <span data-ttu-id="e41b9-164">高山房屋3年移至封存 (自訂封存原則) </span><span class="sxs-lookup"><span data-stu-id="e41b9-164">Alpine House 3 Year Move to Archive (custom archive policy)</span></span>

- <span data-ttu-id="e41b9-165">高山房屋7年會永久刪除 (自訂刪除原則) </span><span class="sxs-lookup"><span data-stu-id="e41b9-165">Alpine House 7 Year Permanently Delete (custom deletion policy)</span></span>

- <span data-ttu-id="e41b9-166">高山房屋刪除的郵件5年刪除並允許復原 (自訂標籤的 [刪除的郵件] 資料夾) </span><span class="sxs-lookup"><span data-stu-id="e41b9-166">Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)</span></span>

<span data-ttu-id="e41b9-167">若要建立新的保留標記，您可以使用 Exchange Online 組織中 (EAC) 的 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="e41b9-167">To create new retention tags, you'll use the Exchange admin center (EAC) in your Exchange Online organization.</span></span> <span data-ttu-id="e41b9-168">請務必使用 EAC 的傳統型版本。</span><span class="sxs-lookup"><span data-stu-id="e41b9-168">Be sure to use the classic version of the EAC.</span></span>
  
1. <span data-ttu-id="e41b9-169">移至 [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) 並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="e41b9-169">Go to [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) and sign in using your credentials.</span></span>
  
2. <span data-ttu-id="e41b9-170">在 EAC 中，移至 [**規範管理**] [  >  **保留標記**]</span><span class="sxs-lookup"><span data-stu-id="e41b9-170">In the EAC, go to **Compliance management** > **Retention tags**</span></span>

    <span data-ttu-id="e41b9-171">隨即會顯示您組織的保留標記清單。</span><span class="sxs-lookup"><span data-stu-id="e41b9-171">A list of the retention tags for your organization is displayed.</span></span>

### <a name="create-a-custom-archive-default-policy-tag"></a><span data-ttu-id="e41b9-172">建立自訂封存預設原則標記</span><span class="sxs-lookup"><span data-stu-id="e41b9-172">Create a custom archive default policy tag</span></span>
  
<span data-ttu-id="e41b9-173">首先，您會建立自訂封存預設原則標記， (DPT) 會在3年後將專案移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-173">First, you'll create a custom archive default policy tag (DPT) that will move items to the archive mailbox after 3 years.</span></span>
  
1. <span data-ttu-id="e41b9-174">在 [**保留標記**] 頁面上，按一下 [**新增標記**] [ ![ 新增圖示] ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) ，然後選取 [**自動套用至整個信箱 (預設)**]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-174">On the **Retention tags** page, click **New tag**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span>

2. <span data-ttu-id="e41b9-175">在 [ **自動套用至整個信箱的新標記] (預設)** ] 頁面上，完成下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="e41b9-175">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 

    ![設定建立新的封存預設原則標記](../media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
   1. <span data-ttu-id="e41b9-177">**名稱** 輸入新保留標記的名稱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-177">**Name** Type a name for the new retention tag.</span></span> 

   2. <span data-ttu-id="e41b9-178">**保留動作** 選取 [ **移至** 封存]，當保留期間到期時，將專案移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-178">**Retention action** Select **Move to Archive** to move items to the archive mailbox when the retention period expires.</span></span>

   3. <span data-ttu-id="e41b9-179">**保留期間** 選取 **專案何時到達下列時期 (天數)**]，然後輸入保留期間的持續時間。</span><span class="sxs-lookup"><span data-stu-id="e41b9-179">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="e41b9-180">在此案例中，會在1095天之後將專案移至封存信箱 (3 年) 。</span><span class="sxs-lookup"><span data-stu-id="e41b9-180">For this scenario, items will be moved to the archive mailbox after 1095 days (3 years).</span></span>

   4. <span data-ttu-id="e41b9-181">**Comment** (Optional) 輸入批註，以說明自訂保留標記的目的。</span><span class="sxs-lookup"><span data-stu-id="e41b9-181">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span>

3. <span data-ttu-id="e41b9-182">按一下 [ **儲存** ] 以建立自訂封存 DPT。</span><span class="sxs-lookup"><span data-stu-id="e41b9-182">Click **Save** to create the custom archive DPT.</span></span>

    <span data-ttu-id="e41b9-183">新的封存 DPT 會顯示在保留標記清單中。</span><span class="sxs-lookup"><span data-stu-id="e41b9-183">The new archive DPT is displayed in the list of retention tags.</span></span>

### <a name="create-a-custom-deletion-default-policy-tag"></a><span data-ttu-id="e41b9-184">建立自訂刪除預設原則標記</span><span class="sxs-lookup"><span data-stu-id="e41b9-184">Create a custom deletion default policy tag</span></span>
  
<span data-ttu-id="e41b9-185">接下來，您將建立另一個自訂 DPT，但這會是一個刪除原則，可在7年後永久刪除專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-185">Next, you'll create another custom DPT but this one will be a deletion policy that permanently deletes items after 7 years.</span></span>
  
1. <span data-ttu-id="e41b9-186">在 [**保留標記**] 頁面上，按一下 [**新增標記**] [ ![ 新增圖示] ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) ，然後選取 [**自動套用至整個信箱 (預設)**]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-186">On the **Retention tags** page, click **New tag**![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span>

2. <span data-ttu-id="e41b9-187">在 [ **自動套用至整個信箱的新標記] (預設)** ] 頁面上，完成下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="e41b9-187">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 

    ![設定以建立新的刪除預設原則標記](../media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
   1. <span data-ttu-id="e41b9-189">**名稱** 輸入新保留標記的名稱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-189">**Name** Type a name for the new retention tag.</span></span> 

   2. <span data-ttu-id="e41b9-190">**保留動作** 選取 [ **永久刪除** ]，當保留期間到期時，清除信箱中的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-190">**Retention action** Select **Permanently Delete** to purge items from the mailbox when the retention period expires.</span></span>

   3. <span data-ttu-id="e41b9-191">**保留期間** 選取 **專案何時到達下列時期 (天數)**]，然後輸入保留期間的持續時間。</span><span class="sxs-lookup"><span data-stu-id="e41b9-191">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="e41b9-192">在此案例中，會在2555天之後清除專案 (7 年) 。</span><span class="sxs-lookup"><span data-stu-id="e41b9-192">For this scenario, items will be purged after 2555 days (7 years).</span></span>

   4. <span data-ttu-id="e41b9-193">**Comment** (Optional) 輸入批註，以說明自訂保留標記的目的。</span><span class="sxs-lookup"><span data-stu-id="e41b9-193">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 

3. <span data-ttu-id="e41b9-194">按一下 [ **儲存** ] 以建立自訂刪除 DPT。</span><span class="sxs-lookup"><span data-stu-id="e41b9-194">Click **Save** to create the custom deletion DPT.</span></span> 

    <span data-ttu-id="e41b9-195">新的刪除 DPT 會顯示在保留標記清單中。</span><span class="sxs-lookup"><span data-stu-id="e41b9-195">The new deletion DPT is displayed in the list of retention tags.</span></span>

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a><span data-ttu-id="e41b9-196">為 [刪除的郵件] 資料夾建立自訂保留原則標記</span><span class="sxs-lookup"><span data-stu-id="e41b9-196">Create a custom retention policy tag for the Deleted Items folder</span></span>
  
<span data-ttu-id="e41b9-197">您將建立的最後一個保留標記是「刪除的郵件」資料夾 (RPT) 的自訂保留原則標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-197">The last retention tag that you'll create is a custom retention policy tag (RPT) for the Deleted Items folder.</span></span> <span data-ttu-id="e41b9-198">這個標記會在5年後刪除 [刪除的郵件] 資料夾中的專案，並在使用者可以使用 [復原刪除的郵件] 工具來復原專案時，提供復原週期。</span><span class="sxs-lookup"><span data-stu-id="e41b9-198">This tag will delete items in the Deleted Items folder after 5 years, and provides a recovery period when users can use the Recover Deleted Items tool to recover an item.</span></span>
  
1. <span data-ttu-id="e41b9-199">在 [ **保留標記** ] 頁面上，按一下 [ **新增標記**] [ ![ 新增圖示] ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) ，然後選取 [ **自動套用至預設資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-199">On the **Retention tags** page, click **New tag** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to a default folder**.</span></span>

2. <span data-ttu-id="e41b9-200">在 [ **自動套用至預設資料夾** ] 頁面上的 [新增標記] 中，完成下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="e41b9-200">On the **New tag applied automatically to a default folder** page, complete the following fields:</span></span>

    ![設定為 [刪除的郵件] 資料夾建立新的保留原則標記](../media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
   1. <span data-ttu-id="e41b9-202">**名稱** 輸入新保留標記的名稱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-202">**Name** Type a name for the new retention tag.</span></span> 

   2. <span data-ttu-id="e41b9-203">**將此標記套用至下列預設資料夾** 在下拉式清單中，選取 [ **刪除的專案**]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-203">**Apply this tag to the following default folder** In the drop-down list, select **Deleted Items**.</span></span>

   3. <span data-ttu-id="e41b9-204">**保留動作** 在保留期間到期時，選取 [ **刪除並允許** 復原] 刪除專案，但是允許使用者在已刪除專案的保留期間內復原已刪除的專案 (預設值為14天) 。</span><span class="sxs-lookup"><span data-stu-id="e41b9-204">**Retention action** Select **Delete and Allow Recovery** to delete items when the retention period expires, but allow users to recover a deleted item within the deleted item retention period (which by default is 14 days).</span></span>

   4. <span data-ttu-id="e41b9-205">**保留期間** 選取 **專案何時到達下列時期 (天數)**]，然後輸入保留期間的持續時間。</span><span class="sxs-lookup"><span data-stu-id="e41b9-205">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="e41b9-206">在此案例中，會在1825天之後刪除專案 (5 年) 。</span><span class="sxs-lookup"><span data-stu-id="e41b9-206">For this scenario, items will be deleted after 1825 days (5 years).</span></span>

   5. <span data-ttu-id="e41b9-207">**Comment** (Optional) 輸入批註，以說明自訂保留標記的目的。</span><span class="sxs-lookup"><span data-stu-id="e41b9-207">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 

3. <span data-ttu-id="e41b9-208">按一下 [ **儲存** ]，以建立「刪除的郵件」資料夾的自訂 RPT。</span><span class="sxs-lookup"><span data-stu-id="e41b9-208">Click **Save** to create the custom RPT for the Deleted Items folder.</span></span>

    <span data-ttu-id="e41b9-209">新的 RPT 會顯示在保留標記清單中。</span><span class="sxs-lookup"><span data-stu-id="e41b9-209">The new RPT is displayed in the list of retention tags.</span></span>

## <a name="step-3-create-a-new-retention-policy"></a><span data-ttu-id="e41b9-210">步驟3：建立新的保留原則</span><span class="sxs-lookup"><span data-stu-id="e41b9-210">Step 3: Create a new retention policy</span></span>

<span data-ttu-id="e41b9-211">在您建立自訂保留標記之後，下一步是建立新的保留原則，並新增保留標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-211">After you create the custom retention tags, the next step is to create a new retention policy and add the retention tags.</span></span> <span data-ttu-id="e41b9-212">您將新增您在步驟2中建立的三個自訂保留標記，以及第一個區段中所述的內建標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-212">You'll add the three custom retention tags that you created in Step 2, and the built-in tags that were mentioned in the first section.</span></span> <span data-ttu-id="e41b9-213">在步驟4中，您會將此新的保留原則指派給使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-213">In Step 4, you'll assign this new retention policy to user mailboxes.</span></span>
  
1. <span data-ttu-id="e41b9-214">在 EAC 中，移至 [**規範管理**] [  >  **保留原則**]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-214">In the EAC, go to **Compliance management** > **Retention policies**.</span></span>

2. <span data-ttu-id="e41b9-215">在 [ **保留原則** ] 頁面上，按一下 [ **新增** ![ 新圖示] ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) 。</span><span class="sxs-lookup"><span data-stu-id="e41b9-215">On the **Retention policies** page, click **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>

3. <span data-ttu-id="e41b9-216">在 [ **名稱** ] 方塊中，輸入新保留原則的名稱;例如， **高山房屋封存和刪除原則**。</span><span class="sxs-lookup"><span data-stu-id="e41b9-216">In the **Name** box, type a name for the new retention policy; for example, **Alpine House Archive and Deletion Policy**.</span></span>

4. <span data-ttu-id="e41b9-217">在 [ **保留標記**] 底下 \*\*，按一下 [\*\* ![ 新增圖示] ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) 。</span><span class="sxs-lookup"><span data-stu-id="e41b9-217">Under **Retention tags**, click **Add** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>

    <span data-ttu-id="e41b9-218">您組織中的保留標記清單隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="e41b9-218">A list of the retention tags in your organization is displayed.</span></span> <span data-ttu-id="e41b9-219">附注會顯示您在步驟2中建立的自訂標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-219">Note the custom tags that you created in Step 2 are displayed.</span></span>

5. <span data-ttu-id="e41b9-220">新增在下列螢幕擷取畫面中已反白顯示的9保留標記 (這些標記會在 [詳細資訊](#more-information) 區段) 中詳細說明。</span><span class="sxs-lookup"><span data-stu-id="e41b9-220">Add the 9 retention tags that are highlighted in the following screenshot (these tags are described in more detail in the [More information](#more-information) section).</span></span> <span data-ttu-id="e41b9-221">若要新增保留標記，請選取它，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-221">To add a retention tag, select it and then click **Add**.</span></span>

    ![將保留標記新增至新的保留原則](../media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > <span data-ttu-id="e41b9-223">您可以按住 **Ctrl** 鍵，然後按一下每個標記，以選取多個保留標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-223">You can select multiple retention tags by holding down the **Ctrl** key and then clicking each tag.</span></span> 
  
6. <span data-ttu-id="e41b9-224">在您新增保留標記之後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e41b9-224">After you've added the retention tags, click **OK**.</span></span>

7. <span data-ttu-id="e41b9-225">在 [ **新增保留原則** ] 頁面上，按一下 [ **儲存** ] 以建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="e41b9-225">On the **New retention policy** page, click **Save** to create the new policy.</span></span>

    <span data-ttu-id="e41b9-226">新的保留原則會顯示在清單中。</span><span class="sxs-lookup"><span data-stu-id="e41b9-226">The new retention policy is displayed in the list.</span></span> <span data-ttu-id="e41b9-227">選取它，以在詳細資料窗格中顯示與其連結的保留標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-227">Select it to display the retention tags linked to it in the details pane.</span></span>

    ![新的保留原則及連結的保留標記清單](../media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a><span data-ttu-id="e41b9-229">步驟4：將新的保留原則指派給使用者信箱</span><span class="sxs-lookup"><span data-stu-id="e41b9-229">Step 4: Assign the new retention policy to user mailboxes</span></span>

<span data-ttu-id="e41b9-230">建立新的信箱時，預設會指派名為「預設 MRM 原則」的保留原則。</span><span class="sxs-lookup"><span data-stu-id="e41b9-230">When a new mailbox is created, a retention policy named Default MRM policy is assigned to it by default.</span></span> <span data-ttu-id="e41b9-231">在這個步驟中，您將會取代此保留原則 (，因為信箱只會指派一個保留原則給它，) 方法是將您在步驟3中建立的新保留原則指派給組織中的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-231">In this step, you'll replace this retention policy (because a mailbox can have only one retention policy assigned to it) by assigning the new retention policy that you created in Step 3 to the user mailboxes in your organization.</span></span> <span data-ttu-id="e41b9-232">這個步驟假設您要將新的原則指派給組織中的所有信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-232">This step assumes that you'll assign the new policy to all mailboxes in your organization.</span></span>
  
1. <span data-ttu-id="e41b9-233">在 EAC 中，**移至 [** 收件者] [  >  **信箱**]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-233">In the EAC, go to **Recipients** > **Mailboxes**.</span></span>

    <span data-ttu-id="e41b9-234">隨即會顯示您組織中所有使用者信箱的清單。</span><span class="sxs-lookup"><span data-stu-id="e41b9-234">A list of all user mailboxes in your organization is displayed.</span></span>

2. <span data-ttu-id="e41b9-235">按一下清單中的第一個信箱，按住 **Shift** 鍵，然後按一下清單中的最後一個，以選取所有信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-235">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 

3. <span data-ttu-id="e41b9-236">在 EAC 右側的 [詳細資料] 窗格中，按一下 [ **大量編輯**] 下的 [ **其他選項**]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-236">In the details pane on the right side of the EAC, under **Bulk Edit**, click **More options**.</span></span>

4. <span data-ttu-id="e41b9-237">在 [保留原則] 下方，按一下 [更新]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-237">Under **Retention Policy**, click **Update**.</span></span>

5. <span data-ttu-id="e41b9-238">在 [ **大量指派保留原則** ] 頁面上，于 [ **選取保留原則** ] 下拉式清單中，選取您在步驟3中建立的保留原則;例如， **高山房屋封存和保留原則**。</span><span class="sxs-lookup"><span data-stu-id="e41b9-238">On the **Bulk assign retention policy** page, in the **Select the retention policy** drop-down list, select the retention policy that you created in Step 3; for example, **Alpine House Archive and Retention Policy**.</span></span>

6. <span data-ttu-id="e41b9-239">按一下 [ **儲存** ]，以儲存新的保留原則指派。</span><span class="sxs-lookup"><span data-stu-id="e41b9-239">Click **Save** to save the new retention policy assignment.</span></span>

7. <span data-ttu-id="e41b9-240">若要確認是否已將新的保留原則指派給信箱，您可以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="e41b9-240">To verify that the new retention policy was assigned to mailboxes, you can do the following:</span></span>

   1. <span data-ttu-id="e41b9-241">在 [ **信箱** ] 頁面上選取信箱，然後按一下 [ **編輯** ![ 編輯] ](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png) 。</span><span class="sxs-lookup"><span data-stu-id="e41b9-241">Select a mailbox on the **Mailboxes** page, and then click **Edit** ![Edit](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png).</span></span>

   2. <span data-ttu-id="e41b9-242">在選取之使用者的信箱屬性頁面上，按一下 [ **信箱功能**]。</span><span class="sxs-lookup"><span data-stu-id="e41b9-242">On the mailbox properties page for the selected user, click **Mailbox features**.</span></span>

   <span data-ttu-id="e41b9-243">指派給信箱的新原則名稱會顯示在 [ **保留原則** ] 下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="e41b9-243">The name of the new policy assigned to the mailbox is displayed in the **Retention policy** drop-down list.</span></span>

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a><span data-ttu-id="e41b9-244"> (選用) 步驟5：執行受管理的資料夾助理以套用新的設定</span><span class="sxs-lookup"><span data-stu-id="e41b9-244">(Optional) Step 5: Run the Managed Folder Assistant to apply the new settings</span></span>

<span data-ttu-id="e41b9-245">在步驟4中對信箱套用新的保留原則之後，最多可能需要7天的 Exchange Online，才能將新的保留設定套用至信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-245">After you apply the new retention policy to mailboxes in Step 4, it can take up to 7 days in Exchange Online for the new retention settings to be applied to the mailboxes.</span></span> <span data-ttu-id="e41b9-246">這是因為稱為「 *受管理的資料夾助理* 」的處理常式至少每隔7天處理一次信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-246">This is because a process called the *Managed Folder Assistant* processes mailboxes at least once every 7 days.</span></span> <span data-ttu-id="e41b9-247">您可以在 Exchange Online PowerShell 中執行 **Start-ManagedFolderAssistant** Cmdlet，強制執行此動作，而不是等待受管理的資料夾助理執行。</span><span class="sxs-lookup"><span data-stu-id="e41b9-247">Instead of waiting for the Managed Folder Assistant to run, you can force this to happen by running the **Start-ManagedFolderAssistant** cmdlet in Exchange Online PowerShell.</span></span>

 <span data-ttu-id="e41b9-248">**當您執行受管理的資料夾助理時會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="e41b9-248">**What happens when you run the Managed Folder Assistant?**</span></span> <span data-ttu-id="e41b9-249">它會檢查信箱中的專案，並決定是否服從保留原則，以套用保留原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="e41b9-249">It applies the settings in the retention policy by inspecting items in the mailbox and determining whether they're subject to retention.</span></span> <span data-ttu-id="e41b9-250">然後使用適當的保留標記來標記要保留的專案，然後對超過保留天數的專案採取指定的保留動作。</span><span class="sxs-lookup"><span data-stu-id="e41b9-250">It then stamps items subject to retention with the appropriate retention tag, and then takes the specified retention action on items past their retention age.</span></span>
  
<span data-ttu-id="e41b9-251">以下是連接至 Exchange Online PowerShell 的步驟，然後在組織中的每個信箱上執行受管理的資料夾助理。</span><span class="sxs-lookup"><span data-stu-id="e41b9-251">Here are the steps to connect to Exchange Online PowerShell, and then run the Managed Folder Assistant on every mailbox in your organization.</span></span>

1. <span data-ttu-id="e41b9-252">[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e41b9-252">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
2. <span data-ttu-id="e41b9-253">執行下列兩個命令，以啟動組織中所有使用者信箱的受管理的資料夾助理。</span><span class="sxs-lookup"><span data-stu-id="e41b9-253">Run the following two commands to start the Managed Folder Assistant for all user mailboxes in your organization.</span></span>

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

<span data-ttu-id="e41b9-254">這就對了！</span><span class="sxs-lookup"><span data-stu-id="e41b9-254">That's it!</span></span> <span data-ttu-id="e41b9-255">您已為高山房屋組織設定封存和刪除原則。</span><span class="sxs-lookup"><span data-stu-id="e41b9-255">You've set up an archive and deletion policy for the Alpine House organization.</span></span>

> [!NOTE]
> <span data-ttu-id="e41b9-256">如先前所述，受管理的資料夾助理每7天至少處理一次信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-256">As previously stated, the Managed Folder Assistant processes mailboxes at least once every 7 days.</span></span> <span data-ttu-id="e41b9-257">因此，受管理的資料夾助理可能會更頻繁地處理信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-257">So it's possible that a mailbox can be processed by the Managed Folder Assistant more frequently.</span></span> <span data-ttu-id="e41b9-258">此外，系統管理員無法預測下一次受管理的資料夾助理所處理的信箱，這是您可能想要手動執行它的原因之一。</span><span class="sxs-lookup"><span data-stu-id="e41b9-258">Also, admins can't predict the next time a mailbox is processed by the Managed Folder Assistant, which is one reason why you may want to run it manually.</span></span> <span data-ttu-id="e41b9-259">不過，如果您想要暫時防止受管理的資料夾助理將新的保留設定套用至信箱，您可以執行 `Set-Mailbox -ElcProcessingDisabled $true` 命令暫時停用受管理的資料夾助理處理信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-259">However, if you want to temporarily prevent the Managed Folder Assistant from applying the new retention settings to a mailbox, you can run the `Set-Mailbox -ElcProcessingDisabled $true` command to temporarily disable the the Managed Folder Assistant from processing a mailbox.</span></span> <span data-ttu-id="e41b9-260">若要重新啟用信箱的受管理的資料夾助理，請執行 `Set-Mailbox -ElcProcessingDisabled $false` 命令。</span><span class="sxs-lookup"><span data-stu-id="e41b9-260">To re-enable the Managed Folder Assistant for a mailbox, run the `Set-Mailbox -ElcProcessingDisabled $false` command.</span></span> <span data-ttu-id="e41b9-261">最後，如果信箱使用者有停用的帳戶，我們將不會處理該信箱的 [移動專案與封存] 動作。</span><span class="sxs-lookup"><span data-stu-id="e41b9-261">Finally, if a mailbox user has a disabled account, we will not process the move items to archive action for that mailbox.</span></span>
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a><span data-ttu-id="e41b9-262"> (選用) 步驟6：將新的保留原則設定為您組織的預設值</span><span class="sxs-lookup"><span data-stu-id="e41b9-262">(Optional) Step 6: Make the new retention policy the default for your organization</span></span>

<span data-ttu-id="e41b9-263">在步驟4中，您必須將新的保留原則指派給現有的信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-263">In Step 4, you have to assign the new retention policy to existing mailboxes.</span></span> <span data-ttu-id="e41b9-264">不過，您可以設定 Exchange Online，讓新的保留原則指派給未來建立的新信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-264">But you can configure Exchange Online so that the new retention policy is assigned to new mailboxes that are created in the future.</span></span> <span data-ttu-id="e41b9-265">您可以使用 Exchange Online PowerShell 來更新組織的預設信箱計畫。</span><span class="sxs-lookup"><span data-stu-id="e41b9-265">You do this by using Exchange Online PowerShell to update your organization's default mailbox plan.</span></span> <span data-ttu-id="e41b9-266">*信箱方案* 是一種範本，可自動設定新信箱的屬性。</span><span class="sxs-lookup"><span data-stu-id="e41b9-266">A *mailbox plan* is a template that automatically configures properties on new mailboxes.</span></span>  <span data-ttu-id="e41b9-267">在此選用的步驟中，您可以取代指派給信箱計畫的目前保留原則 (預設會使用您在步驟3中建立的保留原則) 預設的 MRM 原則。</span><span class="sxs-lookup"><span data-stu-id="e41b9-267">In this optional step, you can replace the current retention policy that's assigned to the mailbox plan (by default, the Default MRM Policy) with the retention policy that you created in Step 3.</span></span> <span data-ttu-id="e41b9-268">在您更新信箱計畫之後，新的保留原則將會指派給新的信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-268">After you update the mailbox plan, the new retention policy will be assigned to new mailboxes.</span></span>

1. <span data-ttu-id="e41b9-269">[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e41b9-269">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e41b9-270">執行下列命令，以顯示組織中信箱計畫的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e41b9-270">Run the following command to display information about the mailbox plans in your organization.</span></span>

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```

    <span data-ttu-id="e41b9-271">請注意設定為預設的信箱計畫。</span><span class="sxs-lookup"><span data-stu-id="e41b9-271">Note the mailbox plan that's set as the default.</span></span>

3. <span data-ttu-id="e41b9-272">執行下列命令以指派您在步驟3中建立的新保留原則 (例如， **高山房屋封存和保留原則**) 預設信箱計畫。</span><span class="sxs-lookup"><span data-stu-id="e41b9-272">Run the following command to assign the new retention policy that you created in Step 3 (for example, **Alpine House Archive and Retention Policy**) to the default mailbox plan.</span></span> <span data-ttu-id="e41b9-273">本範例假設預設信箱計畫的名稱是 **ExchangeOnlineEnterprise**。</span><span class="sxs-lookup"><span data-stu-id="e41b9-273">This example assumes the name of the default mailbox plan is **ExchangeOnlineEnterprise**.</span></span>

    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. <span data-ttu-id="e41b9-274">您可以在步驟2中重新執行命令，以驗證指派給預設信箱計畫的保留原則已變更。</span><span class="sxs-lookup"><span data-stu-id="e41b9-274">You can rerun the command in step 2 to verify that the retention policy assigned to the default mailbox plan was changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="e41b9-275">其他資訊</span><span class="sxs-lookup"><span data-stu-id="e41b9-275">More information</span></span>

- <span data-ttu-id="e41b9-276">保留存留期的計算方式？</span><span class="sxs-lookup"><span data-stu-id="e41b9-276">How is retention age calculated?</span></span> <span data-ttu-id="e41b9-277">信箱專案的保留天數會從傳遞日期或專案建立的日期開始計算，例如未傳送但由使用者建立的草稿郵件。</span><span class="sxs-lookup"><span data-stu-id="e41b9-277">The retention age of mailbox items is calculated from the date of delivery or the date of creation for items such as draft messages that aren't sent but are created by the user.</span></span> <span data-ttu-id="e41b9-278">當受管理的資料夾助理員處理信箱中的項目時，它會針對其保留標記具有 [刪除並允許復原] 或 [永久刪除] 保留動作的所有項目，加上開始日期和到期日的戳記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-278">When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action.</span></span> <span data-ttu-id="e41b9-279">具有封存標籤的專案會以移動日期標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-279">Items that have an archive tag are stamped with a move date.</span></span> 

- <span data-ttu-id="e41b9-280">下表提供使用本主題中的步驟所建立之每個保留標記的詳細資訊，其新增保留原則。</span><span class="sxs-lookup"><span data-stu-id="e41b9-280">The following table provides more information about each retention tag that is added to the custom retention policy that was created by following the steps in this topic.</span></span>

    | <span data-ttu-id="e41b9-281">保留標記</span><span class="sxs-lookup"><span data-stu-id="e41b9-281">Retention tag</span></span> | <span data-ttu-id="e41b9-282">這個標記的功能</span><span class="sxs-lookup"><span data-stu-id="e41b9-282">What this tag does</span></span> | <span data-ttu-id="e41b9-283">內建或自訂的？</span><span class="sxs-lookup"><span data-stu-id="e41b9-283">Built-in or custom?</span></span> | <span data-ttu-id="e41b9-284">類型</span><span class="sxs-lookup"><span data-stu-id="e41b9-284">Type</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e41b9-285">高山房屋3年移至封存</span><span class="sxs-lookup"><span data-stu-id="e41b9-285">Alpine House 3 Year Move to Archive</span></span>  <br/> |<span data-ttu-id="e41b9-286">將1095天的專案 (3 年中) 舊的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-286">Moves items that are 1095 days (3 years) old to the archive mailbox.</span></span>  <br/> |<span data-ttu-id="e41b9-287">自訂 (請參閱「 [步驟2：建立封存和刪除原則的新保留標記](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies) 」) </span><span class="sxs-lookup"><span data-stu-id="e41b9-287">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="e41b9-288">預設原則標記 (封存) ;這個標記會自動套用至整個信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-288">Default Policy Tag (archive); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="e41b9-289">高山房屋7年（永久刪除）</span><span class="sxs-lookup"><span data-stu-id="e41b9-289">Alpine House 7 Year Permanently Delete</span></span>  <br/> |<span data-ttu-id="e41b9-290">當主要信箱或封存信箱中的專案有七年後，永久刪除該信箱中的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-290">Permanently deletes items in the primary mailbox or the archive mailbox when they are 7 years old.</span></span>  <br/> |<span data-ttu-id="e41b9-291">自訂 (請參閱「 [步驟2：建立封存和刪除原則的新保留標記](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies) 」) </span><span class="sxs-lookup"><span data-stu-id="e41b9-291">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="e41b9-292"> (刪除的預設原則標記) ;這個標記會自動套用至整個信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-292">Default Policy Tag (deletion); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="e41b9-293">高山房屋刪除的專案5年刪除並允許復原</span><span class="sxs-lookup"><span data-stu-id="e41b9-293">Alpine House Deleted Items 5 Years Delete and Allow Recovery</span></span>  <br/> |<span data-ttu-id="e41b9-294">會刪除5歲的「刪除的郵件」資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-294">Deletes items from the Deleted Items folder that are 5 years old.</span></span> <span data-ttu-id="e41b9-295">使用者可在刪除後的14天內復原這些專案。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e41b9-295">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="e41b9-296">自訂 (請參閱「 [步驟2：建立封存和刪除原則的新保留標記](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies) 」) </span><span class="sxs-lookup"><span data-stu-id="e41b9-296">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="e41b9-297">) 中 (刪除專案的保留原則標記;這個標記會自動套用至 [刪除的郵件] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-297">Retention Policy Tag (Deleted Items); this tag is automatically applied to items in the Deleted items folder.</span></span>  <br/> |
    |<span data-ttu-id="e41b9-298">可復原的專案14天移至封存</span><span class="sxs-lookup"><span data-stu-id="e41b9-298">Recoverable Items 14 days Move to Archive</span></span>  <br/> |<span data-ttu-id="e41b9-299">將 [可復原的專案] 資料夾中的專案，移至封存信箱中的 [可復原的專案] 資料夾14天。</span><span class="sxs-lookup"><span data-stu-id="e41b9-299">Moves items that have been in the Recoverable Items folder for 14 days to the Recoverable Items folder in the archive mailbox.</span></span>  <br/> |<span data-ttu-id="e41b9-300">內建</span><span class="sxs-lookup"><span data-stu-id="e41b9-300">Built-in</span></span>  <br/> |<span data-ttu-id="e41b9-301">) 的可復原專案 (保留原則標記;這個標記會自動套用至 [可復原的專案] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-301">Retention Policy Tag (Recoverable Items); this tag is automatically applied to items in the Recoverable Items folder.</span></span>  <br/> |
    |<span data-ttu-id="e41b9-302">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="e41b9-302">Junk Email</span></span>  <br/> |<span data-ttu-id="e41b9-303">永久刪除 [垃圾郵件] 資料夾中30天內的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-303">Permanently deletes items that have been in the Junk Email folder for 30 days.</span></span> <span data-ttu-id="e41b9-304">使用者可在刪除後的14天內復原這些專案。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e41b9-304">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="e41b9-305">內建</span><span class="sxs-lookup"><span data-stu-id="e41b9-305">Built-in</span></span>  <br/> |<span data-ttu-id="e41b9-306">保留原則標記 (垃圾郵件) ;這個標記會自動套用至 [垃圾郵件] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-306">Retention Policy Tag (Junk Email); this tag is automatically applied to items in Junk Email folder.</span></span>  <br/> |
    |<span data-ttu-id="e41b9-307">1 個月刪除</span><span class="sxs-lookup"><span data-stu-id="e41b9-307">1 Month Delete</span></span>  <br/> |<span data-ttu-id="e41b9-308">永久刪除30天的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-308">Permanently deletes items that are 30 days old.</span></span> <span data-ttu-id="e41b9-309">使用者可在刪除後的14天內復原這些專案。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e41b9-309">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="e41b9-310">內建</span><span class="sxs-lookup"><span data-stu-id="e41b9-310">Built-in</span></span>  <br/> |<span data-ttu-id="e41b9-311">自己使用者可以套用此標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-311">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="e41b9-312">1 年刪除</span><span class="sxs-lookup"><span data-stu-id="e41b9-312">1 Year Delete</span></span>  <br/> |<span data-ttu-id="e41b9-313">永久刪除365天內的專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-313">Permanently deletes items that are 365 days old.</span></span> <span data-ttu-id="e41b9-314">使用者可在刪除後的14天內復原這些專案。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e41b9-314">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="e41b9-315">內建</span><span class="sxs-lookup"><span data-stu-id="e41b9-315">Built-in</span></span>  <br/> |<span data-ttu-id="e41b9-316">自己使用者可以套用此標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-316">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="e41b9-317">永不刪除</span><span class="sxs-lookup"><span data-stu-id="e41b9-317">Never Delete</span></span>  <br/> |<span data-ttu-id="e41b9-318">此標記可防止保留原則刪除專案。</span><span class="sxs-lookup"><span data-stu-id="e41b9-318">This tag prevents items from being deleted by a retention policy.</span></span>  <br/> |<span data-ttu-id="e41b9-319">內建</span><span class="sxs-lookup"><span data-stu-id="e41b9-319">Built-in</span></span>  <br/> |<span data-ttu-id="e41b9-320">自己使用者可以套用此標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-320">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="e41b9-321">個人 1 年移至封存</span><span class="sxs-lookup"><span data-stu-id="e41b9-321">Personal 1 year move to archive</span></span>  <br/> |<span data-ttu-id="e41b9-322">在1年後將專案移至封存信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-322">Moves items to the archive mailbox after 1 year.</span></span>  <br/> |<span data-ttu-id="e41b9-323">內建</span><span class="sxs-lookup"><span data-stu-id="e41b9-323">Built-in</span></span>  <br/> |<span data-ttu-id="e41b9-324">自己使用者可以套用此標記。</span><span class="sxs-lookup"><span data-stu-id="e41b9-324">Personal; this tag can be applied by users.</span></span>  <br/> |

    > <span data-ttu-id="e41b9-325"><sup>\*</sup>使用者可以使用「復原刪除的郵件」工具 Outlook 和 (Outlook （以前稱為 Outlook Web App) ）在已刪除專案的保留期間內復原已刪除的專案，這在 Exchange Online 中預設為14天。</span><span class="sxs-lookup"><span data-stu-id="e41b9-325"><sup>\*</sup> Users can use the Recover Deleted Items tool in Outlook and Outlook on the web (formerly known as Outlook Web App) to recover a deleted item within the deleted item retention period, which by default is 14 days in Exchange Online.</span></span> <span data-ttu-id="e41b9-326">系統管理員可以使用 Windows PowerShell 將刪除的專案保留期間增加至最長30天。</span><span class="sxs-lookup"><span data-stu-id="e41b9-326">An administrator can use Windows PowerShell to increase the deleted item retention period to a maximum of 30 days.</span></span> <span data-ttu-id="e41b9-327">如需詳細資訊，請參閱：[在 Outlook 中復原已刪除的專案 Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)並[變更 Exchange Online 中信箱的已刪除專案保留期間。](https://www.microsoft.com/?ref=go)</span><span class="sxs-lookup"><span data-stu-id="e41b9-327">For more information, see: [Recover deleted items in Outlook for Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) and [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go)</span></span>
  
- <span data-ttu-id="e41b9-328">使用 **可復原的專案14天移至** 封存保留標記有助於在使用者主要信箱的 [可復原的專案] 資料夾中釋放儲存空間。</span><span class="sxs-lookup"><span data-stu-id="e41b9-328">Using the **Recoverable Items 14 days Move to Archive** retention tag helps free up storage space in the Recoverable Items folder in the user's primary mailbox.</span></span> <span data-ttu-id="e41b9-329">當使用者的信箱處於保留狀態時，這是很有用的，這表示永遠不會永久刪除使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="e41b9-329">This is useful when a user's mailbox is placed on hold, which means nothing is ever permanently deleted the user's mailbox.</span></span> <span data-ttu-id="e41b9-330">在不將專案移至封存信箱時，可能會到達主要信箱中 [可復原的專案] 資料夾的儲存配額。</span><span class="sxs-lookup"><span data-stu-id="e41b9-330">Without moving items to the archive mailbox, it's possible the storage quota for the Recoverable Items folder in the primary mailbox will be reached.</span></span> <span data-ttu-id="e41b9-331">如需這項功能及其避免方式的詳細資訊，請參閱 [增加保留信箱的可復原專案配額](./increase-the-recoverable-quota-for-mailboxes-on-hold.md)。</span><span class="sxs-lookup"><span data-stu-id="e41b9-331">For more information about this and how to avoid it, see [Increase the Recoverable Items quota for mailboxes on hold](./increase-the-recoverable-quota-for-mailboxes-on-hold.md).</span></span>