---
title: 使用 WMI 設定 Microsoft Defender 防毒程式
description: 瞭解如何使用 WMI 腳本來設定及管理 Microsoft Defender 防病毒，以在 Microsoft Defender for Endpoint 中取得、修改和更新設定。
keywords: wmi、腳本、windows management instrumentation、設定
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764060"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="49568-104">使用 Windows Management Instrumentation (WMI) 設定及管理 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="49568-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="49568-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="49568-105">**Applies to:**</span></span>

- [<span data-ttu-id="49568-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="49568-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="49568-107">Windows Management Instrumentation (WMI) 是指令碼介面，可讓您檢索、修改和更新設定。</span><span class="sxs-lookup"><span data-stu-id="49568-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="49568-108">若要深入瞭解，請參閱 [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page)上的 WMI。</span><span class="sxs-lookup"><span data-stu-id="49568-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="49568-109">Microsoft Defender 防毒程式有許多特定的 WMI 類別，可用來執行大部分與群組原則及其他管理工具相同的功能。</span><span class="sxs-lookup"><span data-stu-id="49568-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="49568-110">許多類別與 [Defender PowerShell Cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)類似。</span><span class="sxs-lookup"><span data-stu-id="49568-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="49568-111">[MSDN Windows Defender WMIv2 提供者參考文件庫](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)會列出適用于 Microsoft Defender 防病毒的 WMI 類別，並包含範例腳本。</span><span class="sxs-lookup"><span data-stu-id="49568-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="49568-112">使用 WMI 所做的變更會影響部署變更之端點上的本機設定。</span><span class="sxs-lookup"><span data-stu-id="49568-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="49568-113">這表示使用「群組原則」、「Microsoft 端點設定管理員」或 Microsoft Intune 部署原則，可以覆寫透過 WMI 所做的變更。</span><span class="sxs-lookup"><span data-stu-id="49568-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="49568-114">您可以 [設定哪些設定可以在本機上使用本機原則覆寫](configure-local-policy-overrides-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="49568-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="49568-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="49568-115">Related topics</span></span>

- [<span data-ttu-id="49568-116">管理及設定工具的參考主題</span><span class="sxs-lookup"><span data-stu-id="49568-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="49568-117">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="49568-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)