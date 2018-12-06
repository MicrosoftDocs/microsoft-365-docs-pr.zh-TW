---
title: 步驟 2：設定環境的分類
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定在組織中分類資料的不同方式。
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866317"
---
# <a name="step-2-configure-classification-for-your-environment"></a>步驟 2：設定環境的分類

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

在此步驟中，您會與法律和法規遵循小組合作，定義組織資料的分類配置。

## <a name="microsoft-classifications"></a>Microsoft 的分類

Microsoft 365 的分類有三種：

- Office 365 的敏感資訊類型
- Office 365 標籤
- Azure 資訊保護的標籤和保護

### <a name="sensitive-information-types-for-office-365"></a>Office 365 的敏感資訊類型

Office 365 的機密資訊類型定義了如何自動處理，例如搜尋辨識特定的資訊類型，像是健保卡號、信用卡號碼。您使用機密資料類型來尋找並套用資料外洩防護規則與原則，以保護這些資料。如需詳細資訊，請參閱[資料外洩防護原則概觀](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)。機密資訊類型特別有助於符合規範和法規需求，像是「一般資料保護規定」(GDPR)。

### <a name="office-365-labels"></a>Office 365 標籤
您可以將 Office 365 標籤用於個人資料和以及 SharePoint Online 和商務用 OneDrive 中高度管制的商業機密檔案。如需詳細資訊，包括如何建立標籤，請參閱[標籤概觀](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30)。

如果您決定要使用 Office 365 標籤，每個層級的保護至少必須設定一個標籤。例如，為以下層級建立三個標籤：

- 基準
- 敏感性
- 高管制

### <a name="azure-information-protection-labels-and-protection"></a>Azure 資訊保護的標籤和保護

您可以使用 Azure 資訊保護標籤進行分類，並選擇性地保護組織的文件和電子郵件。這些標籤可以套用到不是儲存在 Office 365 中的文件。系統管理員可以自動套用這些標籤，他需要定義規則和條件、使用者手動套用、或前二者的組合 (使用者會收到建議)。

若要規劃及套用 Azure 資訊保護的標籤和保護，請這麼做：

1. 檢閱 [Azure 資訊保護的需求](https://docs.microsoft.com/information-protection/get-started/requirements)。
2. 遵循[分類、標籤、保護的部署藍圖](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)。

如需詳細資訊，請參閱 [Azure 資訊保護文件的文件庫](https://docs.microsoft.com/information-protection/)。

## <a name="classification-for-gdpr"></a>GDPR 的分類

如需 GDPR 包含個人資料的分類配置範例，請參閱[設計個人資料的分類結構描述](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：資料分類](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step3)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[設定增強的 Office 365 安全性](infoprotect-configure-increased-security-office-365.md)|

