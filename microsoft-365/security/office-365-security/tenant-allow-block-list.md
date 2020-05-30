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
ROBOTS: NOINDEX, NOFOLLOW
description: 系統管理員可以瞭解如何在安全性 & 合規性中心的「租使用者支援/封鎖」清單中設定 URL 和檔專案。
ms.openlocfilehash: b3a25458bbde2b3a78cfecc60ccb75fe298013f7
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419254"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-103">管理承租人允許/封鎖清單中的 URLs 和檔案</span><span class="sxs-lookup"><span data-stu-id="5aabe-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="5aabe-104">本主題中所述的功能包括預覽、可能變更，而且無法在所有的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="5aabe-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="5aabe-105">在未使用 Exchange online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）組織中使用信箱的 Microsoft 365 組織中，您可能會反對 EOP 篩選判定。</span><span class="sxs-lookup"><span data-stu-id="5aabe-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="5aabe-106">例如，正確的郵件可能會標示為壞的郵件（誤報），或可能允許透過錯誤的郵件（誤報）。</span><span class="sxs-lookup"><span data-stu-id="5aabe-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="5aabe-107">Security & 合規性中心內的承租人 Allow/封鎖清單可讓您手動覆寫 Microsoft 365 篩選 verdicts。</span><span class="sxs-lookup"><span data-stu-id="5aabe-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="5aabe-108">承租人允許/封鎖清單是在郵件流程期間和使用者按一下時使用。</span><span class="sxs-lookup"><span data-stu-id="5aabe-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="5aabe-109">您可以在 [承租人允許/封鎖] 清單中指定要允許或封鎖的 URLs 和檔案。</span><span class="sxs-lookup"><span data-stu-id="5aabe-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="5aabe-110">本主題說明如何在 Security & 合規性中心或 PowerShell （Exchange Online PowerShell 中，使用 Exchange Online 中的信箱的 Microsoft 365 組織），在 [Exchange Online] 中設定專案，在沒有 Exchange Online 信箱的組織中，使用獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5aabe-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5aabe-111">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="5aabe-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5aabe-112">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="5aabe-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5aabe-113">若要直接移至「**租使用者允許/封鎖清單**」頁面，請使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="5aabe-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="5aabe-114">您可以使用檔案的 SHA256 雜湊值來指定檔案。</span><span class="sxs-lookup"><span data-stu-id="5aabe-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="5aabe-115">若要在 Windows 中尋找檔案的 SHA256 雜湊值，請在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5aabe-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="5aabe-116">例如，此值可能為 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`。</span><span class="sxs-lookup"><span data-stu-id="5aabe-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="5aabe-117">不允許感知雜湊（pHash）值。</span><span class="sxs-lookup"><span data-stu-id="5aabe-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="5aabe-118">您可以在本主題稍後的[承租人 Allow/封鎖清單區段之 url 語法](#url-syntax-for-the-tenant-allowblock-list)中說明可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="5aabe-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="5aabe-119">承租人允許/封鎖清單可為 URLs 和500專案提供檔案雜湊的最大值為500專案。</span><span class="sxs-lookup"><span data-stu-id="5aabe-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="5aabe-120">專案應該在15分鐘內生效。</span><span class="sxs-lookup"><span data-stu-id="5aabe-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="5aabe-121">封鎖專案優先于允許專案。</span><span class="sxs-lookup"><span data-stu-id="5aabe-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="5aabe-122">根據預設，承租人允許/封鎖清單中的專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="5aabe-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="5aabe-123">您可以指定日期或將其設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="5aabe-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="5aabe-124">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5aabe-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5aabe-125">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5aabe-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5aabe-126">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="5aabe-126">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="5aabe-127">若要從 [承租人允許/封鎖] 清單中新增及移除值，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="5aabe-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="5aabe-128">若要取得租使用者 Allow/封鎖清單的唯讀許可權，您必須是**Security Reader**角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="5aabe-128">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="5aabe-129">如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5aabe-129">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-130">使用安全性 & 規範中心在承租人允許/封鎖清單中建立 URL 專案</span><span class="sxs-lookup"><span data-stu-id="5aabe-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5aabe-131">如需 URL 專案之語法的詳細資訊，請參閱本主題稍後的[承租人 Allow/封鎖清單區段的 URL 語法](#url-syntax-for-the-tenant-allowblock-list)。</span><span class="sxs-lookup"><span data-stu-id="5aabe-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="5aabe-132">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="5aabe-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5aabe-133">在 [**租使用者允許/封鎖清單**] 頁面上，確認已選取 [ **URLs** ] 索引標籤，然後按一下 [**新增**]</span><span class="sxs-lookup"><span data-stu-id="5aabe-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="5aabe-134">在出現的 [**新增 URLs** ] 浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="5aabe-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="5aabe-135">**使用萬用字元新增 URLs**：每行輸入一個 URL，最多20個。</span><span class="sxs-lookup"><span data-stu-id="5aabe-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="5aabe-136">**封鎖/允許**：選取是否要**允許**或**封鎖**指定的 URLs。</span><span class="sxs-lookup"><span data-stu-id="5aabe-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="5aabe-137">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="5aabe-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="5aabe-138">確認設定已關閉（ ![ 關閉切換 ](../../media/scc-toggle-off.png) ），並使用 [**到期**日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="5aabe-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="5aabe-139">或</span><span class="sxs-lookup"><span data-stu-id="5aabe-139">or</span></span>

     - <span data-ttu-id="5aabe-140">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="5aabe-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="5aabe-142">.</span><span class="sxs-lookup"><span data-stu-id="5aabe-142">.</span></span>

   - <span data-ttu-id="5aabe-143">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="5aabe-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="5aabe-144">完成後，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="5aabe-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-145">使用安全性 & 規範中心在承租人允許/封鎖清單中建立檔案專案</span><span class="sxs-lookup"><span data-stu-id="5aabe-145">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5aabe-146">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="5aabe-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5aabe-147">在 [**租使用者允許/封鎖清單** **] 頁面**上，選取 [檔案] 索引標籤，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="5aabe-147">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="5aabe-148">在出現的 [**新增檔**] 浮出視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="5aabe-148">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="5aabe-149">**新增檔案雜湊**：每行輸入一個 SHA256 雜湊值，最多20個。</span><span class="sxs-lookup"><span data-stu-id="5aabe-149">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="5aabe-150">**封鎖/允許**：選取是否要**允許**或**封鎖**指定的檔案。</span><span class="sxs-lookup"><span data-stu-id="5aabe-150">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="5aabe-151">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="5aabe-151">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="5aabe-152">確認設定已關閉（ ![ 關閉切換 ](../../media/scc-toggle-off.png) ），並使用 [**到期**日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="5aabe-152">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="5aabe-153">或</span><span class="sxs-lookup"><span data-stu-id="5aabe-153">or</span></span>

     - <span data-ttu-id="5aabe-154">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="5aabe-154">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="5aabe-156">.</span><span class="sxs-lookup"><span data-stu-id="5aabe-156">.</span></span>

   - <span data-ttu-id="5aabe-157">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="5aabe-157">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="5aabe-158">完成後，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="5aabe-158">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-159">使用安全性 & 合規性中心，在承租人允許/封鎖清單中查看 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="5aabe-159">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5aabe-160">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="5aabe-160">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5aabe-161">選取 [ **URLs** ] 索引標籤**或 [檔案**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5aabe-161">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="5aabe-162">按一下下列欄標題，以遞增或遞減順序排序：</span><span class="sxs-lookup"><span data-stu-id="5aabe-162">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="5aabe-163">**值**： URL 或檔雜湊。</span><span class="sxs-lookup"><span data-stu-id="5aabe-163">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="5aabe-164">**動作**：**封鎖**或**允許**。</span><span class="sxs-lookup"><span data-stu-id="5aabe-164">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="5aabe-165">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="5aabe-165">**Last updated date**</span></span>
- <span data-ttu-id="5aabe-166">**有效期**</span><span class="sxs-lookup"><span data-stu-id="5aabe-166">**Expiration date**</span></span>
- <span data-ttu-id="5aabe-167">**附註**</span><span class="sxs-lookup"><span data-stu-id="5aabe-167">**Note**</span></span>

<span data-ttu-id="5aabe-168">按一下 [**群組**]，依**動作**（**封鎖**或**允許**）或**無**分組專案。</span><span class="sxs-lookup"><span data-stu-id="5aabe-168">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="5aabe-169">按一下 [**搜尋**]，輸入全部或部分的 URL 或檔值，然後按 enter 以尋找特定值。</span><span class="sxs-lookup"><span data-stu-id="5aabe-169">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="5aabe-170">完成後，請按一下 [**清除搜尋** ![ 清除搜尋] 圖示 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="5aabe-170">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="5aabe-171">按一下 [**篩選**]。</span><span class="sxs-lookup"><span data-stu-id="5aabe-171">Click **Filter**.</span></span> <span data-ttu-id="5aabe-172">在出現的 [**篩選**] 浮出控制項中，設定下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="5aabe-172">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="5aabe-173">**動作**：選取 [**允許**]、[**封鎖**] 或 [兩者]。</span><span class="sxs-lookup"><span data-stu-id="5aabe-173">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="5aabe-174">**永不過期**：選取 [關閉] （[ ![ 關閉] 或 [開啟] ](../../media/scc-toggle-off.png) ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ）。</span><span class="sxs-lookup"><span data-stu-id="5aabe-174">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="5aabe-175">**上次更新**：選取 [開始日期] （[**寄件者**]）**、[結束**日期] 或 [兩者]。</span><span class="sxs-lookup"><span data-stu-id="5aabe-175">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="5aabe-176">**到期日**：選取 [開始日期] （[**寄件者**]）、[結束日期]**或 [兩者**]。</span><span class="sxs-lookup"><span data-stu-id="5aabe-176">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="5aabe-177">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="5aabe-177">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="5aabe-178">若要清除現有篩選，請按一下 [**篩選**]，然後在出現的 [**篩選**] 浮出控制項中按一下 [**清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="5aabe-178">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-179">使用安全性 & 合規性中心，修改承租人允許/封鎖清單中的 URL 和檔專案</span><span class="sxs-lookup"><span data-stu-id="5aabe-179">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5aabe-180">您無法修改 URL 或檔值本身。</span><span class="sxs-lookup"><span data-stu-id="5aabe-180">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="5aabe-181">相反地，您必須刪除該專案，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="5aabe-181">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="5aabe-182">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="5aabe-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5aabe-183">選取 [ **URLs** ] 索引標籤**或 [檔案**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5aabe-183">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="5aabe-184">選取您要修改的專案，然後按一下 [**編輯** ![ 編輯圖示] ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="5aabe-184">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="5aabe-185">在出現的浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="5aabe-185">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="5aabe-186">**封鎖/允許**：選取 [**允許**] 或 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="5aabe-186">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="5aabe-187">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="5aabe-187">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="5aabe-188">確認設定已關閉（ ![ 關閉切換 ](../../media/scc-toggle-off.png) ），並使用 [**到期**日] 方塊來指定輸入專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="5aabe-188">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="5aabe-189">或</span><span class="sxs-lookup"><span data-stu-id="5aabe-189">or</span></span>

     - <span data-ttu-id="5aabe-190">將切換向右移動，將專案設定為永不過期：</span><span class="sxs-lookup"><span data-stu-id="5aabe-190">Move the toggle to the right to configure the entry to never expire:</span></span> ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="5aabe-192">.</span><span class="sxs-lookup"><span data-stu-id="5aabe-192">.</span></span>

   - <span data-ttu-id="5aabe-193">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="5aabe-193">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="5aabe-194">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5aabe-194">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-195">使用安全性 & 規範中心從承租人允許/封鎖清單中移除 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="5aabe-195">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5aabe-196">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="5aabe-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5aabe-197">選取 [ **URLs** ] 索引標籤**或 [檔案**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5aabe-197">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="5aabe-198">選取您要移除的專案，然後按一下 [**刪除** ![ 刪除圖示] ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="5aabe-198">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="5aabe-199">在出現的警告對話方塊中，按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="5aabe-199">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-200">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="5aabe-200">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-201">使用 PowerShell 在承租人允許/封鎖清單中新增 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="5aabe-201">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5aabe-202">若要在承租人允許/封鎖清單中新增 URL 和檔案專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="5aabe-202">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="5aabe-203">這個範例會新增 contoso.com 及所有子域的 URL 封鎖專案（例如，contoso.com、www.contoso.com 及 xyz.abc.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="5aabe-203">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="5aabe-204">因為我們未使用 ExpirationDate 或 NoExpiration 參數，所以專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="5aabe-204">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="5aabe-205">此範例會為永不到期的指定檔案新增檔案允許專案。</span><span class="sxs-lookup"><span data-stu-id="5aabe-205">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="5aabe-206">如需詳細的語法及參數資訊，請參閱[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="5aabe-206">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-207">使用 PowerShell 在承租人允許/封鎖清單中查看 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="5aabe-207">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5aabe-208">若要在 [租使用者允許/封鎖] 清單中查看 URL 和檔案專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="5aabe-208">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="5aabe-209">本範例會傳回所有封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="5aabe-209">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="5aabe-210">此範例會傳回指定之檔案雜湊值的資訊。</span><span class="sxs-lookup"><span data-stu-id="5aabe-210">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="5aabe-211">如需詳細的語法及參數資訊，請參閱[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="5aabe-211">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-212">使用 PowerShell 修改承租人 Allow/封鎖清單中的 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="5aabe-212">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5aabe-213">您無法修改 URL 或檔值本身。</span><span class="sxs-lookup"><span data-stu-id="5aabe-213">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="5aabe-214">相反地，您必須刪除該專案，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="5aabe-214">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="5aabe-215">若要修改承租人 Allow/封鎖清單中的 URL 和檔案專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="5aabe-215">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="5aabe-216">本範例會變更指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="5aabe-216">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="5aabe-217">如需詳細的語法及參數資訊，請參閱[Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="5aabe-217">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-218">使用 PowerShell 從承租人允許/封鎖清單移除 URL 和檔案專案</span><span class="sxs-lookup"><span data-stu-id="5aabe-218">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="5aabe-219">若要從承租人允許/封鎖清單移除 URL 和檔案專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="5aabe-219">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="5aabe-220">此範例會從承租人允許/封鎖清單中移除指定的 URL 專案。</span><span class="sxs-lookup"><span data-stu-id="5aabe-220">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="5aabe-221">如需詳細的語法及參數資訊，請參閱[Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="5aabe-221">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="5aabe-222">承租人允許/封鎖清單的 URL 語法</span><span class="sxs-lookup"><span data-stu-id="5aabe-222">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="5aabe-223">允許 IP4v 和 IPv6 位址，但不會 TCP/UDP 埠。</span><span class="sxs-lookup"><span data-stu-id="5aabe-223">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="5aabe-224">不允許副檔名副檔名（例如，[test .pdf]）。</span><span class="sxs-lookup"><span data-stu-id="5aabe-224">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="5aabe-225">不支援 Unicode，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="5aabe-225">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="5aabe-226">如果下列所有陳述皆為 true，則允許主機名稱：</span><span class="sxs-lookup"><span data-stu-id="5aabe-226">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="5aabe-227">主機名稱包含句點。</span><span class="sxs-lookup"><span data-stu-id="5aabe-227">The hostname contains a period.</span></span>
  - <span data-ttu-id="5aabe-228">句點的左側至少有一個字元。</span><span class="sxs-lookup"><span data-stu-id="5aabe-228">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="5aabe-229">句點右側至少有兩個字元。</span><span class="sxs-lookup"><span data-stu-id="5aabe-229">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="5aabe-230">例如， `t.co` 允許; `.com` 或是 `contoso.` 不允許。</span><span class="sxs-lookup"><span data-stu-id="5aabe-230">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="5aabe-231">不暗含子路徑。</span><span class="sxs-lookup"><span data-stu-id="5aabe-231">Subpaths are not implied.</span></span>

  <span data-ttu-id="5aabe-232">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="5aabe-232">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="5aabe-233">在下列案例中，允許使用萬用字元（\*）：</span><span class="sxs-lookup"><span data-stu-id="5aabe-233">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="5aabe-234">左邊的萬用字元必須後接句點，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="5aabe-234">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="5aabe-235">例如， `*.contoso.com` 允許; `*contoso.com` 是不允許的。</span><span class="sxs-lookup"><span data-stu-id="5aabe-235">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="5aabe-236">右萬用字元必須跟隨正斜線（/）以指定路徑。</span><span class="sxs-lookup"><span data-stu-id="5aabe-236">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="5aabe-237">例如， `contoso.com/*` 允許; `contoso.com*` 或是 `contoso.com/ab*` 不允許。</span><span class="sxs-lookup"><span data-stu-id="5aabe-237">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="5aabe-238">所有的子路徑都不是以右邊的萬用字元隱含。</span><span class="sxs-lookup"><span data-stu-id="5aabe-238">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="5aabe-239">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="5aabe-239">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="5aabe-240">`*.com*`無效（不是可解析的網域，正確的萬用字元不跟隨正斜線）。</span><span class="sxs-lookup"><span data-stu-id="5aabe-240">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="5aabe-241">IP 位址中不允許使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="5aabe-241">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="5aabe-242">在下列案例中，可以使用波形符號（~）：</span><span class="sxs-lookup"><span data-stu-id="5aabe-242">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="5aabe-243">左波形符表示網域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="5aabe-243">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="5aabe-244">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="5aabe-244">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="5aabe-245">包含通訊協定的 URL 專案（例如、 `http://` 、 `https://` 或 `ftp://` ）將會失敗，因為 url 專案會套用至所有通訊協定。</span><span class="sxs-lookup"><span data-stu-id="5aabe-245">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="5aabe-246">不支援或不需要使用者名稱或密碼。</span><span class="sxs-lookup"><span data-stu-id="5aabe-246">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="5aabe-247">引號（' 或 "）是不正確字元。</span><span class="sxs-lookup"><span data-stu-id="5aabe-247">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="5aabe-248">URL 應盡可能包括所有重新導向。</span><span class="sxs-lookup"><span data-stu-id="5aabe-248">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="5aabe-249">URL 專案案例</span><span class="sxs-lookup"><span data-stu-id="5aabe-249">URL entry scenarios</span></span>

<span data-ttu-id="5aabe-250">有效的 URL 專案及其結果將在下列各節中說明。</span><span class="sxs-lookup"><span data-stu-id="5aabe-250">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="5aabe-251">案例：沒有萬用字元</span><span class="sxs-lookup"><span data-stu-id="5aabe-251">Scenario: No wildcards</span></span>

<span data-ttu-id="5aabe-252">**專案**：`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="5aabe-252">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="5aabe-253">**允許相符**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-253">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="5aabe-254">**允許不符合**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-254">**Allow not matched**:</span></span>

  - <span data-ttu-id="5aabe-255">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-255">abc-contoso.com</span></span>
  - <span data-ttu-id="5aabe-256">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5aabe-256">contoso.com/a</span></span>
  - <span data-ttu-id="5aabe-257">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-257">payroll.contoso.com</span></span>
  - <span data-ttu-id="5aabe-258">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-258">test.com/contoso.com</span></span>
  - <span data-ttu-id="5aabe-259">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-259">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="5aabe-260">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-260">www.contoso.com</span></span>
  - <span data-ttu-id="5aabe-261">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="5aabe-261">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="5aabe-262">**Block match**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-262">**Block match**:</span></span>

  - <span data-ttu-id="5aabe-263">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-263">contoso.com</span></span>
  - <span data-ttu-id="5aabe-264">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5aabe-264">contoso.com/a</span></span>
  - <span data-ttu-id="5aabe-265">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-265">payroll.contoso.com</span></span>
  - <span data-ttu-id="5aabe-266">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-266">test.com/contoso.com</span></span>
  - <span data-ttu-id="5aabe-267">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-267">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="5aabe-268">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-268">www.contoso.com</span></span>
  - <span data-ttu-id="5aabe-269">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="5aabe-269">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="5aabe-270">**不符合的區塊**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-270">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="5aabe-271">案例：左側萬用字元（子域）</span><span class="sxs-lookup"><span data-stu-id="5aabe-271">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="5aabe-272">**專案**：`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="5aabe-272">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="5aabe-273">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-273">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5aabe-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-274">www.contoso.com</span></span>
  - <span data-ttu-id="5aabe-275">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-275">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="5aabe-276">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-276">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5aabe-277">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-277">123contoso.com</span></span>
  - <span data-ttu-id="5aabe-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-278">contoso.com</span></span>
  - <span data-ttu-id="5aabe-279">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-279">test.com/contoso.com</span></span>
  - <span data-ttu-id="5aabe-280">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="5aabe-280">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="5aabe-281">案例：路徑頂端的右萬用字元</span><span class="sxs-lookup"><span data-stu-id="5aabe-281">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="5aabe-282">**專案**：`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="5aabe-282">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="5aabe-283">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-283">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5aabe-284">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="5aabe-284">contoso.com/a/b</span></span>
  - <span data-ttu-id="5aabe-285">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="5aabe-285">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="5aabe-286">contoso/a/？ q = joe@t .com</span><span class="sxs-lookup"><span data-stu-id="5aabe-286">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="5aabe-287">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-287">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5aabe-288">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-288">contoso.com</span></span>
  - <span data-ttu-id="5aabe-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5aabe-289">contoso.com/a</span></span>
  - <span data-ttu-id="5aabe-290">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-290">www.contoso.com</span></span>
  - <span data-ttu-id="5aabe-291">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="5aabe-291">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="5aabe-292">案例：左波形符</span><span class="sxs-lookup"><span data-stu-id="5aabe-292">Scenario: Left tilde</span></span>

<span data-ttu-id="5aabe-293">**專案**：`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="5aabe-293">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="5aabe-294">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-294">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5aabe-295">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-295">contoso.com</span></span>
  - <span data-ttu-id="5aabe-296">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-296">www.contoso.com</span></span>
  - <span data-ttu-id="5aabe-297">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-297">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="5aabe-298">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-298">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5aabe-299">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-299">123contoso.com</span></span>
  - <span data-ttu-id="5aabe-300">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="5aabe-300">contoso.com/abc</span></span>
  - <span data-ttu-id="5aabe-301">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="5aabe-301">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="5aabe-302">案例：右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="5aabe-302">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="5aabe-303">**專案**：`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="5aabe-303">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="5aabe-304">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-304">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5aabe-305">contoso （.com）/？ q = whatever@fabrikam .com</span><span class="sxs-lookup"><span data-stu-id="5aabe-305">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="5aabe-306">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5aabe-306">contoso.com/a</span></span>
  - <span data-ttu-id="5aabe-307">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="5aabe-307">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="5aabe-308">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="5aabe-308">contoso.com/ab</span></span>
  - <span data-ttu-id="5aabe-309">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="5aabe-309">contoso.com/b</span></span>
  - <span data-ttu-id="5aabe-310">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="5aabe-310">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="5aabe-311">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="5aabe-311">contoso.com/ba</span></span>

- <span data-ttu-id="5aabe-312">**允許不符合**或**不符合的封鎖**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-312">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="5aabe-313">案例： Left 通配子域和右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="5aabe-313">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="5aabe-314">**專案**：`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="5aabe-314">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="5aabe-315">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-315">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5aabe-316">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="5aabe-316">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="5aabe-317">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="5aabe-317">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="5aabe-318">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5aabe-318">www.contoso.com/a</span></span>
  - <span data-ttu-id="5aabe-319">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="5aabe-319">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="5aabe-320">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="5aabe-320">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="5aabe-321">**允許不符合**或**不符合的封鎖**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="5aabe-321">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="5aabe-322">案例：左和右顎化符</span><span class="sxs-lookup"><span data-stu-id="5aabe-322">Scenario: Left and right tilde</span></span>

<span data-ttu-id="5aabe-323">**專案**：`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="5aabe-323">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="5aabe-324">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5aabe-325">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-325">contoso.com</span></span>
  - <span data-ttu-id="5aabe-326">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5aabe-326">contoso.com/a</span></span>
  - <span data-ttu-id="5aabe-327">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-327">www.contoso.com</span></span>
  - <span data-ttu-id="5aabe-328">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="5aabe-328">www.contoso.com/b</span></span>
  - <span data-ttu-id="5aabe-329">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-329">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="5aabe-330">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-330">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5aabe-331">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-331">123contoso.com</span></span>
  - <span data-ttu-id="5aabe-332">contoso.org</span><span class="sxs-lookup"><span data-stu-id="5aabe-332">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="5aabe-333">案例： IP 位址</span><span class="sxs-lookup"><span data-stu-id="5aabe-333">Scenario: IP address</span></span>

<span data-ttu-id="5aabe-334">**專案**：`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="5aabe-334">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="5aabe-335">**允許**比對和**區塊相符**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="5aabe-335">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="5aabe-336">**允許不符合**或**不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-336">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5aabe-337">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="5aabe-337">1.2.3.4/a</span></span>
  - <span data-ttu-id="5aabe-338">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="5aabe-338">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="5aabe-339">具有右萬用字元的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5aabe-339">IP address with right wildcard</span></span>

<span data-ttu-id="5aabe-340">**專案**：`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="5aabe-340">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="5aabe-341">**允許相符**和**區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-341">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5aabe-342">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="5aabe-342">1.2.3.4/b</span></span>
  - <span data-ttu-id="5aabe-343">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="5aabe-343">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="5aabe-344">無效專案的範例</span><span class="sxs-lookup"><span data-stu-id="5aabe-344">Examples of invalid entries</span></span>

<span data-ttu-id="5aabe-345">下列專案是不正確：</span><span class="sxs-lookup"><span data-stu-id="5aabe-345">The following entries are invalid:</span></span>

- <span data-ttu-id="5aabe-346">**遺失或不正確網域值**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-346">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="5aabe-347">尚未</span><span class="sxs-lookup"><span data-stu-id="5aabe-347">contoso</span></span>
  - <span data-ttu-id="5aabe-348">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="5aabe-348">\*.contoso.\*</span></span>
  - <span data-ttu-id="5aabe-349">\*.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-349">\*.com</span></span>
  - <span data-ttu-id="5aabe-350">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="5aabe-350">\*.pdf</span></span>

- <span data-ttu-id="5aabe-351">**文字上的萬用字元，或不含間距的字元**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-351">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="5aabe-352">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-352">\*contoso.com</span></span>
  - <span data-ttu-id="5aabe-353">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="5aabe-353">contoso.com\*</span></span>
  - <span data-ttu-id="5aabe-354">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="5aabe-354">\*1.2.3.4</span></span>
  - <span data-ttu-id="5aabe-355">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="5aabe-355">1.2.3.4\*</span></span>
  - <span data-ttu-id="5aabe-356">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="5aabe-356">contoso.com/a\*</span></span>
  - <span data-ttu-id="5aabe-357">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="5aabe-357">contoso.com/ab\*</span></span>

- <span data-ttu-id="5aabe-358">**含埠的 IP 位址**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-358">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="5aabe-359">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="5aabe-359">contoso.com:443</span></span>
  - <span data-ttu-id="5aabe-360">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="5aabe-360">abc.contoso.com:25</span></span>

- <span data-ttu-id="5aabe-361">**非描述萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-361">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="5aabe-362">\*.\*</span><span class="sxs-lookup"><span data-stu-id="5aabe-362">\*.\*</span></span>

- <span data-ttu-id="5aabe-363">**中間的萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="5aabe-363">**Middle wildcards**:</span></span>

  - <span data-ttu-id="5aabe-364">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="5aabe-364">conto\*so.com</span></span>
  - <span data-ttu-id="5aabe-365">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="5aabe-365">conto~so.com</span></span>

- <span data-ttu-id="5aabe-366">**兩個萬用字元**</span><span class="sxs-lookup"><span data-stu-id="5aabe-366">**Double wildcards**</span></span>

  - <span data-ttu-id="5aabe-367">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="5aabe-367">contoso.com/\*\*</span></span>
  - <span data-ttu-id="5aabe-368">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="5aabe-368">contoso.com/\*/\*</span></span>
