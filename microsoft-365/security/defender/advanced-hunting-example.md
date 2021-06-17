---
title: 適用于 Office 365 之 Microsoft Defender 的高級搜尋範例
description: 使用高級搜尋開始搜尋電子郵件威脅
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，自訂偵測，schema，kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965139"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="57f3f-104">適用于 Office 365 之 Microsoft Defender 的高級搜尋範例</span><span class="sxs-lookup"><span data-stu-id="57f3f-104">Advanced hunting example for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="57f3f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="57f3f-105">**Applies to:**</span></span>
- <span data-ttu-id="57f3f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57f3f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="57f3f-107">想要開始使用進階搜捕來搜尋電子郵件威脅嗎？</span><span class="sxs-lookup"><span data-stu-id="57f3f-107">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="57f3f-108">嘗試這樣做：</span><span class="sxs-lookup"><span data-stu-id="57f3f-108">Try this:</span></span>

<span data-ttu-id="57f3f-109">[適用於 Office 365 的 Microsoft Defender 文章](/microsoft-365/security/office-365-security/defender-for-office-365)的[快速入門](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started)小節包含的邏輯早期設定區塊，看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="57f3f-109">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="57f3f-110">使用名稱中的「反」設定所有專案。</span><span class="sxs-lookup"><span data-stu-id="57f3f-110">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="57f3f-111">反惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="57f3f-111">Anti-malware</span></span>
   - <span data-ttu-id="57f3f-112">反網路釣魚</span><span class="sxs-lookup"><span data-stu-id="57f3f-112">Anti-phishing</span></span>
   - <span data-ttu-id="57f3f-113">反垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="57f3f-113">Anti-spam</span></span>
2. <span data-ttu-id="57f3f-114">使用名稱中的 ' Safe ' 設定所有專案。</span><span class="sxs-lookup"><span data-stu-id="57f3f-114">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="57f3f-115">安全連結</span><span class="sxs-lookup"><span data-stu-id="57f3f-115">Safe Links</span></span>
   - <span data-ttu-id="57f3f-116">安全附件</span><span class="sxs-lookup"><span data-stu-id="57f3f-116">Safe Attachments</span></span>
3. <span data-ttu-id="57f3f-117">保護工作負載 (例如:</span><span class="sxs-lookup"><span data-stu-id="57f3f-117">Defend the workloads (ex.</span></span> <span data-ttu-id="57f3f-118">SharePoint線上、OneDrive 和 Teams) 。</span><span class="sxs-lookup"><span data-stu-id="57f3f-118">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="57f3f-119">使用零小時自動清除加以保護。</span><span class="sxs-lookup"><span data-stu-id="57f3f-119">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="57f3f-120">還有可直接進入並在第 1 天便完成設定的[連結](../office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="57f3f-120">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="57f3f-121">**快速入門** 的最後一個步驟會使用 **零時差自動清除** (也稱為 ZAP) 來保護使用者。</span><span class="sxs-lookup"><span data-stu-id="57f3f-121">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="57f3f-122">了解您對可疑或惡意郵件執行的 ZAP 在傳遞後是否成功非常重要。</span><span class="sxs-lookup"><span data-stu-id="57f3f-122">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="57f3f-123">快速瀏覽至 Kusto 查詢語言以搜捕問題，是這兩個安全性中心交集的優點。</span><span class="sxs-lookup"><span data-stu-id="57f3f-123">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="57f3f-124">安全小組 [可以在 [](https://security.microsoft.com/advanced-hunting)**搜尋** \> **高級搜尋**] 底下執行下一個步驟，以監視 ZAP 未命中。</span><span class="sxs-lookup"><span data-stu-id="57f3f-124">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="57f3f-125">在 [高級搜尋] 頁面上，按一下 [ **查詢**]。</span><span class="sxs-lookup"><span data-stu-id="57f3f-125">On the Advanced Hunting page, click **Query**.</span></span>
1. <span data-ttu-id="57f3f-126">將下列查詢複製到查詢視窗。</span><span class="sxs-lookup"><span data-stu-id="57f3f-126">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="57f3f-127">選取 [ **執行查詢**]。</span><span class="sxs-lookup"><span data-stu-id="57f3f-127">Select **Run query**.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="[高級搜尋] 頁面 ([搜尋) 上的 [搜尋] 面板上方已選取 [查詢]，並執行 Kusto 查詢，以在過去7天內捕獲 ZAP 動作。":::

<span data-ttu-id="57f3f-129">來自此查詢的資料會顯示在查詢本身下方的結果面板中。</span><span class="sxs-lookup"><span data-stu-id="57f3f-129">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="57f3f-130">結果包含可自訂的結果集中的資訊，例如 'DeviceName'、'AccountDisplayName' 和 'ZapTime'。</span><span class="sxs-lookup"><span data-stu-id="57f3f-130">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="57f3f-131">也可以匯出結果做為記錄。</span><span class="sxs-lookup"><span data-stu-id="57f3f-131">Results can also be exported for your records.</span></span> <span data-ttu-id="57f3f-132">如果查詢是您所需要的，請再次選取 [儲存 **]**  >  [另存新檔 **]**，並將查詢新增至您的查詢、共用或社群查詢的清單中。</span><span class="sxs-lookup"><span data-stu-id="57f3f-132">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="57f3f-133">相關資訊</span><span class="sxs-lookup"><span data-stu-id="57f3f-133">Related information</span></span>
- [<span data-ttu-id="57f3f-134">高級搜尋最佳作法</span><span class="sxs-lookup"><span data-stu-id="57f3f-134">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="57f3f-135">概覽-高級搜尋</span><span class="sxs-lookup"><span data-stu-id="57f3f-135">Overview - Advanced hunting</span></span>](advanced-hunting-overview.md)
