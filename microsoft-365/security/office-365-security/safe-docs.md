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
description: 深入瞭解 Microsoft 365 E5 或 Microsoft 365 E5 安全性中的保管庫檔。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e1bd2150a04e51e0d06c6cd1c17a71a032df1a5
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108604"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="b9a39-103">Microsoft 365 E5 中的安全文件</span><span class="sxs-lookup"><span data-stu-id="b9a39-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b9a39-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="b9a39-104">**Applies to**</span></span>
- [<span data-ttu-id="b9a39-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9a39-105">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b9a39-106">保管庫檔是 Microsoft 365 E5 或 Microsoft 365 E5 安全性中的功能，可使用[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)掃描在[受保護的檢視](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中開啟的檔和檔案，或在 Office 中開啟[應用程式防護](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)。</span><span class="sxs-lookup"><span data-stu-id="b9a39-106">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b9a39-107">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="b9a39-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b9a39-108">保管庫只有具有 *Microsoft 365 E5* 或 *Microsoft 365 E5 安全性* 授權的使用者才能使用檔。</span><span class="sxs-lookup"><span data-stu-id="b9a39-108">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="b9a39-109">這些授權不會包含在 Microsoft Defender 中 Office 365 計畫。</span><span class="sxs-lookup"><span data-stu-id="b9a39-109">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="b9a39-110">保管庫在以前稱為 Office 365 專業增強版) 版本2004或更新版本的 Microsoft 365 Apps 企業版 (中支援檔。</span><span class="sxs-lookup"><span data-stu-id="b9a39-110">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="b9a39-111">您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="b9a39-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="b9a39-112">若要直接移至 [**保管庫附件**] 頁面，請使用 <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="b9a39-112">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="b9a39-113">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b9a39-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b9a39-114">您需要 **Exchange Online** 中的許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="b9a39-114">You need permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b9a39-115">若要設定保管庫檔設定，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b9a39-115">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="b9a39-116">若要唯讀的保管庫檔設定的存取權，您必須是 **全域讀取器** 或 **安全性讀者** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b9a39-116">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="b9a39-117">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="b9a39-117">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="b9a39-118">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="b9a39-118">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b9a39-119">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="b9a39-119">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="b9a39-120">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="b9a39-120">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="b9a39-121">Microsoft 如何處理您的資料？</span><span class="sxs-lookup"><span data-stu-id="b9a39-121">How does Microsoft handle your data?</span></span>

<span data-ttu-id="b9a39-122">為了讓您受到保護，保管庫檔會將檔案傳送至[Microsoft Defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud 進行分析。</span><span class="sxs-lookup"><span data-stu-id="b9a39-122">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="b9a39-123">您可以在以下位置找到 Microsoft Defender for Endpoint handles 資料的詳細資料： [Microsoft defender For endpoint data storage and 隱私權](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="b9a39-123">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="b9a39-124">保管庫檔所傳送的檔案不會保留在分析所需的時間內，而不會保留在進行分析所需的時間 (通常是小於24小時) </span><span class="sxs-lookup"><span data-stu-id="b9a39-124">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-microsoft-365-defender-to-configure-safe-documents"></a><span data-ttu-id="b9a39-125">使用 Microsoft 365 Defender 設定保管庫檔</span><span class="sxs-lookup"><span data-stu-id="b9a39-125">Use the Microsoft 365 Defender to configure Safe Documents</span></span>

1. <span data-ttu-id="b9a39-126">開啟 Microsoft 365 Defender 入口網站，然後移至 **電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則**] 頁面 \> **策略** 區段 \> **保管庫附件**。</span><span class="sxs-lookup"><span data-stu-id="b9a39-126">Open the Microsoft 365 Defender portal and go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="b9a39-127">在 [**保管庫附件**] 頁面上，按一下 [**通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="b9a39-127">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="b9a39-128">在顯示的 [ **全域設定** ] 中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="b9a39-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>
   - <span data-ttu-id="b9a39-129">**開啟 Office 用戶端的保管庫檔**：將切換移至右邊開啟功能： ![ 開啟 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="b9a39-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="b9a39-130">**即使保管庫檔識別為惡意的檔案，也可讓使用者依序按一下 [受保護的檢視**]：我們建議您保留此選項關閉 (保持向左切換： ![ 關閉 ](../../media/scc-toggle-off.png)) 。</span><span class="sxs-lookup"><span data-stu-id="b9a39-130">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="b9a39-131">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="b9a39-131">When you're finished, click **Save**.</span></span>

   ![保管庫在 [保管庫附件] 頁面上選取全域設定之後的檔設定。](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="b9a39-133">使用 Exchange Online PowerShell 設定保管庫檔</span><span class="sxs-lookup"><span data-stu-id="b9a39-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="b9a39-134">使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="b9a39-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="b9a39-135">_EnableSafeDocs_ 參數會啟用或停用整個組織的保管庫檔。</span><span class="sxs-lookup"><span data-stu-id="b9a39-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="b9a39-136">_AllowSafeDocsOpen_ 參數可允許或禁止使用者保留受保護的檢視 (也就是說，開啟檔) 如果檔已識別為惡意。</span><span class="sxs-lookup"><span data-stu-id="b9a39-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="b9a39-137">本範例會為整個組織啟用保管庫檔，並防止使用者開啟已從受保護的檢視識別為惡意的檔。</span><span class="sxs-lookup"><span data-stu-id="b9a39-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="b9a39-138">如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="b9a39-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="b9a39-139">已在 Microsoft Defender for Endpoint Service 上板載以啟用審核功能</span><span class="sxs-lookup"><span data-stu-id="b9a39-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="b9a39-140">若要部署 Microsoft Defender for Endpoint，您需要經歷各個部署階段。</span><span class="sxs-lookup"><span data-stu-id="b9a39-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="b9a39-141">在上架之後，您可以在 Microsoft 365 Defender 入口網站中設定審核功能。</span><span class="sxs-lookup"><span data-stu-id="b9a39-141">After onboarding, you can configure auditing capabilities in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="b9a39-142">若要深入瞭解，請參閱 [在 Microsoft Defender For Endpoint service 上的板載](/microsoft-365/security/defender-endpoint/onboarding)。</span><span class="sxs-lookup"><span data-stu-id="b9a39-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="b9a39-143">如果您需要其他協助，請參閱 [疑難排解 Microsoft Defender 的端點上架問題](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="b9a39-143">If you need additional help, refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="b9a39-144">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="b9a39-144">How do I know this worked?</span></span>

<span data-ttu-id="b9a39-145">若要確認您已啟用並設定保管庫檔，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="b9a39-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="b9a39-146">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** \> **威脅原則**] 頁面 \> **原則**] 區域 \> **保管庫附件** \> **全域設定**，並驗證是否 **開啟保管庫用戶端的 Office 檔**，以及是否 **允許使用者在保管庫的檔識別為惡意設定時按一下 [受保護的檢視**]。</span><span class="sxs-lookup"><span data-stu-id="b9a39-146">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments** \> **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="b9a39-147">在 Exchange Online PowerShell 中執行下列命令，並確認屬性值：</span><span class="sxs-lookup"><span data-stu-id="b9a39-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="b9a39-148">下列檔案可用於測試保管庫檔案保護。</span><span class="sxs-lookup"><span data-stu-id="b9a39-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="b9a39-149">這些檔與測試反惡意程式碼和反病毒解決方案的 EICAR.TXT 檔案類似。</span><span class="sxs-lookup"><span data-stu-id="b9a39-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="b9a39-150">檔案不會有害，但會觸發保管庫檔案保護功能。</span><span class="sxs-lookup"><span data-stu-id="b9a39-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="b9a39-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="b9a39-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="b9a39-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="b9a39-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="b9a39-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="b9a39-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
