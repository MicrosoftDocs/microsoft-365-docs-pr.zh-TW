---
title: Microsoft 規範分數版本資訊
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
description: Microsoft 規範分數（預覽）的發行附注與已知問題，M365 規範中心的功能可協助簡化及自動化風險評估。
ms.openlocfilehash: 6678ec03d2cd87a97244acaa55a15483d78dd632
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022190"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a><span data-ttu-id="974b5-103">Microsoft 規範分數（預覽）發行附注</span><span class="sxs-lookup"><span data-stu-id="974b5-103">Microsoft Compliance Score (preview) release notes</span></span>

<span data-ttu-id="974b5-104">**本文內容：** 此頁面顯示[Microsoft 規範評分](compliance-score.md)的公開預覽中的**新**功能，可讓您及早存取新功能。</span><span class="sxs-lookup"><span data-stu-id="974b5-104">**In this article:** This page shows **what's new** in the public preview of [Microsoft Compliance Score](compliance-score.md), which provides you with early access to new functionality.</span></span>

## <a name="assessment-creation-and-management-functionality"></a><span data-ttu-id="974b5-105">評估建立和管理功能</span><span class="sxs-lookup"><span data-stu-id="974b5-105">Assessment creation and management functionality</span></span>

<span data-ttu-id="974b5-106">2020年6月新增功能可讓使用者以相容性分數直接建立、刪除和管理其評估。</span><span class="sxs-lookup"><span data-stu-id="974b5-106">The June 2020 release adds functionality for users to create, delete, and manage their assessments directly in Compliance Score.</span></span> <span data-ttu-id="974b5-107">先前，所有評估管理都是在合規性管理員中。</span><span class="sxs-lookup"><span data-stu-id="974b5-107">Previously, all assessment management resided in Compliance Manager.</span></span> <span data-ttu-id="974b5-108">當您以合規性分數建立或修改評估時，系統會在合規性管理員中呈現更新。</span><span class="sxs-lookup"><span data-stu-id="974b5-108">When you create or modify an assessment in Compliance Score, the updates will surface in Compliance Manager.</span></span> <span data-ttu-id="974b5-109">同樣地，在合規性管理員中執行的任何評估工作都會以相容性分數呈現。</span><span class="sxs-lookup"><span data-stu-id="974b5-109">Likewise, any assessment work performed in Compliance Manager will surface in Compliance Score.</span></span> <span data-ttu-id="974b5-110">瞭解如何[在合規性分數中管理評估](compliance-score-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="974b5-110">Learn how to [manage assessments in Compliance Score](compliance-score-assessments.md).</span></span> <span data-ttu-id="974b5-111">請注意，範本的建立及修改仍會在合規性管理員中進行管理。</span><span class="sxs-lookup"><span data-stu-id="974b5-111">Note that template creation and modification is still managed in Compliance Manager.</span></span>

## <a name="new-templates-for-assessments"></a><span data-ttu-id="974b5-112">新的評估範本</span><span class="sxs-lookup"><span data-stu-id="974b5-112">New templates for assessments</span></span>

<span data-ttu-id="974b5-113">新的準備好使用的範本可用於評估，在其可供使用時，會以符合性分數發行。</span><span class="sxs-lookup"><span data-stu-id="974b5-113">New ready to use templates for assessments are released in Compliance Score as they become available.</span></span> <span data-ttu-id="974b5-114">[在這裡檢查範本的完整清單](compliance-score-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="974b5-114">Check the [full list of templates here](compliance-score-templates.md).</span></span> <span data-ttu-id="974b5-115">最近新增：</span><span class="sxs-lookup"><span data-stu-id="974b5-115">Recently added:</span></span>

- <span data-ttu-id="974b5-116">杜拜資訊安全性解析（DGISR）</span><span class="sxs-lookup"><span data-stu-id="974b5-116">Dubai Information Security Resolution (DGISR)</span></span>

## <a name="compliance-score-relationship-to-compliance-manager"></a><span data-ttu-id="974b5-117">合規性分數與合規性管理員的關係</span><span class="sxs-lookup"><span data-stu-id="974b5-117">Compliance Score relationship to Compliance Manager</span></span>

<span data-ttu-id="974b5-118">現在，在合規性管理員中處理的許多功能都可以在合規性分數中完成。</span><span class="sxs-lookup"><span data-stu-id="974b5-118">Many of the functions handled in Compliance Manager can now be done in Compliance Score.</span></span> <span data-ttu-id="974b5-119">不過，某些功能仍會在合規性管理員中運作。</span><span class="sxs-lookup"><span data-stu-id="974b5-119">However some functions still live in Compliance Manager.</span></span> <span data-ttu-id="974b5-120">在公開預覽期間，當您使用合規性分數和合規性管理員時，請牢記下列幾點：</span><span class="sxs-lookup"><span data-stu-id="974b5-120">Keep these points in mind as you work with Compliance Score and Compliance Manager during public preview:</span></span>

 - <span data-ttu-id="974b5-121">**建立評估的範本**：</span><span class="sxs-lookup"><span data-stu-id="974b5-121">**Creating templates for assessments**:</span></span> 
   - <span data-ttu-id="974b5-122">使用者必須移至合規性管理員，以[建立新的範本並修改現有的範本](working-with-compliance-manager.md#templates)。</span><span class="sxs-lookup"><span data-stu-id="974b5-122">Users must go to Compliance Manager to [create new templates and modify existing templates](working-with-compliance-manager.md#templates).</span></span>
   - <span data-ttu-id="974b5-123">新的範本必須包含**產品\*\*\*\*和憑證**的維度。</span><span class="sxs-lookup"><span data-stu-id="974b5-123">New templates must include Dimensions for both **Product** and **Certification**.</span></span>
 - <span data-ttu-id="974b5-124">**設定許可權**：在合規性管理員中未具有許可權的使用者，必須在 Microsoft 365 規範中心內設定其許可權（[深入瞭解](compliance-score-setup.md#set-user-permissions-and-assign-roles)）。</span><span class="sxs-lookup"><span data-stu-id="974b5-124">**Setting permissions**: Compliance Score users who didn't already have permissions in Compliance Manager need their permissions set in the Microsoft 365 compliance center ([learn more](compliance-score-setup.md#set-user-permissions-and-assign-roles)).</span></span>
- <span data-ttu-id="974b5-125">**資料傳輸**：具有合規性管理員中之資料的組織，將會看到相容性分數中的資料，也就是另一種方式，也是如此。</span><span class="sxs-lookup"><span data-stu-id="974b5-125">**Transfer of data**: organizations with data in Compliance Manager will see that data in Compliance Score, and the same is true the other way around.</span></span>
- <span data-ttu-id="974b5-126">**從合規性分數登入合規性管理員**：如果使用者已登入合規性分數，並選取連結以移至合規性管理員，使用者就不需要重新登入。</span><span class="sxs-lookup"><span data-stu-id="974b5-126">**Signing in to Compliance Manager from Compliance Score**: if a user is signed in to Compliance Score and selects a link to go to Compliance Manager, the user won't have to sign in again.</span></span> <span data-ttu-id="974b5-127">按一下連結後，在瀏覽器中會開啟一個新的索引標籤，其上會有一個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="974b5-127">After clicking the link, a new tab opens in your browser featuring a dialogue box.</span></span> <span data-ttu-id="974b5-128">在標頭為「已是 Microsoft cloud services 客戶」的上方區段中？</span><span class="sxs-lookup"><span data-stu-id="974b5-128">In the top section with the header, "Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="974b5-129">登入您的帳戶，選取 [登**入**] 按鈕，以自動登入合規性管理員。</span><span class="sxs-lookup"><span data-stu-id="974b5-129">Sign in to your account," select the **Sign In** button to automatically sign in to Compliance Manager.</span></span>

## <a name="known-issues-in-compliance-score-preview"></a><span data-ttu-id="974b5-130">合規性分數中的已知問題（預覽）</span><span class="sxs-lookup"><span data-stu-id="974b5-130">Known issues in Compliance Score (Preview)</span></span>

<span data-ttu-id="974b5-131">下列章節涵蓋相容性分數的發行版本本中，待解決的已知問題。</span><span class="sxs-lookup"><span data-stu-id="974b5-131">The following sections cover known issues to be resolved in upcoming releases of Compliance Score.</span></span>

### <a name="long-load-times-for-non-admin-users"></a><span data-ttu-id="974b5-132">非系統管理使用者的長載入時間</span><span class="sxs-lookup"><span data-stu-id="974b5-132">Long load times for non-admin users</span></span>
<span data-ttu-id="974b5-133">合規性分數當嘗試登入時，保留非系統管理員角色角色的使用者可能會經歷很長的載入時間。</span><span class="sxs-lookup"><span data-stu-id="974b5-133">Compliance Score users who hold roles other than an admin role may experience long load times when trying to a sign in.</span></span> <span data-ttu-id="974b5-134">重新整理瀏覽器將會解決此問題。</span><span class="sxs-lookup"><span data-stu-id="974b5-134">Refreshing your browser will resolve this issue.</span></span> <span data-ttu-id="974b5-135">深入瞭解[合規性分數角色](compliance-score-setup.md#set-user-permissions-and-assign-roles)。</span><span class="sxs-lookup"><span data-stu-id="974b5-135">Learn more about [Compliance Score roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="974b5-136">支援的瀏覽器</span><span class="sxs-lookup"><span data-stu-id="974b5-136">Supported browsers</span></span>

- <span data-ttu-id="974b5-137">支援最新版本的 Microsoft Edge、Chrome 和 Safari。</span><span class="sxs-lookup"><span data-stu-id="974b5-137">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="974b5-138">重新整理瀏覽器之後，有時候不會出現更新的資料。</span><span class="sxs-lookup"><span data-stu-id="974b5-138">Updated data sometimes doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="974b5-139">不支援 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="974b5-139">Internet Explorer is not supported.</span></span>
