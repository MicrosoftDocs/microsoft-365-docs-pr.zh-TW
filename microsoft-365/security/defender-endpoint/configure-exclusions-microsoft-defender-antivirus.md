---
title: 設定 Microsoft Defender 防病毒掃描的排除專案
description: 您可以排除檔案 (包含由 Microsoft Defender 防毒程式掃描的指定程式所修改的檔案) 和資料夾。 使用 PowerShell 驗證您的排除專案。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275117"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="db613-104">設定及驗證 Microsoft Defender 防病毒掃描的排除專案</span><span class="sxs-lookup"><span data-stu-id="db613-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="db613-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="db613-105">**Applies to:**</span></span>

- [<span data-ttu-id="db613-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="db613-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="db613-107">您可以從 Microsoft Defender 防病毒掃描中排除某些檔案、資料夾、處理常式及處理常式開啟的檔案。</span><span class="sxs-lookup"><span data-stu-id="db613-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="db613-108">這類排除專案適用于 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、 [隨選掃描](run-scan-microsoft-defender-antivirus.md)，以及 [永遠開啟即時保護和監控](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="db613-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="db613-109">處理常式開啟的檔案排除只適用于即時保護。</span><span class="sxs-lookup"><span data-stu-id="db613-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="db613-110">設定及驗證排除範圍</span><span class="sxs-lookup"><span data-stu-id="db613-110">Configure and validate exclusions</span></span>

<span data-ttu-id="db613-111">若要設定及驗證排除，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="db613-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="db613-112">根據檔案名[、副檔名和資料夾位置，設定及驗證排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="db613-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="db613-113">您可以根據檔案副檔名、檔案名或位置，將檔案從 Microsoft Defender 防病毒掃描中排除。</span><span class="sxs-lookup"><span data-stu-id="db613-113">You can exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="db613-114">[針對由進程開啟的檔案，設定及驗證排除](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)專案。</span><span class="sxs-lookup"><span data-stu-id="db613-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="db613-115">您可以從特定進程所開啟的掃描中排除檔案。</span><span class="sxs-lookup"><span data-stu-id="db613-115">You can exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="db613-116">定義排除的建議</span><span class="sxs-lookup"><span data-stu-id="db613-116">Recommendations for defining exclusions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db613-117">Microsoft Defender 防毒軟體會根據已知的作業系統行為和一般管理檔案（例如企業管理、資料庫管理及其他企業案例及案例中所使用的管理檔案），包含許多自動排除。</span><span class="sxs-lookup"><span data-stu-id="db613-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
> 
> <span data-ttu-id="db613-118">定義排除項會降低 Microsoft Defender 防毒軟體所提供的保護。</span><span class="sxs-lookup"><span data-stu-id="db613-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="db613-119">您應時刻評估與執行排除相關的風險，您應該只排除您確信不會惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="db613-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="db613-120">當您定義排除專案時，請牢記下列幾點：</span><span class="sxs-lookup"><span data-stu-id="db613-120">Keep the following points in mind when you are defining exclusions:</span></span>  

- <span data-ttu-id="db613-121">排除在技術上是保護缺口。</span><span class="sxs-lookup"><span data-stu-id="db613-121">Exclusions are technically a protection gap.</span></span> <span data-ttu-id="db613-122">在定義排除時，一定要考慮緩解。</span><span class="sxs-lookup"><span data-stu-id="db613-122">Always consider mitigations when defining exclusions.</span></span> <span data-ttu-id="db613-123">其他的緩解動作可能非常簡單，只要確定排除的位置具有適當的存取控制清單 (ACLs) 、審核原則，都是由最新的軟體來處理，等等。</span><span class="sxs-lookup"><span data-stu-id="db613-123">Other mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="db613-124">定期複查排除專案。</span><span class="sxs-lookup"><span data-stu-id="db613-124">Review the exclusions periodically.</span></span> <span data-ttu-id="db613-125">請重新檢查並重新執行作為審查程式一部分的緩解。</span><span class="sxs-lookup"><span data-stu-id="db613-125">Recheck and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="db613-126">理想狀況下，避免將排除定義為主動。</span><span class="sxs-lookup"><span data-stu-id="db613-126">Ideally, avoid defining exclusions intending to be proactive.</span></span> <span data-ttu-id="db613-127">例如，請不要排除某些專案，因為您認為它可能是未來的問題。</span><span class="sxs-lookup"><span data-stu-id="db613-127">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="db613-128">只針對特定問題（如與符合性或應用程式相容性相關的問題）使用排除專案，以降低其效能。</span><span class="sxs-lookup"><span data-stu-id="db613-128">Use exclusions only for specific issues, such as those pertaining to performance or application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="db613-129">審核排除清單變更。</span><span class="sxs-lookup"><span data-stu-id="db613-129">Audit the exclusion list changes.</span></span> <span data-ttu-id="db613-130">安全性管理員應該保留足夠的內容，以避免為何新增特定排除。</span><span class="sxs-lookup"><span data-stu-id="db613-130">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="db613-131">您應該能夠提供特定原因的答案，以瞭解排除特定路徑的原因。</span><span class="sxs-lookup"><span data-stu-id="db613-131">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="db613-132">相關文章</span><span class="sxs-lookup"><span data-stu-id="db613-132">Related articles</span></span>

- [<span data-ttu-id="db613-133">Windows Server 2016 上的 Microsoft Defender 防病毒排除</span><span class="sxs-lookup"><span data-stu-id="db613-133">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="db613-134">定義排除時應避免的常見錯誤</span><span class="sxs-lookup"><span data-stu-id="db613-134">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
