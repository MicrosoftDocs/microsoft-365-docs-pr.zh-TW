---
title: Microsoft 365 中的內部人員風險管理
description: 瞭解如何設定 Microsoft 365 中的「有問必答風險管理」。
keywords: Microsoft 365，有問必答風險，合規性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: 3e057677b7d8ef4e74abe705bc3b23e8ea539853
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326756"
---
# <a name="insider-risk-management-in-microsoft-365"></a><span data-ttu-id="e7db0-104">Microsoft 365 中的內部人員風險管理</span><span class="sxs-lookup"><span data-stu-id="e7db0-104">Insider risk management in Microsoft 365</span></span>

<span data-ttu-id="e7db0-105">員工們在許多平臺和服務上都具有更多存取權，可建立、管理及共用資料。</span><span class="sxs-lookup"><span data-stu-id="e7db0-105">Increasingly, employees have more access to create, manage, and share data across a broad spectrum of platforms and services.</span></span> <span data-ttu-id="e7db0-106">在大多數的情況下，組織的資源和工具有限，可找出並減輕整個組織的風險，同時也符合規範需求和員工隱私權標準。</span><span class="sxs-lookup"><span data-stu-id="e7db0-106">In most cases, organizations have limited resources and tools to identify and mitigate organization-wide risks while also meeting compliance requirements and employee privacy standards.</span></span> <span data-ttu-id="e7db0-107">這些風險可能包括透過非有意 oversharing 或惡意目的，向外盜竊員工和組織外資訊的資料洩漏等資料竊取。</span><span class="sxs-lookup"><span data-stu-id="e7db0-107">These risks may include data theft by departing employees and data leaks of information outside your organization by accidental oversharing or malicious intent.</span></span>

<span data-ttu-id="e7db0-108">「內部使用者風險管理」 Microsoft 365 會使用完整的服務和協力廠商指標，協助您快速識別、會審和採取危險的使用者活動。</span><span class="sxs-lookup"><span data-stu-id="e7db0-108">Insider risk management in Microsoft 365 uses the full breadth of service and 3rd-party indicators to help you quickly identify, triage, and act on risky user activity.</span></span> <span data-ttu-id="e7db0-109">透過使用 Microsoft 365 和 Microsoft Graph 中的記錄，「有問必答風險管理」可讓您定義特定原則，以識別風險指示器，並採取行動以減輕這些風險。</span><span class="sxs-lookup"><span data-stu-id="e7db0-109">By using logs from Microsoft 365 and Microsoft Graph, insider risk management allows you to define specific policies to identify risk indicators and to take action to mitigate these risks.</span></span>

## <a name="configure-insider-risk-management-for-microsoft-365"></a><span data-ttu-id="e7db0-110">設定 Microsoft 365 的有問必答風險管理</span><span class="sxs-lookup"><span data-stu-id="e7db0-110">Configure insider risk management for Microsoft 365</span></span>

<span data-ttu-id="e7db0-111">使用下列步驟為您的組織設定有問必答風險管理：</span><span class="sxs-lookup"><span data-stu-id="e7db0-111">Use the following steps to configure insider risk management for your organization:</span></span>

![內部人員風險解決方案有問必答會冒險管理步驟](../media/ir-solution-ir-steps.png)

1. <span data-ttu-id="e7db0-113">深入瞭解 Microsoft 365 中的[內幕人士風險管理](insider-risk-management.md)</span><span class="sxs-lookup"><span data-stu-id="e7db0-113">Learn about [insider risk management](insider-risk-management.md) in Microsoft 365</span></span>
2. <span data-ttu-id="e7db0-114">規劃 [內部人員風險管理並驗證授權](insider-risk-management-plan.md)</span><span class="sxs-lookup"><span data-stu-id="e7db0-114">Plan for [insider risk management and verify licensing](insider-risk-management-plan.md)</span></span>
3. <span data-ttu-id="e7db0-115">設定 [有問必答風險管理設定](insider-risk-management-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e7db0-115">Configure [insider risk management settings](insider-risk-management-settings.md)</span></span>
4. <span data-ttu-id="e7db0-116">設定 & 連接器的 [許可權](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) 和 [原則必要條件](insider-risk-management-configure.md#step-4-configure-prerequisites-for-policies)</span><span class="sxs-lookup"><span data-stu-id="e7db0-116">Configure [permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) and [policy prerequisites & connectors](insider-risk-management-configure.md#step-4-configure-prerequisites-for-policies)</span></span>
5. <span data-ttu-id="e7db0-117">建立及設定 [有問必答風險管理原則](insider-risk-management-configure.md#step-6-create-an-insider-risk-management-policy)</span><span class="sxs-lookup"><span data-stu-id="e7db0-117">Create and configure [insider risk management policies](insider-risk-management-configure.md#step-6-create-an-insider-risk-management-policy)</span></span>

## <a name="more-information-about-insider-risk-management"></a><span data-ttu-id="e7db0-118">有關有問必答風險管理的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="e7db0-118">More information about insider risk management</span></span>

- [<span data-ttu-id="e7db0-119">管理有問必答風險原則</span><span class="sxs-lookup"><span data-stu-id="e7db0-119">Manage insider risk policies</span></span>](insider-risk-management-policies.md)
- [<span data-ttu-id="e7db0-120">調查有問必答風險活動</span><span class="sxs-lookup"><span data-stu-id="e7db0-120">Investigate insider risk activities</span></span>](insider-risk-management-activities.md)
- [<span data-ttu-id="e7db0-121">對內幕人士風險案例採取行動</span><span class="sxs-lookup"><span data-stu-id="e7db0-121">Act on insider risk cases</span></span>](insider-risk-management-cases.md)