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
ms.collection: enabler-strategic
localization_priority: Priority
ms.openlocfilehash: d64dd5ab49d371df075f1044024c12fbf78e265c
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087604"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="456bc-103">將內容類型推入中樞</span><span class="sxs-lookup"><span data-stu-id="456bc-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="456bc-104">要使重要內容類型更一致地可用於 SharePoint 庫和清單，可以將它們推入到您選擇的中樞。</span><span class="sxs-lookup"><span data-stu-id="456bc-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="456bc-105">這會自動將它們新增到在與中樞相關聯的網站上建立的任何新清單和庫中，以及新增到中樞的任何新網站。</span><span class="sxs-lookup"><span data-stu-id="456bc-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="456bc-106">要使此功能正常運作，必須先發行要推入的內容類型。</span><span class="sxs-lookup"><span data-stu-id="456bc-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="456bc-107">將內容類型推入中樞</span><span class="sxs-lookup"><span data-stu-id="456bc-107">To push content types to hubs</span></span>

1. <span data-ttu-id="456bc-108">在 SharePoint 系統管理中心展開 **[內容服務]**，然後按一下 **[内容類型庫]**。</span><span class="sxs-lookup"><span data-stu-id="456bc-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="456bc-109">按一下要推入中樞的內容類型。</span><span class="sxs-lookup"><span data-stu-id="456bc-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="456bc-110">按一下命令列上的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="456bc-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="456bc-111">按一下 **[選擇中樞網站]**。</span><span class="sxs-lookup"><span data-stu-id="456bc-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="456bc-112">選取所需的中樞網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="456bc-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="456bc-113">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="456bc-113">Click **Save**.</span></span>

<span data-ttu-id="456bc-114">首次將內容類型推入到現有中樞及其現有相關網站時，從訪問中樞或相關網站開始，網站中的設定更新可能需要一個小時的時間。</span><span class="sxs-lookup"><span data-stu-id="456bc-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="456bc-115">與中樞的任何新關聯都無需如此等待，且會在幾分鐘內就反映設定。</span><span class="sxs-lookup"><span data-stu-id="456bc-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="456bc-116">設定完成後，具有這些設定的內容類型將在幾分鐘內在任何與中樞關聯的新網站中可用。</span><span class="sxs-lookup"><span data-stu-id="456bc-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="456bc-117">一旦可用，建立的任何新清單或庫都將在建立後幾分鐘內自動將內容類型新增至其中。</span><span class="sxs-lookup"><span data-stu-id="456bc-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="456bc-118">只有當推入內容類型直接或間接從文件內容類型衍生時，才會將其新增至文件庫中；只有當內容類型不是直接或間接衍生自文件內容類型時，才會將其新增至清單中。</span><span class="sxs-lookup"><span data-stu-id="456bc-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="456bc-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="456bc-119">See also</span></span>



  






