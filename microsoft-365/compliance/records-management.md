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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 使用 Microsoft 365 中的記錄管理，您可以將保留時間表套用到管理保留、記錄聲明和處置的檔案計畫中。
ms.openlocfilehash: 0179f208f10921293c164516b26440f5bd043517
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127480"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="1b973-103">Microsoft 365 中的記錄管理</span><span class="sxs-lookup"><span data-stu-id="1b973-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="1b973-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="1b973-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="1b973-105">所有類型的組織都需要記錄管理解決方案，用來管理其公司資料間的法規、法務及業務關鍵記錄。</span><span class="sxs-lookup"><span data-stu-id="1b973-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="1b973-106">Microsoft 365 中的記錄管理可幫助組織管理其法律義務，提供展現法規遵循的能力，並提高不再需要保留、不再具有價值或商業用途不再需要的項目一般處置的效率。</span><span class="sxs-lookup"><span data-stu-id="1b973-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="1b973-107">Microsoft 365 中的記錄管理提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="1b973-107">Records management in Microsoft 365 provides the following capabilities:</span></span>

- <span data-ttu-id="1b973-108">**標籤內容做為記錄**。</span><span class="sxs-lookup"><span data-stu-id="1b973-108">**Label content as a record**.</span></span> <span data-ttu-id="1b973-109">建立並發佈將內容標記為[記錄](records.md)的保留標籤，使用者可識別敏感性資訊、關鍵字或內容類型而套用或[自動套用](apply-retention-labels-automatically.md)標籤。</span><span class="sxs-lookup"><span data-stu-id="1b973-109">Create and publish retention labels that mark content as a [record](records.md) that can then be applied by end users or [auto-applied](apply-retention-labels-automatically.md) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="1b973-110">**使用檔案計劃來移轉和管理您的保留需求**。</span><span class="sxs-lookup"><span data-stu-id="1b973-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="1b973-111">透過使用[檔案計劃](file-plan-manager.md)，您可以將現有的保留計劃帶入 Microsoft 365，或是建立新的保留方案以增強管理功能。</span><span class="sxs-lookup"><span data-stu-id="1b973-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="1b973-112">**使用保留標籤以設定保留和刪除設定**。</span><span class="sxs-lookup"><span data-stu-id="1b973-112">**Configure retention and deletion settings with the retention label**.</span></span> <span data-ttu-id="1b973-113">根據各種因素，包括最後一次修改或建立日期，定義保留與處置期間。</span><span class="sxs-lookup"><span data-stu-id="1b973-113">Define retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="1b973-114">使用[以事件為基礎的保留](event-driven-retention.md)來**觸發以事件為基礎的保留**。</span><span class="sxs-lookup"><span data-stu-id="1b973-114">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="1b973-115">使用[處置檢閱](disposition.md#disposition-reviews)和[記錄刪除](disposition.md#disposition-of-records)證明來**檢閱並驗證處置**。</span><span class="sxs-lookup"><span data-stu-id="1b973-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="1b973-116">使用[匯出選項](disposition.md#filter-and-export-the-views)來**匯出所有已處置項目的相關資訊**。</span><span class="sxs-lookup"><span data-stu-id="1b973-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="1b973-117">為組織中的記錄管理員功能**設定特定權限**，以讓其[具有適當權限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1b973-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="1b973-118">您可以使用 Microsoft 365 中的記錄管理解決方案，將組織的保留排程套納入檔案計畫，以便管理保留、記錄宣告和處置，以支援完整的內容生命週期。</span><span class="sxs-lookup"><span data-stu-id="1b973-118">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1b973-119">其他資源</span><span class="sxs-lookup"><span data-stu-id="1b973-119">Additional resources</span></span>

<span data-ttu-id="1b973-120">請參閱 [網路研討會記錄](https://aka.ms/MIPC/Video-RecordsManagementWebinar)和記錄管理的[常見問題集](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)。</span><span class="sxs-lookup"><span data-stu-id="1b973-120">See the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) and [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar) for records management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1b973-121">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1b973-121">Next steps</span></span>

<span data-ttu-id="1b973-122">如果您準備好要開始使用 Microsoft 365 中的記錄管理，請參閱[了解記錄](records.md)。</span><span class="sxs-lookup"><span data-stu-id="1b973-122">If you are ready to get started with records management in Microsoft 365, see [Learn about records](records.md).</span></span>
