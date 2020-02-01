---
title: 刑事案件正義資訊服務 (CJIS) 安全性原則
description: Microsoft 政府雲端服務遵守美國司法正義資訊 Services 安全性原則。
keywords: Microsoft 365, 合規性, 方案
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 97f769b763b5698dd664dee4ae8659999a62b078
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602610"
---
# <a name="criminal-justice-information-services-cjis-security-policy"></a><span data-ttu-id="f9e13-104">刑事案件正義資訊服務 (CJIS) 安全性原則</span><span class="sxs-lookup"><span data-stu-id="f9e13-104">Criminal Justice Information Services (CJIS) Security Policy</span></span>

## <a name="cjis-overview"></a><span data-ttu-id="f9e13-105">CJIS 概觀</span><span class="sxs-lookup"><span data-stu-id="f9e13-105">CJIS overview</span></span>

<span data-ttu-id="f9e13-106">司法正義資訊服務 (CJIS) 部門的美國聯邦機構的調查 (FBI) 提供狀態，本機、 和聯邦法律強制執行和司法正義行政機關存取司法正義資訊 (CJI) — 例如，指紋記錄及刑事案件的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="f9e13-106">The Criminal Justice Information Services (CJIS) Division of the US Federal Bureau of Investigation (FBI) gives state, local, and federal law enforcement and criminal justice agencies access to criminal justice information (CJI) — for example, fingerprint records and criminal histories.</span></span> <span data-ttu-id="f9e13-107">執法機構及其他政府機關美國，必須確定他們在使用雲端服務的傳輸、 儲存或處理 CJI 遵守[CJIS 安全性原則](https://aka.ms/cjis-security-policy)，它會建立最小的安全性需求，並且控制以保護 CJI。</span><span class="sxs-lookup"><span data-stu-id="f9e13-107">Law enforcement and other government agencies in the United States must ensure that their use of cloud services for the transmission, storage, or processing of CJI complies with the [CJIS Security Policy](https://aka.ms/cjis-security-policy), which establishes minimum security requirements and controls to safeguard CJI.</span></span>

<span data-ttu-id="f9e13-108">CJIS 安全性原則整合總統並 FBI 指示詞、 聯邦法律和司法正義諮詢原則委員會社群的決定，以及從國家標準與技術 (NIST) 的指引。</span><span class="sxs-lookup"><span data-stu-id="f9e13-108">The CJIS Security Policy integrates presidential and FBI directives, federal laws, and the criminal justice community’s Advisory Policy Board decisions, along with guidance from the National Institute of Standards and Technology (NIST).</span></span> <span data-ttu-id="f9e13-109">原則會定期更新以反映不斷變化的安全性需求。</span><span class="sxs-lookup"><span data-stu-id="f9e13-109">The Policy is periodically updated to reflect evolving security requirements.</span></span>

<span data-ttu-id="f9e13-110">CJIS 安全性原則定義 13 領域，例如雲端服務提供者的私用承包商必須評估為判斷如果他們在使用雲端服務可為與 CJIS 要求的一致。</span><span class="sxs-lookup"><span data-stu-id="f9e13-110">The CJIS Security Policy defines 13 areas that private contractors such as cloud service providers must evaluate to determine if their use of cloud services can be consistent with CJIS requirements.</span></span> <span data-ttu-id="f9e13-111">這些區域會密切對應至 NIST 800-53、 也是 「 聯邦風險與授權管理計劃 ([FedRAMP](offering-FedRAMP.md))，在其下 Microsoft 已經認證其政府雲端供應項目的程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="f9e13-111">These areas correspond closely to NIST 800-53, which is also the basis for the Federal Risk and Authorization Management Program ([FedRAMP](offering-FedRAMP.md)), a program under which Microsoft has been certified for its Government Cloud offerings.</span></span>

<span data-ttu-id="f9e13-112">此外，所有的私用承包商處理 CJI 必須登入 CJIS 安全性增訂版，可協助確保安全性和 CJI 安全性原則所需的機密性美國律師一般由核准統一合約。</span><span class="sxs-lookup"><span data-stu-id="f9e13-112">In addition, all private contractors who process CJI must sign the CJIS Security Addendum, a uniform agreement approved by the US Attorney General that helps ensure the security and confidentiality of CJI required by the Security Policy.</span></span> <span data-ttu-id="f9e13-113">它也認可承包商維護安全性計劃一致的聯邦與州法律、 法規和標準，而且會限制的政府機構提供其用途的 CJI 使用。</span><span class="sxs-lookup"><span data-stu-id="f9e13-113">It also commits the contractor to maintaining a security program consistent with federal and state laws, regulations, and standards, and limits the use of CJI to the purposes for which a government agency provided it.</span></span>

## <a name="microsoft-and-cjis-security-policy"></a><span data-ttu-id="f9e13-114">Microsoft 和 CJIS 安全性原則</span><span class="sxs-lookup"><span data-stu-id="f9e13-114">Microsoft and CJIS Security Policy</span></span>

<span data-ttu-id="f9e13-115">Microsoft 簽署 CJIS 安全性增補狀態與 CJIS 資訊協議。</span><span class="sxs-lookup"><span data-stu-id="f9e13-115">Microsoft signs the CJIS Security Addendum in states with CJIS Information Agreements.</span></span> <span data-ttu-id="f9e13-116">這些告訴狀態法律執法機構負責 Microsoft 的雲端安全性措施如何協助保護資料的完整生命週期，並確保操作人員存取的適當背景檢測 CJIS 安全性原則與合規性CJI。</span><span class="sxs-lookup"><span data-stu-id="f9e13-116">These tell state law enforcement authorities responsible for compliance with CJIS Security Policy how Microsoft's cloud security controls help protect the full lifecycle of data and ensure appropriate background screening of operating personnel with access to CJI.</span></span> <span data-ttu-id="f9e13-117">Microsoft 會繼續使用 state 政府 CJIS 資訊協議中輸入。</span><span class="sxs-lookup"><span data-stu-id="f9e13-117">Microsoft continues to work with state governments to enter into CJIS Information Agreements.</span></span>

<span data-ttu-id="f9e13-118">Microsoft 已評估的操作原則和程序的 Microsoft Azure 政府版、 Microsoft Office 365 US Government 和 Microsoft Dynamics 365 美國政府版，並將其能力足以滿足 FBI 適用的服務協議中範圍內的服務使用的需求。</span><span class="sxs-lookup"><span data-stu-id="f9e13-118">Microsoft has assessed the operational policies and procedures of Microsoft Azure Government, Microsoft Office 365 U.S. Government, and Microsoft Dynamics 365 U.S. Government, and will attest to their ability in the applicable services agreements to meet FBI requirements for the use of in-scope services.</span></span>

<span data-ttu-id="f9e13-119">了解 Microsoft Cloud CJIS 安全性原則的優點：[閱讀如何 Genetec 清除刑事案件調查](https://customers.microsoft.com/story/genetec)</span><span class="sxs-lookup"><span data-stu-id="f9e13-119">Learn about the benefits of CJIS Security policy on the Microsoft Cloud: [Read how Genetec cleared criminal investigations](https://customers.microsoft.com/story/genetec)</span></span>

<span data-ttu-id="f9e13-120">了解如何開始加速 CJIS 安全性原則，與我們的 Azure 安全性與合規性藍圖：[下載 Microsoft 政府雲端服務的 CJIS 實作指導方針](https://gallery.technet.microsoft.com/CJIS-Implementation-62af7c27)</span><span class="sxs-lookup"><span data-stu-id="f9e13-120">Learn how to accelerate your CJIS Security policy with our Azure Security and Compliance Blueprint: [Download the CJIS implementation guidelines for Microsoft Government Cloud Services](https://gallery.technet.microsoft.com/CJIS-Implementation-62af7c27)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="f9e13-121">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="f9e13-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="f9e13-122">Azure 政府版</span><span class="sxs-lookup"><span data-stu-id="f9e13-122">Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="f9e13-123">Dynamics 365 美國政府版</span><span class="sxs-lookup"><span data-stu-id="f9e13-123">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- [<span data-ttu-id="f9e13-124">Office 365 US Government</span><span class="sxs-lookup"><span data-stu-id="f9e13-124">Office 365 U.S. Government</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="f9e13-125">Power BI 雲端服務，以獨立服務形式提供或包含在 Office 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="f9e13-125">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="f9e13-126">稽核、報告和認證</span><span class="sxs-lookup"><span data-stu-id="f9e13-126">Audits, reports, and certificates</span></span>

<span data-ttu-id="f9e13-127">FBI 並不提供的 Microsoft 合規性 CJIS 要求的憑證。</span><span class="sxs-lookup"><span data-stu-id="f9e13-127">The FBI does not offer certification of Microsoft compliance with CJIS requirements.</span></span> <span data-ttu-id="f9e13-128">相反地，Microsoft 證明隨附於 Microsoft 和狀態 CJIS 授權，以及之間 Microsoft 和其客戶之間的合約。</span><span class="sxs-lookup"><span data-stu-id="f9e13-128">Instead, a Microsoft attestation is included in agreements between Microsoft and a state’s CJIS authority, and between Microsoft and its customers.</span></span>

[<span data-ttu-id="f9e13-129">Microsoft CJIS 雲端需求</span><span class="sxs-lookup"><span data-stu-id="f9e13-129">Microsoft CJIS Cloud Requirements</span></span>](https://aka.ms/MicrosoftCJISCloudRequirements)

## <a name="cjis-status-in-the-united-states-current-as-of-9232019"></a><span data-ttu-id="f9e13-130">CJIS 狀態美國 （目前截至 9/23/2019年）</span><span class="sxs-lookup"><span data-stu-id="f9e13-130">CJIS status in the United States (current as of 9/23/2019)</span></span>

<span data-ttu-id="f9e13-131">37 狀態和管理協議，反白顯示以綠色標示在地圖上與學的哥倫比亞包括：</span><span class="sxs-lookup"><span data-stu-id="f9e13-131">37 states and the District of Columbia with management agreements, highlighted on the map in green include:</span></span>

<span data-ttu-id="f9e13-132">Alabama、 阿拉斯加、 Arkansas、 亞歷桑那、 加利福尼亞、 哪、 佛羅里達州、 Georgia、 夏威夷、 伊利諾、 印地安那、 稍後、 堪薩斯、 肯塔基、 Maine、 Massachusetts、 密西根、 明尼蘇達、 台、 Montana、 紐澤西、 New York，Nevada，North 羅來那州、 奧克拉荷馬，Oregon，賓州羅德島、 南羅來那州、 美國、 德州、 猶他、 Vermont、 維吉尼亞州、 Washington，Washington D.C.，西維吉尼亞州，威斯康辛。</span><span class="sxs-lookup"><span data-stu-id="f9e13-132">Alabama, Alaska, Arkansas, Arizona, California, Colorado, Florida, Georgia, Hawaii, Illinois, Indiana, Iowa, Kansas, Kentucky, Maine, Massachusetts, Michigan, Minnesota, Missouri, Montana, New Jersey, New York, Nevada, North Carolina, Oklahoma, Oregon, Pennsylvania, Rhode Island, South Carolina, Tennessee, Texas, Utah, Vermont, Virginia, Washington, Washington D.C., West Virginia, Wisconsin.</span></span>

<span data-ttu-id="f9e13-133">Microsoft 的承諾會議的適用的 CJIS 法規的控制項可讓司法正義組織實作雲端式解決方案，並與 CJIS 安全性原則 V5.8 相容。</span><span class="sxs-lookup"><span data-stu-id="f9e13-133">Microsoft's commitment to meeting the applicable CJIS regulatory controls allows Criminal Justice organizations to implement cloud-based solutions and be compliant with CJIS Security Policy V5.8.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f9e13-134">常見問題集</span><span class="sxs-lookup"><span data-stu-id="f9e13-134">Frequently asked questions</span></span>

<span data-ttu-id="f9e13-135">**其中要求合規性資訊？**</span><span class="sxs-lookup"><span data-stu-id="f9e13-135">**Where can I request compliance information?**</span></span>

<span data-ttu-id="f9e13-136">請連絡您的 Microsoft 帳戶代表資訊管轄您感興趣的。</span><span class="sxs-lookup"><span data-stu-id="f9e13-136">Contact your Microsoft account representative for information on the jurisdiction you are interested in.</span></span> <span data-ttu-id="f9e13-137">連絡人<cjis@microsoft.com>所在的服務目前中可用的狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="f9e13-137">Contact <cjis@microsoft.com> for information on which services are currently available in which states.</span></span>

<span data-ttu-id="f9e13-138">**Microsoft 如何示範其雲端服務啟用我的狀態需求的規範？**</span><span class="sxs-lookup"><span data-stu-id="f9e13-138">**How does Microsoft demonstrate that its cloud services enable compliance with my state’s requirements?**</span></span>

<span data-ttu-id="f9e13-139">Microsoft 簽署資訊合約，具有狀態 CJIS 系統機構 (CSA);您可能會從您的狀態 CSA 要求複本。</span><span class="sxs-lookup"><span data-stu-id="f9e13-139">Microsoft signs an Information Agreement with a state CJIS Systems Agency (CSA); you may request a copy from your state’s CSA.</span></span> <span data-ttu-id="f9e13-140">此外，Microsoft 會提供客戶深入的安全性、 隱私權和規範資訊。</span><span class="sxs-lookup"><span data-stu-id="f9e13-140">In addition, Microsoft provides customers with in-depth security, privacy, and compliance information.</span></span> <span data-ttu-id="f9e13-141">客戶也可以檢閱安全性及規範符合性報告備妥由獨立稽核員讓他們可以驗證 Microsoft 已實作適當的相關的稽核範圍 （例如 ISO 27001) 安全性控制。</span><span class="sxs-lookup"><span data-stu-id="f9e13-141">Customers may also review security and compliance reports prepared by independent auditors so they can validate that Microsoft has implemented security controls (such as ISO 27001) appropriate to the relevant audit scope.</span></span>

<span data-ttu-id="f9e13-142">**其中開頭我機構合規性努力？**</span><span class="sxs-lookup"><span data-stu-id="f9e13-142">**Where do I start with my agency’s compliance effort?**</span></span>

<span data-ttu-id="f9e13-143">[CJIS 安全性原則](https://aka.ms/cjis-security-policy)所涵蓋您機構必須保護 CJI 採取預防措施。</span><span class="sxs-lookup"><span data-stu-id="f9e13-143">[CJIS Security Policy](https://aka.ms/cjis-security-policy) covers the precautions that your agency must take to protect CJI.</span></span> <span data-ttu-id="f9e13-144">此外，您的 Microsoft 帳戶代表可以放您聯繫熟悉您管轄的需求</span><span class="sxs-lookup"><span data-stu-id="f9e13-144">In addition, your Microsoft account representative can put you in touch with those familiar with the requirements of your jurisdiction</span></span>

## <a name="resources"></a><span data-ttu-id="f9e13-145">資源</span><span class="sxs-lookup"><span data-stu-id="f9e13-145">Resources</span></span>

- [<span data-ttu-id="f9e13-146">刑事案件正義資訊服務</span><span class="sxs-lookup"><span data-stu-id="f9e13-146">Criminal Justice Information Services</span></span>](https://aka.ms/cjis)
- [<span data-ttu-id="f9e13-147">CJIS 安全性原則</span><span class="sxs-lookup"><span data-stu-id="f9e13-147">CJIS Security Policy</span></span>](https://aka.ms/cjis-security-policy)
- [<span data-ttu-id="f9e13-148">CJIS 安全性原則版本 5.3 背景資料</span><span class="sxs-lookup"><span data-stu-id="f9e13-148">CJIS security policy version 5.3 backgrounder</span></span>](https://aka.ms/cjis-backgrounder)
- [<span data-ttu-id="f9e13-149">CJIS 實作的指導方針 Azure 政府版</span><span class="sxs-lookup"><span data-stu-id="f9e13-149">CJIS implementation guidelines for Azure Government</span></span>](https://aka.ms/cjisimplementationguidelines)
- [<span data-ttu-id="f9e13-150">Microsoft 通用控制措施中樞合規性架構</span><span class="sxs-lookup"><span data-stu-id="f9e13-150">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="f9e13-151">Microsoft 政府雲端</span><span class="sxs-lookup"><span data-stu-id="f9e13-151">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/?linkid=2087246)
- [<span data-ttu-id="f9e13-152">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="f9e13-152">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="f9e13-153">下載方案背景資料</span><span class="sxs-lookup"><span data-stu-id="f9e13-153">Download the offering backgrounder</span></span>

<span data-ttu-id="f9e13-154">是否需要此方案的背景資料文件？</span><span class="sxs-lookup"><span data-stu-id="f9e13-154">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="f9e13-155">下載 [PDF](https://download.microsoft.com/download/4/D/0/4D008840-B8C4-480B-ACD1-D55CB34AD6BC/CJIS_Compliance_Backgrounder.pdf)。</span><span class="sxs-lookup"><span data-stu-id="f9e13-155">Download the [PDF](https://download.microsoft.com/download/4/D/0/4D008840-B8C4-480B-ACD1-D55CB34AD6BC/CJIS_Compliance_Backgrounder.pdf).</span></span>
