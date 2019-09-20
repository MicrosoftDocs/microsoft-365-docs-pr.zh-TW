---
title: 步驟 1：定義安全性和資訊保護層級
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
description: 了解並設定您組織的安全性和資訊保護層級。
ms.openlocfilehash: a216079e38b173a8b35c49317a072975b0c7f36e
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047256"
---
# <a name="step-1-define-security-and-information-protection-levels"></a><span data-ttu-id="2e287-103">步驟 1：定義安全性和資訊保護層級</span><span class="sxs-lookup"><span data-stu-id="2e287-103">Step 1: Define security and information protection levels</span></span>

<span data-ttu-id="2e287-104">*這是必要步驟，且同時適用於 Microsoft 365 企業版 E3 與 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="2e287-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="2e287-105">在此步驟中，您會為組織定義安全性與保護層級。</span><span class="sxs-lookup"><span data-stu-id="2e287-105">In this step, you'll define the levels of security and protection for your organization.</span></span> <span data-ttu-id="2e287-106">例如，銷售部門可能只需要較低的安全性層級。</span><span class="sxs-lookup"><span data-stu-id="2e287-106">For example, your sales department might only require a low security level.</span></span> <span data-ttu-id="2e287-107">不過，您的研究部門與其高價值的智慧財產權可能需要高安全性層級，以便加密檔案並將存取權限制在僅供研究人員使用。</span><span class="sxs-lookup"><span data-stu-id="2e287-107">However, your research department and its highly valuable intellectual property might require a high security level that encrypts files and limits access to only research staff.</span></span>

<span data-ttu-id="2e287-108">雖然您可以定義自己的安全性層級且可能已有定義好的層級，Microsoft 建議您開發計劃，以使用至少三個不同的可套用的安全性與保護層級。</span><span class="sxs-lookup"><span data-stu-id="2e287-108">Although you can define your own security levels and might already have some in place, Microsoft recommends that you develop a plan to use at least three different levels of security and protection that can be applied.</span></span> <span data-ttu-id="2e287-109">以下清單可協助您快速上手：</span><span class="sxs-lookup"><span data-stu-id="2e287-109">Here is a list to get you started:</span></span> 

- <span data-ttu-id="2e287-p103">**基準線：** 此為保護資料的最低標準，適用於存取您資料的身分識別與裝置。您可以遵循基準線安全性與保護建議來提供最強的預設保護，此預設保護符合許多組織或其部門的需求。</span><span class="sxs-lookup"><span data-stu-id="2e287-p103">**Baseline:** This is a minimum standard for protecting data and for the identities and devices that access your data. You can follow baseline security and protection recommendations to provide strong default protection that meets the needs of many organizations or their departments.</span></span>
- <span data-ttu-id="2e287-p104">**敏感性：** 此為對您資料子集的額外保護，該資料的保護層級必須大於基準線。您可以將此提高的保護套用至 Office 365 環境中特定的資料集。Microsoft 也建議將敏感安全性層級套用至會存取敏感資料的身分識別和裝置。</span><span class="sxs-lookup"><span data-stu-id="2e287-p104">**Sensitive:** This is additional protection for a subset of your data that must be protected beyond the baseline level. You can apply this increased protection to specific data sets in your Office 365 environment. Microsoft also recommends applying the sensitive security level to identities and devices that access sensitive data.</span></span>
- <span data-ttu-id="2e287-p105">**高管制：** 這是最高層級的保護，適用於通常有少量高機密資料、受重視的智慧財產權或商業機密或必須遵守嚴格之安全性法規的資料。Microsoft 365 企業版能夠協助組織符合這些高安全性需求 (包括對身分識別與裝置的對等保護)。</span><span class="sxs-lookup"><span data-stu-id="2e287-p105">**Highly regulated:** This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span>

<span data-ttu-id="2e287-117">如需詳細資訊，請參閱[三層的保護](microsoft-365-policies-configurations.md#three-tiers-of-protection)。</span><span class="sxs-lookup"><span data-stu-id="2e287-117">For more information, see [Three tiers of protection](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span></span>

<span data-ttu-id="2e287-118">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step1)。</span><span class="sxs-lookup"><span data-stu-id="2e287-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2e287-119">下一步</span><span class="sxs-lookup"><span data-stu-id="2e287-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="2e287-120">設定環境的分類</span><span class="sxs-lookup"><span data-stu-id="2e287-120">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
