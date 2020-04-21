---
title: 何謂 EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: 這份簡介檔將協助您瞭解 Exchange Online Protection （EOP）及一些重要的術語。 這適用于保護 Exchange Online 雲端託管信箱的客戶，以及保護內部部署信箱（例如 Exchange Server 2016）的 EOP 單機客戶。
ms.openlocfilehash: dc08507a80db8e15d2e08ff5b954dec1905cfada
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630914"
---
# <a name="what-is-exchange-online-protection-eop"></a>何謂 Exchange Online Protection （EOP）

Exchange Online Protection （EOP）是雲端式的電子郵件篩選服務，可協助您的組織抵禦垃圾郵件和惡意程式碼。 如果您在 Microsoft 365 中有信箱，這些信箱會自動受到 EOP 保護，因為它是服務的一部分。 這包括在 Microsoft 365 和內部部署中具有信箱的組織，這通常稱為混合式案例。 EOP 獨立版也可用於沒有雲端信箱的客戶，但想要保護其內部部署信箱。

EOP 會嘗試篩選出垃圾郵件，使您的收件匣不清楚使用者不想要看到的內容。 通常，垃圾郵件會傳遞至 [垃圾郵件] 資料夾。 有些使用者想要檢查，確定篩選執行的是其所需要的功能，因此 [垃圾郵件] 資料夾是一種簡單的方法供使用者自行檢查。  

> [!TIP]
> 當垃圾郵件自動進入 [垃圾郵件] 資料夾時，這是一項很好的做法。 服務會根據預設或自訂的系統管理員設定狀態，進行必要的工作。 換句話說，使用者不應該擔心會在 [垃圾郵件] 資料夾中看到大量的垃圾郵件。 如果系統管理員喜歡移動所有垃圾郵件，則應該設定隔離。 如需詳細資訊，請參閱[隔離電子郵件訊息](quarantine-email-messages.md)文章。

## <a name="important-terms"></a>重要字詞

**輸入**：即將加入 Microsoft 365 的郵件。

**輸出**：即將離開 Microsoft 365 的郵件。

**Internal**：來自組織內部某人的郵件，到組織內部的某人。 這包括混合式案例中的客戶，以及一個信箱可以在內部部署，另一個信箱則位於雲端中。

**False 負數（FN）**：垃圾郵件和其他不正確傳送至收件匣的垃圾郵件。

**誤報（FP）**：合法郵件會錯誤地標示為垃圾郵件，並放入垃圾郵件資料夾或隔離區。

**垃圾郵件，也稱為未經許可的電子郵件**：這種形式的商業廣告、連鎖信、政治郵件等等。這是使用者未針對嘗試徵求產品或嘗試認可欺詐的垃圾郵件人員進行註冊的電子郵件。

**網路釣魚**：網路釣魚是一種特殊類型的垃圾郵件，其目的是為了哄騙您為認可身分識別或欺詐的目的提供個人資訊。 這類郵件通常包含惡意連結或附件，但不一定是。

**哄騙**：哄騙是指寄件者從標頭中偽造時，郵件似乎來自于實際來源以外的某人或其他地方。 這可以是垃圾郵件，但最常見的是用於網路釣魚使用者。

模擬 **：這**種類型的垃圾郵件也是偽造寄件者位址的方式，但是它是透過修改名稱或網域的一部分，使它看起來像是實際來源。 例如，Bi11@micr0s0ft.com，在帳單中，"l" 實際上是數位十一，而 Microsoft 中的 "o" 是由數位零所取代。

**大量**：大宗郵件通常是由使用者要求，但有時會在公司向其他公司銷售資訊時間接使用。 使用者通常會自行註冊大宗郵件（亦即 newletters），但稍後又忘了，並認為是垃圾郵件。 大宗郵件傳送超過使用者的註冊和投訴層級時，大宗郵件會變成垃圾郵件。
