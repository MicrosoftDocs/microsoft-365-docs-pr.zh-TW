---
title: 使用 Microsoft 端點管理員設定 Microsoft Defender 防毒軟體
description: 使用 Microsoft 端點管理員和 Microsoft Intune 設定 Microsoft Defender AV 和 Endpoint Protection
keywords: scep、intune、endpoint protection、configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683748"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="60f3b-104">使用 Microsoft 端點管理員來設定及管理 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="60f3b-104">Use Microsoft Endpoint Manager to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="60f3b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="60f3b-105">**Applies to:**</span></span>

- [<span data-ttu-id="60f3b-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="60f3b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="60f3b-107">您可以使用[Microsoft 端點管理員](/mem/endpoint-manager-overview)來設定 Microsoft Defender 防毒軟體掃描。</span><span class="sxs-lookup"><span data-stu-id="60f3b-107">You can use [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to configure Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="60f3b-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)及[Configuration Manager](/mem/configmgr/core/understand/introduction)現在是端點管理員的一部分。</span><span class="sxs-lookup"><span data-stu-id="60f3b-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Configuration Manager](/mem/configmgr/core/understand/introduction) are now part of Endpoint Manager.</span></span>  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a><span data-ttu-id="60f3b-109">設定端點管理員中的 Microsoft Defender 防毒軟體掃描</span><span class="sxs-lookup"><span data-stu-id="60f3b-109">Configure Microsoft Defender Antivirus scans in Endpoint Manager</span></span>

1. <span data-ttu-id="60f3b-110">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) ，然後登入。</span><span class="sxs-lookup"><span data-stu-id="60f3b-110">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), and sign in.</span></span>

2. <span data-ttu-id="60f3b-111">流覽至 **端點安全性**。</span><span class="sxs-lookup"><span data-stu-id="60f3b-111">Navigate to **Endpoint Security**.</span></span>

3. <span data-ttu-id="60f3b-112">在 [ **管理**] 下，選擇 [ **防病毒**]。</span><span class="sxs-lookup"><span data-stu-id="60f3b-112">Under **Manage**, choose **Antivirus**.</span></span>

4. <span data-ttu-id="60f3b-113">選取您的 Microsoft Defender 防毒軟體原則。</span><span class="sxs-lookup"><span data-stu-id="60f3b-113">Select your Microsoft Defender Antivirus policy.</span></span> 

5. <span data-ttu-id="60f3b-114">在 **[管理]** 底下，選擇 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="60f3b-114">Under **Manage**, choose **Properties**.</span></span>

6. <span data-ttu-id="60f3b-115">在 **[組態設定]** 旁邊，選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="60f3b-115">Next to **Configuration settings**, choose **Edit**.</span></span>

7. <span data-ttu-id="60f3b-116">展開 [ **Scan** ] （掃描）區段，然後查看或編輯您的掃描設定。</span><span class="sxs-lookup"><span data-stu-id="60f3b-116">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

8. <span data-ttu-id="60f3b-117">選擇 [ **審閱 + 儲存**</span><span class="sxs-lookup"><span data-stu-id="60f3b-117">Choose **Review + save**</span></span>


> [!TIP]
> <span data-ttu-id="60f3b-118">需要協助？</span><span class="sxs-lookup"><span data-stu-id="60f3b-118">Need help?</span></span> <span data-ttu-id="60f3b-119">請參閱[Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security)。</span><span class="sxs-lookup"><span data-stu-id="60f3b-119">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="60f3b-120">相關文章</span><span class="sxs-lookup"><span data-stu-id="60f3b-120">Related articles</span></span>

- [<span data-ttu-id="60f3b-121">管理及設定工具的參考文章</span><span class="sxs-lookup"><span data-stu-id="60f3b-121">Reference articles for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="60f3b-122">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="60f3b-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)