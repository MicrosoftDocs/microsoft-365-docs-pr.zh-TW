---
title: 驗證資料儲存位置和更新資料保留設定
description: 確認 Microsoft Defender for Endpoint 的資料儲存位置和更新資料保留設定
keywords: 資料、儲存、設定、保留、更新
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: eb9e4b905112d3d144b10d68418695df3cda29cb
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339247"
---
# <a name="verify-data-storage-location-and-update-data-retention-settings-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="1e4fb-104">確認 Microsoft Defender for Endpoint 的資料儲存位置和更新資料保留設定</span><span class="sxs-lookup"><span data-stu-id="1e4fb-104">Verify data storage location and update data retention settings for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1e4fb-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1e4fb-105">**Applies to:**</span></span>
- [<span data-ttu-id="1e4fb-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1e4fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1e4fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e4fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="1e4fb-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1e4fb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1e4fb-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1e4fb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-gensettings-abovefoldlink)

<span data-ttu-id="1e4fb-110">在上架過程中，嚮導會帶您透過 Defender for Endpoint 的資料儲存區和保留設定。</span><span class="sxs-lookup"><span data-stu-id="1e4fb-110">During the onboarding process, a wizard takes you through the data storage and retention settings of Defender for Endpoint.</span></span> 

<span data-ttu-id="1e4fb-111">完成上架後，您可以在 [資料保留設定] 頁面中驗證您的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="1e4fb-111">After completing the onboarding, you can verify your selection in the data retention settings page.</span></span>

## <a name="verify-data-storage-location"></a><span data-ttu-id="1e4fb-112">驗證資料儲存位置</span><span class="sxs-lookup"><span data-stu-id="1e4fb-112">Verify data storage location</span></span>
<span data-ttu-id="1e4fb-113">在 [設定階段](production-deployment.md)內，您會選取要儲存資料的位置。</span><span class="sxs-lookup"><span data-stu-id="1e4fb-113">During the [Set up phase](production-deployment.md), you would have selected the location to store your data.</span></span> 

<span data-ttu-id="1e4fb-114">您可以流覽至 **設定**  >  **端點**  >  **資料保留**，以確認資料位置。</span><span class="sxs-lookup"><span data-stu-id="1e4fb-114">You can verify the data location by navigating to **Settings** > **Endpoints** > **Data retention**.</span></span>

## <a name="update-data-retention-settings"></a><span data-ttu-id="1e4fb-115">更新資料保留設定</span><span class="sxs-lookup"><span data-stu-id="1e4fb-115">Update data retention settings</span></span>

<span data-ttu-id="1e4fb-116">您可以更新資料保留設定。</span><span class="sxs-lookup"><span data-stu-id="1e4fb-116">You can update the data retention settings.</span></span> <span data-ttu-id="1e4fb-117">依預設，保留期間是180天。</span><span class="sxs-lookup"><span data-stu-id="1e4fb-117">By default, the retention period is 180 days.</span></span> 

1. <span data-ttu-id="1e4fb-118">在功能窗格中，選取 [**設定**  >  **端點**  >  **資料保留**]。</span><span class="sxs-lookup"><span data-stu-id="1e4fb-118">In the navigation pane, select **Settings** > **Endpoints** > **Data retention**.</span></span>

2. <span data-ttu-id="1e4fb-119">從下拉式清單中選取資料保留期間。</span><span class="sxs-lookup"><span data-stu-id="1e4fb-119">Select the data retention duration from the drop-down list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e4fb-120">其他設定無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="1e4fb-120">Other settings are not editable.</span></span>

3. <span data-ttu-id="1e4fb-121">按一下 [ **儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="1e4fb-121">Click **Save preferences**.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1e4fb-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="1e4fb-122">Related topics</span></span>
- [<span data-ttu-id="1e4fb-123">更新資料保留設定</span><span class="sxs-lookup"><span data-stu-id="1e4fb-123">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="1e4fb-124">在 Defender for Endpoint 中設定警示通知</span><span class="sxs-lookup"><span data-stu-id="1e4fb-124">Configure alert notifications in Defender for Endpoint</span></span>](configure-email-notifications.md)
- [<span data-ttu-id="1e4fb-125">設定進階功能</span><span class="sxs-lookup"><span data-stu-id="1e4fb-125">Configure advanced features</span></span>](advanced-features.md)
