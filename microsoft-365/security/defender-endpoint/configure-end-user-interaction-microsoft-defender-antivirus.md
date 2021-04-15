---
title: 設定使用者可以與 Microsoft Defender AV 互動的方式
description: 設定使用者與 Microsoft Defender AV 互動的方式、他們看到的通知，以及是否可以覆寫設定。
keywords: 端點、使用者、互動、通知、ui 鎖定模式、無周邊模式、隱藏介面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: df9f87e725575bad2f36cf7b016d257e766e523b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765224"
---
# <a name="configure-end-user-interaction-with-microsoft-defender-antivirus"></a><span data-ttu-id="a4874-104">使用 Microsoft Defender 防毒軟體設定使用者互動</span><span class="sxs-lookup"><span data-stu-id="a4874-104">Configure end-user interaction with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a4874-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a4874-105">**Applies to:**</span></span>

- [<span data-ttu-id="a4874-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a4874-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a4874-107">您可以設定網路上端點的使用者可以與 Microsoft Defender 防毒程式互動的方式。</span><span class="sxs-lookup"><span data-stu-id="a4874-107">You can configure how users of the endpoints on your network can interact with Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="a4874-108">這包括使用者看到的是 Microsoft Defender 防病毒介面、他們看到的通知，以及是否可以從本機覆寫全域部署的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="a4874-108">This includes whether they see the Microsoft Defender Antivirus interface, what notifications they see, and if they can locally override globally-deployed Group Policy settings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a4874-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="a4874-109">In this section</span></span>

<span data-ttu-id="a4874-110">主題</span><span class="sxs-lookup"><span data-stu-id="a4874-110">Topic</span></span> | <span data-ttu-id="a4874-111">描述</span><span class="sxs-lookup"><span data-stu-id="a4874-111">Description</span></span> 
---|---
[<span data-ttu-id="a4874-112">設定出現在端點上的通知</span><span class="sxs-lookup"><span data-stu-id="a4874-112">Configure notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md) | <span data-ttu-id="a4874-113">設定和自訂其他通知、自訂的通知文字，以及修復重新開機以進行修復的通知</span><span class="sxs-lookup"><span data-stu-id="a4874-113">Configure and customize additional notifications, customized text for notifications, and notifications about reboots for remediation</span></span>
[<span data-ttu-id="a4874-114">防止使用者看到 Microsoft Defender 防病毒使用者介面或與其互動</span><span class="sxs-lookup"><span data-stu-id="a4874-114">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="a4874-115">隱藏使用者的使用者介面</span><span class="sxs-lookup"><span data-stu-id="a4874-115">Hide the user interface from users</span></span>
[<span data-ttu-id="a4874-116">防止使用者在本機修改原則設定</span><span class="sxs-lookup"><span data-stu-id="a4874-116">Prevent users from locally modifying policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) | <span data-ttu-id="a4874-117">避免 (或允許) 使用者覆寫其個別端點上的原則設定</span><span class="sxs-lookup"><span data-stu-id="a4874-117">Prevent (or allow) users from overriding policy settings on their individual endpoints</span></span>