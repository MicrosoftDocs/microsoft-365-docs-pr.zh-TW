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
ms.openlocfilehash: 1049543b11ad14eeeed596367228f025cc8edd65
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054429"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 中的安全文件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

保管庫檔是 Microsoft 365 E5 或 Microsoft 365 E5 安全性中的功能，可使用[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)掃描在[受保護的檢視](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中開啟的檔和檔案，或在 Office 中開啟[應用程式防護](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 保管庫只有具有 *Microsoft 365 E5* 或 *Microsoft 365 E5 安全性* 授權的使用者才能使用檔。 這些授權不會包含在 Microsoft Defender 中 Office 365 計畫。

- 保管庫在以前稱為 Office 365 專業增強版) 版本2004或更新版本的 Microsoft 365 Apps 企業版 (中支援檔。

- 您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。 若要直接移至 [**保管庫附件**] 頁面，請使用 <https://security.microsoft.com/safeattachmentv2> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 您需要 **Exchange Online** 中的許可權，才能執行本文中的程式：
  - 若要設定保管庫檔設定，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。
  - 若要唯讀的保管庫檔設定的存取權，您必須是 **全域讀取器** 或 **安全性讀者** 角色群組的成員。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  >
  > - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft 如何處理您的資料？

為了讓您受到保護，保管庫檔會將檔案傳送至[Microsoft Defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud 進行分析。 您可以在以下位置找到 Microsoft Defender for Endpoint handles 資料的詳細資料： [Microsoft defender For endpoint data storage and 隱私權](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。

保管庫檔所傳送的檔案不會保留在分析所需的時間內，而不會保留在進行分析所需的時間 (通常是小於24小時) 

## <a name="use-the-microsoft-365-defender-to-configure-safe-documents"></a>使用 Microsoft 365 Defender 設定保管庫檔

1. 開啟 Microsoft 365 Defender 入口網站，然後移至 **Email & 協同** 原則 \> **& 規則** \> **威脅原則** 原則] \> 區段 \> **保管庫附件**。

2. 在 [**保管庫附件**] 頁面上，按一下 [**通用設定**]。

3. 在顯示的 [ **全域設定** ] 中，設定下列設定：
   - **開啟 Office 用戶端的保管庫檔**：將切換移至右邊開啟功能： ![ 開啟 ](../../media/scc-toggle-on.png) 。
   - **即使保管庫檔識別為惡意的檔案，也可讓使用者依序按一下 [受保護的檢視**]：我們建議您保留此選項關閉 (保持向左切換： ![ 關閉 ](../../media/scc-toggle-off.png)) 。

   完成後，點擊 **[儲存]**。

   ![保管庫在 [保管庫附件] 頁面上選取全域設定之後的檔設定。](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>使用 Exchange Online PowerShell 設定保管庫檔

使用下列語法：

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_ 參數會啟用或停用整個組織的保管庫檔。
- _AllowSafeDocsOpen_ 參數可允許或禁止使用者保留受保護的檢視 (也就是說，開啟檔) 如果檔已識別為惡意。

本範例會為整個組織啟用保管庫檔，並防止使用者開啟已從受保護的檢視識別為惡意的檔。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>已在 Microsoft Defender for Endpoint Service 上板載以啟用審核功能

若要部署 Microsoft Defender for Endpoint，您需要經歷各個部署階段。 在上架之後，您可以在 Microsoft 365 Defender 入口網站中設定審核功能。

若要深入瞭解，請參閱 [在 Microsoft Defender For Endpoint service 上的板載](/microsoft-365/security/defender-endpoint/onboarding)。 如果您需要其他協助，請參閱 [疑難排解 Microsoft Defender 的端點上架問題](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)。

### <a name="how-do-i-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已啟用並設定保管庫檔，請執行下列任一步驟：

- 在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則] & 規則** 的「 \> **威脅原則** 原則」 \> 區段 \> **保管庫附件** \> **全域設定**，並驗證是否 **開啟保管庫用戶端的 Office 檔**，以及是否 **允許使用者在保管庫的檔識別為惡意設定時，按一下透過受保護的檢視**。

- 在 Exchange Online PowerShell 中執行下列命令，並確認屬性值：

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 下列檔案可用於測試保管庫檔案保護。 這些檔與測試反惡意程式碼和反病毒解決方案的 EICAR.TXT 檔案類似。 檔案不會有害，但會觸發保管庫檔案保護功能。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
