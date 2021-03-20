---
title: EOP 中的郵件流程
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解在 Exchange Online Protection (EOP) 中設定郵件流程及路由的選項。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 043f093c801725cdf006c7c3afe7672e67d9fcef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907023"
---
# <a name="mail-flow-in-eop"></a>EOP 中的郵件流程

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在具有 Exchange Online 信箱的 Microsoft 365 組織中，或獨立 Exchange Online Protection (EOP) 組織沒有 Exchange Online 信箱，所有傳送給您組織的郵件都會透過 EOP 傳遞，然後您的工作者才能看到它們。 您可以選擇如何路由傳送至您的工作人員收件匣的郵件，並透過 EOP 進行處理。

## <a name="working-with-messages-and-message-access-options"></a>使用郵件和郵件存取選項

EOP 提供郵件路由傳送方式的彈性。 下列主題說明郵件流程處理序中的步驟。

[使用目錄架構邊緣封鎖以拒絕傳送至無效收件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 者的郵件描述目錄型 Edge 封鎖功能，可讓您拒絕服務網路周邊上無效收件者的郵件。

[在 EOP 中查看或編輯受管理的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 說明如何管理與 EOP 服務相關聯的網域。

如果您新增子網域至組織，則 EOP 服務也可以協助您管理這些子網域。 若要深入瞭解子域，請參閱 [啟用 Exchange Online 中子域的郵件流程](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。

[使用連接器來設定郵件流程](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 介紹連接器，並說明如何使用這些連接器來自訂郵件路由。 案例包括確保與合作夥伴組織進行安全通訊及設定智慧主機。

[針對連接器的增強篩選](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 說明如何在 EOP 之前，先將郵件路由傳送至服務或裝置，以設定連接器。

在獨立 EOP 組織中，您必須執行一些設定步驟，以確保垃圾郵件可正確路由傳送至每位使用者的垃圾郵件資料夾。 在 [設定獨立 EOP 將垃圾郵件傳送至混合式環境中的 [垃圾郵件] 資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)時，會加以詳述。 如果您不想要將郵件移至每個使用者的垃圾郵件資料夾，您可以編輯反垃圾郵件原則 (也稱為「內容篩選原則」) ，以選擇另一個動作。 如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

## <a name="verify-mail-flow"></a>驗證郵件流程

若要驗證 EOP 設定是否正確運作，包括連接器組態，請參閱[設定 EOP 服務](set-up-your-eop-service.md)中的「如何知道這是否正常運作？」一節。

[測試郵件流程：透過驗證 Microsoft 365 連接器](/exchange/mail-flow-best-practices/test-mail-flow) 提供測試郵件流程設定正確的指示。