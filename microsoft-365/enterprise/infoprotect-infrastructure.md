---
title: 階段 6：資訊保護
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
description: Microsoft 365 企業版的資訊保護基礎結構部署步驟。
ms.openlocfilehash: d6e3501e8262a0c3245c6e13da6633ac465276fb
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268300"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="2c15f-103">第 6 階段：資訊保護</span><span class="sxs-lookup"><span data-stu-id="2c15f-103">Phase 6: Information protection</span></span>

![階段 6：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="2c15f-p101">資訊保護是定義如何傳送、儲存及處理機密資訊的一組原則和技術。在階段 6 中，您會逐步執行 Microsoft 365 企業版的資訊保護設定及功能，可協助您保護雲端式工作負載的資料。</span><span class="sxs-lookup"><span data-stu-id="2c15f-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads.</span></span>

>[!Note]
><span data-ttu-id="2c15f-107">如果您已部署資訊保護，請參閱此階段的[允出準則](infoprotect-exit-criteria.md)，確保其符合 Microsoft 365 企業版的必要與選用條件。</span><span class="sxs-lookup"><span data-stu-id="2c15f-107">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="2c15f-108">規劃及部署 Microsoft 365 企業版資訊保護基礎結構</span><span class="sxs-lookup"><span data-stu-id="2c15f-108">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="2c15f-p102">請務必諮詢法律和法規遵循團隊，判斷貴組織是否需符合規範標準，例如 HIPPA、CJIS 或 GDPR。您也應與安全性群組合作，以判斷您的組織以及需要額外安全性之部門或群組的資訊保護目標。</span><span class="sxs-lookup"><span data-stu-id="2c15f-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="2c15f-111">接下來，請使用下列步驟建立 Microsoft 365 企業版的資訊保護。</span><span class="sxs-lookup"><span data-stu-id="2c15f-111">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![步驟 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="2c15f-113">定義安全性和資訊保護層級</span><span class="sxs-lookup"><span data-stu-id="2c15f-113">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![步驟 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="2c15f-115">設定環境的分類</span><span class="sxs-lookup"><span data-stu-id="2c15f-115">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![步驟 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="2c15f-117">設定增強的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="2c15f-117">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![步驟 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="2c15f-119">設定 Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="2c15f-119">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![步驟 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="2c15f-121">設定資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="2c15f-121">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![步驟 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="2c15f-123">設定電子郵件加密</span><span class="sxs-lookup"><span data-stu-id="2c15f-123">Configure email encryption</span></span>](infoprotect-email-encryption.md)|
|![步驟 7](../media/stepnumbers/Step7.png)|[<span data-ttu-id="2c15f-125">設定 Office 365 的特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="2c15f-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
|||

<span data-ttu-id="2c15f-126">完成這些步驟之後，請移至此階段的[允出準則](infoprotect-exit-criteria.md)，以確定您符合 Microsoft 365 企業版的必要與選用條件。</span><span class="sxs-lookup"><span data-stu-id="2c15f-126">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="2c15f-127">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="2c15f-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2c15f-128">了解 Microsoft 的 IT 專家如何使用[Azure 資訊保護和保護資料安全](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9)。</span><span class="sxs-lookup"><span data-stu-id="2c15f-128">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="2c15f-129">Contoso 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="2c15f-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2c15f-130">請參閱 Contoso Corporation (虛構但有代表性的跨國企業) 如何使用 Microsoft 365 雲端服務[實作資訊保護](contoso-info-protect.md)。</span><span class="sxs-lookup"><span data-stu-id="2c15f-130">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![Contoso 公司](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="2c15f-132">下一步</span><span class="sxs-lookup"><span data-stu-id="2c15f-132">Next step</span></span>

|||
|:-------|:-----|
|![步驟 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="2c15f-134">定義安全性和資訊保護層級</span><span class="sxs-lookup"><span data-stu-id="2c15f-134">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

