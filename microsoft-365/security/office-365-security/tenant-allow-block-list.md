---
title: 在承租人允許/封鎖清單中管理您的允許和封鎖的 URLs
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在安全性 & 合規性中心的承租人允許/封鎖清單中設定 URL 專案。
ms.openlocfilehash: 0fdfa23ba22b240032e7a6888948de180aa0f6ae
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614961"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7a62-103">管理租使用戶允許/封鎖清單中的 URL</span><span class="sxs-lookup"><span data-stu-id="c7a62-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="c7a62-104">本主題中所述的功能包括預覽、可能變更，而且無法在所有的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="c7a62-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="c7a62-105">在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱，您可能會反對 EOP 篩選判定。</span><span class="sxs-lookup"><span data-stu-id="c7a62-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="c7a62-106">例如，良好的郵件可能會標示為壞的 (誤報) 或不良郵件可以透過 (誤報) 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="c7a62-107">Security & 合規性中心內的承租人 Allow/封鎖清單可讓您手動覆寫 Microsoft 365 篩選 verdicts。</span><span class="sxs-lookup"><span data-stu-id="c7a62-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="c7a62-108">承租人允許/封鎖清單是在郵件流程期間和使用者按一下時使用。</span><span class="sxs-lookup"><span data-stu-id="c7a62-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="c7a62-109">您可以在 [承租人允許/封鎖] 清單中指定要允許或封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="c7a62-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="c7a62-110">本主題說明如何使用 Exchange Online 中的信箱，在 Security & 合規性中心或 PowerShell (Exchange Online PowerShell 中，設定 [安全性合規性中心] 或 [Exchange Online 365 中的專案。沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c7a62-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c7a62-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="c7a62-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c7a62-112">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="c7a62-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c7a62-113">若要直接移至「 **租使用者允許/封鎖清單** 」頁面，請使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="c7a62-114">您可以在本主題稍後的 [承租人 Allow/封鎖清單區段之 url 語法](#url-syntax-for-the-tenant-allowblock-list) 中說明可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="c7a62-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="c7a62-115">承租人允許/封鎖清單最多可以有500個專案可供 URLs。</span><span class="sxs-lookup"><span data-stu-id="c7a62-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="c7a62-116">專案應該在15分鐘內生效。</span><span class="sxs-lookup"><span data-stu-id="c7a62-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="c7a62-117">封鎖專案優先于允許專案。</span><span class="sxs-lookup"><span data-stu-id="c7a62-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="c7a62-118">根據預設，承租人允許/封鎖清單中的專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="c7a62-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="c7a62-119">您可以指定日期或將其設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="c7a62-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="c7a62-120">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c7a62-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c7a62-121">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c7a62-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c7a62-122">您必須在安全性 & 合規性中心指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="c7a62-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c7a62-123">若要從 [承租人允許/封鎖] 清單中新增及移除值，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c7a62-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c7a62-124">若要取得租使用者 Allow/封鎖清單的唯讀許可權，您必須是 **全域讀取** 者或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c7a62-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c7a62-125">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c7a62-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="c7a62-126">**附註**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-126">**Notes**:</span></span>

  - <span data-ttu-id="c7a62-127">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="c7a62-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c7a62-128">如需詳細資訊，請參閱[系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="c7a62-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="c7a62-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="c7a62-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7a62-130">使用安全性 & 規範中心在承租人允許/封鎖清單中建立 URL 專案</span><span class="sxs-lookup"><span data-stu-id="c7a62-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7a62-131">如需 URL 專案之語法的詳細資訊，請參閱本主題稍後的 [承租人 Allow/封鎖清單區段的 URL 語法](#url-syntax-for-the-tenant-allowblock-list) 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="c7a62-132">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="c7a62-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c7a62-133">在 [**租使用者允許/封鎖清單**] 頁面上，確認已選取 [ **URLs** ] 索引標籤，然後按一下 [**新增**]</span><span class="sxs-lookup"><span data-stu-id="c7a62-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="c7a62-134">在出現的 [ **新增 URLs** ] 浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="c7a62-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c7a62-135">**使用萬用字元新增 URLs**：每行輸入一個 URL，最多20個。</span><span class="sxs-lookup"><span data-stu-id="c7a62-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c7a62-136">**封鎖/允許**：選取是否要 **允許** 或 **封鎖** 指定的 URLs。</span><span class="sxs-lookup"><span data-stu-id="c7a62-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="c7a62-137">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="c7a62-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c7a62-138">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="c7a62-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="c7a62-139">或</span><span class="sxs-lookup"><span data-stu-id="c7a62-139">or</span></span>

     - <span data-ttu-id="c7a62-140">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="c7a62-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="c7a62-142">.</span><span class="sxs-lookup"><span data-stu-id="c7a62-142">.</span></span>

   - <span data-ttu-id="c7a62-143">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="c7a62-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c7a62-144">完成後，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="c7a62-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7a62-145">使用安全性 & 規範中心來查看承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="c7a62-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c7a62-146">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="c7a62-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c7a62-147">選取 [ **URLs** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c7a62-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="c7a62-148">按一下下列欄標題，以遞增或遞減順序排序：</span><span class="sxs-lookup"><span data-stu-id="c7a62-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="c7a62-149">**Value**</span><span class="sxs-lookup"><span data-stu-id="c7a62-149">**Value**</span></span>
- <span data-ttu-id="c7a62-150">**動作**： **封鎖** 或 **允許**。</span><span class="sxs-lookup"><span data-stu-id="c7a62-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="c7a62-151">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="c7a62-151">**Last updated date**</span></span>
- <span data-ttu-id="c7a62-152">**有效期**</span><span class="sxs-lookup"><span data-stu-id="c7a62-152">**Expiration date**</span></span>
- <span data-ttu-id="c7a62-153">**附註**</span><span class="sxs-lookup"><span data-stu-id="c7a62-153">**Note**</span></span>

<span data-ttu-id="c7a62-154">按一下 [ **群組** ]，依 **動作** 將專案群組 (**封鎖** 或 **允許**) 或 **無**。</span><span class="sxs-lookup"><span data-stu-id="c7a62-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="c7a62-155">按一下 [ **搜尋**]，輸入全部或部分的值，然後按 enter 以尋找特定值。</span><span class="sxs-lookup"><span data-stu-id="c7a62-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="c7a62-156">完成後，請按一下 [ **清除搜尋** ![ 清除搜尋] 圖示 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="c7a62-157">按一下 [ **篩選**]。</span><span class="sxs-lookup"><span data-stu-id="c7a62-157">Click **Filter**.</span></span> <span data-ttu-id="c7a62-158">在出現的 [ **篩選** ] 浮出控制項中，設定下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="c7a62-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="c7a62-159">**動作**：選取 [ **允許**]、[ **封鎖** ] 或 [兩者]。</span><span class="sxs-lookup"><span data-stu-id="c7a62-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="c7a62-160">**永不過期**：選取 [關閉] (![ 切換 ](../../media/scc-toggle-off.png)) 或 (![ 切換上的 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)) 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-160">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="c7a62-161">**上次更新**： **從**)  (的開始日期， (**為**) 或兩者的結束日期。</span><span class="sxs-lookup"><span data-stu-id="c7a62-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="c7a62-162">**到期日**： **從**)  (的開始日期， (**為**) 或兩者的結束日期。</span><span class="sxs-lookup"><span data-stu-id="c7a62-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="c7a62-163">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="c7a62-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="c7a62-164">若要清除現有篩選，請按一下 [ **篩選**]，然後在出現的 [ **篩選** ] 浮出控制項中按一下 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="c7a62-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7a62-165">使用安全性 & 規範中心修改承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="c7a62-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7a62-166">您無法修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="c7a62-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="c7a62-167">相反地，您必須刪除該專案，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="c7a62-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="c7a62-168">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="c7a62-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c7a62-169">選取 [ **URLs** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c7a62-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="c7a62-170">選取您要修改的專案，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="c7a62-171">在出現的浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="c7a62-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c7a62-172">**封鎖/允許**：選取 [ **允許** ] 或 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="c7a62-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="c7a62-173">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="c7a62-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c7a62-174">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定輸入專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="c7a62-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="c7a62-175">或</span><span class="sxs-lookup"><span data-stu-id="c7a62-175">or</span></span>

     - <span data-ttu-id="c7a62-176">將切換向右移動，將專案設定為永不過期：</span><span class="sxs-lookup"><span data-stu-id="c7a62-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="c7a62-178">.</span><span class="sxs-lookup"><span data-stu-id="c7a62-178">.</span></span>

   - <span data-ttu-id="c7a62-179">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="c7a62-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="c7a62-180">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="c7a62-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c7a62-181">使用安全性 & 規範中心移除承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="c7a62-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c7a62-182">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="c7a62-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c7a62-183">選取 [ **URLs** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c7a62-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="c7a62-184">選取您要移除的專案，然後按一下 [ **刪除** ![ 刪除圖示] ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="c7a62-185">在出現的警告對話方塊中，按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="c7a62-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="c7a62-186">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="c7a62-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7a62-187">使用 PowerShell 在承租人允許/封鎖清單中新增專案</span><span class="sxs-lookup"><span data-stu-id="c7a62-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7a62-188">若要在 [租使用者允許/封鎖] 清單中新增專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="c7a62-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c7a62-189">這個範例會新增 contoso.com 及所有子域 (的 URL 封鎖專案（例如，contoso.com、www.contoso.com 及 xyz.abc.contoso.com) ）。</span><span class="sxs-lookup"><span data-stu-id="c7a62-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="c7a62-190">因為我們未使用 ExpirationDate 或 NoExpiration 參數，所以專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="c7a62-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="c7a62-191">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="c7a62-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7a62-192">使用 PowerShell 來查看承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="c7a62-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7a62-193">若要在 [租使用者允許/封鎖] 清單中查看專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="c7a62-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="c7a62-194">本範例會傳回所有封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="c7a62-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="c7a62-195">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="c7a62-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7a62-196">使用 PowerShell 修改承租人 Allow/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="c7a62-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7a62-197">您無法修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="c7a62-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="c7a62-198">相反地，您必須刪除該專案，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="c7a62-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="c7a62-199">若要修改承租人 Allow/封鎖清單中的專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="c7a62-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c7a62-200">本範例會變更指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="c7a62-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="c7a62-201">如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="c7a62-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c7a62-202">使用 PowerShell 從承租人允許/封鎖清單中移除專案</span><span class="sxs-lookup"><span data-stu-id="c7a62-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7a62-203">若要移除承租人允許/封鎖清單中的專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="c7a62-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="c7a62-204">此範例會從承租人允許/封鎖清單中移除指定的 URL 專案。</span><span class="sxs-lookup"><span data-stu-id="c7a62-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="c7a62-205">如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="c7a62-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="c7a62-206">承租人允許/封鎖清單的 URL 語法</span><span class="sxs-lookup"><span data-stu-id="c7a62-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="c7a62-207">允許 IP4v 和 IPv6 位址，但不會 TCP/UDP 埠。</span><span class="sxs-lookup"><span data-stu-id="c7a62-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="c7a62-208">不允許使用副檔名 (例如，test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="c7a62-209">不支援 Unicode，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="c7a62-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="c7a62-210">如果下列所有陳述皆為 true，則允許主機名稱：</span><span class="sxs-lookup"><span data-stu-id="c7a62-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="c7a62-211">主機名稱包含句點。</span><span class="sxs-lookup"><span data-stu-id="c7a62-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="c7a62-212">句點的左側至少有一個字元。</span><span class="sxs-lookup"><span data-stu-id="c7a62-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="c7a62-213">句點右側至少有兩個字元。</span><span class="sxs-lookup"><span data-stu-id="c7a62-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="c7a62-214">例如， `t.co` 允許; `.com` 或是 `contoso.` 不允許。</span><span class="sxs-lookup"><span data-stu-id="c7a62-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="c7a62-215">不暗含子路徑。</span><span class="sxs-lookup"><span data-stu-id="c7a62-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="c7a62-216">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="c7a62-217">在下列案例中，允許使用萬用字元 ( \* ) ：</span><span class="sxs-lookup"><span data-stu-id="c7a62-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="c7a62-218">左邊的萬用字元必須後接句點，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="c7a62-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="c7a62-219">例如， `*.contoso.com` 允許; `*contoso.com` 是不允許的。</span><span class="sxs-lookup"><span data-stu-id="c7a62-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="c7a62-220">右萬用字元必須跟隨正斜線 (/) 來指定路徑。</span><span class="sxs-lookup"><span data-stu-id="c7a62-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="c7a62-221">例如， `contoso.com/*` 允許; `contoso.com*` 或是 `contoso.com/ab*` 不允許。</span><span class="sxs-lookup"><span data-stu-id="c7a62-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="c7a62-222">所有的子路徑都不是以右邊的萬用字元隱含。</span><span class="sxs-lookup"><span data-stu-id="c7a62-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="c7a62-223">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="c7a62-224">`*.com*` 無效 (不是可解析的網域，正確的萬用字元不遵循正斜線) 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="c7a62-225">IP 位址中不允許使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="c7a62-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="c7a62-226">在下列案例中，顎化 (~) 字元是可用的：</span><span class="sxs-lookup"><span data-stu-id="c7a62-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="c7a62-227">左波形符表示網域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="c7a62-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="c7a62-228">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="c7a62-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="c7a62-229">包含通訊協定 (的 URL 專案例如， `http://` 、 `https://` 或 `ftp://`) 會失敗，因為 url 專案適用于所有通訊協定。</span><span class="sxs-lookup"><span data-stu-id="c7a62-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="c7a62-230">不支援或不需要使用者名稱或密碼。</span><span class="sxs-lookup"><span data-stu-id="c7a62-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="c7a62-231">引號 ( ' 或 ") 是不正確字元。</span><span class="sxs-lookup"><span data-stu-id="c7a62-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="c7a62-232">URL 應盡可能包括所有重新導向。</span><span class="sxs-lookup"><span data-stu-id="c7a62-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="c7a62-233">URL 專案案例</span><span class="sxs-lookup"><span data-stu-id="c7a62-233">URL entry scenarios</span></span>

<span data-ttu-id="c7a62-234">有效的 URL 專案及其結果將在下列各節中說明。</span><span class="sxs-lookup"><span data-stu-id="c7a62-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="c7a62-235">案例：沒有萬用字元</span><span class="sxs-lookup"><span data-stu-id="c7a62-235">Scenario: No wildcards</span></span>

<span data-ttu-id="c7a62-236">**專案**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c7a62-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="c7a62-237">**允許相符**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="c7a62-238">**允許不符合**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="c7a62-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-239">abc-contoso.com</span></span>
  - <span data-ttu-id="c7a62-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7a62-240">contoso.com/a</span></span>
  - <span data-ttu-id="c7a62-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="c7a62-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="c7a62-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c7a62-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-244">www.contoso.com</span></span>
  - <span data-ttu-id="c7a62-245">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="c7a62-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c7a62-246">**Block match**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-246">**Block match**:</span></span>

  - <span data-ttu-id="c7a62-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-247">contoso.com</span></span>
  - <span data-ttu-id="c7a62-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7a62-248">contoso.com/a</span></span>
  - <span data-ttu-id="c7a62-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="c7a62-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="c7a62-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c7a62-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-252">www.contoso.com</span></span>
  - <span data-ttu-id="c7a62-253">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="c7a62-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c7a62-254">**不符合的區塊**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="c7a62-255">案例：保留萬用字元 (子域) </span><span class="sxs-lookup"><span data-stu-id="c7a62-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="c7a62-256">**專案**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c7a62-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="c7a62-257">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7a62-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-258">www.contoso.com</span></span>
  - <span data-ttu-id="c7a62-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c7a62-260">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c7a62-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-261">123contoso.com</span></span>
  - <span data-ttu-id="c7a62-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-262">contoso.com</span></span>
  - <span data-ttu-id="c7a62-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="c7a62-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c7a62-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="c7a62-265">案例：路徑頂端的右萬用字元</span><span class="sxs-lookup"><span data-stu-id="c7a62-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="c7a62-266">**專案**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="c7a62-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="c7a62-267">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7a62-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="c7a62-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="c7a62-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c7a62-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c7a62-270">contoso/a/？ q = joe@t .com</span><span class="sxs-lookup"><span data-stu-id="c7a62-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="c7a62-271">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c7a62-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-272">contoso.com</span></span>
  - <span data-ttu-id="c7a62-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7a62-273">contoso.com/a</span></span>
  - <span data-ttu-id="c7a62-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-274">www.contoso.com</span></span>
  - <span data-ttu-id="c7a62-275">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="c7a62-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="c7a62-276">案例：左波形符</span><span class="sxs-lookup"><span data-stu-id="c7a62-276">Scenario: Left tilde</span></span>

<span data-ttu-id="c7a62-277">**專案**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c7a62-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="c7a62-278">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7a62-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-279">contoso.com</span></span>
  - <span data-ttu-id="c7a62-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-280">www.contoso.com</span></span>
  - <span data-ttu-id="c7a62-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c7a62-282">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c7a62-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-283">123contoso.com</span></span>
  - <span data-ttu-id="c7a62-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c7a62-284">contoso.com/abc</span></span>
  - <span data-ttu-id="c7a62-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c7a62-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="c7a62-286">案例：右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="c7a62-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="c7a62-287">**專案**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c7a62-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="c7a62-288">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7a62-289">contoso （.com）/？ q = whatever@fabrikam .com</span><span class="sxs-lookup"><span data-stu-id="c7a62-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="c7a62-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7a62-290">contoso.com/a</span></span>
  - <span data-ttu-id="c7a62-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c7a62-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c7a62-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c7a62-292">contoso.com/ab</span></span>
  - <span data-ttu-id="c7a62-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c7a62-293">contoso.com/b</span></span>
  - <span data-ttu-id="c7a62-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c7a62-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c7a62-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c7a62-295">contoso.com/ba</span></span>

- <span data-ttu-id="c7a62-296">**允許不符合** 或 **不符合的封鎖**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="c7a62-297">案例： Left 通配子域和右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="c7a62-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="c7a62-298">**專案**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c7a62-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="c7a62-299">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7a62-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c7a62-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="c7a62-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c7a62-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c7a62-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7a62-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="c7a62-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c7a62-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c7a62-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c7a62-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="c7a62-305">**允許不符合** 或 **不符合的封鎖**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c7a62-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="c7a62-306">案例：左和右顎化符</span><span class="sxs-lookup"><span data-stu-id="c7a62-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="c7a62-307">**專案**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="c7a62-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="c7a62-308">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7a62-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-309">contoso.com</span></span>
  - <span data-ttu-id="c7a62-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7a62-310">contoso.com/a</span></span>
  - <span data-ttu-id="c7a62-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-311">www.contoso.com</span></span>
  - <span data-ttu-id="c7a62-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c7a62-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="c7a62-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c7a62-314">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c7a62-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-315">123contoso.com</span></span>
  - <span data-ttu-id="c7a62-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="c7a62-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="c7a62-317">案例： IP 位址</span><span class="sxs-lookup"><span data-stu-id="c7a62-317">Scenario: IP address</span></span>

<span data-ttu-id="c7a62-318">**專案**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="c7a62-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="c7a62-319">**允許** 比對和 **區塊相符**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="c7a62-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="c7a62-320">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c7a62-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c7a62-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="c7a62-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c7a62-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="c7a62-323">具有右萬用字元的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="c7a62-323">IP address with right wildcard</span></span>

<span data-ttu-id="c7a62-324">**專案**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="c7a62-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="c7a62-325">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7a62-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="c7a62-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="c7a62-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="c7a62-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="c7a62-328">無效專案的範例</span><span class="sxs-lookup"><span data-stu-id="c7a62-328">Examples of invalid entries</span></span>

<span data-ttu-id="c7a62-329">下列專案是不正確：</span><span class="sxs-lookup"><span data-stu-id="c7a62-329">The following entries are invalid:</span></span>

- <span data-ttu-id="c7a62-330">**遺失或不正確網域值**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="c7a62-331">尚未</span><span class="sxs-lookup"><span data-stu-id="c7a62-331">contoso</span></span>
  - <span data-ttu-id="c7a62-332">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="c7a62-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="c7a62-333">\*.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-333">\*.com</span></span>
  - <span data-ttu-id="c7a62-334">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="c7a62-334">\*.pdf</span></span>

- <span data-ttu-id="c7a62-335">**文字上的萬用字元，或不含間距的字元**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="c7a62-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-336">\*contoso.com</span></span>
  - <span data-ttu-id="c7a62-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="c7a62-337">contoso.com\*</span></span>
  - <span data-ttu-id="c7a62-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c7a62-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="c7a62-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="c7a62-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="c7a62-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="c7a62-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="c7a62-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="c7a62-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="c7a62-342">**含埠的 IP 位址**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="c7a62-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="c7a62-343">contoso.com:443</span></span>
  - <span data-ttu-id="c7a62-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="c7a62-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="c7a62-345">**非描述萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="c7a62-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="c7a62-346">\*.\*</span></span>

- <span data-ttu-id="c7a62-347">**中間的萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="c7a62-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="c7a62-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="c7a62-348">conto\*so.com</span></span>
  - <span data-ttu-id="c7a62-349">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="c7a62-349">conto~so.com</span></span>

- <span data-ttu-id="c7a62-350">**兩個萬用字元**</span><span class="sxs-lookup"><span data-stu-id="c7a62-350">**Double wildcards**</span></span>

  - <span data-ttu-id="c7a62-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="c7a62-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="c7a62-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="c7a62-352">contoso.com/\*/\*</span></span>
