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
description: 深入瞭解 Microsoft 365 E5 或 Microsoft 365 E5 安全性中的安全檔。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1186c7856d0b979c483cf6dd1c0a010ab582e2ce
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644749"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 中的安全文件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

安全檔是 Microsoft 365 E5 或 Microsoft 365 E5 安全性中的一項功能，可使用[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)掃描在[受保護的檢視](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中開啟的檔和檔案，或在 Office 中開啟[應用程式防護](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 只有具有 *Microsoft 365 E5* 或 *Microsoft 365 E5 安全性* 授權的使用者才能使用安全檔。 這些授權不會包含在 Microsoft Defender 中 Office 365 計畫。

- Microsoft 365 Apps 企業版以前稱為 Office 365 專業增強版) 版本2004或更新版本 (支援安全檔。

- 您要在 <https://protection.office.com> 開啟安全性與合規性中心。 若要直接移至 [ **ATP 安全附件** ] 頁面，請開啟] <https://protection.office.com/safeattachmentv2> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 您必須已在 **Exchange Online** 中獲派權限，才能執行此文章中的程序：
  - 若要設定安全檔設定，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要對安全檔設定進行唯讀存取，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  >
  > - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft 如何處理您的資料？

為了讓您受到保護，安全檔會將檔案傳送至 [Microsoft Defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud 進行分析。 您可以在以下位置找到 Microsoft Defender for Endpoint handles 資料的詳細資料： [Microsoft defender For endpoint data storage and 隱私權](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。

安全檔所傳送的檔案不會保留在分析所需的時間，而不會保留在進行分析 (，但通常不會超過24小時) 。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>使用安全性 & 規範中心設定安全檔

1. 在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全附件**]，然後按一下 [ **通用設定**]。

2. 在顯示的 [ **全域設定** ] 中，設定下列設定：

   - **開啟 Office 用戶端的安全檔**：將切換移至右邊開啟功能： ![ 開啟 ](../../media/scc-toggle-on.png) 。

   - **即使安全檔會將檔案識別為惡意，允許人員按一下 [受保護的檢視**]：建議您保留此選項關閉， (保持向左切換：請 ![ 關閉 ](../../media/scc-toggle-off.png)) 。

   完成後，按一下 [儲存]。

   ![在 [安全附件] 頁面上選取全域設定後的 [安全檔] 設定。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>使用 Exchange Online PowerShell 設定安全檔

使用下列語法：

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_ 參數會啟用或停用整個組織的安全檔。
- _AllowSafeDocsOpen_ 參數可允許或禁止使用者保留受保護的檢視 (也就是說，開啟檔) 如果檔已識別為惡意。

本範例會為整個組織啟用安全檔，並防止使用者開啟已從受保護的檢視識別為惡意的檔。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>已在 Microsoft Defender for Endpoint Service 上板載以啟用審核功能

若要部署 Microsoft Defender for Endpoint，您需要經歷各個部署階段。 在上架之後，您可以在安全性 & 規範中心設定審核功能。

若要深入瞭解，請參閱 [在 Microsoft Defender For Endpoint service 上的板載](/microsoft-365/security/defender-endpoint/onboarding)。 如果您需要其他協助，請參閱 [疑難排解 Microsoft Defender 的端點上架問題](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)。

### <a name="how-do-i-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已啟用並設定安全檔，請執行下列任一步驟：

- 在 [安全性 & 合規性中心] 中，移至 [**威脅管理** \> **原則** \> **ATP 安全附件**]，按一下 [**通用設定**]，然後確認 **開啟 Office 用戶端的安全檔**，以及是否 **允許使用者在受保護的檢視上按一下，即使安全檔識別為惡意設定也是如此**。

- 在 Exchange Online PowerShell 中執行下列命令，並確認屬性值：

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 下列檔案可用於測試安全檔案保護。 這些檔與測試反惡意程式碼和反病毒解決方案的 EICAR.TXT 檔案類似。 檔案不會有害，但會觸發安全的檔案保護。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
