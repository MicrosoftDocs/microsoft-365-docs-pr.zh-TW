---
title: EOP 中的郵件流程
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
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: 若為 Exchange Online Protection (EOP) 客戶，傳送到貴組織的所有郵件會先通過 EOP，您的背景工作才會看見這些郵件。不論透過 Exchange Online 在雲端託管所有的信箱，或將信箱託管於內部部署環境 (稱為獨立案例)，或者繼續利用現有的基礎結構，您都可以在即將通過 EOP 進行處理的郵件路由傳送到您的背景工作收件匣之前，先選擇如何路由傳送這些郵件。
ms.openlocfilehash: 6ade456cb4c61203a810784eaa94d6091b05d47b
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893655"
---
# <a name="mail-flow-in-eop"></a>EOP 中的郵件流程

若為 Exchange Online Protection (EOP) 客戶，傳送到貴組織的所有郵件會先通過 EOP，您的背景工作才會看見這些郵件。不論透過 Exchange Online 在雲端託管所有的信箱，或將信箱託管於內部部署環境 (稱為獨立案例)，或者繼續利用現有的基礎結構，您都可以在即將通過 EOP 進行處理的郵件路由傳送到您的背景工作收件匣之前，先選擇如何路由傳送這些郵件。

您可以設定自訂郵件路由，使您的郵件傳遞方式符合業務需求。例如，您可以透過原則篩選裝置傳遞所有的輸出郵件。

## <a name="working-with-messages-and-message-access-options"></a>使用郵件和郵件存取選項

EOP 對您的郵件路由傳送方式提供了很大的彈性。 下列主題說明郵件流程處理序中的步驟。

[使用目錄架構邊緣封鎖以拒絕傳送至無效收件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)者的郵件描述目錄型 Edge 封鎖功能，可讓您拒絕服務網路周邊上無效收件者的郵件。

[在 EOP 中查看或編輯受管理的網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)說明如何管理與 EOP 服務相關聯的網域。

如果您新增子網域至組織，則 EOP 服務也可以協助您管理這些子網域。 若要深入瞭解子域，請參閱[啟用 Exchange Online 中子域的郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。

[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)簡介連接器並說明如何使用 EOP 連結器自訂郵件路由。案例包括確保與合作夥伴組織進行安全通訊及設定智慧主機。

若要確定垃圾郵件已正確路由傳送至每位使用者的垃圾郵件資料夾，您必須執行一些設定步驟。 在[設定獨立 EOP 將垃圾郵件傳送至混合式環境中的 [垃圾郵件] 資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)時，會加以詳述。 如果您不想要將郵件移至每個使用者的垃圾郵件資料夾，您可以在 Exchange 系統管理中心編輯內容篩選原則，以選擇另一個動作。 如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

## <a name="verify-mail-flow"></a>驗證郵件流程

若要驗證 EOP 設定是否正確運作，包括連接器組態，請參閱[設定 EOP 服務](set-up-your-eop-service.md)中的「如何知道這是否正常運作？」一節。

[測試郵件流程：透過驗證您的 Office 365 連接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)提供測試郵件流程設定正確的指示。
