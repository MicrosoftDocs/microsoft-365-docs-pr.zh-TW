---
title: 裝置監視與報告在 Microsoft 365 安全中心
description: 說明如何讓您的裝置，安全且最新狀態，以及您組織中的特別色潛在威脅
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365、 資訊安全中心、 監視、 報表、 裝置
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 71bdb350e8e166e9ccd6a303c7ef7bdde943e79c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078334"
---
# <a name="device-monitoring-and-reporting-in-microsoft-365-security-center"></a><span data-ttu-id="682f8-104">裝置監視與報告在 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="682f8-104">Device monitoring and reporting in Microsoft 365 security center</span></span>

<span data-ttu-id="682f8-105">在 Microsoft 365 安全中心保留裝置安全且最新狀態及特別色的潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="682f8-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="682f8-106">檢視裝置提醒</span><span class="sxs-lookup"><span data-stu-id="682f8-106">View device alerts</span></span>

<span data-ttu-id="682f8-107">從 Microsoft Defender ATP （隨附於 E5 授權），在您的裝置上取得相關資料外洩活動] 和 [其他威脅的最新提醒。</span><span class="sxs-lookup"><span data-stu-id="682f8-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="682f8-108">Microsoft 365 安全性中心有效率地監視這些警示高層級的使用自己偏好的工作流程。</span><span class="sxs-lookup"><span data-stu-id="682f8-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="682f8-109">監視影響力高且警示</span><span class="sxs-lookup"><span data-stu-id="682f8-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="682f8-110">每個 Microsoft Defender ATP 警示有相對應的嚴重性 — 高、 中、 低，或資訊性 — 表示其潛在影響到您的網路若留自動。</span><span class="sxs-lookup"><span data-stu-id="682f8-110">Each Microsoft Defender ATP alert has a corresponding severity—high, medium, low, or informational—that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="682f8-111">使用 [**裝置警示嚴重性**] 卡片，以專注特別的是更嚴重，且可能需要即時回應警訊上。</span><span class="sxs-lookup"><span data-stu-id="682f8-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="682f8-112">從這個卡，您可以檢視 Microsoft defender 資訊安全中心入口網站的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="682f8-112">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![裝置提醒嚴重性卡](../media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="682f8-114">了解來源的提醒</span><span class="sxs-lookup"><span data-stu-id="682f8-114">Understand sources of alerts</span></span>

<span data-ttu-id="682f8-115">Microsoft Defender ATP 會運用廣泛的安全性感應器和智慧來源]，以產生警示中的資料。</span><span class="sxs-lookup"><span data-stu-id="682f8-115">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="682f8-116">例如，它可以使用 Windows Defender 防毒軟體和協力廠商反惡意程式碼，以及透過 web 服務 API 提供自己自訂威脅情報偵測資訊。</span><span class="sxs-lookup"><span data-stu-id="682f8-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="682f8-117">**裝置警示偵測**來源卡片顯示由來源警示的通訊。</span><span class="sxs-lookup"><span data-stu-id="682f8-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="682f8-118">此卡可協助您追蹤活動相關的特定來源，尤其是您自訂的來源。</span><span class="sxs-lookup"><span data-stu-id="682f8-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="682f8-119">您也可以使用這讓您專注於來自感應器未設定為自動封鎖惡意活動或元件的提醒。</span><span class="sxs-lookup"><span data-stu-id="682f8-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![裝置警示偵測來源卡](../media/security-docs/device-alert-detection-sources.png)

<span data-ttu-id="682f8-121">從這個卡，您可以檢視 Microsoft defender 資訊安全中心入口網站的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="682f8-121">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="682f8-122">了解觸發警示的威脅的類型</span><span class="sxs-lookup"><span data-stu-id="682f8-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="682f8-123">Microsoft Defender ATP 排序每個提醒到類別，代表特定階段的攻擊鏈結] 或 [威脅元件的類型。</span><span class="sxs-lookup"><span data-stu-id="682f8-123">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="682f8-124">例如，偵測到威脅活動可能分類為 「 側面移動 」 以指出活動牽涉到嘗試連線到網路上的其他裝置，且可能發生之後攻擊者獲得了初始據點。</span><span class="sxs-lookup"><span data-stu-id="682f8-124">For example, detected threat activity might be categorized into “lateral movement” to indicate that the activity involved an attempt to reach other devices on the network and has likely occurred after attackers have gained an initial foothold.</span></span> <span data-ttu-id="682f8-125">當偵測到，威脅元件可能可以歸類廣泛作為 「 惡意軟體 」 或更明確地說 「 勒索軟體 」、 「 認證竊取 」 或其他類型的惡意或不必要的軟體。</span><span class="sxs-lookup"><span data-stu-id="682f8-125">When detected, a threat component might either be classified broadly as “malware” or more specifically as “ransomware”, “credential stealing” or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="682f8-126">**裝置威脅類別**卡片顯示提醒的散佈，分為下列類別。</span><span class="sxs-lookup"><span data-stu-id="682f8-126">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="682f8-127">您可以使用這項資訊來識別威脅活動，例如認證竊取，可以有多大的影響例如相較於社交，嘗試的嘗試。</span><span class="sxs-lookup"><span data-stu-id="682f8-127">You can use this information to identify threat activity, such as attempts at credential theft, which can have more significant impact compared to attempts at social engineering, for example.</span></span> <span data-ttu-id="682f8-128">您也可以使用這要監視之可能破壞性的威脅，如勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="682f8-128">You can also use this to monitor for potentially destructive threats like ransomware.</span></span>

![裝置威脅類別卡](../media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="682f8-130">監視作用中警示</span><span class="sxs-lookup"><span data-stu-id="682f8-130">Monitor active alerts</span></span>

<span data-ttu-id="682f8-131">**裝置警示狀態**卡片會指出未解決，可能需要加以留意的提醒數目。</span><span class="sxs-lookup"><span data-stu-id="682f8-131">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="682f8-132">從這個卡，您可以檢視 Microsoft defender 資訊安全中心入口網站的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="682f8-132">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![裝置警示狀態卡片](../media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="682f8-134">解決的警示的監視器分類</span><span class="sxs-lookup"><span data-stu-id="682f8-134">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="682f8-135">時，解決 Microsoft Defender ATP 警示，您的安全性人員可以指定警示是否已經驗證為：</span><span class="sxs-lookup"><span data-stu-id="682f8-135">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="682f8-136">識別實際資料外洩活動或威脅元件，則為 true 警示</span><span class="sxs-lookup"><span data-stu-id="682f8-136">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="682f8-137">不正確地偵測到一般活動，則為 false 提醒</span><span class="sxs-lookup"><span data-stu-id="682f8-137">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="682f8-138">**裝置警示分類**卡片顯示是否有已解決的警示歸類為 true 或 false 的提醒。</span><span class="sxs-lookup"><span data-stu-id="682f8-138">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="682f8-139">從這個卡，您可以檢視 Microsoft defender 資訊安全中心入口網站的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="682f8-139">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="682f8-140">附註： 在某些情況下，分類資訊則無法使用某些警示。</span><span class="sxs-lookup"><span data-stu-id="682f8-140">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![裝置警示分類卡片](../media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="682f8-142">監視判定的解析提醒</span><span class="sxs-lookup"><span data-stu-id="682f8-142">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="682f8-143">除了來分類是否警示，則為 true 或 false 解析期間，您的安全性人員可以提供決定，指出找不到驗證警示時的一般或惡意活動的類型。</span><span class="sxs-lookup"><span data-stu-id="682f8-143">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="682f8-144">**裝置警示判斷**卡片顯示特別是在每個警示所提供的決定：</span><span class="sxs-lookup"><span data-stu-id="682f8-144">The **Device alert determination** card shows the determination provided for each alert, specifically:</span></span>

* <span data-ttu-id="682f8-145">**APT** – 進階持續性威脅，指出偵測到的活動或威脅元件設計用來取得在受影響的網路據點複雜資料外洩的一部分</span><span class="sxs-lookup"><span data-stu-id="682f8-145">**APT** – advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="682f8-146">**惡意程式碼**– 惡意檔案或程式碼</span><span class="sxs-lookup"><span data-stu-id="682f8-146">**Malware** – malicious file or code</span></span>
* <span data-ttu-id="682f8-147">**安全性人員**– 安全性人員所執行的一般活動</span><span class="sxs-lookup"><span data-stu-id="682f8-147">**Security personnel** – normal activity performed by security staff</span></span>
* <span data-ttu-id="682f8-148">**安全性測試**– 活動或元件為了模擬實際威脅及預期會觸發安全性感應器並產生警示</span><span class="sxs-lookup"><span data-stu-id="682f8-148">**Security testing** – activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="682f8-149">**不必要的軟體**– 應用程式和其他軟體，不會視為惡意，但否則違反原則或可接受的使用標準</span><span class="sxs-lookup"><span data-stu-id="682f8-149">**Unwanted software** – apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="682f8-150">**其他人**– 未落在提供的類型] 下的任何其他判斷</span><span class="sxs-lookup"><span data-stu-id="682f8-150">**Others** – any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="682f8-151">您可以從這個卡片，來檢視 Microsoft defender 資訊安全中心的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="682f8-151">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![裝置警示判斷卡片](../media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="682f8-153">了解哪些裝置面臨的風險</span><span class="sxs-lookup"><span data-stu-id="682f8-153">Understand which devices are at risk</span></span>

<span data-ttu-id="682f8-154">**裝置保護**顯示裝置的風險層級。</span><span class="sxs-lookup"><span data-stu-id="682f8-154">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="682f8-155">風險層級依據因素影響，例如類型和裝置上有警示的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="682f8-155">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![裝置保護卡片](../media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="682f8-157">監視和報告 Intune 管理的裝置狀態</span><span class="sxs-lookup"><span data-stu-id="682f8-157">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="682f8-158">下列報告包含在 Intune 中註冊的裝置中的資料。</span><span class="sxs-lookup"><span data-stu-id="682f8-158">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="682f8-159">從 unenrolled 裝置資料並不包含在內。</span><span class="sxs-lookup"><span data-stu-id="682f8-159">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="682f8-160">只有全域系統管理員可以檢視這些卡片。</span><span class="sxs-lookup"><span data-stu-id="682f8-160">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="682f8-161">Intune 中註冊的裝置資料，包括：</span><span class="sxs-lookup"><span data-stu-id="682f8-161">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="682f8-162">裝置合規性</span><span class="sxs-lookup"><span data-stu-id="682f8-162">Device compliance</span></span>
* <span data-ttu-id="682f8-163">使用作用中的惡意程式碼的裝置</span><span class="sxs-lookup"><span data-stu-id="682f8-163">Devices with active malware</span></span>
* <span data-ttu-id="682f8-164">類型的裝置上的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="682f8-164">Types of malware on devices</span></span>
* <span data-ttu-id="682f8-165">在裝置上的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="682f8-165">Malware on devices</span></span>
* <span data-ttu-id="682f8-166">裝置與惡意程式碼偵測</span><span class="sxs-lookup"><span data-stu-id="682f8-166">Devices with malware detections</span></span>
* <span data-ttu-id="682f8-167">使用者與惡意程式碼偵測</span><span class="sxs-lookup"><span data-stu-id="682f8-167">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="682f8-168">監視裝置相容性</span><span class="sxs-lookup"><span data-stu-id="682f8-168">Monitor device compliance</span></span>

<span data-ttu-id="682f8-169">**裝置合規性**顯示多少部裝置，在 Intune 中註冊遵守設定原則。</span><span class="sxs-lookup"><span data-stu-id="682f8-169">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![裝置合規性卡片](../media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="682f8-171">探索裝置與惡意程式碼偵測</span><span class="sxs-lookup"><span data-stu-id="682f8-171">Discover devices with malware detections</span></span>

<span data-ttu-id="682f8-172">**裝置惡意程式碼偵測**提供與惡意程式碼尚未到期，以擱置動作完整解析的 Intune 註冊裝置的數目 — 重新啟動、 完整掃描或手動使用者動作，或如果未成功完成的補救動作。</span><span class="sxs-lookup"><span data-stu-id="682f8-172">**Device malware detections** provides the number of Intune enrolled devices with malware that have not been fully resolved due to pending actions—a restart, a full scan or manual user actions—or if the remediation action did not complete successfully.</span></span>

![裝置惡意程式碼偵測卡](../media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="682f8-174">了解偵測到的惡意程式碼的類型</span><span class="sxs-lookup"><span data-stu-id="682f8-174">Understand the types of malware detected</span></span>

<span data-ttu-id="682f8-175">**類型的裝置上的惡意程式碼**會顯示不同種類的惡意程式碼，已偵測到在 Intune 中註冊的裝置上。</span><span class="sxs-lookup"><span data-stu-id="682f8-175">**Types of malware on devices** shows different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="682f8-176">您可以檢查 Microsoft 365 安全性中心中的每個類型。</span><span class="sxs-lookup"><span data-stu-id="682f8-176">You can investigate each type in Microsoft 365 security center.</span></span>

![在 [裝置] 卡片上的惡意程式碼的類型](../media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="682f8-178">了解您的裝置上偵測到的特定惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="682f8-178">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="682f8-179">**在裝置上的惡意程式碼**提供特定的惡意程式碼偵測到您的裝置上的清單。</span><span class="sxs-lookup"><span data-stu-id="682f8-179">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![在 [裝置] 卡片上的惡意程式碼](../media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="682f8-181">了解哪些裝置有最多惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="682f8-181">Understand which devices have the most malware</span></span>

<span data-ttu-id="682f8-182">**惡意程式碼偵測裝置**顯示哪些裝置具有最多惡意程式碼偵測的資訊。</span><span class="sxs-lookup"><span data-stu-id="682f8-182">**Devices with malware detections** shows which devices have the most malware detections.</span></span> <span data-ttu-id="682f8-183">在 Microsoft 365 安全性管理中心中，您可以調查惡意程式碼是否為作用中，使用 Intune 中的裝置，以及其管理狀態的人員。</span><span class="sxs-lookup"><span data-stu-id="682f8-183">In Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![惡意程式碼偵測卡的裝置](../media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="682f8-185">了解哪些使用者必須具有最多惡意程式碼的裝置</span><span class="sxs-lookup"><span data-stu-id="682f8-185">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="682f8-186">**使用惡意程式碼偵測使用者**顯示的使用者與有大部分的惡意程式碼偵測的裝置。</span><span class="sxs-lookup"><span data-stu-id="682f8-186">**Users with malware detections** shows users with devices that had the most malware detections.</span></span> <span data-ttu-id="682f8-187">在 Microsoft 365 安全中心，您可以看到多少部裝置會指派給每位使用者及每個裝置和惡意程式碼的類型的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="682f8-187">In Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![使用者與惡意程式碼偵測卡](../media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="682f8-189">監控及管理 ASR 規則部署與偵測</span><span class="sxs-lookup"><span data-stu-id="682f8-189">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="682f8-190">[攻擊面縮減 (ASR) 規則](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)協助防止動作和通常由惡意探索搜尋惡意程式碼用來感染機器的應用程式。</span><span class="sxs-lookup"><span data-stu-id="682f8-190">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) help prevent actions and apps that are typically used by exploit-seeking malware to infect machines.</span></span> <span data-ttu-id="682f8-191">這些規則會控制何時和如何執行可執行檔。</span><span class="sxs-lookup"><span data-stu-id="682f8-191">These rules control when and how executables can run.</span></span> <span data-ttu-id="682f8-192">例如，您可以防止 JavaScript 或 VBScript 啟動已下載的可執行檔，封鎖來自 Office 巨集、 Win32 API 呼叫或封鎖程序的執行從 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="682f8-192">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![攻擊面縮減卡](../media/security-docs/attack-surface-reduction-rules.png)

<span data-ttu-id="682f8-194">**攻擊縮減規則**卡在裝置提供的規則部署的概觀。</span><span class="sxs-lookup"><span data-stu-id="682f8-194">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="682f8-195">卡片上的上方列顯示下列部署模式中的裝置總數：</span><span class="sxs-lookup"><span data-stu-id="682f8-195">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="682f8-196">**封鎖模式**– 與至少一個規則設定為封鎖偵測到活動的裝置</span><span class="sxs-lookup"><span data-stu-id="682f8-196">**Block mode** – devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="682f8-197">**稽核模式**– 具有任何規則的裝置設定為偵測到的封鎖活動，但有至少一個規則設定為偵測到的稽核活動</span><span class="sxs-lookup"><span data-stu-id="682f8-197">**Audit mode** – devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="682f8-198">**關閉**– 裝置已關閉的所有 ASR 規則</span><span class="sxs-lookup"><span data-stu-id="682f8-198">**Off** – devices with all ASR rules turned off</span></span>

<span data-ttu-id="682f8-199">這個介面卡的下半部會顯示在裝置規則的設定。</span><span class="sxs-lookup"><span data-stu-id="682f8-199">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="682f8-200">每一列會指出設定為 [封鎖] 或 [稽核偵測或已完全關閉規則的裝置的數目。</span><span class="sxs-lookup"><span data-stu-id="682f8-200">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="682f8-201">檢視 ASR 偵測</span><span class="sxs-lookup"><span data-stu-id="682f8-201">View ASR detections</span></span>

<span data-ttu-id="682f8-202">若要檢視您的網路 ASR 規則偵測的詳細的資訊，請**攻擊縮減規則**卡上選取 [**檢視偵測的資訊**。</span><span class="sxs-lookup"><span data-stu-id="682f8-202">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="682f8-203">在 [詳細資料報告] 頁面的 [**偵測的資訊**] 索引標籤會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="682f8-203">The **Detections** tab in the detailed report page will open.</span></span>

![偵測的資訊] 索引標籤](../media/security-docs/detections-tab.png)

<span data-ttu-id="682f8-205">在頁面頂端的圖表顯示偵測透過時間堆疊偵測已封鎖或稽核。</span><span class="sxs-lookup"><span data-stu-id="682f8-205">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="682f8-206">在底部表列出最近偵測的資訊。</span><span class="sxs-lookup"><span data-stu-id="682f8-206">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="682f8-207">若要了解性質的偵測，在資料表上使用下列資訊：</span><span class="sxs-lookup"><span data-stu-id="682f8-207">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="682f8-208">**偵測到檔案**– 檔案、 通常指令碼或文件，其內容觸發疑似的攻擊活動</span><span class="sxs-lookup"><span data-stu-id="682f8-208">**Detected file** – the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="682f8-209">**規則**– 描述規則設計來攔截攻擊活動名稱。</span><span class="sxs-lookup"><span data-stu-id="682f8-209">**Rule** – name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="682f8-210">了解現有 ASR 規則</span><span class="sxs-lookup"><span data-stu-id="682f8-210">Read about existing ASR rules</span></span>
* <span data-ttu-id="682f8-211">**來源應用程式**– 之應用程式的已載入或執行觸發疑似的攻擊活動的內容。</span><span class="sxs-lookup"><span data-stu-id="682f8-211">**Source app** – the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="682f8-212">這可能是合法的應用程式，例如網頁瀏覽器、 Office 應用程式或像是 PowerShell 系統工具</span><span class="sxs-lookup"><span data-stu-id="682f8-212">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="682f8-213">**Publisher** – 發行來源應用程式的廠商</span><span class="sxs-lookup"><span data-stu-id="682f8-213">**Publisher** – the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="682f8-214">檢閱裝置 ASR 規則設定</span><span class="sxs-lookup"><span data-stu-id="682f8-214">Review device ASR rule settings</span></span>

<span data-ttu-id="682f8-215">在 [**攻擊縮減規則**報告] 頁面上，移至 [檢閱規則設定為個別的裝置**組態**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="682f8-215">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="682f8-216">選取裝置以取得每個規則是否處於封鎖模式、 稽核模式，或完全關閉的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="682f8-216">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![組態] 索引標籤](../media/security-docs/configuration-tab.png)

<span data-ttu-id="682f8-218">Microsoft Intune 提供 ASR 規則的管理功能。</span><span class="sxs-lookup"><span data-stu-id="682f8-218">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="682f8-219">如果您想要更新您的設定，選取 [**設定裝置**] 下的 [**快速入門**中開啟在 Intune 裝置管理] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="682f8-219">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="682f8-220">從 ASR 規則排除檔案</span><span class="sxs-lookup"><span data-stu-id="682f8-220">Exclude files from ASR rules</span></span>

<span data-ttu-id="682f8-221">Microsoft 365 安全性中心攻擊縮減規則所偵測從收集[您可能想要排除的檔案](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive)的名稱。</span><span class="sxs-lookup"><span data-stu-id="682f8-221">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="682f8-222">藉由排除檔案，您可以減少誤判，則為 false 會偵測的資訊及更多充滿部署攻擊縮減規則以封鎖模式。</span><span class="sxs-lookup"><span data-stu-id="682f8-222">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="682f8-223">排除項目管理在 Microsoft Intune，但是 Microsoft 365 安全性中心 」 會提供分析工具可協助您了解檔案。</span><span class="sxs-lookup"><span data-stu-id="682f8-223">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="682f8-224">若要開始收集排除的檔案，請前往**攻擊縮減規則**報告] 頁面上的 [**新增排除項目**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="682f8-224">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="682f8-225">此工具會分析偵測所有攻擊縮減規則，但[僅部分規則支援排除項目](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="682f8-225">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules).</span></span>

![新增排除項目] 索引標籤](../media/security-docs/add-exclusions-tab.png)

<span data-ttu-id="682f8-227">資料表會列出您攻擊縮減規則所偵測到的所有檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="682f8-227">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="682f8-228">您可以選取檢視的排除這些影響的檔案：</span><span class="sxs-lookup"><span data-stu-id="682f8-228">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="682f8-229">多少較少的偵測</span><span class="sxs-lookup"><span data-stu-id="682f8-229">How many fewer detections</span></span>
* <span data-ttu-id="682f8-230">多少較少的裝置報告偵測</span><span class="sxs-lookup"><span data-stu-id="682f8-230">How many fewer devices report the detections</span></span>

<span data-ttu-id="682f8-231">若要排除選取其完整路徑與檔案的清單，請選取 [**取得排除的路徑**。</span><span class="sxs-lookup"><span data-stu-id="682f8-231">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="682f8-232">ASR 規則**封鎖認證竊取從 Windows 本機安全性授權子系統 (lsass.exe)** 的記錄檔擷取來源應用程式**lsass.exe**，一般系統檔案，以偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="682f8-232">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**, a normal system file, as the detected file.</span></span> <span data-ttu-id="682f8-233">因此，排除路徑產生的清單會包含此檔案。</span><span class="sxs-lookup"><span data-stu-id="682f8-233">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="682f8-234">若要排除觸發此規則，而不是**lsass.exe**檔案，請使用來源應用程式的路徑而不是偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="682f8-234">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="682f8-235">若要找出來源應用程式，請執行下列[進階的狩獵查詢](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)（由規則 ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 識別） 此特定規則：</span><span class="sxs-lookup"><span data-stu-id="682f8-235">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="682f8-236">檢查排除的檔案</span><span class="sxs-lookup"><span data-stu-id="682f8-236">Check files for exclusion</span></span>
<span data-ttu-id="682f8-237">之前 ASR 從排除檔案，我們建議您檢查來決定它是否確實不惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="682f8-237">Before excluding a file from ASR, we recommend that you inspect the file to determine if it is indeed not malicious.</span></span>

<span data-ttu-id="682f8-238">若要檢閱檔案，使用[檔案資訊] 頁面](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files)上 Microsoft defender 資訊安全中心。</span><span class="sxs-lookup"><span data-stu-id="682f8-238">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="682f8-239">[] 頁面上提供普遍性資訊作為 VirusTotal 防毒偵測比率。</span><span class="sxs-lookup"><span data-stu-id="682f8-239">The page provides prevalence information as well as the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="682f8-240">您也可以使用] 頁面上，以提交深入分析的檔案。</span><span class="sxs-lookup"><span data-stu-id="682f8-240">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="682f8-241">若要在 Microsoft defender 資訊安全中心尋找偵測到的檔案，搜尋所有 ASR 偵測使用下列的進階的狩獵查詢：</span><span class="sxs-lookup"><span data-stu-id="682f8-241">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="682f8-242">使用檔案使用中 Microsoft defender 資訊安全中心萬用搜尋列來搜尋**SHA1**或**InitiatingProcessSHA1**在結果中。</span><span class="sxs-lookup"><span data-stu-id="682f8-242">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
