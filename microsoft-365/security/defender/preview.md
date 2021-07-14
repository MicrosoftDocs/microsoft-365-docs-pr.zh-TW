---
title: Microsoft 365 Defender 中的預覽功能
description: 了解 Microsoft 365 安全性中心的新功能。
keywords: 預覽、全新、m365 安全性、安全性、365、功能
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 088dbd16c3667331843ff934c80f85aa8d3a837f
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430813"
---
# <a name="microsoft-365-defender-preview-features"></a><span data-ttu-id="07c8a-104">Microsoft 365 Defender 預覽功能</span><span class="sxs-lookup"><span data-stu-id="07c8a-104">Microsoft 365 Defender preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="07c8a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="07c8a-105">**Applies to:**</span></span>
- <span data-ttu-id="07c8a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07c8a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="07c8a-107">Microsoft 365 Defender 服務會持續更新，以包含新功能增強功能及功能。</span><span class="sxs-lookup"><span data-stu-id="07c8a-107">The Microsoft 365 Defender service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="07c8a-108">深入瞭解 Microsoft 365 Defender 預覽版本中的新功能，並透過開啟預覽體驗，以嘗試即將推出的功能。</span><span class="sxs-lookup"><span data-stu-id="07c8a-108">Learn about new features in the Microsoft 365 Defender preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="07c8a-109">如需一般可用之新功能的詳細資訊，請參閱[Microsoft 365 Defender 的新](whats-new.md)功能。</span><span class="sxs-lookup"><span data-stu-id="07c8a-109">For more information on new capabilities that are generally available, see [What's new in Microsoft 365 Defender](whats-new.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="07c8a-110">您需要瞭解的事項</span><span class="sxs-lookup"><span data-stu-id="07c8a-110">What you need to know</span></span>

<span data-ttu-id="07c8a-111">在使用 public preview 中的功能時，這些功能包括：</span><span class="sxs-lookup"><span data-stu-id="07c8a-111">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="07c8a-112">可能具有限制或有限的功能。</span><span class="sxs-lookup"><span data-stu-id="07c8a-112">May have restricted or limited functionality.</span></span> <span data-ttu-id="07c8a-113">例如，此功能可能只適用于一個平臺。</span><span class="sxs-lookup"><span data-stu-id="07c8a-113">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="07c8a-114">一般會透過功能變更， (正式) 使用。</span><span class="sxs-lookup"><span data-stu-id="07c8a-114">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="07c8a-115">Microsoft 完全支援。</span><span class="sxs-lookup"><span data-stu-id="07c8a-115">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="07c8a-116">只能在選取的地理區域或雲端環境中使用。</span><span class="sxs-lookup"><span data-stu-id="07c8a-116">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="07c8a-117">例如，該功能可能不存在於政府雲端中。</span><span class="sxs-lookup"><span data-stu-id="07c8a-117">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="07c8a-118">預覽中的個別功能可能會有更多的使用和支援限制。</span><span class="sxs-lookup"><span data-stu-id="07c8a-118">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="07c8a-119">如果是的話，此資訊通常會注明在功能檔中。</span><span class="sxs-lookup"><span data-stu-id="07c8a-119">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="07c8a-120">預覽版本會以標準的支援層級提供，並且可用於實際執行環境。</span><span class="sxs-lookup"><span data-stu-id="07c8a-120">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="required-permissions"></a><span data-ttu-id="07c8a-121">必要權限</span><span class="sxs-lookup"><span data-stu-id="07c8a-121">Required permissions</span></span>

<span data-ttu-id="07c8a-122">已指派下列 Azure Active Directory 的帳戶 (Azure AD) 角色可以開啟 Microsoft 365 Defender 預覽功能：</span><span class="sxs-lookup"><span data-stu-id="07c8a-122">Accounts assigned the following Azure Active Directory (Azure AD) roles can turn on Microsoft 365 Defender Preview features:</span></span>

- <span data-ttu-id="07c8a-123">全域管理員</span><span class="sxs-lookup"><span data-stu-id="07c8a-123">Global administrator</span></span>
- <span data-ttu-id="07c8a-124">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="07c8a-124">Security administrator</span></span>
- <span data-ttu-id="07c8a-125">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="07c8a-125">Security Operator</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="07c8a-126">開啟預覽功能</span><span class="sxs-lookup"><span data-stu-id="07c8a-126">Turn on preview features</span></span>

<span data-ttu-id="07c8a-127">您將可以存取即將推出的功能，您可以在其中提供意見反應，以協助改善整體體驗，使其成為一般可用功能。</span><span class="sxs-lookup"><span data-stu-id="07c8a-127">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="07c8a-128">開啟預覽體驗設定，成為第一批嘗試即將推出的功能的人。</span><span class="sxs-lookup"><span data-stu-id="07c8a-128">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="07c8a-129">在功能窗格中，選取 **[設定]**。</span><span class="sxs-lookup"><span data-stu-id="07c8a-129">In the navigation pane, select **Settings**.</span></span>
2. <span data-ttu-id="07c8a-130">選取 [ **Microsoft 365 Defender**]。</span><span class="sxs-lookup"><span data-stu-id="07c8a-130">Select **Microsoft 365 Defender**.</span></span>
3. <span data-ttu-id="07c8a-131">選取 **預覽功能** > **開啟預覽功能**。</span><span class="sxs-lookup"><span data-stu-id="07c8a-131">Select **Preview features** > **Turn on preview features**.</span></span> 
4. <span data-ttu-id="07c8a-132">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="07c8a-132">Select **Save**.</span></span>

<span data-ttu-id="07c8a-133">當您看到 **[開啟預覽功能]** 核取方塊已選取時，您就會知道您已開啟預覽功能。</span><span class="sxs-lookup"><span data-stu-id="07c8a-133">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="07c8a-134">預覽功能</span><span class="sxs-lookup"><span data-stu-id="07c8a-134">Preview features</span></span>

<span data-ttu-id="07c8a-135">目前預覽版提供下列功能和增強功能：</span><span class="sxs-lookup"><span data-stu-id="07c8a-135">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="07c8a-136">**[依威脅標記查看報告](threat-analytics.md#view-reports-per-threat-tags)** -威脅標記可協助您將重點放在特定威脅類別上，並複查最相關的報告。</span><span class="sxs-lookup"><span data-stu-id="07c8a-136">**[View reports per threat tags](threat-analytics.md#view-reports-per-threat-tags)** - Threat tags help you focus on specific threat categories and review the most relevant reports.</span></span>
- <span data-ttu-id="07c8a-137">**[流式 API](../defender-endpoint/raw-data-export.md)** Microsoft 365 Defender 支援透過 Advanced 搜尋向事件中樞和/或 Azure 儲存體帳戶，處理所有可用的事件。</span><span class="sxs-lookup"><span data-stu-id="07c8a-137">**[Streaming API](../defender-endpoint/raw-data-export.md)** - Microsoft 365 Defender supports streaming all the events available through Advanced Hunting to an Event Hubs and/or Azure storage account.</span></span>
- <span data-ttu-id="07c8a-138">**[Microsoft 365 Defender APIs](api-overview.md)** -最上層 Microsoft 365 Defender APIs 可讓您根據共用的事件和高級搜尋表來自動化工作流程。</span><span class="sxs-lookup"><span data-stu-id="07c8a-138">**[Microsoft 365 Defender APIs](api-overview.md)** - The top-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span> 
- <span data-ttu-id="07c8a-139">**[在高級搜尋中採取行動](advanced-hunting-take-action.md)** -快速包含威脅或處理您在 [高級搜尋](advanced-hunting-overview.md)中所發現的受損資產。</span><span class="sxs-lookup"><span data-stu-id="07c8a-139">**[Take action in advanced hunting](advanced-hunting-take-action.md)** - Quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md).</span></span>
- <span data-ttu-id="07c8a-140">**[In 入口架構參考](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** -直接在「安全性中心」取得高級搜尋架構表格的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="07c8a-140">**[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - Get information about advanced hunting schema tables directly in the security center.</span></span> <span data-ttu-id="07c8a-141">除了資料表和欄描述之外，此參考還包含支援的事件種類 (`ActionType` 值) 和範例查詢。</span><span class="sxs-lookup"><span data-stu-id="07c8a-141">In addition to table and column descriptions, this reference includes supported event types (`ActionType` values) and sample queries.</span></span>
- <span data-ttu-id="07c8a-142">**[DeviceFromIP () 函數](advanced-hunting-devicefromip-function.md)** -取得在指定的時間範圍內，哪些裝置已被指派特定的 IP 位址或位址的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="07c8a-142">**[DeviceFromIP() function](advanced-hunting-devicefromip-function.md)** - Get information about which devices have been assigned a specific IP address or addresses at a given time range.</span></span>
