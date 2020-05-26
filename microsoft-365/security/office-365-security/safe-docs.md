---
title: Office 365 ATP 中的安全文件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 深入瞭解 Office 365 ATP 中的安全檔。
ms.openlocfilehash: f792b1acbdacfd29db5bbbf377f41396c35e3f17
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350948"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a><span data-ttu-id="777e5-103">Office 365 進階威脅防護中的安全文件</span><span class="sxs-lookup"><span data-stu-id="777e5-103">Safe Documents in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="777e5-104">安全檔是 Office 365 高級威脅防護（Office 365 ATP）中的一項功能，可使用[Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)來掃描在[受保護的檢視](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中開啟的檔和檔案。</span><span class="sxs-lookup"><span data-stu-id="777e5-104">Safe Documents is a feature in Office 365 Advanced Threat Protection (Office 365 ATP) that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="777e5-105">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="777e5-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="777e5-106">只有使用 Microsoft 365 E5 或 Microsoft 365 E5 安全性授權的使用者才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="777e5-106">This feature is only available to users with the Microsoft 365 E5 or Microsoft 365 E5 Security license.</span></span>

- <span data-ttu-id="777e5-107">安全檔目前可用於公開預覽，可供屬於 office 版本為2002（12527.20092）或更高版本的[Office 預覽人員計畫](https://insider.office.com/en-us/join)中的使用者。</span><span class="sxs-lookup"><span data-stu-id="777e5-107">Safe Documents is currently available for public preview, available to users that are part of the [Office Insider Program](https://insider.office.com/en-us/join) on the 'Monthly Channel (Targeted)' with Office Version 2002 (12527.20092) or greater.</span></span> <span data-ttu-id="777e5-108">此功能預設為關閉，必須由安全性管理員啟用。</span><span class="sxs-lookup"><span data-stu-id="777e5-108">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="777e5-109">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="777e5-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="777e5-110">若要連線至獨立 EOP PowerShell，請參閱[connect To Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="777e5-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="777e5-111">您必須已獲指派許可權，才能執行本主題中的程式。</span><span class="sxs-lookup"><span data-stu-id="777e5-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="777e5-112">若要啟用及設定安全檔，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="777e5-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="777e5-113">如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱[安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="777e5-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="777e5-114">Microsoft 如何處理您的資料？</span><span class="sxs-lookup"><span data-stu-id="777e5-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="777e5-115">為了讓您受到保護，安全檔會將檔案傳送至[Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)雲端，以進行分析。</span><span class="sxs-lookup"><span data-stu-id="777e5-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="777e5-116">您可以在[這裡](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)找到 Microsoft Defender 高級執行緒保護如何處理資料的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="777e5-116">Details on how Microsoft Defender Advanced Thread Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="777e5-117">除了上述指導之外，由安全檔所傳送的檔案不會保留在進行分析所需的時間（通常是小於24小時）。</span><span class="sxs-lookup"><span data-stu-id="777e5-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="777e5-118">使用安全性 & 規範中心設定安全檔</span><span class="sxs-lookup"><span data-stu-id="777e5-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="777e5-119">開啟安全性 & 規範中心，網址為 <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="777e5-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="777e5-120">移至**威脅管理** \> **原則** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="777e5-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="777e5-121">在 [**信任檔案以在 Office 應用程式中開啟受保護的檢視**] 區段中，在 [協助人員保持安全]] 中，設定下列其中一個設定：</span><span class="sxs-lookup"><span data-stu-id="777e5-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="777e5-122">**開啟 Office 用戶端的安全檔（檔案也會傳送至 Microsoft 雲端進行深入分析）**</span><span class="sxs-lookup"><span data-stu-id="777e5-122">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="777e5-123">**即使安全檔將檔案識別為惡意，允許人員按一下受保護的檢視**：我們建議您不要啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="777e5-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="777e5-124">完成後，請按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="777e5-124">When you're finished, click **Save**.</span></span>

![ATP 安全附件頁面](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="777e5-126">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全檔</span><span class="sxs-lookup"><span data-stu-id="777e5-126">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="777e5-127">請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="777e5-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="777e5-128">_EnableSafeDocs_參數會啟用或停用整個組織的安全檔。</span><span class="sxs-lookup"><span data-stu-id="777e5-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="777e5-129">_AllowSafeDocsOpen_參數可允許或防止使用者在檔已識別為惡意時，留下受保護的檢視（也就是開啟檔）。</span><span class="sxs-lookup"><span data-stu-id="777e5-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="777e5-130">本範例會為整個組織啟用安全檔，並防止使用者開啟已從受保護的檢視識別為惡意的檔。</span><span class="sxs-lookup"><span data-stu-id="777e5-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="777e5-131">如需詳細的語法及參數資訊，請參閱[Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="777e5-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="777e5-132">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="777e5-132">How do I know this worked?</span></span>

<span data-ttu-id="777e5-133">若要確認您已啟用並設定安全檔，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="777e5-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="777e5-134">在安全性 & 合規性中心移至**威脅管理** \> **原則** \> **ATP 安全附件**，並確認**當信任檔案以在 Office 應用程式中開啟受保護的檢視時，協助**中的選項將保持安全。</span><span class="sxs-lookup"><span data-stu-id="777e5-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="777e5-135">在 Exchange Online PowerShell 中執行下列命令，並確認屬性值：</span><span class="sxs-lookup"><span data-stu-id="777e5-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
