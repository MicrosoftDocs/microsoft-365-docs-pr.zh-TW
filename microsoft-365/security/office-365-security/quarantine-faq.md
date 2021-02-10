---
title: 隔離的郵件常見問題
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以在 Exchange Online Protection (EOP) 中查看有關隔離郵件的常見問題和解答。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 019f1c103ef1aaf7641072cd1259d22e83f0de4c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166924"
---
# <a name="quarantined-messages-faq"></a>隔離的郵件常見問題

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

本主題針對 Exchange Online 中的信箱或獨立 Exchange Online Protection (EOP) 組織中的 exchange 電子郵件，提供有關隔離365的電子郵件的常見問題和解答，但沒有 Exchange Online 信箱。

如需反垃圾郵件保護的相關問題和解答，請參閱 [反垃圾郵件保護常見問題](anti-spam-protection-faq.md)。

如需有關反惡意程式碼保護的問題和解答，請參閱 [反惡意程式碼保護常見問題](anti-malware-protection-faq-eop.md)。

如需反欺騙保護的相關問題和解答，請參閱 [反欺騙保護常見問題](anti-spoofing-protection-faq.md)。

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>如何管理被隔離以進行惡意程式碼的郵件？

只有系統管理員可以管理隔離惡意程式碼的郵件。 如需詳細資訊，請參閱 [以系統管理員身分管理被隔離的郵件和](manage-quarantined-messages-and-files.md)檔案。

## <a name="how-do-i-quarantine-spam"></a>如何隔離垃圾郵件？

依預設，歸類為垃圾郵件或大量電子郵件的郵件會傳遞至使用者的信箱，並移至 [垃圾郵件] 資料夾。 不過，您也可以建立並設定反垃圾郵件原則，以隔離垃圾郵件或大量電子郵件。 如需詳細資訊，請參閱[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>如何讓使用者能夠存取隔離區？

使用者必須具有有效的帳戶，才能存取隔離中自己的郵件。 獨立 EOP 要求使用者在 EOP (會以目錄同步處理) 手動建立或建立的方式呈現給郵件使用者。 如需在獨立 EOP 環境中管理使用者的詳細資訊，請參閱 [Manage mail users IN EOP](manage-mail-users-in-eop.md)。

## <a name="what-messages-can-end-users-access-in-quarantine"></a>使用者可以在隔離區中存取哪些郵件？

使用者可以存取垃圾郵件、大量電子郵件，以及從2020年4月的 () 網路釣魚郵件的收件者。 使用者無法存取隔離的惡意程式碼、高信賴網路釣魚或因將郵件傳遞至郵件流程規則中 **主控的隔離** 動作而隔離的郵件 (也稱為傳輸規則) 。 如需存取隔離郵件之使用者的詳細資訊，請參閱 [尋找和以使用者身分發行隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)。

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>郵件保存在隔離區中的時間多久？

您可以使用反垃圾郵件原則，設定隔離區中的垃圾郵件、網路釣魚和大量電子郵件的保留時間。 預設值為30天，也就是最大值。 如需詳細資訊，請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)

針對由郵件流程規則動作隔離的郵件，會將 **郵件傳遞至主控隔離區**，並將郵件保留30天。 您無法設定此持續時間。

時段到期後，郵件即會刪除，而且無法復原。

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>我是否可以一次放開或報告一封以上的隔離郵件？

在 [安全性 & 規範中心] 中，您可以一次選取及發行最多100封郵件。

系統管理員可以使用 Exchange Online PowerShell 或獨立 EOP PowerShell 中的 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) 和 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) Cmdlet，以大量尋找及發行隔離的郵件，並大量報告誤報。

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>搜尋隔離郵件時，是否支援萬用字元？ 是否可以搜尋特定網域的隔離郵件？

在安全性 & 規範中心內不支援萬用字元。 例如，在搜尋寄件者時，您必須指定完整的電子郵件地址。 不過，您可以在 Exchange Online PowerShell 或獨立 EOP PowerShell 中使用萬用字元。

例如，將下列 PowerShell 程式碼複製到 [記事本] 中，並將檔案儲存為. ps1 在輕鬆找到 (的位置，例如 C:\Data\QuarantineRelease.ps1) 。

當您連線至 [Exchange online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 或 [exchange online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)之後，請執行下列命令以執行腳本：

```powershell
& C:\Data\QuarantineRelease.ps1
```

腳本會執行下列動作：

- 尋找以垃圾郵件隔離的 unreleased 郵件（來自 fabrikam 網域中的所有寄件者）。 結果的最大數目為 50000 (50 頁面的1000結果) 。
- 將結果儲存至 CSV 檔案。
- 釋放對應的隔離郵件給所有原始收件者。

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

在您發佈郵件後，就無法再放開。
