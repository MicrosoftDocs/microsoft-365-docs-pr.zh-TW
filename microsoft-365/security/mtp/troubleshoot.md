---
title: 疑難排解 Microsoft 365 Defender 服務問題
description: 尋找已知的 Microsoft 365 Defender 問題的解決方案及變通辦法
keywords: 疑難排解 Microsoft 威脅防護、疑難排解、Azure ATP、問題、附加元件、設定頁面
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
ms.openlocfilehash: d01912532ad2a00abbecee0d0a337be7baf87017
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918663"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="5b92d-104">疑難排解 Microsoft 365 Defender 服務問題</span><span class="sxs-lookup"><span data-stu-id="5b92d-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5b92d-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="5b92d-105">**Applies to:**</span></span>
- <span data-ttu-id="5b92d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b92d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5b92d-107">本節說明當您使用 Microsoft 365 Defender 服務時可能會發生的問題。</span><span class="sxs-lookup"><span data-stu-id="5b92d-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="5b92d-108">我未看到 Microsoft 365 Defender 內容</span><span class="sxs-lookup"><span data-stu-id="5b92d-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="5b92d-109">如果您在流覽窗格中看不到 [事件]、[重要訊息中心] 或 [搜尋] 等功能，您必須確認您的承租人具有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="5b92d-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="5b92d-110">如需詳細資訊，請參閱[先決條件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="5b92d-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="5b92d-111">Microsoft 365 Defender 事件中不會顯示識別警示的 microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5b92d-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="5b92d-112">如果您已在環境中部署 Microsoft Defender，但在 Microsoft 365 Defender 事件中卻沒有看到用於身分識別警示的 Defender，您必須確定已啟用 Microsoft Cloud App Security 和 Defender for Identity integration。</span><span class="sxs-lookup"><span data-stu-id="5b92d-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="5b92d-113">如需詳細資訊，請參閱 [Microsoft Defender For Identity integration](/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="5b92d-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="5b92d-114">開啟服務的設定頁面位於何處？</span><span class="sxs-lookup"><span data-stu-id="5b92d-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="5b92d-115">若要開啟 Microsoft 365 Defender，請從 Microsoft 365 安全性中心的功能窗格存取 **設定** 。</span><span class="sxs-lookup"><span data-stu-id="5b92d-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="5b92d-116">只有當您具有 [必要許可權和授權](mtp-enable.md#check-license-eligibility-and-required-permissions)時，才會顯示此導覽專案。</span><span class="sxs-lookup"><span data-stu-id="5b92d-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>