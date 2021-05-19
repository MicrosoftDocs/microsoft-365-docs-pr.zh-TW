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
ms.openlocfilehash: 270e38d65857de2f4d06460fb3bb77f72a165ecf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538960"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-103">管理租用戶允許/封鎖清單中</span><span class="sxs-lookup"><span data-stu-id="1be20-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1be20-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="1be20-104">**Applies to**</span></span>
- [<span data-ttu-id="1be20-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1be20-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1be20-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="1be20-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1be20-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1be20-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="1be20-108">本文所述的功能都是在預覽中，可能會變更，而且無法在所有的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="1be20-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="1be20-109">如果您的組織沒有如本文所述的欺騙功能，請參閱 [使用哄騙智慧原則管理冒牌寄件者的舊版欺騙管理經驗和 EOP 中的欺騙智慧洞察力](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="1be20-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="1be20-110">在此時間內，您無法在 [租使用者允許/封鎖] 清單中 **設定** 允許的 URL 或檔專案。</span><span class="sxs-lookup"><span data-stu-id="1be20-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="1be20-111">在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織沒有 Exchange Online 信箱，您可能會反對 EOP 篩選判定。</span><span class="sxs-lookup"><span data-stu-id="1be20-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="1be20-112">例如，良好的郵件可能會標示為壞的 (誤報) 或不良郵件可以透過 (誤報) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="1be20-113">Security & 合規性中心內的承租人 Allow/封鎖清單，可讓您以手動方式覆寫 Microsoft 365 篩選 verdicts。</span><span class="sxs-lookup"><span data-stu-id="1be20-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="1be20-114">承租人允許/封鎖清單是在郵件流程期間和使用者按一下時使用。</span><span class="sxs-lookup"><span data-stu-id="1be20-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="1be20-115">您可以指定下列覆寫類型：</span><span class="sxs-lookup"><span data-stu-id="1be20-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="1be20-116">要封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="1be20-116">URLs to block.</span></span>
- <span data-ttu-id="1be20-117">要封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="1be20-117">Files to block.</span></span>
- <span data-ttu-id="1be20-118">允許的大宗郵件寄件者網域。</span><span class="sxs-lookup"><span data-stu-id="1be20-118">Bulk mail sender domains to allow.</span></span> <span data-ttu-id="1be20-119">如需大宗郵件、大量信賴等級 (BCL) ，以及反垃圾郵件原則的大宗郵件篩選的詳細資訊，請參閱 [EOP 中的大量投訴 (BCL) ](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="1be20-119">For more information about bulk mail, the bulk confidence level (BCL), and bulk mail filtering by anti-spam policies, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>
- <span data-ttu-id="1be20-120">要允許或封鎖的欺騙寄件者。</span><span class="sxs-lookup"><span data-stu-id="1be20-120">Spoofed senders to allow or block.</span></span> <span data-ttu-id="1be20-121">[！注意] 如果您在 [哄騙情報洞察力](learn-about-spoof-intelligence.md)中覆寫 allow 或 block 判定，則哄騙寄件者會變成隻會出現在 [租使用者允許/封鎖] 清單的 [ **哄騙** ] 索引標籤上的手動允許或封鎖專案。</span><span class="sxs-lookup"><span data-stu-id="1be20-121">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="1be20-122">您也可以在這裡，以欺騙的寄件者的方式手動建立允許或封鎖專案，以供欺詐情報偵測到。</span><span class="sxs-lookup"><span data-stu-id="1be20-122">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="1be20-123">本文說明如何在「安全性 & 合規性中心」或「PowerShell (Exchange Online PowerShell 中設定使用者在 Microsoft 365 中使用信箱的 Exchange Online 組織的專案。組織的獨立 EOP PowerShell，不 Exchange Online 信箱) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-123">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1be20-124">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="1be20-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1be20-125">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="1be20-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1be20-126">若要直接移至「 **租使用者允許/封鎖清單** 」頁面，請使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="1be20-126">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="1be20-127">您可以使用檔案的 SHA256 雜湊值來指定檔案。</span><span class="sxs-lookup"><span data-stu-id="1be20-127">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="1be20-128">若要在 Windows 中尋找檔案的 SHA256 雜湊值，請在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1be20-128">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="1be20-129">例如，此值可能為 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`。</span><span class="sxs-lookup"><span data-stu-id="1be20-129">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="1be20-130">不支援可感知雜湊 (pHash) 值。</span><span class="sxs-lookup"><span data-stu-id="1be20-130">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="1be20-131">在本文稍後的 [承租人允許/封鎖清單區段的 url 語法](#url-syntax-for-the-tenant-allowblock-list) 中，會說明可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="1be20-131">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="1be20-132">承租人允許/封鎖清單可為 URLs 和500專案提供檔案雜湊的最大值為500專案。</span><span class="sxs-lookup"><span data-stu-id="1be20-132">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="1be20-133">每個專案的字元數上限為：</span><span class="sxs-lookup"><span data-stu-id="1be20-133">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="1be20-134">檔雜湊 = 64</span><span class="sxs-lookup"><span data-stu-id="1be20-134">File hashes = 64</span></span>
  - <span data-ttu-id="1be20-135">URL= 250</span><span class="sxs-lookup"><span data-stu-id="1be20-135">URL = 250</span></span>

- <span data-ttu-id="1be20-136">專案應該在30分鐘內生效。</span><span class="sxs-lookup"><span data-stu-id="1be20-136">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="1be20-137">根據預設，承租人允許/封鎖清單中的專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="1be20-137">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="1be20-138">您可以指定日期或將其設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="1be20-138">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="1be20-139">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1be20-139">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1be20-140">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1be20-140">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1be20-141">您必須已在 Exchange Online 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="1be20-141">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="1be20-142">**URLs、檔案及允許大量寄件者**：</span><span class="sxs-lookup"><span data-stu-id="1be20-142">**URLs, files, and allow bulk senders**:</span></span>
    - <span data-ttu-id="1be20-143">若要從 [承租人允許/封鎖] 清單中新增及移除值，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1be20-143">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="1be20-144">若要取得租使用者 Allow/封鎖清單的唯讀許可權，您必須是 **全域讀取** 者或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1be20-144">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="1be20-145">**哄騙**：下列其中一個組合：</span><span class="sxs-lookup"><span data-stu-id="1be20-145">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="1be20-146">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="1be20-146">**Organization Management**</span></span>
    - <span data-ttu-id="1be20-147">**安全性管理員**<u>和</u> **View-Only** 設定或 **View-Only 組織管理**。</span><span class="sxs-lookup"><span data-stu-id="1be20-147">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="1be20-148">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="1be20-148">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="1be20-149">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="1be20-149">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1be20-150">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="1be20-150">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="1be20-151">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="1be20-151">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-152">使用安全性 & 規範中心在承租人允許/封鎖清單中建立封鎖 URL 專案</span><span class="sxs-lookup"><span data-stu-id="1be20-152">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1be20-153">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="1be20-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1be20-154">在 [**承租人允許/封鎖清單**] 頁面上，確認已選取 [ **URLs** ] 索引標籤，然後按一下 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="1be20-154">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="1be20-155">在出現的 [ **封鎖 URLs** 浮出] 中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="1be20-155">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1be20-156">**新增封鎖 URLs**：每行輸入一個 URL，最多20個。</span><span class="sxs-lookup"><span data-stu-id="1be20-156">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="1be20-157">如需 URL 專案之語法的詳細資訊，請參閱本文稍後的 [承租人 Allow/封鎖清單區段的 URL 語法](#url-syntax-for-the-tenant-allowblock-list) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-157">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="1be20-158">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="1be20-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1be20-159">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="1be20-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="1be20-160">或</span><span class="sxs-lookup"><span data-stu-id="1be20-160">or</span></span>

     - <span data-ttu-id="1be20-161">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="1be20-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="1be20-163">.</span><span class="sxs-lookup"><span data-stu-id="1be20-163">.</span></span>

   - <span data-ttu-id="1be20-164">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="1be20-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="1be20-165">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="1be20-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-166">使用安全性 & 規範中心在承租人允許/封鎖清單中建立封鎖檔案專案</span><span class="sxs-lookup"><span data-stu-id="1be20-166">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1be20-167">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="1be20-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1be20-168">在 [ **承租人允許/封鎖清單** **] 頁面** 上，選取 [檔案] 索引標籤，然後按一下 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="1be20-168">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="1be20-169">在 [ **新增要封鎖** 浮出的浮出] 快顯視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="1be20-169">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1be20-170">**新增檔案雜湊**：每行輸入一個 SHA256 雜湊值，最多20個。</span><span class="sxs-lookup"><span data-stu-id="1be20-170">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="1be20-171">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="1be20-171">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1be20-172">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="1be20-172">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="1be20-173">或</span><span class="sxs-lookup"><span data-stu-id="1be20-173">or</span></span>

     - <span data-ttu-id="1be20-174">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="1be20-174">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="1be20-176">.</span><span class="sxs-lookup"><span data-stu-id="1be20-176">.</span></span>

   - <span data-ttu-id="1be20-177">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="1be20-177">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="1be20-178">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="1be20-178">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-179">使用安全性 & 合規性中心建立承租人允許/封鎖清單中的允許大宗郵件寄件者網域專案</span><span class="sxs-lookup"><span data-stu-id="1be20-179">Use the Security & Compliance Center to create allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1be20-180">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="1be20-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1be20-181">在 [ **承租人允許/封鎖清單** ] 頁面上，選取 [BCL 旁路] 索引標籤的 [ **寄件者網域** ]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="1be20-181">On the **Tenant Allow/Block List** page, select the **Sender domains for BCL bypass** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="1be20-182">在 [ **新增加入寄件者的網域** ] 中，出現出現的 BCL 略過浮出控制項，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="1be20-182">In the **Add sender domain for BCL bypass** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1be20-183">**新增地域略過的寄件者網域**：每行輸入一個適當大宗郵件的來源域，最多20個。</span><span class="sxs-lookup"><span data-stu-id="1be20-183">**Add sender domains for BCL bypass**: Enter one source domain of good bulk mail per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="1be20-184">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="1be20-184">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1be20-185">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="1be20-185">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="1be20-186">或</span><span class="sxs-lookup"><span data-stu-id="1be20-186">or</span></span>

     - <span data-ttu-id="1be20-187">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="1be20-187">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="1be20-189">.</span><span class="sxs-lookup"><span data-stu-id="1be20-189">.</span></span>

4. <span data-ttu-id="1be20-190">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="1be20-190">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-191">使用安全性 & 規範中心在承租人允許/封鎖清單中建立允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="1be20-191">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-192">**附註**：</span><span class="sxs-lookup"><span data-stu-id="1be20-192">**Notes**:</span></span>

- <span data-ttu-id="1be20-193">只會明確允許或封鎖欺騙使用者 _與_ 網域對中所定義之傳送基礎結構的 _組合_。</span><span class="sxs-lookup"><span data-stu-id="1be20-193">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="1be20-194">當您設定網域對的 allow 或封鎖專案時，來自該網域對的郵件就不會再出現在欺騙性智慧洞察力中。</span><span class="sxs-lookup"><span data-stu-id="1be20-194">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="1be20-195">欺騙寄件者的專案永不過期。</span><span class="sxs-lookup"><span data-stu-id="1be20-195">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="1be20-196">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="1be20-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1be20-197">在 [ **承租人允許/封鎖清單** ] 頁面上，選取 [ **哄騙** ] 索引標籤，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="1be20-197">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="1be20-198">在出現的 [ **新增網域配對** ] 浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="1be20-198">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1be20-199">**使用萬用字元新增網域配對**：每行輸入一個網域對，最多20個。</span><span class="sxs-lookup"><span data-stu-id="1be20-199">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="1be20-200">如需有關欺騙寄件者之語法的詳細資訊，請參閱本文稍後的 [承租人允許/封鎖清單區段中的欺騙寄件者專案的網域對語法](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-200">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="1be20-201">**哄騙類型**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="1be20-201">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="1be20-202">**Internal**：哄騙寄件者位於屬於您組織 ([公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 中的網域。</span><span class="sxs-lookup"><span data-stu-id="1be20-202">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="1be20-203">**外部**：冒牌寄件者位於外部網域。</span><span class="sxs-lookup"><span data-stu-id="1be20-203">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="1be20-204">**動作**：選取 [ **允許** ] 或 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="1be20-204">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="1be20-205">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="1be20-205">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-206">使用安全性 & 規範中心來查看承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="1be20-206">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1be20-207">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="1be20-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1be20-208">選取您想要的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1be20-208">Select the tab you want.</span></span> <span data-ttu-id="1be20-209">可用的欄取決於您所選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="1be20-209">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="1be20-210">**URLs**：</span><span class="sxs-lookup"><span data-stu-id="1be20-210">**URLs**:</span></span>
     - <span data-ttu-id="1be20-211">**值**： URL。</span><span class="sxs-lookup"><span data-stu-id="1be20-211">**Value**: The URL.</span></span>
     - <span data-ttu-id="1be20-212">**動作**：值 **區塊**。</span><span class="sxs-lookup"><span data-stu-id="1be20-212">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="1be20-213">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="1be20-213">**Last updated date**</span></span>
     - <span data-ttu-id="1be20-214">**有效期**</span><span class="sxs-lookup"><span data-stu-id="1be20-214">**Expiration date**</span></span>
     - <span data-ttu-id="1be20-215">**附註**</span><span class="sxs-lookup"><span data-stu-id="1be20-215">**Note**</span></span>

   - <span data-ttu-id="1be20-216">**Files**</span><span class="sxs-lookup"><span data-stu-id="1be20-216">**Files**</span></span>
     - <span data-ttu-id="1be20-217">**值**：檔雜湊。</span><span class="sxs-lookup"><span data-stu-id="1be20-217">**Value**: The file hash.</span></span>
     - <span data-ttu-id="1be20-218">**動作**：值 **區塊**。</span><span class="sxs-lookup"><span data-stu-id="1be20-218">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="1be20-219">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="1be20-219">**Last updated date**</span></span>
     - <span data-ttu-id="1be20-220">**有效期**</span><span class="sxs-lookup"><span data-stu-id="1be20-220">**Expiration date**</span></span>
     - <span data-ttu-id="1be20-221">**附註**</span><span class="sxs-lookup"><span data-stu-id="1be20-221">**Note**</span></span>

   - <span data-ttu-id="1be20-222">**BCL 略過的寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="1be20-222">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="1be20-223">**值**：大宗郵件寄件者的網域。</span><span class="sxs-lookup"><span data-stu-id="1be20-223">**Value**: The bulk mail sender's domain.</span></span>
     - <span data-ttu-id="1be20-224">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="1be20-224">**Last updated date**</span></span>
     - <span data-ttu-id="1be20-225">**有效期**</span><span class="sxs-lookup"><span data-stu-id="1be20-225">**Expiration date**</span></span>

   - <span data-ttu-id="1be20-226">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="1be20-226">**Spoofing**</span></span>
     - <span data-ttu-id="1be20-227">**偽裝的使用者**</span><span class="sxs-lookup"><span data-stu-id="1be20-227">**Spoofed user**</span></span>
     - <span data-ttu-id="1be20-228">**傳送基礎結構**</span><span class="sxs-lookup"><span data-stu-id="1be20-228">**Sending infrastructure**</span></span>
     - <span data-ttu-id="1be20-229">**哄騙類型**：值 **Internal** 或 **External**。</span><span class="sxs-lookup"><span data-stu-id="1be20-229">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="1be20-230">**動作**：值 **組塊** 或 **Allow**。</span><span class="sxs-lookup"><span data-stu-id="1be20-230">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="1be20-231">您可以按一下欄標題，以遞增或遞減順序排序。</span><span class="sxs-lookup"><span data-stu-id="1be20-231">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="1be20-232">您可以按一下 [ **群組** ] 以群組結果。</span><span class="sxs-lookup"><span data-stu-id="1be20-232">You can click **Group** to group the results.</span></span> <span data-ttu-id="1be20-233">可用的值取決於您所選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="1be20-233">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="1be20-234">**URLs**：您可以依 **動作** 將結果分組。</span><span class="sxs-lookup"><span data-stu-id="1be20-234">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="1be20-235">檔案 **：您** 可以依 **動作** 將結果分組。</span><span class="sxs-lookup"><span data-stu-id="1be20-235">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="1be20-236">在此索引標籤上無法使用 **群組\*\*\*\*的寄件者網域**。</span><span class="sxs-lookup"><span data-stu-id="1be20-236">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="1be20-237">**哄騙**：您可以依 **動作** 或 **偽造類型** 來分組結果。</span><span class="sxs-lookup"><span data-stu-id="1be20-237">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="1be20-238">按一下 [ **搜尋**]，輸入全部或部分的值，然後按 enter 以尋找特定值。</span><span class="sxs-lookup"><span data-stu-id="1be20-238">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="1be20-239">完成後，請按一下 [ **清除搜尋** ![ 清除搜尋] 圖示 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-239">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="1be20-240">按一下 [ **篩選** ] 以篩選結果。</span><span class="sxs-lookup"><span data-stu-id="1be20-240">Click **Filter** to filter the results.</span></span> <span data-ttu-id="1be20-241">顯示的 [ **篩選** ] 浮出控制項中可用的值，取決於您所選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="1be20-241">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="1be20-242">**URL**</span><span class="sxs-lookup"><span data-stu-id="1be20-242">**URLs**</span></span>
     - <span data-ttu-id="1be20-243">**Action**</span><span class="sxs-lookup"><span data-stu-id="1be20-243">**Action**</span></span>
     - <span data-ttu-id="1be20-244">**永不到期**</span><span class="sxs-lookup"><span data-stu-id="1be20-244">**Never expire**</span></span>
     - <span data-ttu-id="1be20-245">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="1be20-245">**Last updated date**</span></span>
     - <span data-ttu-id="1be20-246">**有效期**</span><span class="sxs-lookup"><span data-stu-id="1be20-246">**Expiration date**</span></span>

   - <span data-ttu-id="1be20-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="1be20-247">**Files**</span></span>
     - <span data-ttu-id="1be20-248">**Action**</span><span class="sxs-lookup"><span data-stu-id="1be20-248">**Action**</span></span>
     - <span data-ttu-id="1be20-249">**永不到期**</span><span class="sxs-lookup"><span data-stu-id="1be20-249">**Never expire**</span></span>
     - <span data-ttu-id="1be20-250">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="1be20-250">**Last updated date**</span></span>
     - <span data-ttu-id="1be20-251">**有效期**</span><span class="sxs-lookup"><span data-stu-id="1be20-251">**Expiration date**</span></span>

   - <span data-ttu-id="1be20-252">**BCL 略過的寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="1be20-252">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="1be20-253">**永不到期**</span><span class="sxs-lookup"><span data-stu-id="1be20-253">**Never expire**</span></span>
     - <span data-ttu-id="1be20-254">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="1be20-254">**Last updated date**</span></span>
     - <span data-ttu-id="1be20-255">**有效期**</span><span class="sxs-lookup"><span data-stu-id="1be20-255">**Expiration date**</span></span>

   - <span data-ttu-id="1be20-256">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="1be20-256">**Spoofing**</span></span>
     - <span data-ttu-id="1be20-257">**Action**</span><span class="sxs-lookup"><span data-stu-id="1be20-257">**Action**</span></span>
     - <span data-ttu-id="1be20-258">**哄騙類型**</span><span class="sxs-lookup"><span data-stu-id="1be20-258">**Spoof type**</span></span>

   <span data-ttu-id="1be20-259">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="1be20-259">When you're finished, click **Apply**.</span></span> <span data-ttu-id="1be20-260">若要清除現有篩選，請按一下 [ **篩選**]，然後在出現的 [ **篩選** ] 浮出控制項中按一下 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="1be20-260">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-261">使用安全性 & 規範中心修改承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="1be20-261">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1be20-262">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="1be20-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1be20-263">選取 [包含您要修改之專案類型的] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="1be20-263">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="1be20-264">**URL**</span><span class="sxs-lookup"><span data-stu-id="1be20-264">**URLs**</span></span>
   - <span data-ttu-id="1be20-265">**Files**</span><span class="sxs-lookup"><span data-stu-id="1be20-265">**Files**</span></span>
   - <span data-ttu-id="1be20-266">**BCL 略過的寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="1be20-266">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="1be20-267">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="1be20-267">**Spoofing**</span></span>

3. <span data-ttu-id="1be20-268">選取您要修改的專案，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-268">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="1be20-269">您可以在出現的浮出控制項中修改的值，取決於您在上一個步驟中選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="1be20-269">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="1be20-270">**URL**</span><span class="sxs-lookup"><span data-stu-id="1be20-270">**URLs**</span></span>
     - <span data-ttu-id="1be20-271">**永不到期** 及（或）到期日。</span><span class="sxs-lookup"><span data-stu-id="1be20-271">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="1be20-272">**選用附注**</span><span class="sxs-lookup"><span data-stu-id="1be20-272">**Optional note**</span></span>

   - <span data-ttu-id="1be20-273">**Files**</span><span class="sxs-lookup"><span data-stu-id="1be20-273">**Files**</span></span>
     - <span data-ttu-id="1be20-274">**永不到期** 及（或）到期日。</span><span class="sxs-lookup"><span data-stu-id="1be20-274">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="1be20-275">**選用附注**</span><span class="sxs-lookup"><span data-stu-id="1be20-275">**Optional note**</span></span>

   - <span data-ttu-id="1be20-276">**BCL 略過的寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="1be20-276">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="1be20-277">**永不到期** 及（或）到期日。</span><span class="sxs-lookup"><span data-stu-id="1be20-277">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="1be20-278">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="1be20-278">**Spoofing**</span></span>
     - <span data-ttu-id="1be20-279">**動作**：您可以將值變更為 [ **允許** ] 或 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="1be20-279">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="1be20-280">完成後，按一下 \*\*\*\*[儲存]。</span><span class="sxs-lookup"><span data-stu-id="1be20-280">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-281">使用安全性 & 規範中心移除承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="1be20-281">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1be20-282">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="1be20-282">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1be20-283">選取 [包含您要移除之專案類型的] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="1be20-283">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="1be20-284">**URL**</span><span class="sxs-lookup"><span data-stu-id="1be20-284">**URLs**</span></span>
   - <span data-ttu-id="1be20-285">**Files**</span><span class="sxs-lookup"><span data-stu-id="1be20-285">**Files**</span></span>
   - <span data-ttu-id="1be20-286">**BCL 略過的寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="1be20-286">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="1be20-287">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="1be20-287">**Spoofing**</span></span>

3. <span data-ttu-id="1be20-288">選取您要移除的專案，然後按一下 [ **刪除** ![ 刪除圖示] ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-288">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="1be20-289">在出現的警告對話方塊中，按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="1be20-289">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-290">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="1be20-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-291">使用 PowerShell 將封鎖檔案或 URL 專案新增至承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="1be20-291">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-292">若要在承租人允許/封鎖清單中新增封鎖檔或 URL 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1be20-292">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="1be20-293">這個範例會為永不到期的指定檔案新增封鎖檔專案。</span><span class="sxs-lookup"><span data-stu-id="1be20-293">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="1be20-294">這個範例會新增 contoso.com 及所有子域 (的封鎖 URL 專案（例如，contoso.com、www.contoso.com 及 xyz.abc.contoso.com) ）。</span><span class="sxs-lookup"><span data-stu-id="1be20-294">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="1be20-295">因為我們未使用 ExpirationDate 或 NoExpiration 參數，所以專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="1be20-295">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="1be20-296">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="1be20-296">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-bulk-mail-sender-domain-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-297">使用 PowerShell 新增允許大宗郵件寄件者網域專案至租使用者允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="1be20-297">Use PowerShell to add allow bulk mail sender domain entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-298">若要新增「租使用者允許/封鎖」清單中的允許大宗郵件寄件者網域專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1be20-298">To add allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType BulkSender -Block:$false -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="1be20-299">此範例會為永不到期的指定網域新增允許的大量寄件者專案。</span><span class="sxs-lookup"><span data-stu-id="1be20-299">This example adds an allowed bulk sender entry for the specified domain that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType BulkSender -Block:$false -Entries contosodailydeals.com
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="1be20-300">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="1be20-300">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-301">使用 PowerShell 將允許或封鎖冒牌寄件者專案新增至承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="1be20-301">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-302">若要在承租人允許/封鎖清單中新增欺騙寄件者專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1be20-302">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="1be20-303">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="1be20-303">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-304">使用 PowerShell 在承租人允許/封鎖清單中查看封鎖檔案或 URL 專案</span><span class="sxs-lookup"><span data-stu-id="1be20-304">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-305">若要在 [租使用者允許/封鎖] 清單中查看封鎖檔案或 URL 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1be20-305">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="1be20-306">此範例會傳回指定之檔案雜湊值的資訊。</span><span class="sxs-lookup"><span data-stu-id="1be20-306">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="1be20-307">本範例會傳回所有封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="1be20-307">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="1be20-308">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="1be20-308">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-309">使用 PowerShell 以查看允許在承租人允許/封鎖清單中大宗郵件寄件者的網域專案</span><span class="sxs-lookup"><span data-stu-id="1be20-309">Use PowerShell to view allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-310">若要在 [租使用者允許/封鎖] 清單中查看 [允許大宗郵件寄件者網域專案]，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1be20-310">To view allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender [-Entry <BulkSenderDomainValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="1be20-311">此範例會傳回所有允許的大宗郵件寄件者網域。</span><span class="sxs-lookup"><span data-stu-id="1be20-311">This example returns all allowed bulk mail sender domains.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender
```

<span data-ttu-id="1be20-312">此範例會傳回指定之大量寄件者網域的資訊。</span><span class="sxs-lookup"><span data-stu-id="1be20-312">This example returns information for the specified bulk sender domain.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "contosodailydeals.com"
```

<span data-ttu-id="1be20-313">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="1be20-313">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-314">在承租人允許/封鎖清單中使用 PowerShell 來查看允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="1be20-314">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-315">若要在 [租使用者允許/封鎖] 清單中查看欺騙寄件者專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1be20-315">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="1be20-316">本範例會傳回 [承租人允許/封鎖] 清單中的所有冒牌寄件者專案。</span><span class="sxs-lookup"><span data-stu-id="1be20-316">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="1be20-317">此範例會傳回所有內部皆為內部的寄件者專案。</span><span class="sxs-lookup"><span data-stu-id="1be20-317">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="1be20-318">此範例會傳回所有外部已封鎖的寄件者專案。</span><span class="sxs-lookup"><span data-stu-id="1be20-318">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="1be20-319">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="1be20-319">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-320">在承租人允許/封鎖清單中使用 PowerShell 修改區塊檔案與 URL 專案</span><span class="sxs-lookup"><span data-stu-id="1be20-320">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-321">若要修改承租人 Allow/封鎖清單中的封鎖檔案及 URL 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1be20-321">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="1be20-322">本範例會變更指定的封鎖 URL 專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="1be20-322">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="1be20-323">如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="1be20-323">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-324">在承租人允許/封鎖清單中使用 PowerShell 修改允許大宗郵件寄件者網域專案</span><span class="sxs-lookup"><span data-stu-id="1be20-324">Use PowerShell to modify allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-325">若要修改允許租使用者/封鎖清單中的大宗郵件寄件者網域專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1be20-325">To modify allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="1be20-326">此範例會將指定之允許大宗郵件寄件者網域專案的到期變更為永不過期。</span><span class="sxs-lookup"><span data-stu-id="1be20-326">This example changes the expiration of the specified allow bulk mail sender domain entry to never expire.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType BulkSender -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -NoExpiration
```

<span data-ttu-id="1be20-327">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="1be20-327">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-328">使用 PowerShell 修改承租人 Allow/封鎖清單中的允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="1be20-328">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-329">若要修改承租人 Allow/封鎖清單中的 [允許] 或 [封鎖欺騙的寄件者] 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1be20-329">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="1be20-330">本範例會將冒牌寄件者專案從 allow 變更為封鎖。</span><span class="sxs-lookup"><span data-stu-id="1be20-330">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="1be20-331">如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="1be20-331">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-bulk-mail-sender-domain-file-and-domain-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-332">使用 PowerShell 從承租人允許/封鎖清單中移除大宗郵件寄件者網域、檔案及網域專案</span><span class="sxs-lookup"><span data-stu-id="1be20-332">Use PowerShell to remove bulk mail sender domain, file, and domain entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-333">若要從承租人允許/封鎖清單中移除 [允許大宗郵件寄件者網域專案]、[封鎖檔案專案] 及 [封鎖 URL] 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1be20-333">To remove allow bulk mail sender domain entries, block file entries, and block URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <BulkSender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="1be20-334">此範例會從承租人允許/封鎖清單中移除指定的封鎖 URL 專案。</span><span class="sxs-lookup"><span data-stu-id="1be20-334">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="1be20-335">如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="1be20-335">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-336">使用 PowerShell 從承租人允許/封鎖清單中移除允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="1be20-336">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-337">若要從 [承租人允許/封鎖] 清單中移除 [允許] 或 [封鎖欺騙寄件者] 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1be20-337">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="1be20-338">如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="1be20-338">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-339">承租人允許/封鎖清單的 URL 語法</span><span class="sxs-lookup"><span data-stu-id="1be20-339">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="1be20-340">允許 IP4v 和 IPv6 位址，但不會 TCP/UDP 埠。</span><span class="sxs-lookup"><span data-stu-id="1be20-340">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="1be20-341">不允許使用副檔名 (例如，test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-341">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="1be20-342">不支援 Unicode，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="1be20-342">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="1be20-343">如果下列所有陳述皆為 true，則允許主機名稱：</span><span class="sxs-lookup"><span data-stu-id="1be20-343">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="1be20-344">主機名稱包含句點。</span><span class="sxs-lookup"><span data-stu-id="1be20-344">The hostname contains a period.</span></span>
  - <span data-ttu-id="1be20-345">句點的左側至少有一個字元。</span><span class="sxs-lookup"><span data-stu-id="1be20-345">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="1be20-346">句點右側至少有兩個字元。</span><span class="sxs-lookup"><span data-stu-id="1be20-346">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="1be20-347">例如， `t.co` 允許; `.com` 或是 `contoso.` 不允許。</span><span class="sxs-lookup"><span data-stu-id="1be20-347">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="1be20-348">不暗含子路徑。</span><span class="sxs-lookup"><span data-stu-id="1be20-348">Subpaths are not implied.</span></span>

  <span data-ttu-id="1be20-349">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="1be20-349">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="1be20-350">在下列案例中，允許使用萬用字元 ( \* ) ：</span><span class="sxs-lookup"><span data-stu-id="1be20-350">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="1be20-351">左邊的萬用字元必須後接句點，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="1be20-351">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="1be20-352">例如， `*.contoso.com` 允許; `*contoso.com` 是不允許的。</span><span class="sxs-lookup"><span data-stu-id="1be20-352">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="1be20-353">右萬用字元必須跟隨正斜線 (/) 來指定路徑。</span><span class="sxs-lookup"><span data-stu-id="1be20-353">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="1be20-354">例如， `contoso.com/*` 允許; `contoso.com*` 或是 `contoso.com/ab*` 不允許。</span><span class="sxs-lookup"><span data-stu-id="1be20-354">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="1be20-355">所有的子路徑都不是以右邊的萬用字元隱含。</span><span class="sxs-lookup"><span data-stu-id="1be20-355">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="1be20-356">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="1be20-356">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="1be20-357">`*.com*` 無效 (不是可解析的網域，正確的萬用字元不遵循正斜線) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-357">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="1be20-358">IP 位址中不允許使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="1be20-358">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="1be20-359">在下列案例中，顎化 (~) 字元是可用的：</span><span class="sxs-lookup"><span data-stu-id="1be20-359">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="1be20-360">左波形符表示網域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="1be20-360">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="1be20-361">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="1be20-361">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="1be20-362">包含通訊協定 (的 URL 專案例如， `http://` 、 `https://` 或 `ftp://`) 會失敗，因為 url 專案適用于所有通訊協定。</span><span class="sxs-lookup"><span data-stu-id="1be20-362">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="1be20-363">不支援或不需要使用者名稱或密碼。</span><span class="sxs-lookup"><span data-stu-id="1be20-363">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="1be20-364">引號 ( ' 或 ") 是不正確字元。</span><span class="sxs-lookup"><span data-stu-id="1be20-364">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="1be20-365">URL 應盡可能包括所有重新導向。</span><span class="sxs-lookup"><span data-stu-id="1be20-365">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="1be20-366">URL 專案案例</span><span class="sxs-lookup"><span data-stu-id="1be20-366">URL entry scenarios</span></span>

<span data-ttu-id="1be20-367">有效的 URL 專案及其結果將在下列各節中說明。</span><span class="sxs-lookup"><span data-stu-id="1be20-367">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="1be20-368">案例：沒有萬用字元</span><span class="sxs-lookup"><span data-stu-id="1be20-368">Scenario: No wildcards</span></span>

<span data-ttu-id="1be20-369">**專案**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1be20-369">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="1be20-370">**允許相符**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-370">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="1be20-371">**允許不符合**：</span><span class="sxs-lookup"><span data-stu-id="1be20-371">**Allow not matched**:</span></span>

  - <span data-ttu-id="1be20-372">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-372">abc-contoso.com</span></span>
  - <span data-ttu-id="1be20-373">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1be20-373">contoso.com/a</span></span>
  - <span data-ttu-id="1be20-374">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-374">payroll.contoso.com</span></span>
  - <span data-ttu-id="1be20-375">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-375">test.com/contoso.com</span></span>
  - <span data-ttu-id="1be20-376">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-376">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1be20-377">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-377">www.contoso.com</span></span>
  - <span data-ttu-id="1be20-378">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-378">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="1be20-379">**Block match**：</span><span class="sxs-lookup"><span data-stu-id="1be20-379">**Block match**:</span></span>

  - <span data-ttu-id="1be20-380">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-380">contoso.com</span></span>
  - <span data-ttu-id="1be20-381">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1be20-381">contoso.com/a</span></span>
  - <span data-ttu-id="1be20-382">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-382">payroll.contoso.com</span></span>
  - <span data-ttu-id="1be20-383">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-383">test.com/contoso.com</span></span>
  - <span data-ttu-id="1be20-384">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-384">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1be20-385">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-385">www.contoso.com</span></span>
  - <span data-ttu-id="1be20-386">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-386">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="1be20-387">**不符合的區塊**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-387">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="1be20-388">案例：保留萬用字元 (子域) </span><span class="sxs-lookup"><span data-stu-id="1be20-388">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="1be20-389">**專案**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1be20-389">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="1be20-390">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1be20-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1be20-391">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-391">www.contoso.com</span></span>
  - <span data-ttu-id="1be20-392">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-392">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1be20-393">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="1be20-393">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1be20-394">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-394">123contoso.com</span></span>
  - <span data-ttu-id="1be20-395">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-395">contoso.com</span></span>
  - <span data-ttu-id="1be20-396">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-396">test.com/contoso.com</span></span>
  - <span data-ttu-id="1be20-397">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1be20-397">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="1be20-398">案例：路徑頂端的右萬用字元</span><span class="sxs-lookup"><span data-stu-id="1be20-398">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="1be20-399">**專案**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="1be20-399">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="1be20-400">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1be20-400">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1be20-401">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="1be20-401">contoso.com/a/b</span></span>
  - <span data-ttu-id="1be20-402">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1be20-402">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1be20-403">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="1be20-403">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="1be20-404">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="1be20-404">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1be20-405">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-405">contoso.com</span></span>
  - <span data-ttu-id="1be20-406">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1be20-406">contoso.com/a</span></span>
  - <span data-ttu-id="1be20-407">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-407">www.contoso.com</span></span>
  - <span data-ttu-id="1be20-408">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-408">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="1be20-409">案例：左波形符</span><span class="sxs-lookup"><span data-stu-id="1be20-409">Scenario: Left tilde</span></span>

<span data-ttu-id="1be20-410">**專案**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1be20-410">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="1be20-411">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1be20-411">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1be20-412">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-412">contoso.com</span></span>
  - <span data-ttu-id="1be20-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-413">www.contoso.com</span></span>
  - <span data-ttu-id="1be20-414">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-414">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1be20-415">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="1be20-415">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1be20-416">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-416">123contoso.com</span></span>
  - <span data-ttu-id="1be20-417">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1be20-417">contoso.com/abc</span></span>
  - <span data-ttu-id="1be20-418">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1be20-418">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="1be20-419">案例：右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="1be20-419">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="1be20-420">**專案**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1be20-420">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="1be20-421">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1be20-421">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1be20-422">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1be20-422">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="1be20-423">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1be20-423">contoso.com/a</span></span>
  - <span data-ttu-id="1be20-424">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1be20-424">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1be20-425">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1be20-425">contoso.com/ab</span></span>
  - <span data-ttu-id="1be20-426">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1be20-426">contoso.com/b</span></span>
  - <span data-ttu-id="1be20-427">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1be20-427">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1be20-428">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1be20-428">contoso.com/ba</span></span>

- <span data-ttu-id="1be20-429">**允許不符合** 或 **不符合的封鎖**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-429">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="1be20-430">案例： Left 通配子域和右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="1be20-430">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="1be20-431">**專案**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1be20-431">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="1be20-432">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1be20-432">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1be20-433">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1be20-433">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="1be20-434">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1be20-434">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1be20-435">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1be20-435">www.contoso.com/a</span></span>
  - <span data-ttu-id="1be20-436">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1be20-436">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1be20-437">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1be20-437">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="1be20-438">**允許不符合** 或 **不符合的封鎖**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1be20-438">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="1be20-439">案例：左和右顎化符</span><span class="sxs-lookup"><span data-stu-id="1be20-439">Scenario: Left and right tilde</span></span>

<span data-ttu-id="1be20-440">**專案**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="1be20-440">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="1be20-441">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1be20-441">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1be20-442">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-442">contoso.com</span></span>
  - <span data-ttu-id="1be20-443">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1be20-443">contoso.com/a</span></span>
  - <span data-ttu-id="1be20-444">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-444">www.contoso.com</span></span>
  - <span data-ttu-id="1be20-445">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1be20-445">www.contoso.com/b</span></span>
  - <span data-ttu-id="1be20-446">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-446">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1be20-447">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="1be20-447">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1be20-448">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-448">123contoso.com</span></span>
  - <span data-ttu-id="1be20-449">contoso.org</span><span class="sxs-lookup"><span data-stu-id="1be20-449">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="1be20-450">案例： IP 位址</span><span class="sxs-lookup"><span data-stu-id="1be20-450">Scenario: IP address</span></span>

<span data-ttu-id="1be20-451">**專案**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="1be20-451">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="1be20-452">**允許** 比對和 **區塊相符**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="1be20-452">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="1be20-453">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="1be20-453">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1be20-454">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1be20-454">1.2.3.4/a</span></span>
  - <span data-ttu-id="1be20-455">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1be20-455">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="1be20-456">具有右萬用字元的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1be20-456">IP address with right wildcard</span></span>

<span data-ttu-id="1be20-457">**專案**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="1be20-457">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="1be20-458">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="1be20-458">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1be20-459">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="1be20-459">1.2.3.4/b</span></span>
  - <span data-ttu-id="1be20-460">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="1be20-460">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="1be20-461">無效專案的範例</span><span class="sxs-lookup"><span data-stu-id="1be20-461">Examples of invalid entries</span></span>

<span data-ttu-id="1be20-462">下列專案是不正確：</span><span class="sxs-lookup"><span data-stu-id="1be20-462">The following entries are invalid:</span></span>

- <span data-ttu-id="1be20-463">**遺失或不正確網域值**：</span><span class="sxs-lookup"><span data-stu-id="1be20-463">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="1be20-464">尚未</span><span class="sxs-lookup"><span data-stu-id="1be20-464">contoso</span></span>
  - <span data-ttu-id="1be20-465">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="1be20-465">\*.contoso.\*</span></span>
  - <span data-ttu-id="1be20-466">\*.com</span><span class="sxs-lookup"><span data-stu-id="1be20-466">\*.com</span></span>
  - <span data-ttu-id="1be20-467">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="1be20-467">\*.pdf</span></span>

- <span data-ttu-id="1be20-468">**文字上的萬用字元，或不含間距的字元**：</span><span class="sxs-lookup"><span data-stu-id="1be20-468">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="1be20-469">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="1be20-469">\*contoso.com</span></span>
  - <span data-ttu-id="1be20-470">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="1be20-470">contoso.com\*</span></span>
  - <span data-ttu-id="1be20-471">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="1be20-471">\*1.2.3.4</span></span>
  - <span data-ttu-id="1be20-472">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="1be20-472">1.2.3.4\*</span></span>
  - <span data-ttu-id="1be20-473">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="1be20-473">contoso.com/a\*</span></span>
  - <span data-ttu-id="1be20-474">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="1be20-474">contoso.com/ab\*</span></span>

- <span data-ttu-id="1be20-475">**含埠的 IP 位址**：</span><span class="sxs-lookup"><span data-stu-id="1be20-475">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="1be20-476">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="1be20-476">contoso.com:443</span></span>
  - <span data-ttu-id="1be20-477">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="1be20-477">abc.contoso.com:25</span></span>

- <span data-ttu-id="1be20-478">**非描述萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="1be20-478">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="1be20-479">\*.\*</span><span class="sxs-lookup"><span data-stu-id="1be20-479">\*.\*</span></span>

- <span data-ttu-id="1be20-480">**中間的萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="1be20-480">**Middle wildcards**:</span></span>

  - <span data-ttu-id="1be20-481">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="1be20-481">conto\*so.com</span></span>
  - <span data-ttu-id="1be20-482">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="1be20-482">conto~so.com</span></span>

- <span data-ttu-id="1be20-483">**兩個萬用字元**</span><span class="sxs-lookup"><span data-stu-id="1be20-483">**Double wildcards**</span></span>

  - <span data-ttu-id="1be20-484">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="1be20-484">contoso.com/\*\*</span></span>
  - <span data-ttu-id="1be20-485">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="1be20-485">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1be20-486">承租人允許/封鎖清單中的欺騙寄件者專案的網域對語法</span><span class="sxs-lookup"><span data-stu-id="1be20-486">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1be20-487">在承租人允許/封鎖清單中，欺騙寄件者的網域對使用下列語法： `<Spoofed user>, <Sending infrastructure>` 。</span><span class="sxs-lookup"><span data-stu-id="1be20-487">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="1be20-488">**冒牌使用者**：此值包含欺騙使用者的電子郵件地址，顯示在電子郵件客戶程式的 [ **寄件者** ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="1be20-488">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="1be20-489">此位址也稱為 `5322.From` 位址。</span><span class="sxs-lookup"><span data-stu-id="1be20-489">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="1be20-490">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="1be20-490">Valid values include:</span></span>
  - <span data-ttu-id="1be20-491">個別的電子郵件地址 (例如，chris@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-491">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="1be20-492">電子郵件網域 (例如，contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-492">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="1be20-493">通配字元 (例如， \*) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-493">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="1be20-494">傳送 **基礎結構**：此值表示來自欺騙使用者的郵件來源。</span><span class="sxs-lookup"><span data-stu-id="1be20-494">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="1be20-495">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="1be20-495">Valid values include:</span></span>
  - <span data-ttu-id="1be20-496">) 來源電子郵件伺服器的 IP 位址的反向 DNS 查閱 (PTR 記錄中找到的網域 (例如，fabrikam.com) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-496">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="1be20-497">如果來源 IP 位址沒有 PTR 記錄，則會將傳送基礎結構識別為 \<source IP\> /24 (例如，192.168.100.100/24) 。</span><span class="sxs-lookup"><span data-stu-id="1be20-497">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="1be20-498">以下是有效網域組的一些範例，用以識別冒牌寄件者：</span><span class="sxs-lookup"><span data-stu-id="1be20-498">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="1be20-499">新增網域對只會允許或封鎖欺騙使用者 *和* 傳送基礎結構的 *組合*。</span><span class="sxs-lookup"><span data-stu-id="1be20-499">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="1be20-500">它不允許來自欺騙使用者的電子郵件來自任何來源，也不允許任何欺騙使用者的傳送基礎結構來源傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1be20-500">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="1be20-501">例如，您新增下列網域對的 allow 專案：</span><span class="sxs-lookup"><span data-stu-id="1be20-501">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="1be20-502">**網域**： gmail.com</span><span class="sxs-lookup"><span data-stu-id="1be20-502">**Domain**: gmail.com</span></span>
- <span data-ttu-id="1be20-503">**基礎結構**： tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="1be20-503">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="1be20-504">只允許來自該網域 *和* 傳送基礎結構的郵件進行欺騙。</span><span class="sxs-lookup"><span data-stu-id="1be20-504">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="1be20-505">不允許其他企圖哄騙 gmail.com 的寄件者。</span><span class="sxs-lookup"><span data-stu-id="1be20-505">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="1be20-506">來自來自 tms.mx.com 的來自其他網域中寄件者的郵件會由哄騙情報檢查。</span><span class="sxs-lookup"><span data-stu-id="1be20-506">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
