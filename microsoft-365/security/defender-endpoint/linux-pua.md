---
title: 在 Linux 上使用 Microsoft Defender for Endpoint 偵測並封鎖可能有害的應用程式
description: 在 Linux 上使用 Microsoft Defender for Endpoint (PUA) 偵測並封鎖可能有害的應用程式。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，pua，pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7ec3399129cc65d75b464f5d5f56bb11250ccaf2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933154"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="940f3-104">在 Linux 上使用 Microsoft Defender for Endpoint 偵測並封鎖可能有害的應用程式</span><span class="sxs-lookup"><span data-stu-id="940f3-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="940f3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="940f3-105">**Applies to:**</span></span>
- [<span data-ttu-id="940f3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="940f3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="940f3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="940f3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="940f3-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="940f3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="940f3-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="940f3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="940f3-110">在 Linux 上的 Defender for PUA 中，可能有害的應用程式 () 保護功能可偵測並封鎖您網路中端點上的 PUA 檔案。</span><span class="sxs-lookup"><span data-stu-id="940f3-110">The potentially unwanted application (PUA) protection feature in Defender for Endpoint on Linux can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="940f3-111">這些應用程式不會被視為病毒、惡意程式碼或其他類型的威脅，但是可能會對對其效能或使用不良影響的端點執行動作。</span><span class="sxs-lookup"><span data-stu-id="940f3-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="940f3-112">PUA 也可以參考被視為具有不良信譽的應用程式。</span><span class="sxs-lookup"><span data-stu-id="940f3-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="940f3-113">這些應用程式可能會增加網路受到惡意程式碼感染的風險，使惡意程式碼感染難以識別，而且可以在清理應用程式時浪費 IT 資源。</span><span class="sxs-lookup"><span data-stu-id="940f3-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="940f3-114">運作方式</span><span class="sxs-lookup"><span data-stu-id="940f3-114">How it works</span></span>

<span data-ttu-id="940f3-115">在 Linux 上的 Defender for Endpoint 可以偵測並報告 PUA 檔案。</span><span class="sxs-lookup"><span data-stu-id="940f3-115">Defender for Endpoint on Linux can detect and report PUA files.</span></span> <span data-ttu-id="940f3-116">當以封鎖模式設定時，PUA 檔案會移至隔離區。</span><span class="sxs-lookup"><span data-stu-id="940f3-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="940f3-117">在端點上偵測到 PUA 時，Linux 上的 Defender Endpoint 會在威脅歷程記錄中保存感染記錄。</span><span class="sxs-lookup"><span data-stu-id="940f3-117">When a PUA is detected on an endpoint, Defender for Endpoint on Linux keeps a record of the infection in the threat history.</span></span> <span data-ttu-id="940f3-118">您可以從 Microsoft Defender 安全性中心入口網站或透過 `mdatp` 命令列工具來進行記錄。</span><span class="sxs-lookup"><span data-stu-id="940f3-118">The history can be visualized from the Microsoft Defender Security Center portal or through the `mdatp` command-line tool.</span></span> <span data-ttu-id="940f3-119">威脅名稱會包含 "Application" 一詞。</span><span class="sxs-lookup"><span data-stu-id="940f3-119">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="940f3-120">設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="940f3-120">Configure PUA protection</span></span>

<span data-ttu-id="940f3-121">您可以採用下列其中一種方式，設定在 Linux 上的 PUA 中的 Defender for Endpoint protection：</span><span class="sxs-lookup"><span data-stu-id="940f3-121">PUA protection in Defender for Endpoint on Linux can be configured in one of the following ways:</span></span>

- <span data-ttu-id="940f3-122">**Off**：已停用 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="940f3-122">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="940f3-123">**Audit**： PUA files 會在產品記錄中報告，但不會在 Microsoft Defender Security Center 中報告。</span><span class="sxs-lookup"><span data-stu-id="940f3-123">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="940f3-124">不會將感染記錄儲存在威脅史中，也不會對產品採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="940f3-124">No record of the infection is stored in the threat history and no action is taken by the product.</span></span>
- <span data-ttu-id="940f3-125">**封鎖**： PUA 檔案會在產品記錄和 Microsoft Defender Security Center 中報告。</span><span class="sxs-lookup"><span data-stu-id="940f3-125">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="940f3-126">感染的記錄會儲存在威脅史中，且會在產品採取動作。</span><span class="sxs-lookup"><span data-stu-id="940f3-126">A record of the infection is stored in the threat history and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="940f3-127">根據預設，會在 **審核** 模式中設定 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="940f3-127">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="940f3-128">您可以從命令列或從管理主控台，設定 PUA 檔案的處理方式。</span><span class="sxs-lookup"><span data-stu-id="940f3-128">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="940f3-129">使用命令列工具來設定 PUA 保護：</span><span class="sxs-lookup"><span data-stu-id="940f3-129">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="940f3-130">在終端中執行下列命令，以設定 PUA 保護：</span><span class="sxs-lookup"><span data-stu-id="940f3-130">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="940f3-131">使用管理主控台來設定 PUA 保護：</span><span class="sxs-lookup"><span data-stu-id="940f3-131">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="940f3-132">在您的企業中，您可以從管理主控台（如 Puppet 或 Ansible）設定 PUA 防護，類似于設定其他產品設定的方式。</span><span class="sxs-lookup"><span data-stu-id="940f3-132">In your enterprise, you can configure PUA protection from a management console, such as Puppet or Ansible, similarly to how other product settings are configured.</span></span> <span data-ttu-id="940f3-133">如需詳細資訊，請參閱在 Linux 文章中的「用於[Defender 的 Defender 設定偏好設定](linux-preferences.md)」的 [[威脅類型](linux-preferences.md#threat-type-settings)設定] 區段。</span><span class="sxs-lookup"><span data-stu-id="940f3-133">For more information, see the [Threat type settings](linux-preferences.md#threat-type-settings) section of the [Set preferences for Defender for Endpoint on Linux](linux-preferences.md) article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="940f3-134">相關文章</span><span class="sxs-lookup"><span data-stu-id="940f3-134">Related articles</span></span>

- [<span data-ttu-id="940f3-135">設定 Linux 上的 Defender for Endpoint 的喜好設定</span><span class="sxs-lookup"><span data-stu-id="940f3-135">Set preferences for Defender for Endpoint on Linux</span></span>](linux-preferences.md)
