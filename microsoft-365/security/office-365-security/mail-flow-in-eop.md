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
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842491"
---
# <a name="mail-flow-in-eop"></a>EOP 中的郵件流程

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在具有 Exchange Online 信箱的 Microsoft 365 組織，或獨立 Exchange Online Protection (EOP) 組織若未 Exchange Online 信箱，所有傳送給您組織的郵件都會透過 EOP，再讓工作者看到這些郵件。 您可以選擇如何路由傳送至您的工作人員收件匣的郵件，並透過 EOP 進行處理。

## <a name="working-with-messages-and-message-access-options"></a>使用郵件和郵件存取選項

EOP 提供郵件路由傳送方式的彈性。 下列主題說明郵件流程處理序中的步驟。

[使用目錄架構邊緣封鎖以拒絕傳送至無效收件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 者的郵件描述目錄型 Edge 封鎖功能，可讓您拒絕服務網路周邊上無效收件者的郵件。

[View or edit 公認的網域 IN EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 說明如何管理與 EOP 服務相關聯的網域。

如果您新增子網域至組織，則 EOP 服務也可以協助您管理這些子網域。 若要深入瞭解子域，請參閱[啟用 Exchange Online 中子域的郵件流程](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。

[使用連接器來設定郵件流程](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 介紹連接器，並說明如何使用這些連接器來自訂郵件路由。 案例包括確保與合作夥伴組織進行安全通訊及設定智慧主機。

[針對連接器的增強篩選](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 說明如何在 EOP 之前，先將郵件路由傳送至服務或裝置，以設定連接器。

在 EOP 會保護內部部署 Exchange 信箱的混合式環境中，您必須在內部部署 Exchange 中設定郵件流程規則 (又稱為傳輸規則) 以轉譯 EOP 垃圾郵件篩選裁決，這樣垃圾郵件規則才可以將郵件移至 [垃圾郵件] 資料夾。 如需詳細資訊，請參閱[設定 EOP 以將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。 如果您不想要將郵件移至每個使用者的 [垃圾郵件] 資料夾，您可以編輯反垃圾郵件原則 (也稱為內容篩選原則) ，以選擇另一個動作。 如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

## <a name="verify-mail-flow"></a>驗證郵件流程

若要驗證 EOP 設定是否正確運作，包括連接器組態，請參閱[設定 EOP 服務](/exchange/standalone-eop/set-up-your-eop-service)中的「如何知道這是否正常運作？」一節。

[測試郵件流程：透過驗證 Microsoft 365 連接器](/exchange/mail-flow-best-practices/test-mail-flow)提供測試郵件流程是否設定正確的指示。
