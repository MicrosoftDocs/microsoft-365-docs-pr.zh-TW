---
title: 使用 Microsoft Edge 中的 eDiscovery 匯出工具
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
description: 您必須啟用 ClickOnce 支援，才能使用最新版的 Microsoft Edge 從內容搜尋和 eDiscovery 的安全性與合規性中心下載搜尋結果。
ms.openlocfilehash: c48e3fb04747306693364a2cdbc6f18047a0fd9e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632378"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="177d9-103">使用 Microsoft Edge 中的 eDiscovery 匯出工具</span><span class="sxs-lookup"><span data-stu-id="177d9-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="177d9-104">由於最近的 Microsoft Edge 版本變更，因此預設不再啟用 ClickOnce 支援。</span><span class="sxs-lookup"><span data-stu-id="177d9-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="177d9-105">若要繼續使用 eDiscovery 匯出工具下載內容搜尋或 eDiscovery 搜尋結果，您需要使用[Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) ，或在最新版的 microsoft Edge 中啟用 ClickOnce 支援。</span><span class="sxs-lookup"><span data-stu-id="177d9-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="177d9-106">在 Microsoft Edge 中啟用 ClickOnce 支援</span><span class="sxs-lookup"><span data-stu-id="177d9-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="177d9-107">在 Microsoft Edge 中，移至**edge://flags/#edge-按一下一次**。</span><span class="sxs-lookup"><span data-stu-id="177d9-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="177d9-108">在下拉式清單中，如果現有的值設為**Default**或**Disabled** ，請將其變更為**Enabled**。</span><span class="sxs-lookup"><span data-stu-id="177d9-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![](../media/ClickOnceimage1.png)

3. <span data-ttu-id="177d9-109">向下滾動至瀏覽器視窗底部，然後按一下 [**重新開機**] 重新開機 Edge。</span><span class="sxs-lookup"><span data-stu-id="177d9-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](../media/ClickOnceimage2.png)

<span data-ttu-id="177d9-110">**附注：** 組織可以使用「群組原則」來停用 ClickOnce 支援。</span><span class="sxs-lookup"><span data-stu-id="177d9-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="177d9-111">若要檢查是否有 ClickOnce 支援的組織原則，請移至**edge://policy**。</span><span class="sxs-lookup"><span data-stu-id="177d9-111">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="177d9-112">下列螢幕擷取畫面顯示整個組織內啟用 ClickOnce。</span><span class="sxs-lookup"><span data-stu-id="177d9-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="177d9-113">如果此原則值設定為**false**，您將需要與組織中的系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="177d9-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="177d9-114">安裝並執行 eDiscovery 匯出工具</span><span class="sxs-lookup"><span data-stu-id="177d9-114">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="177d9-115">在 [內容搜尋] 或 [eDiscovery 案例] 中，按一下 [匯出] 之飛入頁面上的 [**下載結果**]。</span><span class="sxs-lookup"><span data-stu-id="177d9-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![按一下彈出頁面上的 [下載結果] 以下載搜尋結果](../media/ClickOnceExport1.png)

2. <span data-ttu-id="177d9-117">系統會提示您確認啟動工具，請按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="177d9-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![按一下 [開啟] 以啟動 eDiscovery 匯出工具](../media/ClickOnceimage4.png)

   <span data-ttu-id="177d9-119">若尚未安裝 eDiscovery 匯出工具，系統會提示您顯示安全性警告。</span><span class="sxs-lookup"><span data-stu-id="177d9-119">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![按一下 [安裝] 以安裝 eDiscovery 匯出工具](../media/ClickOnceimage5.png)

3. <span data-ttu-id="177d9-121">按一下 [安裝]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="177d9-121">Click **Install**.</span></span> <span data-ttu-id="177d9-122">安裝完畢後，會自動啟動 [匯出工具]。</span><span class="sxs-lookup"><span data-stu-id="177d9-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="177d9-123">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="177d9-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="177d9-124">匯出內容搜尋結果</span><span class="sxs-lookup"><span data-stu-id="177d9-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="177d9-125">如何在 Microsoft Edge 中啟用實驗旗標</span><span class="sxs-lookup"><span data-stu-id="177d9-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
