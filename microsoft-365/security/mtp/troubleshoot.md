---
title: 疑難排解 Microsoft 365 Defender 服務問題
description: 尋找解決方案並解決已知的 Microsoft 365 Defender 問題
keywords: 疑難排解 Microsoft 威脅防護， 疑難排解， Azure ATP， 問題， 附加元件， 設定頁面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925715"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="93a2d-104">疑難排解 Microsoft 365 Defender 服務問題</span><span class="sxs-lookup"><span data-stu-id="93a2d-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="93a2d-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="93a2d-105">**Applies to:**</span></span>
- <span data-ttu-id="93a2d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93a2d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="93a2d-107">本節說明使用 Microsoft 365 Defender 服務時可能會出現的問題。</span><span class="sxs-lookup"><span data-stu-id="93a2d-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="93a2d-108">我看不到 Microsoft 365 Defender 內容</span><span class="sxs-lookup"><span data-stu-id="93a2d-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="93a2d-109">如果您在入口網站中沒在流覽窗格中看到事件、控制中心或搜尋等功能，您必須確認您的租使用者擁有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="93a2d-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="93a2d-110">如需詳細資訊，請參閱[先決條件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="93a2d-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="93a2d-111">Microsoft 365 Defender 事件不會顯示身分識別警示的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="93a2d-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="93a2d-112">如果您在環境中部署了身分識別的 Microsoft Defender，但您沒有看到屬於 Microsoft 365 Defender 事件的 Defender，您必須確認已啟用 Microsoft Cloud App 安全性與身分識別整合的 Defender。</span><span class="sxs-lookup"><span data-stu-id="93a2d-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="93a2d-113">詳細資訊請參閱 Microsoft [Defender 的身分識別整合](https://docs.microsoft.com/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="93a2d-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="93a2d-114">可開啟服務的設定頁面在哪裡？</span><span class="sxs-lookup"><span data-stu-id="93a2d-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="93a2d-115">若要開啟 Microsoft 365 Defender，請從 Microsoft 365 資訊安全中心的流覽窗格存取設定。 </span><span class="sxs-lookup"><span data-stu-id="93a2d-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="93a2d-116">只有您具有先決條件許可權和授權時，才能 [看到此流覽專案](mtp-enable.md#check-license-eligibility-and-required-permissions)。</span><span class="sxs-lookup"><span data-stu-id="93a2d-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
