---
title: 在 Microsoft Edge 中使用 Office 365 電子文件探索匯出工具
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 您必須啟用 ClickOnce 支援，以使用 Microsoft Edge 從內容搜尋和 eDiscovery 的安全性與合規性中心匯出搜尋結果。
ms.openlocfilehash: db70b4cdbc57f519db3b6b962eb8aa43585ba335
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078556"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="48d9b-103">在 Microsoft Edge 中使用 Office 365 電子文件探索匯出工具</span><span class="sxs-lookup"><span data-stu-id="48d9b-103">Use the Office 365 eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="48d9b-104">由於 Microsoft edge 的最新變更，依預設不會再啟用 ClickOnce 支援方法。</span><span class="sxs-lookup"><span data-stu-id="48d9b-104">As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="48d9b-105">若要繼續使用 Microsoft Office 365 電子文件探索匯出工具來下載內容搜尋] 或 [eDiscovery 搜尋結果，您需要使用[Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads)或啟用 ClickOnce 支援 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="48d9b-105">To continue using the Microsoft Office 365 eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in Microsoft Edge.</span></span>

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="48d9b-106">如何啟用 ClickOnce 支援 Microsoft Edge 中</span><span class="sxs-lookup"><span data-stu-id="48d9b-106">How to enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="48d9b-107">在 Microsoft Edge、 瀏覽至**edge://flags/#edge-click-once**。</span><span class="sxs-lookup"><span data-stu-id="48d9b-107">In Microsoft Edge, navigate to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="48d9b-108">如果現有的值設為**預設值**] 或 [**已停用**在下拉式清單中，則會變更為 [**已啟用**。</span><span class="sxs-lookup"><span data-stu-id="48d9b-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>
    
   ![](../media/ClickOnceimage1.png)

3. <span data-ttu-id="48d9b-109">捲動至底部的瀏覽器視窗，然後按一下 [重新啟動 Edge 的 [**重新啟動**。</span><span class="sxs-lookup"><span data-stu-id="48d9b-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](../media/ClickOnceimage2.png)

<span data-ttu-id="48d9b-110">**附註：** 組織可以使用群組原則停用 ClickOnce 支援。</span><span class="sxs-lookup"><span data-stu-id="48d9b-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="48d9b-111">若要檢查是否有 ClickOnce 支援的組織原則，請瀏覽至 [ **edge://policy**。</span><span class="sxs-lookup"><span data-stu-id="48d9b-111">To check if there is an organizational policy for ClickOnce support, navigate to **edge://policy**.</span></span> <span data-ttu-id="48d9b-112">下列螢幕擷取畫面顯示 ClickOnce 已啟用整個組織。</span><span class="sxs-lookup"><span data-stu-id="48d9b-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="48d9b-113">如果此原則值設為**false**，您必須連絡貴組織中的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="48d9b-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a><span data-ttu-id="48d9b-114">安裝和執行 Office 365 電子文件探索匯出工具</span><span class="sxs-lookup"><span data-stu-id="48d9b-114">Install and run the Office 365 eDiscovery Export Tool</span></span>

1. <span data-ttu-id="48d9b-115">在匯出內容搜尋] 或 [eDiscovery 案例中的彈出式頁面上，按一下 [**下載結果**。</span><span class="sxs-lookup"><span data-stu-id="48d9b-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![按一下 [下載結果在彈出式視窗] 頁面上，若要下載搜尋結果](../media/ClickOnceExport1.png)

2. <span data-ttu-id="48d9b-117">您將會出現確認提示來啟動工具，請按一下 [**開啟**。</span><span class="sxs-lookup"><span data-stu-id="48d9b-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![按一下 [開啟] 以啟動 eDiscovery 匯出工具](../media/ClickOnceimage4.png)

   <span data-ttu-id="48d9b-119">如果未安裝 Microsoft Office 365 電子文件探索匯出工具，將會提示您安全性警告，</span><span class="sxs-lookup"><span data-stu-id="48d9b-119">If the Microsoft Office 365 eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![按一下 [安裝] 來安裝 eDiscovery 匯出工具](../media/ClickOnceimage5.png)

3. <span data-ttu-id="48d9b-121">按一下 [安裝]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="48d9b-121">Click **Install**.</span></span> <span data-ttu-id="48d9b-122">安裝之後，匯出工具會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="48d9b-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="48d9b-123">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="48d9b-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="48d9b-124">匯出內容搜尋結果</span><span class="sxs-lookup"><span data-stu-id="48d9b-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="48d9b-125">如何啟用 Microsoft Edge 中的實驗旗標</span><span class="sxs-lookup"><span data-stu-id="48d9b-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
