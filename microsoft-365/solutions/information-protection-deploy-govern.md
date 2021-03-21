---
title: 管理資料隱私權法規的使用資訊
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 使用 Microsoft 365 保留標籤和原則來管理您的 Microsoft 365 環境中的個人資料。
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928433"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>管理資料隱私權法規的使用資訊

您可以在您的環境中使用資訊控管控制，以協助滿足資料隱私權符合性需求，包括一般資料保護法規的特定數位 (GDPR) 、HIPAA-高科技 (美國衛生保健隱私權法案) 、加州消費者 Protection 法案 (CCPA) ，以及巴西資料保護法案 (LGPD) 。 

這些控制項主要分為下列解決方案區域：

- 保留原則
- 保留標籤
- 記錄管理

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>影響資訊管理控制的資料隱私權法規

以下是可能與資訊管理控制相關之資料隱私權法規的範例清單：

- GDPR 文章 (13)  (2)  () 
- GDPR 文章 (5)  (1)  (f) 
- HIPAA-高科技 (45 CFR 164.312 (c)  (2) ) 
- HIPAA-高科技 (45 CFR 164.316 (b)  (1)  (i) ) 
- HIPAA-高科技 (45 CFR 164.316 (b)  (1)  (ii) ) 
- LGPD 文章46

如需這些法規的詳細資訊，請參閱 [評估資料隱私權風險及識別敏感資訊文章](information-protection-deploy-assess.md)。

針對資訊管理，資料隱私權規定一般會呼叫下列各項：

- 您應該針對儲存在 Microsoft 365 中的個人資料，使用技術方案進行保留和刪除。
- 如果您想要儲存個人資料，請將儲存資料的時間，告知其使用時間，這是前端網頁系統的標準作法。
- 個人資料應受到保護，避免意外處理、遺失或篡改使用可驗證的方法。
- 應該記錄針對個人資料執行的任何動作，而且檔應保留指定期間內。

因為資料保密規定是資料保留和刪除的特別不足之處，所以必須考慮其他因素，以規定儲存在 Microsoft 365 訂閱中的個人資訊的資訊控管指導方針。 以下是一些範例：

- 使用五年後的使用者帳戶，且需要在該點之後刪除或匿名帳戶資料，需要在儲存與通知及其他自動化相關之資料和工作流程的系統之間進行業務流程。
- 設定規則，使與 GDPR 相關的原則和程式在已被取代後，以三年為依據，與組織的原則和程式保留排程相符。
- 維護個別訂閱，以透過其支援組織與消費者進行通訊。 所有的電子郵件通訊會在兩周後保留並刪除，以減少系統中的任何隱私權債務。

要回答的重要問題是： 

- 包含個人資料的資訊必須保留多久，以避免「永遠保留它」做法，以避免有效的商業理由？ 這必須與業務持續性的保留需求平衡。

不論保留或刪除個人資訊的法律和業務原因為何，Microsoft 都會提供一些功能，以在 Microsoft 365 中實施您的資料管理架構。

## <a name="managing-information-governance-in-microsoft-365"></a>管理 Microsoft 365 中的資訊管理

若要開始，請參閱管理 Microsoft 365 中的 [資訊](../compliance/manage-information-governance.md) 管理和 [資料保留、刪除和銷毀](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)。

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>開發容器、電子郵件和內容的資料保留時間表

請記住下列事項：

- 為定義的資訊類型建立資料保留排程，應視為實施任何保留或刪除配置的必要條件。

- 根據大多陣列織認為重要的資訊類型數量，以及與這些類型相關的大型記錄保留排程，實現資料保留及記錄管理原則需要規劃。 

- 建立這種類型的有效資料控管策略，主要是著重于需要更正式管理的最高優先順序商務功能和資訊類型。 例如法律合約、金融報表和法規規範檔。 請嘗試避免每一種單一資訊類型都有個別的保留排程。 請盡可能盡可能使用一般類別，例如，針對一般商務內容使用7年的保留時間表。

- 一旦環境中的個人資訊類型更知名，請建立這種內容類型的保留和刪除排程，並調整您的資訊架構，以簡化這類資訊的管理。 例如，以可控存取方式隔離個別網站、文件庫或資料夾中的個人資訊。

### <a name="retention-policies-and-retention-labels"></a>保留原則和保留標籤

使用 [保留原則和保留標籤](../compliance/retention.md) ，保留或刪除包含或預計包含個人資料之 Microsoft 365 中的內容。

### <a name="records-management"></a>記錄管理

使用可宣告內容 a 記錄的保留標籤，以對 Microsoft 365 中的資料執行 [記錄管理解決方案](../compliance/records-management.md) 。

針對資料隱私權，合法系所收到的資料主體要求 (Dsr) 會宣告一筆記錄，而且可以使用大量儲存或處置憑證，以遵守法規活動的保留規格。