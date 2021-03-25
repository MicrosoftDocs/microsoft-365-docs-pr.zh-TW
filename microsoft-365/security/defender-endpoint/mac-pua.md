---
title: 使用 Microsoft Defender ATP for Mac 偵測並封鎖可能有害的應用程式
description: 使用 Microsoft Defender ATP for Mac，偵測並封鎖可能有害的應用程式 (PUA) 。
keywords: microsoft、defender、atp、mac、pua、pus
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
ms.openlocfilehash: 6e65e847403160d24eac04a553ca16a46314e33d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187418"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="a8dda-104">使用 Microsoft Defender for Mac 偵測和封鎖可能有害的應用程式</span><span class="sxs-lookup"><span data-stu-id="a8dda-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a8dda-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a8dda-105">**Applies to:**</span></span>
- [<span data-ttu-id="a8dda-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a8dda-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a8dda-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8dda-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a8dda-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a8dda-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a8dda-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a8dda-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="a8dda-110">Microsoft Defender for Mac 中可能有害的應用程式 (PUA) 保護功能可偵測並封鎖您網路中端點上的 PUA 檔案。</span><span class="sxs-lookup"><span data-stu-id="a8dda-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint for Mac can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="a8dda-111">這些應用程式不會被視為病毒、惡意程式碼或其他類型的威脅，但是可能會對對其效能或使用不良影響的端點執行動作。</span><span class="sxs-lookup"><span data-stu-id="a8dda-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="a8dda-112">PUA 也可以參考被視為具有不良信譽的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8dda-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="a8dda-113">這些應用程式可能會增加網路受到惡意程式碼感染的風險，使惡意程式碼感染難以識別，而且可以在清理應用程式時浪費 IT 資源。</span><span class="sxs-lookup"><span data-stu-id="a8dda-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="a8dda-114">運作方式</span><span class="sxs-lookup"><span data-stu-id="a8dda-114">How it works</span></span>

<span data-ttu-id="a8dda-115">Microsoft Defender for Mac 可以偵測並報告 PUA 檔案。</span><span class="sxs-lookup"><span data-stu-id="a8dda-115">Microsoft Defender for Endpoint for Mac can detect and report PUA files.</span></span> <span data-ttu-id="a8dda-116">當以封鎖模式設定時，PUA 檔案會移至隔離區。</span><span class="sxs-lookup"><span data-stu-id="a8dda-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="a8dda-117">在端點上偵測到 PUA 時，Mac 版端點的 Microsoft Defender 會向使用者呈現通知，除非已停用通知。</span><span class="sxs-lookup"><span data-stu-id="a8dda-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint for Mac presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="a8dda-118">威脅名稱會包含 "Application" 一詞。</span><span class="sxs-lookup"><span data-stu-id="a8dda-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="a8dda-119">設定 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="a8dda-119">Configure PUA protection</span></span>

<span data-ttu-id="a8dda-120">您可以採用下列其中一種方式，設定 Microsoft Defender for Mac 中的 PUA 保護：</span><span class="sxs-lookup"><span data-stu-id="a8dda-120">PUA protection in Microsoft Defender for Endpoint for Mac can be configured in one of the following ways:</span></span>

- <span data-ttu-id="a8dda-121">**Off**：已停用 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="a8dda-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="a8dda-122">**Audit**： PUA files 會在產品記錄中報告，但不會在 Microsoft Defender Security Center 中報告。</span><span class="sxs-lookup"><span data-stu-id="a8dda-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="a8dda-123">使用者不會呈現任何通知，產品也不會採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="a8dda-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="a8dda-124">**封鎖**： PUA 檔案會在產品記錄和 Microsoft Defender Security Center 中報告。</span><span class="sxs-lookup"><span data-stu-id="a8dda-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="a8dda-125">使用者會看到一則通知，並由產品採取動作。</span><span class="sxs-lookup"><span data-stu-id="a8dda-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="a8dda-126">根據預設，會在 **審核** 模式中設定 PUA 保護。</span><span class="sxs-lookup"><span data-stu-id="a8dda-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="a8dda-127">您可以從命令列或從管理主控台，設定 PUA 檔案的處理方式。</span><span class="sxs-lookup"><span data-stu-id="a8dda-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="a8dda-128">使用命令列工具來設定 PUA 保護：</span><span class="sxs-lookup"><span data-stu-id="a8dda-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="a8dda-129">在終端中執行下列命令，以設定 PUA 保護：</span><span class="sxs-lookup"><span data-stu-id="a8dda-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="a8dda-130">使用管理主控台來設定 PUA 保護：</span><span class="sxs-lookup"><span data-stu-id="a8dda-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="a8dda-131">在您的企業中，您可以從管理主控台（如 JAMF 或 Intune）設定 PUA 防護，類似于設定其他產品設定的方式。</span><span class="sxs-lookup"><span data-stu-id="a8dda-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="a8dda-132">如需詳細資訊，請參閱[Microsoft Defender For Mac 的首選項設定](mac-preferences.md)的[威脅類型設定](mac-preferences.md#threat-type-settings)區段主題。</span><span class="sxs-lookup"><span data-stu-id="a8dda-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a8dda-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="a8dda-133">Related topics</span></span>

- [<span data-ttu-id="a8dda-134">設定 Mac 的 Microsoft Defender 端點偏好設定</span><span class="sxs-lookup"><span data-stu-id="a8dda-134">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>](mac-preferences.md)
