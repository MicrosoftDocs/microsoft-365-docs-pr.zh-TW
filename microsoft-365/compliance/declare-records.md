---
title: 使用 [保留標籤] 宣告記錄
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
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 使用 [保留標籤] 宣告記錄。
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695240"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="439c3-103">使用 [保留標籤] 宣告記錄</span><span class="sxs-lookup"><span data-stu-id="439c3-103">Declare records by using retention labels</span></span>

><span data-ttu-id="439c3-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="439c3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="439c3-105">使用[保留標籤](retention.md#retention-labels)將內容標記為記錄。</span><span class="sxs-lookup"><span data-stu-id="439c3-105">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="439c3-106">您可以發佈這些標籤，讓使用者和系統管理員手動將這些標籤套用至內容，或自動將這些標籤套用到您想要標記為記錄的內容。</span><span class="sxs-lookup"><span data-stu-id="439c3-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="439c3-107">設定 [保留標籤] 以宣告記錄</span><span class="sxs-lookup"><span data-stu-id="439c3-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="439c3-108">當您建立 [保留標籤](retention.md#retention-labels) 時，可以選取選項將內容標記為記錄。</span><span class="sxs-lookup"><span data-stu-id="439c3-108">When you create a [retention label](retention.md#retention-labels), select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="439c3-109">當您在 Microsoft 365 合規性中心中建立或設定 **資訊控管** 中的保留標籤時，無法使用將內容標記為記錄的選項。</span><span class="sxs-lookup"><span data-stu-id="439c3-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="439c3-110">而是必須使用 **記錄管理**。</span><span class="sxs-lookup"><span data-stu-id="439c3-110">Instead, you must use **Records Management**.</span></span>

1. <span data-ttu-id="439c3-111">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com) 中，移至 **[記錄管理]** \> **[檔案計畫]**。</span><span class="sxs-lookup"><span data-stu-id="439c3-111">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="439c3-112">選取在 **[檔案計畫]** 頁面上的 **[建立標籤]**。</span><span class="sxs-lookup"><span data-stu-id="439c3-112">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="439c3-113">在精靈的 [標籤設定]\*\*\*\* 頁面上，選擇將內容分類為記錄的選項。</span><span class="sxs-lookup"><span data-stu-id="439c3-113">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![按一下 [使用標籤以將內容分類為「記錄」] 核取方塊](../media/recordversioning6.png)

3. <span data-ttu-id="439c3-115">視需要將保留標籤套用至 SharePoint 或 OneDrive 文件和 Exchange 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="439c3-115">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="439c3-116">如需詳細指示：</span><span class="sxs-lookup"><span data-stu-id="439c3-116">For instructions:</span></span>
    
    - [<span data-ttu-id="439c3-117">建立保留標籤，並在應用程式中使用這些標籤</span><span class="sxs-lookup"><span data-stu-id="439c3-117">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="439c3-118">自動將保留標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="439c3-118">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="439c3-119">將已設定的保留標籤套用至內容</span><span class="sxs-lookup"><span data-stu-id="439c3-119">Applying the configured retention label to content</span></span>

<span data-ttu-id="439c3-120">將內容標示為記錄的保留標籤可供使用者在應用程式中套用：</span><span class="sxs-lookup"><span data-stu-id="439c3-120">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="439c3-121">針對 Exchange，任何信箱存取權的使用者都可以套用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="439c3-121">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="439c3-122">對於 SharePoint 和 OneDrive，預設 [成員] 群組 ([參與] 權限等級) 中的任何使用者都能套用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="439c3-122">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="439c3-123">使用保留標籤將文件標示為記錄的範例：</span><span class="sxs-lookup"><span data-stu-id="439c3-123">Example of a document marked as record by using a retention label:</span></span>

![標記為記錄之文件的詳細資料窗格](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="439c3-125">後續步驟</span><span class="sxs-lookup"><span data-stu-id="439c3-125">Next steps</span></span>

<span data-ttu-id="439c3-126">如果您需要更新記錄的文件，請參閱 [使用記錄版本設定，以更新儲存在 SharePoint 或 OneDrive 中的記錄](record-versioning.md)。</span><span class="sxs-lookup"><span data-stu-id="439c3-126">If you need to update documents that are records, see [Use record versioning to update records stored in SharePoint or OneDrive](record-versioning.md).</span></span>

<span data-ttu-id="439c3-127">若要了解記錄的處置，請參閱[內容處置](disposition.md)。</span><span class="sxs-lookup"><span data-stu-id="439c3-127">To learn about the disposition of records, see [Disposing of content](disposition.md).</span></span>
