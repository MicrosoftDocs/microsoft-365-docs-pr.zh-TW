---
title: 使用評估自訂 Microsoft 合規性分數
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 建立評估，以協助您管理組織的合規性，以設計自訂的 Microsoft 合規性分數。
ms.openlocfilehash: 45a5e76aa4f6581146ded510f75d772c202751ee
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023306"
---
# <a name="customize-compliance-score-preview-with-assessments"></a><span data-ttu-id="ee543-103">使用評估自訂合規性分數（預覽）</span><span class="sxs-lookup"><span data-stu-id="ee543-103">Customize Compliance Score (preview) with assessments</span></span>

<span data-ttu-id="ee543-104">**本文內容：** 瞭解如何設定準備使用**評估**以自訂合規性分數。</span><span class="sxs-lookup"><span data-stu-id="ee543-104">**In this article:** Learn how to customize Compliance Score by setting up ready to use **assessments**.</span></span> <span data-ttu-id="ee543-105">閱讀如何修改評估的**範本**，並建立您自己的自訂評估，以符合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="ee543-105">Read how to modify the **template** for an assessment and create your own Custom Assessments to suit your organization’s needs.</span></span> <span data-ttu-id="ee543-106">本文也說明如何將評估組織成**群組**、使用**控制項**及匯出評估**報告**。</span><span class="sxs-lookup"><span data-stu-id="ee543-106">This article also explains how to organize assessments into **groups**, work with **controls**, and export assessment **reports**.</span></span>

## <a name="introduction-to-assessments"></a><span data-ttu-id="ee543-107">評估簡介</span><span class="sxs-lookup"><span data-stu-id="ee543-107">Introduction to assessments</span></span>

<span data-ttu-id="ee543-108">合規性分數可協助您管理適用于組織之規章和憑證評估的相容性。</span><span class="sxs-lookup"><span data-stu-id="ee543-108">Compliance Score helps you manage compliance with assessments for the regulations and certifications that apply to your organization.</span></span> <span data-ttu-id="ee543-109">評估是特定法規、標準或原則中的控制項群組。</span><span class="sxs-lookup"><span data-stu-id="ee543-109">Assessments are groupings of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="ee543-110">合規性分數可讓您輕鬆地開始使用評估，以涵蓋各種行業和地區性法規和認證，以追蹤您的相容性。</span><span class="sxs-lookup"><span data-stu-id="ee543-110">Compliance Score makes it easy to start tracking your compliance by providing ready to use assessments that cover a variety of industry and regional regulations and certifications.</span></span>

<span data-ttu-id="ee543-111">每個評估都是從範本建立，該範本是一個包含必要控制項的架構，也就是用於完成評估的改進動作。</span><span class="sxs-lookup"><span data-stu-id="ee543-111">Each assessment is created from a template, which serves as a framework containing the necessary controls and improvement actions for completing the assessment.</span></span> <span data-ttu-id="ee543-112">為您的組織設定最相關的評估，可協助確保您在實施可限制法規遵從性風險的原則和操作程式。</span><span class="sxs-lookup"><span data-stu-id="ee543-112">Setting up the most relevant assessments for your organization helps ensure you’re implementing policies and operational procedures that can limit your compliance risk.</span></span>

<span data-ttu-id="ee543-113">您的所有評估都會列在「評估」頁面上。</span><span class="sxs-lookup"><span data-stu-id="ee543-113">All of your assessments are listed on the assessments page.</span></span> <span data-ttu-id="ee543-114">[深入瞭解](compliance-score-setup.md#assessments-page)如何篩選您的評估和轉譯狀態狀態。</span><span class="sxs-lookup"><span data-stu-id="ee543-114">[Learn more](compliance-score-setup.md#assessments-page) about how to filter your view of your assessments and interpret status states.</span></span>

## <a name="data-protection-baseline-default-assessment"></a><span data-ttu-id="ee543-115">資料保護基準的預設評估</span><span class="sxs-lookup"><span data-stu-id="ee543-115">Data protection baseline default assessment</span></span>

<span data-ttu-id="ee543-116">為了讓您開始，Microsoft 提供了包含 Microsoft 365 資料保護基準的符合性分數的**預設**評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-116">To get you started, Microsoft provides a **default** assessment in Compliance Score for you that contains the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="ee543-117">此基準是一組控制項，包含資料保護和一般資料控管的重要規章和標準。</span><span class="sxs-lookup"><span data-stu-id="ee543-117">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="ee543-118">此基準主要是從 NIST CSF （國家標準和技術協會 Cybersecurity Framework）和 ISO （國際標準組織的標準化 FedRAMP）和 GDPR （歐盟的一般資料保護法規）和（一般資料保護法規）中的專案來繪製要素。</span><span class="sxs-lookup"><span data-stu-id="ee543-118">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="ee543-119">在您設定任何其他評估之前，這種評估是用來計算您第一次符合性分數的初始分數。</span><span class="sxs-lookup"><span data-stu-id="ee543-119">This assessment is used to calculate your initial score the first time you come to Compliance Score, before you configure any other assessments.</span></span> <span data-ttu-id="ee543-120">合規性分數會從您的 Microsoft 365 解決方案中收集初始信號。</span><span class="sxs-lookup"><span data-stu-id="ee543-120">Compliance Score collects initial signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="ee543-121">您將會很快看到組織相對於重要資料保護標準與法規的執行方式，並查看建議採取的改進動作。</span><span class="sxs-lookup"><span data-stu-id="ee543-121">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="ee543-122">由於每個組織都有特定需求，因此符合您的需求取決於您設定及管理您自己的評估，以協助盡可能縮小及緩解風險。</span><span class="sxs-lookup"><span data-stu-id="ee543-122">Because every organization has specific needs, Compliance Score relies on you to set up and manage your own assessments to help minimize and mitigate risk as comprehensively as possible.</span></span>

## <a name="assessment-creation-overview"></a><span data-ttu-id="ee543-123">評估建立概述</span><span class="sxs-lookup"><span data-stu-id="ee543-123">Assessment creation overview</span></span>

<span data-ttu-id="ee543-124">您可以透過三種方式來設定評估：</span><span class="sxs-lookup"><span data-stu-id="ee543-124">There are three ways you can set up assessments:</span></span>

1. <span data-ttu-id="ee543-125">選擇 [已準備好使用評估]。</span><span class="sxs-lookup"><span data-stu-id="ee543-125">Choose a ready to use assessment.</span></span>
2. <span data-ttu-id="ee543-126">修改評估的範本，以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="ee543-126">Modify the template of an assessment to suit your own needs.</span></span>
3. <span data-ttu-id="ee543-127">建立您自己的自訂評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-127">Create your own Custom Assessment.</span></span>

<span data-ttu-id="ee543-128">使用者必須保留全域管理員、合規性管理員、合規性資料管理員或安全性管理員的角色，才能建立或修改評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-128">Users must hold a role of global administrator, compliance administrator, compliance data administrator, or security administrator in order to create or modify assessments.</span></span> <span data-ttu-id="ee543-129">深入瞭解[角色和許可權](compliance-score-setup.md#set-user-permissions-and-assign-roles)。</span><span class="sxs-lookup"><span data-stu-id="ee543-129">Learn more about [roles and permissions](compliance-score-setup.md#set-user-permissions-and-assign-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="ee543-130">在合規性分數中建立或修改的任何評估，也會反映在合規性管理員中。</span><span class="sxs-lookup"><span data-stu-id="ee543-130">Any assessments created or modified in Compliance Score will be also be reflected in Compliance Manager.</span></span> <span data-ttu-id="ee543-131">深入瞭解[合規性分數和合規性管理員之間的關係](compliance-score.md#relationship-to-compliance-manager)。</span><span class="sxs-lookup"><span data-stu-id="ee543-131">Learn more about the [relationship between Compliance Score and Compliance Manager](compliance-score.md#relationship-to-compliance-manager).</span></span>

### <a name="ready-to-use-assessments"></a><span data-ttu-id="ee543-132">準備好使用評估</span><span class="sxs-lookup"><span data-stu-id="ee543-132">Ready to use assessments</span></span>

<span data-ttu-id="ee543-133">從建立評估的[範本](compliance-score-templates.md)選擇中，選擇要 Kickstart 相容性旅程。</span><span class="sxs-lookup"><span data-stu-id="ee543-133">Kickstart your compliance journey by choosing from among Compliance Score’s selection of [templates](compliance-score-templates.md) for creating assessments.</span></span> <span data-ttu-id="ee543-134">範本包含每個特定評估所需的控制項和改善動作。</span><span class="sxs-lookup"><span data-stu-id="ee543-134">Templates contain the controls and improvement actions necessary for each particular assessment.</span></span> <span data-ttu-id="ee543-135">合規性分數的範本涵蓋與行業、地區和一般資料保護標準（例如 GDPR 和 ISO 27001）相符的規章和憑證。</span><span class="sxs-lookup"><span data-stu-id="ee543-135">Compliance Score’s templates cover regulations and certifications that align to industries, regions, and common data protection standards, such as GDPR and ISO 27001.</span></span>

<span data-ttu-id="ee543-136">**若要設定評估**，請[從嚮導開始建立評估](#create-an-assessment)時，選擇其中一個範本。</span><span class="sxs-lookup"><span data-stu-id="ee543-136">**To set up an assessment**, choose one of the templates when you start  [building the assessment from the wizard](#create-an-assessment).</span></span>

### <a name="modify-the-template-of-an-assessment"></a><span data-ttu-id="ee543-137">修改評估的範本</span><span class="sxs-lookup"><span data-stu-id="ee543-137">Modify the template of an assessment</span></span>

<span data-ttu-id="ee543-138">您可以修改評估的合規性分數範本，以便更好地符合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="ee543-138">You have the ability to modify Compliance Score templates for assessments in order to better suit your organization’s needs.</span></span> <span data-ttu-id="ee543-139">例如，如果您通常需要遵守 HIPAA，但需要額外的資料保護或安全性控制，您可以採取 HIPAA 範本並新增您自己的自訂欄位，以建立新的評估，以根據您的需求來監視進度。</span><span class="sxs-lookup"><span data-stu-id="ee543-139">For example, if you generally need to comply with HIPAA but require additional data protection or security controls, you can take our HIPAA template and add your own custom fields to create a new assessment that monitors your progress in the ways you require.</span></span> <span data-ttu-id="ee543-140">在公開預覽期間，您需要移至合規性管理員以修改範本。</span><span class="sxs-lookup"><span data-stu-id="ee543-140">During public preview, you’ll need to go to Compliance Manger to modify templates.</span></span>

<span data-ttu-id="ee543-141">**若要修改評估的範本**，請遵循下列指示：</span><span class="sxs-lookup"><span data-stu-id="ee543-141">**To modify the template of an assessment**, follow these instructions:</span></span>

1. <span data-ttu-id="ee543-142">查看符合性分數中可用[範本](compliance-score-templates.md)的清單，以決定要修改哪一個。</span><span class="sxs-lookup"><span data-stu-id="ee543-142">View the list of available [templates](compliance-score-templates.md) in Compliance Score to determine which one you want to modify.</span></span>
2. <span data-ttu-id="ee543-143">請參閱[合規性管理員指示，以使用擴充處理常式自訂範本](working-with-compliance-manager.md#customize-a-template-through-the-extension-process)。</span><span class="sxs-lookup"><span data-stu-id="ee543-143">See the [Compliance Manager instructions to customize a template using the extension process](working-with-compliance-manager.md#customize-a-template-through-the-extension-process).</span></span>
3. <span data-ttu-id="ee543-144">當您建立範本，並將其匯入合規性管理員之後，您就可以在合規性分數中建立新的評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-144">Once you’ve created your template and imported it into Compliance Manger, you can then create your new assessment in Compliance Score.</span></span> <span data-ttu-id="ee543-145">依照「評估建立」[嚮導](#create-an-assessment)的使用建立評估的處理常式。</span><span class="sxs-lookup"><span data-stu-id="ee543-145">Follow the process of building your assessment using the [assessment creation wizard](#create-an-assessment).</span></span>

> [!NOTE]
> <span data-ttu-id="ee543-146">深入瞭解公開預覽期間[合規性分數和合規性管理員之間的關係](compliance-score.md#relationship-to-compliance-manager)。</span><span class="sxs-lookup"><span data-stu-id="ee543-146">Learn  more about the [relationship between Compliance Score and Compliance Manager](compliance-score.md#relationship-to-compliance-manager) during public preview.</span></span>

### <a name="create-your-own-custom-assessment"></a><span data-ttu-id="ee543-147">建立您自己的自訂評估</span><span class="sxs-lookup"><span data-stu-id="ee543-147">Create your own Custom Assessment</span></span>

<span data-ttu-id="ee543-148">您可以完全從頭開始建立您自己的評估，以準確追蹤組織所需的專案。</span><span class="sxs-lookup"><span data-stu-id="ee543-148">You can create your own assessment entirely from scratch to track precisely what your organization needs.</span></span> <span data-ttu-id="ee543-149">如以上所述的修改程式，建立您自己的評估要求您先在合規性管理員中為評估建立您自己的範本。</span><span class="sxs-lookup"><span data-stu-id="ee543-149">As with the modification process outlined above, creating your own assessment requires you to first create your own template for the assessment in Compliance Manager.</span></span>

<span data-ttu-id="ee543-150">**若要建立您自己的自訂評估**，請遵循下列指示：</span><span class="sxs-lookup"><span data-stu-id="ee543-150">**To create your own Custom Assessment**, follow these instructions:</span></span>

1. <span data-ttu-id="ee543-151">閱讀如何[在合規性管理員中建立您自己的範本](working-with-compliance-manager.md#create-your-own-template-and-import-it-into-compliance-manager)。</span><span class="sxs-lookup"><span data-stu-id="ee543-151">Read how to [create your own template in Compliance Manager](working-with-compliance-manager.md#create-your-own-template-and-import-it-into-compliance-manager).</span></span>
2. <span data-ttu-id="ee543-152">當您建立範本，並將其匯入合規性管理員之後，您就可以在合規性分數中建立新的評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-152">Once you’ve created your template and imported it into Compliance Manger, you can then create your new assessment in Compliance Score.</span></span> <span data-ttu-id="ee543-153">依照「評估建立」[嚮導](#create-an-assessment)的使用建立評估的處理常式。</span><span class="sxs-lookup"><span data-stu-id="ee543-153">Follow the process of building your assessment using the [assessment creation wizard](#create-an-assessment).</span></span>

## <a name="understand-groups-before-creating-assessments"></a><span data-ttu-id="ee543-154">在建立評估之前深入瞭解群組</span><span class="sxs-lookup"><span data-stu-id="ee543-154">Understand groups before creating assessments</span></span>

<span data-ttu-id="ee543-155">在您建立或修改評估之前，請務必瞭解群組的運作方式。</span><span class="sxs-lookup"><span data-stu-id="ee543-155">Before you create or modify assessments, it’s important to understand how groups work.</span></span> <span data-ttu-id="ee543-156">當您建立評估時，您必須在該程式中將其指派給群組。</span><span class="sxs-lookup"><span data-stu-id="ee543-156">When you create an assessment, you’ll need to assign it to a group during that process.</span></span> <span data-ttu-id="ee543-157">因此，我們建議您規劃評估的群群組原則，然後再建立評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-157">We therefore recommend planning a grouping strategy for your assessments before you create assessments.</span></span>

### <a name="what-are-groups"></a><span data-ttu-id="ee543-158">何謂群組</span><span class="sxs-lookup"><span data-stu-id="ee543-158">What are groups</span></span>

<span data-ttu-id="ee543-159">群組是可讓您組織評估的容器。</span><span class="sxs-lookup"><span data-stu-id="ee543-159">Groups are containers that allow you to organize assessments.</span></span> <span data-ttu-id="ee543-160">您可以根據對您邏輯的方式來群組評估，例如依年或規定，或根據組織的部門或地理區域。</span><span class="sxs-lookup"><span data-stu-id="ee543-160">You can group assessments in a way that is logical to you, such as by year or regulation, or based on your organization's divisions or geographies.</span></span> <span data-ttu-id="ee543-161">以下是兩個群組和其基礎評估的範例：</span><span class="sxs-lookup"><span data-stu-id="ee543-161">Below are examples of two groups and their underlying assessments:</span></span>

- <span data-ttu-id="ee543-162">**FFIEC 是評估2020**</span><span class="sxs-lookup"><span data-stu-id="ee543-162">**FFIEC IS assessments 2020**</span></span>
  - <span data-ttu-id="ee543-163">Office 365 + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="ee543-163">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="ee543-164">Intune + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="ee543-164">Intune + FFIEC IS</span></span>
- <span data-ttu-id="ee543-165">**資料安全性和隱私權評估**</span><span class="sxs-lookup"><span data-stu-id="ee543-165">**Data security and privacy assessments**</span></span>
  - <span data-ttu-id="ee543-166">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="ee543-166">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="ee543-167">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="ee543-167">Office 365 + ISO 27018:2014</span></span>

<span data-ttu-id="ee543-168">當相同群組中的兩個不同評估共用您所管理的改善動作時，您對動作的執行詳細資料或狀態所做的任何更新，都將自動同步處理至群組中任何其他評估中的相同動作。</span><span class="sxs-lookup"><span data-stu-id="ee543-168">When two different assessments in the same group share improvement actions that are managed by you, any updates you make to an action's implementation details or status will automatically synchronize to the same action in any other assessment in the group.</span></span> <span data-ttu-id="ee543-169">這項同步處理可讓您執行一個改進動作，並符合多種法規的需求。</span><span class="sxs-lookup"><span data-stu-id="ee543-169">This synchronization allows you to implement one improvement action and meet several requirements across multiple regulations.</span></span>

### <a name="how-to-create-a-group"></a><span data-ttu-id="ee543-170">如何建立群組</span><span class="sxs-lookup"><span data-stu-id="ee543-170">How to create a group</span></span>

<span data-ttu-id="ee543-171">您可以在[建立新評估](#create-an-assessment)的過程中建立群組。</span><span class="sxs-lookup"><span data-stu-id="ee543-171">You create a group during the process of [creating a new assessment](#create-an-assessment).</span></span>

<span data-ttu-id="ee543-172">群組無法建立為獨立實體;群組至少必須包含一項評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-172">Groups cannot be created as standalone entities; a group must contain at least one assessment.</span></span> <span data-ttu-id="ee543-173">若要建立群組，您必須先建立評估，以放置在群組中。</span><span class="sxs-lookup"><span data-stu-id="ee543-173">In order to create a group, you must first create an assessment to put in the group.</span></span>

### <a name="what-to-know-when-working-with-groups"></a><span data-ttu-id="ee543-174">使用群組時的須知</span><span class="sxs-lookup"><span data-stu-id="ee543-174">What to know when working with groups</span></span>

- <span data-ttu-id="ee543-175">群組名稱在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ee543-175">Group names must be unique within your organization.</span></span>
- <span data-ttu-id="ee543-176">群組沒有安全性屬性。</span><span class="sxs-lookup"><span data-stu-id="ee543-176">Groups don't have security properties.</span></span> <span data-ttu-id="ee543-177">擁有權限都與評估相關聯。</span><span class="sxs-lookup"><span data-stu-id="ee543-177">All permissions are associated with assessments.</span></span>
- <span data-ttu-id="ee543-178">將評估新增至群組之後，就無法變更該群組。</span><span class="sxs-lookup"><span data-stu-id="ee543-178">Once you add an assessment to a group, the grouping cannot be changed.</span></span>
- <span data-ttu-id="ee543-179">完成時，相同群組內的相關評估控制項會自動更新。</span><span class="sxs-lookup"><span data-stu-id="ee543-179">Related assessment controls in different assessments within the same group automatically update when completed.</span></span>
- <span data-ttu-id="ee543-180">如果您將新的評估新增至現有的群組，則會將該群組中評估的一般資訊複製到新的評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-180">If you add a new assessment to an existing group, common information from assessments in that group are copied to the new assessment.</span></span>
- <span data-ttu-id="ee543-181">群組可以包含同一個憑證或法規的評估，但是每個群組只能包含特定產品認證組的一個評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-181">Groups can contain assessments for the same certification or regulation, but each group can only contain one assessment for a specific product-certification pair.</span></span> <span data-ttu-id="ee543-182">例如，群組不可包含針對 Office 365 和 NIST CSF 的兩項評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-182">For example, a group can't contain two assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="ee543-183">只有在每個群組的對應憑證或法規不同時，群組才可以包含同一個產品的多項評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-183">A group can contain multiple assessments for the same product only if the corresponding certification or regulation for each one is different.</span></span>
- <span data-ttu-id="ee543-184">刪除評估會中斷這種評估與群組之間的關聯。</span><span class="sxs-lookup"><span data-stu-id="ee543-184">Deleting an assessment breaks the relationship between that assessment and the group.</span></span>
- <span data-ttu-id="ee543-185">無法刪除群組。</span><span class="sxs-lookup"><span data-stu-id="ee543-185">Groups can't be deleted.</span></span>
- <span data-ttu-id="ee543-186">對出現在多個群組中的改進進行變更時，該變更會反映在該改進動作的所有實例中。</span><span class="sxs-lookup"><span data-stu-id="ee543-186">When a change is made to an improvement that appears in multiple groups, that change is reflected in all instances of that improvement action.</span></span>

## <a name="create-an-assessment"></a><span data-ttu-id="ee543-187">建立評估</span><span class="sxs-lookup"><span data-stu-id="ee543-187">Create an assessment</span></span>

<span data-ttu-id="ee543-188">若要以合規性分數建立評估，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ee543-188">To create an assessment in Compliance Score, follow the steps below:</span></span>

1. <span data-ttu-id="ee543-189">在 [評估] 頁面中，選取 [**新增評估**]。</span><span class="sxs-lookup"><span data-stu-id="ee543-189">From your assessments page, select **Add assessment**.</span></span> <span data-ttu-id="ee543-190">評估嚮導將會出現在大量飛入窗格中。</span><span class="sxs-lookup"><span data-stu-id="ee543-190">An assessment wizard will appear in a large flyout pane.</span></span>

2. <span data-ttu-id="ee543-191">**選取範本：** 選擇用作評估基礎的範本。</span><span class="sxs-lookup"><span data-stu-id="ee543-191">**Select a template:** Choose a template to serve as the basis for your assessment.</span></span> <span data-ttu-id="ee543-192">您可以選擇 [準備使用範本] 或您已修改或建立的範本。</span><span class="sxs-lookup"><span data-stu-id="ee543-192">You can choose a ready to use template, or a template you’ve modified or created.</span></span> <span data-ttu-id="ee543-193">選取所選範本旁的選項按鈕，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ee543-193">Select the radio button next to your chosen template, then select  **Next**.</span></span>

> [!NOTE]
> <span data-ttu-id="ee543-194">請參閱在合規性管理員中處理的處理常式，以[取得建立及修改範本的指示](working-with-compliance-manager.md#templates)。</span><span class="sxs-lookup"><span data-stu-id="ee543-194">See [instructions for creating and modifying templates](working-with-compliance-manager.md#templates), a process handled in Compliance Manager.</span></span>

3. <span data-ttu-id="ee543-195">**名稱和群組：** 在 [**評估名稱**] 欄位中，輸入評估的名稱。</span><span class="sxs-lookup"><span data-stu-id="ee543-195">**Name and group:** Enter a name for your assessment in the **Assessment name** field.</span></span> <span data-ttu-id="ee543-196">在群組內，評估名稱必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ee543-196">Assessment names must be unique within groups.</span></span> <span data-ttu-id="ee543-197">如果評估的名稱與任何指定群組中的另一個評估名稱相符，您會收到錯誤要求您建立不同的名稱。</span><span class="sxs-lookup"><span data-stu-id="ee543-197">If the name of your assessment matches the name of another assessment in any given group, you’ll receive an error asking you to create a different name.</span></span>

4. <span data-ttu-id="ee543-198">將評估指派給群組。</span><span class="sxs-lookup"><span data-stu-id="ee543-198">Assign your assessment to a group.</span></span> <span data-ttu-id="ee543-199">您可以：</span><span class="sxs-lookup"><span data-stu-id="ee543-199">You can either:</span></span>
    - <span data-ttu-id="ee543-200">選取 [**使用現有的群組**將其指派給您已建立的群組]。或</span><span class="sxs-lookup"><span data-stu-id="ee543-200">Select **Use existing group** to assign it to a group you’ve already created; or</span></span>
    - <span data-ttu-id="ee543-201">選取 [**建立新的群組**]，以建立新的群組，並將這種評估指派給該群組。</span><span class="sxs-lookup"><span data-stu-id="ee543-201">Select **Create new group** to create a new group and assign this assessment to it.</span></span> <span data-ttu-id="ee543-202">決定群組的名稱，並在選項按鈕底下的欄位中輸入。</span><span class="sxs-lookup"><span data-stu-id="ee543-202">Determine a name for your group and enter it in the field beneath the radio button.</span></span>

5. <span data-ttu-id="ee543-203">**審閱並完成：** 嚮導的最後一個畫面會顯示針對評估所選擇的範本、名稱和群組。</span><span class="sxs-lookup"><span data-stu-id="ee543-203">**Review and finish:** The last screen of the wizard shows the template, name, and group chosen for the assessment.</span></span> <span data-ttu-id="ee543-204">您可以從畫面上的連結編輯任何這些設定，讓您回到嚮導的相關步驟。</span><span class="sxs-lookup"><span data-stu-id="ee543-204">You can edit any of these settings from the links on the screen, which take you back to the relevant steps in the wizard.</span></span> <span data-ttu-id="ee543-205">當您完成設定時，請選取 [**建立評估**]。</span><span class="sxs-lookup"><span data-stu-id="ee543-205">Once you’re satisfied with the settings, select **Create assessment**.</span></span>

6. <span data-ttu-id="ee543-206">下一個畫面會確認您已成功建立新的評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-206">The next screen confirms that you’ve successfully created your new assessment.</span></span> <span data-ttu-id="ee543-207">選取 [**完成**] 以關閉嚮導，新評估的 [詳細資料] 頁面會出現在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="ee543-207">Select **Done** to close the wizard, and your new assessment's details page will appear on the screen.</span></span>

<span data-ttu-id="ee543-208">如果在選取 [**建立評估**] 之後看到 [**評估失敗**] 畫面，請選取 [**重試**] 以重新建立評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-208">If you see an **Assessment failed** screen after selecting **Create assessment**, select **Try again** to re-create your assessment.</span></span>

## <a name="delete-an-assessment"></a><span data-ttu-id="ee543-209">刪除評估</span><span class="sxs-lookup"><span data-stu-id="ee543-209">Delete an assessment</span></span>

<span data-ttu-id="ee543-210">刪除評估會將其從評估頁面上的清單中移除。</span><span class="sxs-lookup"><span data-stu-id="ee543-210">Deleting an assessment removes it from the list on your assessments page.</span></span> <span data-ttu-id="ee543-211">**刪除評估是永久性的;您無法將其取回。**</span><span class="sxs-lookup"><span data-stu-id="ee543-211">**Deleting an assessment is permanent; you cannot get it back.**</span></span> <span data-ttu-id="ee543-212">如果您想要重新建立相同的評估，必須從頭開始重新建立。</span><span class="sxs-lookup"><span data-stu-id="ee543-212">If you want the same assessment again, it must be re-created from scratch.</span></span> <span data-ttu-id="ee543-213">如果評估中的改進動作未出現在任何其他評估中，則會在刪除評估時加以刪除。</span><span class="sxs-lookup"><span data-stu-id="ee543-213">If the improvement actions in the assessment do not appear in any other assessment, they will be deleted when the assessment is deleted.</span></span> <span data-ttu-id="ee543-214">建議您先匯出評估報告，再永久刪除。</span><span class="sxs-lookup"><span data-stu-id="ee543-214">We recommend exporting a report of the assessment before you permanently delete it.</span></span>

<span data-ttu-id="ee543-215">若要刪除評估，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ee543-215">To delete an assessment, follow the steps below:</span></span>

1. <span data-ttu-id="ee543-216">在 [評估] 頁面中，選取您要刪除的評估，以開啟評估的 [詳細資料] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ee543-216">From your assessments page, select the assessment you wish to delete to open that assessment’s details page.</span></span>
2. <span data-ttu-id="ee543-217">選取螢幕右上角的 [**刪除評估**]。</span><span class="sxs-lookup"><span data-stu-id="ee543-217">Select **Delete assessment** in the upper-right corner of your screen.</span></span>
3. <span data-ttu-id="ee543-218">隨即會出現一個視窗，詢問您是否要永久刪除評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-218">A window will appear asking you to confirm that you want to permanently delete the assessment.</span></span> <span data-ttu-id="ee543-219">選取 [**刪除評估**] 以關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="ee543-219">Select **Delete assessment** to close the window.</span></span> <span data-ttu-id="ee543-220">您將會看到一個確認視窗，表明評估已從合規性分數中刪除。</span><span class="sxs-lookup"><span data-stu-id="ee543-220">You’ll get a confirmation window that your assessment was deleted from Compliance Score.</span></span>

<span data-ttu-id="ee543-221">如果您只刪除群組中的唯一評估，則該群組也會從合規性分數中刪除。</span><span class="sxs-lookup"><span data-stu-id="ee543-221">If you delete the only assessment in a group, then that group is also deleted from Compliance Score.</span></span>

## <a name="monitor-assessment-progress-and-controls"></a><span data-ttu-id="ee543-222">監視評估進度和控制措施</span><span class="sxs-lookup"><span data-stu-id="ee543-222">Monitor assessment progress and controls</span></span>

<span data-ttu-id="ee543-223">每個評估都有詳細資料頁面，可提供您完成評估的進展一覽。</span><span class="sxs-lookup"><span data-stu-id="ee543-223">Each assessment has a details page that gives an at-a-glance view of your progress in completing the assessment.</span></span> <span data-ttu-id="ee543-224">頁面會顯示您在 [完成] 控制項中的進度，以及這些控制項內重要改進動作的測試狀態。</span><span class="sxs-lookup"><span data-stu-id="ee543-224">The page shows your progress in completing controls, and the test status of key improvement actions within those controls.</span></span>

### <a name="overview-tab"></a><span data-ttu-id="ee543-225">概覽] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="ee543-225">Overview tab</span></span>

<span data-ttu-id="ee543-226">[一覽表] 索引標籤包含圖形，顯示評估的完成百分比。</span><span class="sxs-lookup"><span data-stu-id="ee543-226">The overview tab contains a graph showing your percentage toward completion of the assessment.</span></span> <span data-ttu-id="ee543-227">此圖形包含您所擁有之動作的點數細分，以及 Microsoft 所擁有的動作點，所以您可以查看需要多少點才能完成評估。</span><span class="sxs-lookup"><span data-stu-id="ee543-227">This graph contains a breakdown of points from actions you own, and points from actions owned by Microsoft, so you can see how many more points you need to complete the assessment.</span></span>

<span data-ttu-id="ee543-228">評估中控制項的重要改進動作會以對取得點數的最大潛在影響為序列出。</span><span class="sxs-lookup"><span data-stu-id="ee543-228">The key improvement actions for controls in the assessment are listed in order of greatest potential impact to earn points.</span></span> <span data-ttu-id="ee543-229">關聯的圖表詳述您的改善動作的匯總測試狀態，這樣您就能快速估量已測試的內容和仍需完成的工作。</span><span class="sxs-lookup"><span data-stu-id="ee543-229">The associated graph details the aggregated test status of your improvement actions so you can quickly gauge what has been tested and what still needs to be done.</span></span>

<span data-ttu-id="ee543-230">若要存取個別的改善動作，請移至 [控制項] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ee543-230">To access individual improvement actions, go to the controls tab.</span></span>

### <a name="controls-tab"></a><span data-ttu-id="ee543-231">[控制項] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="ee543-231">Controls tab</span></span>

<span data-ttu-id="ee543-232">[控制項] 索引標籤會顯示對應到評估的每個控制項的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ee543-232">The controls tab displays detailed information for each control mapped to the assessment.</span></span> <span data-ttu-id="ee543-233">**控制項狀態細目**圖表會顯示依系列的控制項狀態，因此您可以快速查看控制項的分組需要注意。</span><span class="sxs-lookup"><span data-stu-id="ee543-233">A **control status breakdown** chart shows the status of controls by family, so you can see at a glance which groupings of controls need attention.</span></span>

<span data-ttu-id="ee543-234">在圖表底下，表格會列出評估中每個控制項的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ee543-234">Beneath the chart, a table lists detailed information about each control within the assessment.</span></span> <span data-ttu-id="ee543-235">控制項依控制項系列群組。</span><span class="sxs-lookup"><span data-stu-id="ee543-235">Controls are grouped by control family.</span></span> <span data-ttu-id="ee543-236">展開每個系列名稱，以顯示其所包含的個別控制項。</span><span class="sxs-lookup"><span data-stu-id="ee543-236">Expand each family name to reveal the individual controls it contains.</span></span> <span data-ttu-id="ee543-237">每個控制項所列的資訊包括：</span><span class="sxs-lookup"><span data-stu-id="ee543-237">The information listed for each control includes:</span></span>

- <span data-ttu-id="ee543-238">**控制項標題**</span><span class="sxs-lookup"><span data-stu-id="ee543-238">**Control title**</span></span>
- <span data-ttu-id="ee543-239">**狀態**：反映控制項內之改進動作的測試狀態</span><span class="sxs-lookup"><span data-stu-id="ee543-239">**Status**: reflects the test status of the improvement actions within the control</span></span> 
    - <span data-ttu-id="ee543-240">已**傳遞**-所有改進動作的測試狀態為「已傳遞」，或是至少有一個已傳遞，其餘部分則是「超出範圍」</span><span class="sxs-lookup"><span data-stu-id="ee543-240">**Passed** - all improvement actions have a test status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    -  <span data-ttu-id="ee543-241">**失敗**-至少有一個改進動作的測試狀態為 "Failed"</span><span class="sxs-lookup"><span data-stu-id="ee543-241">**Failed** - at least one improvement action has a test status of “failed”</span></span>
    - <span data-ttu-id="ee543-242">**None** -尚未測試所有改進動作</span><span class="sxs-lookup"><span data-stu-id="ee543-242">**None** - all improvement actions have not been tested</span></span>
    - <span data-ttu-id="ee543-243">**超出範圍**-這項評估的所有改進動作都超出範圍</span><span class="sxs-lookup"><span data-stu-id="ee543-243">**Out of scope** - all improvement actions are out of scope for this assessment</span></span>
    - <span data-ttu-id="ee543-244">**進行中**的改進動作的狀態不是上面所列的狀態，可能包括「進行中」、「部分信用」或「未檢測」。</span><span class="sxs-lookup"><span data-stu-id="ee543-244">**In progress** - improvement actions have a status other than the ones listed above, which could include “in progress,” “partial credit,” or “undetected”</span></span>
- <span data-ttu-id="ee543-245">**控制項識別碼**：控制項的標識號，由其對應的規章、標準或原則所指派</span><span class="sxs-lookup"><span data-stu-id="ee543-245">**Control ID**: the control’s identification number, assigned by its corresponding regulation, standard, or policy</span></span>
- <span data-ttu-id="ee543-246">**達到的點數**：完成動作所取得的點數，已超出可達到的點數總數目</span><span class="sxs-lookup"><span data-stu-id="ee543-246">**Points achieved**: the number of points earned by completing actions, out of the total number of achievable points</span></span> 
- <span data-ttu-id="ee543-247">**您的動作**：您的動作數目已完成，待完成的動作總數</span><span class="sxs-lookup"><span data-stu-id="ee543-247">**Your actions**: the number of your actions completed out of the total number of actions to be done</span></span>
- <span data-ttu-id="ee543-248">**Microsoft 動作**： microsoft 完成的動作數目</span><span class="sxs-lookup"><span data-stu-id="ee543-248">**Microsoft actions**: the number of actions completed by Microsoft</span></span> 

<span data-ttu-id="ee543-249">若要查看控制項的詳細資料，請從表格中的列選取它。</span><span class="sxs-lookup"><span data-stu-id="ee543-249">To view a control’s details, select it from its row in the table.</span></span> <span data-ttu-id="ee543-250">[控制項詳細資料] 頁面會顯示圖形，指出該控制項內動作的測試狀態。</span><span class="sxs-lookup"><span data-stu-id="ee543-250">The control details page shows a graph indicating the test status of the actions within that control.</span></span> <span data-ttu-id="ee543-251">圖形下方的表格會顯示該控制項的重要改進動作。</span><span class="sxs-lookup"><span data-stu-id="ee543-251">A table below the graph shows key improvement actions for that control.</span></span>

<span data-ttu-id="ee543-252">從清單中選取 [改進動作]，以深入瞭解改進動作的詳細資料頁面。</span><span class="sxs-lookup"><span data-stu-id="ee543-252">Select an improvement action from the list to drill into the improvement action’s details page.</span></span> <span data-ttu-id="ee543-253">[詳細資料] 頁面會顯示測試狀態、執行附注，以及啟動建議的解決方案。</span><span class="sxs-lookup"><span data-stu-id="ee543-253">The details pages shows test status, implementation notes, and launch into the recommended solution.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="ee543-254">深入了解</span><span class="sxs-lookup"><span data-stu-id="ee543-254">Learn more</span></span>
[<span data-ttu-id="ee543-255">瞭解如何依照合規性分數追蹤控制項和改進動作。</span><span class="sxs-lookup"><span data-stu-id="ee543-255">Understand how controls and improvement actions are tracked and scored by Compliance Score.</span></span>](compliance-score-methodology.md)

## <a name="export-an-assessment-report"></a><span data-ttu-id="ee543-256">匯出評估報告</span><span class="sxs-lookup"><span data-stu-id="ee543-256">Export an assessment report</span></span>

<span data-ttu-id="ee543-257">您可以[遵循這些指示](working-with-compliance-manager.md#reports)，將評估匯出至 Excel 檔案，以取得組織中的合規性專案關係人或外部審計員和主管。</span><span class="sxs-lookup"><span data-stu-id="ee543-257">You can export an assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators by [following these instructions](working-with-compliance-manager.md#reports).</span></span> <span data-ttu-id="ee543-258">您必須造訪合規性管理員才能匯出報告。</span><span class="sxs-lookup"><span data-stu-id="ee543-258">You’ll  need to visit Compliance Manager to export the report.</span></span>

<span data-ttu-id="ee543-259">報表是指匯出之日期和時間為止的評估快照。</span><span class="sxs-lookup"><span data-stu-id="ee543-259">The report is a snapshot of the assessment as of the date and time of the export.</span></span> <span data-ttu-id="ee543-260">它包含由您和 Microsoft 管理之控制項的詳細資料，包括實施狀態、測試日期、測試結果，以及上傳的證據檔的連結。</span><span class="sxs-lookup"><span data-stu-id="ee543-260">It contains the details for controls managed by both you and Microsoft, including implementation status, test date, test results, and links to uploaded evidence documents.</span></span>