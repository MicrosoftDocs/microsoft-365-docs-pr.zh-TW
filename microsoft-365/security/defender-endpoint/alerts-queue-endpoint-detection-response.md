---
title: Microsoft Defender Security Center 中的警示佇列
ms.reviewer: ''
description: 查看及管理 Microsoft Defender Security Center 中呈現的警示
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.date: 09/03/2018
ms.technology: mde
ms.openlocfilehash: d40fc887f26dfe62e05f7ee6ac7bbbb8ac45a402
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059963"
---
# <a name="alerts-queue-in-microsoft-defender-security-center"></a><span data-ttu-id="89284-103">Microsoft Defender Security Center 中的警示佇列</span><span class="sxs-lookup"><span data-stu-id="89284-103">Alerts queue in Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="89284-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="89284-104">**Applies to:**</span></span>
- [<span data-ttu-id="89284-105">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="89284-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="89284-106">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="89284-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="89284-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="89284-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="89284-108">瞭解您可以如何查看和管理佇列，以便您可以有效調查實體（如裝置、檔案或使用者帳戶）上所看到的威脅。</span><span class="sxs-lookup"><span data-stu-id="89284-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="89284-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="89284-109">In this section</span></span>
<span data-ttu-id="89284-110">主題</span><span class="sxs-lookup"><span data-stu-id="89284-110">Topic</span></span> | <span data-ttu-id="89284-111">描述</span><span class="sxs-lookup"><span data-stu-id="89284-111">Description</span></span> 
:---|:---
[<span data-ttu-id="89284-112">查看和組織提醒佇列</span><span class="sxs-lookup"><span data-stu-id="89284-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="89284-113">顯示網路中已標示的警示清單。</span><span class="sxs-lookup"><span data-stu-id="89284-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="89284-114">管理提醒</span><span class="sxs-lookup"><span data-stu-id="89284-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="89284-115">瞭解如何管理提醒，例如變更其狀態、將其指派給安全性作業成員，以及查看警示的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="89284-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="89284-116">調查警示</span><span class="sxs-lookup"><span data-stu-id="89284-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="89284-117">調查影響網路的警示，瞭解其含義及解決方法。</span><span class="sxs-lookup"><span data-stu-id="89284-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="89284-118">調查檔</span><span class="sxs-lookup"><span data-stu-id="89284-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="89284-119">調查與特定警示、行為或事件相關聯之檔案的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="89284-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="89284-120">調查裝置</span><span class="sxs-lookup"><span data-stu-id="89284-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="89284-121">調查與特定警示、行為或事件相關聯之裝置的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="89284-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="89284-122">調查 IP 位址</span><span class="sxs-lookup"><span data-stu-id="89284-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="89284-123">檢查您網路中裝置間可能的通訊和外部網際網路通訊協定 (IP) 位址。</span><span class="sxs-lookup"><span data-stu-id="89284-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="89284-124">調查網域</span><span class="sxs-lookup"><span data-stu-id="89284-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="89284-125">調查網域，查看您網路中的裝置和伺服器是否已與已知惡意的網域進行通訊。</span><span class="sxs-lookup"><span data-stu-id="89284-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="89284-126">調查使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="89284-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="89284-127">識別具有最活躍之警示的使用者帳戶，並調查可能遭到破壞之認證的案例。</span><span class="sxs-lookup"><span data-stu-id="89284-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  


