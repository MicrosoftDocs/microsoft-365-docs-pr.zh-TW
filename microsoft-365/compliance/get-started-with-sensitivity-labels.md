---
title: 開始使用敏感度標籤
f1.keywords:
- CSH
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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 準備開始實作敏感度標籤來協助保護貴組織的資料，但不確定從何處著手？ 閱讀一些實用的指導方針，以協助您開始套用標籤的旅程。
ms.openlocfilehash: b2a16da1d4a7b9b35d519d544eba951765122596
ms.sourcegitcommit: 8d28bce1a3445878b066864e766cf52cb83becd1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2021
ms.locfileid: "50071298"
---
# <a name="get-started-with-sensitivity-labels"></a>開始使用敏感度標籤

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

如需敏感度標籤為何及其如何可協助您保護組織資料的相關資訊，請參閱[了解敏感度標籤](sensitivity-labels.md)。

如果您有 [Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)，請判斷是否需要將標籤移轉至統一標籤平台，以及要使用的標籤用戶端：
- [如何判斷我的租用戶是否在統一標籤平台上？](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [選擇要用於 Windows 電腦的標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

當您準備好要開始使用敏感度標籤來保護組織的資料時：

1. **建立標籤。** 根據貴組織用於不同內容敏感度層級的分類法，建立您的敏感度標籤並加以命名。 使用對您的使用者有意義的一般名稱或字詞。 如果您還沒有建立分類法，請考慮從 [個人]、[公用]、[一般]、[機密] 和 [高度機密] 等標籤名稱著手。 您可以接著使用子標籤，依類別將類似的標籤群組。 當您建立標籤時，請使用工具提示文字來協助使用者選取適當的標籤。
    
    如需更廣泛的定義分類法指導方針，請從[服務信任入口網站](https://aka.ms/DataClassificationWhitepaper)下載白皮書《資料分類和敏感度標籤分類》。

2. **定義每個標籤的功能。** 設定您想要與每個標籤相關聯的保護設定。 例如，您可能希望將較低敏感度內容 (如「一般」標籤) 僅套用到頁首或頁尾，而較高敏感度內容 (如「機密」標籤) 則具有浮水印和加密。

3. **發佈標籤。** 設定好敏感度標籤之後，請使用標籤原則加以發佈。 決定哪些使用者和群組應具有標籤，以及所要使用的原則設定。 單一標籤可重複使用；您只要定義一次，就可以將它納入指派給不同使用者的數個標籤原則中。 例如，您可以將標籤原則指派給少數幾個使用者來試驗您的敏感度標籤。 當您準備好在整個組織推出標籤時，您可以為標籤建立新的標籤原則，而這次指定所有使用者。

部署及套用敏感度標籤的基本流程：

![顯示敏感度標籤的工作流程圖](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>敏感度標籤的訂閱和授權需求

許多不同的訂閱都支援敏感度標籤，以及使用者的授權需求取決於您所使用的功能。

若要查看授權使用者使用 Microsoft 365 合規性功能的選項，請參閱 [Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。 如需敏感度標籤，請參閱[資訊保護](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)一節及相關的 PDF 或 Excel 下載。

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>建立和管理敏感度標籤所需的權限

合規性小組成員會建立敏感度標籤，這些成員需要 Microsoft 365 合規性中心、Microsoft 365 安全性中心或安全性與合規性中心的權限。 

根據預設，您的租用戶的全域系統管理員可以存取這些系統管理中心，並且授與法務人員和其他人員存取權限，而不需授與他們租用戶系統管理員的所有權限。如需這個委派的受限系統管理員存取權，請將使用者新增至 [合規性資料系統管理員]、[合規性系統管理員] 或 [安全性系統系統管理員] 角色群組。 

除了使用預設角色以外，您可以建立新的角色群組，並將 [敏感度標籤系統管理員] 或 [組織組態] 角色新增至此群組。 唯讀角色請使用 [敏感度標籤讀取器]。 

如需將使用者新增至預設角色或建立您自己的角色群組的指示，請參閱[讓使用者能夠存取 Office 365 安全規範中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。

只有建立及設定敏感度標籤及其標籤原則時，才需要這些權限。 您不需要在應用程式或服務中套用這些標籤。 如果與敏感度標籤相關的特定設定需要其他權限，則這些權限會列在個別的文件指示中。

## <a name="deployment-strategy-for-sensitivity-labels"></a>敏感度標籤的部署策略
為組織部署敏感度標籤的成功策略是建立工作虛擬小組，以識別及管理業務和技術需求、概念驗證、測試、內部檢查點和核准，以及生產環境的最後部署。

建議使用下一章的表格，確定與影響最大的業務需求對應的前兩種情況。 部署這些案例之後，請回到清單以確定下一個或下兩個部署的優先順序。

您可以在可下載的「資料外洩防護」與《Microsoft 資訊保護部署加速指南》中找到其他一般部署指導方針。 如需詳細資訊，請參閱部落格文章 [Microsoft 365 資訊保護和合規性部署加速指南](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-365-information-protection-and-compliance-deployment/ba-p/2076404) (英文)。

## <a name="common-scenarios-for-sensitivity-labels"></a>敏感度標籤的常見案例

所有案例均會要求您[建立及設定敏感度標籤及其原則](create-sensitivity-labels.md)。

|我想要...|文件|
|----------------|---------------|
|管理 Office 應用程式的敏感度標籤，讓內容標示為已建立 — 包括在所有平台上的手動標籤支援 |[在 Office 應用程式中使用敏感度標籤](sensitivity-labels-office-apps.md)|
|讓使用者能夠使用 Office 應用程式、檔案總管和 PowerShell，從 Windows 電腦標籤及保護檔案|[適用於 Windows 的 Azure 資訊保護整合標籤用戶端](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)|
|使用敏感度標籤加密文件和電子郵件，並限制能夠存取該內容的人員以及使用方式 |[使用敏感度標籤來套用加密以限制存取內容](encryption-sensitivity-labels.md)|
|在網頁上啟用 Office 的敏感度標籤，並提供共同撰寫、電子文件探索、資料遺失防護、搜尋支援，即使文件已加密 | [對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤](sensitivity-labels-sharepoint-onedrive-files.md)
|自動將敏感度標籤套用至文件和電子郵件 | [自動將敏感度標籤套用到內容](apply-sensitivity-label-automatically.md)|
|使用敏感度標籤來保護 Teams 和 SharePoint 中的內容 |[對 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站使用敏感度標籤](sensitivity-labels-teams-groups-sites.md)|
|防止或警告使用者共用具有特定敏感度標籤的檔案或電子郵件 |[使用敏感度標籤作為 DLP 原則中的條件 (預覽)](dlp-sensitivity-label-as-condition.md) |
|探索、標記和保護儲存在內部部署資料存放區中的檔案 |[部署 Azure 資訊保護掃描器以自動分類和保護檔案](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|探索、標記和保護儲存在雲端的資料存放區中的檔案|[探索、分類、標記和保護儲存在雲端中的控管和敏感性資料](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|在 Power BI 中套用和檢視標籤，並在服務外儲存該資料時加以保護|[在 Power BI 套用敏感度標籤](https://docs.microsoft.com/power-bi/admin/service-security-sensitivity-label-overview)|
|監視並了解組織中使用敏感度標籤的方法|[了解您的資料 - 資料分類概觀](data-classification-overview.md) <br /><br /> [開始使用資料分類](data-classification-overview.md)|
|將敏感度標籤延伸至第三方應用程式和服務|[Microsoft 資訊保護 SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|
|將敏感度標籤延伸至 Azure Blob 儲存體、Azure 檔案、Azure Data Lake Storage Gen1 和 Azure Data Lake Storage Gen12 中的內容|[在 Azure Purview 中自動為您的內容加上標籤](https://docs.microsoft.com/azure/purview/create-sensitivity-label) |


## <a name="end-user-documentation-for-sensitivity-labels"></a>敏感度標籤的使用者文件

最有效的使用者文件會是您為所選的標籤名稱和組態提供的自訂指導方針和指示。 請參閱下列部落格文章，以取得可供您用來訓練使用者並推動採用的下載套件：[關於 M365 敏感度標籤的使用者訓練 – 瞭解如何加速採用](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-sensitivity-labels-in-m365-how-to/ba-p/1750880)。 

您也可以使用下列資源來取得基本指示：

- [在 Office 中將敏感度標籤套用至您的檔案和電子郵件](https://support.microsoft.com/zh-TW/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Office 敏感度標籤的已知問題](https://support.microsoft.com/zh-TW/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [在 Office 中自動套用或建議敏感度標籤至您的檔案和電子郵件](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [自動套用或建議敏感度標籤的已知問題](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Azure 資訊保護統一標籤使用者指南](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-user-guide)

如果您的敏感度標籤為 PDF 文件套用加密，則可在 Windows 或 Mac 上使用 Microsoft Edge 開啟這些文件。 如需詳細資訊及替代閱讀程式，請參閱 [受保護的 PDF 文件支援哪些 PDF 閱讀程式？](https://docs.microsoft.com/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)
