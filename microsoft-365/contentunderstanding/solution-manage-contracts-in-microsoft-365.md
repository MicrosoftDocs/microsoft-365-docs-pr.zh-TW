---
title: 使用 Microsoft 365 解決方案管理合約
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts m365solution-overview
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: 瞭解如何使用 SharePoint Syntex、SharePoint 清單、Microsoft Teams 及 Power Automate 的 Microsoft 365 解決方案管理合約。
ms.openlocfilehash: 352ebd1b9170aaf7829c414e87f7a79c4f17a1df
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843767"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a><span data-ttu-id="a7be5-103">使用 Microsoft 365 解決方案管理合約</span><span class="sxs-lookup"><span data-stu-id="a7be5-103">Manage contracts using a Microsoft 365 solution</span></span>

<span data-ttu-id="a7be5-104">本文說明如何使用 Microsoft 365 SharePoint Syntex 和元件為您的組織建立合約管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="a7be5-104">This article describes how to create a contracts management solution for your organization by using SharePoint Syntex and components of Microsoft 365.</span></span> <span data-ttu-id="a7be5-105">它為您提供了一個架構，可協助您規劃及建立符合您獨特業務需求的解決方案。</span><span class="sxs-lookup"><span data-stu-id="a7be5-105">It provides you with a framework to help you plan and create a solution that fits your unique business needs.</span></span> <span data-ttu-id="a7be5-106">即使此解決方案不能完全符合您的業務需求，您在規劃中也可以採用它的部分，以建立自訂的合約管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="a7be5-106">Even if this solution doesn't suit your business needs as a whole, parts of it can be adopted in your planning to create a custom contract management solution.</span></span>

<span data-ttu-id="a7be5-107">*此內容集檔使用 Microsoft Thomas Molbach 與現代的工作解決方案策略小組一起開發的 Microsoft 365 解決方案。*</span><span class="sxs-lookup"><span data-stu-id="a7be5-107">*This content set documents a Microsoft 365 solution developed by Thomas Molbach with the Modern Work Solution Strategy Team at Microsoft.*</span></span>

## <a name="identify-the-business-problem"></a><span data-ttu-id="a7be5-108">識別業務問題</span><span class="sxs-lookup"><span data-stu-id="a7be5-108">Identify the business problem</span></span>

<span data-ttu-id="a7be5-109">規劃合約管理系統的第一步是瞭解您要嘗試解決的問題。</span><span class="sxs-lookup"><span data-stu-id="a7be5-109">The first step in planning your contract management system is to understand the problem you're trying to solve.</span></span> <span data-ttu-id="a7be5-110">針對此解決方案，需要解決四個重要的問題：</span><span class="sxs-lookup"><span data-stu-id="a7be5-110">For this solution, four key issues need to be addressed:</span></span>

- <span data-ttu-id="a7be5-111">**識別合約**。</span><span class="sxs-lookup"><span data-stu-id="a7be5-111">**Identify contracts**.</span></span> <span data-ttu-id="a7be5-112">您的組織可以處理許多檔，例如發票、合約、工作說明書等等。</span><span class="sxs-lookup"><span data-stu-id="a7be5-112">Your organization works with many documents, such as invoices, contracts, statements of work, and so on.</span></span>  <span data-ttu-id="a7be5-113">有些是透過電子郵件傳送的數位資產，有些則是透過傳統郵件傳送的紙面資產。</span><span class="sxs-lookup"><span data-stu-id="a7be5-113">Some are digital assets sent through email, and some are paper assets sent through traditional mail.</span></span> <span data-ttu-id="a7be5-114">您需要從其他所有檔中識別所有客戶協定的方法，然後再將它們分類。</span><span class="sxs-lookup"><span data-stu-id="a7be5-114">You need a way to identify all customer contracts from all other documents, and then classifying them as such.</span></span>

- <span data-ttu-id="a7be5-115">**追蹤合約核准** 的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="a7be5-115">**Track the history of contract approvals**.</span></span> <span data-ttu-id="a7be5-116">您的組織需要一種可靠的方式，來尋找是否已核准或拒絕合約，以及是否已處理付款。</span><span class="sxs-lookup"><span data-stu-id="a7be5-116">Your organization needs a reliable way to find whether contracts have been either approved or rejected, and whether payment has been processed.</span></span> 

- <span data-ttu-id="a7be5-117">**管理合約核准的網站**。</span><span class="sxs-lookup"><span data-stu-id="a7be5-117">**Site to manage contract approvals**.</span></span> <span data-ttu-id="a7be5-118">您的組織必須設定一個共同作業網站，讓所有必要的專案關係人都能輕鬆地查看合約。</span><span class="sxs-lookup"><span data-stu-id="a7be5-118">Your organization needs to set up a collaborative site in which all required stakeholders can easily review contracts.</span></span> <span data-ttu-id="a7be5-119">若有必要，專案關係人應能夠查看整個合約，但經常關心每個合約 (中的幾個主要欄位，例如，客戶名稱、PO 編號及總成本) 。</span><span class="sxs-lookup"><span data-stu-id="a7be5-119">Stakeholders should be able to review the whole contract if needed, but mostly care about seeing several key fields from each contract (for example, customer name, PO number, and total cost).</span></span> <span data-ttu-id="a7be5-120">利益關係人應能夠輕易核准或拒絕傳入的合約。</span><span class="sxs-lookup"><span data-stu-id="a7be5-120">Stakeholders should be able to easily approve or reject incoming contracts.</span></span>

- <span data-ttu-id="a7be5-121">**路由檢查的合約**。</span><span class="sxs-lookup"><span data-stu-id="a7be5-121">**Route reviewed contracts**.</span></span> <span data-ttu-id="a7be5-122">已核准和拒絕的合約必須透過特定工作流程路由傳送。</span><span class="sxs-lookup"><span data-stu-id="a7be5-122">Approved and rejected contracts need to be routed through a specific workflow.</span></span> <span data-ttu-id="a7be5-123">已核准的合約必須路由至協力廠商應用程式進行付款處理。</span><span class="sxs-lookup"><span data-stu-id="a7be5-123">Approved contracts need to be routed to a third-party application for payment processing.</span></span> <span data-ttu-id="a7be5-124">拒絕的合約必須進行路由以供其他複查。</span><span class="sxs-lookup"><span data-stu-id="a7be5-124">Rejected contracts need to be routed for additional review.</span></span>

## <a name="overview-of-the-solution"></a><span data-ttu-id="a7be5-125">解決方案概述</span><span class="sxs-lookup"><span data-stu-id="a7be5-125">Overview of the solution</span></span>

  ![使用 SharePoint Syntex、SharePoint 清單、Teams 及 Power Automate 的解決方案圖表。](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

<span data-ttu-id="a7be5-127">此合約管理解決方案指導方針包括四個 Microsoft 365 元件：</span><span class="sxs-lookup"><span data-stu-id="a7be5-127">This contract management solution guidance includes four components of Microsoft 365:</span></span>

- <span data-ttu-id="a7be5-128">**Microsoft SharePoint Syntex**：建立模型來識別和分類您的合約檔案，然後從這些檔案中解壓縮適當的資料。</span><span class="sxs-lookup"><span data-stu-id="a7be5-128">**Microsoft SharePoint Syntex**: Create models to identify and classify your contract files and then extract the appropriate data from them.</span></span>

- <span data-ttu-id="a7be5-129">**Microsoft SharePoint 清單**：使用新式 SharePoint 清單中的可用格式，以商業友好的格式呈現合約。</span><span class="sxs-lookup"><span data-stu-id="a7be5-129">**Microsoft SharePoint lists**: Use the formatting available in modern SharePoint lists to present contracts in a business-friendly format.</span></span>

- <span data-ttu-id="a7be5-130">**Microsoft Teams**：使用 Teams 通道和關聯的索引標籤的功能，讓您的專案關係人複查及管理合約。</span><span class="sxs-lookup"><span data-stu-id="a7be5-130">**Microsoft Teams**: Use the functionality of a Teams channel and associated tabs to allow your stakeholders to review and manage contracts.</span></span>

- <span data-ttu-id="a7be5-131">**Power Automate**：使用流程來引導透過核准程式的合約，然後再到協力廠商的付款申請。</span><span class="sxs-lookup"><span data-stu-id="a7be5-131">**Power Automate**: Use flows to guide contracts through the approval process, and then to a third-party application for payment.</span></span>

### <a name="how-it-all-works"></a><span data-ttu-id="a7be5-132">所有的運作方式</span><span class="sxs-lookup"><span data-stu-id="a7be5-132">How it all works</span></span>

  ![解決方案的圖表，顯示可上傳檔、提取資料、通知利益關係人，以及核准或拒絕合約的工作流程。](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. <span data-ttu-id="a7be5-134">檔上傳至 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="a7be5-134">Documents are uploaded to a SharePoint document library.</span></span> <span data-ttu-id="a7be5-135">已將 SharePoint Syntex 檔理解模型套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="a7be5-135">A SharePoint Syntex document understanding model has been applied to the document library.</span></span> <span data-ttu-id="a7be5-136">它會檢查每個檔案，以查看是否有任何與「合約」內容類型相符的檔。</span><span class="sxs-lookup"><span data-stu-id="a7be5-136">It checks each file to see if any match a "contract" content type it's trained to look for.</span></span> <span data-ttu-id="a7be5-137">如果找到相符的檔案，則會將檔案歸類為「合約」，並更新檔的內容類型。</span><span class="sxs-lookup"><span data-stu-id="a7be5-137">If it finds a match, it classifies the file as a "contract" and updates the content type for the document.</span></span>

2. <span data-ttu-id="a7be5-138">模型也會從專案關係人所感興趣的每個合約檔中拉出特定資料，例如 *用戶端*、 *合同工* 和 *費用金額*。</span><span class="sxs-lookup"><span data-stu-id="a7be5-138">The model also pulls out specific data from each contract file that stakeholders are interested in seeing, such as the *Client*, *Contractor*, and *Fee amount*.</span></span>

    <span data-ttu-id="a7be5-139">下列頁面是已訓練模型識別的合約範例。</span><span class="sxs-lookup"><span data-stu-id="a7be5-139">The following page is an example of a contract that the model is trained to identify.</span></span>

      ![合約的範例。](../media/content-understanding/contract.png)

3. <span data-ttu-id="a7be5-141">在 Microsoft Teams 中，所有的專案關係人皆為安全 Teams 通道的成員，在此通道中，文件庫中的所有合約均可供核准或拒絕使用。</span><span class="sxs-lookup"><span data-stu-id="a7be5-141">In Microsoft Teams, all stakeholders are members of a secure Teams channel in which all contracts in the document library are visible for approval or rejection.</span></span> <span data-ttu-id="a7be5-142">透過使用 Teams 功能，當需要檢查新的合約時，所有的專案關係人都會收到通知。</span><span class="sxs-lookup"><span data-stu-id="a7be5-142">By using Teams functionality, all stakeholders are notified when new contracts need to be reviewed.</span></span>
 
4. <span data-ttu-id="a7be5-143">透過使用 Power Automate，會透過 Teams 通道中的核准程式移動合約。</span><span class="sxs-lookup"><span data-stu-id="a7be5-143">By using Power Automate, contracts are moved through the approval process in the Teams channel.</span></span> <span data-ttu-id="a7be5-144">當成員核准合約時，合同狀態會變更為 [核准]，所有成員都會透過 Teams 文章通知，並會建立行專案，以顯示合約已準備好進行中的付出。</span><span class="sxs-lookup"><span data-stu-id="a7be5-144">When a member approves a contract, the contract status is changed to approve, all members are notified through a Teams post, and a line item is created to show that the contract is ready for payout.</span></span> <span data-ttu-id="a7be5-145">您可以擴充此程式，以直接寫入協力廠商財務應用程式進行付款。</span><span class="sxs-lookup"><span data-stu-id="a7be5-145">This process can be extended to write directly to a third-party financial application for payment.</span></span>

5.  <span data-ttu-id="a7be5-146">當成員拒絕合約時，狀態會變更為 [已拒絕]，而且會透過 Teams 文章通知所有成員。</span><span class="sxs-lookup"><span data-stu-id="a7be5-146">When a member rejects a contract, the status is changed to rejected, and all members are notified through a Teams post.</span></span>

6. <span data-ttu-id="a7be5-147">此解決方案的最終結果是您組織的自動化業務程式。</span><span class="sxs-lookup"><span data-stu-id="a7be5-147">The end result of this solution is an automated business process for your organization.</span></span> <span data-ttu-id="a7be5-148">員工可輕鬆使用 Teams 中的自訂磚模式，以啟動及監視檔的核准工作流程。</span><span class="sxs-lookup"><span data-stu-id="a7be5-148">Employees can easily use the custom tile view in Teams to initiate and monitor the approval workflow of your documents.</span></span> 

     ![[合約] 索引標籤。](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a><span data-ttu-id="a7be5-150">授權需求</span><span class="sxs-lookup"><span data-stu-id="a7be5-150">Licensing requirements</span></span>

<span data-ttu-id="a7be5-151">此方案依賴下列功能（Microsoft 365 企業版 (E1、E3、E5、F3) 或商務 (Basic、Standard 或進階版) 授權）：</span><span class="sxs-lookup"><span data-stu-id="a7be5-151">This solution relies on the following functionality, all available as part of a Microsoft 365 Enterprise (E1, E3, E5, F3) or Business (Basic, Standard, or Premium) license:</span></span>

-   <span data-ttu-id="a7be5-152">Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="a7be5-152">Microsoft SharePoint Syntex</span></span>
-   <span data-ttu-id="a7be5-153">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a7be5-153">Microsoft Teams</span></span>
-   <span data-ttu-id="a7be5-154">Power Automate</span><span class="sxs-lookup"><span data-stu-id="a7be5-154">Power Automate</span></span>

## <a name="create-the-solution"></a><span data-ttu-id="a7be5-155">建立方案</span><span class="sxs-lookup"><span data-stu-id="a7be5-155">Create the solution</span></span>

<span data-ttu-id="a7be5-156">下一節將詳細說明如何設定您的合約管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="a7be5-156">The next sections will go into detail about how to configure your contracts management solution.</span></span> <span data-ttu-id="a7be5-157">其劃分分為三個步驟：</span><span class="sxs-lookup"><span data-stu-id="a7be5-157">It's divided into three steps:</span></span>

- [<span data-ttu-id="a7be5-158">步驟1。使用 SharePoint Syntex 來識別合約檔案及提取資料</span><span class="sxs-lookup"><span data-stu-id="a7be5-158">Step 1. Use SharePoint Syntex to identify contract files and extract data</span></span>](solution-manage-contracts-step1.md)
- [<span data-ttu-id="a7be5-159">步驟2。使用 Microsoft Teams 建立您的合約管理通道</span><span class="sxs-lookup"><span data-stu-id="a7be5-159">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
- [<span data-ttu-id="a7be5-160">步驟3。使用 Power Automate 建立流程以處理您的合約</span><span class="sxs-lookup"><span data-stu-id="a7be5-160">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
