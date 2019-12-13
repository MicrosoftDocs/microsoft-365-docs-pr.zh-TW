---
title: Microsoft 威脅防護服務問題的疑難排解
description: 尋找已知 Microsoft 威脅防護問題的解決方案與因應措施
keywords: Microsoft 威脅防護的疑難排解、疑難排解、問題
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 4c32f815e262abbe5d901f5c29323f83ef1b71d8
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910948"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="6e4ef-104">Microsoft 威脅防護服務問題的疑難排解</span><span class="sxs-lookup"><span data-stu-id="6e4ef-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="6e4ef-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="6e4ef-105">**Applies to:**</span></span>
- <span data-ttu-id="6e4ef-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="6e4ef-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6e4ef-107">本節說明使用 Microsoft 威脅防護服務時可能會發生的問題。</span><span class="sxs-lookup"><span data-stu-id="6e4ef-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="not-seeing-microsoft-threat-protection-content"></a><span data-ttu-id="6e4ef-108">看不到 Microsoft 威脅防護的內容</span><span class="sxs-lookup"><span data-stu-id="6e4ef-108">Not seeing Microsoft Threat Protection content</span></span>
<span data-ttu-id="6e4ef-109">如果您在入口網站的導覽頁面上看不到 [事件]、[控制中心] 或 [搜捕] 等功能，您需要驗證您的租用戶是否具有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="6e4ef-109">If you don't see capabilities on the navigation page such as the Incidents, Action Center, or Hunting in your portal you'll need to verify that your tenant has the appropriate license.</span></span> 

<span data-ttu-id="6e4ef-110">如需詳細資訊，請參閱[先決條件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="6e4ef-110">For more information, see [](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="6e4ef-111">Azure ATP 警示沒有在 Microsoft 威脅防護事件中顯示</span><span class="sxs-lookup"><span data-stu-id="6e4ef-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="6e4ef-112">如果您已在環境中部署 Azure ATP，但並沒有在 Microsoft 威脅防護事件中看到 Azure ATP 警報，您需要確定已啟用 Microsoft 雲端 App 安全性和 Azure ATP 整合。</span><span class="sxs-lookup"><span data-stu-id="6e4ef-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="6e4ef-113">如需詳細資訊，請參閱 [Azure ATP 整合](https://docs.microsoft.com/cloud-app-security/aatp-integration)。</span><span class="sxs-lookup"><span data-stu-id="6e4ef-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="6e4ef-114">Microsoft 威脅防護是否可用於美國政府社群雲端 (GCC) 或GCC High？</span><span class="sxs-lookup"><span data-stu-id="6e4ef-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="6e4ef-115">目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="6e4ef-115">At the moment, it is not available.</span></span> 


