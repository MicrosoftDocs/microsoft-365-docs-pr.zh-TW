---
title: 評估 Microsoft Defender 防毒軟體
description: 所有規模的企業都可以使用本指南評估及測試 Microsoft Defender 防病毒在 Windows 10 中所提供的保護。
keywords: Microsoft Defender 防毒程式，cloud protection，cloud，反惡意程式碼，安全性，Defender，評估，測試，保護，比較，即時保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f3fa1ca854a75025f850c85637cd3e08678bdbc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764828"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="300fa-104">評估 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="300fa-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="300fa-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="300fa-105">**Applies to:**</span></span>

- [<span data-ttu-id="300fa-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="300fa-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="300fa-107">使用此指南可判斷 Microsoft Defender 防毒軟體如何保護您免受病毒、惡意程式碼和潛在的有害應用程式的威脅。</span><span class="sxs-lookup"><span data-stu-id="300fa-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="300fa-108">您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範網站，以確認下列功能正在運作中，並查看其運作方式：</span><span class="sxs-lookup"><span data-stu-id="300fa-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="300fa-109">雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="300fa-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="300fa-110">Fast 教學 (包括第一次看到區塊) </span><span class="sxs-lookup"><span data-stu-id="300fa-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="300fa-111">可能有害的應用程式封鎖</span><span class="sxs-lookup"><span data-stu-id="300fa-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="300fa-112">它會說明適用于小型和大型企業的 Microsoft Defender 防毒軟體的重要下一代保護功能，以及它們如何增加整個網路的惡意程式碼偵測和保護。</span><span class="sxs-lookup"><span data-stu-id="300fa-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="300fa-113">您可以選擇個別設定和評估每個設定，或一次全部設定。</span><span class="sxs-lookup"><span data-stu-id="300fa-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="300fa-114">我們已根據一般評估案例分組類似設定，並包含使用 PowerShell 來啟用設定的指示。</span><span class="sxs-lookup"><span data-stu-id="300fa-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="300fa-115">您可以使用 PDF 格式，以供離線查看使用的指南：</span><span class="sxs-lookup"><span data-stu-id="300fa-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="300fa-116">下載 PDF 格式的指南</span><span class="sxs-lookup"><span data-stu-id="300fa-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="300fa-117">您也可以下載可讓指南中所述之所有設定自動啟用的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="300fa-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="300fa-118">您可以在上述的 PDF 下載上，或從 PowerShell 圖庫中個別取得腳本：</span><span class="sxs-lookup"><span data-stu-id="300fa-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="300fa-119">下載 PowerShell 腳本，以自動設定設定</span><span class="sxs-lookup"><span data-stu-id="300fa-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="300fa-120">此指南目前適用于 Microsoft Defender 防毒軟體的單一機器評估。</span><span class="sxs-lookup"><span data-stu-id="300fa-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="300fa-121">啟用本指南中的所有設定可能不適合實際部署。</span><span class="sxs-lookup"><span data-stu-id="300fa-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="300fa-122">如需實際部署和監控整個網路上的 Microsoft Defender 防病毒的最新建議，請參閱 [部署 Microsoft Defender 防毒軟體](deploy-manage-report-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="300fa-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="300fa-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="300fa-123">Related topics</span></span>

- [<span data-ttu-id="300fa-124">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="300fa-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="300fa-125">部署 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="300fa-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)