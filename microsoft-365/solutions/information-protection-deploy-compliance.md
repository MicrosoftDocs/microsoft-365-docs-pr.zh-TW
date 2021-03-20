---
title: 使用合規性管理員管理改進動作
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
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
description: 瞭解如何使用合規性分數和合規性管理員，以提升個人資料的保護層級。
ms.openlocfilehash: 87131ea65661e8285fd7c3b36a87c79b618348d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918567"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>使用合規性管理員管理改進動作

Microsoft 合規性管理員可以協助您管理資料隱私權法規（如歐盟一般資料保護法規）的增強功能（如歐盟 [一般資料保護法規） (GDPR) ](/compliance/regulatory/gdpr)、 [加州消費者 Protection 法案 CCPA) ](/compliance/regulatory/ccpa-faq)、HIPAA-高科技 (美國衛生保健隱私權法案) ，以及巴西資料保護法案 (LGPD) 。

本文提供有關資料隱私權用途的使用此工具的指導方針。

>[!Note]
>您不應將 [合規性管理員] 提供的建議視為合規性的保證。 您可以根據法規環境評估和驗證客戶控制措施的效能。 這些服務須遵守 [線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。 另請參閱 [Microsoft 365 授權指南以取得安全性和合規性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>合規性管理員快速入門

#### <a name="what-is-compliance-manager"></a>何謂合規性管理員

[合規性管理員](../compliance/compliance-manager.md) 是 microsoft 365 合規性中心的工作流程型風險評估工具，以管理與 Microsoft cloud services 相關的法規遵從性活動。 在 Microsoft 365 或 Azure Active Directory 的一部分中 (Azure AD) 訂閱，合規性管理員可協助您管理 Microsoft 雲端服務共用責任模型內的法規遵從性。

**準備好使用評估**

合規性管理員提供預先構建的範本，以建立與資料隱私權相關的法規（如 GDPR 和 HIPAA/高科技）對齊的 [評估](../compliance/compliance-manager-assessments.md) 。 範本具有內建的控制項對應，可協助您採取改進的動作來滿足規定的需求。 每項評估都提供有關特定于目標服務之每項法規要求的資訊，並由您管理和控制 Microsoft 管理的控制項所中斷。 

使用預先建立的範本可協助您快速開始使用風險評估。 隨著您在使用合規性管理員的熟練程度，您可以透過新增您自己的控制項和改進動作來自訂預先建立的範本，也可以建立您自己的自訂評估，以符合組織的需求。

查看合規性管理員所提供 [之評估範本的完整清單](../compliance/compliance-manager-templates-list.md) 。

**即時合規性分數**

合規性管理員也會為您提供符合性分數，以度量您在控制項中完成建議的改進動作的進度。 您可以使用這個分數來協助監視您的進度，並根據可能降低風險的可能性來排定動作優先順序。

#### <a name="use-the-compliance-manager-quickstart-guide"></a>使用合規性管理員快速入門手冊

[合規性管理員快速入門](../compliance/compliance-manager-quickstart.md)指南提供逐步的步驟和重要資源的連結，以協助您使用合規性管理員：

- [第一次就診：深入瞭解合規性管理員](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - 與您的合規性管理員儀表板搭配使用
    - 瞭解您的合規性分數
    - 瞭解改進動作
    - 瞭解評估與範本
- [斜向向上：設定合規性管理員以管理您的相容性活動](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - 建立及管理您的第一筆評估
    - 執行執行和測試改進動作以完成評估中的控制項
    - 瞭解不同的動作會如何影響您的合規性分數
- [向上擴充：使用高級功能以符合您的自訂需求](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - 建立您的自訂評估以追蹤非 Microsoft 365 產品
    - 修改現有範本以新增或移除控制項
    - 設定改進動作的自動測試

## <a name="how-your-compliance-score-is-calculated"></a>如何計算合規性分數

您的合規性分數是根據 Microsoft 與客戶管理的控制項實施的組合來計算。 請參閱 [相容性分數計算](../compliance/compliance-score-calculation.md) 以取得詳細的說明。

控制項會根據其是否為強制性或自由的，以及是否為預防性、偵探或糾正，指派分數值。 兩者共同代表其相對於其他控制項的實施風險。

如合規性分數計算文章中所示，預防控制措施取得的分數高於偵探和修正，而強制控制措施取得的分數高於自由。

合規性分數管理 UI 不會列出這些參數，也不會提供加以篩選的功能。 不過，如果您從合規性管理員下載相關聯的範本，則產生的資料集會為大多數規定列出這些參數。

針對技術控制，符合性管理員會在成功實施及測試動作時，自動更新改進動作分數。 其他非技術控制動作（如可 &mdash; 操作或與檔相關的動作）必須 &mdash; 以手動方式錄製，以在分數的點數開始之前進行。

此外，您還可以針對其他用途執行某些改進動作，例如， &mdash; 使用保留標籤的原因並非資料隱私權法規合規性 &mdash; ，因此，即使是用於其他用途，也不是故意執行法規遵從性動作的一部分，您也可以取得使用此類功能的信用。

您的合規性分數應視為追蹤廣泛規模改進的相對量。 您不應採用完美的分數。

## <a name="additional-guidance"></a>其他指引

以下是使用合規性管理員協助您達到資料隱私權法規合規性的一些重要秘訣：

- 每個資料隱私權規定都結合了技術控制、檔規格，以及作業、程式和報表需求。 所有這些動作都會顯示在改進動作中。

- 若要將改進動作的查看重點放在您感興趣的區域，您可以在合規性管理員系統管理員的 [ **解決方案** ] 索引標籤中篩選動作類型。深入瞭解 [篩選合規性管理員儀表板視圖](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)。

- 在合規性管理員中識別的「改進動作」的相對重要性和優先順序，應視為廣泛風險審查的一部分，以及您已判斷貴組織需要管理的資料隱私權風險。

- 即使已選取 GDPR、LGPD、CCPA 及 HIPAA-高科技的規章評估範本，也會針對多種法規需求進行改進動作匯總，例如，合規性管理員中會列出幾乎400改進動作。 若要更好地處理這個長清單，請使用 [改進動作篩選]，將結果集縮小為更易於管理的清單。

- [類別] 篩選提供一種方法，可透過邏輯群組篩選改進動作，以追蹤、避免、保護、保留及調查此整體解決方案中的文章對齊。

- [！附注] 中所列的某些控制項，可能會被視為更直接與特定的規章相關的專案，而其他控制項可能更直接與法規精神產生關聯，許多時間只是建議的活動或最佳作法。