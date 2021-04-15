---
title: 使用 Configuration Manager 和 Intune 設定 Microsoft Defender 防毒軟體
description: 使用 Microsoft 端點管理員和 Microsoft Intune 來設定 Microsoft Defender AV 和 Endpoint Protection
keywords: scep、intune、endpoint protection、configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/26/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 647bda97cfbec5e1583ef66ebd3e9d445371d540
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51749863"
---
# <a name="use-microsoft-endpoint-manager-and-microsoft-intune-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="cddc2-104">使用 Microsoft 端點管理員和 Microsoft Intune 來設定及管理 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="cddc2-104">Use Microsoft Endpoint Manager and Microsoft Intune to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cddc2-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="cddc2-105">**Applies to:**</span></span>

- [<span data-ttu-id="cddc2-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cddc2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cddc2-107">如果您使用 Microsoft 端點管理員或 Microsoft Intune 管理網路上的端點，您現在可以使用 Microsoft 端點管理員來管理 Microsoft Defender 防病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="cddc2-107">If you were using Microsoft Endpoint Manager or Microsoft Intune to manage the endpoints on your network, you can now use Microsoft Endpoint Manager to manage Microsoft Defender Antivirus scans.</span></span>

1. <span data-ttu-id="cddc2-108">在 Microsoft 端點管理員管理中心 () 中 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ，流覽至 [ **端點安全性**]。</span><span class="sxs-lookup"><span data-stu-id="cddc2-108">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Endpoint Security**.</span></span>

2. <span data-ttu-id="cddc2-109">在 [ **管理**] 下，選擇 [ **防病毒**]。</span><span class="sxs-lookup"><span data-stu-id="cddc2-109">Under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="cddc2-110">選取您的 Microsoft Defender 防病毒原則。</span><span class="sxs-lookup"><span data-stu-id="cddc2-110">Select your Microsoft Defender Antivirus policy.</span></span> 

4. <span data-ttu-id="cddc2-111">在 [ **管理**] 下，選擇 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="cddc2-111">Under **Manage**, choose **Properties**.</span></span>

5. <span data-ttu-id="cddc2-112">在 [ **設定設定**] 旁，選擇 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="cddc2-112">Next to **Configuration settings**, choose **Edit**.</span></span>

6. <span data-ttu-id="cddc2-113">展開 [ **Scan** ] （掃描）區段，然後查看或編輯您的掃描設定。</span><span class="sxs-lookup"><span data-stu-id="cddc2-113">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

7. <span data-ttu-id="cddc2-114">選擇 [ **審閱 + 儲存**</span><span class="sxs-lookup"><span data-stu-id="cddc2-114">Choose **Review + save**</span></span>

<span data-ttu-id="cddc2-115">需要協助？</span><span class="sxs-lookup"><span data-stu-id="cddc2-115">Need help?</span></span> <span data-ttu-id="cddc2-116">請參閱 [Manage endpoint security In Microsoft Intune](/mem/intune/protect/endpoint-security)。</span><span class="sxs-lookup"><span data-stu-id="cddc2-116">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="cddc2-117">相關文章</span><span class="sxs-lookup"><span data-stu-id="cddc2-117">Related articles</span></span>

- [<span data-ttu-id="cddc2-118">管理及設定工具的參考主題</span><span class="sxs-lookup"><span data-stu-id="cddc2-118">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cddc2-119">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="cddc2-119">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)