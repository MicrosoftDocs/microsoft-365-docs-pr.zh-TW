---
title: 步驟 2：設定環境的分類
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定在組織中分類資料的不同方式。
ms.openlocfilehash: e8c40ca4c419edc2d59a060dfd4fe8918cf4e784
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067250"
---
# <a name="step-2-configure-classification-for-your-environment"></a>步驟 2：設定環境的分類

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![第 6 階段：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

在此步驟中，您會與法律和法規遵循小組合作，定義組織資料的分類配置。

## <a name="microsoft-365-classification-types"></a>Microsoft 365 分類類型

Microsoft 365 有四種分類：

- 敏感資訊類型
- 保留標籤
- 敏感度標籤
- Azure 資訊保護的標籤和保護

### <a name="sensitive-information-types"></a>敏感資訊類型

Microsoft 365 的敏感資訊類型會定義自動化程序 (例如搜尋) 如何辨識特定的資訊類型。 這些類型包含敏感的員工或客戶資料，例如健保號碼和信用卡號碼。 您可以使用敏感資訊類型來尋找敏感資料，並套用資料外洩防護 (DLP) 規則和原則來保護此資料。 如需詳細資訊，請參閱 [DLP 原則的內容](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains)。 

敏感資訊類型特別有助於符合合規性和法規需求，例如一般資料保護規定 (GDPR)。

### <a name="retention-labels"></a>保留標籤

在定義資料管理策略時，其中一項工作是決定應該將特定類型的文件或具有特定內容的文件保留多久，以符合組織的原則和地區的法規。 例如，某些類型的文件應該先保留一定時間再刪除，其他類型的文件則必須無限期保留。

對於儲存在 Microsoft 365 中的文件，您可以對 Exchange 電子郵件、SharePoint Online、商務用 OneDrive 以及 Teams 聊天和頻道的訊息中所儲存的文件和資料，定義並套用保留標籤。 

如果您使用保留標籤，請對必須套用保留原則的每個檔案類別設定標籤。 在保留標籤內，您可以指定：

- 一組檔案描述項 (例如，依業務部門、檔案類別或法規)。
- 已附加保留標籤的檔案所需的保留設定，例如保留時間和到達保留時間後的行為。

您也可以藉由設定 SharePoint Online 網站來自動對檔案套用保留標籤，以對該網站中的所有新文件套用預設的保留標籤。 

如需詳細資訊，請參閱[保留標籤概觀](https://docs.microsoft.com/office365/securitycompliance/labels)。

### <a name="sensitivity-labels"></a>敏感度標籤

在為特定類型的文件或具有特定內容的文件提供保護並實作安全性時，其中一項工作是使用標籤來加以標示，以便再套用一層安全性。 使用 Microsoft 365 中的敏感度標籤時，您可以：

- 強制執行保護設定，例如加密、權限或新增浮水印。
- 使用 Windows 資訊保護 (WIP) 端點保護來防止該內容遭人複製到第三方應用程式 (例如 Twitter 或 Gmail)，或複製到抽取式儲存體 (例如 USB 磁碟機)。
- 使用 Microsoft Cloud App Security (CAS) 來保護第三方應用程式和服務中的內容。 
- 不使用任何保護設定而將內容分類。

如果您使用敏感度標籤，請為每個安全性和資訊保護層級設定標籤。 例如，為下列項目建立三個敏感度標籤：

- 基準
- 敏感性
- 高管制

如果您將具有高度管控資料的檔案儲存在 SharePoint Online 網站中，並希望這些檔案的權限與網站相同，如果檔案離開網站，您就需要建立權限與網站相同的額外靈敏度標籤。

如需詳細資訊，請參閱此[敏感度標籤概觀](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels)。

### <a name="azure-information-protection-labels-and-protection"></a>Azure 資訊保護的標籤和保護

您可以使用 Azure 資訊保護標籤，將組織的文件和電子郵件進行分類，並選擇是否要提供保護。 這些標籤可以套用至並非儲存在 Microsoft 365 內的文件。 這些標籤可以由定義規則和條件的系統管理員自動套用、由使用者手動完成，或在提供建議給使用者的情況下由系統管理員搭配使用者的組合來完成。

若要規劃及套用 Azure 資訊保護的標籤和保護，請這麼做：

1. 檢閱 [Azure 資訊保護的需求](https://docs.microsoft.com/information-protection/get-started/requirements)。
2. 遵循[分類、標籤、保護的部署藍圖](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)。

如需詳細資訊，請參閱 [Azure 資訊保護文件的文件庫](https://docs.microsoft.com/information-protection/)。

現有的 Azure 資訊保護標籤可與敏感度標籤緊密配合。 例如，您可以將現有的 Azure 資訊保護標籤以及套用至文件和電子郵件的標籤保留下來。

如果您同時擁有敏感度標籤和 Azure 資訊保護標籤，請[將 Azure 資訊保護標籤遷移至敏感度標籤](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels)。

## <a name="example-classification-for-gdpr"></a>範例：GDPR 的分類

如需 GDPR 包含個人資料的分類配置範例，請參閱[設計個人資料的分類結構描述](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)。

## <a name="take-it-for-a-test-drive"></a>試用產品

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：資料分類](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step2)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![步驟 3](../media/stepnumbers/Step3.png)|[設定增強的 Office 365 安全性](infoprotect-configure-increased-security-office-365.md)|

