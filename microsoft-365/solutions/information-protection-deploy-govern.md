---
title: 管理資料隱私權法規的使用資訊
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 使用 Microsoft 365 保留標籤和原則來管理您的 Microsoft 365 環境中的個人資料。
ms.openlocfilehash: c2a933e556213ae4b78db9dc5f903885df969b27
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377042"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="458c1-103">管理資料隱私權法規的使用資訊</span><span class="sxs-lookup"><span data-stu-id="458c1-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="458c1-104">您可以在您的環境中使用資訊控管控制，以協助滿足資料隱私權符合性需求，包括一般資料保護法規的特定數位 (GDPR) 、HIPAA-高科技 (美國衛生保健隱私權法案) 、加州消費者 Protection 法案 (CCPA) ，以及巴西資料保護法案 (LGPD) 。</span><span class="sxs-lookup"><span data-stu-id="458c1-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="458c1-105">這些控制項主要分為下列解決方案區域：</span><span class="sxs-lookup"><span data-stu-id="458c1-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="458c1-106">保留原則</span><span class="sxs-lookup"><span data-stu-id="458c1-106">Retention policies</span></span>
- <span data-ttu-id="458c1-107">保留標籤</span><span class="sxs-lookup"><span data-stu-id="458c1-107">Retention labels</span></span>
- <span data-ttu-id="458c1-108">記錄管理</span><span class="sxs-lookup"><span data-stu-id="458c1-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="458c1-109">影響資訊管理控制的資料隱私權法規</span><span class="sxs-lookup"><span data-stu-id="458c1-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="458c1-110">以下是可能與資訊管理控制相關之資料隱私權法規的範例清單：</span><span class="sxs-lookup"><span data-stu-id="458c1-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="458c1-111">GDPR 文章 (13) # B2 2) # B4 a) </span><span class="sxs-lookup"><span data-stu-id="458c1-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="458c1-112">GDPR 文章 (5) # B2 1) # B4 f) </span><span class="sxs-lookup"><span data-stu-id="458c1-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="458c1-113">HIPAA-高科技 (45 CFR 164.312 (c) # B3 2) # A5</span><span class="sxs-lookup"><span data-stu-id="458c1-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="458c1-114">HIPAA-高科技 (45 CFR 164.316 (b) # B3 1) # B5 i) # A7</span><span class="sxs-lookup"><span data-stu-id="458c1-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="458c1-115">HIPAA-高科技 (45 CFR 164.316 (b) # B3 1) # B5 ii) # A7</span><span class="sxs-lookup"><span data-stu-id="458c1-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="458c1-116">LGPD 文章46</span><span class="sxs-lookup"><span data-stu-id="458c1-116">LGPD Article 46</span></span>

<span data-ttu-id="458c1-117">如需這些法規的詳細資訊，請參閱 [評估資料隱私權風險及識別敏感資訊文章](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="458c1-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="458c1-118">針對資訊管理，資料隱私權規定一般會呼叫下列各項：</span><span class="sxs-lookup"><span data-stu-id="458c1-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="458c1-119">您應該針對儲存在 Microsoft 365 中的個人資料，使用技術方案進行保留和刪除。</span><span class="sxs-lookup"><span data-stu-id="458c1-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="458c1-120">如果您想要儲存個人資料，請將儲存資料的時間，告知其使用時間，這是前端網頁系統的標準作法。</span><span class="sxs-lookup"><span data-stu-id="458c1-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="458c1-121">個人資料應受到保護，避免意外處理、遺失或篡改使用可驗證的方法。</span><span class="sxs-lookup"><span data-stu-id="458c1-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="458c1-122">應該記錄針對個人資料執行的任何動作，而且檔應保留指定期間內。</span><span class="sxs-lookup"><span data-stu-id="458c1-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="458c1-123">因為資料保密規定是資料保留和刪除的特別不足之處，所以必須考慮其他因素，以規定儲存在 Microsoft 365 訂閱中的個人資訊的資訊控管指導方針。</span><span class="sxs-lookup"><span data-stu-id="458c1-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="458c1-124">以下是一些範例：</span><span class="sxs-lookup"><span data-stu-id="458c1-124">Here are a few examples:</span></span>

- <span data-ttu-id="458c1-125">使用五年後的使用者帳戶，且需要在該點之後刪除或匿名帳戶資料，需要在儲存與通知及其他自動化相關之資料和工作流程的系統之間進行業務流程。</span><span class="sxs-lookup"><span data-stu-id="458c1-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="458c1-126">設定規則，使與 GDPR 相關的原則和程式在已被取代後，以三年為依據，與組織的原則和程式保留排程相符。</span><span class="sxs-lookup"><span data-stu-id="458c1-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="458c1-127">維護個別訂閱，以透過其支援組織與消費者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="458c1-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="458c1-128">所有的電子郵件通訊會在兩周後保留並刪除，以減少系統中的任何隱私權債務。</span><span class="sxs-lookup"><span data-stu-id="458c1-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="458c1-129">要回答的重要問題是：</span><span class="sxs-lookup"><span data-stu-id="458c1-129">A key question to answer is:</span></span> 

- <span data-ttu-id="458c1-130">包含個人資料的資訊必須保留多久，以避免「永遠保留它」做法，以避免有效的商業理由？</span><span class="sxs-lookup"><span data-stu-id="458c1-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="458c1-131">這必須與業務持續性的保留需求平衡。</span><span class="sxs-lookup"><span data-stu-id="458c1-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="458c1-132">不論保留或刪除個人資訊的法律和業務原因為何，Microsoft 都會提供一些功能，以在 Microsoft 365 中實施您的資料管理架構。</span><span class="sxs-lookup"><span data-stu-id="458c1-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="458c1-133">管理 Microsoft 365 中的資訊管理</span><span class="sxs-lookup"><span data-stu-id="458c1-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="458c1-134">若要開始，請參閱管理 Microsoft 365 中的 [資訊](../compliance/manage-information-governance.md) 管理和 [資料保留、刪除和銷毀](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)。</span><span class="sxs-lookup"><span data-stu-id="458c1-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="458c1-135">開發容器、電子郵件和內容的資料保留時間表</span><span class="sxs-lookup"><span data-stu-id="458c1-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="458c1-136">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="458c1-136">Keep the following in mind:</span></span>

- <span data-ttu-id="458c1-137">為定義的資訊類型建立資料保留排程，應視為實施任何保留或刪除配置的必要條件。</span><span class="sxs-lookup"><span data-stu-id="458c1-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="458c1-138">根據大多陣列織認為重要的資訊類型數量，以及與這些類型相關的大型記錄保留排程，實現資料保留及記錄管理原則需要規劃。</span><span class="sxs-lookup"><span data-stu-id="458c1-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="458c1-139">建立這種類型的有效資料控管策略，主要是著重于需要更正式管理的最高優先順序商務功能和資訊類型。</span><span class="sxs-lookup"><span data-stu-id="458c1-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="458c1-140">例如法律合約、金融報表和法規規範檔。</span><span class="sxs-lookup"><span data-stu-id="458c1-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="458c1-141">請嘗試避免每一種單一資訊類型都有個別的保留排程。</span><span class="sxs-lookup"><span data-stu-id="458c1-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="458c1-142">請盡可能盡可能使用一般類別，例如，針對一般商務內容使用7年的保留時間表。</span><span class="sxs-lookup"><span data-stu-id="458c1-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="458c1-143">一旦環境中的個人資訊類型更知名，請建立這種內容類型的保留和刪除排程，並調整您的資訊架構，以簡化這類資訊的管理。</span><span class="sxs-lookup"><span data-stu-id="458c1-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="458c1-144">例如，以可控存取方式隔離個別網站、文件庫或資料夾中的個人資訊。</span><span class="sxs-lookup"><span data-stu-id="458c1-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="458c1-145">保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="458c1-145">Retention policies and retention labels</span></span>

<span data-ttu-id="458c1-146">使用 [保留原則和保留標籤](../compliance/retention.md) ，保留或刪除包含或預計包含個人資料之 Microsoft 365 中的內容。</span><span class="sxs-lookup"><span data-stu-id="458c1-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="458c1-147">記錄管理</span><span class="sxs-lookup"><span data-stu-id="458c1-147">Records management</span></span>

<span data-ttu-id="458c1-148">使用可宣告內容 a 記錄的保留標籤，以對 Microsoft 365 中的資料執行 [記錄管理解決方案](../compliance/records-management.md) 。</span><span class="sxs-lookup"><span data-stu-id="458c1-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="458c1-149">針對資料隱私權，合法系所收到的資料主體要求 (Dsr) 會宣告一筆記錄，而且可以使用大量儲存或處置憑證，以遵守法規活動的保留規格。</span><span class="sxs-lookup"><span data-stu-id="458c1-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>

