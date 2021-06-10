---
title: 在 Mac 上使用 Microsoft Defender for Endpoint 偵測並封鎖可能有害的應用程式
description: 使用 Microsoft Defender for Mac (PUA) 偵測並封鎖可能有害的應用程式。
keywords: microsoft，defender，Microsoft Defender for Endpoint，mac，pua，pus
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2d32dd96cd506ebf1752e48d2b7c66208b1abc11
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934534"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="d814a-104">在 macOS 上使用 Microsoft Defender for Endpoint 偵測並封鎖可能有害的應用程式</span><span class="sxs-lookup"><span data-stu-id="d814a-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d814a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d814a-105">**Applies to:**</span></span>
- [<span data-ttu-id="d814a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d814a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d814a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d814a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d814a-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="d814a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d814a-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d814a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="d814a-110">MacOS 上的 Microsoft Defender for Endpoint (PUA) 保護功能可偵測並封鎖您網路中端點上的 PUA 檔案。</span><span class="sxs-lookup"><span data-stu-id="d814a-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint on macOS can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="d814a-111">這些應用程式不會被視為病毒、惡意程式碼或其他類型的威脅，但是可能會對對其效能或使用不良影響的端點執行動作。</span><span class="sxs-lookup"><span data-stu-id="d814a-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="d814a-112">PUA 也可以參考被視為具有不良信譽的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d814a-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="d814a-113">這些應用程式可能會增加網路受到惡意程式碼感染的風險，使惡意程式碼感染難以識別，而且可以在清理應用程式時浪費 IT 資源。</span><span class="sxs-lookup"><span data-stu-id="d814a-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="d814a-114">運作方式</span><span class="sxs-lookup"><span data-stu-id="d814a-114">How it works</span></span>

<span data-ttu-id="d814a-115">MacOS 上的 Microsoft Defender for Endpoint 可以偵測及報告 PUA 檔案。</span><span class="sxs-lookup"><span data-stu-id="d814a-115">Microsoft Defender for Endpoint on macOS can detect and report PUA files.</span></span> <span data-ttu-id="d814a-116">當以封鎖模式設定時，PUA 檔案會移至隔離區。</span><span class="sxs-lookup"><span data-stu-id="d814a-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="d814a-117">當在端點上偵測到 PUA 時，macOS 上的 Microsoft Defender for Endpoint 會向使用者呈現通知，除非已停用通知。</span><span class="sxs-lookup"><span data-stu-id="d814a-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint on macOS presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="d814a-118">威脅名稱會包含 "Application" 一詞。</span><span class="sxs-lookup"><span data-stu-id="d814a-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="d814a-119">設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="d814a-119">Configure PUA protection</span></span>

<span data-ttu-id="d814a-120">您可以透過下列其中一種方式，設定 macOS 的 Microsoft Defender for Endpoint 中的 PUA 保護：</span><span class="sxs-lookup"><span data-stu-id="d814a-120">PUA protection in Microsoft Defender for Endpoint on macOS can be configured in one of the following ways:</span></span>

- <span data-ttu-id="d814a-121">**Off**：已停用 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="d814a-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="d814a-122">**Audit**： PUA files 會在產品記錄中報告，但不會在 Microsoft Defender 資訊安全中心中報告。</span><span class="sxs-lookup"><span data-stu-id="d814a-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="d814a-123">使用者不會呈現任何通知，產品也不會採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="d814a-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="d814a-124">**封鎖**： PUA 檔案會在產品記錄和 Microsoft Defender 資訊安全中心中報告。</span><span class="sxs-lookup"><span data-stu-id="d814a-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="d814a-125">使用者會看到一則通知，並由產品採取動作。</span><span class="sxs-lookup"><span data-stu-id="d814a-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="d814a-126">根據預設，會在 **審核** 模式中設定 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="d814a-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="d814a-127">您可以從命令列或從管理主控台，設定 PUA 檔案的處理方式。</span><span class="sxs-lookup"><span data-stu-id="d814a-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="d814a-128">使用命令列工具來設定 PUA 保護：</span><span class="sxs-lookup"><span data-stu-id="d814a-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="d814a-129">在終端中執行下列命令，以設定 PUA 保護：</span><span class="sxs-lookup"><span data-stu-id="d814a-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="d814a-130">使用管理主控台來設定 PUA 保護：</span><span class="sxs-lookup"><span data-stu-id="d814a-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="d814a-131">在您的企業中，您可以從管理主控台（如 JAMF 或 Intune）設定 PUA 防護，類似于設定其他產品設定的方式。</span><span class="sxs-lookup"><span data-stu-id="d814a-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="d814a-132">如需詳細資訊，請參閱[macOS 主題上的 Microsoft Defender For Endpoint 的 Set 喜好設定](mac-preferences.md)中的[威脅類型設定](mac-preferences.md#threat-type-settings)一節。</span><span class="sxs-lookup"><span data-stu-id="d814a-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d814a-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="d814a-133">Related topics</span></span>

- [<span data-ttu-id="d814a-134">在 macOS 上設定 Microsoft Defender for Endpoint 的喜好設定</span><span class="sxs-lookup"><span data-stu-id="d814a-134">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>](mac-preferences.md)
