---
title: 開始使用 Microsoft 365 中的記錄管理
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
description: 需要適用于 Microsoft 365 的記錄管理解決方案，以管理法律、企業或法規責任的高價值內容，但不確定要從何處著手？ 若要開始進行，請參閱一些實用的指導方針。
ms.openlocfilehash: fd3e3368b7a23cb31a8df4953268576de2419f89
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333849"
---
# <a name="get-started-with-records-management"></a>開始使用記錄管理

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

準備好開始使用 Microsoft 365 中的記錄管理解決方案，著手管理貴組織的法律、商務或法規責任的高價值內容嗎？ 使用下列高層指導方針以開始進行：

1. **瞭解記錄管理解決方案** ，以及當文件和電子郵件聲明為記錄時允許或封鎖的動作： [瞭解記錄管理](records-management.md)。 

2. **瞭解保留標籤以及如何在 SharePoint 和 Exchange 中使用保留功能** ，因為保留標籤是用來聲明記錄： [瞭解保留原則和保留標籤](retention.md)

3. 透過 [匯出現有方案](file-plan-manager.md#import-retention-labels-into-your-file-plan )(如果有的話)，以**針對保留設定和動作建立您的檔案方案**，或建立 [ 聲明記錄的新保留標籤](declare-records.md)。

4. **發佈並套用您的保留標籤**。 保留標籤是可在多個原則中使用的可重複使用構造塊，且可納入使用者工作流程: 
    
    - [建立保留標籤，並在應用程式中使用這些標籤](create-apply-retention-labels.md)
    - [自動將保留標籤套用到內容](apply-retention-labels-automatically.md)

## <a name="subscription-and-licensing-requirements-for-records-management"></a>記錄管理的訂閱和授權需求

許多不同的訂閱都支援記錄管理，以及使用者的授權需求取決於您所使用的功能。

若要查看授權使用者使用 Microsoft 365 合規性功能的選項，請參閱 [Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。 針對記錄管理，請參閱 [記錄管理](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) 一節，以及相關的 PDF 或 Excel 下載功能層級授權需求。

## <a name="permissions-required-for-records-management"></a>記錄管理所需的存取權限。

您的合規性團隊中負責記錄管理的成員，必須具備 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)的權限。 根據預設，租用戶系統管理員 (全域系統管理員) 能夠存取此位置，並可讓法務人員和其他人員存取，而不需要為其提供租用戶系統管理員的所有權限。若要授與此受限制的系統管理權限，建議您將使用者新增至有權授與 **RecordManagement** 角色的 **記錄管理** 系統管理員角色群組。

此角色群組中所包含的權限不包含 [處置檢閱和驗證](disposition.md)所需的權限，根據預設，即使是全域系統管理員也不擁有此權限。 若要管理處置，請透過建立自訂角色群組，或使用包含此角色的預設角色群組(例如 **合規性系統管理員**) 以使用 **處置管理** 角色。

如需有關這些角色群組和角色的詳細資訊，請參閱[安全性與合規性中心的權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center#roles-in-the-security--compliance-center)。

如需將使用者新增至角色和指派角色的指示，請參閱[給予使用者安全性與合規性中心的存取權](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。

只有在建立、設定、和套用聲明記錄及管理處置的保留標籤時，才需要求這些權限。 設定這些保留標籤的人員毋須存取內容。

## <a name="common-scenarios-for-records-management"></a>記錄管理的常見案例。

使用下表來協助您將商務需求對應至記錄管理支援的案例。

> [!NOTE]
> 由於記錄管理會使用保留標籤將專案標示為記錄，因此該表中的許多案例也會列為 [保留原則和保留標籤常見案例](get-started-with-retention.md#common-scenarios-for-retention-policies-and-retention-labels)。

|我想要...|文件|
|----------------|---------------|
|聲明記錄 |[使用保留標籤聲明記錄](declare-records.md)|
|更新記錄 |[使用記錄版本設定來更新儲存在 SharePoint 或 OneDrive 中的記錄](record-versioning.md)|
|讓系統管理員和使用者手動為文件和電子郵件套用保留和刪除動作： <br />- SharePoint <br />- OneDrive <br />- Outlook 和 Outlook 網頁版|[建立保留標籤，並在應用程式中套用這些標籤](create-apply-retention-labels.md)|
|讓網站系統管理員為 SharePoint 文件庫、資料夾或文件集的所有內容設定預設保留和刪除動作|[建立保留標籤，並在應用程式中套用這些標籤](create-apply-retention-labels.md)|
|讓使用者使用 Outlook 規則自動對電子郵件套用保留和刪除動作|[建立保留標籤，並在應用程式中套用這些標籤](create-apply-retention-labels.md)|
|讓系統管理員對文件瞭解模型套用保留和刪除動作，以便將這些動作自動套用至 SharePoint 文件庫中已識別的文件。|[建立保留標籤，並在應用程式中套用這些標籤](create-apply-retention-labels.md)|
|自動對文件和電子郵件套用保留和刪除動作 |[自動將保留標籤套用到內容](apply-retention-labels-automatically.md)|
|當事件發生時，請啟動保留時間，例如:  <br />- 員工離開組織 <br />- 合約到期 <br />- 產品生命週期完結| [事件發生時開始保留](event-driven-retention.md)|
|管理 SharePoint 中不同文件類型的生命週期| [使用保留標籤來管理儲存在 SharePoint 中的文件生命週期](auto-apply-retention-labels-scenario.md)|
|請確認在內容在保留期結束被永久刪除前，有人對內容進行檢查並核准|[處置檢閱](disposition.md#disposition-reviews) |
|在保留期結束時被永久刪除的內容有處置證明|[記錄處置](disposition.md#disposition-of-records) |
|監控保留和刪除設定如何套用至項目 | [監視保留標籤](retention.md#monitoring-retention-labels) |

## <a name="end-user-documentation-for-records"></a>記錄的終端使用者文件

記錄管理的保留標籤會在 Microsoft 365 應用程式中顯示為 UI。 在您將保留標籤部署到生產網路前，請務必為使用者和您的技術支援部門提供指導方針。

最有效的使用者文件會是您為所選的保留標籤名稱和組態提供的自訂指導方針和指示。 不過，您可以使用下列資訊來取得基本指示：

- [手動套用保留標籤](create-apply-retention-labels.md#manually-apply-retention-labels)
