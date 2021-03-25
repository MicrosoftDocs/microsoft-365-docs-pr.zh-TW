---
title: 設定攻擊面減少
description: 使用 Microsoft Intune、Microsoft Endpoint Configuration 管理員、PowerShell Cmdlet 及群組原則來設定攻擊面降低。
keywords: asr、攻擊面減少、windows defender、microsoft defender、防毒軟體、av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166158"
---
# <a name="configure-attack-surface-reduction"></a><span data-ttu-id="004e8-104">設定攻擊面減少</span><span class="sxs-lookup"><span data-stu-id="004e8-104">Configure attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="004e8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="004e8-105">**Applies to:**</span></span>
- [<span data-ttu-id="004e8-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="004e8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="004e8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="004e8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="004e8-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="004e8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="004e8-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="004e8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="004e8-110">您可以使用許多工具來設定攻擊面減少，包括：</span><span class="sxs-lookup"><span data-stu-id="004e8-110">You can configure attack surface reduction with many tools, including:</span></span>

* <span data-ttu-id="004e8-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="004e8-111">Microsoft Intune</span></span>
* <span data-ttu-id="004e8-112">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="004e8-112">Microsoft Endpoint Configuration Manager</span></span>
* <span data-ttu-id="004e8-113">群組原則</span><span class="sxs-lookup"><span data-stu-id="004e8-113">Group Policy</span></span>
* <span data-ttu-id="004e8-114">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="004e8-114">PowerShell cmdlets</span></span>

<span data-ttu-id="004e8-115">文章</span><span class="sxs-lookup"><span data-stu-id="004e8-115">Article</span></span> | <span data-ttu-id="004e8-116">描述</span><span class="sxs-lookup"><span data-stu-id="004e8-116">Description</span></span>
-|-
[<span data-ttu-id="004e8-117">啟用 Microsoft Edge 的硬體隔離</span><span class="sxs-lookup"><span data-stu-id="004e8-117">Enable hardware-based isolation for Microsoft Edge</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | <span data-ttu-id="004e8-118">如何準備及安裝應用程式防護（包括硬體和軟體需求）</span><span class="sxs-lookup"><span data-stu-id="004e8-118">How to prepare for and install Application Guard, including hardware and software requirements</span></span>
[<span data-ttu-id="004e8-119">啟用應用程式控制</span><span class="sxs-lookup"><span data-stu-id="004e8-119">Enable application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|<span data-ttu-id="004e8-120">操作方法：控制使用者執行的應用程式，並保護核心模式進程</span><span class="sxs-lookup"><span data-stu-id="004e8-120">How to control applications run by users and protect kernel mode processes</span></span>
[<span data-ttu-id="004e8-121">Exploit protection</span><span class="sxs-lookup"><span data-stu-id="004e8-121">Exploit protection</span></span>](./enable-exploit-protection.md)|<span data-ttu-id="004e8-122">如何在兩種作業系統處理常式和個別應用程式上自動套用利用漏洞緩解技術</span><span class="sxs-lookup"><span data-stu-id="004e8-122">How to automatically apply exploit mitigation techniques on both operating system processes and on individual apps</span></span>
[<span data-ttu-id="004e8-123">網路保護</span><span class="sxs-lookup"><span data-stu-id="004e8-123">Network protection</span></span>](./enable-network-protection.md)|<span data-ttu-id="004e8-124">如何防止使用者使用任何應用程式來存取危險網域</span><span class="sxs-lookup"><span data-stu-id="004e8-124">How to prevent users from using any apps to access dangerous domains</span></span>
[<span data-ttu-id="004e8-125">受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="004e8-125">Controlled folder access</span></span>](./enable-controlled-folders.md)|<span data-ttu-id="004e8-126">如何保護惡意應用程式中的重要資料</span><span class="sxs-lookup"><span data-stu-id="004e8-126">How to protect valuable data from malicious apps</span></span>
[<span data-ttu-id="004e8-127">受攻擊面縮小</span><span class="sxs-lookup"><span data-stu-id="004e8-127">Attack surface reduction</span></span>](./enable-attack-surface-reduction.md)|<span data-ttu-id="004e8-128">如何防止使用漏洞搜尋惡意程式碼通常使用的動作和應用程式</span><span class="sxs-lookup"><span data-stu-id="004e8-128">How to prevent actions and apps that are typically used by exploit-seeking malware</span></span>
[<span data-ttu-id="004e8-129">網路防火牆</span><span class="sxs-lookup"><span data-stu-id="004e8-129">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|<span data-ttu-id="004e8-130">如何保護網路上的裝置和資料</span><span class="sxs-lookup"><span data-stu-id="004e8-130">How to protect devices and data across a network</span></span>

