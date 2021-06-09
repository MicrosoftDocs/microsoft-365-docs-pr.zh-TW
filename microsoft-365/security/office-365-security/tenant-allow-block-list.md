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
ms.openlocfilehash: 12139708fc5cde133819713fd7185435e594a1a9
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809176"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-103">管理租用戶允許/封鎖清單中</span><span class="sxs-lookup"><span data-stu-id="ec011-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ec011-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="ec011-104">**Applies to**</span></span>
- [<span data-ttu-id="ec011-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ec011-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ec011-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="ec011-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ec011-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec011-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="ec011-108">本文所述的功能都是在預覽中，可能會變更，而且無法在所有的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="ec011-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="ec011-109">如果您的組織沒有如本文所述的欺騙功能，請參閱 [使用哄騙智慧原則管理冒牌寄件者的舊版欺騙管理經驗和 EOP 中的欺騙智慧洞察力](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="ec011-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="ec011-110">在此時間內，您無法在 [租使用者允許/封鎖] 清單中 **設定** 允許的 URL 或檔專案。</span><span class="sxs-lookup"><span data-stu-id="ec011-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="ec011-111">在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織沒有 Exchange Online 信箱，您可能會反對 EOP 篩選判定。</span><span class="sxs-lookup"><span data-stu-id="ec011-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="ec011-112">例如，良好的郵件可能會標示為壞的 (誤報) 或不良郵件可以透過 (誤報) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="ec011-113">Security & 合規性中心內的承租人 Allow/封鎖清單，可讓您以手動方式覆寫 Microsoft 365 篩選 verdicts。</span><span class="sxs-lookup"><span data-stu-id="ec011-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="ec011-114">承租人允許/封鎖清單是在郵件流程期間和使用者按一下時使用。</span><span class="sxs-lookup"><span data-stu-id="ec011-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="ec011-115">您可以指定下列覆寫類型：</span><span class="sxs-lookup"><span data-stu-id="ec011-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="ec011-116">要封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="ec011-116">URLs to block.</span></span>
- <span data-ttu-id="ec011-117">要封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="ec011-117">Files to block.</span></span>
- <span data-ttu-id="ec011-118">要允許或封鎖的欺騙寄件者。</span><span class="sxs-lookup"><span data-stu-id="ec011-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="ec011-119">[！注意] 如果您在 [哄騙情報洞察力](learn-about-spoof-intelligence.md)中覆寫 allow 或 block 判定，則哄騙寄件者會變成隻會出現在 [租使用者允許/封鎖] 清單的 [ **哄騙** ] 索引標籤上的手動允許或封鎖專案。</span><span class="sxs-lookup"><span data-stu-id="ec011-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="ec011-120">您也可以在這裡，以欺騙的寄件者的方式手動建立允許或封鎖專案，以供欺詐情報偵測到。</span><span class="sxs-lookup"><span data-stu-id="ec011-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="ec011-121">本文說明如何在「安全性 & 合規性中心」或「PowerShell (Exchange Online PowerShell 中設定使用者在 Microsoft 365 中使用信箱的 Exchange Online 組織的專案。組織的獨立 EOP PowerShell，不 Exchange Online 信箱) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-121">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ec011-122">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="ec011-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ec011-123">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="ec011-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ec011-124">若要直接移至「 **租使用者允許/封鎖清單** 」頁面，請使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="ec011-124">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="ec011-125">您可以使用檔案的 SHA256 雜湊值來指定檔案。</span><span class="sxs-lookup"><span data-stu-id="ec011-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="ec011-126">若要在 Windows 中尋找檔案的 SHA256 雜湊值，請在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ec011-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="ec011-127">例如，此值可能為 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`。</span><span class="sxs-lookup"><span data-stu-id="ec011-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="ec011-128">不支援可感知雜湊 (pHash) 值。</span><span class="sxs-lookup"><span data-stu-id="ec011-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="ec011-129">在本文稍後的 [承租人允許/封鎖清單區段的 url 語法](#url-syntax-for-the-tenant-allowblock-list) 中，會說明可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="ec011-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="ec011-130">承租人允許/封鎖清單可為 URLs 和500專案提供檔案雜湊的最大值為500專案。</span><span class="sxs-lookup"><span data-stu-id="ec011-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="ec011-131">每個專案的字元數上限為：</span><span class="sxs-lookup"><span data-stu-id="ec011-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="ec011-132">檔雜湊 = 64</span><span class="sxs-lookup"><span data-stu-id="ec011-132">File hashes = 64</span></span>
  - <span data-ttu-id="ec011-133">URL= 250</span><span class="sxs-lookup"><span data-stu-id="ec011-133">URL = 250</span></span>

- <span data-ttu-id="ec011-134">專案應該在30分鐘內生效。</span><span class="sxs-lookup"><span data-stu-id="ec011-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="ec011-135">根據預設，承租人允許/封鎖清單中的專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="ec011-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="ec011-136">您可以指定日期或將其設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="ec011-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="ec011-137">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ec011-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ec011-138">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ec011-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ec011-139">您必須已在 Exchange Online 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="ec011-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ec011-140">**URLs 和** 檔案：</span><span class="sxs-lookup"><span data-stu-id="ec011-140">**URLs and files**:</span></span>
    - <span data-ttu-id="ec011-141">若要從 [承租人允許/封鎖] 清單中新增及移除值，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ec011-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="ec011-142">若要取得租使用者 Allow/封鎖清單的唯讀許可權，您必須是 **全域讀取** 者或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ec011-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="ec011-143">**哄騙**：下列其中一個組合：</span><span class="sxs-lookup"><span data-stu-id="ec011-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="ec011-144">**組織管理**</span><span class="sxs-lookup"><span data-stu-id="ec011-144">**Organization Management**</span></span>
    - <span data-ttu-id="ec011-145">**安全性管理員**<u>和</u> **View-Only** 設定或 **View-Only 組織管理**。</span><span class="sxs-lookup"><span data-stu-id="ec011-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="ec011-146">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="ec011-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="ec011-147">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="ec011-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ec011-148">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ec011-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="ec011-149">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="ec011-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-150">使用安全性 & 規範中心在承租人允許/封鎖清單中建立封鎖 URL 專案</span><span class="sxs-lookup"><span data-stu-id="ec011-150">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ec011-151">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="ec011-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ec011-152">在 [**承租人允許/封鎖清單**] 頁面上，確認已選取 [ **URLs** ] 索引標籤，然後按一下 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="ec011-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="ec011-153">在出現的 [ **封鎖 URLs** 浮出] 中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="ec011-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ec011-154">**新增封鎖 URLs**：每行輸入一個 URL，最多20個。</span><span class="sxs-lookup"><span data-stu-id="ec011-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="ec011-155">如需 URL 專案之語法的詳細資訊，請參閱本文稍後的 [承租人 Allow/封鎖清單區段的 URL 語法](#url-syntax-for-the-tenant-allowblock-list) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="ec011-156">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="ec011-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ec011-157">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="ec011-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="ec011-158">或</span><span class="sxs-lookup"><span data-stu-id="ec011-158">or</span></span>

     - <span data-ttu-id="ec011-159">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="ec011-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="ec011-161">.</span><span class="sxs-lookup"><span data-stu-id="ec011-161">.</span></span>

   - <span data-ttu-id="ec011-162">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="ec011-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ec011-163">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="ec011-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-164">使用安全性 & 規範中心在承租人允許/封鎖清單中建立封鎖檔案專案</span><span class="sxs-lookup"><span data-stu-id="ec011-164">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ec011-165">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="ec011-165">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ec011-166">在 [ **承租人允許/封鎖清單** **] 頁面** 上，選取 [檔案] 索引標籤，然後按一下 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="ec011-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="ec011-167">在 [ **新增要封鎖** 浮出的浮出] 快顯視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="ec011-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ec011-168">**新增檔案雜湊**：每行輸入一個 SHA256 雜湊值，最多20個。</span><span class="sxs-lookup"><span data-stu-id="ec011-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="ec011-169">**永不過期**：執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="ec011-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ec011-170">確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="ec011-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="ec011-171">或</span><span class="sxs-lookup"><span data-stu-id="ec011-171">or</span></span>

     - <span data-ttu-id="ec011-172">將切換向右移動，將專案設定為永不到期：</span><span class="sxs-lookup"><span data-stu-id="ec011-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![開啟](../../media/scc-toggle-on.png)<span data-ttu-id="ec011-174">.</span><span class="sxs-lookup"><span data-stu-id="ec011-174">.</span></span>

   - <span data-ttu-id="ec011-175">**選用附注**：輸入專案的描述性文字。</span><span class="sxs-lookup"><span data-stu-id="ec011-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ec011-176">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="ec011-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-177">使用安全性 & 規範中心在承租人允許/封鎖清單中建立允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="ec011-177">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ec011-178">**附註**：</span><span class="sxs-lookup"><span data-stu-id="ec011-178">**Notes**:</span></span>

- <span data-ttu-id="ec011-179">只會明確允許或封鎖欺騙使用者 _與_ 網域對中所定義之傳送基礎結構的 _組合_。</span><span class="sxs-lookup"><span data-stu-id="ec011-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="ec011-180">當您設定網域對的 allow 或封鎖專案時，來自該網域對的郵件就不會再出現在欺騙性智慧洞察力中。</span><span class="sxs-lookup"><span data-stu-id="ec011-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="ec011-181">欺騙寄件者的專案永不過期。</span><span class="sxs-lookup"><span data-stu-id="ec011-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="ec011-182">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="ec011-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ec011-183">在 [ **承租人允許/封鎖清單** ] 頁面上，選取 [ **哄騙** ] 索引標籤，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="ec011-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="ec011-184">在出現的 [ **新增網域配對** ] 浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="ec011-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ec011-185">**使用萬用字元新增網域配對**：每行輸入一個網域對，最多20個。</span><span class="sxs-lookup"><span data-stu-id="ec011-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="ec011-186">如需有關欺騙寄件者之語法的詳細資訊，請參閱本文稍後的 [承租人允許/封鎖清單區段中的欺騙寄件者專案的網域對語法](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="ec011-187">**哄騙類型**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="ec011-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="ec011-188">**Internal**：哄騙寄件者位於屬於您組織 ([公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 中的網域。</span><span class="sxs-lookup"><span data-stu-id="ec011-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="ec011-189">**外部**：冒牌寄件者位於外部網域。</span><span class="sxs-lookup"><span data-stu-id="ec011-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="ec011-190">**動作**：選取 [ **允許** ] 或 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="ec011-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="ec011-191">完成後，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="ec011-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-192">使用安全性 & 規範中心來查看承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="ec011-192">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ec011-193">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="ec011-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ec011-194">選取您想要的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ec011-194">Select the tab you want.</span></span> <span data-ttu-id="ec011-195">可用的欄取決於您所選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="ec011-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="ec011-196">**URLs**：</span><span class="sxs-lookup"><span data-stu-id="ec011-196">**URLs**:</span></span>
     - <span data-ttu-id="ec011-197">**值**： URL。</span><span class="sxs-lookup"><span data-stu-id="ec011-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="ec011-198">**動作**：值 **區塊**。</span><span class="sxs-lookup"><span data-stu-id="ec011-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="ec011-199">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="ec011-199">**Last updated date**</span></span>
     - <span data-ttu-id="ec011-200">**有效期**</span><span class="sxs-lookup"><span data-stu-id="ec011-200">**Expiration date**</span></span>
     - <span data-ttu-id="ec011-201">**附註**</span><span class="sxs-lookup"><span data-stu-id="ec011-201">**Note**</span></span>

   - <span data-ttu-id="ec011-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="ec011-202">**Files**</span></span>
     - <span data-ttu-id="ec011-203">**值**：檔雜湊。</span><span class="sxs-lookup"><span data-stu-id="ec011-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="ec011-204">**動作**：值 **區塊**。</span><span class="sxs-lookup"><span data-stu-id="ec011-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="ec011-205">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="ec011-205">**Last updated date**</span></span>
     - <span data-ttu-id="ec011-206">**有效期**</span><span class="sxs-lookup"><span data-stu-id="ec011-206">**Expiration date**</span></span>
     - <span data-ttu-id="ec011-207">**附註**</span><span class="sxs-lookup"><span data-stu-id="ec011-207">**Note**</span></span>

   - <span data-ttu-id="ec011-208">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="ec011-208">**Spoofing**</span></span>
     - <span data-ttu-id="ec011-209">**偽裝的使用者**</span><span class="sxs-lookup"><span data-stu-id="ec011-209">**Spoofed user**</span></span>
     - <span data-ttu-id="ec011-210">**傳送基礎結構**</span><span class="sxs-lookup"><span data-stu-id="ec011-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="ec011-211">**哄騙類型**：值 **Internal** 或 **External**。</span><span class="sxs-lookup"><span data-stu-id="ec011-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="ec011-212">**動作**：值 **組塊** 或 **Allow**。</span><span class="sxs-lookup"><span data-stu-id="ec011-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="ec011-213">您可以按一下欄標題，以遞增或遞減順序排序。</span><span class="sxs-lookup"><span data-stu-id="ec011-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="ec011-214">您可以按一下 [ **群組** ] 以群組結果。</span><span class="sxs-lookup"><span data-stu-id="ec011-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="ec011-215">可用的值取決於您所選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="ec011-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="ec011-216">**URLs**：您可以依 **動作** 將結果分組。</span><span class="sxs-lookup"><span data-stu-id="ec011-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="ec011-217">檔案 **：您** 可以依 **動作** 將結果分組。</span><span class="sxs-lookup"><span data-stu-id="ec011-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="ec011-218">在此索引標籤上無法使用 **群組\*\*\*\*的寄件者網域**。</span><span class="sxs-lookup"><span data-stu-id="ec011-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="ec011-219">**哄騙**：您可以依 **動作** 或 **偽造類型** 來分組結果。</span><span class="sxs-lookup"><span data-stu-id="ec011-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="ec011-220">按一下 [ **搜尋**]，輸入全部或部分的值，然後按 enter 以尋找特定值。</span><span class="sxs-lookup"><span data-stu-id="ec011-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="ec011-221">完成後，請按一下 [ **清除搜尋** ![ 清除搜尋] 圖示 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="ec011-222">按一下 [ **篩選** ] 以篩選結果。</span><span class="sxs-lookup"><span data-stu-id="ec011-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="ec011-223">顯示的 [ **篩選** ] 浮出控制項中可用的值，取決於您所選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="ec011-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="ec011-224">**URL**</span><span class="sxs-lookup"><span data-stu-id="ec011-224">**URLs**</span></span>
     - <span data-ttu-id="ec011-225">**Action**</span><span class="sxs-lookup"><span data-stu-id="ec011-225">**Action**</span></span>
     - <span data-ttu-id="ec011-226">**永不到期**</span><span class="sxs-lookup"><span data-stu-id="ec011-226">**Never expire**</span></span>
     - <span data-ttu-id="ec011-227">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="ec011-227">**Last updated date**</span></span>
     - <span data-ttu-id="ec011-228">**有效期**</span><span class="sxs-lookup"><span data-stu-id="ec011-228">**Expiration date**</span></span>

   - <span data-ttu-id="ec011-229">**Files**</span><span class="sxs-lookup"><span data-stu-id="ec011-229">**Files**</span></span>
     - <span data-ttu-id="ec011-230">**Action**</span><span class="sxs-lookup"><span data-stu-id="ec011-230">**Action**</span></span>
     - <span data-ttu-id="ec011-231">**永不到期**</span><span class="sxs-lookup"><span data-stu-id="ec011-231">**Never expire**</span></span>
     - <span data-ttu-id="ec011-232">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="ec011-232">**Last updated date**</span></span>
     - <span data-ttu-id="ec011-233">**有效期**</span><span class="sxs-lookup"><span data-stu-id="ec011-233">**Expiration date**</span></span>

   - <span data-ttu-id="ec011-234">**BCL 略過的寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="ec011-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="ec011-235">**永不到期**</span><span class="sxs-lookup"><span data-stu-id="ec011-235">**Never expire**</span></span>
     - <span data-ttu-id="ec011-236">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="ec011-236">**Last updated date**</span></span>
     - <span data-ttu-id="ec011-237">**有效期**</span><span class="sxs-lookup"><span data-stu-id="ec011-237">**Expiration date**</span></span>

   - <span data-ttu-id="ec011-238">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="ec011-238">**Spoofing**</span></span>
     - <span data-ttu-id="ec011-239">**Action**</span><span class="sxs-lookup"><span data-stu-id="ec011-239">**Action**</span></span>
     - <span data-ttu-id="ec011-240">**哄騙類型**</span><span class="sxs-lookup"><span data-stu-id="ec011-240">**Spoof type**</span></span>

   <span data-ttu-id="ec011-241">當您完成時 **，按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="ec011-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="ec011-242">若要清除現有篩選，請按一下 [ **篩選**]，然後在出現的 [ **篩選** ] 浮出控制項中按一下 [ **清除篩選**]。</span><span class="sxs-lookup"><span data-stu-id="ec011-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-243">使用安全性 & 規範中心修改承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="ec011-243">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ec011-244">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="ec011-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ec011-245">選取 [包含您要修改之專案類型的] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="ec011-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="ec011-246">**URL**</span><span class="sxs-lookup"><span data-stu-id="ec011-246">**URLs**</span></span>
   - <span data-ttu-id="ec011-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="ec011-247">**Files**</span></span>
   - <span data-ttu-id="ec011-248">**BCL 略過的寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="ec011-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="ec011-249">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="ec011-249">**Spoofing**</span></span>

3. <span data-ttu-id="ec011-250">選取您要修改的專案，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="ec011-251">您可以在出現的浮出控制項中修改的值，取決於您在上一個步驟中選取的索引標籤：</span><span class="sxs-lookup"><span data-stu-id="ec011-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="ec011-252">**URL**</span><span class="sxs-lookup"><span data-stu-id="ec011-252">**URLs**</span></span>
     - <span data-ttu-id="ec011-253">**永不到期** 及（或）到期日。</span><span class="sxs-lookup"><span data-stu-id="ec011-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="ec011-254">**選用附注**</span><span class="sxs-lookup"><span data-stu-id="ec011-254">**Optional note**</span></span>

   - <span data-ttu-id="ec011-255">**Files**</span><span class="sxs-lookup"><span data-stu-id="ec011-255">**Files**</span></span>
     - <span data-ttu-id="ec011-256">**永不到期** 及（或）到期日。</span><span class="sxs-lookup"><span data-stu-id="ec011-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="ec011-257">**選用附注**</span><span class="sxs-lookup"><span data-stu-id="ec011-257">**Optional note**</span></span>

   - <span data-ttu-id="ec011-258">**BCL 略過的寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="ec011-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="ec011-259">**永不到期** 及（或）到期日。</span><span class="sxs-lookup"><span data-stu-id="ec011-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="ec011-260">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="ec011-260">**Spoofing**</span></span>
     - <span data-ttu-id="ec011-261">**動作**：您可以將值變更為 [ **允許** ] 或 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="ec011-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="ec011-262">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ec011-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-263">使用安全性 & 規範中心移除承租人允許/封鎖清單中的專案</span><span class="sxs-lookup"><span data-stu-id="ec011-263">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ec011-264">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。</span><span class="sxs-lookup"><span data-stu-id="ec011-264">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ec011-265">選取 [包含您要移除之專案類型的] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="ec011-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="ec011-266">**URL**</span><span class="sxs-lookup"><span data-stu-id="ec011-266">**URLs**</span></span>
   - <span data-ttu-id="ec011-267">**Files**</span><span class="sxs-lookup"><span data-stu-id="ec011-267">**Files**</span></span>
   - <span data-ttu-id="ec011-268">**BCL 略過的寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="ec011-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="ec011-269">**詐騙**</span><span class="sxs-lookup"><span data-stu-id="ec011-269">**Spoofing**</span></span>

3. <span data-ttu-id="ec011-270">選取您要移除的專案，然後按一下 [ **刪除** ![ 刪除圖示] ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="ec011-271">在出現的警告對話方塊中，按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="ec011-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-272">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="ec011-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-273">使用 PowerShell 將封鎖檔案或 URL 專案新增至承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="ec011-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="ec011-274">若要在承租人允許/封鎖清單中新增封鎖檔或 URL 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ec011-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="ec011-275">這個範例會為永不到期的指定檔案新增封鎖檔專案。</span><span class="sxs-lookup"><span data-stu-id="ec011-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="ec011-276">這個範例會新增 contoso.com 及所有子域 (的封鎖 URL 專案（例如，contoso.com、www.contoso.com 及 xyz.abc.contoso.com) ）。</span><span class="sxs-lookup"><span data-stu-id="ec011-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="ec011-277">因為我們未使用 ExpirationDate 或 NoExpiration 參數，所以專案會在30天后到期。</span><span class="sxs-lookup"><span data-stu-id="ec011-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="ec011-278">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="ec011-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-279">使用 PowerShell 將允許或封鎖冒牌寄件者專案新增至承租人允許/封鎖清單</span><span class="sxs-lookup"><span data-stu-id="ec011-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="ec011-280">若要在承租人允許/封鎖清單中新增欺騙寄件者專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ec011-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="ec011-281">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="ec011-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-282">使用 PowerShell 在承租人允許/封鎖清單中查看封鎖檔案或 URL 專案</span><span class="sxs-lookup"><span data-stu-id="ec011-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ec011-283">若要在 [租使用者允許/封鎖] 清單中查看封鎖檔案或 URL 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ec011-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="ec011-284">此範例會傳回指定之檔案雜湊值的資訊。</span><span class="sxs-lookup"><span data-stu-id="ec011-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="ec011-285">本範例會傳回所有封鎖的 URLs。</span><span class="sxs-lookup"><span data-stu-id="ec011-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="ec011-286">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="ec011-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-287">在承租人允許/封鎖清單中使用 PowerShell 來查看允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="ec011-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ec011-288">若要在 [租使用者允許/封鎖] 清單中查看欺騙寄件者專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ec011-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="ec011-289">本範例會傳回 [承租人允許/封鎖] 清單中的所有冒牌寄件者專案。</span><span class="sxs-lookup"><span data-stu-id="ec011-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="ec011-290">此範例會傳回所有內部皆為內部的寄件者專案。</span><span class="sxs-lookup"><span data-stu-id="ec011-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="ec011-291">此範例會傳回所有外部已封鎖的寄件者專案。</span><span class="sxs-lookup"><span data-stu-id="ec011-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="ec011-292">如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="ec011-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-293">在承租人允許/封鎖清單中使用 PowerShell 修改區塊檔案與 URL 專案</span><span class="sxs-lookup"><span data-stu-id="ec011-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ec011-294">若要修改承租人 Allow/封鎖清單中的封鎖檔案及 URL 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ec011-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="ec011-295">本範例會變更指定的封鎖 URL 專案的到期日。</span><span class="sxs-lookup"><span data-stu-id="ec011-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="ec011-296">如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="ec011-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-297">使用 PowerShell 修改承租人 Allow/封鎖清單中的允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="ec011-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ec011-298">若要修改承租人 Allow/封鎖清單中的 [允許] 或 [封鎖欺騙的寄件者] 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ec011-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="ec011-299">本範例會將冒牌寄件者專案從 allow 變更為封鎖。</span><span class="sxs-lookup"><span data-stu-id="ec011-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="ec011-300">如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="ec011-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-301">使用 PowerShell 從承租人允許/封鎖清單移除 URL 或檔專案</span><span class="sxs-lookup"><span data-stu-id="ec011-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="ec011-302">若要從 [承租人允許/封鎖] 清單中移除檔案及 URL 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ec011-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="ec011-303">此範例會從承租人允許/封鎖清單中移除指定的封鎖 URL 專案。</span><span class="sxs-lookup"><span data-stu-id="ec011-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="ec011-304">如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="ec011-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-305">使用 PowerShell 從承租人允許/封鎖清單中移除允許或封鎖欺騙寄件者專案</span><span class="sxs-lookup"><span data-stu-id="ec011-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="ec011-306">若要從 [承租人允許/封鎖] 清單中移除 [允許] 或 [封鎖欺騙寄件者] 專案，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="ec011-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="ec011-307">如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="ec011-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-308">承租人允許/封鎖清單的 URL 語法</span><span class="sxs-lookup"><span data-stu-id="ec011-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="ec011-309">允許 IP4v 和 IPv6 位址，但不會 TCP/UDP 埠。</span><span class="sxs-lookup"><span data-stu-id="ec011-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="ec011-310">不允許使用副檔名 (例如，test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="ec011-311">不支援 Unicode，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="ec011-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="ec011-312">如果下列所有陳述皆為 true，則允許主機名稱：</span><span class="sxs-lookup"><span data-stu-id="ec011-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="ec011-313">主機名稱包含句點。</span><span class="sxs-lookup"><span data-stu-id="ec011-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="ec011-314">句點的左側至少有一個字元。</span><span class="sxs-lookup"><span data-stu-id="ec011-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="ec011-315">句點右側至少有兩個字元。</span><span class="sxs-lookup"><span data-stu-id="ec011-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="ec011-316">例如， `t.co` 允許; `.com` 或是 `contoso.` 不允許。</span><span class="sxs-lookup"><span data-stu-id="ec011-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="ec011-317">不暗含子路徑。</span><span class="sxs-lookup"><span data-stu-id="ec011-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="ec011-318">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="ec011-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="ec011-319">在下列案例中，允許使用萬用字元 ( \* ) ：</span><span class="sxs-lookup"><span data-stu-id="ec011-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="ec011-320">左邊的萬用字元必須後接句點，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="ec011-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="ec011-321">例如， `*.contoso.com` 允許; `*contoso.com` 是不允許的。</span><span class="sxs-lookup"><span data-stu-id="ec011-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="ec011-322">右萬用字元必須跟隨正斜線 (/) 來指定路徑。</span><span class="sxs-lookup"><span data-stu-id="ec011-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="ec011-323">例如， `contoso.com/*` 允許; `contoso.com*` 或是 `contoso.com/ab*` 不允許。</span><span class="sxs-lookup"><span data-stu-id="ec011-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="ec011-324">所有的子路徑都不是以右邊的萬用字元隱含。</span><span class="sxs-lookup"><span data-stu-id="ec011-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="ec011-325">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="ec011-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="ec011-326">`*.com*` 無效 (不是可解析的網域，正確的萬用字元不遵循正斜線) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="ec011-327">IP 位址中不允許使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="ec011-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="ec011-328">在下列案例中，顎化 (~) 字元是可用的：</span><span class="sxs-lookup"><span data-stu-id="ec011-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="ec011-329">左波形符表示網域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="ec011-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="ec011-330">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="ec011-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="ec011-331">包含通訊協定 (的 URL 專案例如， `http://` 、 `https://` 或 `ftp://`) 會失敗，因為 url 專案適用于所有通訊協定。</span><span class="sxs-lookup"><span data-stu-id="ec011-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="ec011-332">不支援或不需要使用者名稱或密碼。</span><span class="sxs-lookup"><span data-stu-id="ec011-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="ec011-333">引號 ( ' 或 ") 是不正確字元。</span><span class="sxs-lookup"><span data-stu-id="ec011-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="ec011-334">URL 應盡可能包括所有重新導向。</span><span class="sxs-lookup"><span data-stu-id="ec011-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="ec011-335">URL 專案案例</span><span class="sxs-lookup"><span data-stu-id="ec011-335">URL entry scenarios</span></span>

<span data-ttu-id="ec011-336">有效的 URL 專案及其結果將在下列各節中說明。</span><span class="sxs-lookup"><span data-stu-id="ec011-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="ec011-337">案例：沒有萬用字元</span><span class="sxs-lookup"><span data-stu-id="ec011-337">Scenario: No wildcards</span></span>

<span data-ttu-id="ec011-338">**專案**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ec011-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="ec011-339">**允許相符**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="ec011-340">**允許不符合**：</span><span class="sxs-lookup"><span data-stu-id="ec011-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="ec011-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-341">abc-contoso.com</span></span>
  - <span data-ttu-id="ec011-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ec011-342">contoso.com/a</span></span>
  - <span data-ttu-id="ec011-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="ec011-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="ec011-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ec011-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-346">www.contoso.com</span></span>
  - <span data-ttu-id="ec011-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ec011-348">**Block match**：</span><span class="sxs-lookup"><span data-stu-id="ec011-348">**Block match**:</span></span>

  - <span data-ttu-id="ec011-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-349">contoso.com</span></span>
  - <span data-ttu-id="ec011-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ec011-350">contoso.com/a</span></span>
  - <span data-ttu-id="ec011-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="ec011-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="ec011-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ec011-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-354">www.contoso.com</span></span>
  - <span data-ttu-id="ec011-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ec011-356">**不符合的區塊**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="ec011-357">案例：保留萬用字元 (子域) </span><span class="sxs-lookup"><span data-stu-id="ec011-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="ec011-358">**專案**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ec011-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="ec011-359">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="ec011-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ec011-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-360">www.contoso.com</span></span>
  - <span data-ttu-id="ec011-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ec011-362">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="ec011-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ec011-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-363">123contoso.com</span></span>
  - <span data-ttu-id="ec011-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-364">contoso.com</span></span>
  - <span data-ttu-id="ec011-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="ec011-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ec011-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="ec011-367">案例：路徑頂端的右萬用字元</span><span class="sxs-lookup"><span data-stu-id="ec011-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="ec011-368">**專案**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="ec011-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="ec011-369">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="ec011-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ec011-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="ec011-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="ec011-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ec011-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ec011-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="ec011-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="ec011-373">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="ec011-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ec011-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-374">contoso.com</span></span>
  - <span data-ttu-id="ec011-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ec011-375">contoso.com/a</span></span>
  - <span data-ttu-id="ec011-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-376">www.contoso.com</span></span>
  - <span data-ttu-id="ec011-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="ec011-378">案例：左波形符</span><span class="sxs-lookup"><span data-stu-id="ec011-378">Scenario: Left tilde</span></span>

<span data-ttu-id="ec011-379">**專案**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ec011-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="ec011-380">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="ec011-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ec011-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-381">contoso.com</span></span>
  - <span data-ttu-id="ec011-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-382">www.contoso.com</span></span>
  - <span data-ttu-id="ec011-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ec011-384">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="ec011-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ec011-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-385">123contoso.com</span></span>
  - <span data-ttu-id="ec011-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ec011-386">contoso.com/abc</span></span>
  - <span data-ttu-id="ec011-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ec011-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="ec011-388">案例：右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="ec011-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="ec011-389">**專案**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ec011-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="ec011-390">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="ec011-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ec011-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ec011-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="ec011-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ec011-392">contoso.com/a</span></span>
  - <span data-ttu-id="ec011-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ec011-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ec011-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ec011-394">contoso.com/ab</span></span>
  - <span data-ttu-id="ec011-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ec011-395">contoso.com/b</span></span>
  - <span data-ttu-id="ec011-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ec011-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ec011-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ec011-397">contoso.com/ba</span></span>

- <span data-ttu-id="ec011-398">**允許不符合** 或 **不符合的封鎖**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="ec011-399">案例： Left 通配子域和右萬用字元尾碼</span><span class="sxs-lookup"><span data-stu-id="ec011-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="ec011-400">**專案**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ec011-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="ec011-401">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="ec011-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ec011-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ec011-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="ec011-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ec011-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ec011-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ec011-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="ec011-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ec011-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ec011-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ec011-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="ec011-407">**允許不符合** 或 **不符合的封鎖**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ec011-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="ec011-408">案例：左和右顎化符</span><span class="sxs-lookup"><span data-stu-id="ec011-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="ec011-409">**專案**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="ec011-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="ec011-410">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="ec011-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ec011-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-411">contoso.com</span></span>
  - <span data-ttu-id="ec011-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ec011-412">contoso.com/a</span></span>
  - <span data-ttu-id="ec011-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-413">www.contoso.com</span></span>
  - <span data-ttu-id="ec011-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ec011-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="ec011-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ec011-416">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="ec011-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ec011-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-417">123contoso.com</span></span>
  - <span data-ttu-id="ec011-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="ec011-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="ec011-419">案例： IP 位址</span><span class="sxs-lookup"><span data-stu-id="ec011-419">Scenario: IP address</span></span>

<span data-ttu-id="ec011-420">**專案**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="ec011-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="ec011-421">**允許** 比對和 **區塊相符**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="ec011-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="ec011-422">**允許不符合** 或 **不符合的封鎖**：</span><span class="sxs-lookup"><span data-stu-id="ec011-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ec011-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ec011-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="ec011-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ec011-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="ec011-425">具有右萬用字元的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ec011-425">IP address with right wildcard</span></span>

<span data-ttu-id="ec011-426">**專案**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="ec011-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="ec011-427">**允許相符** 和 **區塊相符**：</span><span class="sxs-lookup"><span data-stu-id="ec011-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ec011-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="ec011-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="ec011-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="ec011-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="ec011-430">無效專案的範例</span><span class="sxs-lookup"><span data-stu-id="ec011-430">Examples of invalid entries</span></span>

<span data-ttu-id="ec011-431">下列專案是不正確：</span><span class="sxs-lookup"><span data-stu-id="ec011-431">The following entries are invalid:</span></span>

- <span data-ttu-id="ec011-432">**遺失或不正確網域值**：</span><span class="sxs-lookup"><span data-stu-id="ec011-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="ec011-433">尚未</span><span class="sxs-lookup"><span data-stu-id="ec011-433">contoso</span></span>
  - <span data-ttu-id="ec011-434">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="ec011-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="ec011-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="ec011-435">\*.com</span></span>
  - <span data-ttu-id="ec011-436">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="ec011-436">\*.pdf</span></span>

- <span data-ttu-id="ec011-437">**文字上的萬用字元，或不含間距的字元**：</span><span class="sxs-lookup"><span data-stu-id="ec011-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="ec011-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec011-438">\*contoso.com</span></span>
  - <span data-ttu-id="ec011-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="ec011-439">contoso.com\*</span></span>
  - <span data-ttu-id="ec011-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ec011-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="ec011-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="ec011-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="ec011-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="ec011-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="ec011-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="ec011-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="ec011-444">**含埠的 IP 位址**：</span><span class="sxs-lookup"><span data-stu-id="ec011-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="ec011-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="ec011-445">contoso.com:443</span></span>
  - <span data-ttu-id="ec011-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="ec011-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="ec011-447">**非描述萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="ec011-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="ec011-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="ec011-448">\*.\*</span></span>

- <span data-ttu-id="ec011-449">**中間的萬用字元**：</span><span class="sxs-lookup"><span data-stu-id="ec011-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="ec011-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="ec011-450">conto\*so.com</span></span>
  - <span data-ttu-id="ec011-451">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="ec011-451">conto~so.com</span></span>

- <span data-ttu-id="ec011-452">**兩個萬用字元**</span><span class="sxs-lookup"><span data-stu-id="ec011-452">**Double wildcards**</span></span>

  - <span data-ttu-id="ec011-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="ec011-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="ec011-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="ec011-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ec011-455">承租人允許/封鎖清單中的欺騙寄件者專案的網域對語法</span><span class="sxs-lookup"><span data-stu-id="ec011-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ec011-456">在承租人允許/封鎖清單中，欺騙寄件者的網域對使用下列語法： `<Spoofed user>, <Sending infrastructure>` 。</span><span class="sxs-lookup"><span data-stu-id="ec011-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="ec011-457">**冒牌使用者**：此值包含欺騙使用者的電子郵件地址，顯示在電子郵件客戶程式的 [ **寄件者** ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="ec011-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="ec011-458">此位址也稱為 `5322.From` 位址。</span><span class="sxs-lookup"><span data-stu-id="ec011-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="ec011-459">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="ec011-459">Valid values include:</span></span>
  - <span data-ttu-id="ec011-460">個別的電子郵件地址 (例如，chris@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="ec011-461">電子郵件網域 (例如，contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="ec011-462">通配字元 (例如， \*) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="ec011-463">傳送 **基礎結構**：此值表示來自欺騙使用者的郵件來源。</span><span class="sxs-lookup"><span data-stu-id="ec011-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="ec011-464">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="ec011-464">Valid values include:</span></span>
  - <span data-ttu-id="ec011-465">) 來源電子郵件伺服器的 IP 位址的反向 DNS 查閱 (PTR 記錄中找到的網域 (例如，fabrikam.com) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="ec011-466">如果來源 IP 位址沒有 PTR 記錄，則會將傳送基礎結構識別為 \<source IP\> /24 (例如，192.168.100.100/24) 。</span><span class="sxs-lookup"><span data-stu-id="ec011-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="ec011-467">以下是有效網域組的一些範例，用以識別冒牌寄件者：</span><span class="sxs-lookup"><span data-stu-id="ec011-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="ec011-468">欺騙寄件者專案的數目上限為1000。</span><span class="sxs-lookup"><span data-stu-id="ec011-468">The maximum number of spoofed sender entries is 1000.</span></span> 

<span data-ttu-id="ec011-469">新增網域對只會允許或封鎖欺騙使用者 *和* 傳送基礎結構的 *組合*。</span><span class="sxs-lookup"><span data-stu-id="ec011-469">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="ec011-470">它不允許來自欺騙使用者的電子郵件來自任何來源，也不允許任何欺騙使用者的傳送基礎結構來源傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ec011-470">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="ec011-471">例如，您新增下列網域對的 allow 專案：</span><span class="sxs-lookup"><span data-stu-id="ec011-471">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="ec011-472">**網域**： gmail.com</span><span class="sxs-lookup"><span data-stu-id="ec011-472">**Domain**: gmail.com</span></span>
- <span data-ttu-id="ec011-473">**基礎結構**： tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="ec011-473">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="ec011-474">只允許來自該網域 *和* 傳送基礎結構的郵件進行欺騙。</span><span class="sxs-lookup"><span data-stu-id="ec011-474">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="ec011-475">不允許其他企圖哄騙 gmail.com 的寄件者。</span><span class="sxs-lookup"><span data-stu-id="ec011-475">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="ec011-476">來自來自 tms.mx.com 的來自其他網域中寄件者的郵件會由哄騙情報檢查。</span><span class="sxs-lookup"><span data-stu-id="ec011-476">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
