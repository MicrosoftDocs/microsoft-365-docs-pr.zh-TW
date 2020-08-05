---
title: 在承租人允許/封鎖清單中管理您的允許和封鎖的 URLs
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
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在安全性 & 合規性中心的承租人允許/封鎖清單中設定 URL 專案。
ms.openlocfilehash: 5ff34cca922f18a015bd9da847facc8177cf8790
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552547"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cca4-103">在承租人允許/封鎖清單中管理 URLs</span><span class="sxs-lookup"><span data-stu-id="1cca4-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="1cca4-104">本主題中所述的功能包括預覽、可能變更，而且無法在所有的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="1cca4-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="1cca4-105">在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱，您可能會反對 EOP 篩選判定。</span><span class="sxs-lookup"><span data-stu-id="1cca4-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="1cca4-106">例如，良好的郵件可能會標示為壞的 (誤報) 或不良郵件可以透過 (誤報) 。</span><span class="sxs-lookup"><span data-stu-id="1cca4-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="1cca4-107">Security & 合規性中心內的承租人 Allow/封鎖清單可讓您手動覆寫 Microsoft 365 篩選 verdicts。</span><span class="sxs-lookup"><span data-stu-id="1cca4-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="1cca4-108">承租人允許/封鎖清單是在郵件流程期間和使用者按一下時使用。</span><span class="sxs-lookup"><span data-stu-id="1cca4-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="1cca4-109">您可以在 [承租人允許/封鎖] 清單中指定要允許或封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="1cca4-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="1cca4-110">本主題說明如何使用 Exchange Online 中的信箱，在 Security & 合規性中心或 PowerShell (Exchange Online PowerShell 中，設定 [安全性合規性中心] 或 [Exchange Online 365 中的專案。沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1cca4-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1cca4-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="1cca4-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1cca4-112">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="1cca4-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1cca4-113">若要直接移至「**租使用者允許/封鎖清單**」頁面，請使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="1cca4-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="1cca4-114">您可以在本主題稍後的[承租人 Allow/封鎖清單區段之 url 語法](#url-syntax-for-the-tenant-allowblock-list)中說明可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="1cca4-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="1cca4-115">承租人允許/封鎖清單允許 URLss 最多500個專案。</span><span class="sxs-lookup"><span data-stu-id="1cca4-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLss.</span></span>

- <span data-ttu-id="1cca4-116">專案應該在15分鐘內生效。</span><span class="sxs-lookup"><span data-stu-id="1cca4-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="1cca4-117">封鎖專案優先于允許專案。</span><span class="sxs-lookup"><span data-stu-id="1cca4-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="1cca4-118">根據預設，承租人允許/封鎖清單中的專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="1cca4-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="1cca4-119">您可以指定日期或將其設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="1cca4-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="1cca4-120">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1cca4-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1cca4-121">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1cca4-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1cca4-122">您必須已獲派權限，才能進行此主題中的程序:</span><span class="sxs-lookup"><span data-stu-id="1cca4-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="1cca4-123">若要從 [承租人允許/封鎖] 清單中新增及移除值，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="1cca4-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="1cca4-124">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="1cca4-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="1cca4-125">**組織管理** 或 [線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **檢疫管理**。</span><span class="sxs-lookup"><span data-stu-id="1cca4-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="1cca4-126">若要對租使用者 Allow/封鎖清單進行唯讀存取，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="1cca4-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="1cca4-127">[安全性與合規性中心](permissions-in-the-security-and-compliance-center.md) 中的 **安全讀者**。</span><span class="sxs-lookup"><span data-stu-id="1cca4-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="1cca4-128">[線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅檢視組織管理**。</span><span class="sxs-lookup"><span data-stu-id="1cca4-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cca4-129">使用安全性 & 規範中心在承租人允許/封鎖清單中建立 URL 專案</span><span class="sxs-lookup"><span data-stu-id="1cca4-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cca4-130">如需 URL 專案之語法的詳細資訊，請參閱本主題稍後的[承租人 Allow/封鎖清單區段的 URL 語法](#url-syntax-for-the-tenant-allowblock-list)。</span><span class="sxs-lookup"><span data-stu-id="1cca4-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="1cca4-131">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="1cca4-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1cca4-132">在 [**租使用者允許/封鎖清單**] 頁面上，確認已選取 [ **URLs** ] 索引標籤，然後按一下 [**新增**]</span><span class="sxs-lookup"><span data-stu-id="1cca4-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="1cca4-133">在出現的 [**新增 URLs** ] 浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="1cca4-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1cca4-134">**使用萬用字元新增 URLs**：每行輸入一個 URL，最多20個。</span><span class="sxs-lookup"><span data-stu-id="1cca4-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="1cca4-135">**封鎖/允許**：選取是否要**允許**或**封鎖**指定的 URLs。</span><span class="sxs-lookup"><span data-stu-id="1cca4-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="1cca4-136">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="1cca4-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1cca4-137">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [**到期**日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="1cca4-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="1cca4-138">或</span><span class="sxs-lookup"><span data-stu-id="1cca4-138">or</span></span>

     - <span data-ttu-id="1cca4-139">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="1cca4-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="1cca4-141">.</span><span class="sxs-lookup"><span data-stu-id="1cca4-141">.</span></span>

   - <span data-ttu-id="1cca4-142">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="1cca4-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="1cca4-143">完成後，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="1cca4-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cca4-144">使用安全性 & 規範中心來查看承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="1cca4-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1cca4-145">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="1cca4-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1cca4-146">選取 [ **URLs** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1cca4-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="1cca4-147">按一下下列欄標題，以遞增或遞減順序排序：</span><span class="sxs-lookup"><span data-stu-id="1cca4-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="1cca4-148">**值**</span><span class="sxs-lookup"><span data-stu-id="1cca4-148">**Value**</span></span>
- <span data-ttu-id="1cca4-149">**動作**：**封鎖**或**允許**。</span><span class="sxs-lookup"><span data-stu-id="1cca4-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="1cca4-150">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="1cca4-150">**Last updated date**</span></span>
- <span data-ttu-id="1cca4-151">**有效期**</span><span class="sxs-lookup"><span data-stu-id="1cca4-151">**Expiration date**</span></span>
- <span data-ttu-id="1cca4-152">**附註**</span><span class="sxs-lookup"><span data-stu-id="1cca4-152">**Note**</span></span>

<span data-ttu-id="1cca4-153">按一下 [**群組**]，依**動作**將專案群組 (**封鎖**或**允許**) 或**無**。</span><span class="sxs-lookup"><span data-stu-id="1cca4-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="1cca4-154">按一下 [**搜尋**]，輸入全部或部分的值，然後按 enter 以尋找特定值。</span><span class="sxs-lookup"><span data-stu-id="1cca4-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="1cca4-155">完成後，請按一下 [**清除搜尋** ![ 清除搜尋] 圖示 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="1cca4-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="1cca4-156">按一下 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1cca4-156">Click **Filter**.</span></span> <span data-ttu-id="1cca4-157">在出現的 [**篩選**] 浮出控制項中，設定下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="1cca4-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="1cca4-158">**動作**：選取 [**允許**]、[**封鎖**] 或 [兩者]。</span><span class="sxs-lookup"><span data-stu-id="1cca4-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="1cca4-159">**永不過期**：選取 [關閉] (![ 切換 ](../../media/scc-toggle-off.png)) 或 (![ 切換上的 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)) 。</span><span class="sxs-lookup"><span data-stu-id="1cca4-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="1cca4-160">**上次更新**：**從**)  (的開始日期， (**為**) 或兩者的結束日期。</span><span class="sxs-lookup"><span data-stu-id="1cca4-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="1cca4-161">**到期日**：**從**)  (的開始日期， (**為**) 或兩者的結束日期。</span><span class="sxs-lookup"><span data-stu-id="1cca4-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="1cca4-162">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="1cca4-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="1cca4-163">若要清除現有篩選，請按一下 [**篩選**]，然後在出現的 [**篩選**] 浮出控制項中按一下 [**清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1cca4-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cca4-164">使用安全性 & 規範中心修改承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="1cca4-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cca4-165">您無法修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="1cca4-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="1cca4-166">相反地，您必須刪除該專案，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="1cca4-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="1cca4-167">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="1cca4-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1cca4-168">選取 [ **URLs** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1cca4-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="1cca4-169">選取您要修改的專案，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="1cca4-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="1cca4-170">在出現的浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="1cca4-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1cca4-171">**封鎖/允許**：選取 [**允許**] 或 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="1cca4-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="1cca4-172">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="1cca4-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1cca4-173">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [**到期**日] 方塊來指定輸入專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="1cca4-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="1cca4-174">或</span><span class="sxs-lookup"><span data-stu-id="1cca4-174">or</span></span>

     - <span data-ttu-id="1cca4-175">將切換向右移動，將專案設定為永不過期：</span><span class="sxs-lookup"><span data-stu-id="1cca4-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="1cca4-177">.</span><span class="sxs-lookup"><span data-stu-id="1cca4-177">.</span></span>

   - <span data-ttu-id="1cca4-178">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="1cca4-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="1cca4-179">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1cca4-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1cca4-180">使用安全性 & 規範中心移除承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="1cca4-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1cca4-181">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="1cca4-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1cca4-182">選取 [ **URLs** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1cca4-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="1cca4-183">選取您要移除的專案，然後按一下 [**刪除** ![ 刪除圖示] ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="1cca4-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="1cca4-184">在出現的警告對話方塊中，按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="1cca4-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="1cca4-185">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="1cca4-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cca4-186">使用 PowerShell 在承租人允許/封鎖清單中新增專案</span><span class="sxs-lookup"><span data-stu-id="1cca4-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cca4-187">若要在 [租使用者允許/封鎖] 清單中新增專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1cca4-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="1cca4-188">這個範例會新增 contoso.com 及所有子域 (的 URL 封鎖專案（例如，contoso.com、www.contoso.com 及 xyz.abc.contoso.com) ）。</span><span class="sxs-lookup"><span data-stu-id="1cca4-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="1cca4-189">因為我們未使用 ExpirationDate 或 NoExpiration 參數，所以專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="1cca4-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="1cca4-190">如需詳細的語法及參數資訊，請參閱[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="1cca4-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cca4-191">使用 PowerShell 來查看承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="1cca4-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cca4-192">若要在 [租使用者允許/封鎖] 清單中查看專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1cca4-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="1cca4-193">本範例會傳回所有封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="1cca4-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="1cca4-194">如需詳細的語法及參數資訊，請參閱[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="1cca4-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cca4-195">使用 PowerShell 修改承租人 Allow/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="1cca4-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cca4-196">您無法修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="1cca4-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="1cca4-197">相反地，您必須刪除該專案，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="1cca4-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="1cca4-198">若要修改承租人 Allow/封鎖清單中的專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1cca4-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="1cca4-199">本範例會變更指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="1cca4-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="1cca4-200">如需詳細的語法及參數資訊，請參閱[Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="1cca4-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1cca4-201">使用 PowerShell 從承租人允許/封鎖清單中移除專案</span><span class="sxs-lookup"><span data-stu-id="1cca4-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cca4-202">若要移除承租人允許/封鎖清單中的專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1cca4-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="1cca4-203">此範例會從承租人允許/封鎖清單中移除指定的 URL 專案。</span><span class="sxs-lookup"><span data-stu-id="1cca4-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="1cca4-204">如需詳細的語法及參數資訊，請參閱[Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="1cca4-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="1cca4-205">承租人允許/封鎖清單的 URL 語法</span><span class="sxs-lookup"><span data-stu-id="1cca4-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="1cca4-206">允許 IP4v 和 IPv6 位址，但不會 TCP/UDP 埠。</span><span class="sxs-lookup"><span data-stu-id="1cca4-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="1cca4-207">不允許使用副檔名 (例如，test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="1cca4-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="1cca4-208">不支援 Unicode，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="1cca4-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="1cca4-209">如果下列所有陳述皆為 true，則允許主機名稱：</span><span class="sxs-lookup"><span data-stu-id="1cca4-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="1cca4-210">主機名稱包含句點。</span><span class="sxs-lookup"><span data-stu-id="1cca4-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="1cca4-211">句點的左側至少有一個字元。</span><span class="sxs-lookup"><span data-stu-id="1cca4-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="1cca4-212">句點右側至少有兩個字元。</span><span class="sxs-lookup"><span data-stu-id="1cca4-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="1cca4-213">例如， `t.co` 允許; `.com` 或是 `contoso.` 不允許。</span><span class="sxs-lookup"><span data-stu-id="1cca4-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="1cca4-214">不暗含子路徑。</span><span class="sxs-lookup"><span data-stu-id="1cca4-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="1cca4-215">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="1cca4-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="1cca4-216">在下列案例中，允許使用萬用字元 ( \* ) ：</span><span class="sxs-lookup"><span data-stu-id="1cca4-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="1cca4-217">左邊的萬用字元必須後接句點，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="1cca4-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="1cca4-218">例如， `*.contoso.com` 允許; `*contoso.com` 是不允許的。</span><span class="sxs-lookup"><span data-stu-id="1cca4-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="1cca4-219">右萬用字元必須跟隨正斜線 (/) 來指定路徑。</span><span class="sxs-lookup"><span data-stu-id="1cca4-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="1cca4-220">例如， `contoso.com/*` 允許; `contoso.com*` 或是 `contoso.com/ab*` 不允許。</span><span class="sxs-lookup"><span data-stu-id="1cca4-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="1cca4-221">所有的子路徑都不是以右邊的萬用字元隱含。</span><span class="sxs-lookup"><span data-stu-id="1cca4-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="1cca4-222">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="1cca4-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="1cca4-223">`*.com*`無效 (不是可解析的網域，正確的萬用字元不遵循正斜線) 。</span><span class="sxs-lookup"><span data-stu-id="1cca4-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="1cca4-224">IP 位址中不允許使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="1cca4-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="1cca4-225">在下列案例中，顎化 (~) 字元是可用的：</span><span class="sxs-lookup"><span data-stu-id="1cca4-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="1cca4-226">左波形符表示網域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="1cca4-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="1cca4-227">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="1cca4-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="1cca4-228">包含通訊協定 (的 URL 專案例如， `http://` 、 `https://` 或 `ftp://`) 會失敗，因為 url 專案適用于所有通訊協定。</span><span class="sxs-lookup"><span data-stu-id="1cca4-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="1cca4-229">不支援或不需要使用者名稱或密碼。</span><span class="sxs-lookup"><span data-stu-id="1cca4-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="1cca4-230">引號 ( ' 或 ") 是不正確字元。</span><span class="sxs-lookup"><span data-stu-id="1cca4-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="1cca4-231">URL 應盡可能包括所有重新導向。</span><span class="sxs-lookup"><span data-stu-id="1cca4-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="1cca4-232">URL 專案案例</span><span class="sxs-lookup"><span data-stu-id="1cca4-232">URL entry scenarios</span></span>

<span data-ttu-id="1cca4-233">有效的 URL 專案及其結果將在下列各節中說明。</span><span class="sxs-lookup"><span data-stu-id="1cca4-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="1cca4-234">案例：沒有萬用字元</span><span class="sxs-lookup"><span data-stu-id="1cca4-234">Scenario: No wildcards</span></span>

<span data-ttu-id="1cca4-235">**專案**：`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1cca4-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="1cca4-236">**允許相符**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="1cca4-237">**允許不符合**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="1cca4-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-238">abc-contoso.com</span></span>
  - <span data-ttu-id="1cca4-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cca4-239">contoso.com/a</span></span>
  - <span data-ttu-id="1cca4-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="1cca4-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="1cca4-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1cca4-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-243">www.contoso.com</span></span>
  - <span data-ttu-id="1cca4-244">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="1cca4-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="1cca4-245">**Block match**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-245">**Block match**:</span></span>

  - <span data-ttu-id="1cca4-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-246">contoso.com</span></span>
  - <span data-ttu-id="1cca4-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cca4-247">contoso.com/a</span></span>
  - <span data-ttu-id="1cca4-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="1cca4-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="1cca4-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1cca4-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-251">www.contoso.com</span></span>
  - <span data-ttu-id="1cca4-252">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="1cca4-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="1cca4-253">**不符合的區塊**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="1cca4-254">案例：保留萬用字元 (子域) </span><span class="sxs-lookup"><span data-stu-id="1cca4-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="1cca4-255">**專案**：`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1cca4-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="1cca4-256">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cca4-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-257">www.contoso.com</span></span>
  - <span data-ttu-id="1cca4-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1cca4-259">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1cca4-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-260">123contoso.com</span></span>
  - <span data-ttu-id="1cca4-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-261">contoso.com</span></span>
  - <span data-ttu-id="1cca4-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="1cca4-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1cca4-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="1cca4-264">案例：路徑頂端的右萬用字元</span><span class="sxs-lookup"><span data-stu-id="1cca4-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="1cca4-265">**專案**：`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="1cca4-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="1cca4-266">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cca4-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="1cca4-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="1cca4-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1cca4-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1cca4-269">contoso/a/？ q = joe@t .com</span><span class="sxs-lookup"><span data-stu-id="1cca4-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="1cca4-270">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1cca4-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-271">contoso.com</span></span>
  - <span data-ttu-id="1cca4-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cca4-272">contoso.com/a</span></span>
  - <span data-ttu-id="1cca4-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-273">www.contoso.com</span></span>
  - <span data-ttu-id="1cca4-274">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="1cca4-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="1cca4-275">案例：左波形符</span><span class="sxs-lookup"><span data-stu-id="1cca4-275">Scenario: Left tilde</span></span>

<span data-ttu-id="1cca4-276">**專案**：`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1cca4-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="1cca4-277">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cca4-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-278">contoso.com</span></span>
  - <span data-ttu-id="1cca4-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-279">www.contoso.com</span></span>
  - <span data-ttu-id="1cca4-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1cca4-281">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1cca4-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-282">123contoso.com</span></span>
  - <span data-ttu-id="1cca4-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1cca4-283">contoso.com/abc</span></span>
  - <span data-ttu-id="1cca4-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1cca4-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="1cca4-285">案例：右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="1cca4-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="1cca4-286">**專案**：`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1cca4-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="1cca4-287">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cca4-288">contoso （.com）/？ q = whatever@fabrikam .com</span><span class="sxs-lookup"><span data-stu-id="1cca4-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="1cca4-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cca4-289">contoso.com/a</span></span>
  - <span data-ttu-id="1cca4-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1cca4-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1cca4-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1cca4-291">contoso.com/ab</span></span>
  - <span data-ttu-id="1cca4-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1cca4-292">contoso.com/b</span></span>
  - <span data-ttu-id="1cca4-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1cca4-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1cca4-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1cca4-294">contoso.com/ba</span></span>

- <span data-ttu-id="1cca4-295">**允許不符合**或**不符合的封鎖**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="1cca4-296">案例： Left 通配子域和右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="1cca4-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="1cca4-297">**專案**：`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1cca4-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="1cca4-298">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cca4-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1cca4-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="1cca4-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1cca4-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1cca4-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cca4-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="1cca4-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1cca4-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1cca4-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1cca4-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="1cca4-304">**允許不符合**或**不符合的封鎖**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1cca4-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="1cca4-305">案例：左和右顎化符</span><span class="sxs-lookup"><span data-stu-id="1cca4-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="1cca4-306">**專案**：`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="1cca4-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="1cca4-307">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cca4-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-308">contoso.com</span></span>
  - <span data-ttu-id="1cca4-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cca4-309">contoso.com/a</span></span>
  - <span data-ttu-id="1cca4-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-310">www.contoso.com</span></span>
  - <span data-ttu-id="1cca4-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1cca4-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="1cca4-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1cca4-313">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1cca4-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-314">123contoso.com</span></span>
  - <span data-ttu-id="1cca4-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="1cca4-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="1cca4-316">案例： IP 位址</span><span class="sxs-lookup"><span data-stu-id="1cca4-316">Scenario: IP address</span></span>

<span data-ttu-id="1cca4-317">**專案**：`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="1cca4-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="1cca4-318">**允許**比對和**區塊相符**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="1cca4-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="1cca4-319">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1cca4-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1cca4-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="1cca4-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1cca4-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="1cca4-322">具有右萬用字元的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1cca4-322">IP address with right wildcard</span></span>

<span data-ttu-id="1cca4-323">**專案**：`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="1cca4-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="1cca4-324">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cca4-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="1cca4-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="1cca4-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="1cca4-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="1cca4-327">無效專案的範例</span><span class="sxs-lookup"><span data-stu-id="1cca4-327">Examples of invalid entries</span></span>

<span data-ttu-id="1cca4-328">下列專案是不正確：</span><span class="sxs-lookup"><span data-stu-id="1cca4-328">The following entries are invalid:</span></span>

- <span data-ttu-id="1cca4-329">**遺失或不正確網域值**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="1cca4-330">尚未</span><span class="sxs-lookup"><span data-stu-id="1cca4-330">contoso</span></span>
  - <span data-ttu-id="1cca4-331">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="1cca4-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="1cca4-332">\*.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-332">\*.com</span></span>
  - <span data-ttu-id="1cca4-333">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="1cca4-333">\*.pdf</span></span>

- <span data-ttu-id="1cca4-334">**文字上的萬用字元，或不含間距的字元**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="1cca4-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-335">\*contoso.com</span></span>
  - <span data-ttu-id="1cca4-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="1cca4-336">contoso.com\*</span></span>
  - <span data-ttu-id="1cca4-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="1cca4-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="1cca4-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="1cca4-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="1cca4-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="1cca4-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="1cca4-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="1cca4-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="1cca4-341">**含埠的 IP 位址**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="1cca4-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="1cca4-342">contoso.com:443</span></span>
  - <span data-ttu-id="1cca4-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="1cca4-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="1cca4-344">**非描述萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="1cca4-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="1cca4-345">\*.\*</span></span>

- <span data-ttu-id="1cca4-346">**中間的萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="1cca4-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="1cca4-347">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="1cca4-347">conto\*so.com</span></span>
  - <span data-ttu-id="1cca4-348">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="1cca4-348">conto~so.com</span></span>

- <span data-ttu-id="1cca4-349">**兩個萬用字元**</span><span class="sxs-lookup"><span data-stu-id="1cca4-349">**Double wildcards**</span></span>

  - <span data-ttu-id="1cca4-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="1cca4-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="1cca4-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="1cca4-351">contoso.com/\*/\*</span></span>
