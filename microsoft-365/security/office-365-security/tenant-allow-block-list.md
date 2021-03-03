---
title: 在承租人允許/封鎖清單中管理您的允許和封鎖
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
ms.collection:
- M365-security-compliance
description: 系統管理員可以在安全性入口網站中瞭解如何在承租人允許/封鎖清單中設定允許和封鎖。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 960fbf26b610485fb46c935b04aedcc593b85752
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407247"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-103">管理租用戶允許/封鎖清單中</span><span class="sxs-lookup"><span data-stu-id="8ccd2-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8ccd2-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="8ccd2-104">**Applies to**</span></span>
- [<span data-ttu-id="8ccd2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8ccd2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8ccd2-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="8ccd2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="8ccd2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ccd2-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="8ccd2-108">本文所述的功能都是在預覽中，可能會變更，而且無法在所有的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="8ccd2-109">您此時無法在 [租使用者允許/封鎖] 清單中 **設定** 允許的專案。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="8ccd2-110">在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱，您可能會反對 EOP 篩選判定。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="8ccd2-111">例如，良好的郵件可能會標示為壞的 (誤報) 或不良郵件可以透過 (誤報) 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="8ccd2-112">Security & 合規性中心內的承租人 Allow/封鎖清單可讓您手動覆寫 Microsoft 365 篩選 verdicts。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="8ccd2-113">承租人允許/封鎖清單是在郵件流程期間和使用者按一下時使用。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="8ccd2-114">您可以指定要永遠封鎖 URLs 或檔案。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="8ccd2-115">本文說明如何在「安全性 & 合規性中心」或「PowerShell (Exchange online PowerShell 中使用 Exchange Online 信箱的 Microsoft 365 組織來設定專案]。沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8ccd2-116">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="8ccd2-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8ccd2-117">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8ccd2-118">若要直接移至「 **租使用者允許/封鎖清單** 」頁面，請使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="8ccd2-119">您可以使用檔案的 SHA256 雜湊值來指定檔案。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="8ccd2-120">若要在 Windows 中尋找檔案的 SHA256 雜湊值，請在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="8ccd2-121">例如，此值可能為 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="8ccd2-122">不支援可感知雜湊 (pHash) 值。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="8ccd2-123">在本文稍後的 [承租人允許/封鎖清單區段的 url 語法](#url-syntax-for-the-tenant-allowblock-list) 中，會說明可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="8ccd2-124">承租人允許/封鎖清單可為 URLs 和500專案提供檔案雜湊的最大值為500專案。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="8ccd2-125">專案應該在15分鐘內生效。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="8ccd2-126">根據預設，承租人允許/封鎖清單中的專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="8ccd2-127">您可以指定日期或將其設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="8ccd2-128">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8ccd2-129">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8ccd2-130">您必須先在 **Exchange Online** 中指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-130">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8ccd2-131">若要從 [承租人允許/封鎖] 清單中新增及移除值，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="8ccd2-132">若要取得租使用者 Allow/封鎖清單的唯讀許可權，您必須是 **全域讀取** 者或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="8ccd2-133">如需詳細資訊，請參閱 [Exchange Online 中的權限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-133">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="8ccd2-134">**附註**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-134">**Notes**:</span></span>

  - <span data-ttu-id="8ccd2-135">將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 中其他功能的必要許可權 _和_ 許可權。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8ccd2-136">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="8ccd2-137">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-138">使用安全性 & 規範中心在承租人允許/封鎖清單中建立 URL 專案</span><span class="sxs-lookup"><span data-stu-id="8ccd2-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8ccd2-139">如需 URL 專案之語法的詳細資訊，請參閱本文稍後的 [承租人 Allow/封鎖清單區段的 URL 語法](#url-syntax-for-the-tenant-allowblock-list) 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="8ccd2-140">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8ccd2-141">在 [**承租人允許/封鎖清單**] 頁面上，確認已選取 [ **URLs** ] 索引標籤，然後按一下 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="8ccd2-142">在出現的 [ **封鎖 URLs** 浮出] 中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8ccd2-143">**新增封鎖 URLs**：每行輸入一個 URL，最多20個。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="8ccd2-144">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8ccd2-145">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="8ccd2-146">或</span><span class="sxs-lookup"><span data-stu-id="8ccd2-146">or</span></span>

     - <span data-ttu-id="8ccd2-147">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="8ccd2-149">.</span><span class="sxs-lookup"><span data-stu-id="8ccd2-149">.</span></span>

   - <span data-ttu-id="8ccd2-150">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="8ccd2-151">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-152">使用安全性 & 規範中心在承租人允許/封鎖清單中建立檔案專案</span><span class="sxs-lookup"><span data-stu-id="8ccd2-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8ccd2-153">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8ccd2-154">在 [ **租使用者允許/封鎖清單** **] 頁面** 上，選取 [檔案] 索引標籤，然後按一下 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="8ccd2-155">在 [ **新增要封鎖** 浮出的浮出] 快顯視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8ccd2-156">**新增檔案雜湊**：每行輸入一個 SHA256 雜湊值，最多20個。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="8ccd2-157">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8ccd2-158">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="8ccd2-159">或</span><span class="sxs-lookup"><span data-stu-id="8ccd2-159">or</span></span>

     - <span data-ttu-id="8ccd2-160">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="8ccd2-162">.</span><span class="sxs-lookup"><span data-stu-id="8ccd2-162">.</span></span>

   - <span data-ttu-id="8ccd2-163">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="8ccd2-164">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-165">使用安全性 & 規範中心來查看承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="8ccd2-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8ccd2-166">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8ccd2-167">選取 [ **URLs** ] 索引標籤 **或 [檔案** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="8ccd2-168">按一下下列欄標題，以遞增或遞減順序排序：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="8ccd2-169">**值**： URL 或檔雜湊。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="8ccd2-170">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="8ccd2-170">**Last updated date**</span></span>
- <span data-ttu-id="8ccd2-171">**有效期**</span><span class="sxs-lookup"><span data-stu-id="8ccd2-171">**Expiration date**</span></span>
- <span data-ttu-id="8ccd2-172">**附註**</span><span class="sxs-lookup"><span data-stu-id="8ccd2-172">**Note**</span></span>

<span data-ttu-id="8ccd2-173">按一下 [ **搜尋**]，輸入全部或部分的值，然後按 enter 以尋找特定值。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="8ccd2-174">完成後，請按一下 [ **清除搜尋** ![ 清除搜尋] 圖示 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="8ccd2-175">按一下 [ **篩選**]。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-175">Click **Filter**.</span></span> <span data-ttu-id="8ccd2-176">在出現的 [ **篩選** ] 浮出控制項中，設定下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="8ccd2-177">**永不到期**：選取 [關閉]： [關閉] 或 [開啟]：開啟開啟] ![ ](../../media/scc-toggle-off.png) ![ ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="8ccd2-178">**上次更新**： **從**)  (的開始日期， (**為**) 或兩者的結束日期。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="8ccd2-179">**到期日**： **從**)  (的開始日期， (**為**) 或兩者的結束日期。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="8ccd2-180">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="8ccd2-181">若要清除現有篩選，請按一下 [ **篩選**]，然後在出現的 [ **篩選** ] 浮出控制項中按一下 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-182">使用安全性 & 合規性中心修改承租人允許/封鎖清單中的封鎖專案</span><span class="sxs-lookup"><span data-stu-id="8ccd2-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8ccd2-183">您無法在專案中修改現有的封鎖 URL 或檔值。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="8ccd2-184">若要修改這些值，您必須刪除並重新建立專案。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="8ccd2-185">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8ccd2-186">選取 [ **URLs** ] 索引標籤 **或 [檔案** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="8ccd2-187">選取您要修改的封鎖專案，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="8ccd2-188">在出現的浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8ccd2-189">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8ccd2-190">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定輸入專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="8ccd2-191">或</span><span class="sxs-lookup"><span data-stu-id="8ccd2-191">or</span></span>

     - <span data-ttu-id="8ccd2-192">將切換向右移動，將專案設定為永不過期：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="8ccd2-194">.</span><span class="sxs-lookup"><span data-stu-id="8ccd2-194">.</span></span>

   - <span data-ttu-id="8ccd2-195">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="8ccd2-196">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-197">使用安全性 & 合規性中心移除租使用者允許/封鎖清單中的封鎖專案</span><span class="sxs-lookup"><span data-stu-id="8ccd2-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8ccd2-198">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8ccd2-199">選取 [ **URLs** ] 索引標籤 **或 [檔案** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="8ccd2-200">選取您要移除的封鎖專案，然後按一下 [ **刪除** ![ 刪除圖示] ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="8ccd2-201">在出現的警告對話方塊中，按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-202">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="8ccd2-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-203">使用 PowerShell 將封鎖專案新增至承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="8ccd2-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="8ccd2-204">若要在 [租使用者允許/封鎖] 清單中新增封鎖專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="8ccd2-205">這個範例會新增 contoso.com 及所有子域 (的封鎖 URL 專案（例如，contoso.com、www.contoso.com 及 xyz.abc.contoso.com) ）。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="8ccd2-206">因為我們未使用 ExpirationDate 或 NoExpiration 參數，所以專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="8ccd2-207">這個範例會為永不到期的指定檔案新增封鎖檔專案。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="8ccd2-208">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-209">使用 PowerShell 來查看承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="8ccd2-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8ccd2-210">若要在 [租使用者允許/封鎖] 清單中查看專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="8ccd2-211">本範例會傳回所有封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="8ccd2-212">此範例會傳回指定之檔案雜湊值的資訊。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="8ccd2-213">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-214">使用 PowerShell 修改承租人 Allow/封鎖清單中的封鎖專案</span><span class="sxs-lookup"><span data-stu-id="8ccd2-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8ccd2-215">您無法在區塊專案中修改現有的 URL 或檔值。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="8ccd2-216">若要修改這些值，您必須刪除並重新建立專案。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="8ccd2-217">若要修改承租人 Allow/封鎖清單中的封鎖專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="8ccd2-218">本範例會變更指定的封鎖專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="8ccd2-219">如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-220">使用 PowerShell 從承租人允許/封鎖清單中移除封鎖專案</span><span class="sxs-lookup"><span data-stu-id="8ccd2-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="8ccd2-221">若要從承租人允許/封鎖清單中移除封鎖專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="8ccd2-222">此範例會從承租人允許/封鎖清單中移除指定的封鎖 URL 專案。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="8ccd2-223">如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="8ccd2-224">承租人允許/封鎖清單的 URL 語法</span><span class="sxs-lookup"><span data-stu-id="8ccd2-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="8ccd2-225">允許 IP4v 和 IPv6 位址，但不會 TCP/UDP 埠。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="8ccd2-226">不允許使用副檔名 (例如，test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="8ccd2-227">不支援 Unicode，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="8ccd2-228">如果下列所有陳述皆為 true，則允許主機名稱：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="8ccd2-229">主機名稱包含句點。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="8ccd2-230">句點的左側至少有一個字元。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="8ccd2-231">句點右側至少有兩個字元。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="8ccd2-232">例如， `t.co` 允許; `.com` 或是 `contoso.` 不允許。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="8ccd2-233">不暗含子路徑。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="8ccd2-234">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="8ccd2-235">在下列案例中，允許使用萬用字元 ( \* ) ：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="8ccd2-236">左邊的萬用字元必須後接句點，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="8ccd2-237">例如， `*.contoso.com` 允許; `*contoso.com` 是不允許的。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="8ccd2-238">右萬用字元必須跟隨正斜線 (/) 來指定路徑。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="8ccd2-239">例如， `contoso.com/*` 允許; `contoso.com*` 或是 `contoso.com/ab*` 不允許。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="8ccd2-240">所有的子路徑都不是以右邊的萬用字元隱含。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="8ccd2-241">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="8ccd2-242">`*.com*` 無效 (不是可解析的網域，正確的萬用字元不遵循正斜線) 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="8ccd2-243">IP 位址中不允許使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="8ccd2-244">在下列案例中，顎化 (~) 字元是可用的：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="8ccd2-245">左波形符表示網域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="8ccd2-246">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="8ccd2-247">包含通訊協定 (的 URL 專案例如， `http://` 、 `https://` 或 `ftp://`) 會失敗，因為 url 專案適用于所有通訊協定。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="8ccd2-248">不支援或不需要使用者名稱或密碼。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="8ccd2-249">引號 ( ' 或 ") 是不正確字元。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="8ccd2-250">URL 應盡可能包括所有重新導向。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="8ccd2-251">URL 專案案例</span><span class="sxs-lookup"><span data-stu-id="8ccd2-251">URL entry scenarios</span></span>

<span data-ttu-id="8ccd2-252">有效的 URL 專案及其結果將在下列各節中說明。</span><span class="sxs-lookup"><span data-stu-id="8ccd2-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="8ccd2-253">案例：沒有萬用字元</span><span class="sxs-lookup"><span data-stu-id="8ccd2-253">Scenario: No wildcards</span></span>

<span data-ttu-id="8ccd2-254">**專案**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8ccd2-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="8ccd2-255">**允許相符**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="8ccd2-256">**允許不符合**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="8ccd2-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-257">abc-contoso.com</span></span>
  - <span data-ttu-id="8ccd2-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8ccd2-258">contoso.com/a</span></span>
  - <span data-ttu-id="8ccd2-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="8ccd2-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="8ccd2-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="8ccd2-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-262">www.contoso.com</span></span>
  - <span data-ttu-id="8ccd2-263">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="8ccd2-264">**Block match**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-264">**Block match**:</span></span>

  - <span data-ttu-id="8ccd2-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-265">contoso.com</span></span>
  - <span data-ttu-id="8ccd2-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8ccd2-266">contoso.com/a</span></span>
  - <span data-ttu-id="8ccd2-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="8ccd2-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="8ccd2-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="8ccd2-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-270">www.contoso.com</span></span>
  - <span data-ttu-id="8ccd2-271">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="8ccd2-272">**不符合的區塊**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="8ccd2-273">案例：保留萬用字元 (子域) </span><span class="sxs-lookup"><span data-stu-id="8ccd2-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="8ccd2-274">**專案**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8ccd2-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="8ccd2-275">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8ccd2-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-276">www.contoso.com</span></span>
  - <span data-ttu-id="8ccd2-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8ccd2-278">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8ccd2-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-279">123contoso.com</span></span>
  - <span data-ttu-id="8ccd2-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-280">contoso.com</span></span>
  - <span data-ttu-id="8ccd2-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="8ccd2-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8ccd2-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="8ccd2-283">案例：路徑頂端的右萬用字元</span><span class="sxs-lookup"><span data-stu-id="8ccd2-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="8ccd2-284">**專案**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="8ccd2-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="8ccd2-285">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8ccd2-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="8ccd2-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="8ccd2-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8ccd2-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8ccd2-288">contoso/a/？ q = joe@t .com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="8ccd2-289">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8ccd2-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-290">contoso.com</span></span>
  - <span data-ttu-id="8ccd2-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8ccd2-291">contoso.com/a</span></span>
  - <span data-ttu-id="8ccd2-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-292">www.contoso.com</span></span>
  - <span data-ttu-id="8ccd2-293">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="8ccd2-294">案例：左波形符</span><span class="sxs-lookup"><span data-stu-id="8ccd2-294">Scenario: Left tilde</span></span>

<span data-ttu-id="8ccd2-295">**專案**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8ccd2-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="8ccd2-296">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8ccd2-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-297">contoso.com</span></span>
  - <span data-ttu-id="8ccd2-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-298">www.contoso.com</span></span>
  - <span data-ttu-id="8ccd2-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8ccd2-300">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8ccd2-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-301">123contoso.com</span></span>
  - <span data-ttu-id="8ccd2-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8ccd2-302">contoso.com/abc</span></span>
  - <span data-ttu-id="8ccd2-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8ccd2-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="8ccd2-304">案例：右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="8ccd2-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="8ccd2-305">**專案**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="8ccd2-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="8ccd2-306">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8ccd2-307">contoso （.com）/？ q = whatever@fabrikam .com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="8ccd2-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8ccd2-308">contoso.com/a</span></span>
  - <span data-ttu-id="8ccd2-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8ccd2-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8ccd2-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="8ccd2-310">contoso.com/ab</span></span>
  - <span data-ttu-id="8ccd2-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8ccd2-311">contoso.com/b</span></span>
  - <span data-ttu-id="8ccd2-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="8ccd2-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="8ccd2-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="8ccd2-313">contoso.com/ba</span></span>

- <span data-ttu-id="8ccd2-314">**允許不符合** 或 **不符合的封鎖**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="8ccd2-315">案例： Left 通配子域和右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="8ccd2-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="8ccd2-316">**專案**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="8ccd2-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="8ccd2-317">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8ccd2-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="8ccd2-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="8ccd2-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8ccd2-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8ccd2-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8ccd2-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="8ccd2-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="8ccd2-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="8ccd2-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="8ccd2-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="8ccd2-323">**允許不符合** 或 **不符合的封鎖**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8ccd2-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="8ccd2-324">案例：左和右顎化符</span><span class="sxs-lookup"><span data-stu-id="8ccd2-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="8ccd2-325">**專案**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="8ccd2-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="8ccd2-326">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8ccd2-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-327">contoso.com</span></span>
  - <span data-ttu-id="8ccd2-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8ccd2-328">contoso.com/a</span></span>
  - <span data-ttu-id="8ccd2-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-329">www.contoso.com</span></span>
  - <span data-ttu-id="8ccd2-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8ccd2-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="8ccd2-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8ccd2-332">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8ccd2-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-333">123contoso.com</span></span>
  - <span data-ttu-id="8ccd2-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="8ccd2-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="8ccd2-335">案例： IP 位址</span><span class="sxs-lookup"><span data-stu-id="8ccd2-335">Scenario: IP address</span></span>

<span data-ttu-id="8ccd2-336">**專案**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="8ccd2-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="8ccd2-337">**允許** 比對和 **區塊相符**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="8ccd2-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="8ccd2-338">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8ccd2-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="8ccd2-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="8ccd2-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="8ccd2-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="8ccd2-341">具有右萬用字元的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8ccd2-341">IP address with right wildcard</span></span>

<span data-ttu-id="8ccd2-342">**專案**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="8ccd2-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="8ccd2-343">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8ccd2-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="8ccd2-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="8ccd2-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="8ccd2-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="8ccd2-346">無效專案的範例</span><span class="sxs-lookup"><span data-stu-id="8ccd2-346">Examples of invalid entries</span></span>

<span data-ttu-id="8ccd2-347">下列專案是不正確：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-347">The following entries are invalid:</span></span>

- <span data-ttu-id="8ccd2-348">**遺失或不正確網域值**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="8ccd2-349">尚未</span><span class="sxs-lookup"><span data-stu-id="8ccd2-349">contoso</span></span>
  - <span data-ttu-id="8ccd2-350">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="8ccd2-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="8ccd2-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-351">\*.com</span></span>
  - <span data-ttu-id="8ccd2-352">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="8ccd2-352">\*.pdf</span></span>

- <span data-ttu-id="8ccd2-353">**文字上的萬用字元，或不含間距的字元**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="8ccd2-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-354">\*contoso.com</span></span>
  - <span data-ttu-id="8ccd2-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="8ccd2-355">contoso.com\*</span></span>
  - <span data-ttu-id="8ccd2-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="8ccd2-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="8ccd2-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="8ccd2-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="8ccd2-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="8ccd2-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="8ccd2-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="8ccd2-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="8ccd2-360">**含埠的 IP 位址**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="8ccd2-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="8ccd2-361">contoso.com:443</span></span>
  - <span data-ttu-id="8ccd2-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="8ccd2-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="8ccd2-363">**非描述萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="8ccd2-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="8ccd2-364">\*.\*</span></span>

- <span data-ttu-id="8ccd2-365">**中間的萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="8ccd2-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="8ccd2-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-366">conto\*so.com</span></span>
  - <span data-ttu-id="8ccd2-367">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="8ccd2-367">conto~so.com</span></span>

- <span data-ttu-id="8ccd2-368">**兩個萬用字元**</span><span class="sxs-lookup"><span data-stu-id="8ccd2-368">**Double wildcards**</span></span>

  - <span data-ttu-id="8ccd2-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="8ccd2-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="8ccd2-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="8ccd2-370">contoso.com/\*/\*</span></span>
