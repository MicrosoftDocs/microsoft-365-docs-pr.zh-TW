---
title: 金融業資訊系統中心 (FISC)
description: Microsoft 符合日本金融業資訊系統第 8 版標準的需求。
keywords: Microsoft 365, 合規性, 方案
localization_priority: Priority
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
ms.openlocfilehash: 546e4b29f26ffdee8c876032fe83254fb5643fff
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602380"
---
# <a name="center-for-financial-industry-information-systems-fisc"></a><span data-ttu-id="c7f8b-104">金融業資訊系統中心 (FISC)</span><span class="sxs-lookup"><span data-stu-id="c7f8b-104">Center for Financial Industry Information Systems (FISC)</span></span>

## <a name="fisc-overview"></a><span data-ttu-id="c7f8b-105">FISC 概觀</span><span class="sxs-lookup"><span data-stu-id="c7f8b-105">FISC overview</span></span>

<span data-ttu-id="c7f8b-106">金融業資訊系統中心 (FISC) 是由日本財務省於 1984 年成立的非營利組織，旨在提升日本銀行電腦系統的安全性。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-106">The Center for Financial Industry Information Systems (FISC) is a not-for-profit organization established by the Japanese Ministry of Finance in 1984 to promote security in banking computer systems in Japan.</span></span> <span data-ttu-id="c7f8b-107">日本大約有 700 家公司支持此組織，包括主要的金融機構、保險和信貸公司、證券公司、電腦製造商和電信企業。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-107">Some 700 corporations in Japan are supporting members, including major financial institutions, insurance and credit companies, securities firms, computer manufacturers, and telecommunications enterprises.</span></span>

<span data-ttu-id="c7f8b-108">FISC 與其成員機構、日本銀行和金融服務局 (負責監督日本銀行、證券和交易，以及保險的政府組織) 合作，制定了銀行資訊系統安全性的準則。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-108">In collaboration with its member institutions, the Bank of Japan, and the Financial Services Agency (a government organization responsible for overseeing banking, securities and exchange, and insurance in Japan), the FISC created guidelines for the security of banking information systems.</span></span> <span data-ttu-id="c7f8b-109">其中包括適用於電腦系統控制的基本稽核標準、發生重大災難時的應急規劃，以及開發內含超過 300 個控制的安全性原則和標準。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-109">These include basic auditing standards for computer system controls, contingency planning in the event of a disaster, and the development of security policies and standards encompassed in more than 300 controls.</span></span>

<span data-ttu-id="c7f8b-110">雖然法規沒有要求在雲端運算環境中應用這些準則，但是日本大多數實作雲端服務的金融機構已建立了符合這些安全性標準的資訊系統，並且難以證明與它們相背離。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-110">Although the application of these guidelines in a cloud computing environment is not required by regulation, most financial institutions in Japan that implement cloud services have built information systems that satisfy these security standards, and it can be difficult to justify diverging from them.</span></span> <span data-ttu-id="c7f8b-111">(2015 年發布的最新準則第 8 版補充修訂版增加了兩個修訂版，涉及金融機構對雲端服務的使用，以及針對網絡攻擊的對策。)</span><span class="sxs-lookup"><span data-stu-id="c7f8b-111">(The latest guidelines, Version 8 Supplemental Revised, issued in 2015, added two revisions relating to the use of cloud services by financial institutions and countermeasures against cyberattack.)</span></span>

<span data-ttu-id="c7f8b-112">法規不要求符合此架構，並且未經 FISC 稽核或驗證。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-112">Conformance with this framework is not required by regulation, and not audited or otherwise validated by the FISC.</span></span>

## <a name="microsoft-and-fisc"></a><span data-ttu-id="c7f8b-113">Microsoft 和 FISC</span><span class="sxs-lookup"><span data-stu-id="c7f8b-113">Microsoft and FISC</span></span>

<span data-ttu-id="c7f8b-114">Microsoft 已聘雇外部評估員來驗證 Microsoft Azure、Dynamics 365 和 Microsoft Office 365 是否符合 FISC 金融機構電腦系統安全性準則第 9 版修訂版的需求。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-114">Microsoft engaged outside assessors to validate that Microsoft Azure, Dynamics 365, and Microsoft Office 365 meet requirements of the FISC Security Guidelines on Computer Systems for Financial Institutions 9th Edition Revised.</span></span> <span data-ttu-id="c7f8b-115">Microsoft 已在下列每一個區域提供合規性證據：</span><span class="sxs-lookup"><span data-stu-id="c7f8b-115">Microsoft provided evidence of compliance in each of the following areas:</span></span>

- <span data-ttu-id="c7f8b-116">建築物和電腦機房、電源、空調、資料中心和設施監視的資料中心準則。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-116">Datacenter guidelines for buildings and computer rooms, power, air conditioning, datacenter, and facilities monitoring.</span></span>
- <span data-ttu-id="c7f8b-117">組織、訓練、存取控制、系統開發和稽核的操作準則。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-117">Operational guidelines for organizations, training, access control, system development, and auditing.</span></span>
- <span data-ttu-id="c7f8b-118">改善硬體和軟體可靠性，以及防範安全風險 (包括資料保護、防範未經授權的使用、威脅偵測，以及災難復原) 的措施技術準則。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-118">Technical guidelines for measures to improve the reliability of hardware and software, and for countermeasures against security risks including data protection, prevention against unauthorized use, threat detection, and disaster recovery.</span></span>

<span data-ttu-id="c7f8b-119">金融機構可以依賴下列評估：評估 Azure、Dynamics 365、Office 365 和 Microsoft Cloud App Security 的範圍內基礎架構和平台服務是否符合這三個區域。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-119">Financial institutions can rely on this evaluation of the compliance of these three areas for the in-scope infrastructure and platform services of Azure, Dynamics 365, Office 365, and Microsoft Cloud App Security.</span></span>

<span data-ttu-id="c7f8b-120">[深入了解外部評定者和評定者網站連結的驗證 (僅提供日文)](https://cloudblogs.microsoft.com/industry-blog/ja-jp/financial-services/2018/05/11/fisc_v9/)。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-120">[Learn more about validation of external assessors and links to assessor’s sites (Japanese Only](https://cloudblogs.microsoft.com/industry-blog/ja-jp/financial-services/2018/05/11/fisc_v9/).</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="c7f8b-121">Microsoft 範圍內雲端服務</span><span class="sxs-lookup"><span data-stu-id="c7f8b-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="c7f8b-122">Azure</span><span class="sxs-lookup"><span data-stu-id="c7f8b-122">Azure</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="c7f8b-123">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c7f8b-123">Cloud App Security</span></span>
- <span data-ttu-id="c7f8b-124">Intune</span><span class="sxs-lookup"><span data-stu-id="c7f8b-124">Intune</span></span>
- [<span data-ttu-id="c7f8b-125">Office 365</span><span class="sxs-lookup"><span data-stu-id="c7f8b-125">Office 365</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="c7f8b-126">Power BI 雲端服務可作為獨立服務或包含在 Office 365 品牌方案或套件中</span><span class="sxs-lookup"><span data-stu-id="c7f8b-126">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c7f8b-127">常見問題集</span><span class="sxs-lookup"><span data-stu-id="c7f8b-127">Frequently asked questions</span></span>

<span data-ttu-id="c7f8b-128">**誰適用 FISC 準則？**</span><span class="sxs-lookup"><span data-stu-id="c7f8b-128">**To whom do the FISC guidelines apply?**</span></span>

<span data-ttu-id="c7f8b-129">日本的銀行和其他金融機構若要驗證其在系統安全性、可靠性和稽核方面的方法，並與日本已建立的最佳做法保持一致，請遵循 FISC 準則。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-129">Banks and other financial institutions in Japan that want to validate their approach to system security, reliability, and auditing, and align with established best practices in Japan, follow the FISC guidelines.</span></span>

<span data-ttu-id="c7f8b-130">**哪裡可以取得第 8 版 FISC 需求的詳細資訊？**</span><span class="sxs-lookup"><span data-stu-id="c7f8b-130">**Where can I get more information on Version 8 of the FISC requirements?**</span></span>

<span data-ttu-id="c7f8b-131">FISC 已發佈兩份來自其專家委員會的報告：</span><span class="sxs-lookup"><span data-stu-id="c7f8b-131">The FISC has published two reports from its Council of Experts:</span></span>

- [<span data-ttu-id="c7f8b-132">金融機構使用雲端運算的情況</span><span class="sxs-lookup"><span data-stu-id="c7f8b-132">Usage of Cloud Computing by Financial Institutions</span></span>](https://aka.ms/cloud-computing-report-en)
- [<span data-ttu-id="c7f8b-133">金融機構防範網路攻擊的對策</span><span class="sxs-lookup"><span data-stu-id="c7f8b-133">Countermeasures Against Cyber Attacks on Financial Institutions</span></span>](https://aka.ms/cyberattack-counter)

<span data-ttu-id="c7f8b-134">**哪裡可以取得 Microsoft 回應 FISC 架構的詳細資料？**</span><span class="sxs-lookup"><span data-stu-id="c7f8b-134">**Where can I get the details of Microsoft's responses to the FISC framework?**</span></span>

<span data-ttu-id="c7f8b-135">您也可以參閱安全性參考 ([日文版](https://aka.ms/microsoftresponsetofiscguidancejapanese))，這是已評估 Microsoft 雲端服務是否符合 FISC 的協力廠商所提供。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-135">You can also see security references ([in Japanese](https://aka.ms/microsoftresponsetofiscguidancejapanese)) from third parties who have evaluated the FISC compliance of Microsoft cloud services.</span></span>

<span data-ttu-id="c7f8b-136">**我是否可以在組織的資格程序中使用 Microsoft 對此架構的回應？**</span><span class="sxs-lookup"><span data-stu-id="c7f8b-136">**Can I use Microsoft’s responses to this framework in my organization’s qualification process?**</span></span>

<span data-ttu-id="c7f8b-137">是。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-137">Yes.</span></span> <span data-ttu-id="c7f8b-138">不過，雖然 Microsoft 對此架構的回應是由協力廠商確認，但客戶負責驗證其已在 Azure 或 Office 365 上實作的解決方案合規性。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-138">However, although Microsoft responses to this framework are confirmed compliant by third parties, customers are responsible for validating the compliance of solutions they have implemented on Azure or Office 365.</span></span>

## <a name="resources"></a><span data-ttu-id="c7f8b-139">資源</span><span class="sxs-lookup"><span data-stu-id="c7f8b-139">Resources</span></span>

- [<span data-ttu-id="c7f8b-140">Microsoft Online Services 條款</span><span class="sxs-lookup"><span data-stu-id="c7f8b-140">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="c7f8b-141">FISC 安全性準則/安全標準</span><span class="sxs-lookup"><span data-stu-id="c7f8b-141">FISC Security Guidelines/Safety Standards</span></span>](https://www.fisc.or.jp/english)
- [<span data-ttu-id="c7f8b-142">有關使用雲端運算的 FISC 報告</span><span class="sxs-lookup"><span data-stu-id="c7f8b-142">FISC Report on Usage of Cloud Computing</span></span>](https://aka.ms/cloud-computing-report-en)
- [<span data-ttu-id="c7f8b-143">Microsoft 信任中心的合規性</span><span class="sxs-lookup"><span data-stu-id="c7f8b-143">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="resources-in-japanese"></a><span data-ttu-id="c7f8b-144">日本的資源</span><span class="sxs-lookup"><span data-stu-id="c7f8b-144">Resources in Japanese</span></span>

- [<span data-ttu-id="c7f8b-145">FISC</span><span class="sxs-lookup"><span data-stu-id="c7f8b-145">FISC</span></span>](https://www.fisc.or.jp/)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="c7f8b-146">下載方案背景資料</span><span class="sxs-lookup"><span data-stu-id="c7f8b-146">Download the offering backgrounder</span></span>

<span data-ttu-id="c7f8b-147">是否需要此方案的背景資料文件？</span><span class="sxs-lookup"><span data-stu-id="c7f8b-147">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="c7f8b-148">下載 [PDF](https://download.microsoft.com/download/9/1/D/91D74F03-AA26-4D22-AB99-576FE9F88B58/FISC-Compliance.pdf)。</span><span class="sxs-lookup"><span data-stu-id="c7f8b-148">Download the [PDF](https://download.microsoft.com/download/9/1/D/91D74F03-AA26-4D22-AB99-576FE9F88B58/FISC-Compliance.pdf).</span></span>
