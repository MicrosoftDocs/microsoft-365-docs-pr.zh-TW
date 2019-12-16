---
title: 隔離常見問題集
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 本主題提供有關託管隔離區的常見問題與解答。
ms.openlocfilehash: f8d7d0820685671c4cbe9ae7671058cc60d8e637
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971551"
---
# <a name="quarantine-faq"></a>隔離區常見問題集

本主題提供有關託管隔離區的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection 客戶。

 **問：如何管理隔離區中的惡意程式碼隔離郵件？**

您需要使用安全性與合規性中心，以便查看並使用傳送到隔離區的郵件，因為他們包含惡意程式碼。 如需詳細資訊，請參閱[在 Office 365 中隔離電子郵件訊息](quarantine-email-messages.md)。

 **問：如何設定服務以將因垃圾郵件而遭到隔離的郵件傳送至隔離區？**

答： 根據預設，經過內容篩選的郵件會傳送到收件者的 [垃圾郵件] 資料夾。 但系統管理員可以設定內容篩選原則，改成將垃圾郵件隔離郵件傳送至隔離區。 如需在經過內容篩選的郵件上可執行的各種動作的詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。

 **問：此服務是否可讓系統管理員和使用者管理被當成垃圾郵件隔離的郵件？**

答：如果您是系統管理員，您可以在 Exchange 系統管理中心 (EAC) 中搜尋及檢視關於所有隔離電子郵件的詳細資訊。找到郵件後，您可以將該郵件釋出給特定使用者，並可選擇向 Microsoft 垃圾郵件分析小組報告該郵件為誤判 (非垃圾郵件)。如需詳細資訊，請參閱 [以系統管理員身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-an-administrator.md)。

如果您是使用者，則可以透過下列項目管理自己被當成垃圾郵件隔離的郵件：

- 垃圾郵件隔離使用者介面。 如需詳細資訊，請參閱 [以 Office 365 使用者身分尋找並釋出被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)。

 **問：如何授權使用者存取垃圾郵件隔離區？**

答： 若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。 保護內部部署信箱的 EOP 客戶必須是透過目錄同步處理或 EAC 建立的有效電子郵件使用者。 如需管理使用者的詳細資訊，EOP 系統管理員可以參閱[在 EOP 中管理郵件使用者](manage-mail-users-in-eop.md)。 對於 EOP 獨立客戶，則建議使用目錄同步處理並啟用目錄架構邊緣封鎖；如需詳細資訊，請參閱[使用目錄架構邊緣封鎖以拒絕傳送至無效收件者的郵件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

 **問：不是垃圾郵件的項目是否會傳送到隔離區？**

答： 是的。 如果這是已設定的動作，則符合郵件流程 (也稱為傳輸規則) 的郵件以及被確認為網路釣魚的郵件也會被傳送到系統管理員隔離區。 使用者隔離區僅供隔離垃圾郵件。

 **問：郵件會保留在隔離區中多久？**

答： 根據預設，垃圾郵件隔離的郵件會保留在隔離區 30 天，而符合郵件流程規則的隔離郵件會根據您在預設內容篩選原則中設定的保留期，最多保留在隔離區 30 天。 超過這段時間後，郵件就會遭到刪除，而無法擷取。 符合郵件流程規則的隔離郵件無法設定保留期限。 不過，您可以透過內容篩選原則的 [保留垃圾郵件的天數]**** 設定，縮短垃圾郵件隔離郵件的保留期限。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。

 **問：我可以一次釋出或報告多個隔離的郵件嗎？**

答： 是，在隔離區入口網站中最多可同時釋出 100 封郵件。 此外，系統管理員還可以建立遠端 Windows PowerShell 指令碼來完成這項工作。 使用 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) 指令程式來搜尋郵件，使用 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) 指令程式來釋出郵件。

 **問：搜尋隔離的郵件時是否支援萬用字元？我可以搜尋特定網域的隔離郵件嗎？**

答：在 Exchange 系統管理中心指定搜尋準則時不支援萬用字元。例如，在搜尋寄件者時，您必須指定完整的電子郵件地址。

系統管理員可以使用遠端 Windows PowerShell，指定 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) 指令程式在特定網域 (例如 contoso.com) 中搜尋隔離的郵件：

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

結果可以傳遞至 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) 指令程式。請加上 -ReleaseToAll 參數，以將郵件釋出給所有收件者。郵件一經釋出，就無法再釋出一次。

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```
