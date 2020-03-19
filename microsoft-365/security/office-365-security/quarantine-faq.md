---
title: 隔離常見問題集
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 有關 Office 365 中的隔離常見問題的答案。
ms.openlocfilehash: 58800d5645241c2115356bc9899ce53302d1e37e
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856902"
---
# <a name="quarantine-faq-in-office-365"></a>Office 365 中的隔離常見問題

本主題提供 Exchange Online 或獨立 Exchange Online Protection （EOP）客戶沒有 Exchange Online 信箱之信箱的365隔離問題和解答。

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Q：如何管理被隔離以進行惡意程式碼的郵件？

只有系統管理員可以管理隔離惡意程式碼的郵件。 如需詳細資訊，請參閱[在 Office 365 中以系統管理員身分管理隔離的郵件和](manage-quarantined-messages-and-files.md)檔案。

## <a name="q-how-do-i-quarantine-spam"></a>問：如何隔離垃圾郵件？

答： 依預設，歸類為垃圾郵件或大量電子郵件的郵件會傳遞至使用者的信箱，並移至 [垃圾郵件] 資料夾。 不過，您也可以建立並設定反垃圾郵件原則，以隔離垃圾郵件或大量電子郵件。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a>問：如何讓使用者能夠存取隔離區？

答： 使用者必須具有有效的帳戶，才能存取隔離中自己的郵件。 獨立 EOP 要求使用者在 EOP 中以郵件使用者的身分呈現（透過目錄同步處理手動建立或建立）。 如需在獨立 EOP 環境中管理使用者的詳細資訊，請參閱[Manage mail users IN EOP](manage-mail-users-in-eop.md)。

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a>問：哪些郵件可以讓使用者在隔離區中存取？

答： 使用者可以存取垃圾郵件、大量電子郵件，以及（從2020年4月的）網路釣魚郵件，其為收件者。 由於將**郵件傳遞至**郵件流程規則（也稱為傳輸規則）中的主控隔離動作，因此使用者無法存取隔離的惡意程式碼、高信賴網路釣魚或已隔離的郵件。 如需存取隔離郵件之使用者的詳細資訊，請參閱[在 Office 365 中尋找及發行隔離郵件為使用者](find-and-release-quarantined-messages-as-a-user.md)。

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a>問：郵件保存在隔離區中的時間多久？

答： 您可以使用反垃圾郵件原則，設定隔離區中的垃圾郵件、網路釣魚和大量電子郵件的保留時間。 預設值為30天，也就是最大值。 如需詳細資訊，請參閱[在 Office 365 設定反垃圾郵件原則](configure-your-spam-filter-policies.md)

針對由郵件流程規則動作隔離的郵件，會將**郵件傳遞至主控隔離區**，並將郵件保留30天。 您無法設定此持續時間。

時段到期後，郵件即會刪除，而且無法復原。

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>問：一次可以放開或報告一封以上的隔離郵件？

答： 在 [安全性 & 規範中心] 中，您可以一次選取及發行最多100封郵件。

系統管理員可以使用 Exchange Online 中的[Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)和[Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) Cmdlet PowerShell 或獨立 Exchange online Protection PowerShell 以大量尋找及發行隔離的郵件，以及大量報告誤報。

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Q：搜尋隔離郵件時是否支援萬用字元？ 是否可以搜尋特定網域的隔離郵件？

答： 在安全性 & 規範中心內不支援萬用字元。 例如，在搜尋寄件者時，您必須指定完整的電子郵件地址。 不過，您可以在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中使用萬用字元。

例如，執行下列命令，尋找來自網域 contoso.com 中所有寄件者的垃圾郵件隔離郵件：

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

然後，執行下列命令，以將這些郵件釋放給所有原始收件者：

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $CQ.Identity -ReleaseToAll}
```

在您發佈郵件後，就無法再放開。
