---
title: 用戶端行為封鎖
description: 用戶端行為封鎖是 Microsoft Defender for Endpoint 中行為封鎖和包容功能的一部分
keywords: 行為封鎖，快速保護，用戶端行為，Microsoft Defender for Endpoint
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
ms.openlocfilehash: 4e416aa9484f251280649035247a59dcc82ce750
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795955"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="90e45-104">用戶端行為封鎖</span><span class="sxs-lookup"><span data-stu-id="90e45-104">Client behavioral blocking</span></span>

<span data-ttu-id="90e45-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="90e45-105">**Applies to:**</span></span>
- [<span data-ttu-id="90e45-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="90e45-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="90e45-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90e45-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="90e45-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="90e45-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="90e45-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="90e45-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="90e45-110">概觀</span><span class="sxs-lookup"><span data-stu-id="90e45-110">Overview</span></span>

<span data-ttu-id="90e45-111">用戶端行為封鎖是在 Defender for Endpoint 中的 [行為封鎖和包容功能](behavioral-blocking-containment.md) 的元件。</span><span class="sxs-lookup"><span data-stu-id="90e45-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](behavioral-blocking-containment.md) in Defender for Endpoint.</span></span> <span data-ttu-id="90e45-112">在裝置上偵測到可疑行為時 (也稱為「用戶端」或「端點」) 時，系統會自動封鎖、檢查和修正偽像 (（如檔案或應用程式) ）。</span><span class="sxs-lookup"><span data-stu-id="90e45-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="雲端和用戶端保護":::

<span data-ttu-id="90e45-114">搭配雲端保護時，防防毒保護的運作方式最佳。</span><span class="sxs-lookup"><span data-stu-id="90e45-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="90e45-115">用戶端行為封鎖的運作方式</span><span class="sxs-lookup"><span data-stu-id="90e45-115">How client behavioral blocking works</span></span>

<span data-ttu-id="90e45-116">[Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)可以偵測可疑行為、惡意程式碼、fileless 及記憶體中的攻擊，以及裝置上的其他功能。</span><span class="sxs-lookup"><span data-stu-id="90e45-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="90e45-117">偵測到可疑行為時，Microsoft Defender 防毒軟體會監視並將這些可疑行為及其程式樹傳送至雲端保護服務。</span><span class="sxs-lookup"><span data-stu-id="90e45-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="90e45-118">機器學習會區別惡意應用程式與在毫秒內的良好行為，以及分類每個專案。</span><span class="sxs-lookup"><span data-stu-id="90e45-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="90e45-119">在幾乎即時的情況下，只要有惡意的偽像，該專案就會在裝置上遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="90e45-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="90e45-120">每當偵測到可疑行為時，就會產生[警示](alerts-queue.md)，而且會在 Microsoft Defender 資訊安全中心 () 中顯示 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="90e45-120">Whenever a suspicious behavior is detected, an [alert](alerts-queue.md) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="90e45-121">用戶端行為封鎖是有效的，因為它不只是協助防止攻擊的啟動，它可協助停止已開始執行的攻擊。</span><span class="sxs-lookup"><span data-stu-id="90e45-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="90e45-122">而且，以反應反應 [封鎖](feedback-loop-blocking.md) (另一個功能封鎖和包含) 的功能，您的組織中的其他裝置都可以攻擊。</span><span class="sxs-lookup"><span data-stu-id="90e45-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="90e45-123">以行為為基礎的偵測</span><span class="sxs-lookup"><span data-stu-id="90e45-123">Behavior-based detections</span></span>

<span data-ttu-id="90e45-124">行為架構的偵測是根據[Enterprise 的 MITRE ATT&CK 矩陣](https://attack.mitre.org/matrices/enterprise)命名。</span><span class="sxs-lookup"><span data-stu-id="90e45-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="90e45-125">命名慣例有助於識別遭受惡意行為的攻擊階段：</span><span class="sxs-lookup"><span data-stu-id="90e45-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="90e45-126">策略</span><span class="sxs-lookup"><span data-stu-id="90e45-126">Tactic</span></span> |   <span data-ttu-id="90e45-127">偵測威脅名稱</span><span class="sxs-lookup"><span data-stu-id="90e45-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="90e45-128">初始存取</span><span class="sxs-lookup"><span data-stu-id="90e45-128">Initial Access</span></span> | `Behavior:Win32/InitialAccess.*!ml` |
|<span data-ttu-id="90e45-129">執行</span><span class="sxs-lookup"><span data-stu-id="90e45-129">Execution</span></span>  | `Behavior:Win32/Execution.*!ml` |
|<span data-ttu-id="90e45-130">堅持</span><span class="sxs-lookup"><span data-stu-id="90e45-130">Persistence</span></span>    | `Behavior:Win32/Persistence.*!ml` |
|<span data-ttu-id="90e45-131">許可權提升</span><span class="sxs-lookup"><span data-stu-id="90e45-131">Privilege Escalation</span></span>   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|<span data-ttu-id="90e45-132">國防規避</span><span class="sxs-lookup"><span data-stu-id="90e45-132">Defense Evasion</span></span>    | `Behavior:Win32/DefenseEvasion.*!ml` |
|<span data-ttu-id="90e45-133">認證存取</span><span class="sxs-lookup"><span data-stu-id="90e45-133">Credential Access</span></span>  | `Behavior:Win32/CredentialAccess.*!ml` |
|<span data-ttu-id="90e45-134">發現</span><span class="sxs-lookup"><span data-stu-id="90e45-134">Discovery</span></span>  | `Behavior:Win32/Discovery.*!ml` |
|<span data-ttu-id="90e45-135">橫向移動</span><span class="sxs-lookup"><span data-stu-id="90e45-135">Lateral Movement</span></span> | `Behavior:Win32/LateralMovement.*!ml` |
|<span data-ttu-id="90e45-136">集合</span><span class="sxs-lookup"><span data-stu-id="90e45-136">Collection</span></span> |   `Behavior:Win32/Collection.*!ml` |
|<span data-ttu-id="90e45-137">命令和控制項</span><span class="sxs-lookup"><span data-stu-id="90e45-137">Command and Control</span></span> | `Behavior:Win32/CommandAndControl.*!ml` |
|<span data-ttu-id="90e45-138">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="90e45-138">Exfiltration</span></span>   | `Behavior:Win32/Exfiltration.*!ml` |
|<span data-ttu-id="90e45-139">影響</span><span class="sxs-lookup"><span data-stu-id="90e45-139">Impact</span></span> | `Behavior:Win32/Impact.*!ml` |
|<span data-ttu-id="90e45-140">未分類</span><span class="sxs-lookup"><span data-stu-id="90e45-140">Uncategorized</span></span>  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> <span data-ttu-id="90e45-141">若要深入瞭解特定威脅，請參閱 **[最近的全域威脅活動](https://www.microsoft.com/wdsi/threats)**。</span><span class="sxs-lookup"><span data-stu-id="90e45-141">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="90e45-142">設定用戶端行為封鎖</span><span class="sxs-lookup"><span data-stu-id="90e45-142">Configuring client behavioral blocking</span></span>

<span data-ttu-id="90e45-143">如果您的組織使用的是用於端點的 Defender，則預設會啟用用戶端行為封鎖。</span><span class="sxs-lookup"><span data-stu-id="90e45-143">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="90e45-144">不過，若要受益于所有的 Defender for Endpoint 功能，包括 [行為封鎖和包容](behavioral-blocking-containment.md)，請確定已啟用並設定 Defender for endpoint 的下列功能和功能：</span><span class="sxs-lookup"><span data-stu-id="90e45-144">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="90e45-145">用於端點基準的 Defender</span><span class="sxs-lookup"><span data-stu-id="90e45-145">Defender for Endpoint baselines</span></span>](configure-machines-security-baseline.md)

- [<span data-ttu-id="90e45-146">裝置架至 Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="90e45-146">Devices onboarded to Defender for Endpoint</span></span>](onboard-configure.md)

- [<span data-ttu-id="90e45-147">封鎖模式中的 EDR</span><span class="sxs-lookup"><span data-stu-id="90e45-147">EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="90e45-148">攻擊面縮減</span><span class="sxs-lookup"><span data-stu-id="90e45-148">Attack surface reduction</span></span>](attack-surface-reduction.md)

- <span data-ttu-id="90e45-149">[下一代保護](configure-microsoft-defender-antivirus-features.md) (防病毒、反惡意程式碼和其他威脅防護功能) </span><span class="sxs-lookup"><span data-stu-id="90e45-149">[Next-generation protection](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware, and other threat protection capabilities)</span></span>

