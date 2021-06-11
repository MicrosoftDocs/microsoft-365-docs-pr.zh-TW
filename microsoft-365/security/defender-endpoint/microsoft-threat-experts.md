---
title: Microsoft 威脅專家
ms.reviewer: ''
description: Microsoft 威脅專家提供另一層的專業知識以供 Microsoft Defender 用於端點。
keywords: 受管理的威脅搜尋服務、受管理的威脅搜尋、受管理的偵測和回應 (MDR) service、MTE、Microsoft 威脅專家、MTE-TAN、目標攻擊通知、目標攻擊通知
search.product: Windows 10
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 956fb591154df374c8010d875645e1122f3419b2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879237"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="20899-104">Microsoft 威脅專家</span><span class="sxs-lookup"><span data-stu-id="20899-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="20899-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="20899-105">**Applies to:**</span></span>
- [<span data-ttu-id="20899-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="20899-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="20899-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20899-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="20899-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="20899-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="20899-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="20899-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="20899-110">Microsoft 威脅專家是受管理的威脅搜尋服務，可讓您的安全性運作中心 (SOCs) 使用專家級的監控和分析，協助他們確保您獨特環境中的重大威脅不會遭到錯過。</span><span class="sxs-lookup"><span data-stu-id="20899-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="20899-111">此受管理的威脅搜尋服務透過下列兩項功能提供了專家導向的真知灼見和資料：目標攻擊通知，以及對專家的要求。</span><span class="sxs-lookup"><span data-stu-id="20899-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="20899-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="20899-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="20899-113">在您套用至受管理的威脅搜尋服務之前，請與您的 Microsoft 技術服務提供者和客戶小組討論資格需求。</span><span class="sxs-lookup"><span data-stu-id="20899-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="20899-114">如果您是 Microsoft Defender for Endpoint 客戶，您必須針對 **Microsoft 威脅專家目標攻擊通知** 進行套用，以取得特殊的洞察力和分析，以協助識別您環境中最重要的威脅，讓您能快速回應這些威脅。</span><span class="sxs-lookup"><span data-stu-id="20899-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly.</span></span>

<span data-ttu-id="20899-115">若要登記 Microsoft 威脅專家目標攻擊通知權益，請移至 **設定**  >  **端點**  >  **一般**  >  **高級功能**  >  **Microsoft 威脅專家要套用的已設定攻擊通知**。</span><span class="sxs-lookup"><span data-stu-id="20899-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **Endpoints** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="20899-116">一旦接受，您就會獲得目標攻擊通知的優點。</span><span class="sxs-lookup"><span data-stu-id="20899-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="20899-117">請與您的帳戶小組或 Microsoft 代表聯繫，以訂閱 **Microsoft 威脅專家的專家** 針對您的組織所面臨的相關偵測和敵人，向威脅專家請教。</span><span class="sxs-lookup"><span data-stu-id="20899-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="20899-118">如需詳細資訊，請參閱[設定 Microsoft 威脅專家功能](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin)。</span><span class="sxs-lookup"><span data-stu-id="20899-118">See [Configure Microsoft Threat Experts capabilities](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="20899-119">Microsoft 威脅專家目標攻擊通知</span><span class="sxs-lookup"><span data-stu-id="20899-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="20899-120">Microsoft 威脅專家目標攻擊通知可為網路的最重要威脅（包括人敵人入侵、鍵盤攻擊或網路間諜等高級攻擊）提供主動搜尋。</span><span class="sxs-lookup"><span data-stu-id="20899-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="20899-121">這些通知會顯示為新的警示。</span><span class="sxs-lookup"><span data-stu-id="20899-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="20899-122">受管理的搜尋服務包括：</span><span class="sxs-lookup"><span data-stu-id="20899-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="20899-123">威脅監控和分析，縮短工作的停留時間和風險</span><span class="sxs-lookup"><span data-stu-id="20899-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="20899-124">Hunter-訓練有素的人工情報，用以探索已知和未知的攻擊的優先順序</span><span class="sxs-lookup"><span data-stu-id="20899-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="20899-125">找出最重要的風險，協助 SOCs 最大化時間和能量</span><span class="sxs-lookup"><span data-stu-id="20899-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="20899-126">安全的範圍，以及可以快速傳遞以啟用 fast SOC 回應的最大內容。</span><span class="sxs-lookup"><span data-stu-id="20899-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="20899-127">Microsoft 威脅專家-依需求的專家</span><span class="sxs-lookup"><span data-stu-id="20899-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="20899-128">客戶可以直接從 Microsoft Defender 資訊安全中心內與我們的安全性專家互動，以進行及時且準確的回應。</span><span class="sxs-lookup"><span data-stu-id="20899-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="20899-129">專家會提供深入瞭解影響組織之複雜威脅（從警示查詢、可能受損的裝置，以及可疑網路連線的根本原因），以進一步瞭解有關持續性的高級威脅活動的其他威脅情報。</span><span class="sxs-lookup"><span data-stu-id="20899-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="20899-130">使用此功能，您可以：</span><span class="sxs-lookup"><span data-stu-id="20899-130">With this capability, you can:</span></span>
- <span data-ttu-id="20899-131">取得警示的其他說明，包括事件的根本原因或範圍</span><span class="sxs-lookup"><span data-stu-id="20899-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="20899-132">在面臨的可疑裝置行為中取得清晰的行為，以及在面臨高級攻擊者的後續步驟</span><span class="sxs-lookup"><span data-stu-id="20899-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="20899-133">決定威脅演員、活動或新興攻擊者技術的風險和保護</span><span class="sxs-lookup"><span data-stu-id="20899-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="20899-134">「 **威脅專家** 」的選項可在入口網站中的數個地方取得，所以您可以在調查的內容中與專家接洽：</span><span class="sxs-lookup"><span data-stu-id="20899-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="20899-135"><i>**協助和支援功能表**</i></span><span class="sxs-lookup"><span data-stu-id="20899-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="20899-136">![MTE-EOD 功能表選項的螢幕擷取畫面](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="20899-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="20899-137"><i>**裝置頁面動作功能表**</i></span><span class="sxs-lookup"><span data-stu-id="20899-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="20899-138">![MTE-EOD 裝置頁面動作功能表選項的螢幕擷取畫面](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="20899-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="20899-139"><i>**警示頁面動作功能表**</i></span><span class="sxs-lookup"><span data-stu-id="20899-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="20899-140">![MTE-EOD 警示頁面動作功能表選項的螢幕擷取畫面](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="20899-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="20899-141"><i>**檔案頁面動作功能表**</i></span><span class="sxs-lookup"><span data-stu-id="20899-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="20899-142">![MTE-EOD 檔頁面動作功能表選項的螢幕擷取畫面](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="20899-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="20899-143">如果您想要透過 Microsoft Services Hub 追蹤專家對需求案例的狀態，請與您的技術客戶經理聯繫。</span><span class="sxs-lookup"><span data-stu-id="20899-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="20899-144">觀賞這段影片，以快速流覽 Microsoft Services 中樞。</span><span class="sxs-lookup"><span data-stu-id="20899-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="20899-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="20899-145">Related topic</span></span>
- [<span data-ttu-id="20899-146">設定 Microsoft 威脅專家功能</span><span class="sxs-lookup"><span data-stu-id="20899-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)
