---
title: 管理 Microsoft Defender 防毒軟體更新及套用基準
description: 管理 Microsoft Defender 防毒軟體如何接收保護和產品更新。
keywords: 更新，安全性基準，保護，排程更新，強制更新，行動更新，wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/04/2021
ms.openlocfilehash: 264a3b7a4a24c446048d6cfc6863f1ae9765566f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789180"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="393a4-104">管理 Microsoft Defender 防毒軟體更新及套用基準</span><span class="sxs-lookup"><span data-stu-id="393a4-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="393a4-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="393a4-105">**Applies to:**</span></span>

- [<span data-ttu-id="393a4-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="393a4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="393a4-107">Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="393a4-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="393a4-108">有兩種與 Microsoft Defender 防毒軟體保持最新狀態相關的更新：</span><span class="sxs-lookup"><span data-stu-id="393a4-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="393a4-109">安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="393a4-109">Security intelligence updates</span></span>
- <span data-ttu-id="393a4-110">產品更新</span><span class="sxs-lookup"><span data-stu-id="393a4-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="393a4-111">將 Microsoft Defender 防毒軟體保持在最新狀態，是確保您的裝置具備防範新惡意程式碼和攻擊技巧所需的最新技術和功能。</span><span class="sxs-lookup"><span data-stu-id="393a4-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="393a4-112">即使在[被動模式下](./microsoft-defender-antivirus-compatibility.md)執行 Microsoft Defender 防毒軟體，也請務必更新防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="393a4-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="393a4-113">若要查看最新的引擎、平臺及簽章日期，請流覽[Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體的安全性情報更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="393a4-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="393a4-114">安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="393a4-114">Security intelligence updates</span></span>

<span data-ttu-id="393a4-115">Microsoft Defender 防毒軟體使用[雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md) (也稱為 Microsoft Advanced protection 服務或對應) ，定期下載安全性情報更新，以提供保護。</span><span class="sxs-lookup"><span data-stu-id="393a4-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="393a4-116">更新會在下列 KB 編號之下發行：</span><span class="sxs-lookup"><span data-stu-id="393a4-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="393a4-117">Microsoft Defender 防毒軟體： KB2267602</span><span class="sxs-lookup"><span data-stu-id="393a4-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="393a4-118">System Center Endpoint Protection： KB2461484</span><span class="sxs-lookup"><span data-stu-id="393a4-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="393a4-119">雲端傳送保護功能永遠都是開啟的，且需要網際網路連線才能運作。</span><span class="sxs-lookup"><span data-stu-id="393a4-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="393a4-120">安全智慧更新會在排程的節奏上進行， (可透過原則) 設定。</span><span class="sxs-lookup"><span data-stu-id="393a4-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="393a4-121">如需詳細資訊，請參閱[在 Microsoft Defender 防毒軟體中使用 Microsoft 雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="393a4-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="393a4-122">如需最近的安全性情報更新清單，請參閱[Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體的安全性情報更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="393a4-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="393a4-123">引擎更新包含在安全性智慧更新中，並以每月的節奏發行。</span><span class="sxs-lookup"><span data-stu-id="393a4-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="393a4-124">產品更新</span><span class="sxs-lookup"><span data-stu-id="393a4-124">Product updates</span></span>

<span data-ttu-id="393a4-125">Microsoft Defender 防毒軟體需要 [每月更新 (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (稱為 *平臺更新*) ，而且會在 Windows 10 版本的情況下收到重要的功能更新。</span><span class="sxs-lookup"><span data-stu-id="393a4-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="393a4-126">您可以透過下列其中一種方法來管理更新的發佈：</span><span class="sxs-lookup"><span data-stu-id="393a4-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="393a4-127">Windows伺服器更新服務 (WSUS) </span><span class="sxs-lookup"><span data-stu-id="393a4-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="393a4-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="393a4-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="393a4-129">您用來部署 Microsoft 和 Windows 網路中端點更新的常用方法。</span><span class="sxs-lookup"><span data-stu-id="393a4-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="393a4-130">如需詳細資訊，請參閱[管理來源以取得 Microsoft Defender 防毒軟體保護更新](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="393a4-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="393a4-131">每月更新都會以階段發行，導致您的 [視窗伺服器更新服務](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)中顯示多個套件。</span><span class="sxs-lookup"><span data-stu-id="393a4-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="393a4-132">每月平臺及引擎版本</span><span class="sxs-lookup"><span data-stu-id="393a4-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="393a4-133">如需如何更新或安裝平臺更新的資訊，請參閱[Windows Defender 的反惡意程式碼平臺更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="393a4-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="393a4-134">我們所有的更新均包含</span><span class="sxs-lookup"><span data-stu-id="393a4-134">All our updates contain</span></span> 
- <span data-ttu-id="393a4-135">效能改進;</span><span class="sxs-lookup"><span data-stu-id="393a4-135">performance improvements;</span></span>
- <span data-ttu-id="393a4-136">可維護性改進;和</span><span class="sxs-lookup"><span data-stu-id="393a4-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="393a4-137"> (Cloud Microsoft 365 Defender) 的整合增強功能。</span><span class="sxs-lookup"><span data-stu-id="393a4-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="393a4-138">2021年5月 (平臺： 4.18.2105.4 |Engine： 1.1.18200.4) </span><span class="sxs-lookup"><span data-stu-id="393a4-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="393a4-139">&ensp;安全性智慧更新版本： **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="393a4-140">&ensp;發行日期： **2021 年6月4日**</span><span class="sxs-lookup"><span data-stu-id="393a4-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="393a4-141">&ensp;Platform： **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="393a4-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="393a4-142">&ensp;Engine： **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="393a4-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="393a4-143">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="393a4-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-144">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-144">What's new</span></span>
- <span data-ttu-id="393a4-145">行為監控的增強功能</span><span class="sxs-lookup"><span data-stu-id="393a4-145">Improvements to behavior monitoring</span></span> 

### <a name="known-issues"></a><span data-ttu-id="393a4-146">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-146">Known Issues</span></span>
<span data-ttu-id="393a4-147">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-147">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="393a4-148">四月-2021 (平臺： 4.18.2104.14 |Engine： 1.1.18100.5) </span><span class="sxs-lookup"><span data-stu-id="393a4-148">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="393a4-149">&ensp;安全性智慧更新版本： **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-149">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="393a4-150">&ensp;發行日期： **2021 年4月1日**</span><span class="sxs-lookup"><span data-stu-id="393a4-150">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="393a4-151">&ensp;Platform： **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="393a4-151">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="393a4-152">&ensp;Engine： **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="393a4-153">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="393a4-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-154">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-154">What's new</span></span>
- <span data-ttu-id="393a4-155">其他行為監控邏輯</span><span class="sxs-lookup"><span data-stu-id="393a4-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="393a4-156">改進的核心模式 keylogger 偵測</span><span class="sxs-lookup"><span data-stu-id="393a4-156">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="393a4-157">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-157">Known Issues</span></span>
<span data-ttu-id="393a4-158">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-158">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="393a4-159">三月份-2021 (平臺： 4.18.2103.7 |Engine： 1.1.18000.5) </span><span class="sxs-lookup"><span data-stu-id="393a4-159">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="393a4-160">&ensp;安全性智慧更新版本： **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-160">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="393a4-161">&ensp;發行日期： **2021 年4月1日**</span><span class="sxs-lookup"><span data-stu-id="393a4-161">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="393a4-162">&ensp;Platform： **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="393a4-162">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="393a4-163">&ensp;Engine： **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-163">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="393a4-164">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="393a4-164">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-165">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-165">What's new</span></span>

- <span data-ttu-id="393a4-166">改進行為監控引擎</span><span class="sxs-lookup"><span data-stu-id="393a4-166">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="393a4-167">擴充網路暴力攻擊緩解</span><span class="sxs-lookup"><span data-stu-id="393a4-167">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="393a4-168">啟用 [防篡改保護](prevent-changes-to-security-settings-with-tamper-protection.md) 時，其他失敗的篡改嘗試事件產生</span><span class="sxs-lookup"><span data-stu-id="393a4-168">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="393a4-169">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-169">Known Issues</span></span>
<span data-ttu-id="393a4-170">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-170">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="393a4-171">舊版本更新：僅限技術升級支援</span><span class="sxs-lookup"><span data-stu-id="393a4-171">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="393a4-172">發行新的套件版本之後，支援舊版的兩個版本只會縮小為技術支援。</span><span class="sxs-lookup"><span data-stu-id="393a4-172">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="393a4-173">這一節所列出的版本舊，僅提供支援技術升級。</span><span class="sxs-lookup"><span data-stu-id="393a4-173">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="393a4-174">二月份-2021 (平臺： 4.18.2102.3 |Engine： 1.1.17900.7) </span><span class="sxs-lookup"><span data-stu-id="393a4-174">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="393a4-175">&ensp;安全性智慧更新版本： **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-175">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="393a4-176">&ensp;發行日期： **2021 年3月9日**</span><span class="sxs-lookup"><span data-stu-id="393a4-176">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="393a4-177">&ensp;Platform： **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="393a4-177">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="393a4-178">&ensp;Engine： **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="393a4-178">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="393a4-179">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-179">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-180">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-180">What's new</span></span>

- <span data-ttu-id="393a4-181">透過[防篡改保護](prevent-changes-to-security-settings-with-tamper-protection.md)改進服務復原</span><span class="sxs-lookup"><span data-stu-id="393a4-181">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="393a4-182">擴充不可篡改的保護範圍</span><span class="sxs-lookup"><span data-stu-id="393a4-182">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="393a4-183">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-183">Known Issues</span></span>
<span data-ttu-id="393a4-184">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-184">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="393a4-185">2021年1月 (平臺： 4.18.2101.9 |Engine： 1.1.17800.5) </span><span class="sxs-lookup"><span data-stu-id="393a4-185">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="393a4-186">&ensp;安全性智慧更新版本： **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-186">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="393a4-187">&ensp;發行日期： **2021 年2月2日**</span><span class="sxs-lookup"><span data-stu-id="393a4-187">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="393a4-188">&ensp;Platform： **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="393a4-188">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="393a4-189">&ensp;Engine： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-189">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="393a4-190">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-190">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-191">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-191">What's new</span></span>

- <span data-ttu-id="393a4-192">外殼代碼利用偵測增強功能</span><span class="sxs-lookup"><span data-stu-id="393a4-192">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="393a4-193">增強認證竊取嘗試的知名度</span><span class="sxs-lookup"><span data-stu-id="393a4-193">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="393a4-194">Microsoft Defender 防毒軟體服務中的 antitampering 功能的增強功能</span><span class="sxs-lookup"><span data-stu-id="393a4-194">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="393a4-195">改進支援 ARM x64 模擬</span><span class="sxs-lookup"><span data-stu-id="393a4-195">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="393a4-196">修正：在即時保護執行初始偵測後，威脅史中仍會保留 EDR 封鎖通知</span><span class="sxs-lookup"><span data-stu-id="393a4-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="393a4-197">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-197">Known Issues</span></span>
<span data-ttu-id="393a4-198">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="393a4-199">11月-2020 (平臺： 4.18.2011.6 |Engine： 1.1.17700.4) </span><span class="sxs-lookup"><span data-stu-id="393a4-199">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="393a4-200">&ensp;安全性智慧更新版本： **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-200">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="393a4-201">&ensp;發行日期： **2020 年12月**</span><span class="sxs-lookup"><span data-stu-id="393a4-201">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="393a4-202">&ensp;Platform： **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="393a4-202">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="393a4-203">&ensp;Engine： **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="393a4-203">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="393a4-204">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-205">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-205">What's new</span></span>

- <span data-ttu-id="393a4-206">改進的 [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 狀態支援記錄</span><span class="sxs-lookup"><span data-stu-id="393a4-206">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="393a4-207">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-207">Known Issues</span></span>
<span data-ttu-id="393a4-208">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-208">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="393a4-209">十月-2020 (平臺： 4.18.2010.7 |Engine： 1.1.17600.5) </span><span class="sxs-lookup"><span data-stu-id="393a4-209">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="393a4-210">&ensp;安全性智慧更新版本： **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-210">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="393a4-211">&ensp;發行日期： **2020 年10月29日**</span><span class="sxs-lookup"><span data-stu-id="393a4-211">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="393a4-212">&ensp;Platform： **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="393a4-212">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="393a4-213">&ensp;Engine： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-213">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="393a4-214">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-214">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-215">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-215">What's new</span></span>

- <span data-ttu-id="393a4-216">特殊威脅類別的新描述</span><span class="sxs-lookup"><span data-stu-id="393a4-216">New descriptions for special threat categories</span></span>
- <span data-ttu-id="393a4-217">改進模擬功能</span><span class="sxs-lookup"><span data-stu-id="393a4-217">Improved emulation capabilities</span></span>
- <span data-ttu-id="393a4-218">改進的主機位址允許/封鎖功能</span><span class="sxs-lookup"><span data-stu-id="393a4-218">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="393a4-219">在 Defender CSP 中新增選項，以忽略本機使用者排除的合併</span><span class="sxs-lookup"><span data-stu-id="393a4-219">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="393a4-220">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-220">Known Issues</span></span>

<span data-ttu-id="393a4-221">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-221">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="393a4-222">九月份-2020 (平臺： 4.18.2009.7 |Engine： 1.1.17500.4) </span><span class="sxs-lookup"><span data-stu-id="393a4-222">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="393a4-223">&ensp;安全性智慧更新版本： **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-223">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="393a4-224">&ensp;發行日期： **2020 年10月1日**</span><span class="sxs-lookup"><span data-stu-id="393a4-224">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="393a4-225">&ensp;Platform： **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="393a4-225">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="393a4-226">&ensp;Engine： **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="393a4-226">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="393a4-227">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-227">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-228">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-228">What's new</span></span>

- <span data-ttu-id="393a4-229">需要有系統管理員許可權，才能還原隔離中的檔案</span><span class="sxs-lookup"><span data-stu-id="393a4-229">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="393a4-230">現在支援 XML 格式化的事件</span><span class="sxs-lookup"><span data-stu-id="393a4-230">XML formatted events are now supported</span></span>
- <span data-ttu-id="393a4-231">用於忽略排除合併的 CSP 支援</span><span class="sxs-lookup"><span data-stu-id="393a4-231">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="393a4-232">下列專案的新管理介面：</span><span class="sxs-lookup"><span data-stu-id="393a4-232">New management interfaces for:</span></span>
   - <span data-ttu-id="393a4-233">UDP 檢查</span><span class="sxs-lookup"><span data-stu-id="393a4-233">UDP Inspection</span></span>
   - <span data-ttu-id="393a4-234">伺服器2019上的網路保護</span><span class="sxs-lookup"><span data-stu-id="393a4-234">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="393a4-235">網路保護的 IP 位址排除</span><span class="sxs-lookup"><span data-stu-id="393a4-235">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="393a4-236">改善 TPM 測量的可見度</span><span class="sxs-lookup"><span data-stu-id="393a4-236">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="393a4-237">改進的 Office VBA 模組掃描</span><span class="sxs-lookup"><span data-stu-id="393a4-237">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="393a4-238">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-238">Known Issues</span></span>

<span data-ttu-id="393a4-239">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-239">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="393a4-240">八月-2020 (平臺： 4.18.2008.9 |Engine： 1.1.17400.5) </span><span class="sxs-lookup"><span data-stu-id="393a4-240">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="393a4-241">&ensp;安全性智慧更新版本： **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-241">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="393a4-242">&ensp;發行日期： **2020 年8月27日**</span><span class="sxs-lookup"><span data-stu-id="393a4-242">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="393a4-243">&ensp;Platform： **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="393a4-243">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="393a4-244">&ensp;Engine： **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-244">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="393a4-245">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-245">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="393a4-246">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-246">What's new</span></span>

- <span data-ttu-id="393a4-247">新增更多遙測事件</span><span class="sxs-lookup"><span data-stu-id="393a4-247">Add more telemetry events</span></span>
- <span data-ttu-id="393a4-248">改進的掃描事件遙測</span><span class="sxs-lookup"><span data-stu-id="393a4-248">Improved scan event telemetry</span></span>
- <span data-ttu-id="393a4-249">改進的記憶體掃描行為監控</span><span class="sxs-lookup"><span data-stu-id="393a4-249">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="393a4-250">改進的宏資料流程掃描</span><span class="sxs-lookup"><span data-stu-id="393a4-250">Improved macro streams scanning</span></span>
- <span data-ttu-id="393a4-251">新增 `AMRunningMode` 至 Get-MpComputerStatus PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="393a4-251">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="393a4-252">會忽略[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 。</span><span class="sxs-lookup"><span data-stu-id="393a4-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="393a4-253">Microsoft Defender 防毒軟體會在偵測其他防毒程式時自動開啟自身。</span><span class="sxs-lookup"><span data-stu-id="393a4-253">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="393a4-254">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-254">Known Issues</span></span>
<span data-ttu-id="393a4-255">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-255">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="393a4-256">2020年7月- (平臺： 4.18.2007.8 |Engine： 1.1.17300.4) </span><span class="sxs-lookup"><span data-stu-id="393a4-256">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="393a4-257">&ensp;安全性智慧更新版本： **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-257">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="393a4-258">&ensp;發行日期： **2020 年7月28日**</span><span class="sxs-lookup"><span data-stu-id="393a4-258">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="393a4-259">&ensp;Platform： **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="393a4-259">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="393a4-260">&ensp;Engine： **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="393a4-260">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="393a4-261">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-261">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-262">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-262">What's new</span></span>

- <span data-ttu-id="393a4-263">改進的遙測的 BITS</span><span class="sxs-lookup"><span data-stu-id="393a4-263">Improved telemetry for BITS</span></span>
- <span data-ttu-id="393a4-264">改進的驗證碼簽名憑證驗證</span><span class="sxs-lookup"><span data-stu-id="393a4-264">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="393a4-265">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-265">Known Issues</span></span>
<span data-ttu-id="393a4-266">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-266">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="393a4-267">六月-2020 (平臺： 4.18.2006.10 |Engine： 1.1.17200.2) </span><span class="sxs-lookup"><span data-stu-id="393a4-267">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="393a4-268">&ensp;安全性智慧更新版本： **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-268">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="393a4-269">&ensp;發行日期： **2020 年6月22日**</span><span class="sxs-lookup"><span data-stu-id="393a4-269">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="393a4-270">&ensp;Platform： **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="393a4-270">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="393a4-271">&ensp;Engine： **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="393a4-271">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="393a4-272">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-272">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-273">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-273">What's new</span></span>

- <span data-ttu-id="393a4-274">可能指定[支援記錄](./collect-diagnostic-data.md)檔的位置</span><span class="sxs-lookup"><span data-stu-id="393a4-274">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="393a4-275">在被動模式中略過積極 catchup 掃描。</span><span class="sxs-lookup"><span data-stu-id="393a4-275">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="393a4-276">允許 Defender 在流量計費的連線上更新</span><span class="sxs-lookup"><span data-stu-id="393a4-276">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="393a4-277">停用快取時的固定效能調整</span><span class="sxs-lookup"><span data-stu-id="393a4-277">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="393a4-278">固定登錄查詢</span><span class="sxs-lookup"><span data-stu-id="393a4-278">Fixed registry query</span></span> 
- <span data-ttu-id="393a4-279">ADMX 中的固定 scantime 隨機化</span><span class="sxs-lookup"><span data-stu-id="393a4-279">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="393a4-280">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-280">Known Issues</span></span>
<span data-ttu-id="393a4-281">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-281">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="393a4-282">2020年5月 (平臺： 4.18.2005.4 |Engine： 1.1.17100.2) </span><span class="sxs-lookup"><span data-stu-id="393a4-282">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="393a4-283">&ensp;安全性智慧更新版本： **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-283">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="393a4-284">&ensp;發行日期： **2020 年5月26日**</span><span class="sxs-lookup"><span data-stu-id="393a4-284">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="393a4-285">&ensp;Platform： **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="393a4-285">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="393a4-286">&ensp;Engine： **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="393a4-286">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="393a4-287">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-287">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-288">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-288">What's new</span></span>

- <span data-ttu-id="393a4-289">改進的掃描事件記錄</span><span class="sxs-lookup"><span data-stu-id="393a4-289">Improved logging for scan events</span></span>
- <span data-ttu-id="393a4-290">改進的使用者模式損毀處理。</span><span class="sxs-lookup"><span data-stu-id="393a4-290">Improved user mode crash handling.</span></span>
- <span data-ttu-id="393a4-291">新增防篡改保護的事件追蹤</span><span class="sxs-lookup"><span data-stu-id="393a4-291">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="393a4-292">修正 AMSI 範例提交</span><span class="sxs-lookup"><span data-stu-id="393a4-292">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="393a4-293">固定 AMSI Cloud 封鎖</span><span class="sxs-lookup"><span data-stu-id="393a4-293">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="393a4-294">修正的安全性更新安裝記錄檔</span><span class="sxs-lookup"><span data-stu-id="393a4-294">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="393a4-295">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-295">Known Issues</span></span>
<span data-ttu-id="393a4-296">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-296">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="393a4-297">四月-2020 (平臺： 4.18.2004.6 |Engine： 1.1.17000.2) </span><span class="sxs-lookup"><span data-stu-id="393a4-297">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="393a4-298">&ensp;安全性智慧更新版本： **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-298">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="393a4-299">&ensp;發行日期： **2020 年4月30日**</span><span class="sxs-lookup"><span data-stu-id="393a4-299">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="393a4-300">&ensp;Platform： **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="393a4-300">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="393a4-301">&ensp;Engine： **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="393a4-301">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="393a4-302">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-302">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-303">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-303">What's new</span></span>
- <span data-ttu-id="393a4-304">WDfilter 改進功能</span><span class="sxs-lookup"><span data-stu-id="393a4-304">WDfilter improvements</span></span>
- <span data-ttu-id="393a4-305">新增更具可操作性的事件資料至攻擊面減少偵測事件</span><span class="sxs-lookup"><span data-stu-id="393a4-305">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="393a4-306">診斷資料和 WMI 中的固定版本資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-306">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="393a4-307">在平臺更新後在 UI 中修復不正確的平臺版本</span><span class="sxs-lookup"><span data-stu-id="393a4-307">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="393a4-308">動態 URL intel for Fileless 威脅防護</span><span class="sxs-lookup"><span data-stu-id="393a4-308">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="393a4-309">UEFI 掃描功能</span><span class="sxs-lookup"><span data-stu-id="393a4-309">UEFI scan capability</span></span>
- <span data-ttu-id="393a4-310">擴充更新記錄</span><span class="sxs-lookup"><span data-stu-id="393a4-310">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="393a4-311">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-311">Known Issues</span></span>
<span data-ttu-id="393a4-312">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-312">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="393a4-313">三月份-2020 (平臺： 4.18.2003.8 |Engine： 1.1.16900.2) </span><span class="sxs-lookup"><span data-stu-id="393a4-313">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="393a4-314">&ensp;安全性智慧更新版本： **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-314">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="393a4-315">&ensp;發行日期： **2020 年3月24日**</span><span class="sxs-lookup"><span data-stu-id="393a4-315">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="393a4-316">&ensp;Platform： **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="393a4-316">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="393a4-317">&ensp;Engine： **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="393a4-317">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="393a4-318">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-318">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="393a4-319">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-319">What's new</span></span>

- <span data-ttu-id="393a4-320">新增至[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 節流選項</span><span class="sxs-lookup"><span data-stu-id="393a4-320">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="393a4-321">改善診斷功能</span><span class="sxs-lookup"><span data-stu-id="393a4-321">Improve diagnostic capability</span></span>
- <span data-ttu-id="393a4-322">降低安全性情報超時 (5 分鐘) </span><span class="sxs-lookup"><span data-stu-id="393a4-322">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="393a4-323">擴充 AMSI 引擎內部記錄功能</span><span class="sxs-lookup"><span data-stu-id="393a4-323">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="393a4-324">改進處理常式封鎖的通知</span><span class="sxs-lookup"><span data-stu-id="393a4-324">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="393a4-325">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-325">Known Issues</span></span>
<span data-ttu-id="393a4-326">[**Fixed**]Microsoft Defender 防毒軟體會在執行掃描時略過檔案。</span><span class="sxs-lookup"><span data-stu-id="393a4-326">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="393a4-327">二月份-2020 (平臺： |Engine： 1.1.16800.2) </span><span class="sxs-lookup"><span data-stu-id="393a4-327">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="393a4-328">&ensp;安全性智慧更新版本： **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="393a4-328">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="393a4-329">&ensp;發行日期： **2020 年2月25日**</span><span class="sxs-lookup"><span data-stu-id="393a4-329">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="393a4-330">&ensp;平臺/用戶端： **-**</span><span class="sxs-lookup"><span data-stu-id="393a4-330">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="393a4-331">&ensp;Engine： **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="393a4-331">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="393a4-332">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-332">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="393a4-333">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-333">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="393a4-334">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-334">Known Issues</span></span>
<span data-ttu-id="393a4-335">無已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-335">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="393a4-336">2020年1月 (平臺： 4.18.2001.10 |Engine： 1.1.16700.2) </span><span class="sxs-lookup"><span data-stu-id="393a4-336">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="393a4-337">安全性智慧更新版本： **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-337">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="393a4-338">發行日期： **2020 年1月30日**</span><span class="sxs-lookup"><span data-stu-id="393a4-338">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="393a4-339">Platform/Client： **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="393a4-339">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="393a4-340">Engine： **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="393a4-340">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="393a4-341">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="393a4-341">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="393a4-342">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-342">What's new</span></span>

- <span data-ttu-id="393a4-343">具有 Exchange 的 WS2016 上的固定 BSOD</span><span class="sxs-lookup"><span data-stu-id="393a4-343">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="393a4-344">當 TMP 重新導向至網路路徑時支援平臺更新</span><span class="sxs-lookup"><span data-stu-id="393a4-344">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="393a4-345">平臺和引擎版本已新增至 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="393a4-345">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="393a4-346">將緊急特徵碼更新擴充為 [被動模式](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="393a4-346">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="393a4-347">修正4.18.1911.3 懸掛</span><span class="sxs-lookup"><span data-stu-id="393a4-347">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="393a4-348">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-348">Known Issues</span></span>

<span data-ttu-id="393a4-349">[**Fixed**] 採用 [新式待機模式](/windows-hardware/design/device-experiences/modern-standby)的裝置可能會在 Windows Defender 篩選器驅動程式遇到中斷，從而導致保護的缺口。</span><span class="sxs-lookup"><span data-stu-id="393a4-349">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="393a4-350">受影響的機器會因尚未更新為最新的反惡意程式碼平臺而向客戶呈現。</span><span class="sxs-lookup"><span data-stu-id="393a4-350">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="393a4-351">此更新如下：</span><span class="sxs-lookup"><span data-stu-id="393a4-351">This update is:</span></span>
> - <span data-ttu-id="393a4-352">由執行低版本平臺的 RS1 裝置所需，以支援 SHA2;</span><span class="sxs-lookup"><span data-stu-id="393a4-352">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="393a4-353">具有懸掛問題的系統重新開機標誌;</span><span class="sxs-lookup"><span data-stu-id="393a4-353">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="393a4-354">會在4月2020內重新發佈，而且不會被更新的更新取代以保留未來的可用性;</span><span class="sxs-lookup"><span data-stu-id="393a4-354">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="393a4-355">因重新開機要求而分類為更新和</span><span class="sxs-lookup"><span data-stu-id="393a4-355">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="393a4-356">只會以[Windows 更新](https://support.microsoft.com/help/4027667/windows-10-update)提供。</span><span class="sxs-lookup"><span data-stu-id="393a4-356">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="393a4-357">11月-2019 (平臺： 4.18.1911.3 |Engine： 1.1.16600.7) </span><span class="sxs-lookup"><span data-stu-id="393a4-357">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="393a4-358">安全性智慧更新版本： **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-358">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="393a4-359">發行日期： **2019 月7日**</span><span class="sxs-lookup"><span data-stu-id="393a4-359">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="393a4-360">Platform： **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="393a4-360">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="393a4-361">Engine： **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="393a4-361">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="393a4-362">支援階段： **不支援**</span><span class="sxs-lookup"><span data-stu-id="393a4-362">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="393a4-363">新增功能</span><span class="sxs-lookup"><span data-stu-id="393a4-363">What's new</span></span>

- <span data-ttu-id="393a4-364">固定 MpCmdRun 追蹤層級</span><span class="sxs-lookup"><span data-stu-id="393a4-364">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="393a4-365">固定 WDFilter 版本資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-365">Fixed WDFilter version info</span></span>
- <span data-ttu-id="393a4-366"> (PUA) 提升通知</span><span class="sxs-lookup"><span data-stu-id="393a4-366">Improve notifications (PUA)</span></span>
- <span data-ttu-id="393a4-367">新增 MRT.LOG 記錄以支援檔案</span><span class="sxs-lookup"><span data-stu-id="393a4-367">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="393a4-368">已知問題</span><span class="sxs-lookup"><span data-stu-id="393a4-368">Known Issues</span></span>
<span data-ttu-id="393a4-369">安裝此更新時，裝置需要「跳過套件4.10.2001.10」才能更新為最新的平臺版本。</span><span class="sxs-lookup"><span data-stu-id="393a4-369">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="393a4-370">Microsoft Defender 防毒軟體平臺支援</span><span class="sxs-lookup"><span data-stu-id="393a4-370">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="393a4-371">平臺和引擎更新是以每月節奏提供。</span><span class="sxs-lookup"><span data-stu-id="393a4-371">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="393a4-372">若要完全支援，請使用最新的平臺更新來保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="393a4-372">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="393a4-373">我們的支援結構是動態的，而且會根據最新平臺版本的可用性而演變成兩個階段：</span><span class="sxs-lookup"><span data-stu-id="393a4-373">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="393a4-374">**安全性和重要更新服務階段** -執行最新的平臺版本時，您將有資格收到反惡意程式碼平臺的安全性和重要更新。</span><span class="sxs-lookup"><span data-stu-id="393a4-374">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="393a4-375">**僅限) 階段的技術支援 (** 。發行新的平臺版本之後，支援較舊版本 (n-1) 只會降低技術支援。</span><span class="sxs-lookup"><span data-stu-id="393a4-375">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="393a4-376">不再支援非 N-2 版本的平臺。</span><span class="sxs-lookup"><span data-stu-id="393a4-376">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="393a4-377">\*將繼續提供技術支援，以供從 Windows 10 發行版本本升級 (請參閱[Windows 10 版本隨附的平臺版本](#platform-version-included-with-windows-10-releases)) 至最新的平臺版本。</span><span class="sxs-lookup"><span data-stu-id="393a4-377">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="393a4-378">在技術支援 (只有) 階段，將會透過 Microsoft 客戶服務 & 支援和 Microsoft 受管理的支援服務， (例如 Premier Support) ，供應商業上合理的支援事件。</span><span class="sxs-lookup"><span data-stu-id="393a4-378">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="393a4-379">如果支援事件需要升級開發以取得進一步的指導方針、需要非安全性更新，或需要安全性更新，則系統會要求客戶升級至最新的平臺版本或中級更新 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="393a4-379">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="393a4-380">Windows 10 版本隨附的平臺版本</span><span class="sxs-lookup"><span data-stu-id="393a4-380">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="393a4-381">下表提供隨附于最新 Windows 10 版本的 Microsoft Defender 防毒軟體平臺和引擎版本：</span><span class="sxs-lookup"><span data-stu-id="393a4-381">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="393a4-382">Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="393a4-382">Windows 10 release</span></span>  |<span data-ttu-id="393a4-383">平臺版本</span><span class="sxs-lookup"><span data-stu-id="393a4-383">Platform version</span></span>  |<span data-ttu-id="393a4-384">引擎版本</span><span class="sxs-lookup"><span data-stu-id="393a4-384">Engine version</span></span> |<span data-ttu-id="393a4-385">支援階段</span><span class="sxs-lookup"><span data-stu-id="393a4-385">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="393a4-386">2004 (20H1/20H2) </span><span class="sxs-lookup"><span data-stu-id="393a4-386">2004  (20H1/20H2)</span></span> |<span data-ttu-id="393a4-387">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="393a4-387">4.18.1909.6</span></span> |<span data-ttu-id="393a4-388">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="393a4-388">1.1.17000.2</span></span> | <span data-ttu-id="393a4-389">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="393a4-389">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="393a4-390">1909 (19H2) </span><span class="sxs-lookup"><span data-stu-id="393a4-390">1909  (19H2)</span></span> |<span data-ttu-id="393a4-391">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="393a4-391">4.18.1902.5</span></span> |<span data-ttu-id="393a4-392">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="393a4-392">1.1.16700.3</span></span> | <span data-ttu-id="393a4-393">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="393a4-393">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="393a4-394">1903 (19H1) </span><span class="sxs-lookup"><span data-stu-id="393a4-394">1903  (19H1)</span></span> |<span data-ttu-id="393a4-395">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="393a4-395">4.18.1902.5</span></span> |<span data-ttu-id="393a4-396">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="393a4-396">1.1.15600.4</span></span> | <span data-ttu-id="393a4-397">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="393a4-397">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="393a4-398">1809 (RS5) </span><span class="sxs-lookup"><span data-stu-id="393a4-398">1809  (RS5)</span></span> |<span data-ttu-id="393a4-399">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="393a4-399">4.18.1807.18075</span></span> |<span data-ttu-id="393a4-400">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="393a4-400">1.1.15000.2</span></span> | <span data-ttu-id="393a4-401">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="393a4-401">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="393a4-402">1803 (RS4) </span><span class="sxs-lookup"><span data-stu-id="393a4-402">1803  (RS4)</span></span> |<span data-ttu-id="393a4-403">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="393a4-403">4.13.17134.1</span></span> |<span data-ttu-id="393a4-404">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="393a4-404">1.1.14600.4</span></span> | <span data-ttu-id="393a4-405">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="393a4-405">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="393a4-406">1709 (RS3) </span><span class="sxs-lookup"><span data-stu-id="393a4-406">1709  (RS3)</span></span> |<span data-ttu-id="393a4-407">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="393a4-407">4.12.16299.15</span></span> |<span data-ttu-id="393a4-408">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="393a4-408">1.1.14104.0</span></span> | <span data-ttu-id="393a4-409">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="393a4-409">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="393a4-410">1703 (RS2) </span><span class="sxs-lookup"><span data-stu-id="393a4-410">1703  (RS2)</span></span> |<span data-ttu-id="393a4-411">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="393a4-411">4.11.15603.2</span></span> |<span data-ttu-id="393a4-412">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="393a4-412">1.1.13504.0</span></span> | <span data-ttu-id="393a4-413">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="393a4-413">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="393a4-414">1607 (RS1) </span><span class="sxs-lookup"><span data-stu-id="393a4-414">1607 (RS1)</span></span> |<span data-ttu-id="393a4-415">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="393a4-415">4.10.14393.3683</span></span> |<span data-ttu-id="393a4-416">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="393a4-416">1.1.12805.0</span></span> | <span data-ttu-id="393a4-417">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="393a4-417">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="393a4-418">如需 Windows 10 版本資訊，請參閱[Windows 生命週期事實資料表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="393a4-418">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="393a4-419">更新部署映像服務與管理 (DISM) </span><span class="sxs-lookup"><span data-stu-id="393a4-419">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="393a4-420">建議您更新 Windows 10 (Enterprise、Pro 及 Home edition) 、Windows Server 2019，以及 Windows Server 2016 OS 安裝影像與最新的防病毒和反惡意軟體更新。</span><span class="sxs-lookup"><span data-stu-id="393a4-420">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="393a4-421">將您的作業系統安裝影像保持在最新狀態，可協助避免保護方面的缺口。</span><span class="sxs-lookup"><span data-stu-id="393a4-421">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="393a4-422">如需詳細資訊，請參閱[Microsoft Defender update for Windows 作業系統安裝影像](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="393a4-422">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="393a4-423">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="393a4-423">1.1.2106.01</span></span></summary>

<span data-ttu-id="393a4-424">&ensp;套件版本： **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="393a4-424">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="393a4-425">&ensp;平臺版本： **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="393a4-425">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="393a4-426">&ensp;引擎版本： **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="393a4-426">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="393a4-427">&ensp;簽章版本： **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-427">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="393a4-428">修復</span><span class="sxs-lookup"><span data-stu-id="393a4-428">Fixes</span></span>
- <span data-ttu-id="393a4-429">無</span><span class="sxs-lookup"><span data-stu-id="393a4-429">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="393a4-430">其他資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-430">Additional information</span></span>
- <span data-ttu-id="393a4-431">無</span><span class="sxs-lookup"><span data-stu-id="393a4-431">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="393a4-432">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="393a4-432">1.1.2105.01</span></span></summary>

<span data-ttu-id="393a4-433">&ensp;套件版本： **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="393a4-433">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="393a4-434">&ensp;平臺版本： **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="393a4-434">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="393a4-435">&ensp;引擎版本： **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="393a4-435">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="393a4-436">&ensp;簽章版本： **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-436">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="393a4-437">修復</span><span class="sxs-lookup"><span data-stu-id="393a4-437">Fixes</span></span>
- <span data-ttu-id="393a4-438">無</span><span class="sxs-lookup"><span data-stu-id="393a4-438">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="393a4-439">其他資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-439">Additional information</span></span>
- <span data-ttu-id="393a4-440">無</span><span class="sxs-lookup"><span data-stu-id="393a4-440">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="393a4-441">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="393a4-441">1.1.2104.01</span></span></summary>

<span data-ttu-id="393a4-442">&ensp;套件版本： **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="393a4-442">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="393a4-443">&ensp;平臺版本： **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="393a4-443">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="393a4-444">&ensp;引擎版本： **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-444">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="393a4-445">&ensp;簽章版本： **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-445">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="393a4-446">修復</span><span class="sxs-lookup"><span data-stu-id="393a4-446">Fixes</span></span>
- <span data-ttu-id="393a4-447">無</span><span class="sxs-lookup"><span data-stu-id="393a4-447">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="393a4-448">其他資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-448">Additional information</span></span>
- <span data-ttu-id="393a4-449">無</span><span class="sxs-lookup"><span data-stu-id="393a4-449">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="393a4-450">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="393a4-450">1.1.2103.01</span></span></summary>

<span data-ttu-id="393a4-451">&ensp;套件版本： **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="393a4-451">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="393a4-452">&ensp;平臺版本： **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="393a4-452">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="393a4-453">&ensp;引擎版本： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-453">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="393a4-454">&ensp;簽章版本： **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-454">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="393a4-455">修復</span><span class="sxs-lookup"><span data-stu-id="393a4-455">Fixes</span></span>
- <span data-ttu-id="393a4-456">無</span><span class="sxs-lookup"><span data-stu-id="393a4-456">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="393a4-457">其他資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-457">Additional information</span></span>
- <span data-ttu-id="393a4-458">無</span><span class="sxs-lookup"><span data-stu-id="393a4-458">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="393a4-459">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="393a4-459">1.1.2102.03</span></span></summary>

<span data-ttu-id="393a4-460">&ensp;套件版本： **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="393a4-460">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="393a4-461">&ensp;平臺版本： **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="393a4-461">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="393a4-462">&ensp;引擎版本： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-462">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="393a4-463">&ensp;簽章版本： **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-463">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="393a4-464">修復</span><span class="sxs-lookup"><span data-stu-id="393a4-464">Fixes</span></span>
- <span data-ttu-id="393a4-465">無</span><span class="sxs-lookup"><span data-stu-id="393a4-465">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="393a4-466">其他資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-466">Additional information</span></span>
- <span data-ttu-id="393a4-467">無</span><span class="sxs-lookup"><span data-stu-id="393a4-467">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="393a4-468">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="393a4-468">1.1.2101.02</span></span></summary>

<span data-ttu-id="393a4-469">&ensp;套件版本： **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="393a4-469">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="393a4-470">&ensp;平臺版本： **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="393a4-470">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="393a4-471">&ensp;引擎版本： **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="393a4-471">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="393a4-472">&ensp;簽章版本： **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-472">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="393a4-473">修復</span><span class="sxs-lookup"><span data-stu-id="393a4-473">Fixes</span></span>
- <span data-ttu-id="393a4-474">無</span><span class="sxs-lookup"><span data-stu-id="393a4-474">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="393a4-475">其他資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-475">Additional information</span></span>
- <span data-ttu-id="393a4-476">無</span><span class="sxs-lookup"><span data-stu-id="393a4-476">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="393a4-477">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="393a4-477">1.1.2012.01</span></span></summary>

<span data-ttu-id="393a4-478">&ensp;套件版本： **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="393a4-478">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="393a4-479">&ensp;平臺版本： **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="393a4-479">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="393a4-480">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-480">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="393a4-481">&ensp;簽章版本： **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-481">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="393a4-482">修復</span><span class="sxs-lookup"><span data-stu-id="393a4-482">Fixes</span></span>
- <span data-ttu-id="393a4-483">無</span><span class="sxs-lookup"><span data-stu-id="393a4-483">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="393a4-484">其他資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-484">Additional information</span></span>
- <span data-ttu-id="393a4-485">無</span><span class="sxs-lookup"><span data-stu-id="393a4-485">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="393a4-486">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="393a4-486">1.1.2011.02</span></span></summary>

<span data-ttu-id="393a4-487">&ensp;套件版本： **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="393a4-487">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="393a4-488">&ensp;平臺版本： **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="393a4-488">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="393a4-489">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-489">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="393a4-490">&ensp;簽章版本： **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-490">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="393a4-491">修復</span><span class="sxs-lookup"><span data-stu-id="393a4-491">Fixes</span></span>
- <span data-ttu-id="393a4-492">無</span><span class="sxs-lookup"><span data-stu-id="393a4-492">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="393a4-493">其他資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-493">Additional information</span></span>
- <span data-ttu-id="393a4-494">更新 Microsoft Defender 防毒軟體簽章</span><span class="sxs-lookup"><span data-stu-id="393a4-494">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="393a4-495">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="393a4-495">1.1.2011.01</span></span></summary>

<span data-ttu-id="393a4-496">&ensp;套件版本： **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="393a4-496">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="393a4-497">&ensp;平臺版本： **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="393a4-497">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="393a4-498">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-498">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="393a4-499">&ensp;簽章版本： **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-499">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="393a4-500">修復</span><span class="sxs-lookup"><span data-stu-id="393a4-500">Fixes</span></span>
- <span data-ttu-id="393a4-501">無</span><span class="sxs-lookup"><span data-stu-id="393a4-501">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="393a4-502">其他資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-502">Additional information</span></span>
- <span data-ttu-id="393a4-503">無</span><span class="sxs-lookup"><span data-stu-id="393a4-503">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="393a4-504">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="393a4-504">1.1.2009.10</span></span></summary>

<span data-ttu-id="393a4-505">&ensp;套件版本： **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="393a4-505">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="393a4-506">&ensp;平臺版本： **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="393a4-506">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="393a4-507">&ensp;引擎版本： **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="393a4-507">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="393a4-508">&ensp;簽章版本： **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="393a4-508">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="393a4-509">修復</span><span class="sxs-lookup"><span data-stu-id="393a4-509">Fixes</span></span>
- <span data-ttu-id="393a4-510">無</span><span class="sxs-lookup"><span data-stu-id="393a4-510">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="393a4-511">其他資訊</span><span class="sxs-lookup"><span data-stu-id="393a4-511">Additional information</span></span>
- <span data-ttu-id="393a4-512">新增對 Windows 10 RS1 或更新版本作業系統安裝影像的支援。</span><span class="sxs-lookup"><span data-stu-id="393a4-512">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="393a4-513">其他資源</span><span class="sxs-lookup"><span data-stu-id="393a4-513">Additional resources</span></span>

| <span data-ttu-id="393a4-514">文章</span><span class="sxs-lookup"><span data-stu-id="393a4-514">Article</span></span> | <span data-ttu-id="393a4-515">描述</span><span class="sxs-lookup"><span data-stu-id="393a4-515">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="393a4-516">適用于 Windows 作業系統安裝映射的 Microsoft Defender 更新</span><span class="sxs-lookup"><span data-stu-id="393a4-516">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="393a4-517">查看您 OS 安裝映射的反惡意軟體更新軟體包 (WIM 和 VHD 檔案) 。</span><span class="sxs-lookup"><span data-stu-id="393a4-517">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="393a4-518">取得 Windows 10 (Enterprise、Pro 和家用版的 Microsoft Defender 防毒軟體更新) 、Windows Server 2019 及 Windows Server 2016 安裝影像。</span><span class="sxs-lookup"><span data-stu-id="393a4-518">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="393a4-519">管理如何下載及套用保護更新</span><span class="sxs-lookup"><span data-stu-id="393a4-519">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="393a4-520">保護更新可透過許多來源傳遞。</span><span class="sxs-lookup"><span data-stu-id="393a4-520">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="393a4-521">管理應下載及套用防護更新的時間</span><span class="sxs-lookup"><span data-stu-id="393a4-521">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="393a4-522">您可以排程應下載保護更新的時間。</span><span class="sxs-lookup"><span data-stu-id="393a4-522">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="393a4-523">管理已過期端點的更新</span><span class="sxs-lookup"><span data-stu-id="393a4-523">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="393a4-524">如果端點未接更新或排程的掃描，您可以在下次使用者登入時強制更新或掃描。</span><span class="sxs-lookup"><span data-stu-id="393a4-524">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="393a4-525">管理事件型強制更新</span><span class="sxs-lookup"><span data-stu-id="393a4-525">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="393a4-526">您可以設定保護更新，以在啟動時或在某些雲端提供的保護事件之後下載。</span><span class="sxs-lookup"><span data-stu-id="393a4-526">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="393a4-527">管理行動裝置和虛擬機器 (VM) 的更新</span><span class="sxs-lookup"><span data-stu-id="393a4-527">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="393a4-528">您可以指定設定，例如是否應該在電池電源上進行更新，對行動裝置和虛擬機器尤其有用。</span><span class="sxs-lookup"><span data-stu-id="393a4-528">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
