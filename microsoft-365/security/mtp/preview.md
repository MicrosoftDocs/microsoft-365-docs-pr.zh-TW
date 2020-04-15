---
title: Microsoft 威脅防護中的預覽功能
description: 深入瞭解 Microsoft 365 安全性中的新功能
keywords: 預覽、新的 m365 安全性、安全性、365、功能
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c4facaac82ff8486c0c3a846e4f577c7888a3161
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503980"
---
# <a name="microsoft-threat-protection-preview-features"></a><span data-ttu-id="705a7-104">Microsoft 威脅防護預覽功能</span><span class="sxs-lookup"><span data-stu-id="705a7-104">Microsoft Threat Protection preview features</span></span>

<span data-ttu-id="705a7-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="705a7-105">**Applies to:**</span></span>
- <span data-ttu-id="705a7-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="705a7-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="705a7-107">Microsoft 威脅防護服務會不斷更新，以包含新功能增強功能及功能。</span><span class="sxs-lookup"><span data-stu-id="705a7-107">The Microsoft Threat Protection service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="705a7-108">深入瞭解 Microsoft 威脅防護預覽版本中的新功能，並透過開啟預覽體驗，以嘗試即將推出的功能。</span><span class="sxs-lookup"><span data-stu-id="705a7-108">Learn about new features in the Microsoft Threat Protection preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="705a7-109">如需更多公開推出的全新功能資訊，請查看 [Microsoft 威脅防護新增功能](whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="705a7-109">For more information on new capabilities that are generally available, see [What's new in Microsoft Threat Protection](whats-new.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="705a7-110">開啟預覽功能</span><span class="sxs-lookup"><span data-stu-id="705a7-110">Turn on preview features</span></span>
<span data-ttu-id="705a7-111">您將可以存取即將推出的功能，您可以在其中提供意見反應，以協助改善整體體驗，使其成為一般可用功能。</span><span class="sxs-lookup"><span data-stu-id="705a7-111">You'll have access to upcoming features which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="705a7-112">開啟預覽體驗設定，以進行第一次嘗試後續功能。</span><span class="sxs-lookup"><span data-stu-id="705a7-112">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="705a7-113">在功能窗格中，選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="705a7-113">In the navigation pane, select **Settings**.</span></span>

2. <span data-ttu-id="705a7-114">選取 [ **Microsoft 威脅防護**]。</span><span class="sxs-lookup"><span data-stu-id="705a7-114">Select **Microsoft Threat Protection**.</span></span>


3. <span data-ttu-id="705a7-115">選取 [**預覽功能** > ]**開啟預覽功能**。</span><span class="sxs-lookup"><span data-stu-id="705a7-115">Select **Preview features** > **Turn on preview features**.</span></span> 

3. <span data-ttu-id="705a7-116">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="705a7-116">Select **Save**.</span></span>

<span data-ttu-id="705a7-117">當您看到已選取 [**開啟預覽功能**] 核取方塊時，您會知道已開啟預覽功能。</span><span class="sxs-lookup"><span data-stu-id="705a7-117">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="705a7-118">預覽功能</span><span class="sxs-lookup"><span data-stu-id="705a7-118">Preview features</span></span>
<span data-ttu-id="705a7-119">下列是目前可供預覽的功能和增強功能：</span><span class="sxs-lookup"><span data-stu-id="705a7-119">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="705a7-120">**[自訂](custom-detections-overview.md)** 偵測-使用高級搜尋查詢來建立規則，以定期搜尋侵犯行為和其他感興趣的專案。</span><span class="sxs-lookup"><span data-stu-id="705a7-120">**[Custom detections](custom-detections-overview.md)** — use advanced hunting queries to create rules that automatically search for breach activity and other items of interest at regular intervals.</span></span> <span data-ttu-id="705a7-121">符合查詢觸發警示和您指定的回應動作。</span><span class="sxs-lookup"><span data-stu-id="705a7-121">Matches to the queries trigger alerts and your specified response actions.</span></span>

- <span data-ttu-id="705a7-122">身分**[識別和應用程式表格](advanced-hunting-schema-tables.md)**--在高級搜尋架構中深入瞭解驗證事件、Active Directory 查詢和應用程式相關的活動與[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)、 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)和[AppFileEvents](advanced-hunting-appfileevents-table.md)表格。</span><span class="sxs-lookup"><span data-stu-id="705a7-122">**[Identity and app tables](advanced-hunting-schema-tables.md)** — get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
