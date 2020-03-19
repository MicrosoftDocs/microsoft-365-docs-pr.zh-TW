---
title: Microsoft 合規性分數更新
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
description: M365 規範中心中的一項功能，可協助簡化及自動化風險評估的後續更新的詳細資料。
ms.openlocfilehash: c46b70d0762a805e4ecfc83b70173c56d21a3933
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857752"
---
# <a name="microsoft-compliance-score-preview-updates"></a><span data-ttu-id="09c2a-103">Microsoft 合規性分數（預覽）更新</span><span class="sxs-lookup"><span data-stu-id="09c2a-103">Microsoft Compliance Score (Preview) updates</span></span>

 <span data-ttu-id="09c2a-104">本文提供對[Microsoft 合規性分數](compliance-score.md)和[Microsoft 合規性管理員](compliance-manager-overview.md)未來更新的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="09c2a-104">This article provides details about future updates to [Microsoft Compliance Score](compliance-score.md) and [Microsoft Compliance Manager](compliance-manager-overview.md).</span></span> <span data-ttu-id="09c2a-105">深入瞭解其[關聯](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)性。</span><span class="sxs-lookup"><span data-stu-id="09c2a-105">Learn more about their [relationship](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).</span></span>

## <a name="improved-template-creation-and-update-processes"></a><span data-ttu-id="09c2a-106">改進的範本建立和更新程式</span><span class="sxs-lookup"><span data-stu-id="09c2a-106">Improved template creation and update processes</span></span>

<span data-ttu-id="09c2a-107">我們正在簡化針對評估的匯入、匯出及修改範本的處理常式。</span><span class="sxs-lookup"><span data-stu-id="09c2a-107">We're simplifying the process for importing, exporting, and modifying templates for assessments.</span></span> <span data-ttu-id="09c2a-108">新的經驗可讓您更輕鬆地將您自己的評估帶入法規遵從性分數並保持更新。</span><span class="sxs-lookup"><span data-stu-id="09c2a-108">The new experience will make it easier for you to bring your own assessments into Compliance Score and keep them updated.</span></span>

### <a name="the-current-process"></a><span data-ttu-id="09c2a-109">目前的處理常式</span><span class="sxs-lookup"><span data-stu-id="09c2a-109">The current process</span></span>

<span data-ttu-id="09c2a-110">在合規性管理員中建立範本的方式有兩種。</span><span class="sxs-lookup"><span data-stu-id="09c2a-110">There are two ways to create a template in Compliance Manager.</span></span> <span data-ttu-id="09c2a-111">您可以複製現有的範本，也可以將範本資料從 Excel 試算表匯入新的範本。</span><span class="sxs-lookup"><span data-stu-id="09c2a-111">You can copy an existing template, or you can import template data from an Excel spreadsheet into a new template.</span></span> <span data-ttu-id="09c2a-112">在 [**範本**] 頁面上，選取 [**新增範本**]，以建立全新的範本，方法是輸入名稱、選取 [維度]，然後使用特定的格式和架構上傳 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="09c2a-112">From your **Templates** page, you select **+ Add template** to create a brand new template by entering a name, selecting dimensions, and uploading an Excel file with a specific format and schema.</span></span> <span data-ttu-id="09c2a-113">或者，您可以選取 [**從現有範本複製**] 方塊，選取要複製的範本，然後驗證尺寸，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="09c2a-113">Or you can check the **Copy from an existing template** box, select a template to copy, and verify dimensions, as shown in the image below.</span></span> <span data-ttu-id="09c2a-114">若要自訂您的範本，必須先選取 [**新增自訂控制項**之後建立範本]，即可開始執行[多步驟](working-with-compliance-manager.md#templates)程式。</span><span class="sxs-lookup"><span data-stu-id="09c2a-114">Customizing your template requires a [multi-step process](working-with-compliance-manager.md#templates) that begins by selecting **Add custom control** after creating your template.</span></span>

<span data-ttu-id="09c2a-115">![合規性分數-儀表板](../media/compliance-score-template-update-old.png "目前的範本複製程式")</span><span class="sxs-lookup"><span data-stu-id="09c2a-115">![Compliance Score - dashboard](../media/compliance-score-template-update-old.png "Current template copy process")</span></span>

### <a name="whats-changing"></a><span data-ttu-id="09c2a-116">變更的功能</span><span class="sxs-lookup"><span data-stu-id="09c2a-116">What's changing</span></span>

<span data-ttu-id="09c2a-117">我們要讓您更輕鬆地建立新的範本。</span><span class="sxs-lookup"><span data-stu-id="09c2a-117">We're making it easier for you to create new templates.</span></span> <span data-ttu-id="09c2a-118">在單一步驟**擴充**過程中，您可以將動作和控制項的試算表新增至現有的 Microsoft 範本，以製作您自己的自訂版本。</span><span class="sxs-lookup"><span data-stu-id="09c2a-118">In a one-step **extension** process, you can add a spreadsheet with your actions and controls to an existing Microsoft template to make your own customized version.</span></span> <span data-ttu-id="09c2a-119">在 [**範本**] 飛入窗格上，選取 [**從通用範本建立副檔名**] 核取方塊，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="09c2a-119">On the **Template** flyout pane, select the **Create extension from global template** checkbox, as shown in the image below.</span></span> <span data-ttu-id="09c2a-120">然後，您會使用新的 Excel 格式（而不是目前的複雜格式）來新增自訂。</span><span class="sxs-lookup"><span data-stu-id="09c2a-120">You'll then add customizations using a new Excel format that is less complex than the current one.</span></span> <span data-ttu-id="09c2a-121">這個新程式會取代**現有範本**的目前副本，並**新增自訂控制項**函數。</span><span class="sxs-lookup"><span data-stu-id="09c2a-121">This new process replaces the current **Copy from an existing template** and **Add custom control** functions.</span></span>

<span data-ttu-id="09c2a-122">每次使用下列所述的版本設定程式更新原始評估時，您的自訂評估會繼承這些更新，並保留您的自訂控制項。</span><span class="sxs-lookup"><span data-stu-id="09c2a-122">Each time the original assessment is updated through the versioning process outlined below, your customized assessment will inherit those updates and keep your custom controls.</span></span>

<span data-ttu-id="09c2a-123">我們也讓您更容易修改現有的範本。</span><span class="sxs-lookup"><span data-stu-id="09c2a-123">We're also making it easier to modify your own existing templates.</span></span> <span data-ttu-id="09c2a-124">您可以匯出範本，在相同的活頁簿中進行變更，然後使用儲存的編輯匯入。</span><span class="sxs-lookup"><span data-stu-id="09c2a-124">You can export your template, make changes in the same workbook, then import it with your edits saved.</span></span>

<span data-ttu-id="09c2a-125">![合規性分數-儀表板](../media/compliance-score-template-update-new.png "新的範本建立過程")</span><span class="sxs-lookup"><span data-stu-id="09c2a-125">![Compliance Score - dashboard](../media/compliance-score-template-update-new.png "New template creation process")</span></span>

## <a name="versioning-notice-and-control"></a><span data-ttu-id="09c2a-126">版本設定通知和控制</span><span class="sxs-lookup"><span data-stu-id="09c2a-126">Versioning notice and control</span></span>

<span data-ttu-id="09c2a-127">您的組織將會在下一個版本的合規性分數和合規性管理員中接收更新的評估，以協助您與認證和法規更新相符。</span><span class="sxs-lookup"><span data-stu-id="09c2a-127">Your organization will receive updated assessments in the next release of Compliance Score and Compliance Manager to help you align with certification and regulation updates.</span></span>

<span data-ttu-id="09c2a-128">接下來，每當有可供評估的範本或改進動作使用更新時，提醒圖示會通知您已準備好更新。</span><span class="sxs-lookup"><span data-stu-id="09c2a-128">Going forward, whenever an update is available for an assessment's template or an improvement action, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="09c2a-129">當您按一下該圖示時，會快顯視窗來說明更新，並提示您接受。</span><span class="sxs-lookup"><span data-stu-id="09c2a-129">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="09c2a-130">以下是評估的版本設定警示範例：</span><span class="sxs-lookup"><span data-stu-id="09c2a-130">Below is an example of the versioning alert for an assessment:</span></span>

<span data-ttu-id="09c2a-131">![合規性分數-版本設定警示](../media/compliance-score-assessment-version.png "評估版本更新警示")</span><span class="sxs-lookup"><span data-stu-id="09c2a-131">![Compliance Score - versioning alert](../media/compliance-score-assessment-version.png "Assessment version update alert")</span></span>

<span data-ttu-id="09c2a-132">選取警示圖示會顯示彈出窗格，說明更新並提示您接受：</span><span class="sxs-lookup"><span data-stu-id="09c2a-132">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept:</span></span>

<span data-ttu-id="09c2a-133">![合規性分數-版本快顯視窗](../media/compliance-score-assessment-version-accept.png "評估更新確認窗格")</span><span class="sxs-lookup"><span data-stu-id="09c2a-133">![Compliance Score - versioning flyout](../media/compliance-score-assessment-version-accept.png "Assessment update confirmation pane")</span></span>

## <a name="common-actions-will-synch-status-across-groups"></a><span data-ttu-id="09c2a-134">一般動作會在群組間同步處理狀態</span><span class="sxs-lookup"><span data-stu-id="09c2a-134">Common actions will synch status across groups</span></span>

<span data-ttu-id="09c2a-135">如果您的組織有多個評估群組，**技術**動作的行為（也就是影響整個組織的動作）將會變更。</span><span class="sxs-lookup"><span data-stu-id="09c2a-135">If your organization has multiple groups of assessments, the behavior of **Technical** actions (that is, actions affecting your entire organization) will change.</span></span> <span data-ttu-id="09c2a-136">群組間的任何重複動作都會合並成一個單一的動作。</span><span class="sxs-lookup"><span data-stu-id="09c2a-136">Any duplicate actions across groups will be combined into one single action.</span></span> <span data-ttu-id="09c2a-137">該單一動作會包含重複的版本中所有上傳的記事及證據。</span><span class="sxs-lookup"><span data-stu-id="09c2a-137">That single action will contain all uploaded notes and evidence from the duplicate versions.</span></span> <span data-ttu-id="09c2a-138">使用此變更，當技術動作屬於相同群組時，其行為會與目前相同。</span><span class="sxs-lookup"><span data-stu-id="09c2a-138">With this change, technical actions will behave as they currently do when they belong to the same group.</span></span> <span data-ttu-id="09c2a-139">在一個群組或評估中對動作所做的任何變更現在都會反映在所有的實例中。</span><span class="sxs-lookup"><span data-stu-id="09c2a-139">Any change made to the action in one group or assessment will now be reflected in all instances.</span></span> <span data-ttu-id="09c2a-140">「 **實施」狀態**、「**實施 Dat**」、「**測試狀態**」及「**測試日期** 」會反映最新的更新。</span><span class="sxs-lookup"><span data-stu-id="09c2a-140">The **Implementation Status**, **Implementation Dat**, **Test Status**, and **Test Date** will reflect the most recent updates.</span></span>

## <a name="language-support"></a><span data-ttu-id="09c2a-141">語言支援</span><span class="sxs-lookup"><span data-stu-id="09c2a-141">Language support</span></span>

<span data-ttu-id="09c2a-142">由於英文：中文（簡體）、中文（繁體）、法文、德文、義大利文、日文、韓文、葡萄牙文（巴西）、俄語及西班牙文，下列語言仍提供合規性分數。</span><span class="sxs-lookup"><span data-stu-id="09c2a-142">Compliance Score will now be available in the following languages in addition to English: Chinese (Simplified), Chinese (Traditional), French, German, Italian, Japanese, Korean, Portuguese (Brazil), Russian, and Spanish.</span></span>
