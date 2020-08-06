---
title: 開始使用保留原則和保留標籤
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 準備開始實作保留原則及保留標籤來管理貴組織的資料，但不確定從何處著手？ 若要開始進行，請參閱一些實用的指導方針。
ms.openlocfilehash: b390e4594d97e96eadac9541429a838abe006a3f
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560760"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>開始使用保留原則和保留標籤

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

準備好透過保留您要保留的內容，並刪除您不想要的內容，以開始管理貴組織的資料了嗎？ 使用下列高層指導方針以開始進行：

1. **瞭解 Microsoft 365 中的保留運作方式**，然後找出您是否需要使用保留原則或保留標籤，或下列其中一種組合方式： [瞭解保留原則](retention.md)

2. **識別組織政策或行業法規所需的保留設定和動作**。
    
    在此評估中，請判斷您是否會使用 [記錄管理](records-management.md)。

3. 根據您發現的保留設定和動作**建立保留原則和保留標籤**。
    
    針對保留標籤，您可能會發現使用 [[檔案計畫]](file-plan-manager.md) 定義及精煉試算表中的保留標籤是非常實用的。 然後，匯入該試算表以建立您的標籤。
    
3. **發佈並套用您的保留標籤**。 保留原則是專為「設定並遺忘」設定而設計，保留標籤是可在多個原則中使用的可重複使用構造塊，且可納入使用者工作流程。 請參閱 [常見案例](#common-scenarios-for-retention-policies-and-retention-labels) ，以協助您找出保留標籤的使用方式。 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>保留原則和保留標籤的訂閱和授權需求

許多不同的訂閱都支援保留原則和保留標籤，以及使用者的授權需求取決於您所使用的功能。

若要查看授權使用者使用 Microsoft 365 合規性功能的選項，請參閱 [Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。 如需保留，請參閱 [資訊管轄](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 一節，以及相關的 PDF 或 Excel 下載功能層級授權需求。

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>建立和管理保留原則和保留標籤所需權限。

您的合規性團隊中負責建立和管理保留原則和保留標籤的成員，必須具備 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)的權限。 根據預設，租用戶系統管理員 (全域系統管理員) 能夠存取此位置，並可讓法務人員和其他人員存取，而不需要為其提供租用戶系統管理員的所有權限。若要授與此受限制的系統管理權限，建議您將使用者新增至 [合規性系統管理員]**** 系統管理員角色群組。 如需相關指示，請參閱[讓使用者能夠存取安全性與合規性中心的權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。

需要這些權限才能建立及套用保留原則。 設定保留原則的人員不需要存取內容。

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>保留原則和保留標籤的常見案例

使用下表來協助您將商務需求對應至保留原則和保留標籤支援的保留案例。

|我想要...|文件|
|----------------|---------------|
|為組織有效設定的保留和刪除動作，或按 Microsoft 365 服務： <br />- Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Microsoft 365 群組 <br />- 商務用 Skype  <br />- Microsoft Teams  |[建立及設定保留原則](create-retention-policies.md)|
|讓系統管理員和使用者手動為文件和電子郵件套用一組保留和刪除動作： <br />- SharePoint <br />- OneDrive <br />- Outlook 和 Outlook 網頁版|[建立保留標籤，並在應用程式中使用這些標籤](create-apply-retention-labels.md)|
|讓網站系統管理員為 SharePoint 文件庫、資料夾或文件集的所有內容設定預設保留標籤|[建立保留標籤，並在應用程式中使用這些標籤](create-apply-retention-labels.md)|
|讓使用者使用 Outlook 規則自動將保留標籤套用至電子郵件|[建立保留標籤，並在應用程式中使用這些標籤](create-apply-retention-labels.md)|
|自動為文件和電子郵件套用一組保留和刪除動作 |[自動將保留標籤套用到內容](apply-retention-labels-automatically.md)|
|當事件發生時，請啟動保留時間，例如:  <br />- 員工離開組織 <br />- 合約到期 <br />- 產品生命週期完結| [事件發生時開始保留](event-driven-retention.md)|
|管理 SharePoint 中不同文件類型的生命週期| [使用保留標籤來管理儲存在 SharePoint 中的文件生命週期](auto-apply-retention-labels-scenario.md)|
|針對文件和電子郵件使用單一記錄管理解決方案 |[Microsoft 365 中的記錄管理](records-management.md) |
|符合美國證券交易委員會規定 17A-4|[使用 Exchange Online 和安全性與合規性中心以符合 SEC Rule 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md) |
|請確認在內容在保留期結束被刪除前，有人對內容進行檢查並核准|[處置檢閱](disposition.md#disposition-reviews) |
|對於在保留期結束時被刪除的內容是否有處理證明|[記錄處置](disposition.md#disposition-of-records) |

## <a name="end-user-documentation-for-retention-labels"></a>保留標籤的終端使用者文件

不同于保留原則，保留標籤在 Microsoft 365 應用程式中具有 UI。 在您將保留標籤部署到生產網路前，請務必為使用者和您的技術支援部門提供指導方針。

最有效的使用者文件會是您為所選的保留標籤名稱和組態提供的自訂指導方針和指示。 不過，您可以使用下列資訊來取得基本指示：

- [手動套用保留標籤](create-apply-retention-labels.md#manually-apply-retention-labels)
