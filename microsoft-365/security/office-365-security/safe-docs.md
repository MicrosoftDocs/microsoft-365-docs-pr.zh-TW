---
title: 適用於 Office 365 的 Microsoft Defender 中的安全文件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 深入瞭解 Microsoft 365 E5 或 Microsoft 365 E5 Security 中的安全檔。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1dc6c5dc54acd73b68fcd6241a270d2abdcc5c1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203572"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="74de3-103">Microsoft 365 E5 中的安全文件</span><span class="sxs-lookup"><span data-stu-id="74de3-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="74de3-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="74de3-104">**Applies to**</span></span>
- [<span data-ttu-id="74de3-105">適用於 Office 365 的 Microsoft Defender 方案 2</span><span class="sxs-lookup"><span data-stu-id="74de3-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="74de3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74de3-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="74de3-107">安全檔是 Microsoft 365 E5 或 Microsoft 365 E5 安全性中的一項功能，可使用 [Microsoft Defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 來掃描在 [受保護的檢視](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中開啟的檔和檔案。</span><span class="sxs-lookup"><span data-stu-id="74de3-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="74de3-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="74de3-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="74de3-109">只有使用 *Microsoft 365 e5* 或 *Microsoft 365 e5 安全性* 授權的使用者才能使用安全檔。</span><span class="sxs-lookup"><span data-stu-id="74de3-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="74de3-110">Microsoft Defender for Office 365 方案中並未包含這些授權。</span><span class="sxs-lookup"><span data-stu-id="74de3-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="74de3-111">Microsoft 365 Apps for enterprise (（以前稱為 Office 365 ProPlus) 版本2004或更新版本）支援安全檔。</span><span class="sxs-lookup"><span data-stu-id="74de3-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="74de3-112">您要在 <https://protection.office.com> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="74de3-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="74de3-113">若要直接移至 [ **ATP 安全附件** ] 頁面，請開啟] <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="74de3-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="74de3-114">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="74de3-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="74de3-115">您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：</span><span class="sxs-lookup"><span data-stu-id="74de3-115">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="74de3-116">若要設定安全檔設定，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="74de3-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="74de3-117">若要對安全檔設定進行唯讀存取，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="74de3-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="74de3-118">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="74de3-118">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="74de3-119">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="74de3-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="74de3-120">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="74de3-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="74de3-121">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="74de3-121">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="74de3-122">Microsoft 如何處理您的資料？</span><span class="sxs-lookup"><span data-stu-id="74de3-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="74de3-123">為了讓您受到保護，安全檔會將檔案傳送至 [Microsoft Defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud 進行分析。</span><span class="sxs-lookup"><span data-stu-id="74de3-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="74de3-124">您可以在以下位置找到 Microsoft Defender for Endpoint handles 資料的詳細資料： [Microsoft defender For endpoint data storage and 隱私權](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="74de3-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="74de3-125">安全檔所傳送的檔案不會保留在分析所需的時間，而不會保留在進行分析 (，但通常不會超過24小時) 。</span><span class="sxs-lookup"><span data-stu-id="74de3-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="74de3-126">使用安全性 & 規範中心設定安全檔</span><span class="sxs-lookup"><span data-stu-id="74de3-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="74de3-127">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全附件**]，然後按一下 [ **通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="74de3-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="74de3-128">在顯示的 [ **全域設定** ] 中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="74de3-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="74de3-129">**開啟 Office 用戶端的安全檔**：向右移動切換以開啟功能： ![ 開啟開啟 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="74de3-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="74de3-130">**即使安全檔會將檔案識別為惡意，允許人員按一下 [受保護的檢視**]：建議您保留此選項關閉， (保持向左切換：請 ![ 關閉 ](../../media/scc-toggle-off.png)) 。</span><span class="sxs-lookup"><span data-stu-id="74de3-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="74de3-131">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="74de3-131">When you're finished, click **Save**.</span></span>

   ![在 [安全附件] 頁面上選取全域設定後的 [安全檔] 設定。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="74de3-133">使用 Exchange Online PowerShell 設定安全檔</span><span class="sxs-lookup"><span data-stu-id="74de3-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="74de3-134">使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="74de3-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="74de3-135">_EnableSafeDocs_ 參數會啟用或停用整個組織的安全檔。</span><span class="sxs-lookup"><span data-stu-id="74de3-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="74de3-136">_AllowSafeDocsOpen_ 參數可允許或禁止使用者保留受保護的檢視 (也就是說，開啟檔) 如果檔已識別為惡意。</span><span class="sxs-lookup"><span data-stu-id="74de3-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="74de3-137">本範例會為整個組織啟用安全檔，並防止使用者開啟已從受保護的檢視識別為惡意的檔。</span><span class="sxs-lookup"><span data-stu-id="74de3-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="74de3-138">如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="74de3-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="74de3-139">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="74de3-139">How do I know this worked?</span></span>

<span data-ttu-id="74de3-140">若要確認您已啟用並設定安全檔，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="74de3-140">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="74de3-141">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全附件**]，按一下 [ **通用設定**]，然後確認 [ **開啟 Office 用戶端的安全檔** ]，而且 **即使安全檔識別為惡意設定，也可讓使用者依序按一下透過受保護的檢視** 。</span><span class="sxs-lookup"><span data-stu-id="74de3-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="74de3-142">在 Exchange Online PowerShell 中執行下列命令，並確認屬性值：</span><span class="sxs-lookup"><span data-stu-id="74de3-142">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="74de3-143">下列檔案可用於測試安全檔案保護。</span><span class="sxs-lookup"><span data-stu-id="74de3-143">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="74de3-144">這些檔與測試反惡意程式碼和反病毒解決方案的 EICAR.TXT 檔案類似。</span><span class="sxs-lookup"><span data-stu-id="74de3-144">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="74de3-145">檔案不會有害，但會觸發安全的檔案保護。</span><span class="sxs-lookup"><span data-stu-id="74de3-145">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="74de3-146">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="74de3-146">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="74de3-147">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="74de3-147">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="74de3-148">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="74de3-148">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)