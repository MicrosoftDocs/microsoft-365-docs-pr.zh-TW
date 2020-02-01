---
title: Microsoft 威脅防護服務問題的疑難排解
description: 尋找已知 Microsoft 威脅防護問題的解決方案與因應措施
keywords: 疑難排解 Microsoft 威脅防護、 進行疑難排解，Azure ATP、 問題、 附加元件、 設定] 頁面
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
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661979"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="d52dd-104">Microsoft 威脅防護服務問題的疑難排解</span><span class="sxs-lookup"><span data-stu-id="d52dd-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="d52dd-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="d52dd-105">**Applies to:**</span></span>
- <span data-ttu-id="d52dd-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="d52dd-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d52dd-107">本節說明使用 Microsoft 威脅防護服務時可能會發生的問題。</span><span class="sxs-lookup"><span data-stu-id="d52dd-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="d52dd-108">看不到 Microsoft 威脅保護內容</span><span class="sxs-lookup"><span data-stu-id="d52dd-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="d52dd-109">如果您沒有看到例如事件、 重要訊息中心或狩獵的功能窗格上的功能，在您的入口網站中，您需要確認您的租用戶都有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="d52dd-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="d52dd-110">如需詳細資訊，請參閱[先決條件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="d52dd-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="d52dd-111">Azure ATP 警示沒有在 Microsoft 威脅防護事件中顯示</span><span class="sxs-lookup"><span data-stu-id="d52dd-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="d52dd-112">如果您已在環境中部署 Azure ATP，但並沒有在 Microsoft 威脅防護事件中看到 Azure ATP 警報，您需要確定已啟用 Microsoft 雲端 App 安全性和 Azure ATP 整合。</span><span class="sxs-lookup"><span data-stu-id="d52dd-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="d52dd-113">如需詳細資訊，請參閱 [Azure ATP 整合](https://docs.microsoft.com/cloud-app-security/aatp-integration)。</span><span class="sxs-lookup"><span data-stu-id="d52dd-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="d52dd-114">Microsoft 威脅防護是否可用於美國政府社群雲端 (GCC) 或GCC High？</span><span class="sxs-lookup"><span data-stu-id="d52dd-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="d52dd-115">目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="d52dd-115">At the moment, it is not available.</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="d52dd-116">[設定] 頁面開啟服務位於何處？</span><span class="sxs-lookup"><span data-stu-id="d52dd-116">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="d52dd-117">若要開啟 Microsoft 威脅防護，請從功能窗格中，Microsoft 365 安全性中心存取**設定**。</span><span class="sxs-lookup"><span data-stu-id="d52dd-117">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="d52dd-118">此導覽項目會顯示只有當您具備[必要權限和授權](mtp-enable.md#check-license-eligibility-and-required-permissions)。</span><span class="sxs-lookup"><span data-stu-id="d52dd-118">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a><span data-ttu-id="d52dd-119">可以使用附加元件而不是必要的 E5 授權嗎？</span><span class="sxs-lookup"><span data-stu-id="d52dd-119">Can I use an add-on instead of the required E5 licenses?</span></span>
<span data-ttu-id="d52dd-120">目前有任何 Microsoft 威脅防護的附加元件。</span><span class="sxs-lookup"><span data-stu-id="d52dd-120">There are currently no add-ons for Microsoft Threat Protection.</span></span> [<span data-ttu-id="d52dd-121">請參閱授權需求</span><span class="sxs-lookup"><span data-stu-id="d52dd-121">See licensing requirements</span></span>](prerequisites.md) 

