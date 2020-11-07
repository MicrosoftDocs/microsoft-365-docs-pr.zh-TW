---
title: Office 365 中預設的安全性
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: '深入瞭解 Exchange Online Protection (EOP 中的安全性預設設定) '
ms.openlocfilehash: 50d1c64e4d8343fdb9b25bfcbeee5d988ddc6b8a
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945327"
---
# <a name="secure-by-default-in-office-365"></a>Office 365 中預設的安全性

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

「預設使用安全」是一種術語，用來定義盡可能最安全的預設設定。

不過，安全性需要與生產力進行平衡。 這可能包括平衡：

- 可用性：設定不應該以使用者生產力的方式取得。
- 風險：安全性可能會封鎖重要的活動。
- 舊的設定：有些舊版產品及功能的設定可能出於商務原因而必須維護，即使新的新式設定也有所改善。

在 Exchange Online 中使用信箱的 Microsoft 365 組織會受到 Exchange Online Protection (EOP) 的保護。 這種保護包括：

1. 具有可疑惡意軟體的電子郵件將會自動遭到隔離，並會通知收件者。 請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。
1. 識別為「高信賴」的網路釣魚電子郵件會依照反垃圾郵件原則動作進行處理。 請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

因為 Microsoft 想要讓我們的客戶在預設情況下是安全的，所以部分承租人覆寫不會針對惡意程式碼或高可信度網路釣魚應用程式。 這些覆寫包括：

-  (反垃圾郵件原則所允許的寄件者清單或允許的網域清單) 
- Outlook 安全寄件者
- IP 允許清單 (連線篩選) 

您可以在 [ [建立安全的寄件者清單](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365)] 中找到這些優先選項的詳細資訊。

在下列情況下安全保護此設定不是一種可能開啟或關閉的設定，但是我們的篩選功能會從盒出的方式，讓您的信箱無法使用可能有害或有害的郵件。 惡意程式碼和高可信度網路釣魚網路應傳送至隔離區。 只有系統管理員可以管理被隔離為惡意程式碼或高可信度網路釣魚的郵件，也可以從那裡向 Microsoft 報告誤報。 如需詳細資訊，請參閱 [在 EOP 中管理被隔離的郵件和檔案為系統管理員](manage-quarantined-messages-and-files.md)

## <a name="exceptions"></a>例外狀況

只會略過所有篩選的覆寫包括：

- Exchange Transport Rules (ETR) /mail 流程規則。 使用郵件流程規則來設定 EOP 中郵件中的垃圾郵件信賴等級 (SCL) 。
- 承租人 Allow/封鎖清單：管理承租人 Allow/封鎖清單中的 URLs 和檔案。

下列的覆寫類型適用于：

- 網路釣魚模擬：模擬的攻擊可協助您識別遭到攻擊的使用者，在實際攻擊影響組織之前。
- 安全性/SecOps 信箱：安全小組用來取得未篩選郵件 (良好且錯誤) 的專用信箱。 然後，小組可以查看是否包含惡意內容。
- 協力廠商篩選器：部分協力廠商廠商會建議您關閉 EOP (SCL =-1) ，因為協力廠商篩選器會管理郵件篩選。 Microsoft 不建議關閉 EOP （適用于 Office 365 的 Defender 所需）。
- 誤報：您可能想要允許由 Microsoft 透過系統 [管理員報送](admin-submission.md)進行的某些郵件仍在進行分析。 就像所有覆寫一樣，建議它們是臨時性的。
