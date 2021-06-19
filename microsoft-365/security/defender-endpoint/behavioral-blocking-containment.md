---
title: 行為封鎖和包含專案
description: 深入瞭解 Microsoft Defender for Endpoint 中的行為封鎖和包容功能
keywords: Microsoft Defender for Endpoint，EDR 以封鎖模式，被動模式封鎖
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 98ea631536bbfa9e1858f70ae3a0ea9de8743572
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029774"
---
# <a name="behavioral-blocking-and-containment"></a><span data-ttu-id="5c0b7-104">行為封鎖和包含專案</span><span class="sxs-lookup"><span data-stu-id="5c0b7-104">Behavioral blocking and containment</span></span>

<span data-ttu-id="5c0b7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="5c0b7-105">**Applies to:**</span></span>
- [<span data-ttu-id="5c0b7-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5c0b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5c0b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c0b7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5c0b7-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5c0b7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5c0b7-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="5c0b7-110">概觀</span><span class="sxs-lookup"><span data-stu-id="5c0b7-110">Overview</span></span>

<span data-ttu-id="5c0b7-111">目前的威脅環境會因 [fileless 惡意](/windows/security/threat-protection/intelligence/fileless-threats) 代碼而溢出，但離土地的高多態威脅，隨著傳統解決方案的變化速度，可持續保持和人工運作的攻擊，以適應敵人在受損的裝置上找到的內容。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-111">Today's threat landscape is overrun by [fileless malware](/windows/security/threat-protection/intelligence/fileless-threats) and that lives off the land, highly polymorphic threats that mutate faster than traditional solutions can keep up with, and human-operated attacks that adapt to what adversaries find on compromised devices.</span></span> <span data-ttu-id="5c0b7-112">傳統的安全性解決方案不足以停止這類攻擊;您需要 (AI) 和裝置學習 (ML) 備份的功能（例如行為封鎖及包容）包含在[Defender for Endpoint](/windows/security)中。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-112">Traditional security solutions are not sufficient to stop such attacks; you need artificial intelligence (AI) and device learning (ML) backed capabilities, such as behavioral blocking and containment, included in [Defender for Endpoint](/windows/security).</span></span>

<span data-ttu-id="5c0b7-113">行為封鎖和包容功能可在威脅已開始執行時，根據其行為和程式樹，協助識別及停止威脅。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-113">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> <span data-ttu-id="5c0b7-114">下一代保護、EDR 和 Defender 用於端點元件和功能，可搭配行為封鎖和包容功能一起運作。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-114">Next-generation protection, EDR, and Defender for Endpoint components and features work together in behavioral blocking and containment capabilities.</span></span>

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="行為封鎖和包含專案":::

<span data-ttu-id="5c0b7-116">行為封鎖和包容功能可與使用的 Defender 的多個元件和功能搭配使用，以立即停止攻擊，並防止攻擊的進展。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-116">Behavioral blocking and containment capabilities work with multiple components and features of Defender for Endpoint to stop attacks immediately and prevent attacks from progressing.</span></span>

- <span data-ttu-id="5c0b7-117">[下一代保護](microsoft-defender-antivirus-in-windows-10.md) (包括 Microsoft Defender 防毒軟體) 可透過分析行為來偵測威脅，以及停止已開始執行的威脅。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-117">[Next-generation protection](microsoft-defender-antivirus-in-windows-10.md) (which includes Microsoft Defender Antivirus) can detect threats by analyzing behaviors, and stop threats that have started running.</span></span>

- <span data-ttu-id="5c0b7-118">[端點偵測和回應](overview-endpoint-detection-response.md) (EDR) 接收網路、裝置和內核行為間的安全性信號。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-118">[Endpoint detection and response](overview-endpoint-detection-response.md) (EDR) receives security signals across your network, devices, and kernel behavior.</span></span> <span data-ttu-id="5c0b7-119">當偵測到威脅時，即會建立警示。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-119">As threats are detected, alerts are created.</span></span> <span data-ttu-id="5c0b7-120">相同類型的多個警示會匯總到事件中，這可讓安全性作業小組更輕鬆地調查和回應。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-120">Multiple alerts of the same type are aggregated into incidents, which makes it easier for your security operations team to investigate and respond.</span></span>

- <span data-ttu-id="5c0b7-121">除了透過 EDR 所收到的網路、端點和內核行為信號之外，該[端點的 Defender](overview-endpoint-detection-response.md)都具有各種身分識別、電子郵件、資料和應用程式的光纖。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-121">[Defender for Endpoint](overview-endpoint-detection-response.md) has a wide range of optics across identities, email, data, and apps, in addition to the network, endpoint, and kernel behavior signals received through EDR.</span></span> <span data-ttu-id="5c0b7-122">[Microsoft 365 Defender](../defender/microsoft-365-defender.md)的元件、端點程式的 Defender 處理常式及相關聯的信號、引發偵測警示，以及連接事件中的相關警示。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-122">A component of [Microsoft 365 Defender](../defender/microsoft-365-defender.md), Defender for Endpoint processes and correlates these signals, raises detection alerts, and connects related alerts in incidents.</span></span>

<span data-ttu-id="5c0b7-123">使用這些功能時，即使已開始執行，也可以阻止或封鎖更多威脅。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-123">With these capabilities, more threats can be prevented or blocked, even if they start running.</span></span> <span data-ttu-id="5c0b7-124">每當偵測到可疑行為時，就會包含威脅、建立警示，並在其蹤跡中停止威脅。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-124">Whenever suspicious behavior is detected, the threat is contained, alerts are created, and threats are stopped in their tracks.</span></span>

<span data-ttu-id="5c0b7-125">下圖顯示由行為封鎖及包容功能所觸發之警示的範例：</span><span class="sxs-lookup"><span data-stu-id="5c0b7-125">The following image shows an example of an alert that was triggered by behavioral blocking and containment capabilities:</span></span>

:::image type="content" source="images/blocked-behav-alert.png" alt-text="透過行為封鎖和包含的警示範例":::

## <a name="components-of-behavioral-blocking-and-containment"></a><span data-ttu-id="5c0b7-127">行為封鎖及包容元件</span><span class="sxs-lookup"><span data-stu-id="5c0b7-127">Components of behavioral blocking and containment</span></span>

- <span data-ttu-id="5c0b7-128">**用戶端、原則導向的 [攻擊面降低規則](attack-surface-reduction.md)** 預先定義的常見攻擊行為會因攻擊面減少規則而無法執行。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-128">**On-client, policy-driven [attack surface reduction rules](attack-surface-reduction.md)** Predefined common attack behaviors are prevented from executing, according to your attack surface reduction rules.</span></span> <span data-ttu-id="5c0b7-129">當這類行為企圖執行時，可以在 Microsoft 365 Defender 中看到這些行為 <https://security.microsoft.com> 以資訊性警示。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-129">When such behaviors attempt to execute, they can be seen in Microsoft 365 Defender <https://security.microsoft.com> as informational alerts.</span></span> <span data-ttu-id="5c0b7-130">預設不會啟用攻擊面減少規則;您可以在[Microsoft 365 Defender](microsoft-defender-security-center.md)中設定您的原則。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-130">Attack surface reduction rules are not enabled by default; you configure your policies in the [Microsoft 365 Defender](microsoft-defender-security-center.md).</span></span>

- <span data-ttu-id="5c0b7-131">**[用戶端行為封鎖](client-behavioral-blocking.md)** 會透過機器學習來偵測端點的威脅，然後自動封鎖並修正。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-131">**[Client behavioral blocking](client-behavioral-blocking.md)** Threats on endpoints are detected through machine learning, and then are blocked and remediated automatically.</span></span> <span data-ttu-id="5c0b7-132">預設會啟用用戶端行為封鎖 (。 ) </span><span class="sxs-lookup"><span data-stu-id="5c0b7-132">(Client behavioral blocking is enabled by default.)</span></span>

- <span data-ttu-id="5c0b7-133">反應反應 **[-環路封鎖](feedback-loop-blocking.md)** (也稱為快速防護) 威脅偵測透過行為情報加以觀察。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-133">**[Feedback-loop blocking](feedback-loop-blocking.md)** (also referred to as rapid protection) Threat detections are observed through behavioral intelligence.</span></span> <span data-ttu-id="5c0b7-134">威脅已停止，無法在其他端點上執行。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-134">Threats are stopped and prevented from running on other endpoints.</span></span> <span data-ttu-id="5c0b7-135"> (反應-迴圈封鎖預設為啟用。 ) </span><span class="sxs-lookup"><span data-stu-id="5c0b7-135">(Feedback-loop blocking is enabled by default.)</span></span>

- <span data-ttu-id="5c0b7-136">**[在封鎖模式中) 的端點偵測和回應 (EDR](edr-in-block-mode.md)** 會封鎖並包含透過破壞性保護所觀測到的惡意專案或行為。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-136">**[Endpoint detection and response (EDR) in block mode](edr-in-block-mode.md)** Malicious artifacts or behaviors that are observed through post-breach protection are blocked and contained.</span></span> <span data-ttu-id="5c0b7-137">即使 Microsoft Defender 防毒軟體不是主要的防病毒解決方案，封鎖模式中的 EDR 仍可運作。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-137">EDR in block mode works even if Microsoft Defender Antivirus is not the primary antivirus solution.</span></span> <span data-ttu-id="5c0b7-138">預設不會啟用封鎖模式中的 (EDR;在 Microsoft 365 Defender 中將其開啟。 ) </span><span class="sxs-lookup"><span data-stu-id="5c0b7-138">(EDR in block mode is not enabled by default; you turn it on in Microsoft 365 Defender.)</span></span>

<span data-ttu-id="5c0b7-139">預期會有更多的行為封鎖和包容領域，因為 Microsoft 會繼續改進威脅防護的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-139">Expect more to come in the area of behavioral blocking and containment, as Microsoft continues to improve threat protection features and capabilities.</span></span> <span data-ttu-id="5c0b7-140">若要查看現在已計畫及推出的專案，請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-140">To see what's planned and rolling out now, visit the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a><span data-ttu-id="5c0b7-141">動作中的行為封鎖及包容範例</span><span class="sxs-lookup"><span data-stu-id="5c0b7-141">Examples of behavioral blocking and containment in action</span></span>

<span data-ttu-id="5c0b7-142">行為封鎖和包容功能已封鎖攻擊者的技術，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5c0b7-142">Behavioral blocking and containment capabilities have blocked attacker techniques such as the following:</span></span>

- <span data-ttu-id="5c0b7-143">從 LSASS 轉儲憑證</span><span class="sxs-lookup"><span data-stu-id="5c0b7-143">Credential dumping from LSASS</span></span>
- <span data-ttu-id="5c0b7-144">跨進程注入</span><span class="sxs-lookup"><span data-stu-id="5c0b7-144">Cross-process injection</span></span>
- <span data-ttu-id="5c0b7-145">處理 hollowing</span><span class="sxs-lookup"><span data-stu-id="5c0b7-145">Process hollowing</span></span>
- <span data-ttu-id="5c0b7-146">使用者帳戶控制旁路</span><span class="sxs-lookup"><span data-stu-id="5c0b7-146">User Account Control bypass</span></span>
- <span data-ttu-id="5c0b7-147">篡改防病毒 (，例如停用它或將惡意程式碼新增為排除) </span><span class="sxs-lookup"><span data-stu-id="5c0b7-147">Tampering with antivirus (such as disabling it or adding the malware as exclusion)</span></span>
- <span data-ttu-id="5c0b7-148">聯繫我們命令和控制項 (C&C) 下載有效載荷</span><span class="sxs-lookup"><span data-stu-id="5c0b7-148">Contacting Command and Control (C&C) to download payloads</span></span>
- <span data-ttu-id="5c0b7-149">硬幣挖掘</span><span class="sxs-lookup"><span data-stu-id="5c0b7-149">Coin mining</span></span>
- <span data-ttu-id="5c0b7-150">修改開機記錄</span><span class="sxs-lookup"><span data-stu-id="5c0b7-150">Boot record modification</span></span>
- <span data-ttu-id="5c0b7-151">傳遞-雜湊攻擊</span><span class="sxs-lookup"><span data-stu-id="5c0b7-151">Pass-the-hash attacks</span></span>
- <span data-ttu-id="5c0b7-152">安裝根憑證</span><span class="sxs-lookup"><span data-stu-id="5c0b7-152">Installation of root certificate</span></span>
- <span data-ttu-id="5c0b7-153">各種漏洞的攻擊嘗試</span><span class="sxs-lookup"><span data-stu-id="5c0b7-153">Exploitation attempt for various vulnerabilities</span></span>

<span data-ttu-id="5c0b7-154">以下是兩個實際行為封鎖和包含在動作中的範例。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-154">Below are two real-life examples of behavioral blocking and containment in action.</span></span>

### <a name="example-1-credential-theft-attack-against-100-organizations"></a><span data-ttu-id="5c0b7-155">範例1：針對100組織的認證盜竊攻擊</span><span class="sxs-lookup"><span data-stu-id="5c0b7-155">Example 1: Credential theft attack against 100 organizations</span></span>

<span data-ttu-id="5c0b7-156">如 [elusive 威脅的熱實施中所述：以 AI 為導向的行為基礎的封鎖會在其追蹤中停止攻擊](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)。由於行為封鎖及包容能力，對全球各地的100組織所進行的認證盜竊攻擊已停止。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-156">As described in [In hot pursuit of elusive threats: AI-driven behavior-based blocking stops attacks in their tracks](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks), a credential theft attack against 100 organizations around the world was stopped by behavioral blocking and containment capabilities.</span></span> <span data-ttu-id="5c0b7-157">Spear-包含引誘檔的網路釣魚電子郵件會傳送給目標群組織。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-157">Spear-phishing email messages that contained a lure document were sent to the targeted organizations.</span></span> <span data-ttu-id="5c0b7-158">如果收件者開啟附件，則相關的遠端檔能夠在使用者的裝置上執行程式碼，並載入 Lokibot 惡意程式碼，這會 stole 認證、挾帶竊取的資料，並等候來自命令和控制伺服器的進一步指示。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-158">If a recipient opened the attachment, a related remote document was able to execute code on the user's device and load Lokibot malware, which stole credentials, exfiltrated stolen data, and waited for further instructions from a command-and-control server.</span></span>

<span data-ttu-id="5c0b7-159">Defender for Endpoint 中的行為基礎裝置教學模型，在攻擊鏈中的兩個點上捕捉及停止攻擊者的技術：</span><span class="sxs-lookup"><span data-stu-id="5c0b7-159">Behavior-based device learning models in Defender for Endpoint caught and stopped the attacker's techniques at two points in the attack chain:</span></span>

- <span data-ttu-id="5c0b7-160">第一個保護層偵測到利用行為行為。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-160">The first protection layer detected the exploit behavior.</span></span> <span data-ttu-id="5c0b7-161">雲端中的裝置學習分類器已正確識別威脅，並立即指示用戶端裝置封鎖攻擊。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-161">Device learning classifiers in the cloud correctly identified the threat as and immediately instructed the client device to block the attack.</span></span>
- <span data-ttu-id="5c0b7-162">第二個保護層，可協助停止攻擊超過第一層的情況、偵測到的處理常式 hollowing、停止該處理常式，並移除對應的檔案 (例如 Lokibot) 。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-162">The second protection layer, which helped stop cases where the attack got past the first layer, detected process hollowing, stopped that process, and removed the corresponding files (such as Lokibot).</span></span>

<span data-ttu-id="5c0b7-163">在偵測和停止攻擊時，系統會觸發及顯示[Microsoft 365 Defender 入口網站](microsoft-defender-security-center.md)中的警示（如「初始存取警示」） (先前 Microsoft Defender 資訊安全中心) ：</span><span class="sxs-lookup"><span data-stu-id="5c0b7-163">While the attack was detected and stopped, alerts, such as an "initial access alert," were triggered and appeared in the [Microsoft 365 Defender portal](microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center):</span></span>

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Microsoft 365 Defender 入口網站中的初始存取警示":::

<span data-ttu-id="5c0b7-165">此範例會顯示雲端中的行為基礎裝置教學模型如何在攻擊開始執行之後，新增防護的新層。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-165">This example shows how behavior-based device learning models in the cloud add new layers of protection against attacks, even after they have started running.</span></span>

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a><span data-ttu-id="5c0b7-166">範例2： NTLM 轉送 Juicy 薯片惡意程式碼變種</span><span class="sxs-lookup"><span data-stu-id="5c0b7-166">Example 2: NTLM relay - Juicy Potato malware variant</span></span>

<span data-ttu-id="5c0b7-167">如近期的博客文章中所述， [行為封鎖和包容：將光學器件轉換成保護](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)，在2020年1月，該端點的 Defender 已偵測到組織中裝置上的許可權提升活動。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-167">As described in the recent blog post, [Behavioral blocking and containment: Transforming optics into protection](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection), in January 2020, Defender for Endpoint detected a privilege escalation activity on a device in an organization.</span></span> <span data-ttu-id="5c0b7-168">觸發稱為「使用 NTLM 轉送可能的許可權提升」的警示。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-168">An alert called "Possible privilege escalation using NTLM relay" was triggered.</span></span>

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="Juicy 薯片惡意程式碼的 NTLM 警示":::

<span data-ttu-id="5c0b7-170">威脅已變成惡意程式碼;它是一種稱為「Juicy 薯片」之 notorious 駭客工具的新功能之前的變種，它是被攻擊者在裝置上取得許可權提升所用的。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-170">The threat turned out to be malware; it was a new, not-seen-before variant of a notorious hacking tool called Juicy Potato, which is used by attackers to get privilege escalation on a device.</span></span>

<span data-ttu-id="5c0b7-171">觸發警示之後的分鐘數，會分析檔案，並確認是否有惡意。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-171">Minutes after the alert was triggered, the file was analyzed, and confirmed to be malicious.</span></span> <span data-ttu-id="5c0b7-172">其進程已停止並封鎖，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="5c0b7-172">Its process was stopped and blocked, as shown in the following image:</span></span>

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="封鎖專案":::

<span data-ttu-id="5c0b7-174">在專案遭到封鎖之後的幾分鐘內，相同檔案的多個實例會在相同的裝置上封鎖，以防其他攻擊者或其他惡意程式碼無法在裝置上部署。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-174">A few minutes after the artifact was blocked, multiple instances of the same file were blocked on the same device, preventing additional attackers or other malware from deploying on the device.</span></span>

<span data-ttu-id="5c0b7-175">本範例顯示使用行為封鎖和包容功能，會自動偵測、包含並封鎖威脅。</span><span class="sxs-lookup"><span data-stu-id="5c0b7-175">This example shows that with behavioral blocking and containment capabilities, threats are detected, contained, and blocked automatically.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c0b7-176">後續步驟</span><span class="sxs-lookup"><span data-stu-id="5c0b7-176">Next steps</span></span>

- [<span data-ttu-id="5c0b7-177">深入瞭解端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="5c0b7-177">Learn more about Defender for Endpoint</span></span>](overview-endpoint-detection-response.md)

- [<span data-ttu-id="5c0b7-178">設定攻擊面減少規則</span><span class="sxs-lookup"><span data-stu-id="5c0b7-178">Configure your attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="5c0b7-179">在封鎖模式中啟用 EDR</span><span class="sxs-lookup"><span data-stu-id="5c0b7-179">Enable EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="5c0b7-180">查看最近的全域威脅活動</span><span class="sxs-lookup"><span data-stu-id="5c0b7-180">See recent global threat activity</span></span>](https://www.microsoft.com/wdsi/threats)

- [<span data-ttu-id="5c0b7-181">深入瞭解 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c0b7-181">Get an overview of Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)
