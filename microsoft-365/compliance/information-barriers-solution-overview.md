---
title: Microsoft 365 中的資訊障礙
description: 瞭解如何在 Microsoft 365 中設定資訊障礙。
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
- m365solution-scenario
ms.openlocfilehash: a4c7b711c0a977e0980cd0c72f9369833e9e5c65
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423594"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="52c64-104">Microsoft 365 中的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="52c64-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="52c64-105">Microsoft 365 可跨群組和組織進行通訊及共同作業，並支援在必要時限制特定使用者群組間通訊和共同作業的方式。</span><span class="sxs-lookup"><span data-stu-id="52c64-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="52c64-106">這可能包括您想要限制兩個群組之間的通訊和共同作業，以避免組織中發生利益衝突的情況或案例。</span><span class="sxs-lookup"><span data-stu-id="52c64-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="52c64-107">如果您需要限制組織內部的某些人員之間的通訊和共同作業，也可能會發生這種情況，以確保內部資訊的安全。</span><span class="sxs-lookup"><span data-stu-id="52c64-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="52c64-108">資訊障礙在 Microsoft 小組中支援，SharePoint 線上和商務 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="52c64-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="52c64-109">合規性管理員或資訊屏障管理員可以定義原則，以允許或防止 Microsoft 小組中的使用者群組之間進行通訊。</span><span class="sxs-lookup"><span data-stu-id="52c64-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="52c64-110">資訊屏障原則可以用於下列情況：</span><span class="sxs-lookup"><span data-stu-id="52c64-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="52c64-111">Day trader 群組中的使用者應該不會與行銷小組進行通訊或共用檔案</span><span class="sxs-lookup"><span data-stu-id="52c64-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="52c64-112">從事機密公司資訊的融資人員不應該與組織內的某些群組進行通訊或共用檔案</span><span class="sxs-lookup"><span data-stu-id="52c64-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="52c64-113">內部團隊使用貿易秘訣材料時，不應與組織內特定群組的人員線上通話或聊天</span><span class="sxs-lookup"><span data-stu-id="52c64-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="52c64-114">調查小組應只通話或與產品開發小組線上交談</span><span class="sxs-lookup"><span data-stu-id="52c64-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="52c64-115">設定 Microsoft 365 的資訊障礙</span><span class="sxs-lookup"><span data-stu-id="52c64-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="52c64-116">使用下列步驟為您的組織設定資訊障礙：</span><span class="sxs-lookup"><span data-stu-id="52c64-116">Use the following steps to configure information barriers for your organization:</span></span>

![有問必答風險解決方案資訊壁壘步驟](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="52c64-118">深入瞭解 Microsoft 365 中的[資訊障礙](information-barriers.md)</span><span class="sxs-lookup"><span data-stu-id="52c64-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="52c64-119">設定 [必要條件和許可權](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="52c64-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="52c64-120">分割 [組織中的使用者](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="52c64-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="52c64-121">建立及設定 [資訊障礙原則](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="52c64-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="52c64-122">套用 [資訊屏障原則](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="52c64-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="52c64-123">資訊障礙的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="52c64-123">More information about information barriers</span></span>

- [<span data-ttu-id="52c64-124">資訊屏障原則的屬性</span><span class="sxs-lookup"><span data-stu-id="52c64-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="52c64-125">編輯或移除資訊障礙原則</span><span class="sxs-lookup"><span data-stu-id="52c64-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)