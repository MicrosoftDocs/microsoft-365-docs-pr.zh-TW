---
title: Microsoft 威脅防護服務問題的疑難排解
description: 尋找已知 Microsoft 威脅防護問題的解決方案與因應措施
keywords: 疑難排解 Microsoft 威脅防護、疑難排解、Azure ATP、問題、附加元件、設定頁面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: e19e5758f4d42799c96ecec51fd6295e3da19f9b
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844915"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="0272a-104">Microsoft 威脅防護服務問題的疑難排解</span><span class="sxs-lookup"><span data-stu-id="0272a-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="0272a-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="0272a-105">**Applies to:**</span></span>
- <span data-ttu-id="0272a-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="0272a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0272a-107">本節說明使用 Microsoft 威脅防護服務時可能會發生的問題。</span><span class="sxs-lookup"><span data-stu-id="0272a-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="0272a-108">我沒有看到 Microsoft 威脅防護內容</span><span class="sxs-lookup"><span data-stu-id="0272a-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="0272a-109">如果您在流覽窗格中看不到 [事件]、[重要訊息中心] 或 [搜尋] 等功能，您必須確認您的承租人具有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="0272a-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="0272a-110">如需詳細資訊，請參閱[先決條件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="0272a-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="0272a-111">Azure ATP 警示沒有在 Microsoft 威脅防護事件中顯示</span><span class="sxs-lookup"><span data-stu-id="0272a-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="0272a-112">如果您已在環境中部署 Azure ATP，但並沒有在 Microsoft 威脅防護事件中看到 Azure ATP 警報，您需要確定已啟用 Microsoft 雲端 App 安全性和 Azure ATP 整合。</span><span class="sxs-lookup"><span data-stu-id="0272a-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="0272a-113">如需詳細資訊，請參閱 [Azure ATP 整合](https://docs.microsoft.com/cloud-app-security/aatp-integration)。</span><span class="sxs-lookup"><span data-stu-id="0272a-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="0272a-114">開啟服務的設定頁面位於何處？</span><span class="sxs-lookup"><span data-stu-id="0272a-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="0272a-115">若要開啟 Microsoft 威脅防護，請從 Microsoft 365 安全性中心的功能窗格存取**設定**。</span><span class="sxs-lookup"><span data-stu-id="0272a-115">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="0272a-116">只有當您具有[必要許可權和授權](mtp-enable.md#check-license-eligibility-and-required-permissions)時，才會顯示此導覽專案。</span><span class="sxs-lookup"><span data-stu-id="0272a-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

