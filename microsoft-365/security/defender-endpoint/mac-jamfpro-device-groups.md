---
title: 在 Jamf 中設定裝置群組 Pro
description: 瞭解如何在 Jamf Pro 中為 Microsoft Defender for Endpoint 設定裝置群組 macOS
keywords: device，group，microsoft，defender，Microsoft Defender for Endpoint，mac，安裝，部署，卸載，intune，jamfpro，macos，catalina，mojave，高塞拉里昂
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 772b67ec84ae9614c9322763c140a60e7884644d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933802"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="d3d43-104">在 Jamf 的 macOS 裝置群組上設定 Microsoft Defender for Endpoint Pro</span><span class="sxs-lookup"><span data-stu-id="d3d43-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d3d43-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d3d43-105">**Applies to:**</span></span>
- [<span data-ttu-id="d3d43-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d3d43-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d3d43-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3d43-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d3d43-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d3d43-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d3d43-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d3d43-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="d3d43-110">設定裝置群組，類似于群組原則組織統一 (ou) 、Microsoft Endpoint Configuration Manager 的裝置集合及 Intune 的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="d3d43-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="d3d43-111">流覽至 [ **靜態電腦群組**]。</span><span class="sxs-lookup"><span data-stu-id="d3d43-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="d3d43-112">選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="d3d43-112">Select **New**.</span></span> 

    ![Jamf Pro1 的影像](images/jamf-pro-static-group.png)

3. <span data-ttu-id="d3d43-114">提供顯示名稱，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d3d43-114">Provide a display name and select **Save**.</span></span>

    ![Jamf Pro2 的影像](images/jamfpro-machine-group.png)

4. <span data-ttu-id="d3d43-116">現在，您會在 [**靜態電腦群組**] 底下看到 **Contoso 的電腦群組**。</span><span class="sxs-lookup"><span data-stu-id="d3d43-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Jamf Pro3 的影像](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="d3d43-118">下一步</span><span class="sxs-lookup"><span data-stu-id="d3d43-118">Next step</span></span>
- [<span data-ttu-id="d3d43-119">在 Jamf 的 macOS 原則上設定 Microsoft Defender for Endpoint Pro</span><span class="sxs-lookup"><span data-stu-id="d3d43-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
