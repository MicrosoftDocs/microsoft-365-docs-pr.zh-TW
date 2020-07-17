---
title: 緩慢的郵件流程規則深入解析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 5/3/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解安全性 & 規範中心的郵件流程儀表板中的慢速郵件流程規則。
ms.openlocfilehash: 52ddb6bf5ab6998309fd3122c59636c14b3da1dd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819361"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="ead7c-103">緩慢的郵件流程規則深入解析</span><span class="sxs-lookup"><span data-stu-id="ead7c-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="ead7c-104">低效的郵件流程規則（也稱為傳輸規則）可能會導致組織的郵件流程延遲。</span><span class="sxs-lookup"><span data-stu-id="ead7c-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="ead7c-105">這種洞察力可報告影響組織郵件流程的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="ead7c-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="ead7c-106">這些規則類型的範例包括：</span><span class="sxs-lookup"><span data-stu-id="ead7c-106">Examples of these types of rules are:</span></span>

- <span data-ttu-id="ead7c-107">使用的條件**是**大型群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ead7c-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="ead7c-108">使用複雜正則運算式（RegEx）模式對應的條件。</span><span class="sxs-lookup"><span data-stu-id="ead7c-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="ead7c-109">在附件中使用內容檢查的條件。</span><span class="sxs-lookup"><span data-stu-id="ead7c-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="ead7c-110">這種洞察力可協助您識別及微調郵件流程規則，以協助減少郵件流程延遲。</span><span class="sxs-lookup"><span data-stu-id="ead7c-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![慢速郵件流程會在安全性 & 規範中心的郵件流程儀表板中進行洞察](../../media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="ead7c-112">當您按一下 [**查看詳細資料**] 時，會顯示一個彈出窗格，您可以在其中查看規則。</span><span class="sxs-lookup"><span data-stu-id="ead7c-112">When you click **View details**, a flyout pane appears where you can review the rule.</span></span> <span data-ttu-id="ead7c-113">在飛入窗格中，也可以按一下 [ **view sample messages** ]，以查看規則會影響的郵件類型。</span><span class="sxs-lookup"><span data-stu-id="ead7c-113">In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![按一下慢速郵件流程中的 [查看詳細資料] 之後的浮出窗格郵件流程儀表板中的洞察力](../../media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="related-topics"></a><span data-ttu-id="ead7c-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="ead7c-115">Related topics</span></span>

<span data-ttu-id="ead7c-116">如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="ead7c-116">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
