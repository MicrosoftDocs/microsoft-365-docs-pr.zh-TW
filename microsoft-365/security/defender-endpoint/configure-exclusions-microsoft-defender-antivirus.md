---
title: 設定 Microsoft Defender 防病毒掃描的排除專案
description: 您可以排除檔案 (包含由 Microsoft Defender AV 掃描的指定程式所修改的檔案) 和資料夾。 使用 PowerShell 驗證您的排除專案。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 08f7f9d4a6e9e70d3ef071f30712b2ae53f4ea52
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764660"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="38c33-104">設定及驗證 Microsoft Defender 防病毒掃描的排除專案</span><span class="sxs-lookup"><span data-stu-id="38c33-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="38c33-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="38c33-105">**Applies to:**</span></span>

- [<span data-ttu-id="38c33-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="38c33-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="38c33-107">您可以從 Microsoft Defender 防病毒掃描中排除某些檔案、資料夾、處理常式及處理常式開啟的檔案。</span><span class="sxs-lookup"><span data-stu-id="38c33-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="38c33-108">這類排除專案適用于 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、 [隨選掃描](run-scan-microsoft-defender-antivirus.md)，以及 [永遠開啟即時保護和監控](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="38c33-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="38c33-109">處理常式開啟的檔案排除只適用于即時保護。</span><span class="sxs-lookup"><span data-stu-id="38c33-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="38c33-110">設定及驗證排除範圍</span><span class="sxs-lookup"><span data-stu-id="38c33-110">Configure and validate exclusions</span></span>

<span data-ttu-id="38c33-111">若要設定及驗證排除，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="38c33-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="38c33-112">根據檔案名[、副檔名和資料夾位置，設定及驗證排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="38c33-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="38c33-113">這可讓您根據檔副檔名、檔案名或位置，將檔案從 Microsoft Defender 防病毒掃描中排除。</span><span class="sxs-lookup"><span data-stu-id="38c33-113">This enables you to exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="38c33-114">[針對由進程開啟的檔案，設定及驗證排除](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)專案。</span><span class="sxs-lookup"><span data-stu-id="38c33-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="38c33-115">這可讓您從特定進程所開啟的掃描中排除檔案。</span><span class="sxs-lookup"><span data-stu-id="38c33-115">This enables you to exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="38c33-116">定義排除的建議</span><span class="sxs-lookup"><span data-stu-id="38c33-116">Recommendations for defining exclusions</span></span>
[!IMPORTANT]
<span data-ttu-id="38c33-117">Microsoft Defender 防毒軟體會根據已知的作業系統行為和一般管理檔案（例如企業管理、資料庫管理及其他企業案例及案例中所使用的管理檔案），包含許多自動排除。</span><span class="sxs-lookup"><span data-stu-id="38c33-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
<span data-ttu-id="38c33-118">定義排除項會降低 Microsoft Defender 防毒軟體所提供的保護。</span><span class="sxs-lookup"><span data-stu-id="38c33-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="38c33-119">您應時刻評估與執行排除相關的風險，您應該只排除您確信不會惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="38c33-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="38c33-120">以下是定義排除時，應謹記的建議清單：</span><span class="sxs-lookup"><span data-stu-id="38c33-120">The following is a list of recommendations that you should keep in mind when defining exclusions:</span></span>  

- <span data-ttu-id="38c33-121">排除在技術上是保護缺口，在定義排除時一定要考慮額外的緩解。</span><span class="sxs-lookup"><span data-stu-id="38c33-121">Exclusions are technically a protection gap—always consider additional mitigations when defining exclusions.</span></span> <span data-ttu-id="38c33-122">其他的緩解可能非常簡單，只要確定排除的位置具有適當的存取控制清單 (ACLs) 、審核原則，都是由最新的軟體來處理，等等。</span><span class="sxs-lookup"><span data-stu-id="38c33-122">Additional mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="38c33-123">定期複查排除專案。</span><span class="sxs-lookup"><span data-stu-id="38c33-123">Review the exclusions periodically.</span></span> <span data-ttu-id="38c33-124">請重新檢查並重新執行緩解程式做為審查程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="38c33-124">Re-check and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="38c33-125">理想狀況下，避免定義主動排除。</span><span class="sxs-lookup"><span data-stu-id="38c33-125">Ideally, avoid defining proactive exclusions.</span></span> <span data-ttu-id="38c33-126">例如，請不要排除某些專案，因為您認為它可能是未來的問題。</span><span class="sxs-lookup"><span data-stu-id="38c33-126">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="38c33-127">僅針對特定問題（主要是在效能上）使用排除，也可以在排除排除問題的應用程式相容性方面使用排除。</span><span class="sxs-lookup"><span data-stu-id="38c33-127">Use exclusions only for specific issues—mostly around performance, or sometimes around application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="38c33-128">審核排除清單變更。</span><span class="sxs-lookup"><span data-stu-id="38c33-128">Audit the exclusion list changes.</span></span> <span data-ttu-id="38c33-129">安全性管理員應該保留足夠的內容，以避免為何新增特定排除。</span><span class="sxs-lookup"><span data-stu-id="38c33-129">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="38c33-130">您應該能夠提供特定原因的答案，以瞭解排除特定路徑的原因。</span><span class="sxs-lookup"><span data-stu-id="38c33-130">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="38c33-131">相關文章</span><span class="sxs-lookup"><span data-stu-id="38c33-131">Related articles</span></span>

- [<span data-ttu-id="38c33-132">Windows Server 2016 上的 Microsoft Defender 防病毒排除</span><span class="sxs-lookup"><span data-stu-id="38c33-132">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="38c33-133">定義排除時所避免的常見錯誤</span><span class="sxs-lookup"><span data-stu-id="38c33-133">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
