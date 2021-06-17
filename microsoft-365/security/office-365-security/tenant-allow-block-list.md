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
ms.openlocfilehash: 1548eda760b7b6b19214cb834d7fc43357dc0357
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985489"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="be303-103">管理租用戶允許/封鎖清單中</span><span class="sxs-lookup"><span data-stu-id="be303-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="be303-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="be303-104">**Applies to**</span></span>
- [<span data-ttu-id="be303-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="be303-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="be303-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="be303-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="be303-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be303-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="be303-108">本文所述的功能都是在預覽中，可能會變更，而且無法在所有的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="be303-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="be303-109">如果您的組織沒有如本文所述的欺騙功能，請參閱 [使用哄騙智慧原則管理冒牌寄件者的舊版欺騙管理經驗和 EOP 中的欺騙智慧洞察力](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="be303-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="be303-110">在此時間內，您無法在 [租使用者允許/封鎖] 清單中 **設定** 允許的 URL 或檔專案。</span><span class="sxs-lookup"><span data-stu-id="be303-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="be303-111">在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織沒有 Exchange Online 信箱，您可能會反對 EOP 篩選判定。</span><span class="sxs-lookup"><span data-stu-id="be303-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="be303-112">例如，良好的郵件可能會標示為壞的 (誤報) 或不良郵件可以透過 (誤報) 。</span><span class="sxs-lookup"><span data-stu-id="be303-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="be303-113">Microsoft 365 Defender 入口網站中的承租人 Allow/封鎖清單提供了一種方式，可供您手動覆寫 Microsoft 365 篩選 verdicts。</span><span class="sxs-lookup"><span data-stu-id="be303-113">The Tenant Allow/Block List in the Microsoft 365 Defender portal gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="be303-114">承租人允許/封鎖清單是在郵件流程期間和使用者按一下時使用。</span><span class="sxs-lookup"><span data-stu-id="be303-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="be303-115">您可以指定下列覆寫類型：</span><span class="sxs-lookup"><span data-stu-id="be303-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="be303-116">要封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="be303-116">URLs to block.</span></span>
- <span data-ttu-id="be303-117">要封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="be303-117">Files to block.</span></span>
- <span data-ttu-id="be303-118">要允許或封鎖的欺騙寄件者。</span><span class="sxs-lookup"><span data-stu-id="be303-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="be303-119">[！注意] 如果您在 [哄騙情報洞察力](learn-about-spoof-intelligence.md)中覆寫 allow 或 block 判定，則哄騙寄件者會變成隻會出現在 [租使用者允許/封鎖] 清單的 [ **哄騙** ] 索引標籤上的手動允許或封鎖專案。</span><span class="sxs-lookup"><span data-stu-id="be303-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="be303-120">您也可以在這裡，以欺騙的寄件者的方式手動建立允許或封鎖專案，以供欺詐情報偵測到。</span><span class="sxs-lookup"><span data-stu-id="be303-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="be303-121">本文說明如何在 Microsoft 365 Defender 入口網站中的承租人允許/封鎖清單中設定專案，或在 PowerShell 中使用信箱的 Microsoft 365 組織使用 PowerShell (Exchange Online Exchange Online;組織的獨立 EOP PowerShell，不 Exchange Online 信箱) 。</span><span class="sxs-lookup"><span data-stu-id="be303-121">This article describes how to configure entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="be303-122">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="be303-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="be303-123">您於 <https://security.microsoft.com/> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="be303-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="be303-124">若要直接移至 [ **租使用者允許/封鎖清單** ] 頁面，請使用 <https://security.microsoft.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="be303-124">To go directly to the **Tenant Allow/Block Lists** page, use <https://security.microsoft.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="be303-125">您可以使用檔案的 SHA256 雜湊值來指定檔案。</span><span class="sxs-lookup"><span data-stu-id="be303-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="be303-126">若要在 Windows 中尋找檔案的 SHA256 雜湊值，請在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="be303-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="be303-127">例如，此值可能為 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`。</span><span class="sxs-lookup"><span data-stu-id="be303-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="be303-128">不支援可感知雜湊 (pHash) 值。</span><span class="sxs-lookup"><span data-stu-id="be303-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="be303-129">在本文稍後的 [承租人允許/封鎖清單區段的 url 語法](#url-syntax-for-the-tenant-allowblock-list) 中，會說明可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="be303-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="be303-130">承租人允許/封鎖清單可為 URLs 和500專案提供檔案雜湊的最大值為500專案。</span><span class="sxs-lookup"><span data-stu-id="be303-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="be303-131">每個專案的字元數上限為：</span><span class="sxs-lookup"><span data-stu-id="be303-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="be303-132">檔雜湊 = 64</span><span class="sxs-lookup"><span data-stu-id="be303-132">File hashes = 64</span></span>
  - <span data-ttu-id="be303-133">URL= 250</span><span class="sxs-lookup"><span data-stu-id="be303-133">URL = 250</span></span>

- <span data-ttu-id="be303-134">專案應該在30分鐘內生效。</span><span class="sxs-lookup"><span data-stu-id="be303-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="be303-135">根據預設，承租人允許/封鎖清單中的專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="be303-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="be303-136">您可以指定日期或將其設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="be303-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="be303-137">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="be303-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="be303-138">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="be303-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="be303-139">您必須已在 Exchange Online 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="be303-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="be303-140">**URLs 和** 檔案：</span><span class="sxs-lookup"><span data-stu-id="be303-140">**URLs and files**:</span></span>
    - <span data-ttu-id="be303-141">若要從 [承租人允許/封鎖] 清單中新增及移除值，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="be303-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="be303-142">若要取得租使用者 Allow/封鎖清單的唯讀許可權，您必須是 **全域讀取** 者或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="be303-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="be303-143">**哄騙**：下列其中一個組合：</span><span class="sxs-lookup"><span data-stu-id="be303-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="be303-144">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="be303-144">**Organization Management**</span></span>
    - <span data-ttu-id="be303-145">**安全性管理員**<u>和</u> **View-Only** 設定或 **View-Only 組織管理**。</span><span class="sxs-lookup"><span data-stu-id="be303-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="be303-146">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="be303-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="be303-147">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="be303-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="be303-148">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="be303-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="be303-149">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="be303-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="be303-150">在承租人允許/封鎖清單中使用 Microsoft 365 Defender 入口網站建立封鎖 URL 專案</span><span class="sxs-lookup"><span data-stu-id="be303-150">Use the Microsoft 365 Defender portal to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="be303-151">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **規則** 區段 \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="be303-151">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="be303-152">在 [ **承租人允許/封鎖清單** ] 頁面上，確認已選取 [ **URLs** ] 索引標籤，然後按一下 [ ![ 封鎖圖示 ](../../media/m365-cc-sc-create-icon.png) **區塊**]。</span><span class="sxs-lookup"><span data-stu-id="be303-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="be303-153">在出現的 [ **封鎖 URLs** 浮出] 中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="be303-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="be303-154">**使用萬用字元新增 URLs**：每行輸入一個 URL，最多20個。</span><span class="sxs-lookup"><span data-stu-id="be303-154">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="be303-155">如需 URL 專案之語法的詳細資訊，請參閱本文稍後的 [承租人 Allow/封鎖清單區段的 URL 語法](#url-syntax-for-the-tenant-allowblock-list) 。</span><span class="sxs-lookup"><span data-stu-id="be303-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="be303-156">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="be303-156">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="be303-157">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **移除于** ] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="be303-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="be303-158">或</span><span class="sxs-lookup"><span data-stu-id="be303-158">or</span></span>

     - <span data-ttu-id="be303-159">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="be303-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="be303-161">.</span><span class="sxs-lookup"><span data-stu-id="be303-161">.</span></span>
   - <span data-ttu-id="be303-162">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="be303-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="be303-163">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="be303-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="be303-164">在承租人允許/封鎖清單中使用 Microsoft 365 Defender 入口網站建立封鎖檔案專案</span><span class="sxs-lookup"><span data-stu-id="be303-164">Use the Microsoft 365 Defender portal to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="be303-165">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **規則** 區段 \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="be303-165">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="be303-166">在 [ **承租人允許/封鎖清單** **] 頁面** 上，選取 [檔案] 索引標籤，然後按一下 [ ![ 封鎖圖示 ](../../media/m365-cc-sc-create-icon.png) **區塊**]。</span><span class="sxs-lookup"><span data-stu-id="be303-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="be303-167">在出現的 [ **封鎖檔** ] 浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="be303-167">In the **Block files** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="be303-168">**新增檔案雜湊**：每行輸入一個 SHA256 雜湊值，最多20個。</span><span class="sxs-lookup"><span data-stu-id="be303-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>
   - <span data-ttu-id="be303-169">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="be303-169">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="be303-170">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **移除于** ] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="be303-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="be303-171">或</span><span class="sxs-lookup"><span data-stu-id="be303-171">or</span></span>

     - <span data-ttu-id="be303-172">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="be303-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="be303-174">.</span><span class="sxs-lookup"><span data-stu-id="be303-174">.</span></span>
   - <span data-ttu-id="be303-175">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="be303-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="be303-176">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="be303-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="be303-177">在承租人允許/封鎖清單中使用 Microsoft 365 Defender 入口網站建立允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="be303-177">Use the Microsoft 365 Defender portal to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="be303-178">**附註**：</span><span class="sxs-lookup"><span data-stu-id="be303-178">**Notes**:</span></span>

- <span data-ttu-id="be303-179">只會明確允許或封鎖欺騙使用者 _與_ 網域對中所定義之傳送基礎結構的 _組合_。</span><span class="sxs-lookup"><span data-stu-id="be303-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="be303-180">當您設定網域對的 allow 或封鎖專案時，來自該網域對的郵件就不會再出現在欺騙性智慧洞察力中。</span><span class="sxs-lookup"><span data-stu-id="be303-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="be303-181">欺騙寄件者的專案永不過期。</span><span class="sxs-lookup"><span data-stu-id="be303-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="be303-182">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **規則** 區段 \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="be303-182">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="be303-183">在 [ **租使用者允許/封鎖清單** ] 頁面上，選取 [ **哄騙** ] 索引標籤，然後按一下 [ ![ 封鎖圖示] [ ](../../media/m365-cc-sc-create-icon.png) **新增**]。</span><span class="sxs-lookup"><span data-stu-id="be303-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Add**.</span></span>

3. <span data-ttu-id="be303-184">在出現的 [ **新增網域配對** ] 浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="be303-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="be303-185">**使用萬用字元新增網域配對**：每行輸入一個網域對，最多20個。</span><span class="sxs-lookup"><span data-stu-id="be303-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="be303-186">如需有關欺騙寄件者之語法的詳細資訊，請參閱本文稍後的 [承租人允許/封鎖清單區段中的欺騙寄件者專案的網域對語法](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) 。</span><span class="sxs-lookup"><span data-stu-id="be303-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="be303-187">**哄騙類型**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="be303-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="be303-188">**Internal**：哄騙寄件者位於屬於您組織 ([公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 中的網域。</span><span class="sxs-lookup"><span data-stu-id="be303-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="be303-189">**外部**：冒牌寄件者位於外部網域。</span><span class="sxs-lookup"><span data-stu-id="be303-189">**External**: The spoofed sender is in an external domain.</span></span>
   - <span data-ttu-id="be303-190">**動作**：選取 [ **允許** ] 或 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="be303-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="be303-191">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="be303-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="be303-192">使用 Microsoft 365 Defender 入口網站來查看承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="be303-192">Use the Microsoft 365 Defender portal to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="be303-193">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **規則** 區段 \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="be303-193">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="be303-194">選取您想要的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="be303-194">Select the tab you want.</span></span> <span data-ttu-id="be303-195">可用的欄取決於您所選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="be303-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="be303-196">**URLs**：</span><span class="sxs-lookup"><span data-stu-id="be303-196">**URLs**:</span></span>
     - <span data-ttu-id="be303-197">**值**： URL。</span><span class="sxs-lookup"><span data-stu-id="be303-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="be303-198">**動作**：值 **區塊**。</span><span class="sxs-lookup"><span data-stu-id="be303-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="be303-199">**上次更新**</span><span class="sxs-lookup"><span data-stu-id="be303-199">**Last updated**</span></span>
     - <span data-ttu-id="be303-200">**移除**</span><span class="sxs-lookup"><span data-stu-id="be303-200">**Remove on**</span></span>
     - <span data-ttu-id="be303-201">**附註**</span><span class="sxs-lookup"><span data-stu-id="be303-201">**Notes**</span></span>
   - <span data-ttu-id="be303-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="be303-202">**Files**</span></span>
     - <span data-ttu-id="be303-203">**值**：檔雜湊。</span><span class="sxs-lookup"><span data-stu-id="be303-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="be303-204">**動作**：值 **區塊**。</span><span class="sxs-lookup"><span data-stu-id="be303-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="be303-205">**上次更新**</span><span class="sxs-lookup"><span data-stu-id="be303-205">**Last updated**</span></span>
     - <span data-ttu-id="be303-206">**移除**</span><span class="sxs-lookup"><span data-stu-id="be303-206">**Remove on**</span></span>
     - <span data-ttu-id="be303-207">**附註**</span><span class="sxs-lookup"><span data-stu-id="be303-207">**Notes**</span></span>
   - <span data-ttu-id="be303-208">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="be303-208">**Spoofing**</span></span>
     - <span data-ttu-id="be303-209">**偽裝的使用者**</span><span class="sxs-lookup"><span data-stu-id="be303-209">**Spoofed user**</span></span>
     - <span data-ttu-id="be303-210">**傳送基礎結構**</span><span class="sxs-lookup"><span data-stu-id="be303-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="be303-211">**哄騙類型**：值 **Internal** 或 **External**。</span><span class="sxs-lookup"><span data-stu-id="be303-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="be303-212">**動作**：值 **組塊** 或 **Allow**。</span><span class="sxs-lookup"><span data-stu-id="be303-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="be303-213">您可以按一下欄標題，以遞增或遞減順序排序。</span><span class="sxs-lookup"><span data-stu-id="be303-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="be303-214">您可以按一下 [ **群組** ] 以群組結果。</span><span class="sxs-lookup"><span data-stu-id="be303-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="be303-215">可用的值取決於您所選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="be303-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="be303-216">**URLs**：您可以依 **動作** 將結果分組。</span><span class="sxs-lookup"><span data-stu-id="be303-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="be303-217">檔案 **：您** 可以依 **動作** 將結果分組。</span><span class="sxs-lookup"><span data-stu-id="be303-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="be303-218">**哄騙**：您可以依 **動作** 或 **偽造類型** 來分組結果。</span><span class="sxs-lookup"><span data-stu-id="be303-218">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="be303-219">按一下 [ **搜尋**]，輸入全部或部分的值，然後按 enter 以尋找特定值。</span><span class="sxs-lookup"><span data-stu-id="be303-219">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="be303-220">完成後，按一下 [ ![ 清除搜尋] 圖示 ](../../media/m365-cc-sc-close-icon.png) **清除搜尋**。</span><span class="sxs-lookup"><span data-stu-id="be303-220">When you're finished, click ![Clear search icon](../../media/m365-cc-sc-close-icon.png) **Clear search**.</span></span>

   <span data-ttu-id="be303-221">按一下 [ **篩選** ] 以篩選結果。</span><span class="sxs-lookup"><span data-stu-id="be303-221">Click **Filter** to filter the results.</span></span> <span data-ttu-id="be303-222">顯示的 [ **篩選** ] 浮出控制項中可用的值，取決於您所選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="be303-222">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="be303-223">**URL**</span><span class="sxs-lookup"><span data-stu-id="be303-223">**URLs**</span></span>
     - <span data-ttu-id="be303-224">**Action**</span><span class="sxs-lookup"><span data-stu-id="be303-224">**Action**</span></span>
     - <span data-ttu-id="be303-225">**永不到期**</span><span class="sxs-lookup"><span data-stu-id="be303-225">**Never expire**</span></span>
     - <span data-ttu-id="be303-226">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="be303-226">**Last updated date**</span></span>
     - <span data-ttu-id="be303-227">**移除**</span><span class="sxs-lookup"><span data-stu-id="be303-227">**Remove on**</span></span>
   - <span data-ttu-id="be303-228">**Files**</span><span class="sxs-lookup"><span data-stu-id="be303-228">**Files**</span></span>
     - <span data-ttu-id="be303-229">**Action**</span><span class="sxs-lookup"><span data-stu-id="be303-229">**Action**</span></span>
     - <span data-ttu-id="be303-230">**永不到期**</span><span class="sxs-lookup"><span data-stu-id="be303-230">**Never expire**</span></span>
     - <span data-ttu-id="be303-231">**上次更新**</span><span class="sxs-lookup"><span data-stu-id="be303-231">**Last updated**</span></span>
     - <span data-ttu-id="be303-232">**移除**</span><span class="sxs-lookup"><span data-stu-id="be303-232">**Remove on**</span></span>
   - <span data-ttu-id="be303-233">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="be303-233">**Spoofing**</span></span>
     - <span data-ttu-id="be303-234">**Action**</span><span class="sxs-lookup"><span data-stu-id="be303-234">**Action**</span></span>
     - <span data-ttu-id="be303-235">**哄騙類型**</span><span class="sxs-lookup"><span data-stu-id="be303-235">**Spoof type**</span></span>

   <span data-ttu-id="be303-236">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="be303-236">When you're finished, click **Apply**.</span></span> <span data-ttu-id="be303-237">若要清除現有篩選，請按一下 [ **篩選**]，然後在出現的 [ **篩選** ] 浮出控制項中按一下 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="be303-237">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="be303-238">使用 Microsoft 365 Defender 入口網站修改承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="be303-238">Use the Microsoft 365 Defender portal to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="be303-239">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **規則** 區段 \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="be303-239">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="be303-240">選取 [包含您要修改之專案類型的] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="be303-240">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="be303-241">**URL**</span><span class="sxs-lookup"><span data-stu-id="be303-241">**URLs**</span></span>
   - <span data-ttu-id="be303-242">**Files**</span><span class="sxs-lookup"><span data-stu-id="be303-242">**Files**</span></span>
   - <span data-ttu-id="be303-243">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="be303-243">**Spoofing**</span></span>

3. <span data-ttu-id="be303-244">選取您要修改的專案，然後按一下 [ ![ 編輯圖示] [ ](../../media/m365-cc-sc-edit-icon.png) **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="be303-244">Select the entry that you want to modify, and then click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span> <span data-ttu-id="be303-245">您可以在出現的浮出控制項中修改的值，取決於您在上一個步驟中選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="be303-245">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>
   - <span data-ttu-id="be303-246">**URL**</span><span class="sxs-lookup"><span data-stu-id="be303-246">**URLs**</span></span>
     - <span data-ttu-id="be303-247">**永不到期** 及（或）到期日。</span><span class="sxs-lookup"><span data-stu-id="be303-247">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="be303-248">**選用附注**</span><span class="sxs-lookup"><span data-stu-id="be303-248">**Optional note**</span></span>
   - <span data-ttu-id="be303-249">**Files**</span><span class="sxs-lookup"><span data-stu-id="be303-249">**Files**</span></span>
     - <span data-ttu-id="be303-250">**永不到期** 及（或）到期日。</span><span class="sxs-lookup"><span data-stu-id="be303-250">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="be303-251">**選用附注**</span><span class="sxs-lookup"><span data-stu-id="be303-251">**Optional note**</span></span>
   - <span data-ttu-id="be303-252">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="be303-252">**Spoofing**</span></span>
     - <span data-ttu-id="be303-253">**動作**：您可以將值變更為 [ **允許** ] 或 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="be303-253">**Action**: You can change the value to **Allow** or **Block**.</span></span>
4. <span data-ttu-id="be303-254">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="be303-254">When you're finished, click **Save**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="be303-255">使用 Microsoft 365 Defender 入口網站從承租人允許/封鎖清單中移除專案</span><span class="sxs-lookup"><span data-stu-id="be303-255">Use the Microsoft 365 Defender portal to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="be303-256">在 Microsoft 365 Defender 入口網站中，移至 [原則] **& 規則** \> **威脅** 原則 \> **規則** 區段 \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="be303-256">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="be303-257">選取 [包含您要移除之專案類型的] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="be303-257">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="be303-258">**URL**</span><span class="sxs-lookup"><span data-stu-id="be303-258">**URLs**</span></span>
   - <span data-ttu-id="be303-259">**Files**</span><span class="sxs-lookup"><span data-stu-id="be303-259">**Files**</span></span>
   - <span data-ttu-id="be303-260">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="be303-260">**Spoofing**</span></span>

3. <span data-ttu-id="be303-261">選取您要移除的專案，然後按一下 [ ![ 刪除圖示 ](../../media/m365-cc-sc-delete-icon.png) **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="be303-261">Select the entry that you want to remove, and then click ![Delete icon](../../media/m365-cc-sc-delete-icon.png) **Delete**.</span></span>

4. <span data-ttu-id="be303-262">在出現的警告對話方塊中，按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="be303-262">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="be303-263">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="be303-263">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="be303-264">使用 PowerShell 將封鎖檔案或 URL 專案新增至承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="be303-264">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="be303-265">若要在承租人允許/封鎖清單中新增封鎖檔或 URL 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="be303-265">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="be303-266">這個範例會為永不到期的指定檔案新增封鎖檔專案。</span><span class="sxs-lookup"><span data-stu-id="be303-266">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="be303-267">這個範例會新增 contoso.com 及所有子域 (的封鎖 URL 專案（例如，contoso.com、www.contoso.com 及 xyz.abc.contoso.com) ）。</span><span class="sxs-lookup"><span data-stu-id="be303-267">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="be303-268">因為我們未使用 ExpirationDate 或 NoExpiration 參數，所以專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="be303-268">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="be303-269">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="be303-269">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="be303-270">使用 PowerShell 將允許或封鎖冒牌寄件者專案新增至承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="be303-270">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="be303-271">若要在承租人允許/封鎖清單中新增欺騙寄件者專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="be303-271">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="be303-272">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="be303-272">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="be303-273">使用 PowerShell 在承租人允許/封鎖清單中查看封鎖檔案或 URL 專案</span><span class="sxs-lookup"><span data-stu-id="be303-273">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="be303-274">若要在 [租使用者允許/封鎖] 清單中查看封鎖檔案或 URL 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="be303-274">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="be303-275">此範例會傳回指定之檔案雜湊值的資訊。</span><span class="sxs-lookup"><span data-stu-id="be303-275">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="be303-276">本範例會傳回所有封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="be303-276">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="be303-277">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="be303-277">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="be303-278">在承租人允許/封鎖清單中使用 PowerShell 來查看允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="be303-278">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="be303-279">若要在 [租使用者允許/封鎖] 清單中查看欺騙寄件者專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="be303-279">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="be303-280">本範例會傳回 [承租人允許/封鎖] 清單中的所有冒牌寄件者專案。</span><span class="sxs-lookup"><span data-stu-id="be303-280">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="be303-281">此範例會傳回所有內部皆為內部的寄件者專案。</span><span class="sxs-lookup"><span data-stu-id="be303-281">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="be303-282">此範例會傳回所有外部已封鎖的寄件者專案。</span><span class="sxs-lookup"><span data-stu-id="be303-282">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="be303-283">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="be303-283">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="be303-284">在承租人允許/封鎖清單中使用 PowerShell 修改區塊檔案與 URL 專案</span><span class="sxs-lookup"><span data-stu-id="be303-284">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="be303-285">若要修改承租人 Allow/封鎖清單中的封鎖檔案及 URL 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="be303-285">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="be303-286">本範例會變更指定的封鎖 URL 專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="be303-286">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="be303-287">如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="be303-287">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="be303-288">使用 PowerShell 修改承租人 Allow/封鎖清單中的允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="be303-288">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="be303-289">若要修改承租人 Allow/封鎖清單中的 [允許] 或 [封鎖欺騙的寄件者] 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="be303-289">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="be303-290">本範例會將冒牌寄件者專案從 allow 變更為封鎖。</span><span class="sxs-lookup"><span data-stu-id="be303-290">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="be303-291">如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="be303-291">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="be303-292">使用 PowerShell 從承租人允許/封鎖清單移除 URL 或檔專案</span><span class="sxs-lookup"><span data-stu-id="be303-292">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="be303-293">若要從 [承租人允許/封鎖] 清單中移除檔案及 URL 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="be303-293">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="be303-294">此範例會從承租人允許/封鎖清單中移除指定的封鎖 URL 專案。</span><span class="sxs-lookup"><span data-stu-id="be303-294">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="be303-295">如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="be303-295">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="be303-296">使用 PowerShell 從承租人允許/封鎖清單中移除允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="be303-296">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="be303-297">若要從 [承租人允許/封鎖] 清單中移除 [允許] 或 [封鎖欺騙寄件者] 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="be303-297">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="be303-298">如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="be303-298">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="be303-299">承租人允許/封鎖清單的 URL 語法</span><span class="sxs-lookup"><span data-stu-id="be303-299">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="be303-300">允許 IP4v 和 IPv6 位址，但不會 TCP/UDP 埠。</span><span class="sxs-lookup"><span data-stu-id="be303-300">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="be303-301">不允許使用副檔名 (例如，test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="be303-301">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="be303-302">不支援 Unicode，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="be303-302">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="be303-303">如果下列所有陳述皆為 true，則允許主機名稱：</span><span class="sxs-lookup"><span data-stu-id="be303-303">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="be303-304">主機名稱包含句點。</span><span class="sxs-lookup"><span data-stu-id="be303-304">The hostname contains a period.</span></span>
  - <span data-ttu-id="be303-305">句點的左側至少有一個字元。</span><span class="sxs-lookup"><span data-stu-id="be303-305">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="be303-306">句點右側至少有兩個字元。</span><span class="sxs-lookup"><span data-stu-id="be303-306">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="be303-307">例如， `t.co` 允許; `.com` 或是 `contoso.` 不允許。</span><span class="sxs-lookup"><span data-stu-id="be303-307">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="be303-308">不暗含子路徑。</span><span class="sxs-lookup"><span data-stu-id="be303-308">Subpaths are not implied.</span></span>

  <span data-ttu-id="be303-309">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="be303-309">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="be303-310">在下列案例中，允許使用萬用字元 ( \* ) ：</span><span class="sxs-lookup"><span data-stu-id="be303-310">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="be303-311">左邊的萬用字元必須後接句點，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="be303-311">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="be303-312">例如， `*.contoso.com` 允許; `*contoso.com` 是不允許的。</span><span class="sxs-lookup"><span data-stu-id="be303-312">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="be303-313">右萬用字元必須跟隨正斜線 (/) 來指定路徑。</span><span class="sxs-lookup"><span data-stu-id="be303-313">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="be303-314">例如， `contoso.com/*` 允許; `contoso.com*` 或是 `contoso.com/ab*` 不允許。</span><span class="sxs-lookup"><span data-stu-id="be303-314">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="be303-315">所有的子路徑都不是以右邊的萬用字元隱含。</span><span class="sxs-lookup"><span data-stu-id="be303-315">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="be303-316">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="be303-316">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="be303-317">`*.com*` 無效 (不是可解析的網域，正確的萬用字元不遵循正斜線) 。</span><span class="sxs-lookup"><span data-stu-id="be303-317">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="be303-318">IP 位址中不允許使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="be303-318">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="be303-319">在下列案例中，顎化 (~) 字元是可用的：</span><span class="sxs-lookup"><span data-stu-id="be303-319">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="be303-320">左波形符表示網域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="be303-320">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="be303-321">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="be303-321">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="be303-322">包含通訊協定 (的 URL 專案例如， `http://` 、 `https://` 或 `ftp://`) 會失敗，因為 url 專案適用于所有通訊協定。</span><span class="sxs-lookup"><span data-stu-id="be303-322">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="be303-323">不支援或不需要使用者名稱或密碼。</span><span class="sxs-lookup"><span data-stu-id="be303-323">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="be303-324">引號 ( ' 或 ") 是不正確字元。</span><span class="sxs-lookup"><span data-stu-id="be303-324">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="be303-325">URL 應盡可能包括所有重新導向。</span><span class="sxs-lookup"><span data-stu-id="be303-325">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="be303-326">URL 專案案例</span><span class="sxs-lookup"><span data-stu-id="be303-326">URL entry scenarios</span></span>

<span data-ttu-id="be303-327">有效的 URL 專案及其結果將在下列各節中說明。</span><span class="sxs-lookup"><span data-stu-id="be303-327">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="be303-328">案例：沒有萬用字元</span><span class="sxs-lookup"><span data-stu-id="be303-328">Scenario: No wildcards</span></span>

<span data-ttu-id="be303-329">**專案**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="be303-329">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="be303-330">**允許相符**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-330">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="be303-331">**允許不符合**：</span><span class="sxs-lookup"><span data-stu-id="be303-331">**Allow not matched**:</span></span>

  - <span data-ttu-id="be303-332">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-332">abc-contoso.com</span></span>
  - <span data-ttu-id="be303-333">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="be303-333">contoso.com/a</span></span>
  - <span data-ttu-id="be303-334">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-334">payroll.contoso.com</span></span>
  - <span data-ttu-id="be303-335">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-335">test.com/contoso.com</span></span>
  - <span data-ttu-id="be303-336">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-336">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="be303-337">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-337">www.contoso.com</span></span>
  - <span data-ttu-id="be303-338">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-338">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="be303-339">**Block match**：</span><span class="sxs-lookup"><span data-stu-id="be303-339">**Block match**:</span></span>

  - <span data-ttu-id="be303-340">contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-340">contoso.com</span></span>
  - <span data-ttu-id="be303-341">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="be303-341">contoso.com/a</span></span>
  - <span data-ttu-id="be303-342">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-342">payroll.contoso.com</span></span>
  - <span data-ttu-id="be303-343">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-343">test.com/contoso.com</span></span>
  - <span data-ttu-id="be303-344">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-344">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="be303-345">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-345">www.contoso.com</span></span>
  - <span data-ttu-id="be303-346">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-346">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="be303-347">**不符合的區塊**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-347">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="be303-348">案例：保留萬用字元 (子域) </span><span class="sxs-lookup"><span data-stu-id="be303-348">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="be303-349">**專案**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="be303-349">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="be303-350">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="be303-350">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="be303-351">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-351">www.contoso.com</span></span>
  - <span data-ttu-id="be303-352">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-352">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="be303-353">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="be303-353">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="be303-354">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-354">123contoso.com</span></span>
  - <span data-ttu-id="be303-355">contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-355">contoso.com</span></span>
  - <span data-ttu-id="be303-356">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-356">test.com/contoso.com</span></span>
  - <span data-ttu-id="be303-357">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="be303-357">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="be303-358">案例：路徑頂端的右萬用字元</span><span class="sxs-lookup"><span data-stu-id="be303-358">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="be303-359">**專案**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="be303-359">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="be303-360">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="be303-360">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="be303-361">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="be303-361">contoso.com/a/b</span></span>
  - <span data-ttu-id="be303-362">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="be303-362">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="be303-363">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="be303-363">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="be303-364">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="be303-364">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="be303-365">contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-365">contoso.com</span></span>
  - <span data-ttu-id="be303-366">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="be303-366">contoso.com/a</span></span>
  - <span data-ttu-id="be303-367">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-367">www.contoso.com</span></span>
  - <span data-ttu-id="be303-368">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-368">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="be303-369">案例：左波形符</span><span class="sxs-lookup"><span data-stu-id="be303-369">Scenario: Left tilde</span></span>

<span data-ttu-id="be303-370">**專案**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="be303-370">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="be303-371">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="be303-371">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="be303-372">contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-372">contoso.com</span></span>
  - <span data-ttu-id="be303-373">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-373">www.contoso.com</span></span>
  - <span data-ttu-id="be303-374">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-374">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="be303-375">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="be303-375">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="be303-376">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-376">123contoso.com</span></span>
  - <span data-ttu-id="be303-377">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="be303-377">contoso.com/abc</span></span>
  - <span data-ttu-id="be303-378">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="be303-378">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="be303-379">案例：右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="be303-379">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="be303-380">**專案**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="be303-380">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="be303-381">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="be303-381">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="be303-382">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="be303-382">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="be303-383">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="be303-383">contoso.com/a</span></span>
  - <span data-ttu-id="be303-384">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="be303-384">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="be303-385">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="be303-385">contoso.com/ab</span></span>
  - <span data-ttu-id="be303-386">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="be303-386">contoso.com/b</span></span>
  - <span data-ttu-id="be303-387">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="be303-387">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="be303-388">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="be303-388">contoso.com/ba</span></span>

- <span data-ttu-id="be303-389">**允許不符合** 或 **不符合的封鎖**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-389">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="be303-390">案例： Left 通配子域和右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="be303-390">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="be303-391">**專案**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="be303-391">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="be303-392">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="be303-392">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="be303-393">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="be303-393">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="be303-394">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="be303-394">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="be303-395">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="be303-395">www.contoso.com/a</span></span>
  - <span data-ttu-id="be303-396">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="be303-396">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="be303-397">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="be303-397">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="be303-398">**允許不符合** 或 **不符合的封鎖**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="be303-398">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="be303-399">案例：左和右顎化符</span><span class="sxs-lookup"><span data-stu-id="be303-399">Scenario: Left and right tilde</span></span>

<span data-ttu-id="be303-400">**專案**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="be303-400">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="be303-401">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="be303-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="be303-402">contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-402">contoso.com</span></span>
  - <span data-ttu-id="be303-403">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="be303-403">contoso.com/a</span></span>
  - <span data-ttu-id="be303-404">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-404">www.contoso.com</span></span>
  - <span data-ttu-id="be303-405">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="be303-405">www.contoso.com/b</span></span>
  - <span data-ttu-id="be303-406">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-406">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="be303-407">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="be303-407">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="be303-408">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-408">123contoso.com</span></span>
  - <span data-ttu-id="be303-409">contoso.org</span><span class="sxs-lookup"><span data-stu-id="be303-409">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="be303-410">案例： IP 位址</span><span class="sxs-lookup"><span data-stu-id="be303-410">Scenario: IP address</span></span>

<span data-ttu-id="be303-411">**專案**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="be303-411">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="be303-412">**允許** 比對和 **區塊相符**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="be303-412">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="be303-413">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="be303-413">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="be303-414">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="be303-414">1.2.3.4/a</span></span>
  - <span data-ttu-id="be303-415">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="be303-415">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="be303-416">具有右萬用字元的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="be303-416">IP address with right wildcard</span></span>

<span data-ttu-id="be303-417">**專案**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="be303-417">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="be303-418">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="be303-418">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="be303-419">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="be303-419">1.2.3.4/b</span></span>
  - <span data-ttu-id="be303-420">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="be303-420">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="be303-421">無效專案的範例</span><span class="sxs-lookup"><span data-stu-id="be303-421">Examples of invalid entries</span></span>

<span data-ttu-id="be303-422">下列專案是不正確：</span><span class="sxs-lookup"><span data-stu-id="be303-422">The following entries are invalid:</span></span>

- <span data-ttu-id="be303-423">**遺失或不正確網域值**：</span><span class="sxs-lookup"><span data-stu-id="be303-423">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="be303-424">尚未</span><span class="sxs-lookup"><span data-stu-id="be303-424">contoso</span></span>
  - <span data-ttu-id="be303-425">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="be303-425">\*.contoso.\*</span></span>
  - <span data-ttu-id="be303-426">\*.com</span><span class="sxs-lookup"><span data-stu-id="be303-426">\*.com</span></span>
  - <span data-ttu-id="be303-427">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="be303-427">\*.pdf</span></span>

- <span data-ttu-id="be303-428">**文字上的萬用字元，或不含間距的字元**：</span><span class="sxs-lookup"><span data-stu-id="be303-428">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="be303-429">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="be303-429">\*contoso.com</span></span>
  - <span data-ttu-id="be303-430">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="be303-430">contoso.com\*</span></span>
  - <span data-ttu-id="be303-431">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="be303-431">\*1.2.3.4</span></span>
  - <span data-ttu-id="be303-432">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="be303-432">1.2.3.4\*</span></span>
  - <span data-ttu-id="be303-433">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="be303-433">contoso.com/a\*</span></span>
  - <span data-ttu-id="be303-434">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="be303-434">contoso.com/ab\*</span></span>

- <span data-ttu-id="be303-435">**含埠的 IP 位址**：</span><span class="sxs-lookup"><span data-stu-id="be303-435">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="be303-436">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="be303-436">contoso.com:443</span></span>
  - <span data-ttu-id="be303-437">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="be303-437">abc.contoso.com:25</span></span>

- <span data-ttu-id="be303-438">**非描述萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="be303-438">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="be303-439">\*.\*</span><span class="sxs-lookup"><span data-stu-id="be303-439">\*.\*</span></span>

- <span data-ttu-id="be303-440">**中間的萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="be303-440">**Middle wildcards**:</span></span>

  - <span data-ttu-id="be303-441">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="be303-441">conto\*so.com</span></span>
  - <span data-ttu-id="be303-442">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="be303-442">conto~so.com</span></span>

- <span data-ttu-id="be303-443">**兩個萬用字元**</span><span class="sxs-lookup"><span data-stu-id="be303-443">**Double wildcards**</span></span>

  - <span data-ttu-id="be303-444">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="be303-444">contoso.com/\*\*</span></span>
  - <span data-ttu-id="be303-445">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="be303-445">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="be303-446">承租人允許/封鎖清單中的欺騙寄件者專案的網域對語法</span><span class="sxs-lookup"><span data-stu-id="be303-446">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="be303-447">在承租人允許/封鎖清單中，欺騙寄件者的網域對使用下列語法： `<Spoofed user>, <Sending infrastructure>` 。</span><span class="sxs-lookup"><span data-stu-id="be303-447">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="be303-448">**冒牌使用者**：此值包含欺騙使用者的電子郵件地址，顯示在電子郵件客戶程式的 [ **寄件者** ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="be303-448">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="be303-449">此位址也稱為 `5322.From` 位址。</span><span class="sxs-lookup"><span data-stu-id="be303-449">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="be303-450">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="be303-450">Valid values include:</span></span>
  - <span data-ttu-id="be303-451">個別的電子郵件地址 (例如，chris@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="be303-451">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="be303-452">電子郵件網域 (例如，contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="be303-452">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="be303-453">通配字元 (例如， \*) 。</span><span class="sxs-lookup"><span data-stu-id="be303-453">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="be303-454">傳送 **基礎結構**：此值表示來自欺騙使用者的郵件來源。</span><span class="sxs-lookup"><span data-stu-id="be303-454">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="be303-455">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="be303-455">Valid values include:</span></span>
  - <span data-ttu-id="be303-456">) 來源電子郵件伺服器的 IP 位址的反向 DNS 查閱 (PTR 記錄中找到的網域 (例如，fabrikam.com) 。</span><span class="sxs-lookup"><span data-stu-id="be303-456">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="be303-457">如果來源 IP 位址沒有 PTR 記錄，則會將傳送基礎結構識別為 \<source IP\> /24 (例如，192.168.100.100/24) 。</span><span class="sxs-lookup"><span data-stu-id="be303-457">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="be303-458">以下是有效網域組的一些範例，用以識別冒牌寄件者：</span><span class="sxs-lookup"><span data-stu-id="be303-458">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="be303-459">欺騙寄件者專案的數目上限為1000。</span><span class="sxs-lookup"><span data-stu-id="be303-459">The maximum number of spoofed sender entries is 1000.</span></span>

<span data-ttu-id="be303-460">新增網域對只會允許或封鎖欺騙使用者 *和* 傳送基礎結構的 *組合*。</span><span class="sxs-lookup"><span data-stu-id="be303-460">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="be303-461">它不允許來自欺騙使用者的電子郵件來自任何來源，也不允許任何欺騙使用者的傳送基礎結構來源傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="be303-461">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="be303-462">例如，您新增下列網域對的 allow 專案：</span><span class="sxs-lookup"><span data-stu-id="be303-462">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="be303-463">**網域**： gmail.com</span><span class="sxs-lookup"><span data-stu-id="be303-463">**Domain**: gmail.com</span></span>
- <span data-ttu-id="be303-464">**基礎結構**： tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="be303-464">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="be303-465">只允許來自該網域 *和* 傳送基礎結構的郵件進行欺騙。</span><span class="sxs-lookup"><span data-stu-id="be303-465">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="be303-466">不允許其他企圖哄騙 gmail.com 的寄件者。</span><span class="sxs-lookup"><span data-stu-id="be303-466">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="be303-467">來自來自 tms.mx.com 的來自其他網域中寄件者的郵件會由哄騙情報檢查。</span><span class="sxs-lookup"><span data-stu-id="be303-467">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
