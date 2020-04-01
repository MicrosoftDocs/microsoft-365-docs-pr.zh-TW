---
title: '在 Outlook 網頁版中回報垃圾郵件與網路釣魚詐騙 '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Office 365 具有 Exchange Online 信箱的使用者可以使用網頁型 Outlook （Outlook Web App），將垃圾郵件、非垃圾郵件和網路釣魚郵件提交給 Microsoft 進行分析。
ms.openlocfilehash: b58e3ae5be9bf2a473b655287ad9bb1cb8ef2c78
ms.sourcegitcommit: 4d4d27a49eb258dc560439ca4baf61ebb9c1eff3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2020
ms.locfileid: "43075617"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a>在 Office 365 的 Outlook 網頁版中報告垃圾郵件和網路釣魚電子郵件

如果您是 Office 365 客戶的 Exchange Online 信箱，您可以使用網頁型 Outlook （先前稱為 Outlook Web App）的內建報告選項，送出誤報（良好的電子郵件，允許錯誤的電子郵件），以及網路釣魚郵件至 Exchange Online Protection （EOP）。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 如果您是 Office 365 組織中 Exchange Online 信箱的系統管理員，建議您在 Office 365 安全性 & 規範中心使用提交入口網站。 如需詳細資訊，請參閱[使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。

- 系統管理員可以停用或啟用使用者在 Outlook 網頁版中將郵件報告給 Microsoft 的功能。 如需詳細資訊，請參閱本主題稍後的在[Outlook 網頁版中停用或啟用垃圾郵件報告](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)一節。

- 如需向 Microsoft 報告訊息的詳細資訊，請參閱[在 Office 365 中報告訊息和檔案至 microsoft](report-junk-email-messages-to-microsoft.md)。

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>在 Outlook 網頁版中報告垃圾郵件和網路釣魚郵件

1. 對於收件匣或任何其他電子郵件資料夾（除了垃圾郵件）以外的郵件，請使用下列其中一種方法來報告垃圾郵件和網路釣魚郵件：

   - 選取郵件，按一下工具列上的 [**垃圾**郵件]，然後選取 [**垃圾**郵件] 或 [**網路釣魚**]。

     ![從功能區報告垃圾郵件或網路釣魚電子郵件](../../media/owa-report-junk.png)

   - 選取一或多封郵件、按一下滑鼠右鍵，然後選取 [**標記為垃圾**郵件]。

2. 在出現的對話方塊中，按一下 [**報表**]。 如果您變更主意，請按一下 [**不報告**]。

   ![報告為垃圾郵件對話方塊](../../media/owa-report-as-junk-dialog.png)

   ![報告為網路釣魚對話方塊](../../media/owa-report-as-phishing-dialog.png)

3. 選取的郵件會傳送給 Microsoft 進行分析。 若要確認郵件已提交，請開啟 **[寄件備份]** 資料夾，以檢視已提交的郵件。

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>從網頁型 Outlook 中的 [垃圾郵件] 資料夾報告非垃圾郵件和網路釣魚郵件

1. 在 [垃圾郵件] 資料夾中，使用下列其中一種方法來報告垃圾郵件誤報或網路釣魚郵件：

   - 選取郵件，按一下工具列上的 [**非垃圾**郵件]，然後選取 [**不是垃圾**郵件或**網路釣魚**]。

     ![從功能區報告垃圾郵件或網路釣魚電子郵件](../../media/owa-report-not-junk.png)

   - 選取一或多封郵件、按一下滑鼠右鍵，然後選取 [**標記為非垃圾**郵件]。

2. 在出現的對話方塊中，閱讀資訊，然後按一下 [**報告**]。 如果您變更主意，請按一下 [**不報告**]。

   ![[報告為非垃圾郵件] 對話方塊](../../media/owa-report-as-not-junk-dialog.png)

   ![報告為網路釣魚對話方塊](../../media/owa-report-as-phishing-dialog.png)

3. 選取的郵件會傳送給 Microsoft 進行分析。 若要確認郵件已提交，請開啟 **[寄件備份]** 資料夾，以檢視已提交的郵件。

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>在 web 上的 Outlook 中停用或啟用垃圾郵件報告

根據預設，使用者可以在網頁上的 Outlook 中，將垃圾郵件誤報、錯誤否定和網路釣魚郵件報告給 Microsoft 進行分析。 系統管理員可以在 Exchange Online PowerShell 中設定 web 信箱原則上的 Outlook，以防止使用者向 Microsoft 報告垃圾郵件誤報和垃圾郵件漏報。 您無法停用使用者將網路釣魚郵件報告給 Microsoft 的功能。

### <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

- 您必須已獲指派權限，才能執行這些程序。 具體說來，您需要 Exchange Online 中的**收件者原則**或**郵件**收件者角色（預設會指派給**組織管理**和**收件者管理**角色群組）。 如需有關 Exchange Online 中角色群組的詳細資訊，請參閱[Modify role groups In Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。

- 每個組織都有一個名為 OwaMailboxPolicy-Default 的預設原則，但您可以建立自訂原則。 在預設原則之前，自訂原則會套用至範圍的使用者。 如需有關 Outlook 網頁信箱原則的詳細資訊，請參閱[outlook On Exchange Online 中的 web 信箱原則](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。

- 停用垃圾郵件報告時，並不會移除將郵件標示為垃圾郵件的功能，也不會移除 Outlook 網頁版中的垃圾郵件。 選取 [垃圾郵件] 資料夾中的郵件，然後按一下 [**不** \>是垃圾郵件] 中的 [不是垃圾郵件 **] 會將**郵件傳回收件匣 在任何其他電子郵件資料夾中選取郵件，然後按一下 [**垃圾** \> **郵件]，仍然會**將郵件移至 [垃圾郵件] 資料夾。 您無法再使用的是將郵件報告給 Microsoft 的選項。

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>使用 Exchange Online PowerShell 在 web 上的 Outlook 中停用或啟用垃圾郵件報告

1. 若要尋找您的現有 Outlook 信箱原則及垃圾郵件報告狀態，請執行下列命令：

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. 若要在 Outlook 網頁版中停用或啟用垃圾郵件報告，請使用下列語法：

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   本範例會停用預設原則中的垃圾郵件報告。

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   此範例會在名為 Contoso 管理員的自訂原則中，啟用垃圾郵件報告。

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

如需詳細的語法及參數資訊，請參閱[Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)和[Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您是否已成功啟用或停用 Outlook 網頁版中的垃圾郵件報告，請使用下列任何一項步驟：

- 在 Exchange Online PowerShell 中，執行下列命令，並確認**ReportJunkEmailEnabled**屬性值：

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- 在網頁上的 Outlook 中開啟受影響使用者的信箱，在 [收件匣] 中選取一封郵件，按一下 [**垃圾** \> **郵件]，然後確認**提示您將郵件報告給 Microsoft （或不會顯示）。<sup>\*</sup>

- 在 web 上的 Outlook 中開啟受影響使用者的信箱，選取 [垃圾郵件] 資料夾中的郵件，按一下 [**垃圾** \> **郵件]，然後確認**提示您將郵件報告給 Microsoft （或不會顯示）。<sup>\*</sup>

<sup>\*</sup>使用者可以在仍報告郵件時隱藏提示來報告郵件。 若要在 Outlook 網頁版中檢查此設定：

1. 按一下 **[設定** ![網頁上的 outlook]](../../media/owa-settings-icon.png) \>圖示，以**查看所有 outlook 設定** \> **垃圾郵件**。
2. 在 [**報告**] 區段中，確認值： [傳送**報告前請先詢問我**]。

   ![網頁版 Outlook 垃圾郵件報告設定](../../media/owa-junk-email-reporting-options.png)
