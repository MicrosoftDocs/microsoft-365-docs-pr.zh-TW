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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 準備開始實作保留原則及保留標籤來管理貴組織的資料，但不確定從何處著手？ 若要開始進行，請參閱一些實用的指導方針。
ms.openlocfilehash: 26568d2a603e447156aead751178555fa400db5e
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682528"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>開始使用保留原則和保留標籤

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

準備好透過保留您要保留的內容，並刪除您不想要的內容，以開始管理貴組織的資料了嗎？ 使用下列高層指導方針以開始進行：

1. **瞭解 Microsoft 365 中的保留運作方式**，然後找出您是否需要使用保留原則或保留標籤，或下列其中一種組合方式： [瞭解保留原則](retention.md)

2. **識別組織政策或行業法規所需的保留設定和動作**。
    
    在此評估中，請判斷您是否會使用 [記錄管理](records-management.md)。

3. 根據您發現的保留設定和動作 **建立保留原則和保留標籤**。
    
    針對保留標籤，您可能會發現使用 [[檔案計畫]](file-plan-manager.md) 定義及精煉試算表中的保留標籤是非常實用的。 然後，匯入該試算表以建立您的標籤。
    
3. **發佈並套用您的保留標籤**。 保留原則是專為「設定並遺忘」設定而設計，保留標籤是可在多個原則中使用的可重複使用構造塊，且可納入使用者工作流程。 請參閱 [常見案例](#common-scenarios-for-retention-policies-and-retention-labels) ，以協助您找出保留標籤的使用方式。 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>保留原則和保留標籤的訂閱和授權需求

許多不同的訂閱都支援保留原則和保留標籤，以及使用者的授權需求取決於您所使用的功能。

若要查看授權使用者使用 Microsoft 365 合規性功能的選項，請參閱 [Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。 如需保留，請參閱 [資訊管轄](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 一節，以及相關的 PDF 或 Excel 下載功能層級授權需求。

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>建立和管理保留原則和保留標籤所需權限。

您的合規性團隊中負責建立和管理保留原則和保留標籤的成員，必須具備 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)的權限。 根據預設，租用戶系統管理員 (全域系統管理員) 能夠存取此位置，並可讓法務人員和其他人員存取，而不需要為其提供租用戶系統管理員的所有權限。若要授與此受限制的系統管理權限，建議您將使用者新增至 [合規性系統管理員] 系統管理員角色群組。

除了使用此預設角色之外，您還可以建立新角色群組並將 **[保留管理]** 角色新增到此群組中。 對於唯讀角色，請使用 **[僅檢視保留管理]**。 

如需有關角色群組和角色的詳細資訊，請參閱[安全性與合規性中心的權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center#roles-in-the-security--compliance-center)。

如需將使用者新增至角色和指派角色的指示，請參閱[給予使用者安全性與合規性中心的存取權](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。

只有在建立、設定、和套用保留原則及保留標籤時，才需要求這些權限。 設定這些保留原則和標籤的人員不需要內容的存取權。

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>保留原則和保留標籤的常見案例

使用下表來協助您將商務需求對應至保留原則和保留標籤支援的保留案例。

|我想要...|文件|
|----------------|---------------|
|按 Microsoft 365 服務有效設定保留和刪除動作： <br />- Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Microsoft 365 群組 <br />- 商務用 Skype  <br />- Microsoft Teams <br />- Yammer 網路 |[建立及設定保留原則](create-retention-policies.md)|
|讓系統管理員和使用者手動為文件和電子郵件套用保留和刪除動作： <br />- SharePoint <br />- OneDrive <br />- Outlook 和 Outlook 網頁版|[建立保留標籤，並在應用程式中套用這些標籤](create-apply-retention-labels.md)|
|讓網站系統管理員為 SharePoint 文件庫、資料夾或文件集的所有內容設定預設保留和刪除動作|[建立保留標籤，並在應用程式中套用這些標籤](create-apply-retention-labels.md)|
|讓使用者使用 Outlook 規則自動對電子郵件套用保留和刪除動作|[建立保留標籤，並在應用程式中套用這些標籤](create-apply-retention-labels.md)|
|讓系統管理員對文件瞭解模型套用保留和刪除動作，以便將這些動作自動套用至 SharePoint 文件庫中已識別的文件。|[建立保留標籤，並在應用程式中套用這些標籤](create-apply-retention-labels.md)|
|自動對文件和電子郵件套用保留和刪除動作 |[自動將保留標籤套用到內容](apply-retention-labels-automatically.md)|
|當事件發生時，請啟動保留時間，例如:  <br />- 員工離開組織 <br />- 合約到期 <br />- 產品生命週期完結| [事件發生時開始保留](event-driven-retention.md)|
|限制變更原則，以協助符合法規需求或防範惡意系統管理員| [使用「保留鎖定」來限制變更保留原則和保留標籤原則](retention-preservation-lock.md)
|請確認在內容在保留期結束被刪除前，有人對內容進行檢查並核准|[處置檢閱](disposition.md#disposition-reviews) |
| 監控保留和刪除設定如何套用至項目 | [監視保留標籤](retention.md#monitoring-retention-labels) |
|針對文件和電子郵件使用單一記錄管理解決方案 |[了解記錄管理](records-management.md) |

如果您是為了記錄管理而使用保留標籤，還有其他保留標籤專用的案例，也可將其內容標示為記錄。 請參閱 [記錄管理的常見案例](get-started-with-records-management.md#common-scenarios-for-records-management)。

## <a name="end-user-documentation-for-retention-labels"></a>保留標籤的終端使用者文件

不同于保留原則，保留標籤在 Microsoft 365 應用程式中具有 UI。 在您將保留標籤部署到生產網路前，請務必為使用者和您的技術支援部門提供指導方針。

最有效的使用者文件會是您為所選的保留標籤名稱和組態提供的自訂指導方針和指示。 請參閱下列部落格文章，以取得可供您用來訓練使用者並推動採用的下載套件：[關於 M365 保留標籤的使用者訓練 – 瞭解如何加速採用](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-retention-labels-in-m365-how-to-accelerate/ba-p/1750861) (英文)。

您也會在以下章節中找到基本的使用者指示：[手動套用保留標籤](create-apply-retention-labels.md#manually-apply-retention-labels)。
