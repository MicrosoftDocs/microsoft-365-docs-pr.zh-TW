---
title: 在 Microsoft Defender AV 中還原隔離的檔案
description: 您可以還原由 Microsoft Defender AV 隔離的檔案和資料夾。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: e0253c4ac7d92c91e3fda45681568d721645f2b0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275381"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a><span data-ttu-id="99db8-103">在 Microsoft Defender AV 中還原隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="99db8-103">Restore quarantined files in Microsoft Defender AV</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="99db8-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="99db8-104">**Applies to:**</span></span>

- [<span data-ttu-id="99db8-105">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="99db8-105">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="99db8-106">如果 Microsoft Defender 防毒軟體設定為偵測和修正裝置上的威脅，Microsoft Defender 防毒軟體會隔離可疑的檔案。</span><span class="sxs-lookup"><span data-stu-id="99db8-106">If Microsoft Defender Antivirus is configured to detect and remediate threats on your device, Microsoft Defender Antivirus quarantines suspicious files.</span></span> <span data-ttu-id="99db8-107">如果您確定隔離的檔案不是威脅，您可以將它還原。</span><span class="sxs-lookup"><span data-stu-id="99db8-107">If you are certain a quarantined file is not a threat, you can restore it.</span></span>

1. <span data-ttu-id="99db8-108">開啟 **Windows 安全性**。</span><span class="sxs-lookup"><span data-stu-id="99db8-108">Open **Windows Security**.</span></span>
2. <span data-ttu-id="99db8-109">選取 [ **病毒 & 威脅防護** ]，然後按一下 [ **保護歷程記錄**]。</span><span class="sxs-lookup"><span data-stu-id="99db8-109">Select **Virus & threat protection** and then click **Protection history**.</span></span>
3. <span data-ttu-id="99db8-110">在所有近期專案的清單中，篩選 **隔離的專案**。</span><span class="sxs-lookup"><span data-stu-id="99db8-110">In the list of all recent items, filter on **Quarantined Items**.</span></span>
4. <span data-ttu-id="99db8-111">選取您要保留的專案，並採取動作，例如 [還原]。</span><span class="sxs-lookup"><span data-stu-id="99db8-111">Select an item you want to keep, and take an action, such as restore.</span></span>

> [!TIP]
> <span data-ttu-id="99db8-112">使用命令提示字元，也可以從隔離區還原檔案。</span><span class="sxs-lookup"><span data-stu-id="99db8-112">Restoring a file from quarantine can also be done using Command Prompt.</span></span> <span data-ttu-id="99db8-113">請參閱 [從隔離區還原](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine)檔案。</span><span class="sxs-lookup"><span data-stu-id="99db8-113">See [Restore a file from quarantine](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine).</span></span> 

## <a name="related-articles"></a><span data-ttu-id="99db8-114">相關文章</span><span class="sxs-lookup"><span data-stu-id="99db8-114">Related articles</span></span>

- [<span data-ttu-id="99db8-115">設定掃描的修正</span><span class="sxs-lookup"><span data-stu-id="99db8-115">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
- [<span data-ttu-id="99db8-116">查看掃描結果</span><span class="sxs-lookup"><span data-stu-id="99db8-116">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md)
- [<span data-ttu-id="99db8-117">根據檔案名、副檔名和資料夾位置，設定及驗證排除</span><span class="sxs-lookup"><span data-stu-id="99db8-117">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="99db8-118">設定及驗證由進程開啟之檔案的排除專案</span><span class="sxs-lookup"><span data-stu-id="99db8-118">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="99db8-119">設定 Windows 伺服器上的 Microsoft Defender 防毒軟體排除</span><span class="sxs-lookup"><span data-stu-id="99db8-119">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)