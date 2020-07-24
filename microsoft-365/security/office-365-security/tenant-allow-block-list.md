---
title: 在承租人允許/封鎖清單中管理您的允許和封鎖的 URLs 和檔案
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
description: 系統管理員可以瞭解如何在安全性 & 合規性中心的「租使用者支援/封鎖」清單中設定 URL 和檔專案。
ms.openlocfilehash: db34abf28b5ead8106eb0b1447052d63072b2da3
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391563"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-103">管理用戶允許/封鎖清單中的 URL 和檔案</span><span class="sxs-lookup"><span data-stu-id="d40da-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="d40da-104">本主題中所述的功能包括預覽、可能變更，而且無法在所有的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="d40da-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="d40da-105">在未使用 Exchange online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中使用信箱的 Microsoft 365 組織中，您可能會反對 EOP 篩選判定。</span><span class="sxs-lookup"><span data-stu-id="d40da-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="d40da-106">例如，正確的郵件可能會標示為壞的郵件（誤報），或可能允許透過錯誤的郵件（誤報）。</span><span class="sxs-lookup"><span data-stu-id="d40da-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="d40da-107">Security & 合規性中心內的承租人 Allow/封鎖清單可讓您手動覆寫 Microsoft 365 篩選 verdicts。</span><span class="sxs-lookup"><span data-stu-id="d40da-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="d40da-108">承租人允許/封鎖清單是在郵件流程期間和使用者按一下時使用。</span><span class="sxs-lookup"><span data-stu-id="d40da-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="d40da-109">您可以在 [承租人允許/封鎖] 清單中指定要允許或封鎖的 URLs 和檔案。</span><span class="sxs-lookup"><span data-stu-id="d40da-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="d40da-110">本主題說明如何在 Security & 合規性中心或 PowerShell （Exchange Online PowerShell 中，使用 Exchange Online 中的信箱的 Microsoft 365 組織），在 [Exchange Online] 中設定專案，在沒有 Exchange Online 信箱的組織中，使用獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d40da-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d40da-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="d40da-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d40da-112">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="d40da-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d40da-113">若要直接移至「**租使用者允許/封鎖清單**」頁面，請使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="d40da-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="d40da-114">您可以使用檔案的 SHA256 雜湊值來指定檔案。</span><span class="sxs-lookup"><span data-stu-id="d40da-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="d40da-115">若要在 Windows 中尋找檔案的 SHA256 雜湊值，請在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d40da-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="d40da-116">例如，此值可能為 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`。</span><span class="sxs-lookup"><span data-stu-id="d40da-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="d40da-117">不允許感知雜湊（pHash）值。</span><span class="sxs-lookup"><span data-stu-id="d40da-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="d40da-118">您可以在本主題稍後的[承租人 Allow/封鎖清單區段之 url 語法](#url-syntax-for-the-tenant-allowblock-list)中說明可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="d40da-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="d40da-119">承租人允許/封鎖清單可為 URLs 和500專案提供檔案雜湊的最大值為500專案。</span><span class="sxs-lookup"><span data-stu-id="d40da-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="d40da-120">專案應該在15分鐘內生效。</span><span class="sxs-lookup"><span data-stu-id="d40da-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="d40da-121">封鎖專案優先于允許專案。</span><span class="sxs-lookup"><span data-stu-id="d40da-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="d40da-122">根據預設，承租人允許/封鎖清單中的專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="d40da-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="d40da-123">您可以指定日期或將其設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="d40da-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="d40da-124">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d40da-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d40da-125">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d40da-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d40da-126">您必須已獲派權限，才能進行此主題中的程序:</span><span class="sxs-lookup"><span data-stu-id="d40da-126">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="d40da-127">若要從 [承租人允許/封鎖] 清單中新增及移除值，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="d40da-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d40da-128">**組織管理** 或 [安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md) 的 **安全性系統管理員**。 </span><span class="sxs-lookup"><span data-stu-id="d40da-128">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d40da-129">**組織管理** 或 [線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **檢疫管理**。</span><span class="sxs-lookup"><span data-stu-id="d40da-129">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="d40da-130">若要對租使用者 Allow/封鎖清單進行唯讀存取，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="d40da-130">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d40da-131">[安全性與合規性中心](permissions-in-the-security-and-compliance-center.md) 中的 **安全讀者**。</span><span class="sxs-lookup"><span data-stu-id="d40da-131">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d40da-132">[線上交換](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅檢視組織管理**。</span><span class="sxs-lookup"><span data-stu-id="d40da-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-133">使用安全性 & 規範中心在承租人允許/封鎖清單中建立 URL 專案</span><span class="sxs-lookup"><span data-stu-id="d40da-133">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d40da-134">如需 URL 專案之語法的詳細資訊，請參閱本主題稍後的[承租人 Allow/封鎖清單區段的 URL 語法](#url-syntax-for-the-tenant-allowblock-list)。</span><span class="sxs-lookup"><span data-stu-id="d40da-134">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="d40da-135">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="d40da-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d40da-136">在 [**租使用者允許/封鎖清單**] 頁面上，確認已選取 [ **URLs** ] 索引標籤，然後按一下 [**新增**]</span><span class="sxs-lookup"><span data-stu-id="d40da-136">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="d40da-137">在出現的 [**新增 URLs** ] 浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="d40da-137">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d40da-138">**使用萬用字元新增 URLs**：每行輸入一個 URL，最多20個。</span><span class="sxs-lookup"><span data-stu-id="d40da-138">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="d40da-139">**封鎖/允許**：選取是否要**允許**或**封鎖**指定的 URLs。</span><span class="sxs-lookup"><span data-stu-id="d40da-139">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="d40da-140">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="d40da-140">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="d40da-141">確認設定已關閉（ ![ 關閉切換 ](../../media/scc-toggle-off.png) ），並使用 [**到期**日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="d40da-141">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="d40da-142">或</span><span class="sxs-lookup"><span data-stu-id="d40da-142">or</span></span>

     - <span data-ttu-id="d40da-143">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="d40da-143">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="d40da-145">.</span><span class="sxs-lookup"><span data-stu-id="d40da-145">.</span></span>

   - <span data-ttu-id="d40da-146">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="d40da-146">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="d40da-147">完成後，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d40da-147">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-148">使用安全性 & 規範中心在承租人允許/封鎖清單中建立檔案專案</span><span class="sxs-lookup"><span data-stu-id="d40da-148">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="d40da-149">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="d40da-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d40da-150">在 [**租使用者允許/封鎖清單** **] 頁面**上，選取 [檔案] 索引標籤，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d40da-150">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="d40da-151">在出現的 [**新增檔**] 浮出視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="d40da-151">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d40da-152">**新增檔案雜湊**：每行輸入一個 SHA256 雜湊值，最多20個。</span><span class="sxs-lookup"><span data-stu-id="d40da-152">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="d40da-153">**封鎖/允許**：選取是否要**允許**或**封鎖**指定的檔案。</span><span class="sxs-lookup"><span data-stu-id="d40da-153">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="d40da-154">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="d40da-154">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="d40da-155">確認設定已關閉（ ![ 關閉切換 ](../../media/scc-toggle-off.png) ），並使用 [**到期**日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="d40da-155">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="d40da-156">或</span><span class="sxs-lookup"><span data-stu-id="d40da-156">or</span></span>

     - <span data-ttu-id="d40da-157">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="d40da-157">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="d40da-159">.</span><span class="sxs-lookup"><span data-stu-id="d40da-159">.</span></span>

   - <span data-ttu-id="d40da-160">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="d40da-160">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="d40da-161">完成後，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d40da-161">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-162">使用安全性 & 合規性中心，在承租人允許/封鎖清單中查看 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="d40da-162">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="d40da-163">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="d40da-163">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d40da-164">選取 [ **URLs** ] 索引標籤**或 [檔案**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d40da-164">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="d40da-165">按一下下列欄標題，以遞增或遞減順序排序：</span><span class="sxs-lookup"><span data-stu-id="d40da-165">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="d40da-166">**值**： URL 或檔雜湊。</span><span class="sxs-lookup"><span data-stu-id="d40da-166">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="d40da-167">**動作**：**封鎖**或**允許**。</span><span class="sxs-lookup"><span data-stu-id="d40da-167">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="d40da-168">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="d40da-168">**Last updated date**</span></span>
- <span data-ttu-id="d40da-169">**有效期**</span><span class="sxs-lookup"><span data-stu-id="d40da-169">**Expiration date**</span></span>
- <span data-ttu-id="d40da-170">**附註**</span><span class="sxs-lookup"><span data-stu-id="d40da-170">**Note**</span></span>

<span data-ttu-id="d40da-171">按一下 [**群組**]，依**動作**（**封鎖**或**允許**）或**無**分組專案。</span><span class="sxs-lookup"><span data-stu-id="d40da-171">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="d40da-172">按一下 [**搜尋**]，輸入全部或部分的 URL 或檔值，然後按 enter 以尋找特定值。</span><span class="sxs-lookup"><span data-stu-id="d40da-172">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="d40da-173">完成後，請按一下 [**清除搜尋** ![ 清除搜尋] 圖示 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="d40da-173">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="d40da-174">按一下 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="d40da-174">Click **Filter**.</span></span> <span data-ttu-id="d40da-175">在出現的 [**篩選**] 浮出控制項中，設定下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="d40da-175">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="d40da-176">**動作**：選取 [**允許**]、[**封鎖**] 或 [兩者]。</span><span class="sxs-lookup"><span data-stu-id="d40da-176">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="d40da-177">**永不過期**：選取 [關閉] （[ ![ 關閉] 或 [開啟] ](../../media/scc-toggle-off.png) ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ）。</span><span class="sxs-lookup"><span data-stu-id="d40da-177">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="d40da-178">**上次更新**：選取 [開始日期] （[**寄件者**]）**、[結束**日期] 或 [兩者]。</span><span class="sxs-lookup"><span data-stu-id="d40da-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="d40da-179">**到期日**：選取 [開始日期] （[**寄件者**]）、[結束日期]**或 [兩者**]。</span><span class="sxs-lookup"><span data-stu-id="d40da-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="d40da-180">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="d40da-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="d40da-181">若要清除現有篩選，請按一下 [**篩選**]，然後在出現的 [**篩選**] 浮出控制項中按一下 [**清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="d40da-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-182">使用安全性 & 合規性中心，修改承租人允許/封鎖清單中的 URL 和檔專案</span><span class="sxs-lookup"><span data-stu-id="d40da-182">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d40da-183">您無法修改 URL 或檔值本身。</span><span class="sxs-lookup"><span data-stu-id="d40da-183">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="d40da-184">相反地，您必須刪除該專案，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="d40da-184">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="d40da-185">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="d40da-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d40da-186">選取 [ **URLs** ] 索引標籤**或 [檔案**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d40da-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="d40da-187">選取您要修改的專案，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="d40da-187">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="d40da-188">在出現的浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="d40da-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d40da-189">**封鎖/允許**：選取 [**允許**] 或 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="d40da-189">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="d40da-190">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="d40da-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="d40da-191">確認設定已關閉（ ![ 關閉切換 ](../../media/scc-toggle-off.png) ），並使用 [**到期**日] 方塊來指定輸入專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="d40da-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="d40da-192">或</span><span class="sxs-lookup"><span data-stu-id="d40da-192">or</span></span>

     - <span data-ttu-id="d40da-193">將切換向右移動，將專案設定為永不過期：</span><span class="sxs-lookup"><span data-stu-id="d40da-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="d40da-195">.</span><span class="sxs-lookup"><span data-stu-id="d40da-195">.</span></span>

   - <span data-ttu-id="d40da-196">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="d40da-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="d40da-197">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d40da-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-198">使用安全性 & 規範中心從承租人允許/封鎖清單中移除 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="d40da-198">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="d40da-199">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="d40da-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d40da-200">選取 [ **URLs** ] 索引標籤**或 [檔案**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d40da-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="d40da-201">選取您要移除的專案，然後按一下 [**刪除** ![ 刪除圖示] ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="d40da-201">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="d40da-202">在出現的警告對話方塊中，按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="d40da-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-203">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="d40da-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-204">使用 PowerShell 在承租人允許/封鎖清單中新增 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="d40da-204">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d40da-205">若要在承租人允許/封鎖清單中新增 URL 和檔案專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d40da-205">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="d40da-206">這個範例會新增 contoso.com 及所有子域的 URL 封鎖專案（例如，contoso.com、www.contoso.com 及 xyz.abc.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="d40da-206">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="d40da-207">因為我們未使用 ExpirationDate 或 NoExpiration 參數，所以專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="d40da-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="d40da-208">此範例會為永不到期的指定檔案新增檔案允許專案。</span><span class="sxs-lookup"><span data-stu-id="d40da-208">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="d40da-209">如需詳細的語法及參數資訊，請參閱[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="d40da-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-210">使用 PowerShell 在承租人允許/封鎖清單中查看 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="d40da-210">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d40da-211">若要在 [租使用者允許/封鎖] 清單中查看 URL 和檔案專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d40da-211">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="d40da-212">本範例會傳回所有封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="d40da-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="d40da-213">此範例會傳回指定之檔案雜湊值的資訊。</span><span class="sxs-lookup"><span data-stu-id="d40da-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="d40da-214">如需詳細的語法及參數資訊，請參閱[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="d40da-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-215">使用 PowerShell 修改承租人 Allow/封鎖清單中的 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="d40da-215">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d40da-216">您無法修改 URL 或檔值本身。</span><span class="sxs-lookup"><span data-stu-id="d40da-216">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="d40da-217">相反地，您必須刪除該專案，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="d40da-217">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="d40da-218">若要修改承租人 Allow/封鎖清單中的 URL 和檔案專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d40da-218">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="d40da-219">本範例會變更指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="d40da-219">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="d40da-220">如需詳細的語法及參數資訊，請參閱[Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="d40da-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-221">使用 PowerShell 從承租人允許/封鎖清單移除 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="d40da-221">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="d40da-222">若要從承租人允許/封鎖清單移除 URL 和檔案專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="d40da-222">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="d40da-223">此範例會從承租人允許/封鎖清單中移除指定的 URL 專案。</span><span class="sxs-lookup"><span data-stu-id="d40da-223">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="d40da-224">如需詳細的語法及參數資訊，請參閱[Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="d40da-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="d40da-225">承租人允許/封鎖清單的 URL 語法</span><span class="sxs-lookup"><span data-stu-id="d40da-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="d40da-226">允許 IP4v 和 IPv6 位址，但不會 TCP/UDP 埠。</span><span class="sxs-lookup"><span data-stu-id="d40da-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="d40da-227">不允許副檔名副檔名（例如，test.pdf）。</span><span class="sxs-lookup"><span data-stu-id="d40da-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="d40da-228">不支援 Unicode，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="d40da-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="d40da-229">如果下列所有陳述皆為 true，則允許主機名稱：</span><span class="sxs-lookup"><span data-stu-id="d40da-229">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="d40da-230">主機名稱包含句點。</span><span class="sxs-lookup"><span data-stu-id="d40da-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="d40da-231">句點的左側至少有一個字元。</span><span class="sxs-lookup"><span data-stu-id="d40da-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="d40da-232">句點右側至少有兩個字元。</span><span class="sxs-lookup"><span data-stu-id="d40da-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="d40da-233">例如， `t.co` 允許; `.com` 或是 `contoso.` 不允許。</span><span class="sxs-lookup"><span data-stu-id="d40da-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="d40da-234">不暗含子路徑。</span><span class="sxs-lookup"><span data-stu-id="d40da-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="d40da-235">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="d40da-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="d40da-236">在下列案例中，允許使用萬用字元（\*）：</span><span class="sxs-lookup"><span data-stu-id="d40da-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="d40da-237">左邊的萬用字元必須後接句點，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="d40da-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="d40da-238">例如， `*.contoso.com` 允許; `*contoso.com` 是不允許的。</span><span class="sxs-lookup"><span data-stu-id="d40da-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="d40da-239">右萬用字元必須跟隨正斜線（/）以指定路徑。</span><span class="sxs-lookup"><span data-stu-id="d40da-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="d40da-240">例如， `contoso.com/*` 允許; `contoso.com*` 或是 `contoso.com/ab*` 不允許。</span><span class="sxs-lookup"><span data-stu-id="d40da-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="d40da-241">所有的子路徑都不是以右邊的萬用字元隱含。</span><span class="sxs-lookup"><span data-stu-id="d40da-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="d40da-242">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="d40da-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="d40da-243">`*.com*`無效（不是可解析的網域，正確的萬用字元不跟隨正斜線）。</span><span class="sxs-lookup"><span data-stu-id="d40da-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="d40da-244">IP 位址中不允許使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="d40da-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="d40da-245">在下列案例中，可以使用波形符號（~）：</span><span class="sxs-lookup"><span data-stu-id="d40da-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="d40da-246">左波形符表示網域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="d40da-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="d40da-247">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="d40da-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="d40da-248">包含通訊協定的 URL 專案（例如、 `http://` 、 `https://` 或 `ftp://` ）將會失敗，因為 url 專案會套用至所有通訊協定。</span><span class="sxs-lookup"><span data-stu-id="d40da-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="d40da-249">不支援或不需要使用者名稱或密碼。</span><span class="sxs-lookup"><span data-stu-id="d40da-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="d40da-250">引號（' 或 "）是不正確字元。</span><span class="sxs-lookup"><span data-stu-id="d40da-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="d40da-251">URL 應盡可能包括所有重新導向。</span><span class="sxs-lookup"><span data-stu-id="d40da-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="d40da-252">URL 專案案例</span><span class="sxs-lookup"><span data-stu-id="d40da-252">URL entry scenarios</span></span>

<span data-ttu-id="d40da-253">有效的 URL 專案及其結果將在下列各節中說明。</span><span class="sxs-lookup"><span data-stu-id="d40da-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="d40da-254">案例：沒有萬用字元</span><span class="sxs-lookup"><span data-stu-id="d40da-254">Scenario: No wildcards</span></span>

<span data-ttu-id="d40da-255">**專案**：`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="d40da-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="d40da-256">**允許相符**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="d40da-257">**允許不符合**：</span><span class="sxs-lookup"><span data-stu-id="d40da-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="d40da-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-258">abc-contoso.com</span></span>
  - <span data-ttu-id="d40da-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d40da-259">contoso.com/a</span></span>
  - <span data-ttu-id="d40da-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="d40da-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="d40da-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="d40da-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-263">www.contoso.com</span></span>
  - <span data-ttu-id="d40da-264">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="d40da-264">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="d40da-265">**Block match**：</span><span class="sxs-lookup"><span data-stu-id="d40da-265">**Block match**:</span></span>

  - <span data-ttu-id="d40da-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-266">contoso.com</span></span>
  - <span data-ttu-id="d40da-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d40da-267">contoso.com/a</span></span>
  - <span data-ttu-id="d40da-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="d40da-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="d40da-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="d40da-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-271">www.contoso.com</span></span>
  - <span data-ttu-id="d40da-272">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="d40da-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="d40da-273">**不符合的區塊**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="d40da-274">案例：左側萬用字元（子域）</span><span class="sxs-lookup"><span data-stu-id="d40da-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="d40da-275">**專案**：`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="d40da-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="d40da-276">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="d40da-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d40da-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-277">www.contoso.com</span></span>
  - <span data-ttu-id="d40da-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="d40da-279">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="d40da-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d40da-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-280">123contoso.com</span></span>
  - <span data-ttu-id="d40da-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-281">contoso.com</span></span>
  - <span data-ttu-id="d40da-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="d40da-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="d40da-283">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="d40da-284">案例：路徑頂端的右萬用字元</span><span class="sxs-lookup"><span data-stu-id="d40da-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="d40da-285">**專案**：`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="d40da-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="d40da-286">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="d40da-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d40da-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="d40da-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="d40da-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="d40da-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="d40da-289">contoso/a/？ q = joe@t .com</span><span class="sxs-lookup"><span data-stu-id="d40da-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="d40da-290">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="d40da-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d40da-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-291">contoso.com</span></span>
  - <span data-ttu-id="d40da-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d40da-292">contoso.com/a</span></span>
  - <span data-ttu-id="d40da-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-293">www.contoso.com</span></span>
  - <span data-ttu-id="d40da-294">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="d40da-294">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="d40da-295">案例：左波形符</span><span class="sxs-lookup"><span data-stu-id="d40da-295">Scenario: Left tilde</span></span>

<span data-ttu-id="d40da-296">**專案**：`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="d40da-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="d40da-297">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="d40da-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d40da-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-298">contoso.com</span></span>
  - <span data-ttu-id="d40da-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-299">www.contoso.com</span></span>
  - <span data-ttu-id="d40da-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="d40da-301">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="d40da-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d40da-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-302">123contoso.com</span></span>
  - <span data-ttu-id="d40da-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="d40da-303">contoso.com/abc</span></span>
  - <span data-ttu-id="d40da-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="d40da-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="d40da-305">案例：右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="d40da-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="d40da-306">**專案**：`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="d40da-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="d40da-307">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="d40da-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d40da-308">contoso （.com）/？ q = whatever@fabrikam .com</span><span class="sxs-lookup"><span data-stu-id="d40da-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="d40da-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d40da-309">contoso.com/a</span></span>
  - <span data-ttu-id="d40da-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="d40da-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="d40da-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="d40da-311">contoso.com/ab</span></span>
  - <span data-ttu-id="d40da-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="d40da-312">contoso.com/b</span></span>
  - <span data-ttu-id="d40da-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="d40da-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="d40da-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="d40da-314">contoso.com/ba</span></span>

- <span data-ttu-id="d40da-315">**允許不符合**或**不符合的封鎖**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="d40da-316">案例： Left 通配子域和右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="d40da-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="d40da-317">**專案**：`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="d40da-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="d40da-318">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="d40da-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d40da-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="d40da-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="d40da-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="d40da-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="d40da-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d40da-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="d40da-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="d40da-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="d40da-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="d40da-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="d40da-324">**允許不符合**或**不符合的封鎖**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="d40da-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="d40da-325">案例：左和右顎化符</span><span class="sxs-lookup"><span data-stu-id="d40da-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="d40da-326">**專案**：`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="d40da-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="d40da-327">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="d40da-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d40da-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-328">contoso.com</span></span>
  - <span data-ttu-id="d40da-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d40da-329">contoso.com/a</span></span>
  - <span data-ttu-id="d40da-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-330">www.contoso.com</span></span>
  - <span data-ttu-id="d40da-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="d40da-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="d40da-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="d40da-333">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="d40da-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d40da-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-334">123contoso.com</span></span>
  - <span data-ttu-id="d40da-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="d40da-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="d40da-336">案例： IP 位址</span><span class="sxs-lookup"><span data-stu-id="d40da-336">Scenario: IP address</span></span>

<span data-ttu-id="d40da-337">**專案**：`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="d40da-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="d40da-338">**允許**比對和**區塊相符**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="d40da-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="d40da-339">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="d40da-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d40da-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="d40da-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="d40da-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="d40da-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="d40da-342">具有右萬用字元的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="d40da-342">IP address with right wildcard</span></span>

<span data-ttu-id="d40da-343">**專案**：`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="d40da-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="d40da-344">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="d40da-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d40da-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="d40da-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="d40da-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="d40da-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="d40da-347">無效專案的範例</span><span class="sxs-lookup"><span data-stu-id="d40da-347">Examples of invalid entries</span></span>

<span data-ttu-id="d40da-348">下列專案是不正確：</span><span class="sxs-lookup"><span data-stu-id="d40da-348">The following entries are invalid:</span></span>

- <span data-ttu-id="d40da-349">**遺失或不正確網域值**：</span><span class="sxs-lookup"><span data-stu-id="d40da-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="d40da-350">尚未</span><span class="sxs-lookup"><span data-stu-id="d40da-350">contoso</span></span>
  - <span data-ttu-id="d40da-351">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="d40da-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="d40da-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="d40da-352">\*.com</span></span>
  - <span data-ttu-id="d40da-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="d40da-353">\*.pdf</span></span>

- <span data-ttu-id="d40da-354">**文字上的萬用字元，或不含間距的字元**：</span><span class="sxs-lookup"><span data-stu-id="d40da-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="d40da-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="d40da-355">\*contoso.com</span></span>
  - <span data-ttu-id="d40da-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="d40da-356">contoso.com\*</span></span>
  - <span data-ttu-id="d40da-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="d40da-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="d40da-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="d40da-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="d40da-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="d40da-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="d40da-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="d40da-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="d40da-361">**含埠的 IP 位址**：</span><span class="sxs-lookup"><span data-stu-id="d40da-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="d40da-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="d40da-362">contoso.com:443</span></span>
  - <span data-ttu-id="d40da-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="d40da-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="d40da-364">**非描述萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="d40da-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="d40da-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="d40da-365">\*.\*</span></span>

- <span data-ttu-id="d40da-366">**中間的萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="d40da-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="d40da-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="d40da-367">conto\*so.com</span></span>
  - <span data-ttu-id="d40da-368">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="d40da-368">conto~so.com</span></span>

- <span data-ttu-id="d40da-369">**兩個萬用字元**</span><span class="sxs-lookup"><span data-stu-id="d40da-369">**Double wildcards**</span></span>

  - <span data-ttu-id="d40da-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="d40da-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="d40da-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="d40da-371">contoso.com/\*/\*</span></span>
