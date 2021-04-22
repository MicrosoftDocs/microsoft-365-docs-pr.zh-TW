---
title: 使用自動調查以調查和修正威脅
description: 瞭解 Microsoft Defender for Endpoint 中的自動調查流程。
keywords: 自動化，調查，偵測，Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 5ea869d4016cc794b3046a664c1519f6b3250c67
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933970"
---
# <a name="overview-of-automated-investigations"></a><span data-ttu-id="d17b5-104">自動化調查的概述</span><span class="sxs-lookup"><span data-stu-id="d17b5-104">Overview of automated investigations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d17b5-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d17b5-105">**Applies to:**</span></span>
- [<span data-ttu-id="d17b5-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d17b5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d17b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d17b5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="d17b5-108">想要瞭解其運作方式？</span><span class="sxs-lookup"><span data-stu-id="d17b5-108">Want to see how it works?</span></span> <span data-ttu-id="d17b5-109">觀賞下列影片：</span><span class="sxs-lookup"><span data-stu-id="d17b5-109">Watch the following video:</span></span> <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

<span data-ttu-id="d17b5-110">自動調查中的技術會使用各種檢查演算法，並以安全分析員所使用的程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="d17b5-110">The technology in automated investigation uses various inspection algorithms and is based on processes that are used by security analysts.</span></span> <span data-ttu-id="d17b5-111">AIR 功能的設計目的是要檢查提醒並立即採取行動以解決違規行為。</span><span class="sxs-lookup"><span data-stu-id="d17b5-111">AIR capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="d17b5-112">AIR 功能大幅減少警示數量，讓安全性運作能夠將重點放在更複雜的威脅及其他高價值的計畫上。</span><span class="sxs-lookup"><span data-stu-id="d17b5-112">AIR capabilities significantly reduce alert volume, allowing security operations to focus on more sophisticated threats and other high-value initiatives.</span></span> <span data-ttu-id="d17b5-113">在重要訊息 [中心](auto-investigation-action-center.md)追蹤所有修正動作（不論是擱置或已完成的動作）。</span><span class="sxs-lookup"><span data-stu-id="d17b5-113">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="d17b5-114">在「行動中心」中，待定的動作會獲核准 (或拒絕) ，而且必要時可復原完成的動作。</span><span class="sxs-lookup"><span data-stu-id="d17b5-114">In the Action center, pending actions are approved (or rejected), and completed actions can be undone if needed.</span></span>

<span data-ttu-id="d17b5-115">本文提供 AIR 的概述，並包含後續步驟和其他資源的連結。</span><span class="sxs-lookup"><span data-stu-id="d17b5-115">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="d17b5-116">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="d17b5-116">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="d17b5-117">[註冊免費試用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="d17b5-117">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).</span></span>

## <a name="how-the-automated-investigation-starts"></a><span data-ttu-id="d17b5-118">自動化調查的開始方式</span><span class="sxs-lookup"><span data-stu-id="d17b5-118">How the automated investigation starts</span></span>

<span data-ttu-id="d17b5-119">在觸發警示時，或在安全性操作員開始調查時，就可以開始進行自動調查。</span><span class="sxs-lookup"><span data-stu-id="d17b5-119">An automated investigation can start when an alert is triggered or when a security operator initiates the investigation.</span></span>

|<span data-ttu-id="d17b5-120">情況</span><span class="sxs-lookup"><span data-stu-id="d17b5-120">Situation</span></span>  |<span data-ttu-id="d17b5-121">會發生什麼事</span><span class="sxs-lookup"><span data-stu-id="d17b5-121">What happens</span></span>  |
|---------|---------|
|<span data-ttu-id="d17b5-122">觸發警示</span><span class="sxs-lookup"><span data-stu-id="d17b5-122">An alert is triggered</span></span>     | <span data-ttu-id="d17b5-123">一般來說，當觸發 [警示](review-alerts.md) 時，會自動進行調查，而且會建立 [事件](view-incidents-queue.md) 。</span><span class="sxs-lookup"><span data-stu-id="d17b5-123">In general, an automated investigation starts when an [alert](review-alerts.md) is triggered, and an [incident](view-incidents-queue.md) is created.</span></span> <span data-ttu-id="d17b5-124">例如，假設某個惡意檔案位於裝置上。</span><span class="sxs-lookup"><span data-stu-id="d17b5-124">For example, suppose a malicious file resides on a device.</span></span> <span data-ttu-id="d17b5-125">偵測到該檔案時，會觸發警示，並建立事件。</span><span class="sxs-lookup"><span data-stu-id="d17b5-125">When that file is detected, an alert is triggered, and incident is created.</span></span> <span data-ttu-id="d17b5-126">在裝置上開始自動調查過程。</span><span class="sxs-lookup"><span data-stu-id="d17b5-126">An automated investigation process begins on the device.</span></span> <span data-ttu-id="d17b5-127">因為其他的警示是由於其他裝置上的相同檔案而產生，所以它們會新增至相關聯的事件及自動調查。</span><span class="sxs-lookup"><span data-stu-id="d17b5-127">As other alerts are generated because of the same file on other devices, they are added to the associated incident and to the automated investigation.</span></span>         |
|<span data-ttu-id="d17b5-128">手動開始調查</span><span class="sxs-lookup"><span data-stu-id="d17b5-128">An investigation is started manually</span></span>     | <span data-ttu-id="d17b5-129">您的安全性運作小組可以手動啟動自動調查。</span><span class="sxs-lookup"><span data-stu-id="d17b5-129">An automated investigation can be started manually by your security operations team.</span></span> <span data-ttu-id="d17b5-130">例如，假設安全性操作員正在複查裝置清單，並注意到裝置具有高風險層級。</span><span class="sxs-lookup"><span data-stu-id="d17b5-130">For example, suppose a security operator is reviewing a list of devices and notices that a device has a high risk level.</span></span> <span data-ttu-id="d17b5-131">安全操作員可在清單中選取要開啟其快顯視窗的裝置，然後選取 [ **啟動自動調查**]。</span><span class="sxs-lookup"><span data-stu-id="d17b5-131">The security operator can select the device in the list to open its flyout, and then select **Initiate Automated Investigation**.</span></span> |

## <a name="how-an-automated-investigation-expands-its-scope"></a><span data-ttu-id="d17b5-132">自動化調查如何擴充其範圍</span><span class="sxs-lookup"><span data-stu-id="d17b5-132">How an automated investigation expands its scope</span></span>

<span data-ttu-id="d17b5-133">在執行調查時，系統會將從裝置產生的任何其他警示新增至進行中的自動調查，直到完成調查為止。</span><span class="sxs-lookup"><span data-stu-id="d17b5-133">While an investigation is running, any other alerts generated from the device are added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="d17b5-134">此外，如果在其他裝置上看到相同威脅，就會將這些裝置新增至調查。</span><span class="sxs-lookup"><span data-stu-id="d17b5-134">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>

<span data-ttu-id="d17b5-135">如果在另一個裝置中看到 incriminated 實體，自動化調查程式會將其範圍擴大至包含該裝置，並在該裝置上開始一般的安全性行動手冊。</span><span class="sxs-lookup"><span data-stu-id="d17b5-135">If an incriminated entity is seen in another device, the automated investigation process expands its scope to include that device, and a general security playbook starts on that device.</span></span> <span data-ttu-id="d17b5-136">如果在此擴充程式從相同實體找到10個以上的裝置，則該展開動作需要核准，而且會顯示在 [擱置的 **動作** ] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="d17b5-136">If 10 or more devices are found during this expansion process from the same entity, then that expansion action requires an approval, and is visible on the **Pending actions** tab.</span></span>

## <a name="how-threats-are-remediated"></a><span data-ttu-id="d17b5-137">如何修正威脅</span><span class="sxs-lookup"><span data-stu-id="d17b5-137">How threats are remediated</span></span>

<span data-ttu-id="d17b5-138">在觸發警示時，自動調查執行時，會針對每個證據調查產生一個判定。</span><span class="sxs-lookup"><span data-stu-id="d17b5-138">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="d17b5-139">Verdicts 可以是</span><span class="sxs-lookup"><span data-stu-id="d17b5-139">Verdicts can be</span></span> 
- <span data-ttu-id="d17b5-140">*惡意*;</span><span class="sxs-lookup"><span data-stu-id="d17b5-140">*Malicious*;</span></span>
- <span data-ttu-id="d17b5-141">*可疑*;或</span><span class="sxs-lookup"><span data-stu-id="d17b5-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="d17b5-142">*找不到威脅*。</span><span class="sxs-lookup"><span data-stu-id="d17b5-142">*No threats found*.</span></span> 

<span data-ttu-id="d17b5-143">當達到 verdicts 時，自動調查可能會產生一或多項修復動作。</span><span class="sxs-lookup"><span data-stu-id="d17b5-143">As verdicts are reached, automated investigations can result in one or more remediation actions.</span></span> <span data-ttu-id="d17b5-144">修正動作的範例包括將檔案傳送至隔離區、停止服務、移除排程的任務等等。</span><span class="sxs-lookup"><span data-stu-id="d17b5-144">Examples of remediation actions include sending a file to quarantine, stopping a service, removing a scheduled task, and more.</span></span> <span data-ttu-id="d17b5-145">若要深入瞭解，請參閱 [修復動作](manage-auto-investigation.md#remediation-actions)。</span><span class="sxs-lookup"><span data-stu-id="d17b5-145">To learn more, see [Remediation actions](manage-auto-investigation.md#remediation-actions).</span></span>  

<span data-ttu-id="d17b5-146">根據您組織的 [自動化設定層級](automation-levels.md) 以及其他安全性設定，修正動作可以自動進行，也可以只在安全操作小組核准時進行。</span><span class="sxs-lookup"><span data-stu-id="d17b5-146">Depending on the [level of automation](automation-levels.md) set for your organization, as well as other security settings, remediation actions can occur automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="d17b5-147">其他可影響自動修復的安全性設定包括 [保護可能有害的應用程式](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA) 。</span><span class="sxs-lookup"><span data-stu-id="d17b5-147">Additional security settings that can affect automatic remediation include [protection from potentially unwanted applications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA).</span></span> 

<span data-ttu-id="d17b5-148">在重要訊息 [中心](auto-investigation-action-center.md)追蹤所有修正動作（不論是擱置或已完成的動作）。</span><span class="sxs-lookup"><span data-stu-id="d17b5-148">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="d17b5-149">如有必要，您的安全性作業小組可以復原修正動作。</span><span class="sxs-lookup"><span data-stu-id="d17b5-149">If necessary, your security operations team can undo a remediation action.</span></span> <span data-ttu-id="d17b5-150">若要深入瞭解，請參閱 [在自動調查後複查和核准修正動作](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)。</span><span class="sxs-lookup"><span data-stu-id="d17b5-150">To learn more, see [Review and approve remediation actions following an automated investigation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation).</span></span>

> [!TIP]
> <span data-ttu-id="d17b5-151">請參閱 Microsoft 365 security center 中新的整合調查頁面。</span><span class="sxs-lookup"><span data-stu-id="d17b5-151">Check out the new, unified investigation page in the Microsoft 365 security center.</span></span> <span data-ttu-id="d17b5-152">若要深入瞭解，請參閱 [ (NEW！ ) 整合調查] 頁面](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page)。</span><span class="sxs-lookup"><span data-stu-id="d17b5-152">To learn more, see [(NEW!) Unified investigation page](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span></span>


## <a name="requirements-for-air"></a><span data-ttu-id="d17b5-153">空氣需求</span><span class="sxs-lookup"><span data-stu-id="d17b5-153">Requirements for AIR</span></span>

<span data-ttu-id="d17b5-154">您的組織必須具有 Defender for Endpoint (請參閱 [Microsoft defender For endpoint) 的基本需求](minimum-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="d17b5-154">Your organization must have Defender for Endpoint (see [Minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)).</span></span>

<span data-ttu-id="d17b5-155">目前，AIR 只支援下列作業系統版本：</span><span class="sxs-lookup"><span data-stu-id="d17b5-155">Currently, AIR only supports the following OS versions:</span></span>
- <span data-ttu-id="d17b5-156">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="d17b5-156">Windows Server 2019</span></span>
- <span data-ttu-id="d17b5-157">Windows 10，版本 1709 (OS 組建16299.1085，含 [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="d17b5-157">Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) or later</span></span>
- <span data-ttu-id="d17b5-158">Windows 10，版本 1803 (OS 組建17134.704，含 [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="d17b5-158">Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) or later</span></span>
- <span data-ttu-id="d17b5-159">Windows 10，版本 [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="d17b5-159">Windows 10, version [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) or later</span></span>

## <a name="next-steps"></a><span data-ttu-id="d17b5-160">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d17b5-160">Next steps</span></span>

- [<span data-ttu-id="d17b5-161">深入瞭解自動化層級</span><span class="sxs-lookup"><span data-stu-id="d17b5-161">Learn more about automation levels</span></span>](automation-levels.md)
- [<span data-ttu-id="d17b5-162">請參閱互動式指南：使用 Microsoft Defender for Endpoint 調查和修正威脅</span><span class="sxs-lookup"><span data-stu-id="d17b5-162">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
- [<span data-ttu-id="d17b5-163">在 Microsoft Defender for Endpoint 中設定自動調查和修正功能</span><span class="sxs-lookup"><span data-stu-id="d17b5-163">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>](configure-automated-investigations-remediation.md)

## <a name="see-also"></a><span data-ttu-id="d17b5-164">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d17b5-164">See also</span></span>

- [<span data-ttu-id="d17b5-165">PUA 保護</span><span class="sxs-lookup"><span data-stu-id="d17b5-165">PUA protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="d17b5-166">Microsoft Defender for Office 365 中的自動調查和回應</span><span class="sxs-lookup"><span data-stu-id="d17b5-166">Automated investigation and response in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="d17b5-167">Microsoft 365 Defender 的自動化調查和回應</span><span class="sxs-lookup"><span data-stu-id="d17b5-167">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
