---
title: '以硬體為基礎的隔離 (Windows 10) '
ms.reviewer: ''
description: 深入瞭解 Windows 10 中以硬體為基礎的隔離如何協助抵禦惡意程式碼。
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: 82841ccdb2a6ad09f43d0bf8d12cb54fe44d6dfe
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186902"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="2fe7a-103">Windows 10 中以硬體為基礎的隔離</span><span class="sxs-lookup"><span data-stu-id="2fe7a-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2fe7a-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2fe7a-104">**Applies to:**</span></span>
- [<span data-ttu-id="2fe7a-105">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2fe7a-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2fe7a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2fe7a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2fe7a-107">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2fe7a-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2fe7a-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2fe7a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="2fe7a-109">以硬體為基礎的隔離可協助保護 Windows 10 中的系統完整性，並與 Microsoft Defender for Endpoint 整合。</span><span class="sxs-lookup"><span data-stu-id="2fe7a-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="2fe7a-110">功能</span><span class="sxs-lookup"><span data-stu-id="2fe7a-110">Feature</span></span> | <span data-ttu-id="2fe7a-111">描述</span><span class="sxs-lookup"><span data-stu-id="2fe7a-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="2fe7a-112">Windows Defender 應用程式防護</span><span class="sxs-lookup"><span data-stu-id="2fe7a-112">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="2fe7a-113">Application Guard 會保護您的裝置免受高級攻擊，同時保持您的工作效率。</span><span class="sxs-lookup"><span data-stu-id="2fe7a-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="2fe7a-114">使用獨特的硬體隔離方法，目標是將不受信任的網站和 PDF 檔，隔離與作業系統（透過原生 Windows 虛擬機器監控程式）分開的輕量容器內。</span><span class="sxs-lookup"><span data-stu-id="2fe7a-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="2fe7a-115">如果不受信任的網站或 PDF 檔遭到惡意，它仍保留在 Application Guard 的安全容器內，使桌上型電腦受到保護，並使攻擊者遠離您的企業資料。</span><span class="sxs-lookup"><span data-stu-id="2fe7a-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="2fe7a-116">Windows Defender 系統防護</span><span class="sxs-lookup"><span data-stu-id="2fe7a-116">Windows Defender System Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="2fe7a-117">在啟動和執行後，系統保護會保護及維護系統的完整性，並使用認證來驗證系統完整性。</span><span class="sxs-lookup"><span data-stu-id="2fe7a-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |

