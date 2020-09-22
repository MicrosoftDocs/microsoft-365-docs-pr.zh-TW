---
title: Office 365 ATP 中的安全文件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 深入瞭解 Microsoft 365 E5 或 Microsoft 365 E5 Security 中的安全檔。
ms.openlocfilehash: d2220bb088ddf6e739b79212c3c1f7f0ac7bd865
ms.sourcegitcommit: dcbcd5ef278949c777059b0aa6db072e821f72dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "48173293"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="39326-103">Microsoft 365 E5 中的安全檔</span><span class="sxs-lookup"><span data-stu-id="39326-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="39326-104">安全檔是 Microsoft 365 E5 或 Microsoft 365 E5 安全性中的一項功能，可使用 [Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 來掃描在 [受保護的檢視](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中開啟的檔和檔案。</span><span class="sxs-lookup"><span data-stu-id="39326-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="39326-105">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="39326-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="39326-106">只有使用 *Microsoft 365 e5* 或 *Microsoft 365 e5 安全性* 授權的使用者才能使用安全檔。</span><span class="sxs-lookup"><span data-stu-id="39326-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="39326-107">這些授權不包含在 Office 365 Advanced 威脅防護 (ATP) 方案中。</span><span class="sxs-lookup"><span data-stu-id="39326-107">These licenses are not included in Office 365 Advanced Threat Protection (ATP) plans.</span></span>

- <span data-ttu-id="39326-108">您要在 <https://protection.office.com> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="39326-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="39326-109">若要直接移至 [ **ATP 安全附件** ] 頁面，請開啟] <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="39326-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="39326-110">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="39326-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="39326-111">您必須已獲指派許可權，才能執行本主題中的程式。</span><span class="sxs-lookup"><span data-stu-id="39326-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="39326-112">若要啟用及設定安全檔，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="39326-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="39326-113">如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="39326-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="39326-114">Microsoft 如何處理您的資料？</span><span class="sxs-lookup"><span data-stu-id="39326-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="39326-115">為了讓您受到保護，安全檔會將檔案傳送至 [Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 雲端，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="39326-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="39326-116">您可以在以下位置找到 Microsoft Defender ATP 如何處理資料的詳細資訊： [Microsoft DEFENDER atp 資料儲存區和隱私權](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="39326-116">Details on how Microsoft Defender ATP handles your data can be found here: [Microsoft Defender ATP data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="39326-117">安全檔所傳送的檔案不會保留在分析所需的時間，而不會保留在進行分析 (，但通常不會超過24小時) 。</span><span class="sxs-lookup"><span data-stu-id="39326-117">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="39326-118">使用安全性 & 規範中心設定安全檔</span><span class="sxs-lookup"><span data-stu-id="39326-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="39326-119">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全附件**]，然後按一下 [ **通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="39326-119">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="39326-120">在顯示的 [ **全域設定** ] 中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="39326-120">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="39326-121">**開啟 Office 用戶端的安全檔**：向右移動切換以開啟功能： ![ 開啟開啟 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。</span><span class="sxs-lookup"><span data-stu-id="39326-121">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="39326-122">**即使安全檔會將檔案識別為惡意，允許人員按一下 [受保護的檢視**]：建議您保留此選項關閉， (保持向左切換：請 ![ 關閉 ](../../media/scc-toggle-off.png)) 。</span><span class="sxs-lookup"><span data-stu-id="39326-122">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="39326-123">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39326-123">When you're finished, click **Save**.</span></span>

   ![在 [ATP 安全附件] 頁面上選取全域設定後的 [安全檔] 設定。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="39326-125">使用 Exchange Online PowerShell 設定安全檔</span><span class="sxs-lookup"><span data-stu-id="39326-125">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="39326-126">使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="39326-126">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="39326-127">_EnableSafeDocs_參數會啟用或停用整個組織的安全檔。</span><span class="sxs-lookup"><span data-stu-id="39326-127">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="39326-128">_AllowSafeDocsOpen_參數可允許或禁止使用者保留受保護的檢視 (也就是說，開啟檔) 如果檔已識別為惡意。</span><span class="sxs-lookup"><span data-stu-id="39326-128">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="39326-129">本範例會為整個組織啟用安全檔，並防止使用者開啟已從受保護的檢視識別為惡意的檔。</span><span class="sxs-lookup"><span data-stu-id="39326-129">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="39326-130">如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="39326-130">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="39326-131">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="39326-131">How do I know this worked?</span></span>

<span data-ttu-id="39326-132">若要確認您已啟用並設定安全檔，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="39326-132">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="39326-133">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全附件**]，按一下 [ **通用設定**]，然後確認 [ **開啟 Office 用戶端的安全檔** ]，而且 **即使安全檔識別為惡意設定，也可讓使用者依序按一下透過受保護的檢視** 。</span><span class="sxs-lookup"><span data-stu-id="39326-133">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="39326-134">在 Exchange Online PowerShell 中執行下列命令，並確認屬性值：</span><span class="sxs-lookup"><span data-stu-id="39326-134">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="39326-135">下列檔案可用於測試安全檔案保護。</span><span class="sxs-lookup"><span data-stu-id="39326-135">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="39326-136">這些檔與測試反惡意程式碼和反病毒解決方案的 EICAR.TXT 檔案類似。</span><span class="sxs-lookup"><span data-stu-id="39326-136">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="39326-137">檔案不會有害，但會觸發安全的檔案保護。</span><span class="sxs-lookup"><span data-stu-id="39326-137">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="39326-138">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="39326-138">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="39326-139">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="39326-139">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="39326-140">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="39326-140">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
