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
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="6fde1-103">步驟 2：設定環境的分類</span><span class="sxs-lookup"><span data-stu-id="6fde1-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="6fde1-104">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="6fde1-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="6fde1-105">在此步驟中，您會與法律和法規遵循小組合作，定義組織資料的分類配置。</span><span class="sxs-lookup"><span data-stu-id="6fde1-105">In Step 3, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-classifications"></a><span data-ttu-id="6fde1-106">Microsoft 的分類</span><span class="sxs-lookup"><span data-stu-id="6fde1-106">Microsoft classifications</span></span>

<span data-ttu-id="6fde1-107">Microsoft 365 的分類有三種：</span><span class="sxs-lookup"><span data-stu-id="6fde1-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="6fde1-108">Office 365 的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="6fde1-108">Sensitive information types for Office 365</span></span>
- <span data-ttu-id="6fde1-109">Office 365 標籤</span><span class="sxs-lookup"><span data-stu-id="6fde1-109">Office 365 labels</span></span>
- <span data-ttu-id="6fde1-110">Azure 資訊保護的標籤和保護</span><span class="sxs-lookup"><span data-stu-id="6fde1-110">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types-for-office-365"></a><span data-ttu-id="6fde1-111">Office 365 的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="6fde1-111">Sensitive information types for Office 365</span></span>

<span data-ttu-id="6fde1-p101">Office 365 的機密資訊類型定義了如何自動處理，例如搜尋辨識特定的資訊類型，像是健保卡號、信用卡號碼。您使用機密資料類型來尋找並套用資料外洩防護規則與原則，以保護這些資料。如需詳細資訊，請參閱[資料外洩防護原則概觀](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)。機密資訊類型特別有助於符合規範和法規需求，像是「一般資料保護規定」(GDPR)。</span><span class="sxs-lookup"><span data-stu-id="6fde1-p101">Sensitive information types for Office 365 define how automated processes such as search recognize specific information types such as health service numbers and credit card numbers. You use sensitive information types to find sensitive data and apply data loss prevention rules and policies to protect this data. For more information, see [Overview of data loss prevention policies](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). For example, sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="office-365-labels"></a><span data-ttu-id="6fde1-116">Office 365 標籤</span><span class="sxs-lookup"><span data-stu-id="6fde1-116">Office 365 labels</span></span>
<span data-ttu-id="6fde1-p102">您可以將 Office 365 標籤用於個人資料和以及 SharePoint Online 和商務用 OneDrive 中高度管制的商業機密檔案。如需詳細資訊，包括如何建立標籤，請參閱[標籤概觀](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30)。</span><span class="sxs-lookup"><span data-stu-id="6fde1-p102">You can use Office 365 labels for personal data and for highly regulated and trade secret files stored in SharePoint Online and OneDrive for Business. For more information, including how to create them, see [Overview of labels](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span></span>

<span data-ttu-id="6fde1-p103">如果您決定要使用 Office 365 標籤，每個層級的保護至少必須設定一個標籤。例如，為以下層級建立三個標籤：</span><span class="sxs-lookup"><span data-stu-id="6fde1-p103">If you decide to use Office 365 labels, you should configure at least one for each level of protection. For example, create three labels for:</span></span>

- <span data-ttu-id="6fde1-121">基準</span><span class="sxs-lookup"><span data-stu-id="6fde1-121">Baseline</span></span>
- <span data-ttu-id="6fde1-122">敏感性</span><span class="sxs-lookup"><span data-stu-id="6fde1-122">Sensitive</span></span>
- <span data-ttu-id="6fde1-123">高管制</span><span class="sxs-lookup"><span data-stu-id="6fde1-123">Highly regulated</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="6fde1-124">Azure 資訊保護的標籤和保護</span><span class="sxs-lookup"><span data-stu-id="6fde1-124">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="6fde1-p104">您可以使用 Azure 資訊保護標籤進行分類，並選擇性地保護組織的文件和電子郵件。這些標籤可以套用到不是儲存在 Office 365 中的文件。系統管理員可以自動套用這些標籤，他需要定義規則和條件、使用者手動套用、或前二者的組合 (使用者會收到建議)。</span><span class="sxs-lookup"><span data-stu-id="6fde1-p104">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails. These labels can apply to documents that are stored outside of Office 365. These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="6fde1-128">若要規劃及套用 Azure 資訊保護的標籤和保護，請這麼做：</span><span class="sxs-lookup"><span data-stu-id="6fde1-128">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="6fde1-129">檢閱 [Azure 資訊保護的需求](https://docs.microsoft.com/information-protection/get-started/requirements)。</span><span class="sxs-lookup"><span data-stu-id="6fde1-129">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="6fde1-130">遵循[分類、標籤、保護的部署藍圖](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)。</span><span class="sxs-lookup"><span data-stu-id="6fde1-130">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="6fde1-131">如需詳細資訊，請參閱 [Azure 資訊保護文件的文件庫](https://docs.microsoft.com/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="6fde1-131">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

## <a name="classification-for-gdpr"></a><span data-ttu-id="6fde1-132">GDPR 的分類</span><span class="sxs-lookup"><span data-stu-id="6fde1-132">Classification for GDPR</span></span>

<span data-ttu-id="6fde1-133">如需 GDPR 包含個人資料的分類配置範例，請參閱[設計個人資料的分類結構描述](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)。</span><span class="sxs-lookup"><span data-stu-id="6fde1-133">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="6fde1-135">測試實驗室指南：資料分類</span><span class="sxs-lookup"><span data-stu-id="6fde1-135">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="6fde1-136">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step3)。</span><span class="sxs-lookup"><span data-stu-id="6fde1-136">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="6fde1-137">下一步</span><span class="sxs-lookup"><span data-stu-id="6fde1-137">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="6fde1-138">設定增強的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="6fde1-138">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

