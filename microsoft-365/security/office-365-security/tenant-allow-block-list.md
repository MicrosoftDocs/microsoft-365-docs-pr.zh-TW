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
ms.openlocfilehash: 20e460f4e93f7b87faaead8b87ba561224e38938
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515205"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-103">管理租用戶允許/封鎖清單中</span><span class="sxs-lookup"><span data-stu-id="a3cec-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a3cec-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="a3cec-104">**Applies to**</span></span>
- [<span data-ttu-id="a3cec-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a3cec-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a3cec-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="a3cec-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a3cec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3cec-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="a3cec-108">本文所述的功能都是在預覽中，可能會變更，而且無法在所有的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="a3cec-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="a3cec-109">您此時無法在 [租使用者允許/封鎖] 清單中 **設定** 允許的專案。</span><span class="sxs-lookup"><span data-stu-id="a3cec-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="a3cec-110">在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱，您可能會反對 EOP 篩選判定。</span><span class="sxs-lookup"><span data-stu-id="a3cec-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="a3cec-111">例如，良好的郵件可能會標示為壞的 (誤報) 或不良郵件可以透過 (誤報) 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="a3cec-112">Security & 合規性中心內的承租人 Allow/封鎖清單可讓您手動覆寫 Microsoft 365 篩選 verdicts。</span><span class="sxs-lookup"><span data-stu-id="a3cec-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="a3cec-113">承租人允許/封鎖清單是在郵件流程期間和使用者按一下時使用。</span><span class="sxs-lookup"><span data-stu-id="a3cec-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="a3cec-114">您可以指定要永遠封鎖 URLs 或檔案。</span><span class="sxs-lookup"><span data-stu-id="a3cec-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="a3cec-115">本文說明如何在「安全性 & 合規性中心」或「PowerShell (Exchange online PowerShell 中使用 Exchange Online 信箱的 Microsoft 365 組織來設定專案]。沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a3cec-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a3cec-116">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="a3cec-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a3cec-117">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="a3cec-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a3cec-118">若要直接移至「 **租使用者允許/封鎖清單** 」頁面，請使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="a3cec-119">您可以使用檔案的 SHA256 雜湊值來指定檔案。</span><span class="sxs-lookup"><span data-stu-id="a3cec-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="a3cec-120">若要在 Windows 中尋找檔案的 SHA256 雜湊值，請在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a3cec-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="a3cec-121">例如，此值可能為 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`。</span><span class="sxs-lookup"><span data-stu-id="a3cec-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="a3cec-122">不支援可感知雜湊 (pHash) 值。</span><span class="sxs-lookup"><span data-stu-id="a3cec-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="a3cec-123">在本文稍後的 [承租人允許/封鎖清單區段的 url 語法](#url-syntax-for-the-tenant-allowblock-list) 中，會說明可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="a3cec-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="a3cec-124">承租人允許/封鎖清單可為 URLs 和500專案提供檔案雜湊的最大值為500專案。</span><span class="sxs-lookup"><span data-stu-id="a3cec-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="a3cec-125">每個專案的字元數上限為：</span><span class="sxs-lookup"><span data-stu-id="a3cec-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="a3cec-126">檔雜湊 = 64</span><span class="sxs-lookup"><span data-stu-id="a3cec-126">File hashes = 64</span></span>
  - <span data-ttu-id="a3cec-127">URL= 250</span><span class="sxs-lookup"><span data-stu-id="a3cec-127">URL = 250</span></span>

- <span data-ttu-id="a3cec-128">專案應該在30分鐘內生效。</span><span class="sxs-lookup"><span data-stu-id="a3cec-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="a3cec-129">根據預設，承租人允許/封鎖清單中的專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="a3cec-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="a3cec-130">您可以指定日期或將其設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="a3cec-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="a3cec-131">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a3cec-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a3cec-132">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a3cec-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a3cec-133">您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="a3cec-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a3cec-134">若要從 [承租人允許/封鎖] 清單中新增及移除值，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a3cec-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a3cec-135">若要取得租使用者 Allow/封鎖清單的唯讀許可權，您必須是 **全域讀取** 者或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a3cec-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a3cec-136">如需詳細資訊，請參閱 [Exchange Online 中的權限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="a3cec-136">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="a3cec-137">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="a3cec-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a3cec-138">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a3cec-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="a3cec-139">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="a3cec-139">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-140">使用安全性 & 規範中心在承租人允許/封鎖清單中建立 URL 專案</span><span class="sxs-lookup"><span data-stu-id="a3cec-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a3cec-141">如需 URL 專案之語法的詳細資訊，請參閱本文稍後的 [承租人 Allow/封鎖清單區段的 URL 語法](#url-syntax-for-the-tenant-allowblock-list) 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="a3cec-142">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="a3cec-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a3cec-143">在 [**承租人允許/封鎖清單**] 頁面上，確認已選取 [ **URLs** ] 索引標籤，然後按一下 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="a3cec-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="a3cec-144">在出現的 [ **封鎖 URLs** 浮出] 中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a3cec-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a3cec-145">**新增封鎖 URLs**：每行輸入一個 URL，最多20個。</span><span class="sxs-lookup"><span data-stu-id="a3cec-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="a3cec-146">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="a3cec-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a3cec-147">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="a3cec-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="a3cec-148">或</span><span class="sxs-lookup"><span data-stu-id="a3cec-148">or</span></span>

     - <span data-ttu-id="a3cec-149">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="a3cec-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="a3cec-151">.</span><span class="sxs-lookup"><span data-stu-id="a3cec-151">.</span></span>

   - <span data-ttu-id="a3cec-152">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="a3cec-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a3cec-153">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="a3cec-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-154">使用安全性 & 規範中心在承租人允許/封鎖清單中建立檔案專案</span><span class="sxs-lookup"><span data-stu-id="a3cec-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a3cec-155">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="a3cec-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a3cec-156">在 [ **租使用者允許/封鎖清單** **] 頁面** 上，選取 [檔案] 索引標籤，然後按一下 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="a3cec-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="a3cec-157">在 [ **新增要封鎖** 浮出的浮出] 快顯視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a3cec-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a3cec-158">**新增檔案雜湊**：每行輸入一個 SHA256 雜湊值，最多20個。</span><span class="sxs-lookup"><span data-stu-id="a3cec-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="a3cec-159">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="a3cec-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a3cec-160">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="a3cec-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="a3cec-161">或</span><span class="sxs-lookup"><span data-stu-id="a3cec-161">or</span></span>

     - <span data-ttu-id="a3cec-162">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="a3cec-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="a3cec-164">.</span><span class="sxs-lookup"><span data-stu-id="a3cec-164">.</span></span>

   - <span data-ttu-id="a3cec-165">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="a3cec-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a3cec-166">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="a3cec-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-167">使用安全性 & 規範中心來查看承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="a3cec-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a3cec-168">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="a3cec-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a3cec-169">選取 [ **URLs** ] 索引標籤 **或 [檔案** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a3cec-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="a3cec-170">按一下下列欄標題，以遞增或遞減順序排序：</span><span class="sxs-lookup"><span data-stu-id="a3cec-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="a3cec-171">**值**： URL 或檔雜湊。</span><span class="sxs-lookup"><span data-stu-id="a3cec-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="a3cec-172">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="a3cec-172">**Last updated date**</span></span>
- <span data-ttu-id="a3cec-173">**有效期**</span><span class="sxs-lookup"><span data-stu-id="a3cec-173">**Expiration date**</span></span>
- <span data-ttu-id="a3cec-174">**附註**</span><span class="sxs-lookup"><span data-stu-id="a3cec-174">**Note**</span></span>

<span data-ttu-id="a3cec-175">按一下 [ **搜尋**]，輸入全部或部分的值，然後按 enter 以尋找特定值。</span><span class="sxs-lookup"><span data-stu-id="a3cec-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="a3cec-176">完成後，請按一下 [ **清除搜尋** ![ 清除搜尋] 圖示 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="a3cec-177">按一下 [ **篩選**]。</span><span class="sxs-lookup"><span data-stu-id="a3cec-177">Click **Filter**.</span></span> <span data-ttu-id="a3cec-178">在出現的 [ **篩選** ] 浮出控制項中，設定下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="a3cec-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="a3cec-179">**永不到期**：選取 [關閉]： [關閉] 或 [開啟]：開啟開啟] ![ ](../../media/scc-toggle-off.png) ![ ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="a3cec-180">**上次更新**： **從**)  (的開始日期， (**為**) 或兩者的結束日期。</span><span class="sxs-lookup"><span data-stu-id="a3cec-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="a3cec-181">**到期日**： **從**)  (的開始日期， (**為**) 或兩者的結束日期。</span><span class="sxs-lookup"><span data-stu-id="a3cec-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="a3cec-182">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="a3cec-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="a3cec-183">若要清除現有篩選，請按一下 [ **篩選**]，然後在出現的 [ **篩選** ] 浮出控制項中按一下 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="a3cec-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-184">使用安全性 & 合規性中心修改承租人允許/封鎖清單中的封鎖專案</span><span class="sxs-lookup"><span data-stu-id="a3cec-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a3cec-185">您無法在專案中修改現有的封鎖 URL 或檔值。</span><span class="sxs-lookup"><span data-stu-id="a3cec-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="a3cec-186">若要修改這些值，您必須刪除並重新建立專案。</span><span class="sxs-lookup"><span data-stu-id="a3cec-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="a3cec-187">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="a3cec-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a3cec-188">選取 [ **URLs** ] 索引標籤 **或 [檔案** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a3cec-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="a3cec-189">選取您要修改的封鎖專案，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="a3cec-190">在出現的浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a3cec-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a3cec-191">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="a3cec-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a3cec-192">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定輸入專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="a3cec-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="a3cec-193">或</span><span class="sxs-lookup"><span data-stu-id="a3cec-193">or</span></span>

     - <span data-ttu-id="a3cec-194">將切換向右移動，將專案設定為永不過期：</span><span class="sxs-lookup"><span data-stu-id="a3cec-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="a3cec-196">.</span><span class="sxs-lookup"><span data-stu-id="a3cec-196">.</span></span>

   - <span data-ttu-id="a3cec-197">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="a3cec-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="a3cec-198">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="a3cec-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-199">使用安全性 & 合規性中心移除租使用者允許/封鎖清單中的封鎖專案</span><span class="sxs-lookup"><span data-stu-id="a3cec-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a3cec-200">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="a3cec-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a3cec-201">選取 [ **URLs** ] 索引標籤 **或 [檔案** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="a3cec-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="a3cec-202">選取您要移除的封鎖專案，然後按一下 [ **刪除** ![ 刪除圖示] ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="a3cec-203">在出現的警告對話方塊中，按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="a3cec-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-204">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="a3cec-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-205">使用 PowerShell 將封鎖專案新增至承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="a3cec-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="a3cec-206">若要在 [租使用者允許/封鎖] 清單中新增封鎖專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a3cec-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="a3cec-207">這個範例會新增 contoso.com 及所有子域 (的封鎖 URL 專案（例如，contoso.com、www.contoso.com 及 xyz.abc.contoso.com) ）。</span><span class="sxs-lookup"><span data-stu-id="a3cec-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="a3cec-208">因為我們未使用 ExpirationDate 或 NoExpiration 參數，所以專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="a3cec-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="a3cec-209">這個範例會為永不到期的指定檔案新增封鎖檔專案。</span><span class="sxs-lookup"><span data-stu-id="a3cec-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="a3cec-210">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a3cec-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-211">使用 PowerShell 來查看承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="a3cec-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a3cec-212">若要在 [租使用者允許/封鎖] 清單中查看專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a3cec-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="a3cec-213">本範例會傳回所有封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="a3cec-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="a3cec-214">此範例會傳回指定之檔案雜湊值的資訊。</span><span class="sxs-lookup"><span data-stu-id="a3cec-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="a3cec-215">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a3cec-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-216">使用 PowerShell 修改承租人 Allow/封鎖清單中的封鎖專案</span><span class="sxs-lookup"><span data-stu-id="a3cec-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a3cec-217">您無法在區塊專案中修改現有的 URL 或檔值。</span><span class="sxs-lookup"><span data-stu-id="a3cec-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="a3cec-218">若要修改這些值，您必須刪除並重新建立專案。</span><span class="sxs-lookup"><span data-stu-id="a3cec-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="a3cec-219">若要修改承租人 Allow/封鎖清單中的封鎖專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a3cec-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="a3cec-220">本範例會變更指定的封鎖專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="a3cec-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="a3cec-221">如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a3cec-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-222">使用 PowerShell 從承租人允許/封鎖清單中移除封鎖專案</span><span class="sxs-lookup"><span data-stu-id="a3cec-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="a3cec-223">若要從承租人允許/封鎖清單中移除封鎖專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="a3cec-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="a3cec-224">此範例會從承租人允許/封鎖清單中移除指定的封鎖 URL 專案。</span><span class="sxs-lookup"><span data-stu-id="a3cec-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="a3cec-225">如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a3cec-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="a3cec-226">承租人允許/封鎖清單的 URL 語法</span><span class="sxs-lookup"><span data-stu-id="a3cec-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="a3cec-227">允許 IP4v 和 IPv6 位址，但不會 TCP/UDP 埠。</span><span class="sxs-lookup"><span data-stu-id="a3cec-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="a3cec-228">不允許使用副檔名 (例如，test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="a3cec-229">不支援 Unicode，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="a3cec-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="a3cec-230">如果下列所有陳述皆為 true，則允許主機名稱：</span><span class="sxs-lookup"><span data-stu-id="a3cec-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="a3cec-231">主機名稱包含句點。</span><span class="sxs-lookup"><span data-stu-id="a3cec-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="a3cec-232">句點的左側至少有一個字元。</span><span class="sxs-lookup"><span data-stu-id="a3cec-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="a3cec-233">句點右側至少有兩個字元。</span><span class="sxs-lookup"><span data-stu-id="a3cec-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="a3cec-234">例如， `t.co` 允許; `.com` 或是 `contoso.` 不允許。</span><span class="sxs-lookup"><span data-stu-id="a3cec-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="a3cec-235">不暗含子路徑。</span><span class="sxs-lookup"><span data-stu-id="a3cec-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="a3cec-236">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="a3cec-237">在下列案例中，允許使用萬用字元 ( \* ) ：</span><span class="sxs-lookup"><span data-stu-id="a3cec-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="a3cec-238">左邊的萬用字元必須後接句點，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="a3cec-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="a3cec-239">例如， `*.contoso.com` 允許; `*contoso.com` 是不允許的。</span><span class="sxs-lookup"><span data-stu-id="a3cec-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="a3cec-240">右萬用字元必須跟隨正斜線 (/) 來指定路徑。</span><span class="sxs-lookup"><span data-stu-id="a3cec-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="a3cec-241">例如， `contoso.com/*` 允許; `contoso.com*` 或是 `contoso.com/ab*` 不允許。</span><span class="sxs-lookup"><span data-stu-id="a3cec-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="a3cec-242">所有的子路徑都不是以右邊的萬用字元隱含。</span><span class="sxs-lookup"><span data-stu-id="a3cec-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="a3cec-243">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="a3cec-244">`*.com*` 無效 (不是可解析的網域，正確的萬用字元不遵循正斜線) 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="a3cec-245">IP 位址中不允許使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="a3cec-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="a3cec-246">在下列案例中，顎化 (~) 字元是可用的：</span><span class="sxs-lookup"><span data-stu-id="a3cec-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="a3cec-247">左波形符表示網域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="a3cec-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="a3cec-248">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="a3cec-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="a3cec-249">包含通訊協定 (的 URL 專案例如， `http://` 、 `https://` 或 `ftp://`) 會失敗，因為 url 專案適用于所有通訊協定。</span><span class="sxs-lookup"><span data-stu-id="a3cec-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="a3cec-250">不支援或不需要使用者名稱或密碼。</span><span class="sxs-lookup"><span data-stu-id="a3cec-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="a3cec-251">引號 ( ' 或 ") 是不正確字元。</span><span class="sxs-lookup"><span data-stu-id="a3cec-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="a3cec-252">URL 應盡可能包括所有重新導向。</span><span class="sxs-lookup"><span data-stu-id="a3cec-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="a3cec-253">URL 專案案例</span><span class="sxs-lookup"><span data-stu-id="a3cec-253">URL entry scenarios</span></span>

<span data-ttu-id="a3cec-254">有效的 URL 專案及其結果將在下列各節中說明。</span><span class="sxs-lookup"><span data-stu-id="a3cec-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="a3cec-255">案例：沒有萬用字元</span><span class="sxs-lookup"><span data-stu-id="a3cec-255">Scenario: No wildcards</span></span>

<span data-ttu-id="a3cec-256">**專案**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a3cec-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="a3cec-257">**允許相符**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="a3cec-258">**允許不符合**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="a3cec-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-259">abc-contoso.com</span></span>
  - <span data-ttu-id="a3cec-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a3cec-260">contoso.com/a</span></span>
  - <span data-ttu-id="a3cec-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="a3cec-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="a3cec-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a3cec-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-264">www.contoso.com</span></span>
  - <span data-ttu-id="a3cec-265">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="a3cec-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a3cec-266">**Block match**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-266">**Block match**:</span></span>

  - <span data-ttu-id="a3cec-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-267">contoso.com</span></span>
  - <span data-ttu-id="a3cec-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a3cec-268">contoso.com/a</span></span>
  - <span data-ttu-id="a3cec-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="a3cec-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="a3cec-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a3cec-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-272">www.contoso.com</span></span>
  - <span data-ttu-id="a3cec-273">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="a3cec-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a3cec-274">**不符合的區塊**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="a3cec-275">案例：保留萬用字元 (子域) </span><span class="sxs-lookup"><span data-stu-id="a3cec-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="a3cec-276">**專案**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a3cec-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="a3cec-277">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a3cec-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-278">www.contoso.com</span></span>
  - <span data-ttu-id="a3cec-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a3cec-280">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a3cec-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-281">123contoso.com</span></span>
  - <span data-ttu-id="a3cec-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-282">contoso.com</span></span>
  - <span data-ttu-id="a3cec-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="a3cec-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a3cec-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="a3cec-285">案例：路徑頂端的右萬用字元</span><span class="sxs-lookup"><span data-stu-id="a3cec-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="a3cec-286">**專案**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="a3cec-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="a3cec-287">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a3cec-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="a3cec-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="a3cec-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a3cec-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a3cec-290">contoso/a/？ q = joe@t .com</span><span class="sxs-lookup"><span data-stu-id="a3cec-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="a3cec-291">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a3cec-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-292">contoso.com</span></span>
  - <span data-ttu-id="a3cec-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a3cec-293">contoso.com/a</span></span>
  - <span data-ttu-id="a3cec-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-294">www.contoso.com</span></span>
  - <span data-ttu-id="a3cec-295">www .com/q = a@contoso .com</span><span class="sxs-lookup"><span data-stu-id="a3cec-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="a3cec-296">案例：左波形符</span><span class="sxs-lookup"><span data-stu-id="a3cec-296">Scenario: Left tilde</span></span>

<span data-ttu-id="a3cec-297">**專案**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a3cec-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="a3cec-298">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a3cec-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-299">contoso.com</span></span>
  - <span data-ttu-id="a3cec-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-300">www.contoso.com</span></span>
  - <span data-ttu-id="a3cec-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a3cec-302">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a3cec-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-303">123contoso.com</span></span>
  - <span data-ttu-id="a3cec-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a3cec-304">contoso.com/abc</span></span>
  - <span data-ttu-id="a3cec-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a3cec-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="a3cec-306">案例：右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="a3cec-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="a3cec-307">**專案**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a3cec-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="a3cec-308">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a3cec-309">contoso （.com）/？ q = whatever@fabrikam .com</span><span class="sxs-lookup"><span data-stu-id="a3cec-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="a3cec-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a3cec-310">contoso.com/a</span></span>
  - <span data-ttu-id="a3cec-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a3cec-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a3cec-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a3cec-312">contoso.com/ab</span></span>
  - <span data-ttu-id="a3cec-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a3cec-313">contoso.com/b</span></span>
  - <span data-ttu-id="a3cec-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a3cec-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a3cec-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a3cec-315">contoso.com/ba</span></span>

- <span data-ttu-id="a3cec-316">**允許不符合** 或 **不符合的封鎖**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="a3cec-317">案例： Left 通配子域和右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="a3cec-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="a3cec-318">**專案**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a3cec-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="a3cec-319">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a3cec-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a3cec-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="a3cec-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a3cec-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a3cec-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a3cec-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="a3cec-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a3cec-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a3cec-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a3cec-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="a3cec-325">**允許不符合** 或 **不符合的封鎖**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a3cec-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="a3cec-326">案例：左和右顎化符</span><span class="sxs-lookup"><span data-stu-id="a3cec-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="a3cec-327">**專案**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="a3cec-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="a3cec-328">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a3cec-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-329">contoso.com</span></span>
  - <span data-ttu-id="a3cec-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a3cec-330">contoso.com/a</span></span>
  - <span data-ttu-id="a3cec-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-331">www.contoso.com</span></span>
  - <span data-ttu-id="a3cec-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a3cec-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="a3cec-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a3cec-334">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a3cec-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-335">123contoso.com</span></span>
  - <span data-ttu-id="a3cec-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="a3cec-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="a3cec-337">案例： IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3cec-337">Scenario: IP address</span></span>

<span data-ttu-id="a3cec-338">**專案**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="a3cec-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="a3cec-339">**允許** 比對和 **區塊相符**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="a3cec-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="a3cec-340">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a3cec-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a3cec-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="a3cec-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a3cec-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="a3cec-343">具有右萬用字元的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3cec-343">IP address with right wildcard</span></span>

<span data-ttu-id="a3cec-344">**專案**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="a3cec-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="a3cec-345">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a3cec-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="a3cec-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="a3cec-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="a3cec-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="a3cec-348">無效專案的範例</span><span class="sxs-lookup"><span data-stu-id="a3cec-348">Examples of invalid entries</span></span>

<span data-ttu-id="a3cec-349">下列專案是不正確：</span><span class="sxs-lookup"><span data-stu-id="a3cec-349">The following entries are invalid:</span></span>

- <span data-ttu-id="a3cec-350">**遺失或不正確網域值**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="a3cec-351">尚未</span><span class="sxs-lookup"><span data-stu-id="a3cec-351">contoso</span></span>
  - <span data-ttu-id="a3cec-352">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="a3cec-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="a3cec-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-353">\*.com</span></span>
  - <span data-ttu-id="a3cec-354">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="a3cec-354">\*.pdf</span></span>

- <span data-ttu-id="a3cec-355">**文字上的萬用字元，或不含間距的字元**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="a3cec-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-356">\*contoso.com</span></span>
  - <span data-ttu-id="a3cec-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="a3cec-357">contoso.com\*</span></span>
  - <span data-ttu-id="a3cec-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a3cec-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="a3cec-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="a3cec-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="a3cec-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="a3cec-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="a3cec-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="a3cec-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="a3cec-362">**含埠的 IP 位址**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="a3cec-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="a3cec-363">contoso.com:443</span></span>
  - <span data-ttu-id="a3cec-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="a3cec-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="a3cec-365">**非描述萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="a3cec-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="a3cec-366">\*.\*</span></span>

- <span data-ttu-id="a3cec-367">**中間的萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="a3cec-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="a3cec-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="a3cec-368">conto\*so.com</span></span>
  - <span data-ttu-id="a3cec-369">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="a3cec-369">conto~so.com</span></span>

- <span data-ttu-id="a3cec-370">**兩個萬用字元**</span><span class="sxs-lookup"><span data-stu-id="a3cec-370">**Double wildcards**</span></span>

  - <span data-ttu-id="a3cec-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="a3cec-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="a3cec-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="a3cec-372">contoso.com/\*/\*</span></span>
