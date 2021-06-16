---
title: 啟用「有限的定期 Microsoft Defender 防毒軟體掃描」功能
description: 有限的定期掃描可讓您除了其他已安裝的 AV 提供者之外，使用 Microsoft Defender 防毒軟體
keywords: lps，有限，週期性，掃描，掃描，相容性，協力廠商，其他 av，停用
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ad49b08e687f4ba389616542bd607d4140e91132
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926688"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a><span data-ttu-id="6e11d-104">在 Microsoft Defender 防毒軟體中使用有限的定期掃描</span><span class="sxs-lookup"><span data-stu-id="6e11d-104">Use limited periodic scanning in Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6e11d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="6e11d-105">**Applies to:**</span></span>

- [<span data-ttu-id="6e11d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6e11d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6e11d-107">「定期掃描」是一種特殊類型的威脅偵測和修正，當您已在 Windows 10 裝置上安裝其他防病毒產品時，就可以啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="6e11d-107">Limited periodic scanning is a special type of threat detection and remediation that can be enabled when you have installed another antivirus product on a Windows 10 device.</span></span>

<span data-ttu-id="6e11d-108">只有在某些情況下才能啟用。</span><span class="sxs-lookup"><span data-stu-id="6e11d-108">It can only be enabled in certain situations.</span></span> <span data-ttu-id="6e11d-109">如需有限定期掃描的詳細資訊，以及 Microsoft Defender 防毒軟體如何與其他防病毒產品搭配運作，請參閱[Microsoft Defender 防毒軟體相容性](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="6e11d-109">For more information about limited periodic scanning and how Microsoft Defender Antivirus works with other antivirus products, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

<span data-ttu-id="6e11d-110">**Microsoft 不建議在企業環境中使用這項功能。這是主要供消費者使用的功能。**</span><span class="sxs-lookup"><span data-stu-id="6e11d-110">**Microsoft does not recommend using this feature in enterprise environments. This is a feature primarily intended for consumers.**</span></span> <span data-ttu-id="6e11d-111">這項功能只會使用有限的 Microsoft Defender 防毒軟體功能子集偵測惡意程式碼，而且將無法偵測大多數惡意程式碼和潛在不需要的軟體。</span><span class="sxs-lookup"><span data-stu-id="6e11d-111">This feature only uses a limited subset of the Microsoft Defender Antivirus capabilities to detect malware, and will not be able to detect most malware and potentially unwanted software.</span></span> <span data-ttu-id="6e11d-112">此外，管理與報告功能將會受到限制。</span><span class="sxs-lookup"><span data-stu-id="6e11d-112">Also, management and reporting capabilities will be limited.</span></span> <span data-ttu-id="6e11d-113">Microsoft 建議企業選擇他們的主要防病毒方案，並以獨佔方式使用。</span><span class="sxs-lookup"><span data-stu-id="6e11d-113">Microsoft recommends enterprises choose their primary antivirus solution and use it exclusively.</span></span>

## <a name="how-to-enable-limited-periodic-scanning"></a><span data-ttu-id="6e11d-114">如何啟用有限的定期掃描</span><span class="sxs-lookup"><span data-stu-id="6e11d-114">How to enable limited periodic scanning</span></span>

<span data-ttu-id="6e11d-115">根據預設，如果沒有安裝其他的防病毒產品，或其他產品已過期或無法正常運作，Microsoft Defender 防毒軟體會在 Windows 10 裝置上自行啟用。</span><span class="sxs-lookup"><span data-stu-id="6e11d-115">By default, Microsoft Defender Antivirus will enable itself on a Windows 10 device if there is no other antivirus product installed, or if the other product is out-of-date, expired, or not working correctly.</span></span>

<span data-ttu-id="6e11d-116">如果啟用 Microsoft Defender 防毒軟體，一般的選項會顯示在該裝置上進行設定：</span><span class="sxs-lookup"><span data-stu-id="6e11d-116">If Microsoft Defender Antivirus is enabled, the usual options will appear to configure it on that device:</span></span>

![顯示 Microsoft Defender AV 選項（包括掃描選項、設定及更新選項）的 Windows 安全性應用程式](images/vtp-wdav.png)

<span data-ttu-id="6e11d-118">如果已安裝另一種防病毒產品且運作正常，Microsoft Defender 防毒軟體會自行停用。</span><span class="sxs-lookup"><span data-stu-id="6e11d-118">If another antivirus product is installed and working correctly, Microsoft Defender Antivirus will disable itself.</span></span> <span data-ttu-id="6e11d-119">Windows 安全性應用程式會變更 **病毒 & 威脅防護**] 區段，以顯示 AV 產品的狀態，並提供產品設定選項的連結。</span><span class="sxs-lookup"><span data-stu-id="6e11d-119">The Windows Security app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.</span></span>

<span data-ttu-id="6e11d-120">在任何協力廠商 AV 產品下，新的連結會顯示為 **Microsoft Defender 防毒軟體選項**。</span><span class="sxs-lookup"><span data-stu-id="6e11d-120">Underneath any third party AV products, a new link will appear as **Microsoft Defender Antivirus options**.</span></span> <span data-ttu-id="6e11d-121">按一下此連結會展開以顯示可啟用有限定期掃描的切換功能。</span><span class="sxs-lookup"><span data-stu-id="6e11d-121">Clicking this link will expand to show the toggle that enables limited periodic scanning.</span></span> <span data-ttu-id="6e11d-122">請注意，[有限週期] 選項是以啟用或停用定期掃描的切換方式。</span><span class="sxs-lookup"><span data-stu-id="6e11d-122">Note that the limited periodic option is a toggle to enable or disable periodic scanning.</span></span> 

<span data-ttu-id="6e11d-123">將開關切換到 [ **開啟** ]，會在協力廠商 av 產品下顯示標準的 MICROSOFT Defender AV 選項。</span><span class="sxs-lookup"><span data-stu-id="6e11d-123">Sliding the switch to **On** will show the standard Microsoft Defender AV options underneath the third party AV product.</span></span> <span data-ttu-id="6e11d-124">[有限的定期掃描] 選項會出現在頁面底部。</span><span class="sxs-lookup"><span data-stu-id="6e11d-124">The limited periodic scanning option will appear at the bottom of the page.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6e11d-125">相關文章</span><span class="sxs-lookup"><span data-stu-id="6e11d-125">Related articles</span></span>

- [<span data-ttu-id="6e11d-126">設定行為、啟發學習法和即時保護</span><span class="sxs-lookup"><span data-stu-id="6e11d-126">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6e11d-127">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="6e11d-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)