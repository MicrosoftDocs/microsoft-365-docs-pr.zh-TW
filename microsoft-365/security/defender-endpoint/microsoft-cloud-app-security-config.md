---
title: 設定 Microsoft Cloud App Security 整合
ms.reviewer: ''
description: 瞭解如何開啟設定，以啟用 Microsoft Defender 與 Microsoft Cloud App Security 的端點整合。
keywords: 雲端，應用程式，安全性，設定，整合，探索，報表
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4f7aca5cb532510d55042c70d04d65f2aa08baa3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844751"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c2d89-104">在 Microsoft Defender for Endpoint 中設定 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c2d89-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c2d89-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c2d89-105">**Applies to:**</span></span>
- [<span data-ttu-id="c2d89-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c2d89-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c2d89-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2d89-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c2d89-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="c2d89-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c2d89-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="c2d89-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="c2d89-110">若要從 Microsoft Defender 受益于 Endpoint cloud 應用程式探索信號，請開啟 Microsoft Cloud App Security 整合。</span><span class="sxs-lookup"><span data-stu-id="c2d89-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="c2d89-111">您可以在執行 Windows 10 的裝置上使用[Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)的 E5 授權，取得此項功能; 版本 1709 (os 組建 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)) ，Windows 10，版本 1803 (os 組建 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)) ，Windows 10，版本 1809 (os 組建17763.379 搭配[KB4489899](https://support.microsoft.com/help/4489899)) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="c2d89-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="c2d89-112">請參閱[microsoft defender for endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration) ，以取得 Microsoft defender for endpoint with Microsoft Cloud App Security 的詳細整合。</span><span class="sxs-lookup"><span data-stu-id="c2d89-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c2d89-113">在 Microsoft Defender for Endpoint 中啟用 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c2d89-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="c2d89-114">在功能窗格中，選取 [**喜好設定**] [  >  **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="c2d89-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="c2d89-115">選取 [ **Microsoft Cloud App Security** ]，然後切換至 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="c2d89-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="c2d89-116">按一下 [ **儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="c2d89-116">Click **Save preferences**.</span></span>

<span data-ttu-id="c2d89-117">一旦啟動，Microsoft Defender for Endpoint 便會立即開始轉寄探索信號給雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="c2d89-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="c2d89-118">查看收集的資料</span><span class="sxs-lookup"><span data-stu-id="c2d89-118">View the data collected</span></span>

<span data-ttu-id="c2d89-119">若要在 microsoft Cloud Apps Security 中查看和存取 microsoft Defender for Endpoint data，請參閱[調查裝置 in 雲端 App 安全性](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="c2d89-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="c2d89-120">如需雲端探索的詳細資訊，請參閱使用已 [探索的應用程式](/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="c2d89-120">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="c2d89-121">如果您有興趣嘗試 Microsoft Cloud App Security，請參閱[Microsoft Cloud App Security 試用版](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。</span><span class="sxs-lookup"><span data-stu-id="c2d89-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="c2d89-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="c2d89-122">Related topic</span></span>
- [<span data-ttu-id="c2d89-123">Microsoft Cloud App Security 整合</span><span class="sxs-lookup"><span data-stu-id="c2d89-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
