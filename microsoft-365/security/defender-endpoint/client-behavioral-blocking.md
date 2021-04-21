---
title: 用戶端行為封鎖
description: 用戶端行為封鎖是 Microsoft Defender for Endpoint 中行為封鎖和包容功能的一部分
keywords: 行為封鎖，快速保護，用戶端行為，Microsoft Defender ATP，microsoft defender for endpoint
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
ms.openlocfilehash: 48929d0e2b0c932d37cb5d29783712d00b17117f
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904149"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="1e9dc-104">用戶端行為封鎖</span><span class="sxs-lookup"><span data-stu-id="1e9dc-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1e9dc-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1e9dc-105">**Applies to:**</span></span>
- [<span data-ttu-id="1e9dc-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1e9dc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1e9dc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e9dc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1e9dc-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1e9dc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1e9dc-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="1e9dc-110">概觀</span><span class="sxs-lookup"><span data-stu-id="1e9dc-110">Overview</span></span>

<span data-ttu-id="1e9dc-111">用戶端行為封鎖是在 Defender for Endpoint 中的 [行為封鎖和包容功能](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) 的元件。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="1e9dc-112">在裝置上偵測到可疑行為時 (也稱為「用戶端」或「端點」) 時，系統會自動封鎖、檢查和修正偽像 (（如檔案或應用程式) ）。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="雲端和用戶端保護":::

<span data-ttu-id="1e9dc-114">搭配雲端保護時，防防毒保護的運作方式最佳。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="1e9dc-115">用戶端行為封鎖的運作方式</span><span class="sxs-lookup"><span data-stu-id="1e9dc-115">How client behavioral blocking works</span></span>

<span data-ttu-id="1e9dc-116">[Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 可以偵測可疑行為、惡意程式碼、fileless 及記憶體中的攻擊，以及裝置上的其他功能。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="1e9dc-117">偵測到可疑行為時，Microsoft Defender 防毒程式會監視並將這些可疑行為及其程式樹傳送至雲端保護服務。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="1e9dc-118">機器學習會區別惡意應用程式與在毫秒內的良好行為，以及分類每個專案。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="1e9dc-119">在幾乎即時的情況下，只要有惡意的偽像，該專案就會在裝置上遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="1e9dc-120">每當偵測到可疑行為時，就會產生 [警示](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) ，而且會在 Microsoft Defender 安全中心 () 中顯示 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="1e9dc-121">用戶端行為封鎖是有效的，因為它不只是協助防止攻擊的啟動，它可協助停止已開始執行的攻擊。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="1e9dc-122">而且，以反應反應 [封鎖](feedback-loop-blocking.md) (另一個功能封鎖和包含) 的功能，您的組織中的其他裝置都可以攻擊。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="1e9dc-123">以行為為基礎的偵測</span><span class="sxs-lookup"><span data-stu-id="1e9dc-123">Behavior-based detections</span></span>

<span data-ttu-id="1e9dc-124">行為架構的偵測會根據 [MITRE ATT&CK Matrix For Enterprise](https://attack.mitre.org/matrices/enterprise)來命名。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="1e9dc-125">命名慣例有助於識別遭受惡意行為的攻擊階段：</span><span class="sxs-lookup"><span data-stu-id="1e9dc-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="1e9dc-126">策略</span><span class="sxs-lookup"><span data-stu-id="1e9dc-126">Tactic</span></span> |   <span data-ttu-id="1e9dc-127">偵測威脅名稱</span><span class="sxs-lookup"><span data-stu-id="1e9dc-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="1e9dc-128">初始存取</span><span class="sxs-lookup"><span data-stu-id="1e9dc-128">Initial Access</span></span> | <span data-ttu-id="1e9dc-129">行為： Win32/InitialAccess. \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-130">執行</span><span class="sxs-lookup"><span data-stu-id="1e9dc-130">Execution</span></span>  | <span data-ttu-id="1e9dc-131">行為： Win32/執行。 \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-132">堅持</span><span class="sxs-lookup"><span data-stu-id="1e9dc-132">Persistence</span></span>    | <span data-ttu-id="1e9dc-133">行為： Win32/持久化。 \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-134">許可權提升</span><span class="sxs-lookup"><span data-stu-id="1e9dc-134">Privilege Escalation</span></span>   | <span data-ttu-id="1e9dc-135">行為： Win32/PrivilegeEscalation. \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-136">國防規避</span><span class="sxs-lookup"><span data-stu-id="1e9dc-136">Defense Evasion</span></span>    | <span data-ttu-id="1e9dc-137">行為： Win32/DefenseEvasion. \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-138">認證存取</span><span class="sxs-lookup"><span data-stu-id="1e9dc-138">Credential Access</span></span>  | <span data-ttu-id="1e9dc-139">行為： Win32/CredentialAccess. \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-140">發現</span><span class="sxs-lookup"><span data-stu-id="1e9dc-140">Discovery</span></span>  | <span data-ttu-id="1e9dc-141">行為： Win32/探索。 \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-142">橫向移動</span><span class="sxs-lookup"><span data-stu-id="1e9dc-142">Lateral Movement</span></span> | <span data-ttu-id="1e9dc-143">行為： Win32/LateralMovement. \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-144">集合</span><span class="sxs-lookup"><span data-stu-id="1e9dc-144">Collection</span></span> |   <span data-ttu-id="1e9dc-145">行為： Win32/集合。 \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-146">命令和控制項</span><span class="sxs-lookup"><span data-stu-id="1e9dc-146">Command and Control</span></span> | <span data-ttu-id="1e9dc-147">行為： Win32/CommandAndControl. \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-148">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="1e9dc-148">Exfiltration</span></span>   | <span data-ttu-id="1e9dc-149">行為： Win32/Exfiltration. \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-150">影響</span><span class="sxs-lookup"><span data-stu-id="1e9dc-150">Impact</span></span> | <span data-ttu-id="1e9dc-151">行為： Win32/影響。 \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="1e9dc-152">未分類</span><span class="sxs-lookup"><span data-stu-id="1e9dc-152">Uncategorized</span></span>  | <span data-ttu-id="1e9dc-153">行為： Win32/Generic. \*！ ml</span><span class="sxs-lookup"><span data-stu-id="1e9dc-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="1e9dc-154">若要深入瞭解特定威脅，請參閱 **[最近的全域威脅活動](https://www.microsoft.com/wdsi/threats)**。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="1e9dc-155">設定用戶端行為封鎖</span><span class="sxs-lookup"><span data-stu-id="1e9dc-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="1e9dc-156">如果您的組織使用的是用於端點的 Defender，則預設會啟用用戶端行為封鎖。</span><span class="sxs-lookup"><span data-stu-id="1e9dc-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="1e9dc-157">不過，若要受益于所有的 Defender for Endpoint 功能，包括 [行為封鎖和包容](behavioral-blocking-containment.md)，請確定已啟用並設定 Defender for endpoint 的下列功能和功能：</span><span class="sxs-lookup"><span data-stu-id="1e9dc-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="1e9dc-158">用於端點基準的 Defender</span><span class="sxs-lookup"><span data-stu-id="1e9dc-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="1e9dc-159">裝置架至 Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1e9dc-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="1e9dc-160">封鎖模式中的 EDR</span><span class="sxs-lookup"><span data-stu-id="1e9dc-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="1e9dc-161">攻擊面縮減</span><span class="sxs-lookup"><span data-stu-id="1e9dc-161">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="1e9dc-162">[下一代保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (防病毒) </span><span class="sxs-lookup"><span data-stu-id="1e9dc-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="1e9dc-163">相關文章</span><span class="sxs-lookup"><span data-stu-id="1e9dc-163">Related articles</span></span>

- [<span data-ttu-id="1e9dc-164">行為封鎖和包含專案</span><span class="sxs-lookup"><span data-stu-id="1e9dc-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="1e9dc-165">意見反應迴圈封鎖</span><span class="sxs-lookup"><span data-stu-id="1e9dc-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="1e9dc-166"> (博客) 行為封鎖與包容：將光學器件轉換成保護</span><span class="sxs-lookup"><span data-stu-id="1e9dc-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="1e9dc-167">適用于端點資源的有用的 Defender</span><span class="sxs-lookup"><span data-stu-id="1e9dc-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
