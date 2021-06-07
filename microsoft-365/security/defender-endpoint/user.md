---
title: 使用者資源類型
description: 檢索與使用者相關的最近 Microsoft Defender 的端點警示。
keywords: api、graph api、支援的 api、get、警示、最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 39b73772bcc626590aa784bb5b21357f66229816
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772134"
---
# <a name="user-resource-type"></a><span data-ttu-id="b5072-104">使用者資源類型</span><span class="sxs-lookup"><span data-stu-id="b5072-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b5072-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b5072-105">**Applies to:**</span></span>
- [<span data-ttu-id="b5072-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b5072-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b5072-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5072-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b5072-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b5072-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b5072-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b5072-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="b5072-110">方法</span><span class="sxs-lookup"><span data-stu-id="b5072-110">Method</span></span>|<span data-ttu-id="b5072-111">傳回類型</span><span class="sxs-lookup"><span data-stu-id="b5072-111">Return Type</span></span> |<span data-ttu-id="b5072-112">描述</span><span class="sxs-lookup"><span data-stu-id="b5072-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="b5072-113">列出使用者相關的警示</span><span class="sxs-lookup"><span data-stu-id="b5072-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="b5072-114">[警示](alerts.md) 集合</span><span class="sxs-lookup"><span data-stu-id="b5072-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="b5072-115">列出與 [使用者](user.md)相關聯的所有警示。</span><span class="sxs-lookup"><span data-stu-id="b5072-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="b5072-116">清單使用者相關裝置</span><span class="sxs-lookup"><span data-stu-id="b5072-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="b5072-117">[電腦](machine.md) 集合</span><span class="sxs-lookup"><span data-stu-id="b5072-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="b5072-118">列出 [使用者](user.md)已登入的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="b5072-118">List all the devices that were logged on by a [user](user.md).</span></span>
