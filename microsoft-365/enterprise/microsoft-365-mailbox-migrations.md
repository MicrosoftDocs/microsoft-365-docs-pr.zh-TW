---
title: Microsoft 365 信箱遷移
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 本文包含有關 Microsoft 365 信箱遷移的簡短摘要，以及用於遷移的 Cmdlet 清單。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 86681cbca6f0899268ce11e233e8781619cb18e3
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332313"
---
# <a name="microsoft-365-mailbox-migrations"></a>Microsoft 365 信箱遷移

透過以 Exchange 為基礎的混合式部署，客戶可以選擇將內部部署 Exchange 信箱移至 [Exchange online](https://docs.microsoft.com/Exchange/exchange-online) 組織，或將 exchange Online 信箱移至 [exchange 內部部署](https://docs.microsoft.com/Exchange/exchange-server) 組織。 在內部部署和 Exchange Online 組織之間移動信箱時，會使用遷移批次。

客戶可以使用下列 Cmdlet 來查看信箱遷移的統計資料和其他資訊：

- [Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps)：提供使用者信箱的預設統計資料，其中包括狀態、信箱大小、封存信箱大小，以及完成百分比。
- [Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
)：提供組織中信箱物件及屬性的摘要清單。
- [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps)：提供現有擁有郵件功能的物件清單，例如信箱、郵件使用者、連絡人及通訊群組。
- [Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps)：提供進行中信箱遷移的詳細狀態。
- [Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps)：提供信箱移動和遷移使用者的相關資訊。
- [Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps)：提供目前遷移批次狀態的相關資訊。
- [Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps)：提供特定使用者之遷移狀態的詳細資訊。
- [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps)：提供信箱的相關資訊，例如大小、郵件數目及最後存取時間。

如需 Cmdlet 的詳細資訊，請參閱 [Exchange Online 中的移動和遷移 Cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)。
