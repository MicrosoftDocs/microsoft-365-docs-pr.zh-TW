---
title: Microsoft 365 的 Privileged Access Management
description: 瞭解如何跨 Microsoft 365 設定有問必答風險功能。
keywords: Microsoft 365，內幕人士風險，合規性
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
ms.openlocfilehash: 7fecfd7088f65effd6addddc51c1236c7b2af191
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613793"
---
# <a name="privileged-access-management-in-microsoft-365"></a><span data-ttu-id="8727e-104">Microsoft 365 的 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="8727e-104">Privileged access management in Microsoft 365</span></span>

<span data-ttu-id="8727e-105">在 Microsoft Exchange Online 中，某些使用者對機密資訊或重要網路設定設定的存取權，對遭到損害的帳戶或內部威脅活動可能是一種可能的路徑。</span><span class="sxs-lookup"><span data-stu-id="8727e-105">Having standing access by some users to sensitive information or critical network configuration settings in Microsoft Exchange Online is a potential pathway for compromised accounts or internal threat activities.</span></span> <span data-ttu-id="8727e-106">「特殊設定管理」可協助保護您的組織不會遭到破壞，並可限制存取機密資料或存取重要的設定設定，以協助滿足法規遵從性最佳作法。</span><span class="sxs-lookup"><span data-stu-id="8727e-106">Privileged access management helps protect your organization from breaches and helps to meet compliance best practices by limiting standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="8727e-107">不是具有持續存取權的系統管理員，需要提升許可權的工作才會執行即時存取規則。</span><span class="sxs-lookup"><span data-stu-id="8727e-107">Instead of administrators having constant access, just-in-time access rules are implemented for tasks that need elevated permissions.</span></span> <span data-ttu-id="8727e-108">在 Microsoft 365 中啟用 Exchange Online 的「特殊存取權存取」功能可讓您的組織以零為起始的許可權運作，並提供防禦受影響的系統管理存取弱點。</span><span class="sxs-lookup"><span data-stu-id="8727e-108">Enabling privileged access management for Exchange Online in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

## <a name="configure-privileged-access-management-for-microsoft-365"></a><span data-ttu-id="8727e-109">設定 Microsoft 365 的特殊許可權存取管理</span><span class="sxs-lookup"><span data-stu-id="8727e-109">Configure privileged access management for Microsoft 365</span></span>

<span data-ttu-id="8727e-110">使用下列步驟為您的組織設定特殊許可權存取管理：</span><span class="sxs-lookup"><span data-stu-id="8727e-110">Use the following steps to configure privileged access management for your organization:</span></span>

![內部人員風險方案的特殊許可權存取管理步驟](../media/ir-solution-pam-steps.png)

1. <span data-ttu-id="8727e-112">深入瞭解 Microsoft 365 中的特殊[許可權存取管理](privileged-access-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8727e-112">Learn about [privileged access management](privileged-access-management-overview.md) in Microsoft 365</span></span>
2. <span data-ttu-id="8727e-113">建立 [核准者的群組](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span><span class="sxs-lookup"><span data-stu-id="8727e-113">Create an [approver's group](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span></span>
3. <span data-ttu-id="8727e-114">啟用特殊 [許可權存取管理](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="8727e-114">Enable [privileged access management](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span></span>
4. <span data-ttu-id="8727e-115">建立 [存取原則](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span><span class="sxs-lookup"><span data-stu-id="8727e-115">Create an [access policy](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span></span>
5. <span data-ttu-id="8727e-116">提交/核准 [許可權存取要求](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span><span class="sxs-lookup"><span data-stu-id="8727e-116">Submit/approve [privileged access requests](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span></span>

## <a name="more-information-about-privileged-access-management"></a><span data-ttu-id="8727e-117">有關特殊許可權存取管理的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="8727e-117">More information about privileged access management</span></span>

- [<span data-ttu-id="8727e-118">有關特殊許可權存取管理的常見問題</span><span class="sxs-lookup"><span data-stu-id="8727e-118">Frequently asked questions about privileged access management</span></span>](privileged-access-management-overview.md#frequently-asked-questions)