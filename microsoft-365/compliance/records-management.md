---
title: 記錄管理
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 您可以利用 Microsoft 365 中的記錄管理，將組織的特定保留排程套用到檔案計畫，以便管理保留、記錄宣告和處置，以支援完整的內容生命週期。
ms.openlocfilehash: e4454ba5940d9a67d9f160d90d0a9db14563bcf7
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949246"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="de816-103">Microsoft 365 中的記錄管理</span><span class="sxs-lookup"><span data-stu-id="de816-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="de816-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="de816-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="de816-105">所有類型的組織都需要記錄管理解決方案，用來管理其公司資料間的法規、法務及業務關鍵記錄。</span><span class="sxs-lookup"><span data-stu-id="de816-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="de816-106">Microsoft 365 中的記錄管理可幫助組織管理其法律義務，提供展現法規遵循的能力，並提高不再需要保留、不再具有價值或商業用途不再需要的項目一般處置的效率。</span><span class="sxs-lookup"><span data-stu-id="de816-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="de816-107">記錄管理解決方案支援下列元素：</span><span class="sxs-lookup"><span data-stu-id="de816-107">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="de816-108">**標籤內容做為記錄**。</span><span class="sxs-lookup"><span data-stu-id="de816-108">**Label content as a record**.</span></span> <span data-ttu-id="de816-109">建立並發佈將內容宣告為[記錄](records.md)的保留標籤，使用者可識別敏感性資訊、關鍵字或內容類型而套用或 [自動套用](labels.md#applying-a-retention-label-automatically-based-on-conditions)標籤。</span><span class="sxs-lookup"><span data-stu-id="de816-109">Create and publish retention labels that declare content as a [record](records.md) that can then be applied by end users or [auto-applied](labels.md#applying-a-retention-label-automatically-based-on-conditions) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="de816-110">**使用檔案計畫移轉和管理您的保留計畫**，並使用[檔案計畫管理員](file-plan-manager.md)來帶出您的現有保留計畫，或使用檔案描述項建立新檔案並擴充階層。</span><span class="sxs-lookup"><span data-stu-id="de816-110">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="de816-111">**建立保留和刪除原則**。</span><span class="sxs-lookup"><span data-stu-id="de816-111">**Establish retention and deletion policies**.</span></span> <span data-ttu-id="de816-112">根據包括上次修改或建立日期的各種因素，來定義[保留](retention-policies.md#retaining-content-for-a-specific-period-of-time)與[處置](retention-policies.md#deleting-content-thats-older-than-a-specific-age)期間。</span><span class="sxs-lookup"><span data-stu-id="de816-112">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="de816-113">使用[以事件為基礎的保留](event-driven-retention.md)來**觸發以事件為基礎的保留**。</span><span class="sxs-lookup"><span data-stu-id="de816-113">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="de816-114">使用[處置檢閱](disposition.md#disposition-reviews)和[記錄刪除](disposition.md#disposition-of-records)證明來**檢閱並驗證處置**。</span><span class="sxs-lookup"><span data-stu-id="de816-114">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="de816-115">使用[匯出選項](disposition.md#filter-and-export-the-views)來**匯出所有已處置項目的相關資訊**。</span><span class="sxs-lookup"><span data-stu-id="de816-115">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="de816-116">為組織中的記錄管理員功能**設定特定權限**，以讓其[具有適當權限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="de816-116">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="de816-117">您可以使用 Microsoft 365 中的記錄管理解決方案，將組織的保留排程套納入檔案計畫，以便管理保留、記錄宣告和處置，以支援完整的內容生命週期。</span><span class="sxs-lookup"><span data-stu-id="de816-117">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>
