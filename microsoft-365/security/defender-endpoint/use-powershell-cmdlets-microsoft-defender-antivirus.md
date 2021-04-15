---
title: 使用 PowerShell Cmdlet 來設定及執行 Microsoft Defender AV
description: 在 Windows 10 中，您可以使用 PowerShell Cmdlet 來執行掃描、更新安全性情報，以及變更 Microsoft Defender 防病毒中的設定。
keywords: 掃描、命令列、mpcmdrun、defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765296"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="a1cef-104">使用 PowerShell Cmdlet 來設定及管理 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="a1cef-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a1cef-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a1cef-105">**Applies to:**</span></span>

- [<span data-ttu-id="a1cef-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a1cef-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a1cef-107">您可以使用 PowerShell 在 Windows Defender 中執行各種功能。</span><span class="sxs-lookup"><span data-stu-id="a1cef-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="a1cef-108">類似于命令提示字元或命令列，PowerShell 是以任務為基礎的命令列命令介面及指令碼語言，特別是用來管理系統。</span><span class="sxs-lookup"><span data-stu-id="a1cef-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="a1cef-109">您可以在 [MSDN 的 PowerShell hub](/previous-versions/msdn10/mt173057(v=msdn.10))中深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="a1cef-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="a1cef-110">如需 Cmdlet 及其功能和可用參數的清單，請參閱 [Defender Cmdlet](/powershell/module/defender) 主題。</span><span class="sxs-lookup"><span data-stu-id="a1cef-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="a1cef-111">PowerShell Cmdlet 在 Windows 伺服器環境中最為有用，但不依賴圖形使用者介面 (GUI) 來設定軟體。</span><span class="sxs-lookup"><span data-stu-id="a1cef-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="a1cef-112">PowerShell Cmdlet 不應該用作完整網路原則管理基礎結構（例如 [Microsoft 端點設定管理員](/configmgr)、 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))或 [Microsoft DEFENDER 防病毒群組原則 ADMX 範本](https://www.microsoft.com/download/101445)）的取代。</span><span class="sxs-lookup"><span data-stu-id="a1cef-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="a1cef-113">PowerShell 所做的變更會影響部署變更之端點的本機設定。</span><span class="sxs-lookup"><span data-stu-id="a1cef-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="a1cef-114">這表示使用「群組原則」、「Microsoft 端點設定管理員」或 Microsoft Intune 部署原則，可以覆寫 PowerShell 所做的變更。</span><span class="sxs-lookup"><span data-stu-id="a1cef-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="a1cef-115">您可以 [設定哪些設定可以在本機上使用本機原則覆寫](configure-local-policy-overrides-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="a1cef-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="a1cef-116">PowerShell 一般會安裝在資料夾底下 `%SystemRoot%\system32\WindowsPowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="a1cef-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="a1cef-117">使用 Microsoft Defender 防病毒 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a1cef-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="a1cef-118">在 Windows 搜尋列中，輸入 **powershell**。</span><span class="sxs-lookup"><span data-stu-id="a1cef-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="a1cef-119">從結果中選取 [ **Windows PowerShell** ]，以開啟介面。</span><span class="sxs-lookup"><span data-stu-id="a1cef-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="a1cef-120">輸入 PowerShell 命令和任何參數。</span><span class="sxs-lookup"><span data-stu-id="a1cef-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="a1cef-121">您可能需要以系統管理員模式開啟 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a1cef-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="a1cef-122">在 [開始] 功能表中，以滑鼠右鍵按一下專案，按一下 [以 **系統管理員身分執行** ]，然後在許可權提示中按一下 **[是]** 。</span><span class="sxs-lookup"><span data-stu-id="a1cef-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="a1cef-123">若要針對任何 Cmdlet 開啟線上說明，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="a1cef-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="a1cef-124">省略此 `-online` 參數可取得本機快取説明。</span><span class="sxs-lookup"><span data-stu-id="a1cef-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a1cef-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="a1cef-125">Related topics</span></span>

- [<span data-ttu-id="a1cef-126">管理及設定工具的參考主題</span><span class="sxs-lookup"><span data-stu-id="a1cef-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a1cef-127">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="a1cef-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="a1cef-128">Microsoft Defender 防病毒 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a1cef-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender)