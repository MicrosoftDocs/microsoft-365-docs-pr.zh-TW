---
title: 階段 6：資訊保護
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/01/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 企業版的資訊保護基礎結構部署步驟。
ms.openlocfilehash: a0d2c485b05e0969fe45cfd79c86e4e7dcb1d5ff
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33399997"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="bba99-103">階段 6：資訊保護</span><span class="sxs-lookup"><span data-stu-id="bba99-103">Phase 6: Information protection</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="bba99-p101">資訊保護是定義如何傳送、儲存及處理機密資訊的一組原則和技術。在階段 6 中，您會逐步執行 Microsoft 365 企業版的資訊保護設定及功能，可協助您保護雲端式工作負載和案例的資料。</span><span class="sxs-lookup"><span data-stu-id="bba99-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="bba99-106">如果您已部署資訊保護，請參閱此階段的[允出準則](infoprotect-exit-criteria.md)，確保其符合 Microsoft 365 企業版的必要與選用條件。</span><span class="sxs-lookup"><span data-stu-id="bba99-106">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="bba99-107">規劃及部署 Microsoft 365 企業版資訊保護基礎結構</span><span class="sxs-lookup"><span data-stu-id="bba99-107">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="bba99-p102">請務必諮詢法律和法規遵循團隊，判斷貴組織是否需符合規範標準，例如 HIPPA、CJIS 或 GDPR。您也應與安全性群組合作，以判斷您的組織以及需要額外安全性之部門或群組的資訊保護目標。</span><span class="sxs-lookup"><span data-stu-id="bba99-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="bba99-110">接下來，請使用下列步驟建立 Microsoft 365 企業版的資訊保護。</span><span class="sxs-lookup"><span data-stu-id="bba99-110">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="bba99-111">定義安全性和資訊保護層級</span><span class="sxs-lookup"><span data-stu-id="bba99-111">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="bba99-112">設定環境的分類</span><span class="sxs-lookup"><span data-stu-id="bba99-112">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="bba99-113">設定增強的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="bba99-113">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![](./media/stepnumbers/Step4.png)|<span data-ttu-id="bba99-114">[設定 Windows 資訊保護](infoprotect-deploy-windows-information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="bba99-114">[](infoprotect-deploy-windows-information-protection.md)Configure Azure Information Protection</span></span>|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="bba99-115">設定 Office 365 資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="bba99-115">Office 365 Data Loss Prevention (DLP)</span></span>](infoprotect-data-loss-prevention.md)|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="bba99-116">設定 Office 365 的特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="bba99-116">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|


<span data-ttu-id="bba99-117">完成這些步驟之後，請移至此階段的[允出準則](infoprotect-exit-criteria.md)，以確定您符合 Microsoft 365 企業版的必要與選用條件。</span><span class="sxs-lookup"><span data-stu-id="bba99-117">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="bba99-118">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="bba99-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="bba99-119">了解 Microsoft IT 專家如何使用 Microsoft 365 企業版的資訊保護功能來保護資訊及防禦網路攻擊：</span><span class="sxs-lookup"><span data-stu-id="bba99-119">Learn how IT experts at Microsoft use the information protection capabilities of Microsoft 356 Enterprise to protect information and defend against cyber attacks:</span></span>

- [<span data-ttu-id="bba99-120">使用 Azure 資訊保護來保護雲端的檔案</span><span class="sxs-lookup"><span data-stu-id="bba99-120">Protecting files in the cloud with Azure Information Protection</span></span>](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection)
- [<span data-ttu-id="bba99-121">Microsoft 會使用威脅情報來保護、偵測及回應威脅</span><span class="sxs-lookup"><span data-stu-id="bba99-121">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="bba99-122">Microsoft 會使用 Office 365 來阻撓網路釣魚嘗試</span><span class="sxs-lookup"><span data-stu-id="bba99-122">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="bba99-123">Contoso 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="bba99-123">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="bba99-124">請參閱 Contoso Corporation (虛構但有代表性的跨國企業) 如何使用 Microsoft 365 雲端服務[實作資訊保護](contoso-info-protect.md)。</span><span class="sxs-lookup"><span data-stu-id="bba99-124">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="bba99-125">下一步</span><span class="sxs-lookup"><span data-stu-id="bba99-125">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="bba99-126">定義安全性和資訊保護層級</span><span class="sxs-lookup"><span data-stu-id="bba99-126">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

