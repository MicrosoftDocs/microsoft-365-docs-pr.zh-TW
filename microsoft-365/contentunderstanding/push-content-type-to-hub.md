---
title: 將內容類型推入 hub
description: 瞭解如何將內容類型推入 hub
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a852207bfd1a2a7643ce8895a533371d194954cf
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295802"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="d6204-103">將內容類型推入 hub</span><span class="sxs-lookup"><span data-stu-id="d6204-103">Push content types to a hub</span></span>

<span data-ttu-id="d6204-104">若要讓重要的內容類型可 SharePoint 文件庫和清單，您可以將它們推入您所選擇的中樞。</span><span class="sxs-lookup"><span data-stu-id="d6204-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="d6204-105">這會自動將其新增至與 hub 相關聯之網站上建立的任何新清單和程式庫，以及加入至 hub 的任何新網站。</span><span class="sxs-lookup"><span data-stu-id="d6204-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="d6204-106">若要讓此功能能夠運作，必須已發佈推入的內容類型。</span><span class="sxs-lookup"><span data-stu-id="d6204-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="d6204-107">將內容類型推入中樞</span><span class="sxs-lookup"><span data-stu-id="d6204-107">To push content types to hubs</span></span>

1. <span data-ttu-id="d6204-108">在 SharePoint 系統管理中心，展開 [ **內容服務**]，然後按一下 [ **內容類型庫**]。</span><span class="sxs-lookup"><span data-stu-id="d6204-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="d6204-109">按一下您要推送至集線器的內容類型。</span><span class="sxs-lookup"><span data-stu-id="d6204-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="d6204-110">按一下命令列中的 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="d6204-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="d6204-111">按一下 **[選擇中心網站**]。</span><span class="sxs-lookup"><span data-stu-id="d6204-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="d6204-112">選取所需的 hub 網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d6204-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="d6204-113">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="d6204-113">Click **Save**.</span></span>

<span data-ttu-id="d6204-114">當您第一次將內容類型推向現有的中樞 & 現有的關聯網站時，最多可能需要一小時的時間，才能從 hub 或關聯的網站進行訪問，以供網站中更新的設定。</span><span class="sxs-lookup"><span data-stu-id="d6204-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="d6204-115">任何新的 hub 關聯都不需要此等待，而且會在幾分鐘內反映設定。</span><span class="sxs-lookup"><span data-stu-id="d6204-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="d6204-116">設定此設定後，具有這些設定的內容類型，將會在幾分鐘內，與 hub 產生任何新近關聯的網站。</span><span class="sxs-lookup"><span data-stu-id="d6204-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="d6204-117">一旦可用，任何已建立的新清單或文件庫將會在建立幾分鐘內自動新增內容類型。</span><span class="sxs-lookup"><span data-stu-id="d6204-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="d6204-118">只有當推入的內容類型直接或間接從檔內容類型派生時，才會將其新增至文件庫，而且只有在它不是直接或間接從檔內容類型派生時，才會將內容類型新增至清單。</span><span class="sxs-lookup"><span data-stu-id="d6204-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6204-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d6204-119">See also</span></span>



  






