---
title: 隔離
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
ms.assetid: e9eecdde-dcc2-4283-a820-98d1e740e4f
ms.collection:
- M365-security-compliance
description: 了解託管隔離區的 Exchange Online 和 Exchange Online Protection。
ms.openlocfilehash: a986a44c572c0cce52a11ea6a6d30ec27d06fedd
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032168"
---
# <a name="quarantine"></a>隔離

下列主題為 Exchange Online 與 Exchange Online Protection (EOP) 系統管理員和使用者提供託管隔離區的相關資訊：

- [隔離常見問題集](quarantine-faq.md) - 為系統管理員和使用者提供隔離區的一般問題與解答

- [以系統管理員身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-an-administrator.md) - 說明系統管理員如何在 Exchange 系統管理中心 (EAC) 尋找和釋出位於隔離區中的任何郵件，並選擇性地向 Microsoft 將該郵件報告為誤判的郵件 (非垃圾郵件)。

- [Find and Release Quarantined Messages (End Users)](https://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx) -將告訴您如何使用者可以尋找和釋出自己被當成垃圾郵件隔離的郵件在垃圾郵件隔離使用者介面中，並向 Microsoft 報告這些郵件不是垃圾郵件。

  > [!IMPORTANT]
  > 若要存取使用者垃圾郵件隔離區，使用者必須具有有效的 Office 365 使用者識別碼和密碼。 保護內部部署信箱的 EOP 客戶必須是透過目錄同步處理或 EAC 建立的有效電子郵件使用者。 如需管理使用者的詳細資訊，EOP 系統管理員可以參閱[管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)。 對於 EOP 獨立客戶，則建議使用目錄同步處理並啟用目錄架構邊緣封鎖；如需詳細資訊，請參閱[使用目錄架構邊緣封鎖以拒絕傳送至無效收件者的郵件](https://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。
