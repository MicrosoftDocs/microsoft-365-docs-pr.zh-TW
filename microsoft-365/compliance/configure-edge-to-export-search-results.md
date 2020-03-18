---
title: 在 Microsoft Edge 中使用 Office 365 eDiscovery 匯出工具
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
ms.openlocfilehash: 80924b124521b24ffabf1e0273802265cd715500
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710342"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="37dcc-103">在 Microsoft Edge 中使用 Office 365 eDiscovery 匯出工具</span><span class="sxs-lookup"><span data-stu-id="37dcc-103">Use the Office 365 eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="37dcc-104">由於最近的 Microsoft Edge 版本變更，因此預設不再啟用 ClickOnce 支援。</span><span class="sxs-lookup"><span data-stu-id="37dcc-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="37dcc-105">若要繼續使用 Microsoft Office 365 eDiscovery 匯出工具下載內容搜尋或 eDiscovery 搜尋結果，您需要使用[Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads)或在最新版的 microsoft Edge 中啟用 ClickOnce 支援。</span><span class="sxs-lookup"><span data-stu-id="37dcc-105">To continue using the Microsoft Office 365 eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="37dcc-106">在 Microsoft Edge 中啟用 ClickOnce 支援</span><span class="sxs-lookup"><span data-stu-id="37dcc-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="37dcc-107">在 Microsoft Edge 中，移至**edge://flags/#edge-按一下一次**。</span><span class="sxs-lookup"><span data-stu-id="37dcc-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="37dcc-108">在下拉式清單中，如果現有的值設為**Default**或**Disabled** ，請將其變更為**Enabled**。</span><span class="sxs-lookup"><span data-stu-id="37dcc-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![](../media/ClickOnceimage1.png)

3. <span data-ttu-id="37dcc-109">向下滾動至瀏覽器視窗底部，然後按一下 [**重新開機**] 重新開機 Edge。</span><span class="sxs-lookup"><span data-stu-id="37dcc-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](../media/ClickOnceimage2.png)

<span data-ttu-id="37dcc-110">**附注：** 組織可以使用「群組原則」來停用 ClickOnce 支援。</span><span class="sxs-lookup"><span data-stu-id="37dcc-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="37dcc-111">若要檢查是否有 ClickOnce 支援的組織原則，請移至**edge://policy**。</span><span class="sxs-lookup"><span data-stu-id="37dcc-111">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="37dcc-112">下列螢幕擷取畫面顯示整個組織內啟用 ClickOnce。</span><span class="sxs-lookup"><span data-stu-id="37dcc-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="37dcc-113">如果此原則值設定為**false**，您將需要與組織中的系統管理員聯繫。</span><span class="sxs-lookup"><span data-stu-id="37dcc-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="37dcc-114">安裝並執行 eDiscovery 匯出工具</span><span class="sxs-lookup"><span data-stu-id="37dcc-114">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="37dcc-115">在 [內容搜尋] 或 [eDiscovery 案例] 中，按一下 [匯出] 之飛入頁面上的 [**下載結果**]。</span><span class="sxs-lookup"><span data-stu-id="37dcc-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![按一下彈出頁面上的 [下載結果] 以下載搜尋結果](../media/ClickOnceExport1.png)

2. <span data-ttu-id="37dcc-117">系統會提示您確認啟動工具，請按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="37dcc-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![按一下 [開啟] 以啟動 eDiscovery 匯出工具](../media/ClickOnceimage4.png)

   <span data-ttu-id="37dcc-119">如果未安裝 Microsoft Office 365 eDiscovery 匯出工具，系統會提示您顯示安全性警告。</span><span class="sxs-lookup"><span data-stu-id="37dcc-119">If the Microsoft Office 365 eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![按一下 [安裝] 以安裝 eDiscovery 匯出工具](../media/ClickOnceimage5.png)

3. <span data-ttu-id="37dcc-121">按一下 [安裝]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="37dcc-121">Click **Install**.</span></span> <span data-ttu-id="37dcc-122">安裝完畢後，會自動啟動 [匯出工具]。</span><span class="sxs-lookup"><span data-stu-id="37dcc-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="37dcc-123">如需詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="37dcc-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="37dcc-124">匯出內容搜尋結果</span><span class="sxs-lookup"><span data-stu-id="37dcc-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="37dcc-125">如何在 Microsoft Edge 中啟用實驗旗標</span><span class="sxs-lookup"><span data-stu-id="37dcc-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
