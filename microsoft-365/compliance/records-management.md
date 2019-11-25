---
title: Microsoft 365 中的記錄管理
ms.author: laurawi
author: laurawi
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
ms.openlocfilehash: 3057b5ab061bc5107acbde3c67ecde8a9edaffd7
ms.sourcegitcommit: 0d423b50d2f1f4eccd64e35e00f67313244efba9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "39233209"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="e97a8-103">Microsoft 365 中的記錄管理</span><span class="sxs-lookup"><span data-stu-id="e97a8-103">Records management in Microsoft 365</span></span>

<span data-ttu-id="e97a8-104">所有類型的組織都需要記錄管理解決方案，用來管理其公司資料間的法規、法務及業務關鍵記錄。</span><span class="sxs-lookup"><span data-stu-id="e97a8-104">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="e97a8-105">Microsoft 365 中的記錄管理可幫助組織管理其法律義務，提供展現法規遵循的能力，並提高不再需要保留、不再具有價值或商業用途不再需要的項目一般處置的效率。</span><span class="sxs-lookup"><span data-stu-id="e97a8-105">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="e97a8-106">記錄管理解決方案支援下列元素：</span><span class="sxs-lookup"><span data-stu-id="e97a8-106">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="e97a8-107">**標籤內容做為記錄**。</span><span class="sxs-lookup"><span data-stu-id="e97a8-107">**Label as a record**.</span></span> <span data-ttu-id="e97a8-108">發佈供使用者套用的[記錄標籤](records.md)，或[自動套用](labels.md#applying-a-retention-label-automatically-based-on-conditions)記錄標籤至包含特定敏感性資訊、關鍵字或內容類型的項目。</span><span class="sxs-lookup"><span data-stu-id="e97a8-108">Publish [record labels](records.md) to be applied by end users, or [auto-apply record labels](labels.md#applying-a-retention-label-automatically-based-on-conditions) to items containing specific sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="e97a8-109">**使用檔案計畫移轉和管理您的保留計畫**，並使用[檔案計畫管理員](file-plan-manager.md)來帶出您的現有保留計畫，或使用檔案描述項建立新檔案並擴充階層。</span><span class="sxs-lookup"><span data-stu-id="e97a8-109">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="e97a8-110">**在記錄標籤中建立保留和刪除原則**。</span><span class="sxs-lookup"><span data-stu-id="e97a8-110">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="e97a8-111">根據各種因素，包括上次修改或建立日期，來定義[保留](retention-policies.md#retaining-content-for-a-specific-period-of-time)與[處置](retention-policies.md#deleting-content-thats-older-than-a-specific-age)期間。</span><span class="sxs-lookup"><span data-stu-id="e97a8-111">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors including the date last modified or created.</span></span>

- <span data-ttu-id="e97a8-112">使用[以事件為基礎的保留](event-driven-retention.md)來**觸發以事件為基礎的保留**。</span><span class="sxs-lookup"><span data-stu-id="e97a8-112">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="e97a8-113">利用[處置檢閱](disposition-reviews.md)**檢閱並驗證處置**。</span><span class="sxs-lookup"><span data-stu-id="e97a8-113">**Review and validate disposition** with [disposition review](disposition-reviews.md).</span></span>

- <span data-ttu-id="e97a8-114">**利用檢閱處置來檢閱處置的項目**，並[匯出處置報告](disposition-reviews.md#export-the-disposition-items)來進一步驗證及報告。</span><span class="sxs-lookup"><span data-stu-id="e97a8-114">**Review disposed items with disposition review** and [export a disposition report](disposition-reviews.md#export-the-disposition-items) for further validation and reporting.</span></span>

- <span data-ttu-id="e97a8-115">為組織中的記錄管理員功能**設定特定權限**，以讓其[具有適當權限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e97a8-115">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="e97a8-116">您可以利用 Microsoft 365 中的記錄管理解決方案，將組織的保留排程套納入檔案計畫，以便管理保留、記錄宣告和處置，以支援完整的內容生命週期。</span><span class="sxs-lookup"><span data-stu-id="e97a8-116">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition in support of the full content lifecycle.</span></span>
