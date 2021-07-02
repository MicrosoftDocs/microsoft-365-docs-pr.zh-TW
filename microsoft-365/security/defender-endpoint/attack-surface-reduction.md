---
title: 使用受攻擊面縮小規則防止惡意程式碼感染
description: 攻擊面減少規則可協助防止利用應用程式和腳本感染具有惡意程式碼的裝置。
keywords: 攻擊面減少規則，asr，hips，主機入侵防護系統，保護規則，反侵入，antiexploit，exploit，感染防護，Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ed6dc9956c3e78f8ed39dca9cd6bf0421dd28456
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276986"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="3f893-104">使用受攻擊面縮小規則防止惡意程式碼感染</span><span class="sxs-lookup"><span data-stu-id="3f893-104">Use attack surface reduction rules to prevent malware infection</span></span>

<span data-ttu-id="3f893-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3f893-105">**Applies to:**</span></span>

- [<span data-ttu-id="3f893-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3f893-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3f893-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f893-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="3f893-108">攻擊面減少規則為何很重要</span><span class="sxs-lookup"><span data-stu-id="3f893-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="3f893-109">組織的攻擊麵包括攻擊者可能會損害組織之裝置或網路的所有地方。</span><span class="sxs-lookup"><span data-stu-id="3f893-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="3f893-110">減少攻擊面是指保護您組織的裝置和網路，這可讓攻擊者以較少的方式執行攻擊。</span><span class="sxs-lookup"><span data-stu-id="3f893-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="3f893-111">在 Microsoft Defender for Endpoint 中設定攻擊面降低規則可協助！</span><span class="sxs-lookup"><span data-stu-id="3f893-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="3f893-112">攻擊面減少規則會以特定的軟體行為為目標，例如：</span><span class="sxs-lookup"><span data-stu-id="3f893-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="3f893-113">啟動可執行檔及腳本，以嘗試下載或執行檔</span><span class="sxs-lookup"><span data-stu-id="3f893-113">Launching executable files and scripts that attempt to download or run files</span></span>
- <span data-ttu-id="3f893-114">執行模糊或其他可疑的腳本</span><span class="sxs-lookup"><span data-stu-id="3f893-114">Running obfuscated or otherwise suspicious scripts</span></span>
- <span data-ttu-id="3f893-115">執行在正常的日常工作中，應用程式通常不會啟動的行為</span><span class="sxs-lookup"><span data-stu-id="3f893-115">Performing behaviors that apps don't usually initiate during normal day-to-day work</span></span>

<span data-ttu-id="3f893-116">這類軟體行為有時會出現在合法的應用程式中。</span><span class="sxs-lookup"><span data-stu-id="3f893-116">Such software behaviors are sometimes seen in legitimate applications.</span></span> <span data-ttu-id="3f893-117">不過，這些行為通常會被視為危險，因為它們通常是透過惡意程式碼被攻擊者濫用。</span><span class="sxs-lookup"><span data-stu-id="3f893-117">However, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="3f893-118">攻擊面減少規則可以限制以軟體為基礎的危險行為，並協助保護您的組織安全。</span><span class="sxs-lookup"><span data-stu-id="3f893-118">Attack surface reduction rules can constrain software-based risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="3f893-119">如需設定攻擊面減少規則的相關資訊，請參閱 [啟用攻擊面降減規則](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="3f893-119">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="3f893-120">在部署之前評估規則影響</span><span class="sxs-lookup"><span data-stu-id="3f893-120">Assess rule impact before deployment</span></span>

<span data-ttu-id="3f893-121">您可以在[威脅與弱點管理](/windows/security/threat-protection/#tvm)中開啟該規則的安全性建議，以評估攻擊面降低規則可能會如何影響您的網路。</span><span class="sxs-lookup"><span data-stu-id="3f893-121">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](/windows/security/threat-protection/#tvm).</span></span>

:::image type="content" source="images/asrrecommendation.png" alt-text="攻擊面降低規則的安全性 reco":::

<span data-ttu-id="3f893-123">在 [建議詳細資料] 窗格中，檢查 [使用者影響] 以判斷您的裝置可接受新原則的百分比，以封鎖模式啟用規則，而不會對生產力造成不良影響。</span><span class="sxs-lookup"><span data-stu-id="3f893-123">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

<span data-ttu-id="3f893-124">如需支援的作業系統及其他需求資訊的相關資訊，請參閱「啟用攻擊面降低規則」一文中的 [需求](enable-attack-surface-reduction.md#requirements) 。</span><span class="sxs-lookup"><span data-stu-id="3f893-124">See [Requirements](enable-attack-surface-reduction.md#requirements) in the "Enable attack surface reduction rules" article for information about supported operating systems and additional requirement information.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="3f893-125">評估的審計模式</span><span class="sxs-lookup"><span data-stu-id="3f893-125">Audit mode for evaluation</span></span>

<span data-ttu-id="3f893-126">使用 [稽核模式](audit-windows-defender.md) 評估攻擊面降低規則在啟用時對組織的影響。</span><span class="sxs-lookup"><span data-stu-id="3f893-126">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if enabled.</span></span> <span data-ttu-id="3f893-127">請先在稽核模式中執行所有規則，以便了解它們如何影響您的企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="3f893-127">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="3f893-128">許多商務營運應用程式都是以有限的安全性考慮來編寫，而且他們可能會以類似惡意程式碼的方式執行工作。</span><span class="sxs-lookup"><span data-stu-id="3f893-128">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="3f893-129">透過監視審核資料並 [新增](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 必要應用程式的排除專案，您可以在不降低生產力的情況下，部署攻擊面減少規則。</span><span class="sxs-lookup"><span data-stu-id="3f893-129">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="3f893-130">使用者的警告模式</span><span class="sxs-lookup"><span data-stu-id="3f893-130">Warn mode for users</span></span>

<span data-ttu-id="3f893-131"> (**NEW**！ ) 在警告模式功能之前，已啟用的攻擊面降規則可以設定為 [稽核模式] 或 [封鎖模式]。</span><span class="sxs-lookup"><span data-stu-id="3f893-131">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="3f893-132">使用新的警告模式時，每當攻擊面減少規則封鎖內容時，使用者會看到指出內容已封鎖的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="3f893-132">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="3f893-133">對話方塊也會為使用者提供取消封鎖內容的選項。</span><span class="sxs-lookup"><span data-stu-id="3f893-133">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="3f893-134">然後，使用者可以重試其動作，並完成操作。</span><span class="sxs-lookup"><span data-stu-id="3f893-134">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="3f893-135">當使用者取消封鎖內容時，內容會維持在24小時內解除封鎖，然後封鎖簡歷。</span><span class="sxs-lookup"><span data-stu-id="3f893-135">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="3f893-136">警告模式可協助您的組織實施攻擊面降減規則，而不會防止使用者存取他們執行其工作所需的內容。</span><span class="sxs-lookup"><span data-stu-id="3f893-136">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span>

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="3f893-137">警告模式的運作需求</span><span class="sxs-lookup"><span data-stu-id="3f893-137">Requirements for warn mode to work</span></span>

<span data-ttu-id="3f893-138">在執行下列 Windows 版本的裝置上支援警告模式：</span><span class="sxs-lookup"><span data-stu-id="3f893-138">Warn mode is supported on devices running the following versions of Windows:</span></span>

- <span data-ttu-id="3f893-139">[Windows 10 版本 1809](/windows/whats-new/whats-new-windows-10-version-1809)或更新版本</span><span class="sxs-lookup"><span data-stu-id="3f893-139">[Windows 10, version 1809](/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="3f893-140">[Windows Server，版本 1809](/windows-server/get-started/whats-new-in-windows-server-1809)或更新版本</span><span class="sxs-lookup"><span data-stu-id="3f893-140">[Windows Server, version 1809](/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>

<span data-ttu-id="3f893-141">使用[Active 模式](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)中的即時保護時，必須執行 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="3f893-141">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="3f893-142">此外，請確定已安裝[Microsoft Defender 防毒軟體和反惡意軟體更新](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。</span><span class="sxs-lookup"><span data-stu-id="3f893-142">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>

- <span data-ttu-id="3f893-143">最低平臺版本需求： `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="3f893-143">Minimum platform release requirement: `4.18.2008.9`</span></span>
- <span data-ttu-id="3f893-144">最低引擎發行需求： `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="3f893-144">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="3f893-145">如需詳細資訊和若要取得更新，請參閱 [Microsoft Defender 反惡意程式碼平臺的更新](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="3f893-145">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="3f893-146">不支援警告模式的情況</span><span class="sxs-lookup"><span data-stu-id="3f893-146">Cases where warn mode is not supported</span></span>

<span data-ttu-id="3f893-147">當您在 Microsoft 端點管理員中設定三種攻擊面降減規則時，不支援警告模式。</span><span class="sxs-lookup"><span data-stu-id="3f893-147">Warn mode is not supported for three attack surface reduction rules when you configure them in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="3f893-148"> (如果使用群組原則來設定攻擊面降低規則，則會支援警告模式。 ) 在 Microsoft 端點管理員中進行設定時，不支援警告模式的三個規則如下：</span><span class="sxs-lookup"><span data-stu-id="3f893-148">(If you use Group Policy to configure your attack surface reduction rules, warn mode is supported.) The three rules that do not support warn mode when you configure them in Microsoft Endpoint Manager are as follows:</span></span>

- <span data-ttu-id="3f893-149">[封鎖 JavaScript 或 VBScript 啟動下載的可執行內容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`) </span><span class="sxs-lookup"><span data-stu-id="3f893-149">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="3f893-150">[透過 WMI 事件訂閱封鎖的封鎖](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`) </span><span class="sxs-lookup"><span data-stu-id="3f893-150">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="3f893-151">[使用針對勒索軟體](#use-advanced-protection-against-ransomware) (GUID 的高級防護 `c1db55ab-c21a-4637-bb3f-a12568109d35`) </span><span class="sxs-lookup"><span data-stu-id="3f893-151">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="3f893-152">此外，執行舊版本 Windows 的裝置不支援警告模式。</span><span class="sxs-lookup"><span data-stu-id="3f893-152">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="3f893-153">在這種情況下，已設定為在警告模式中執行的攻擊面降規則會以封鎖模式執行。</span><span class="sxs-lookup"><span data-stu-id="3f893-153">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="3f893-154">通知與警示</span><span class="sxs-lookup"><span data-stu-id="3f893-154">Notifications and alerts</span></span>

<span data-ttu-id="3f893-155">每當觸發攻擊面降低規則時，就會在裝置上顯示通知。</span><span class="sxs-lookup"><span data-stu-id="3f893-155">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="3f893-156">您可以使用公司詳細資料和連絡資訊[自訂通知](customize-attack-surface-reduction.md#customize-the-notification)。</span><span class="sxs-lookup"><span data-stu-id="3f893-156">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="3f893-157">此外，當觸發某些攻擊面降低規則時，會產生警示。</span><span class="sxs-lookup"><span data-stu-id="3f893-157">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span>

<span data-ttu-id="3f893-158">您可以在 Microsoft 365 Defender 入口網站 (中查看通知及所產生的任何警示 [https://security.microsoft.com](https://security.microsoft.com)) 先前稱為[Microsoft Defender 資訊安全中心](microsoft-defender-security-center.md)) 的 (。</span><span class="sxs-lookup"><span data-stu-id="3f893-158">Notifications and any alerts that are generated can be viewed in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com)) (formerly called the [Microsoft Defender Security Center](microsoft-defender-security-center.md)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="3f893-159">高級搜尋和攻擊面降低事件</span><span class="sxs-lookup"><span data-stu-id="3f893-159">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="3f893-160">您可以使用高級搜尋來查看攻擊面降低事件。</span><span class="sxs-lookup"><span data-stu-id="3f893-160">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="3f893-161">為了簡化傳入資料的數量，您可以透過高級搜尋查看每小時只有一個唯一的處理常式。</span><span class="sxs-lookup"><span data-stu-id="3f893-161">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="3f893-162">攻擊面降低事件的時間是在一小時內第一次看到的事件。</span><span class="sxs-lookup"><span data-stu-id="3f893-162">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="3f893-163">例如，假設在 2:00 PM 小時內10台裝置上發生攻擊面降低事件。</span><span class="sxs-lookup"><span data-stu-id="3f893-163">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="3f893-164">假設第一個事件發生于2:15，最後是2:45。</span><span class="sxs-lookup"><span data-stu-id="3f893-164">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="3f893-165">使用高級搜尋時，您會看到該事件的一個實例 (，即使它實際發生于10個裝置) 上，而且其時間戳記會是 2:15 PM。</span><span class="sxs-lookup"><span data-stu-id="3f893-165">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span>

<span data-ttu-id="3f893-166">如需有關高級搜尋的詳細資訊，請參閱 [使用高級搜尋主動搜尋威脅](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3f893-166">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="3f893-167">跨 Windows 版本的攻擊面減少功能</span><span class="sxs-lookup"><span data-stu-id="3f893-167">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="3f893-168">您可以針對執行下列任何版本與 Windows 的裝置，設定攻擊面減少規則：</span><span class="sxs-lookup"><span data-stu-id="3f893-168">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="3f893-169">Windows 10 專業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="3f893-169">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3f893-170">Windows 10 企業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="3f893-170">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3f893-171">Windows伺服器，[版本 1803 (半年通道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更新版本</span><span class="sxs-lookup"><span data-stu-id="3f893-171">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="3f893-172">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-172">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="3f893-173">雖然攻擊面降減規則不需要[Windows E5 授權](/windows/deployment/deploy-enterprise-licenses)，但如果您有 Windows E5，就會取得高級管理功能。</span><span class="sxs-lookup"><span data-stu-id="3f893-173">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="3f893-174">「高級功能」-僅適用于 Windows E5-包括：</span><span class="sxs-lookup"><span data-stu-id="3f893-174">The advanced capabilities - available only in Windows E5 - include:</span></span>

- <span data-ttu-id="3f893-175">在[Defender For Endpoint](microsoft-defender-endpoint.md)中可用的監控、分析和工作流程</span><span class="sxs-lookup"><span data-stu-id="3f893-175">The monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md)</span></span>
- <span data-ttu-id="3f893-176">[Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center)中的報告和設定功能。</span><span class="sxs-lookup"><span data-stu-id="3f893-176">The reporting and configuration capabilities in [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="3f893-177">Windows Professional 或 Windows E3 授權無法使用這些高級功能。</span><span class="sxs-lookup"><span data-stu-id="3f893-177">These advanced capabilities aren't available with a Windows Professional or Windows E3 license.</span></span> <span data-ttu-id="3f893-178">不過，如果您有這些授權，您可以使用「事件檢視器」和 Microsoft Defender 防毒軟體記錄檔，以查看攻擊面減少規則事件。</span><span class="sxs-lookup"><span data-stu-id="3f893-178">However, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="3f893-179">在 Microsoft 365 Defender 入口網站中查看攻擊面降低事件</span><span class="sxs-lookup"><span data-stu-id="3f893-179">Review attack surface reduction events in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="3f893-180">當警示調查案例中，Defender for Endpoint 提供事件和區塊的詳細報告。</span><span class="sxs-lookup"><span data-stu-id="3f893-180">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="3f893-181">您可以使用 [[高級搜尋](advanced-hunting-query-language.md)]，在[Microsoft 365 Defender](microsoft-defender-security-center.md)中查詢 Defender 的端點資料。</span><span class="sxs-lookup"><span data-stu-id="3f893-181">You can query Defender for Endpoint data in [Microsoft 365 Defender](microsoft-defender-security-center.md) by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="3f893-182">如果您正在執行 [稽核模式](audit-windows-defender.md)，您可以使用高級搜尋來瞭解攻擊面降低規則可能會如何影響您的環境。</span><span class="sxs-lookup"><span data-stu-id="3f893-182">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules might affect your environment.</span></span>

<span data-ttu-id="3f893-183">範例查詢如下：</span><span class="sxs-lookup"><span data-stu-id="3f893-183">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="3f893-184">在 Windows 事件檢視器中查看攻擊面降低事件</span><span class="sxs-lookup"><span data-stu-id="3f893-184">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="3f893-185">您可以查看 Windows 事件記錄檔，以查看攻擊面減少規則所產生的事件：</span><span class="sxs-lookup"><span data-stu-id="3f893-185">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="3f893-186">下載 [評估套件](https://aka.ms/mp7z2w) ，並將檔案 *cfa-events.xml* 解壓至裝置上易於存取的位置。</span><span class="sxs-lookup"><span data-stu-id="3f893-186">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>

2. <span data-ttu-id="3f893-187">在 [開始] 功能表中輸入文字、*事件檢視器*，以開啟 Windows 事件檢視器。</span><span class="sxs-lookup"><span data-stu-id="3f893-187">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>

3. <span data-ttu-id="3f893-188">在 [ **動作**] 下，選取 [匯 **入自訂視圖 ...**]。</span><span class="sxs-lookup"><span data-stu-id="3f893-188">Under **Actions**, select **Import custom view...**.</span></span>

4. <span data-ttu-id="3f893-189">從解壓縮的位置選取檔案 *cfa-events.xml* 。</span><span class="sxs-lookup"><span data-stu-id="3f893-189">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="3f893-190">或者， [直接複製 XML](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="3f893-190">Alternatively, [copy the XML directly](event-views.md).</span></span>

5. <span data-ttu-id="3f893-191">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="3f893-191">Select **OK**.</span></span>

<span data-ttu-id="3f893-192">您可以建立篩選事件只顯示下列事件的自訂視圖，這些事件都與「受控資料夾存取」有關：</span><span class="sxs-lookup"><span data-stu-id="3f893-192">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="3f893-193">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="3f893-193">Event ID</span></span>|<span data-ttu-id="3f893-194">描述</span><span class="sxs-lookup"><span data-stu-id="3f893-194">Description</span></span>|
|---|---|
|<span data-ttu-id="3f893-195">5007</span><span class="sxs-lookup"><span data-stu-id="3f893-195">5007</span></span>|<span data-ttu-id="3f893-196">設定變更時的事件</span><span class="sxs-lookup"><span data-stu-id="3f893-196">Event when settings are changed</span></span>|
|<span data-ttu-id="3f893-197">1121</span><span class="sxs-lookup"><span data-stu-id="3f893-197">1121</span></span>|<span data-ttu-id="3f893-198">在組塊模式中激發規則時的事件</span><span class="sxs-lookup"><span data-stu-id="3f893-198">Event when rule fires in Block-mode</span></span>|
|<span data-ttu-id="3f893-199">1122</span><span class="sxs-lookup"><span data-stu-id="3f893-199">1122</span></span>|<span data-ttu-id="3f893-200">在稽核模式中觸發規則時的事件</span><span class="sxs-lookup"><span data-stu-id="3f893-200">Event when rule fires in Audit-mode</span></span>|

<span data-ttu-id="3f893-201">在事件記錄中，列出的攻擊面降低事件的「引擎版本」是由 Defender for Endpoint 所產生，而不是由作業系統產生。</span><span class="sxs-lookup"><span data-stu-id="3f893-201">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="3f893-202">與 Windows 10 的 Defender 已整合，所以此功能可在已安裝 Windows 10 的所有裝置上運作。</span><span class="sxs-lookup"><span data-stu-id="3f893-202">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="3f893-203">受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="3f893-203">Attack surface reduction rules</span></span>

<span data-ttu-id="3f893-204">下表與子小節分別說明16個攻擊面降低規則。</span><span class="sxs-lookup"><span data-stu-id="3f893-204">The following table and subsections describe each of the 16 attack surface reduction rules.</span></span> <span data-ttu-id="3f893-205">攻擊面降低規則會依規則名稱依字母順序列出。</span><span class="sxs-lookup"><span data-stu-id="3f893-205">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span>

<span data-ttu-id="3f893-206">如果您是使用群組原則或 PowerShell 來設定攻擊面降低規則，則需要 Guid。</span><span class="sxs-lookup"><span data-stu-id="3f893-206">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="3f893-207">另一方面，如果您使用 Microsoft 端點管理員或 Microsoft Intune，便不需要 guid。</span><span class="sxs-lookup"><span data-stu-id="3f893-207">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>

|<span data-ttu-id="3f893-208">規則名稱</span><span class="sxs-lookup"><span data-stu-id="3f893-208">Rule name</span></span>|<span data-ttu-id="3f893-209">GUID</span><span class="sxs-lookup"><span data-stu-id="3f893-209">GUID</span></span>|<span data-ttu-id="3f893-210">File & 資料夾排除</span><span class="sxs-lookup"><span data-stu-id="3f893-210">File & folder exclusions</span></span>|<span data-ttu-id="3f893-211">支援的最低作業系統</span><span class="sxs-lookup"><span data-stu-id="3f893-211">Minimum OS supported</span></span>|
|---|:---:|---|---|
|[<span data-ttu-id="3f893-212">封鎖濫用的漏洞簽章驅動程式</span><span class="sxs-lookup"><span data-stu-id="3f893-212">Block abuse of exploited vulnerable signed drivers</span></span>](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|<span data-ttu-id="3f893-213">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-213">Supported</span></span>|<span data-ttu-id="3f893-214">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本) </span><span class="sxs-lookup"><span data-stu-id="3f893-214">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater)</span></span> |
|[<span data-ttu-id="3f893-215">封鎖 Adobe Reader，以建立子流程</span><span class="sxs-lookup"><span data-stu-id="3f893-215">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|<span data-ttu-id="3f893-216">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-216">Supported</span></span>|<span data-ttu-id="3f893-217">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-217">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-218">封鎖所有 Office 的應用程式建立子流程</span><span class="sxs-lookup"><span data-stu-id="3f893-218">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|<span data-ttu-id="3f893-219">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-219">Supported</span></span>|<span data-ttu-id="3f893-220">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-220">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-221">封鎖 Windows 本機安全性群組子系統 (lsass.exe 中的認證竊取) </span><span class="sxs-lookup"><span data-stu-id="3f893-221">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|<span data-ttu-id="3f893-222">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-222">Supported</span></span>|<span data-ttu-id="3f893-223">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-223">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-224">從電子郵件客戶程式和 web 郵件封鎖可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="3f893-224">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|<span data-ttu-id="3f893-225">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-225">Supported</span></span>|<span data-ttu-id="3f893-226">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-226">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-227">封鎖可執行檔，除非符合流行、age 或受信任的清單準則</span><span class="sxs-lookup"><span data-stu-id="3f893-227">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|<span data-ttu-id="3f893-228">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-228">Supported</span></span>|<span data-ttu-id="3f893-229">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-229">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-230">封鎖可能混淆的腳本執行</span><span class="sxs-lookup"><span data-stu-id="3f893-230">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|<span data-ttu-id="3f893-231">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-231">Supported</span></span>|<span data-ttu-id="3f893-232">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-232">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-233">從啟動下載的可執行內容封鎖 JavaScript 或 VBScript</span><span class="sxs-lookup"><span data-stu-id="3f893-233">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|<span data-ttu-id="3f893-234">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-234">Supported</span></span>|<span data-ttu-id="3f893-235">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-235">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-236">封鎖 Office 應用程式建立可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="3f893-236">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|<span data-ttu-id="3f893-237">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-237">Supported</span></span>|<span data-ttu-id="3f893-238">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-238">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-239">封鎖 Office 的應用程式將程式碼注入其他進程</span><span class="sxs-lookup"><span data-stu-id="3f893-239">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|<span data-ttu-id="3f893-240">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-240">Supported</span></span>|<span data-ttu-id="3f893-241">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-241">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-242">封鎖 Office 通訊應用程式建立子流程</span><span class="sxs-lookup"><span data-stu-id="3f893-242">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|<span data-ttu-id="3f893-243">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-243">Supported</span></span>|<span data-ttu-id="3f893-244">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-244">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-245">透過 WMI 事件訂閱封鎖持久性</span><span class="sxs-lookup"><span data-stu-id="3f893-245">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|<span data-ttu-id="3f893-246">不支援</span><span class="sxs-lookup"><span data-stu-id="3f893-246">Not supported</span></span>|<span data-ttu-id="3f893-247">[Windows 10，版本 1903](/windows/whats-new/whats-new-windows-10-version-1903) (組建 18362) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-247">[Windows 10, version 1903](/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span>|
|[<span data-ttu-id="3f893-248">封鎖來自 PSExec 和 WMI 命令的進程建立</span><span class="sxs-lookup"><span data-stu-id="3f893-248">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|<span data-ttu-id="3f893-249">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-249">Supported</span></span>|<span data-ttu-id="3f893-250">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-250">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-251">封鎖從 USB 執行的不受信任和未簽署程式</span><span class="sxs-lookup"><span data-stu-id="3f893-251">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|<span data-ttu-id="3f893-252">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-252">Supported</span></span>|<span data-ttu-id="3f893-253">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-253">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-254">從 Office 宏封鎖 WIN32 API 通話</span><span class="sxs-lookup"><span data-stu-id="3f893-254">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|<span data-ttu-id="3f893-255">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-255">Supported</span></span>|<span data-ttu-id="3f893-256">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-256">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="3f893-257">使用勒索軟體的高級防護</span><span class="sxs-lookup"><span data-stu-id="3f893-257">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|<span data-ttu-id="3f893-258">支援</span><span class="sxs-lookup"><span data-stu-id="3f893-258">Supported</span></span>|<span data-ttu-id="3f893-259">[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3f893-259">[Windows 10, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a><span data-ttu-id="3f893-260">封鎖濫用的漏洞簽章驅動程式</span><span class="sxs-lookup"><span data-stu-id="3f893-260">Block abuse of exploited vulnerable signed drivers</span></span>

<span data-ttu-id="3f893-261">此規則可防止應用程式將有漏洞的簽署驅動程式寫入磁片。</span><span class="sxs-lookup"><span data-stu-id="3f893-261">This rule prevents an application from writing a vulnerable signed driver to disk.</span></span> <span data-ttu-id="3f893-262">實際上， \- _具有足夠許可權_ \- 才能存取內核的本機應用程式可以利用有漏洞的已簽署驅動程式。</span><span class="sxs-lookup"><span data-stu-id="3f893-262">In-the-wild, vulnerable signed drivers can be exploited by local applications \- _that have sufficient privileges_ \- to gain access to the kernel.</span></span> <span data-ttu-id="3f893-263">有漏洞的簽章驅動程式可讓攻擊者停用或規避安全性解決方案，最後導致系統受損。</span><span class="sxs-lookup"><span data-stu-id="3f893-263">Vulnerable signed drivers enable attackers to disable or circumvent security solutions, eventually leading to system compromise.</span></span>

<span data-ttu-id="3f893-264">遭到 **濫用的漏洞已簽章驅動程式規則封鎖** ，不會封鎖已存在於已在系統上載入的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="3f893-264">The **Block abuse of exploited vulnerable signed drivers** rule does not block a driver already existing on the system from being loaded.</span></span>

>[!NOTE]
>
> <span data-ttu-id="3f893-265">您可以使用 mem OMA-URI 自訂規則的程式 [資訊，來](enable-attack-surface-reduction.md#mem) 設定此規則。</span><span class="sxs-lookup"><span data-stu-id="3f893-265">You can configure this rule using [MEM OMA-URI](enable-attack-surface-reduction.md#mem) for MEM OMA-URI custom rules procedural information.</span></span>
>
> <span data-ttu-id="3f893-266">您也可以使用 [PowerShell](enable-attack-surface-reduction.md#powershell)來設定此規則。</span><span class="sxs-lookup"><span data-stu-id="3f893-266">You can also configure this rule using [PowerShell](enable-attack-surface-reduction.md#powershell).</span></span>
>
> <span data-ttu-id="3f893-267">若要檢查驅動程式，請使用此網站 [提交分析的驅動程式](https://www.microsoft.com/en-us/wdsi/driversubmission)。</span><span class="sxs-lookup"><span data-stu-id="3f893-267">To have a driver examined, use this Web site to [Submit a driver for analysis](https://www.microsoft.com/en-us/wdsi/driversubmission).</span></span>

<span data-ttu-id="3f893-268">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-268">Supported operating systems:</span></span>

- <span data-ttu-id="3f893-269">[Windows 10 專業版，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="3f893-269">[Windows 10 Pro, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3f893-270">[Windows 10 企業版，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="3f893-270">[Windows 10 Enterprise, version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3f893-271">[Windows Server，版本 1803 (半年通道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更新版本</span><span class="sxs-lookup"><span data-stu-id="3f893-271">[Windows Server, version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="3f893-272">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-272">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="3f893-273">Intune 名稱： `Block abuse of exploited vulnerable signed drivers`</span><span class="sxs-lookup"><span data-stu-id="3f893-273">Intune Name: `Block abuse of exploited vulnerable signed drivers`</span></span>

<span data-ttu-id="3f893-274">GUID:：  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span><span class="sxs-lookup"><span data-stu-id="3f893-274">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span></span>

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="3f893-275">封鎖 Adobe Reader，以建立子流程</span><span class="sxs-lookup"><span data-stu-id="3f893-275">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="3f893-276">此規則會封鎖來自 Adobe Reader 的攻擊，使其無法建立處理常式。</span><span class="sxs-lookup"><span data-stu-id="3f893-276">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="3f893-277">透過社交工程或利用方式，惡意程式碼可以下載和啟動有效載荷，並中斷 Adobe Reader。</span><span class="sxs-lookup"><span data-stu-id="3f893-277">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="3f893-278">透過封鎖子流程以供 Adobe Reader 的產生，惡意程式碼嘗試使用它做為向量，便無法散佈。</span><span class="sxs-lookup"><span data-stu-id="3f893-278">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="3f893-279">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-279">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-280">Windows 10 版本 1809</span><span class="sxs-lookup"><span data-stu-id="3f893-280">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="3f893-281">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-281">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-282">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-282">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="3f893-283">Intune 名稱： `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="3f893-283">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="3f893-284">Configuration Manager 名稱：尚未提供</span><span class="sxs-lookup"><span data-stu-id="3f893-284">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="3f893-285">GUID:： `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="3f893-285">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="3f893-286">封鎖所有 Office 的應用程式建立子流程</span><span class="sxs-lookup"><span data-stu-id="3f893-286">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="3f893-287">此規則會封鎖 Office 的應用程式建立子流程。</span><span class="sxs-lookup"><span data-stu-id="3f893-287">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="3f893-288">Office 應用程式包括 Word、Excel、PowerPoint、OneNote 和 Access。</span><span class="sxs-lookup"><span data-stu-id="3f893-288">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="3f893-289">建立惡意的子流程是常見的惡意程式碼策略。</span><span class="sxs-lookup"><span data-stu-id="3f893-289">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="3f893-290">濫用 Office 為向量的惡意程式碼通常會執行 VBA 宏，並利用程式碼下載並嘗試執行更多負載。</span><span class="sxs-lookup"><span data-stu-id="3f893-290">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="3f893-291">不過，某些合法的企業營運應用程式也可能會產生子進程，以用於良性目的;例如，產生命令提示字元或使用 PowerShell 來設定登錄設定。</span><span class="sxs-lookup"><span data-stu-id="3f893-291">However, some legitimate line-of-business applications might also generate child processes for benign purposes; such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="3f893-292">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-292">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-293">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="3f893-293">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="3f893-294">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-294">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-295">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-295">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="3f893-296">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="3f893-296">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="3f893-297">Intune 名稱： `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="3f893-297">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="3f893-298">Configuration Manager 名稱： `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="3f893-298">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="3f893-299">GUID:： `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="3f893-299">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="3f893-300">封鎖從 Windows 本機安全授權子系統偷竊的認證</span><span class="sxs-lookup"><span data-stu-id="3f893-300">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="3f893-301">此規則可鎖定本機安全授權子系統服務 (LSASS) ，以防止認證偷竊。</span><span class="sxs-lookup"><span data-stu-id="3f893-301">This rule helps prevent credential stealing by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="3f893-302">LSASS 驗證在 Windows 電腦上登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="3f893-302">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="3f893-303">Microsoft Defender Credential Guard in Windows 10 一般會防止嘗試從 LSASS 提取認證。</span><span class="sxs-lookup"><span data-stu-id="3f893-303">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="3f893-304">不過，某些組織無法在其所有電腦上啟用認證防護，因為自訂的智慧卡驅動程式或其他載入至本機安全授權的程式的相容性問題 (LSA) 。</span><span class="sxs-lookup"><span data-stu-id="3f893-304">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="3f893-305">在這些情況下，攻擊者可以使用像是 Mimikatz 的駭客攻擊工具，從 LSASS scrape 純文字密碼和 NTLM 雜湊。</span><span class="sxs-lookup"><span data-stu-id="3f893-305">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="3f893-306">在某些應用程式中，此程式碼會列舉所有執行中的程式，並嘗試以詳盡的許可權來開啟這些進程。</span><span class="sxs-lookup"><span data-stu-id="3f893-306">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="3f893-307">此規則會拒絕應用程式的「開啟」動作，並將詳細資料記錄到安全性事件記錄檔。</span><span class="sxs-lookup"><span data-stu-id="3f893-307">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="3f893-308">此規則會產生大量的噪音。</span><span class="sxs-lookup"><span data-stu-id="3f893-308">This rule can generate a lot of noise.</span></span> <span data-ttu-id="3f893-309">如果您有一個應用程式，只列舉 LSASS，但沒有任何實際的功能影響，便不需要將其新增至排除清單。</span><span class="sxs-lookup"><span data-stu-id="3f893-309">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="3f893-310">這個事件記錄專案本身不一定表示惡意威脅。</span><span class="sxs-lookup"><span data-stu-id="3f893-310">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="3f893-311">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-311">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-312">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="3f893-312">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="3f893-313">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-313">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-314">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-314">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="3f893-315">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="3f893-315">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="3f893-316">Intune 名稱： `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="3f893-316">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="3f893-317">Configuration Manager 名稱： `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="3f893-317">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="3f893-318">GUID:： `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="3f893-318">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="3f893-319">從電子郵件客戶程式和 web 郵件封鎖可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="3f893-319">Block executable content from email client and webmail</span></span>

<span data-ttu-id="3f893-320">此規則會封鎖下列檔案類型，以從 Microsoft Outlook 應用程式內開啟的電子郵件，或 Outlook .com 和其他流行的 web 郵件提供者來啟動：</span><span class="sxs-lookup"><span data-stu-id="3f893-320">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="3f893-321">可執行檔 (例如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="3f893-321">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="3f893-322">腳本檔案 (例如 PowerShell .ps、Visual Basic .vbs 或 JavaScript .js 檔) </span><span class="sxs-lookup"><span data-stu-id="3f893-322">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="3f893-323">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-323">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-324">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="3f893-324">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="3f893-325">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-325">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-326">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-326">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="3f893-327">Microsoft 端點管理員CB 1710</span><span class="sxs-lookup"><span data-stu-id="3f893-327">Microsoft Endpoint Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="3f893-328">Intune 名稱： `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="3f893-328">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="3f893-329">Microsoft 端點管理員名稱：`Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="3f893-329">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="3f893-330">GUID:： `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="3f893-330">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="3f893-331">**從電子郵件客戶程式和 web 郵件封鎖可執行檔內容**，具有下列替代描述（取決於您所使用的應用程式）：</span><span class="sxs-lookup"><span data-stu-id="3f893-331">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
>
> - <span data-ttu-id="3f893-332">Intune (設定檔) ：執行可執行檔內容 (exe、dll、ps、js、vbs 等 ) 從電子郵件 (郵件) web 郵件用戶端 () 沒有例外。</span><span class="sxs-lookup"><span data-stu-id="3f893-332">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="3f893-333">端點管理員：封鎖電子郵件和郵件傳送用戶端的可執行內容下載。</span><span class="sxs-lookup"><span data-stu-id="3f893-333">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="3f893-334">群組原則：從電子郵件客戶程式和 web 郵件封鎖可執行檔內容。</span><span class="sxs-lookup"><span data-stu-id="3f893-334">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="3f893-335">封鎖可執行檔，除非符合流行、age 或受信任的清單準則</span><span class="sxs-lookup"><span data-stu-id="3f893-335">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="3f893-336">此規則會封鎖可執行檔，例如 .exe、.dll 或 .scr，除非符合下列任一條件，否則不會啟動：</span><span class="sxs-lookup"><span data-stu-id="3f893-336">This rule blocks executable files, such as .exe, .dll, or .scr, from launching unless any of the following conditions are met:</span></span>

- <span data-ttu-id="3f893-337">傳播：可執行檔位於1000以上的端點上</span><span class="sxs-lookup"><span data-stu-id="3f893-337">Prevalence: The executable files are found on more than 1,000 endpoints</span></span>
- <span data-ttu-id="3f893-338">Age：已于24小時前發行可執行檔</span><span class="sxs-lookup"><span data-stu-id="3f893-338">Age: The executable files were released more than 24 hours ago</span></span>
- <span data-ttu-id="3f893-339">位置：可執行檔會包含在信任的清單或排除清單中</span><span class="sxs-lookup"><span data-stu-id="3f893-339">Location: The executable files are included in a trusted list or an exclusion list</span></span>

<span data-ttu-id="3f893-340">啟動不受信任或未知的可執行檔可能會是危險的，因為如果這些檔案是惡意的，就可能不會做為清除。</span><span class="sxs-lookup"><span data-stu-id="3f893-340">Launching untrusted or unknown executable files can be risky, as it might not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f893-341">您必須 [啟用雲端提供的保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 才能使用此規則。</span><span class="sxs-lookup"><span data-stu-id="3f893-341">You must [enable cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>
>
> <span data-ttu-id="3f893-342">規則會 **封鎖可執行檔，除非符合** 「具有 GUID 的流行」、「年齡」或「受信任」清單準則， `01443614-cd74-433a-b99e-2ecdc07bfc25` 且不是由系統管理員所指定的狀態。</span><span class="sxs-lookup"><span data-stu-id="3f893-342">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="3f893-343">此規則使用雲端提供的保護，定期更新其信任清單。</span><span class="sxs-lookup"><span data-stu-id="3f893-343">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
> <span data-ttu-id="3f893-344">您可以使用資料夾路徑或完全限定的資源名稱來指定個別檔案或資料夾 () 但是您無法指定適用的規則或排除專案。</span><span class="sxs-lookup"><span data-stu-id="3f893-344">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="3f893-345">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-345">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-346">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="3f893-346">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="3f893-347">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-347">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-348">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-348">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="3f893-349">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="3f893-349">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="3f893-350">Intune 名稱： `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="3f893-350">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="3f893-351">Configuration Manager 名稱： `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="3f893-351">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="3f893-352">GUID:： `01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="3f893-352">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="3f893-353">封鎖可能混淆的腳本執行</span><span class="sxs-lookup"><span data-stu-id="3f893-353">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="3f893-354">此規則會偵測模糊腳本中的可疑屬性。</span><span class="sxs-lookup"><span data-stu-id="3f893-354">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="3f893-355">腳本模糊處理是一種常見的技術，惡意程式碼作者和合法的應用程式都使用它來隱藏知識屬性或減少腳本載入時間。</span><span class="sxs-lookup"><span data-stu-id="3f893-355">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="3f893-356">惡意程式碼作者也會使用模糊處理，使惡意程式碼難以閱讀，這可防止人員和安全性軟體的接近審查。</span><span class="sxs-lookup"><span data-stu-id="3f893-356">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="3f893-357">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-357">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-358">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="3f893-358">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="3f893-359">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-359">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-360">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-360">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="3f893-361">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="3f893-361">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="3f893-362">Intune 名稱： `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="3f893-362">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="3f893-363">Configuration Manager 名稱： `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="3f893-363">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="3f893-364">GUID:： `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="3f893-364">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="3f893-365">從啟動下載的可執行內容封鎖 JavaScript 或 VBScript</span><span class="sxs-lookup"><span data-stu-id="3f893-365">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="3f893-366">此規則可防止腳本啟動可能已下載的惡意內容。</span><span class="sxs-lookup"><span data-stu-id="3f893-366">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="3f893-367">撰寫在 JavaScript 或 VBScript 中的惡意程式碼通常是可從網際網路取得及啟動其他惡意程式碼的下載宏。</span><span class="sxs-lookup"><span data-stu-id="3f893-367">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="3f893-368">雖然不是常見的企業營運應用程式，但有時會使用腳本下載及啟動安裝程式。</span><span class="sxs-lookup"><span data-stu-id="3f893-368">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="3f893-369">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-369">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-370">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="3f893-370">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="3f893-371">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-371">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-372">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-372">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="3f893-373">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="3f893-373">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="3f893-374">Intune 名稱： `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="3f893-374">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="3f893-375">Configuration Manager 名稱： `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="3f893-375">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="3f893-376">GUID:： `D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="3f893-376">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="3f893-377">封鎖 Office 應用程式建立可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="3f893-377">Block Office applications from creating executable content</span></span>

<span data-ttu-id="3f893-378">此規則可防止 Office 的應用程式（包括 Word、Excel 及 PowerPoint）從建立潛在的惡意可執行檔內容，封鎖惡意程式碼寫入磁片。</span><span class="sxs-lookup"><span data-stu-id="3f893-378">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="3f893-379">以向量進行濫用 Office 的惡意程式碼可能會嘗試中斷 Office，並將惡意元件儲存至磁片。</span><span class="sxs-lookup"><span data-stu-id="3f893-379">Malware that abuses Office as a vector might attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="3f893-380">這些惡意元件會在電腦重新開機後，在系統上持續保存下來。</span><span class="sxs-lookup"><span data-stu-id="3f893-380">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="3f893-381">因此，此規則會防禦一般的持久性技術。</span><span class="sxs-lookup"><span data-stu-id="3f893-381">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="3f893-382">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-382">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-383">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="3f893-383">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="3f893-384">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-384">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-385">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-385">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="3f893-386">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (sccm) CB 1710 (SCCM 現在已 Microsoft Endpoint Configuration Manager) </span><span class="sxs-lookup"><span data-stu-id="3f893-386">[System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="3f893-387">Intune 名稱： `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="3f893-387">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="3f893-388">SCCM 名稱： `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="3f893-388">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="3f893-389">GUID:： `3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="3f893-389">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="3f893-390">封鎖 Office 的應用程式將程式碼注入其他進程</span><span class="sxs-lookup"><span data-stu-id="3f893-390">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="3f893-391">此規則封鎖程式碼注入嘗試 Office 的應用程式到其他的處理常式。</span><span class="sxs-lookup"><span data-stu-id="3f893-391">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="3f893-392">攻擊者可能會嘗試使用 Office 的應用程式，透過程式碼注入將惡意程式碼遷移到其他程式中，讓程式碼可以偽裝成一種乾淨的處理常式。</span><span class="sxs-lookup"><span data-stu-id="3f893-392">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="3f893-393">使用程式碼注入，並沒有已知的合法商務目的。</span><span class="sxs-lookup"><span data-stu-id="3f893-393">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="3f893-394">此規則會套用至 Word、Excel 及 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="3f893-394">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="3f893-395">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-395">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-396">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="3f893-396">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="3f893-397">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-397">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-398">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-398">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="3f893-399">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="3f893-399">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="3f893-400">Intune 名稱： `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="3f893-400">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="3f893-401">Configuration Manager 名稱： `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="3f893-401">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="3f893-402">GUID:： `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="3f893-402">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="3f893-403">封鎖 Office 通訊應用程式建立子流程</span><span class="sxs-lookup"><span data-stu-id="3f893-403">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="3f893-404">此規則可防止 Outlook 建立子流程，但仍然允許合法 Outlook 函式。</span><span class="sxs-lookup"><span data-stu-id="3f893-404">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="3f893-405">此規則可防止「社交工程」攻擊，並防止在 Outlook 中利用 abusing 弱點的程式碼。</span><span class="sxs-lookup"><span data-stu-id="3f893-405">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="3f893-406">它也會防止攻擊者在使用者的認證遭到破壞時可使用的[Outlook 規則和表單攻擊](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)。</span><span class="sxs-lookup"><span data-stu-id="3f893-406">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="3f893-407">此規則會在 Outlook 中封鎖 DLP 原則提示和工具提示。</span><span class="sxs-lookup"><span data-stu-id="3f893-407">This rule blocks DLP policy tips and ToolTips in Outlook.</span></span> <span data-ttu-id="3f893-408">此規則只適用于 Outlook 和 Outlook .com。</span><span class="sxs-lookup"><span data-stu-id="3f893-408">This rule applies to Outlook and Outlook.com only.</span></span>

<span data-ttu-id="3f893-409">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-409">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-410">Windows 10 版本 1809</span><span class="sxs-lookup"><span data-stu-id="3f893-410">Windows 10, version 1809</span></span>](/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="3f893-411">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-411">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-412">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-412">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="3f893-413">Intune 名稱： `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="3f893-413">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="3f893-414">Configuration Manager 名稱：無法使用</span><span class="sxs-lookup"><span data-stu-id="3f893-414">Configuration Manager name: Not available</span></span>

<span data-ttu-id="3f893-415">GUID:： `26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="3f893-415">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="3f893-416">透過 WMI 事件訂閱封鎖持久性</span><span class="sxs-lookup"><span data-stu-id="3f893-416">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="3f893-417">此規則可防止惡意程式碼 abusing WMI 在裝置上取得持久性。</span><span class="sxs-lookup"><span data-stu-id="3f893-417">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f893-418">檔案與資料夾排除不適用於此攻擊面降規則。</span><span class="sxs-lookup"><span data-stu-id="3f893-418">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="3f893-419">Fileless 威脅使用各種不同的戰術來保持隱藏狀態，以避免在檔案系統中看到，以及取得定期執行控制。</span><span class="sxs-lookup"><span data-stu-id="3f893-419">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="3f893-420">有些威脅可以濫用 WMI 存放庫和事件模型，以保持隱藏狀態。</span><span class="sxs-lookup"><span data-stu-id="3f893-420">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="3f893-421">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-421">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-422">Windows 10，版本1903</span><span class="sxs-lookup"><span data-stu-id="3f893-422">Windows 10, version 1903</span></span>](/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="3f893-423">Windows伺服器1903</span><span class="sxs-lookup"><span data-stu-id="3f893-423">Windows Server 1903</span></span>](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="3f893-424">Intune 名稱：無法使用</span><span class="sxs-lookup"><span data-stu-id="3f893-424">Intune name: Not available</span></span>

<span data-ttu-id="3f893-425">Configuration Manager 名稱：無法使用</span><span class="sxs-lookup"><span data-stu-id="3f893-425">Configuration Manager name: Not available</span></span>

<span data-ttu-id="3f893-426">GUID:： `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="3f893-426">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="3f893-427">封鎖來自 PSExec 和 WMI 命令的進程建立</span><span class="sxs-lookup"><span data-stu-id="3f893-427">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="3f893-428">此規則會封鎖透過 [PsExec](/sysinternals/downloads/psexec) 和 [WMI](/windows/win32/wmisdk/about-wmi) 所建立的處理常式執行。</span><span class="sxs-lookup"><span data-stu-id="3f893-428">This rule blocks processes created through [PsExec](/sysinternals/downloads/psexec) and [WMI](/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="3f893-429">PsExec 和 WMI 都可以遠端執行程式碼，因此惡意程式碼會 abusing 此功能以進行命令和控制，或將感染傳播到整個組織的網路。</span><span class="sxs-lookup"><span data-stu-id="3f893-429">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="3f893-430">只有在您使用 [Intune](/intune) 或另一個 MDM 解決方案管理裝置時，才使用此規則。</span><span class="sxs-lookup"><span data-stu-id="3f893-430">Only use this rule if you're managing your devices with [Intune](/intune) or another MDM solution.</span></span> <span data-ttu-id="3f893-431">因為此規則會封鎖 Configuration Manager 用戶端用來正確運作的 WMI 命令，所以此規則與管理的[Microsoft Endpoint Configuration Manager](/configmgr)不相容。</span><span class="sxs-lookup"><span data-stu-id="3f893-431">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="3f893-432">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-432">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-433">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="3f893-433">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="3f893-434">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-434">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-435">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-435">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="3f893-436">Intune 名稱： `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="3f893-436">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="3f893-437">Configuration Manager 名稱：不適用</span><span class="sxs-lookup"><span data-stu-id="3f893-437">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="3f893-438">GUID:： `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="3f893-438">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="3f893-439">封鎖從 USB 執行的不受信任和未簽署程式</span><span class="sxs-lookup"><span data-stu-id="3f893-439">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="3f893-440">使用此規則時，系統管理員可以防止未簽署或不受信任的可執行檔，從 USB 抽取式磁碟磁碟機（包括 SD 卡）執行。</span><span class="sxs-lookup"><span data-stu-id="3f893-440">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="3f893-441">封鎖的檔案類型包括可執行檔 (例如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="3f893-441">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="3f893-442">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-442">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-443">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="3f893-443">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="3f893-444">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-444">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-445">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-445">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="3f893-446">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="3f893-446">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="3f893-447">Intune 名稱： `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="3f893-447">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="3f893-448">Configuration Manager 名稱： `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="3f893-448">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="3f893-449">GUID:： `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="3f893-449">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="3f893-450">從 Office 宏封鎖 WIN32 API 通話</span><span class="sxs-lookup"><span data-stu-id="3f893-450">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="3f893-451">此規則可防止 VBA 宏呼叫 WIN32 APIs。</span><span class="sxs-lookup"><span data-stu-id="3f893-451">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="3f893-452">OfficeVBA 啟用 WIN32 API 呼叫。</span><span class="sxs-lookup"><span data-stu-id="3f893-452">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="3f893-453">惡意程式碼可能會濫用這項功能，例如 [呼叫 WIN32 APIs 以發動惡意外殼代碼](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) ，而不需直接寫入任何內容。</span><span class="sxs-lookup"><span data-stu-id="3f893-453">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="3f893-454">大多數的組織不依賴在日常運作中呼叫 WIN32 APIs 的功能，即使它們是以其他方式使用宏。</span><span class="sxs-lookup"><span data-stu-id="3f893-454">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="3f893-455">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-455">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-456">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="3f893-456">Windows 10, version 1709</span></span>](/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="3f893-457">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-457">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-458">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-458">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="3f893-459">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="3f893-459">Configuration Manager CB 1710</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="3f893-460">Intune 名稱： `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="3f893-460">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="3f893-461">Configuration Manager 名稱： `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="3f893-461">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="3f893-462">GUID:： `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="3f893-462">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="3f893-463">使用勒索軟體的高級防護</span><span class="sxs-lookup"><span data-stu-id="3f893-463">Use advanced protection against ransomware</span></span>

<span data-ttu-id="3f893-464">此規則可提供額外的保護，以防禦勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="3f893-464">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="3f893-465">它會同時使用用戶端和雲端試探法來判斷檔案是否與勒索軟體類似。</span><span class="sxs-lookup"><span data-stu-id="3f893-465">It uses both client and cloud heuristics to determine whether a file resembles ransomware.</span></span> <span data-ttu-id="3f893-466">此規則不會封鎖具備下列一項或多項特性的檔案：</span><span class="sxs-lookup"><span data-stu-id="3f893-466">This rule does not block files that have one or more of the following characteristics:</span></span>

- <span data-ttu-id="3f893-467">檔案已在 Microsoft 雲端中找到 unharmful。</span><span class="sxs-lookup"><span data-stu-id="3f893-467">The file has already been found to be unharmful in the Microsoft cloud.</span></span>
- <span data-ttu-id="3f893-468">檔案是有效的簽署檔。</span><span class="sxs-lookup"><span data-stu-id="3f893-468">The file is a valid signed file.</span></span>
- <span data-ttu-id="3f893-469">檔案的流行不足，無法視為勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="3f893-469">The file is prevalent enough to not be considered as ransomware.</span></span>

<span data-ttu-id="3f893-470">這項規則通常會在警告的另一個方面，以防止勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="3f893-470">The rule tends to err on the side of caution to prevent ransomware.</span></span>

> [!NOTE]
> <span data-ttu-id="3f893-471">您必須 [啟用雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md) 才能使用此規則。</span><span class="sxs-lookup"><span data-stu-id="3f893-471">You must [enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) to use this rule.</span></span>

<span data-ttu-id="3f893-472">支援的作業系統：</span><span class="sxs-lookup"><span data-stu-id="3f893-472">Supported operating systems:</span></span>

- [<span data-ttu-id="3f893-473">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="3f893-473">Windows 10, version 1803</span></span>](/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="3f893-474">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="3f893-474">Windows Server, version 1809</span></span>](/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="3f893-475">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f893-475">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="3f893-476">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="3f893-476">Configuration Manager CB 1802</span></span>](/configmgr/core/servers/manage/updates)

<span data-ttu-id="3f893-477">Intune 名稱： `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="3f893-477">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="3f893-478">Configuration Manager 名稱： `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="3f893-478">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="3f893-479">GUID:： `c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="3f893-479">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>
