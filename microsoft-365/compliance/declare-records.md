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
ms.openlocfilehash: fed988d2f880e4c0af1321cfb6ef4a873bd4e7ab
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730543"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="76bf8-103">使用 [保留標籤] 宣告記錄</span><span class="sxs-lookup"><span data-stu-id="76bf8-103">Declare records by using retention labels</span></span>

><span data-ttu-id="76bf8-104">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="76bf8-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="76bf8-105">若要將文件和電子郵件宣告為 [[紀錄]](records-management.md#records)，您可使用 [[保留標籤]](retention.md#retention-labels) 將内容標記為 **[紀錄]** 或 **[監管記錄]**。</span><span class="sxs-lookup"><span data-stu-id="76bf8-105">To declare documents and emails as [records](records-management.md#records), you use [retention labels](retention.md#retention-labels) that mark the content as a **record** or a **regulatory record**.</span></span>

<span data-ttu-id="76bf8-106">如果您不確定要使用記錄還是監管記錄，請參閱 [比較允許或封鎖哪些動作的限制](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。</span><span class="sxs-lookup"><span data-stu-id="76bf8-106">If you're not sure whether to use a record or a regulatory record, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span> <span data-ttu-id="76bf8-107">如果您需要使用監管記錄，您必須先執行 PowerShell 命令（如下個章節所述）。</span><span class="sxs-lookup"><span data-stu-id="76bf8-107">If you need to use regulatory records, you must first run a PowerShell command, as described in the next section.</span></span>

<span data-ttu-id="76bf8-108">您可以在保留標籤原則中發佈這些標籤，讓使用者和系統管理員將這些標籤套用至內容，或針對可將項目標示為記錄 (而非監管記錄) 的標籤，您還可以自動將這些標籤套用到您想要宣告為記錄的內容。</span><span class="sxs-lookup"><span data-stu-id="76bf8-108">You can then either publish those labels in a retention label policy so that users and administrators can apply them to content, or for labels that mark items as records (but not regulatory records), auto-apply those labels to content that you want to declare a record.</span></span>

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a><span data-ttu-id="76bf8-109">如何顯示將內容標示為監管記錄的選項</span><span class="sxs-lookup"><span data-stu-id="76bf8-109">How to display the option to mark content as a regulatory record</span></span>

>[!NOTE] 
> <span data-ttu-id="76bf8-110">下列程序是可審核的動作，在審核記錄的 [[保留原則和保留標籤活動]](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) 章節中記錄 **[為保留標籤啟動的監管記錄選項]**。</span><span class="sxs-lookup"><span data-stu-id="76bf8-110">The following procedure is an auditable action, logging **Enabled regulatory record option for retention labels** in the [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) section of the audit log.</span></span>

<span data-ttu-id="76bf8-111">根據預設，用以將內容標示為監管記錄的保留標籤選項，不會在保留標籤精靈中顯示。</span><span class="sxs-lookup"><span data-stu-id="76bf8-111">By default, the retention label option to mark content as a regulatory record isn't displayed in the retention label wizard.</span></span> <span data-ttu-id="76bf8-112">若要顯示此選項，您必須先執行 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="76bf8-112">To display this option, you must first run a PowerShell command:</span></span>

1. <span data-ttu-id="76bf8-113">[連接到 Office 365 安全性與合規性中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="76bf8-113">[Connect to the Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="76bf8-114">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="76bf8-114">Run the following cmdlet:</span></span>
    
    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````
    <span data-ttu-id="76bf8-115">系統不會提示您確認，且設定會立即生效。</span><span class="sxs-lookup"><span data-stu-id="76bf8-115">There is no prompt to confirm and the setting takes effect immediately.</span></span>

<span data-ttu-id="76bf8-116">如果您改變主意，想在保留標籤精靈中變更這個選項，要將它再次隱藏您可以執行相同的 Cmdlet 並使用 **[false]** 值：`Set-RegulatoryComplianceUI -Enabled $false`</span><span class="sxs-lookup"><span data-stu-id="76bf8-116">If you change your mind about seeing this option in the retention label wizard, you can hide it again by running the same cmdlet with the **false** value: `Set-RegulatoryComplianceUI -Enabled $false`</span></span> 

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="76bf8-117">設定 [保留標籤] 以宣告記錄</span><span class="sxs-lookup"><span data-stu-id="76bf8-117">Configuring retention labels to declare records</span></span>

<span data-ttu-id="76bf8-118">當您在 Microsoft 365 合規性中心的 **[記錄管理]** 解決方案中建立保留標籤時，您可以選擇將項目標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="76bf8-118">When you create a retention label from the **Records Management** solution in the Microsoft 365 compliance center, you have the option to mark items as a record.</span></span> <span data-ttu-id="76bf8-119">如果您執行上一章節的 PowerShell 命令，則可將項目標示為監管記錄。</span><span class="sxs-lookup"><span data-stu-id="76bf8-119">If you ran the PowerShell command from the previous section, you can alternatively mark items as a regulatory record.</span></span>

<span data-ttu-id="76bf8-120">例如：</span><span class="sxs-lookup"><span data-stu-id="76bf8-120">For example:</span></span>

![設定保留標籤，將內容標示為記錄或監管](../media/recordversioning6.png)

<span data-ttu-id="76bf8-122">您可視需要將保留標籤套用至 SharePoint 或 OneDrive 文件和 Exchange 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="76bf8-122">Using this retention label, you can now apply it to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> 

<span data-ttu-id="76bf8-123">如需完整指示：</span><span class="sxs-lookup"><span data-stu-id="76bf8-123">For full instructions:</span></span>

- [<span data-ttu-id="76bf8-124">建立保留標籤，並在應用程式中套用這些標籤</span><span class="sxs-lookup"><span data-stu-id="76bf8-124">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)

- <span data-ttu-id="76bf8-125">[自動將保留標籤套用至內容](apply-retention-labels-automatically.md) (不支援監管記錄)</span><span class="sxs-lookup"><span data-stu-id="76bf8-125">[Apply a retention label to content automatically](apply-retention-labels-automatically.md) (not supported for regulatory records)</span></span>


## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="76bf8-126">將已設定的保留標籤套用至內容</span><span class="sxs-lookup"><span data-stu-id="76bf8-126">Applying the configured retention label to content</span></span>

<span data-ttu-id="76bf8-127">將內容標示為記錄或監管記錄的保留標籤，可供使用者在應用程式中套用：</span><span class="sxs-lookup"><span data-stu-id="76bf8-127">When retention labels that mark items as a record or regulatory record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="76bf8-128">針對 Exchange，任何信箱存取權的使用者都可以套用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="76bf8-128">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="76bf8-129">對於 SharePoint 和 OneDrive，預設 [成員] 群組 ([參與] 權限等級) 中的任何使用者都能套用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="76bf8-129">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="76bf8-130">使用保留標籤將文件標示為記錄的範例：</span><span class="sxs-lookup"><span data-stu-id="76bf8-130">Example of a document marked as record by using a retention label:</span></span>

![標記為記錄之文件的詳細資料窗格](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="76bf8-132">後續步驟</span><span class="sxs-lookup"><span data-stu-id="76bf8-132">Next steps</span></span>

<span data-ttu-id="76bf8-133">若需記錄管理支援的案例清單，請參閱 [[記錄管理的常見案例]](get-started-with-records-management.md#common-scenarios-for-records-management)。</span><span class="sxs-lookup"><span data-stu-id="76bf8-133">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
