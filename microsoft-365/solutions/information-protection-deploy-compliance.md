---
title: 使用合規性管理員管理改進動作
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
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
description: 瞭解如何使用合規性分數和合規性管理員，以提升個人資料的保護層級。
ms.openlocfilehash: f90826795197b392f629eb8eec71b7f27081b697
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791879"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a><span data-ttu-id="898a6-103">使用合規性管理員管理改進動作</span><span class="sxs-lookup"><span data-stu-id="898a6-103">Use Compliance Manager to manage improvement actions</span></span>

<span data-ttu-id="898a6-104">Microsoft 合規性管理員可以協助您管理資料隱私權法規（如歐盟一般資料保護法規）的增強功能（如歐盟 [一般資料保護法規） (GDPR) ](../compliance/gdpr.md)、 [加州消費者 Protection 法案 CCPA) ](../compliance/ccpa-faq.md)、HIPAA-高科技 (美國衛生保健隱私權法案) ，以及巴西資料保護法案 (LGPD) 。</span><span class="sxs-lookup"><span data-stu-id="898a6-104">Microsoft Compliance Manager can help you manage improvements related to data privacy regulations such as the European Union [General Data Protection Regulation (GDPR)](../compliance/gdpr.md), [California Consumer Protection Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (US health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="898a6-105">本文提供有關資料隱私權用途的使用此工具的指導方針。</span><span class="sxs-lookup"><span data-stu-id="898a6-105">This article provides guidance on the use of this tool for data privacy purposes.</span></span>

>[!Note]
><span data-ttu-id="898a6-106">您不應將 [合規性管理員] 提供的建議視為合規性的保證。</span><span class="sxs-lookup"><span data-stu-id="898a6-106">Recommendations from Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="898a6-107">您可以根據法規環境評估和驗證客戶控制措施的效能。</span><span class="sxs-lookup"><span data-stu-id="898a6-107">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="898a6-108">這些服務須遵守 [線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。</span><span class="sxs-lookup"><span data-stu-id="898a6-108">These services are subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="898a6-109">另請參閱 [Microsoft 365 授權指南以取得安全性和合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span><span class="sxs-lookup"><span data-stu-id="898a6-109">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span></span>
>

## <a name="getting-started-with-compliance-manager"></a><span data-ttu-id="898a6-110">合規性管理員快速入門</span><span class="sxs-lookup"><span data-stu-id="898a6-110">Getting started with Compliance Manager</span></span>

#### <a name="what-is-compliance-manager"></a><span data-ttu-id="898a6-111">何謂合規性管理員</span><span class="sxs-lookup"><span data-stu-id="898a6-111">What is Compliance Manager</span></span>

<span data-ttu-id="898a6-112">[合規性管理員](../compliance/compliance-manager.md) 是 microsoft 365 合規性中心的工作流程型風險評估工具，以管理與 Microsoft cloud services 相關的法規遵從性活動。</span><span class="sxs-lookup"><span data-stu-id="898a6-112">[Compliance Manager](../compliance/compliance-manager.md) is a workflow-based risk assessment tool in the Microsoft 365 compliance center for managing regulatory compliance activities related to Microsoft cloud services.</span></span> <span data-ttu-id="898a6-113">在 Microsoft 365 或 Azure Active Directory 的一部分中 (Azure AD) 訂閱，合規性管理員可協助您管理 Microsoft 雲端服務共用責任模型內的法規遵從性。</span><span class="sxs-lookup"><span data-stu-id="898a6-113">As part of your Microsoft 365 or Azure Active Directory (Azure AD) subscription, Compliance Manager helps you manage regulatory compliance within the shared responsibility model for Microsoft cloud services.</span></span>

<span data-ttu-id="898a6-114">**準備好使用評估**</span><span class="sxs-lookup"><span data-stu-id="898a6-114">**Ready to use assessments**</span></span>

<span data-ttu-id="898a6-115">合規性管理員提供預先構建的範本，以建立與資料隱私權相關的法規（如 GDPR 和 HIPAA/高科技）對齊的 [評估](../compliance/compliance-manager-assessments.md) 。</span><span class="sxs-lookup"><span data-stu-id="898a6-115">Compliance Manager provides pre-built templates for [building assessments](../compliance/compliance-manager-assessments.md) that are aligned to data privacy-related regulations, such as GDPR and HIPAA/HITECH.</span></span> <span data-ttu-id="898a6-116">範本具有內建的控制項對應，可協助您採取改進的動作來滿足規定的需求。</span><span class="sxs-lookup"><span data-stu-id="898a6-116">The templates have built-in control mapping to help you take improvement actions for meeting the regulation's requirements.</span></span> <span data-ttu-id="898a6-117">每項評估都提供有關特定于目標服務之每項法規要求的資訊，並由您管理和控制 Microsoft 管理的控制項所中斷。</span><span class="sxs-lookup"><span data-stu-id="898a6-117">Each assessment provides information about the controls each regulation calls for specific to the target service, broken out by controls you manage and controls Microsoft manages.</span></span> 

<span data-ttu-id="898a6-118">使用預先建立的範本可協助您快速開始使用風險評估。</span><span class="sxs-lookup"><span data-stu-id="898a6-118">Using a pre-built template helps you quickly get started with risk assessments.</span></span> <span data-ttu-id="898a6-119">隨著您在使用合規性管理員的熟練程度，您可以透過新增您自己的控制項和改進動作來自訂預先建立的範本，也可以建立您自己的自訂評估，以符合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="898a6-119">As you become more proficient in using Compliance Manager, you can customize a pre-built template by adding your own controls and improvement actions, or you can create your own custom assessments to suit your organization's needs.</span></span>

<span data-ttu-id="898a6-120">查看合規性管理員所提供 [之評估範本的完整清單](../compliance/compliance-manager-templates-list.md) 。</span><span class="sxs-lookup"><span data-stu-id="898a6-120">View the [full list of assessment templates](../compliance/compliance-manager-templates-list.md) provided by Compliance Manager.</span></span>

<span data-ttu-id="898a6-121">**即時合規性分數**</span><span class="sxs-lookup"><span data-stu-id="898a6-121">**Real-time compliance score**</span></span>

<span data-ttu-id="898a6-122">合規性管理員也會為您提供符合性分數，以度量您在控制項中完成建議的改進動作的進度。</span><span class="sxs-lookup"><span data-stu-id="898a6-122">Compliance Manager also provides you with a compliance score that measures your progress in completing recommended improvement actions within controls.</span></span> <span data-ttu-id="898a6-123">您可以使用這個分數來協助監視您的進度，並根據可能降低風險的可能性來排定動作優先順序。</span><span class="sxs-lookup"><span data-stu-id="898a6-123">You can use this score to help monitor your progress and prioritize actions based on their potential to reduce risk.</span></span>

#### <a name="use-the-compliance-manager-quickstart-guide"></a><span data-ttu-id="898a6-124">使用合規性管理員快速入門手冊</span><span class="sxs-lookup"><span data-stu-id="898a6-124">Use the Compliance Manager quickstart guide</span></span>

<span data-ttu-id="898a6-125">[合規性管理員快速入門](../compliance/compliance-manager-quickstart.md)指南提供逐步的步驟和重要資源的連結，以協助您使用合規性管理員：</span><span class="sxs-lookup"><span data-stu-id="898a6-125">The [Compliance Manager quickstart](../compliance/compliance-manager-quickstart.md) guide provides graduated steps and links to key resources to help you work with Compliance Manager:</span></span>

- [<span data-ttu-id="898a6-126">第一次就診：深入瞭解合規性管理員</span><span class="sxs-lookup"><span data-stu-id="898a6-126">First visit: get familiar with Compliance Manager</span></span>](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - <span data-ttu-id="898a6-127">與您的合規性管理員儀表板搭配使用</span><span class="sxs-lookup"><span data-stu-id="898a6-127">Working with your Compliance Manager dashboard</span></span>
    - <span data-ttu-id="898a6-128">瞭解您的合規性分數</span><span class="sxs-lookup"><span data-stu-id="898a6-128">Understanding your compliance score</span></span>
    - <span data-ttu-id="898a6-129">瞭解改進動作</span><span class="sxs-lookup"><span data-stu-id="898a6-129">Learning about improvement actions</span></span>
    - <span data-ttu-id="898a6-130">瞭解評估與範本</span><span class="sxs-lookup"><span data-stu-id="898a6-130">Understanding assessments and templates</span></span>
- [<span data-ttu-id="898a6-131">斜向向上：設定合規性管理員以管理您的相容性活動</span><span class="sxs-lookup"><span data-stu-id="898a6-131">Ramping up: configure Compliance Manager to manage your compliance activities</span></span>](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - <span data-ttu-id="898a6-132">建立及管理您的第一筆評估</span><span class="sxs-lookup"><span data-stu-id="898a6-132">Building and managing your first assessment</span></span>
    - <span data-ttu-id="898a6-133">執行執行和測試改進動作以完成評估中的控制項</span><span class="sxs-lookup"><span data-stu-id="898a6-133">Performing implementation and testing work on improvement actions to complete controls in your assessments</span></span>
    - <span data-ttu-id="898a6-134">瞭解不同的動作會如何影響您的合規性分數</span><span class="sxs-lookup"><span data-stu-id="898a6-134">Understanding how different actions impact your compliance score</span></span>
- [<span data-ttu-id="898a6-135">向上擴充：使用高級功能以符合您的自訂需求</span><span class="sxs-lookup"><span data-stu-id="898a6-135">Scaling up: use advanced functionality to meet your custom needs</span></span>](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - <span data-ttu-id="898a6-136">建立您的自訂評估以追蹤非 Microsoft 365 產品</span><span class="sxs-lookup"><span data-stu-id="898a6-136">Creating your custom assessments to track non-Microsoft 365 products</span></span>
    - <span data-ttu-id="898a6-137">修改現有範本以新增或移除控制項</span><span class="sxs-lookup"><span data-stu-id="898a6-137">Modifying existing templates to add or remove controls</span></span>
    - <span data-ttu-id="898a6-138">設定改進動作的自動測試</span><span class="sxs-lookup"><span data-stu-id="898a6-138">Setting up automated testing of improvement actions</span></span>

## <a name="how-your-compliance-score-is-calculated"></a><span data-ttu-id="898a6-139">如何計算合規性分數</span><span class="sxs-lookup"><span data-stu-id="898a6-139">How your compliance score is calculated</span></span>

<span data-ttu-id="898a6-140">您的合規性分數是根據 Microsoft 與客戶管理的控制項實施的組合來計算。</span><span class="sxs-lookup"><span data-stu-id="898a6-140">Your compliance score is calculated based on a combination of Microsoft and customer-managed control implementations.</span></span> <span data-ttu-id="898a6-141">請參閱 [相容性分數計算](../compliance/compliance-score-calculation.md) 以取得詳細的說明。</span><span class="sxs-lookup"><span data-stu-id="898a6-141">See [compliance score calculation](../compliance/compliance-score-calculation.md) for a detailed explanation.</span></span>

<span data-ttu-id="898a6-142">控制項會根據其是否為強制性或自由的，以及是否為預防性、偵探或糾正，指派分數值。</span><span class="sxs-lookup"><span data-stu-id="898a6-142">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span> <span data-ttu-id="898a6-143">兩者共同代表其相對於其他控制項的實施風險。</span><span class="sxs-lookup"><span data-stu-id="898a6-143">These collectively represent the risk of not implementing it relative to other controls.</span></span>

<span data-ttu-id="898a6-144">如合規性分數計算文章中所示，預防控制措施取得的分數高於偵探和修正，而強制控制措施取得的分數高於自由。</span><span class="sxs-lookup"><span data-stu-id="898a6-144">As presented in the compliance score calculation article, preventative controls get a higher score than detective and corrective ones, and mandatory controls get a higher score than discretionary ones.</span></span>

<span data-ttu-id="898a6-145">合規性分數管理 UI 不會列出這些參數，也不會提供加以篩選的功能。</span><span class="sxs-lookup"><span data-stu-id="898a6-145">The Compliance Score admin UI does not list these parameters, nor does it provide the ability to filter by them.</span></span> <span data-ttu-id="898a6-146">不過，如果您從合規性管理員下載相關聯的範本，則產生的資料集會為大多數規定列出這些參數。</span><span class="sxs-lookup"><span data-stu-id="898a6-146">However, if you download the associated template from  Compliance Manager, the resulting data set does list these parameters for most regulations.</span></span>

<span data-ttu-id="898a6-147">針對技術控制，符合性管理員會在成功實施及測試動作時，自動更新改進動作分數。</span><span class="sxs-lookup"><span data-stu-id="898a6-147">For technical controls, Compliance Manager automatically updates the improvement action score once the action has been successfully implemented and tested.</span></span> <span data-ttu-id="898a6-148">其他非技術控制動作（如可 &mdash; 操作或與檔相關的動作）必須 &mdash; 以手動方式錄製，以在分數的點數開始之前進行。</span><span class="sxs-lookup"><span data-stu-id="898a6-148">Other, non-technical control actions&mdash;such as those that are operational or related to documentation&mdash;need to be recorded manually as implemented before points count toward your score.</span></span>

<span data-ttu-id="898a6-149">此外，您還可以針對其他用途執行某些改進動作，例如， &mdash; 使用保留標籤的原因並非資料隱私權法規合規性 &mdash; ，因此，即使是用於其他用途，也不是故意執行法規遵從性動作的一部分，您也可以取得使用此類功能的信用。</span><span class="sxs-lookup"><span data-stu-id="898a6-149">You many also be implementing certain improvement actions for other purposes&mdash;for example using retention labels for reasons other than data privacy regulation compliance&mdash;so you would get credit for using such a feature even if it is being used for other purposes, and not part of a deliberate compliance action.</span></span>

<span data-ttu-id="898a6-150">您的合規性分數應視為追蹤廣泛規模改進的相對量。</span><span class="sxs-lookup"><span data-stu-id="898a6-150">Your compliance score should be considered a relative measure to track improvement on a broad scale.</span></span> <span data-ttu-id="898a6-151">您不應採用完美的分數。</span><span class="sxs-lookup"><span data-stu-id="898a6-151">You should not pursue a perfect score.</span></span>

## <a name="additional-guidance"></a><span data-ttu-id="898a6-152">其他指引</span><span class="sxs-lookup"><span data-stu-id="898a6-152">Additional guidance</span></span>

<span data-ttu-id="898a6-153">以下是使用合規性管理員協助您達到資料隱私權法規合規性的一些重要秘訣：</span><span class="sxs-lookup"><span data-stu-id="898a6-153">Here are a few important tips for using Compliance Manager to help you achieve data privacy regulation compliance:</span></span>

- <span data-ttu-id="898a6-154">每個資料隱私權規定都結合了技術控制、檔規格，以及作業、程式和報表需求。</span><span class="sxs-lookup"><span data-stu-id="898a6-154">Each data privacy regulation has a combination of technical controls, documentation specifications, and operational, process, and reporting requirements.</span></span> <span data-ttu-id="898a6-155">所有這些動作都會顯示在改進動作中。</span><span class="sxs-lookup"><span data-stu-id="898a6-155">All of these show up in the improvement actions.</span></span>

- <span data-ttu-id="898a6-156">若要將改進動作的查看重點放在您感興趣的區域，您可以在合規性管理員系統管理員的 [ **解決方案** ] 索引標籤中篩選動作類型。深入瞭解 [篩選合規性管理員儀表板視圖](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)。</span><span class="sxs-lookup"><span data-stu-id="898a6-156">To focus the view of improvement actions to your area of interest, you can filter by action type in the **Solutions** tab in the Compliance Manager admin. Learn more about [filtering your Compliance Manager dashboard view](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).</span></span>

- <span data-ttu-id="898a6-157">在合規性管理員中識別的「改進動作」的相對重要性和優先順序，應視為廣泛風險審查的一部分，以及您已判斷貴組織需要管理的資料隱私權風險。</span><span class="sxs-lookup"><span data-stu-id="898a6-157">The relative importance and priority of improvement actions identified in Compliance Manager should be considered as part of a broader risk review along with the data privacy risk you've determined your organization needs to manage.</span></span>

- <span data-ttu-id="898a6-158">即使已選取 GDPR、LGPD、CCPA 及 HIPAA-高科技的規章評估範本，也會針對多種法規需求進行改進動作匯總，例如，合規性管理員中會列出幾乎400改進動作。</span><span class="sxs-lookup"><span data-stu-id="898a6-158">Even with improvement action aggregation across multiple regulatory requirements, if the regulation assessment templates for GDPR, LGPD, CCPA, and HIPAA-HITECH are selected, for example, almost 400 improvement actions will be listed in Compliance Manager.</span></span> <span data-ttu-id="898a6-159">若要更好地處理這個長清單，請使用 [改進動作篩選]，將結果集縮小為更易於管理的清單。</span><span class="sxs-lookup"><span data-stu-id="898a6-159">To better tackle this long list, use the improvement action filter to reduce the result set to a more manageable list.</span></span>

- <span data-ttu-id="898a6-160">[類別] 篩選提供一種方法，可透過邏輯群組篩選改進動作，以追蹤、避免、保護、保留及調查此整體解決方案中的文章對齊。</span><span class="sxs-lookup"><span data-stu-id="898a6-160">The Categories filter provides a means to filter improvement actions by logical grouping, which the Track, Prevent, Protect, Retain, and Investigate articles in this overall solution align to.</span></span>

- <span data-ttu-id="898a6-161">[！附注] 中所列的某些控制項，可能會被視為更直接與特定的規章相關的專案，而其他控制項可能更直接與法規精神產生關聯，許多時間只是建議的活動或最佳作法。</span><span class="sxs-lookup"><span data-stu-id="898a6-161">Some of the controls listed in the improvement actions may be considered more directly tied to a specific regulatory article, while other controls may be more indirectly associated with the spirit of a regulation and many times are simply recommended activities or best practices.</span></span>