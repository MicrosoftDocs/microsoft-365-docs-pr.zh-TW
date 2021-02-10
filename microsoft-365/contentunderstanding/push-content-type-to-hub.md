---
title: 將內容類型推入中樞
description: 了解如何將內容類型推入中樞
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 22d146b1d376bab134e82ad7d1313cb7881ca45b
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2021
ms.locfileid: "50144968"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="a0acd-103">將內容類型推入中樞</span><span class="sxs-lookup"><span data-stu-id="a0acd-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="a0acd-104">要使重要內容類型更一致地可用於 SharePoint 庫和清單，可以將它們推入到您選擇的中樞。</span><span class="sxs-lookup"><span data-stu-id="a0acd-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="a0acd-105">內容類型的自動推入功能會將它們新增到在與中樞相關聯的網站上所建立的新清單與文件庫，以及新增到中樞的所有新網站。</span><span class="sxs-lookup"><span data-stu-id="a0acd-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span> <span data-ttu-id="a0acd-106">此功能需要 [SharePoint Syntex](index.md) 授權。</span><span class="sxs-lookup"><span data-stu-id="a0acd-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="a0acd-107">要使此功能正常運作，必須先發行要推入的內容類型。</span><span class="sxs-lookup"><span data-stu-id="a0acd-107">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="a0acd-108">將內容類型推入中樞</span><span class="sxs-lookup"><span data-stu-id="a0acd-108">To push content types to hubs</span></span>

1. <span data-ttu-id="a0acd-109">在 SharePoint 系統管理中心展開 **[內容服務]**，然後選取 **[内容類型庫]**。</span><span class="sxs-lookup"><span data-stu-id="a0acd-109">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="a0acd-110">選取您要推入中樞的內容類型。</span><span class="sxs-lookup"><span data-stu-id="a0acd-110">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="a0acd-111">選取命令列上的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="a0acd-111">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="a0acd-112">選取 **[選擇中樞網站]**。</span><span class="sxs-lookup"><span data-stu-id="a0acd-112">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="a0acd-113">選取您要的中樞網站，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a0acd-113">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="a0acd-114">選擇 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a0acd-114">Choose **Save**.</span></span>

<span data-ttu-id="a0acd-115">當您首次將內容類型推入到現有中樞及其現有相關網站時，從存取中樞或相關網站開始，網站中的設定更新可能需要一個小時的時間。</span><span class="sxs-lookup"><span data-stu-id="a0acd-115">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="a0acd-116">與中樞的任何新關聯都無需如此等待，且會在幾分鐘內就反映設定。</span><span class="sxs-lookup"><span data-stu-id="a0acd-116">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="a0acd-117">設定完成後，具有這些設定的內容類型將在幾分鐘內便可在任何與中樞關聯的新網站中使用。</span><span class="sxs-lookup"><span data-stu-id="a0acd-117">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="a0acd-118">然後，建立的任何新清單或文件庫都將在建立後幾分鐘內自動將內容類型新增至其中。</span><span class="sxs-lookup"><span data-stu-id="a0acd-118">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="a0acd-119">只有當推入內容類型直接或間接從文件內容類型衍生時，才會將其新增至文件庫中；只有當內容類型不是直接或間接衍生自文件內容類型時，才會將其新增至清單中。</span><span class="sxs-lookup"><span data-stu-id="a0acd-119">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0acd-120">請參閱</span><span class="sxs-lookup"><span data-stu-id="a0acd-120">See also</span></span>
