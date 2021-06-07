---
title: 在 web 上的 Outlook 中報告垃圾郵件和網路釣魚電子郵件
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 系統管理員可以深入瞭解 Outlook 網頁 (Outlook Web App Exchange Online) 的內建垃圾郵件、非垃圾郵件和網路釣魚電子郵件報告選項，以及如何為使用者停用這些報告選項。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788304"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>在 Exchange Online 中的網頁 Outlook 中報告垃圾郵件和網路釣魚電子郵件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在使用[混合式新式驗證](../../enterprise/hybrid-modern-auth-overview.md)的 Exchange Online 或內部部署信箱中使用信箱的 Microsoft 365 組織，您可以提交誤報) 的 (誤報電子郵件、false 不利 (允許不良電子郵件) ，以及網路釣魚郵件 Exchange Online Protection (EOP) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

> [!IMPORTANT]
> 建議使用者提交的報告訊息增益集或報告網路釣魚增益集。 如需詳細資訊，請參閱[Enable The Report Message Or report](./enable-the-report-message-add-in.md)information the 增益集。由於無法使用[使用者提交原則](./user-submission.md)，因此建議您不要在 Outlook 內建報告經驗。

- 如果您是組織中 Exchange Online 信箱的系統管理員，建議您在安全性 & 規範中心使用提交入口網站。 如需詳細資訊，請參閱 [使用系統管理員提交將可疑的垃圾郵件、網路釣魚、URLs 和檔案提交給 Microsoft](admin-submission.md)。

- 系統管理員可以停用或啟用使用者將郵件報告給 Microsoft 的 Outlook 網頁上的功能。 如需詳細資訊，請參閱本文稍後的在 Outlook 的 web 區段中[停用或啟用垃圾郵件報告](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)。

- 您可以設定報告的郵件以複製或重新導向至您指定的信箱。 如需詳細資訊，請參閱 [使用者報送原則](user-submission.md)。

- 如需將郵件報告給 Microsoft 的詳細資訊，請參閱 [將郵件和檔案報告給 microsoft](report-junk-email-messages-to-microsoft.md)。

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>在 web 上的 Outlook 停用或啟用垃圾郵件報告

根據預設，使用者可以將垃圾郵件誤報、漏報和網路釣魚郵件報告給 Microsoft，以在 web 上的 Outlook 進行分析。 系統管理員可以在 Exchange Online PowerShell 中的網頁信箱原則上設定 Outlook，以防止使用者向 Microsoft 報告垃圾郵件誤報和垃圾郵件的漏報。 您無法停用使用者將網路釣魚郵件報告給 Microsoft 的功能。

### <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 您必須在 Exchange Online 中指派許可權，才能執行本文中的程式。 具體而言，您需要 **收件者原則** 或 **郵件** 收件者角色，預設會指派給 **組織管理** 和 **收件者管理** 角色群組。 如需 Exchange Online 中角色群組的詳細資訊，請參閱 Exchange Online 中 Exchange Online 及[修改角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups)中[的許可權](/exchange/permissions-exo/permissions-exo)。

- 每個組織都有一個名為 OwaMailboxPolicy-Default 的預設原則，但您可以建立自訂原則。 在預設原則之前，自訂原則會套用至範圍的使用者。 如需有關網頁信箱原則 Outlook 的詳細資訊，請參閱[Exchange Online 中的 Outlook 網頁信箱原則](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。

- 停用垃圾郵件報告時，並不會移除將郵件標示為垃圾郵件的功能，也不會移除網頁 Outlook 中的垃圾郵件。 選取 [垃圾郵件] 資料夾中的郵件，然後按一下 [不是垃圾郵件] 中的 [**不** 是垃圾郵件] 會 \> 將郵件傳回收件匣 在任何其他電子郵件資料夾中選取郵件，然後按一下 [**垃圾** \> 郵件]，仍然會將郵件移至 [垃圾郵件] 資料夾。 您無法再使用的是將郵件報告給 Microsoft 的選項。

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>使用 Exchange Online PowerShell 在網頁 Outlook 上停用或啟用垃圾郵件報告

1. 若要在 web 信箱原則上尋找現有的 Outlook，以及垃圾郵件報告的狀態，請執行下列命令：

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. 若要停用或啟用網頁 Outlook 中的垃圾郵件報告，請使用下列語法：

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

如需詳細的語法及參數資訊，請參閱 [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) 和 [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您是否已成功啟用或停用網頁 Outlook 中的垃圾郵件報告，請使用下列任一步驟：

- 在 Exchange Online PowerShell 中，執行下列命令，並確認 **ReportJunkEmailEnabled** 屬性值：

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- 在網頁的 Outlook 中開啟受影響使用者的信箱，在 [收件匣] 中選取郵件，然後按一下 [**垃圾** 郵件]， \> 然後確認提示您將郵件報告給 Microsoft （或不會顯示）。<sup>\*</sup>

- 在 web 上的 Outlook 中開啟受影響使用者的信箱，選取 [垃圾郵件] 資料夾中的郵件，按一下 [**垃圾** 郵件]， \> 然後確認提示您將郵件報告給 Microsoft （或不會顯示）。<sup>\*</sup>

<sup>\*</sup> 使用者可以在仍報告郵件時隱藏提示來報告郵件。 若要在 web 上的 Outlook 中檢查此設定：

1. 按一下 ![ [網站設定] 圖示上的 [設定 Outlook]， ](../../media/owa-settings-icon.png) \> **查看 [所有 Outlook 設定** \> **垃圾郵件**]。
2. 在 [ **報告** ] 區段中，確認值： [傳送 **報告前請先詢問我**]。

   ![Outlook 網頁垃圾郵件報告設定](../../media/owa-junk-email-reporting-options.png)
