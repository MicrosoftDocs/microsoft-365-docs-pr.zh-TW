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
ms.date: 06/08/2021
ms.openlocfilehash: ccbb57d781196e352e0fed456a1f7cb43eb17300
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822271"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="6a023-104">管理 Microsoft Defender 防毒軟體更新及套用基準</span><span class="sxs-lookup"><span data-stu-id="6a023-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="6a023-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="6a023-105">**Applies to:**</span></span>

- [<span data-ttu-id="6a023-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6a023-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="6a023-107">Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="6a023-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="6a023-108">有兩種與 Microsoft Defender 防毒軟體保持最新狀態相關的更新：</span><span class="sxs-lookup"><span data-stu-id="6a023-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="6a023-109">安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="6a023-109">Security intelligence updates</span></span>
- <span data-ttu-id="6a023-110">產品更新</span><span class="sxs-lookup"><span data-stu-id="6a023-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a023-111">將 Microsoft Defender 防毒軟體保持在最新狀態，是確保您的裝置具備防範新惡意程式碼和攻擊技巧所需的最新技術和功能。</span><span class="sxs-lookup"><span data-stu-id="6a023-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="6a023-112">即使在[被動模式下](./microsoft-defender-antivirus-compatibility.md)執行 Microsoft Defender 防毒軟體，也請務必更新防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="6a023-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="6a023-113">若要查看最新的引擎、平臺及簽章日期，請流覽[Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體的安全性情報更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="6a023-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="6a023-114">安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="6a023-114">Security intelligence updates</span></span>

<span data-ttu-id="6a023-115">Microsoft Defender 防毒軟體使用[雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md) (也稱為 Microsoft Advanced protection 服務或對應) ，定期下載安全性情報更新，以提供保護。</span><span class="sxs-lookup"><span data-stu-id="6a023-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="6a023-116">更新會在下列 KB 編號之下發行：</span><span class="sxs-lookup"><span data-stu-id="6a023-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="6a023-117">Microsoft Defender 防毒軟體： KB2267602</span><span class="sxs-lookup"><span data-stu-id="6a023-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="6a023-118">System Center Endpoint Protection： KB2461484</span><span class="sxs-lookup"><span data-stu-id="6a023-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="6a023-119">雲端傳送保護功能永遠都是開啟的，且需要網際網路連線才能運作。</span><span class="sxs-lookup"><span data-stu-id="6a023-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="6a023-120">安全智慧更新會在排程的節奏上進行， (可透過原則) 設定。</span><span class="sxs-lookup"><span data-stu-id="6a023-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="6a023-121">如需詳細資訊，請參閱[在 Microsoft Defender 防毒軟體中使用 Microsoft 雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="6a023-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="6a023-122">如需最近的安全性情報更新清單，請參閱[Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體的安全性情報更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="6a023-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="6a023-123">引擎更新包含在安全性智慧更新中，並以每月的節奏發行。</span><span class="sxs-lookup"><span data-stu-id="6a023-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="6a023-124">產品更新</span><span class="sxs-lookup"><span data-stu-id="6a023-124">Product updates</span></span>

<span data-ttu-id="6a023-125">Microsoft Defender 防毒軟體需要 [每月更新 (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (稱為 *平臺更新*) ，而且會在 Windows 10 版本的情況下收到重要的功能更新。</span><span class="sxs-lookup"><span data-stu-id="6a023-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="6a023-126">您可以透過下列其中一種方法來管理更新的發佈：</span><span class="sxs-lookup"><span data-stu-id="6a023-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="6a023-127">Windows伺服器更新服務 (WSUS) </span><span class="sxs-lookup"><span data-stu-id="6a023-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="6a023-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6a023-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="6a023-129">您用來部署 Microsoft 和 Windows 網路中端點更新的常用方法。</span><span class="sxs-lookup"><span data-stu-id="6a023-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="6a023-130">如需詳細資訊，請參閱[管理來源以取得 Microsoft Defender 防毒軟體保護更新](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="6a023-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="6a023-131">每月更新都會以階段發行，導致您的 [視窗伺服器更新服務](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)中顯示多個套件。</span><span class="sxs-lookup"><span data-stu-id="6a023-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="6a023-132">每月平臺及引擎版本</span><span class="sxs-lookup"><span data-stu-id="6a023-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="6a023-133">如需如何更新或安裝平臺更新的資訊，請參閱[Windows Defender 的反惡意程式碼平臺更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="6a023-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="6a023-134">我們所有的更新均包含</span><span class="sxs-lookup"><span data-stu-id="6a023-134">All our updates contain</span></span> 
- <span data-ttu-id="6a023-135">效能改進;</span><span class="sxs-lookup"><span data-stu-id="6a023-135">performance improvements;</span></span>
- <span data-ttu-id="6a023-136">可維護性改進;和</span><span class="sxs-lookup"><span data-stu-id="6a023-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="6a023-137"> (Cloud [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)) 的整合增強功能。</span><span class="sxs-lookup"><span data-stu-id="6a023-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="6a023-138">2021年5月 (平臺： 4.18.2105.4 |Engine： 1.1.18200.4) </span><span class="sxs-lookup"><span data-stu-id="6a023-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="6a023-139">&ensp;安全性智慧更新版本： **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="6a023-140">&ensp;發行日期： **2021 年6月4日**</span><span class="sxs-lookup"><span data-stu-id="6a023-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="6a023-141">&ensp;Platform： **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="6a023-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="6a023-142">&ensp;Engine： **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="6a023-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="6a023-143">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="6a023-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-144">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-144">What's new</span></span>
- <span data-ttu-id="6a023-145">[行為監控](client-behavioral-blocking.md)的增強功能</span><span class="sxs-lookup"><span data-stu-id="6a023-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="6a023-146">固定 [網路保護](network-protection.md) 通知篩選功能</span><span class="sxs-lookup"><span data-stu-id="6a023-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-147">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-147">Known Issues</span></span>
<span data-ttu-id="6a023-148">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="6a023-149">四月-2021 (平臺： 4.18.2104.14 |Engine： 1.1.18100.5) </span><span class="sxs-lookup"><span data-stu-id="6a023-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="6a023-150">&ensp;安全性智慧更新版本： **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="6a023-151">&ensp;發行日期： **2021 年4月1日**</span><span class="sxs-lookup"><span data-stu-id="6a023-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="6a023-152">&ensp;Platform： **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="6a023-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="6a023-153">&ensp;Engine： **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="6a023-154">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="6a023-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-155">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-155">What's new</span></span>
- <span data-ttu-id="6a023-156">其他行為監控邏輯</span><span class="sxs-lookup"><span data-stu-id="6a023-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="6a023-157">改進的核心模式 keylogger 偵測</span><span class="sxs-lookup"><span data-stu-id="6a023-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="6a023-158">新增控制項以管理[Microsoft Defender 更新](updates.md)的逐步式展示過程</span><span class="sxs-lookup"><span data-stu-id="6a023-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-159">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-159">Known Issues</span></span>
<span data-ttu-id="6a023-160">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="6a023-161">三月份-2021 (平臺： 4.18.2103.7 |Engine： 1.1.18000.5) </span><span class="sxs-lookup"><span data-stu-id="6a023-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="6a023-162">&ensp;安全性智慧更新版本： **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="6a023-163">&ensp;發行日期： **2021 年4月1日**</span><span class="sxs-lookup"><span data-stu-id="6a023-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="6a023-164">&ensp;Platform： **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="6a023-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="6a023-165">&ensp;Engine： **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="6a023-166">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="6a023-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-167">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-167">What's new</span></span>

- <span data-ttu-id="6a023-168">改進行為監控引擎</span><span class="sxs-lookup"><span data-stu-id="6a023-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="6a023-169">擴充網路暴力攻擊緩解</span><span class="sxs-lookup"><span data-stu-id="6a023-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="6a023-170">啟用 [防篡改保護](prevent-changes-to-security-settings-with-tamper-protection.md) 時，其他失敗的篡改嘗試事件產生</span><span class="sxs-lookup"><span data-stu-id="6a023-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-171">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-171">Known Issues</span></span>
<span data-ttu-id="6a023-172">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="6a023-173">舊版本更新：僅限技術升級支援</span><span class="sxs-lookup"><span data-stu-id="6a023-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="6a023-174">發行新的套件版本之後，支援舊版的兩個版本只會縮小為技術支援。</span><span class="sxs-lookup"><span data-stu-id="6a023-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="6a023-175">這一節所列出的版本舊，僅提供支援技術升級。</span><span class="sxs-lookup"><span data-stu-id="6a023-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="6a023-176">二月份-2021 (平臺： 4.18.2102.3 |Engine： 1.1.17900.7) </span><span class="sxs-lookup"><span data-stu-id="6a023-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="6a023-177">&ensp;安全性智慧更新版本： **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="6a023-178">&ensp;發行日期： **2021 年3月9日**</span><span class="sxs-lookup"><span data-stu-id="6a023-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="6a023-179">&ensp;Platform： **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="6a023-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="6a023-180">&ensp;Engine： **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="6a023-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="6a023-181">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-182">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-182">What's new</span></span>

- <span data-ttu-id="6a023-183">透過[防篡改保護](prevent-changes-to-security-settings-with-tamper-protection.md)改進服務復原</span><span class="sxs-lookup"><span data-stu-id="6a023-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="6a023-184">擴充不可篡改的保護範圍</span><span class="sxs-lookup"><span data-stu-id="6a023-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-185">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-185">Known Issues</span></span>
<span data-ttu-id="6a023-186">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="6a023-187">2021年1月 (平臺： 4.18.2101.9 |Engine： 1.1.17800.5) </span><span class="sxs-lookup"><span data-stu-id="6a023-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="6a023-188">&ensp;安全性智慧更新版本： **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="6a023-189">&ensp;發行日期： **2021 年2月2日**</span><span class="sxs-lookup"><span data-stu-id="6a023-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="6a023-190">&ensp;Platform： **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="6a023-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="6a023-191">&ensp;Engine： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="6a023-192">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-193">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-193">What's new</span></span>

- <span data-ttu-id="6a023-194">外殼代碼利用偵測增強功能</span><span class="sxs-lookup"><span data-stu-id="6a023-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="6a023-195">增強認證竊取嘗試的知名度</span><span class="sxs-lookup"><span data-stu-id="6a023-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="6a023-196">Microsoft Defender 防毒軟體服務中的 antitampering 功能的增強功能</span><span class="sxs-lookup"><span data-stu-id="6a023-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="6a023-197">改進支援 ARM x64 模擬</span><span class="sxs-lookup"><span data-stu-id="6a023-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="6a023-198">修正：在即時保護執行初始偵測後，威脅史中仍會保留 EDR 封鎖通知</span><span class="sxs-lookup"><span data-stu-id="6a023-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-199">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-199">Known Issues</span></span>
<span data-ttu-id="6a023-200">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="6a023-201">11月-2020 (平臺： 4.18.2011.6 |Engine： 1.1.17700.4) </span><span class="sxs-lookup"><span data-stu-id="6a023-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="6a023-202">&ensp;安全性智慧更新版本： **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="6a023-203">&ensp;發行日期： **2020 年12月**</span><span class="sxs-lookup"><span data-stu-id="6a023-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="6a023-204">&ensp;Platform： **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="6a023-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="6a023-205">&ensp;Engine： **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="6a023-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="6a023-206">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-207">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-207">What's new</span></span>

- <span data-ttu-id="6a023-208">改進的 [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 狀態支援記錄</span><span class="sxs-lookup"><span data-stu-id="6a023-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-209">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-209">Known Issues</span></span>
<span data-ttu-id="6a023-210">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="6a023-211">十月-2020 (平臺： 4.18.2010.7 |Engine： 1.1.17600.5) </span><span class="sxs-lookup"><span data-stu-id="6a023-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="6a023-212">&ensp;安全性智慧更新版本： **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="6a023-213">&ensp;發行日期： **2020 年10月29日**</span><span class="sxs-lookup"><span data-stu-id="6a023-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="6a023-214">&ensp;Platform： **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="6a023-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="6a023-215">&ensp;Engine： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="6a023-216">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-217">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-217">What's new</span></span>

- <span data-ttu-id="6a023-218">特殊威脅類別的新描述</span><span class="sxs-lookup"><span data-stu-id="6a023-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="6a023-219">改進模擬功能</span><span class="sxs-lookup"><span data-stu-id="6a023-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="6a023-220">改進的主機位址允許/封鎖功能</span><span class="sxs-lookup"><span data-stu-id="6a023-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="6a023-221">在 Defender CSP 中新增選項，以忽略本機使用者排除的合併</span><span class="sxs-lookup"><span data-stu-id="6a023-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-222">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-222">Known Issues</span></span>

<span data-ttu-id="6a023-223">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="6a023-224">九月份-2020 (平臺： 4.18.2009.7 |Engine： 1.1.17500.4) </span><span class="sxs-lookup"><span data-stu-id="6a023-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="6a023-225">&ensp;安全性智慧更新版本： **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="6a023-226">&ensp;發行日期： **2020 年10月1日**</span><span class="sxs-lookup"><span data-stu-id="6a023-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="6a023-227">&ensp;Platform： **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="6a023-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="6a023-228">&ensp;Engine： **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="6a023-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="6a023-229">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-230">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-230">What's new</span></span>

- <span data-ttu-id="6a023-231">需要有系統管理員許可權，才能還原隔離中的檔案</span><span class="sxs-lookup"><span data-stu-id="6a023-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="6a023-232">現在支援 XML 格式化的事件</span><span class="sxs-lookup"><span data-stu-id="6a023-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="6a023-233">用於忽略排除合併的 CSP 支援</span><span class="sxs-lookup"><span data-stu-id="6a023-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="6a023-234">下列專案的新管理介面：</span><span class="sxs-lookup"><span data-stu-id="6a023-234">New management interfaces for:</span></span>
   - <span data-ttu-id="6a023-235">UDP 檢查</span><span class="sxs-lookup"><span data-stu-id="6a023-235">UDP Inspection</span></span>
   - <span data-ttu-id="6a023-236">伺服器2019上的網路保護</span><span class="sxs-lookup"><span data-stu-id="6a023-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="6a023-237">網路保護的 IP 位址排除</span><span class="sxs-lookup"><span data-stu-id="6a023-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="6a023-238">改善 TPM 測量的可見度</span><span class="sxs-lookup"><span data-stu-id="6a023-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="6a023-239">改進的 Office VBA 模組掃描</span><span class="sxs-lookup"><span data-stu-id="6a023-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-240">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-240">Known Issues</span></span>

<span data-ttu-id="6a023-241">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="6a023-242">八月-2020 (平臺： 4.18.2008.9 |Engine： 1.1.17400.5) </span><span class="sxs-lookup"><span data-stu-id="6a023-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="6a023-243">&ensp;安全性智慧更新版本： **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="6a023-244">&ensp;發行日期： **2020 年8月27日**</span><span class="sxs-lookup"><span data-stu-id="6a023-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="6a023-245">&ensp;Platform： **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="6a023-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="6a023-246">&ensp;Engine： **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="6a023-247">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="6a023-248">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-248">What's new</span></span>

- <span data-ttu-id="6a023-249">新增更多遙測事件</span><span class="sxs-lookup"><span data-stu-id="6a023-249">Add more telemetry events</span></span>
- <span data-ttu-id="6a023-250">改進的掃描事件遙測</span><span class="sxs-lookup"><span data-stu-id="6a023-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="6a023-251">改進的記憶體掃描行為監控</span><span class="sxs-lookup"><span data-stu-id="6a023-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="6a023-252">改進的宏資料流程掃描</span><span class="sxs-lookup"><span data-stu-id="6a023-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="6a023-253">新增 `AMRunningMode` 至 Get-MpComputerStatus PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6a023-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="6a023-254">會忽略[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 。</span><span class="sxs-lookup"><span data-stu-id="6a023-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="6a023-255">Microsoft Defender 防毒軟體會在偵測其他防毒程式時自動開啟自身。</span><span class="sxs-lookup"><span data-stu-id="6a023-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="6a023-256">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-256">Known Issues</span></span>
<span data-ttu-id="6a023-257">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="6a023-258">2020年7月- (平臺： 4.18.2007.8 |Engine： 1.1.17300.4) </span><span class="sxs-lookup"><span data-stu-id="6a023-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="6a023-259">&ensp;安全性智慧更新版本： **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="6a023-260">&ensp;發行日期： **2020 年7月28日**</span><span class="sxs-lookup"><span data-stu-id="6a023-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="6a023-261">&ensp;Platform： **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="6a023-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="6a023-262">&ensp;Engine： **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="6a023-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="6a023-263">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-264">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-264">What's new</span></span>

- <span data-ttu-id="6a023-265">改進的遙測的 BITS</span><span class="sxs-lookup"><span data-stu-id="6a023-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="6a023-266">改進的驗證碼簽名憑證驗證</span><span class="sxs-lookup"><span data-stu-id="6a023-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-267">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-267">Known Issues</span></span>
<span data-ttu-id="6a023-268">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="6a023-269">六月-2020 (平臺： 4.18.2006.10 |Engine： 1.1.17200.2) </span><span class="sxs-lookup"><span data-stu-id="6a023-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="6a023-270">&ensp;安全性智慧更新版本： **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="6a023-271">&ensp;發行日期： **2020 年6月22日**</span><span class="sxs-lookup"><span data-stu-id="6a023-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="6a023-272">&ensp;Platform： **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="6a023-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="6a023-273">&ensp;Engine： **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="6a023-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="6a023-274">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-275">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-275">What's new</span></span>

- <span data-ttu-id="6a023-276">可能指定[支援記錄](./collect-diagnostic-data.md)檔的位置</span><span class="sxs-lookup"><span data-stu-id="6a023-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="6a023-277">在被動模式中略過積極 catchup 掃描。</span><span class="sxs-lookup"><span data-stu-id="6a023-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="6a023-278">允許 Defender 在流量計費的連線上更新</span><span class="sxs-lookup"><span data-stu-id="6a023-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="6a023-279">停用快取時的固定效能調整</span><span class="sxs-lookup"><span data-stu-id="6a023-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="6a023-280">固定登錄查詢</span><span class="sxs-lookup"><span data-stu-id="6a023-280">Fixed registry query</span></span> 
- <span data-ttu-id="6a023-281">ADMX 中的固定 scantime 隨機化</span><span class="sxs-lookup"><span data-stu-id="6a023-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-282">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-282">Known Issues</span></span>
<span data-ttu-id="6a023-283">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="6a023-284">2020年5月 (平臺： 4.18.2005.4 |Engine： 1.1.17100.2) </span><span class="sxs-lookup"><span data-stu-id="6a023-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="6a023-285">&ensp;安全性智慧更新版本： **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="6a023-286">&ensp;發行日期： **2020 年5月26日**</span><span class="sxs-lookup"><span data-stu-id="6a023-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="6a023-287">&ensp;Platform： **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="6a023-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="6a023-288">&ensp;Engine： **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="6a023-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="6a023-289">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-290">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-290">What's new</span></span>

- <span data-ttu-id="6a023-291">改進的掃描事件記錄</span><span class="sxs-lookup"><span data-stu-id="6a023-291">Improved logging for scan events</span></span>
- <span data-ttu-id="6a023-292">改進的使用者模式損毀處理。</span><span class="sxs-lookup"><span data-stu-id="6a023-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="6a023-293">新增防篡改保護的事件追蹤</span><span class="sxs-lookup"><span data-stu-id="6a023-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="6a023-294">修正 AMSI 範例提交</span><span class="sxs-lookup"><span data-stu-id="6a023-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="6a023-295">固定 AMSI Cloud 封鎖</span><span class="sxs-lookup"><span data-stu-id="6a023-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="6a023-296">修正的安全性更新安裝記錄檔</span><span class="sxs-lookup"><span data-stu-id="6a023-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-297">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-297">Known Issues</span></span>
<span data-ttu-id="6a023-298">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="6a023-299">四月-2020 (平臺： 4.18.2004.6 |Engine： 1.1.17000.2) </span><span class="sxs-lookup"><span data-stu-id="6a023-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="6a023-300">&ensp;安全性智慧更新版本： **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="6a023-301">&ensp;發行日期： **2020 年4月30日**</span><span class="sxs-lookup"><span data-stu-id="6a023-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="6a023-302">&ensp;Platform： **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="6a023-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="6a023-303">&ensp;Engine： **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="6a023-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="6a023-304">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-305">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-305">What's new</span></span>
- <span data-ttu-id="6a023-306">WDfilter 改進功能</span><span class="sxs-lookup"><span data-stu-id="6a023-306">WDfilter improvements</span></span>
- <span data-ttu-id="6a023-307">新增更具可操作性的事件資料至攻擊面減少偵測事件</span><span class="sxs-lookup"><span data-stu-id="6a023-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="6a023-308">診斷資料和 WMI 中的固定版本資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="6a023-309">在平臺更新後在 UI 中修復不正確的平臺版本</span><span class="sxs-lookup"><span data-stu-id="6a023-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="6a023-310">動態 URL intel for Fileless 威脅防護</span><span class="sxs-lookup"><span data-stu-id="6a023-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="6a023-311">UEFI 掃描功能</span><span class="sxs-lookup"><span data-stu-id="6a023-311">UEFI scan capability</span></span>
- <span data-ttu-id="6a023-312">擴充更新記錄</span><span class="sxs-lookup"><span data-stu-id="6a023-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="6a023-313">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-313">Known Issues</span></span>
<span data-ttu-id="6a023-314">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="6a023-315">三月份-2020 (平臺： 4.18.2003.8 |Engine： 1.1.16900.2) </span><span class="sxs-lookup"><span data-stu-id="6a023-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="6a023-316">&ensp;安全性智慧更新版本： **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="6a023-317">&ensp;發行日期： **2020 年3月24日**</span><span class="sxs-lookup"><span data-stu-id="6a023-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="6a023-318">&ensp;Platform： **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="6a023-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="6a023-319">&ensp;Engine： **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="6a023-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="6a023-320">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="6a023-321">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-321">What's new</span></span>

- <span data-ttu-id="6a023-322">新增至[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 節流選項</span><span class="sxs-lookup"><span data-stu-id="6a023-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="6a023-323">改善診斷功能</span><span class="sxs-lookup"><span data-stu-id="6a023-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="6a023-324">降低安全性情報超時 (5 分鐘) </span><span class="sxs-lookup"><span data-stu-id="6a023-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="6a023-325">擴充 AMSI 引擎內部記錄功能</span><span class="sxs-lookup"><span data-stu-id="6a023-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="6a023-326">改進處理常式封鎖的通知</span><span class="sxs-lookup"><span data-stu-id="6a023-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="6a023-327">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-327">Known Issues</span></span>
<span data-ttu-id="6a023-328">[**Fixed**]Microsoft Defender 防毒軟體會在執行掃描時略過檔案。</span><span class="sxs-lookup"><span data-stu-id="6a023-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="6a023-329">二月份-2020 (平臺： |Engine： 1.1.16800.2) </span><span class="sxs-lookup"><span data-stu-id="6a023-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="6a023-330">&ensp;安全性智慧更新版本： **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="6a023-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="6a023-331">&ensp;發行日期： **2020 年2月25日**</span><span class="sxs-lookup"><span data-stu-id="6a023-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="6a023-332">&ensp;平臺/用戶端： **-**</span><span class="sxs-lookup"><span data-stu-id="6a023-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="6a023-333">&ensp;Engine： **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="6a023-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="6a023-334">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="6a023-335">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="6a023-336">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-336">Known Issues</span></span>
<span data-ttu-id="6a023-337">無已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="6a023-338">2020年1月 (平臺： 4.18.2001.10 |Engine： 1.1.16700.2) </span><span class="sxs-lookup"><span data-stu-id="6a023-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="6a023-339">安全性智慧更新版本： **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="6a023-340">發行日期： **2020 年1月30日**</span><span class="sxs-lookup"><span data-stu-id="6a023-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="6a023-341">Platform/Client： **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="6a023-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="6a023-342">Engine： **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="6a023-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="6a023-343">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="6a023-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="6a023-344">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-344">What's new</span></span>

- <span data-ttu-id="6a023-345">具有 Exchange 的 WS2016 上的固定 BSOD</span><span class="sxs-lookup"><span data-stu-id="6a023-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="6a023-346">當 TMP 重新導向至網路路徑時支援平臺更新</span><span class="sxs-lookup"><span data-stu-id="6a023-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="6a023-347">平臺和引擎版本已新增至 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="6a023-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="6a023-348">將緊急特徵碼更新擴充為 [被動模式](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="6a023-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="6a023-349">修正4.18.1911.3 懸掛</span><span class="sxs-lookup"><span data-stu-id="6a023-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="6a023-350">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-350">Known Issues</span></span>

<span data-ttu-id="6a023-351">[**Fixed**] 採用 [新式待機模式](/windows-hardware/design/device-experiences/modern-standby)的裝置可能會在 Windows Defender 篩選器驅動程式遇到中斷，從而導致保護的缺口。</span><span class="sxs-lookup"><span data-stu-id="6a023-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="6a023-352">受影響的機器會因尚未更新為最新的反惡意程式碼平臺而向客戶呈現。</span><span class="sxs-lookup"><span data-stu-id="6a023-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="6a023-353">此更新如下：</span><span class="sxs-lookup"><span data-stu-id="6a023-353">This update is:</span></span>
> - <span data-ttu-id="6a023-354">由執行低版本平臺的 RS1 裝置所需，以支援 SHA2;</span><span class="sxs-lookup"><span data-stu-id="6a023-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="6a023-355">具有懸掛問題的系統重新開機標誌;</span><span class="sxs-lookup"><span data-stu-id="6a023-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="6a023-356">會在4月2020內重新發佈，而且不會被更新的更新取代以保留未來的可用性;</span><span class="sxs-lookup"><span data-stu-id="6a023-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="6a023-357">因重新開機要求而分類為更新和</span><span class="sxs-lookup"><span data-stu-id="6a023-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="6a023-358">只會以[Windows 更新](https://support.microsoft.com/help/4027667/windows-10-update)提供。</span><span class="sxs-lookup"><span data-stu-id="6a023-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="6a023-359">11月-2019 (平臺： 4.18.1911.3 |Engine： 1.1.16600.7) </span><span class="sxs-lookup"><span data-stu-id="6a023-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="6a023-360">安全性智慧更新版本： **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="6a023-361">發行日期： **2019 月7日**</span><span class="sxs-lookup"><span data-stu-id="6a023-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="6a023-362">Platform： **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="6a023-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="6a023-363">Engine： **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="6a023-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="6a023-364">支援階段： **不支援**</span><span class="sxs-lookup"><span data-stu-id="6a023-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="6a023-365">新增功能</span><span class="sxs-lookup"><span data-stu-id="6a023-365">What's new</span></span>

- <span data-ttu-id="6a023-366">固定 MpCmdRun 追蹤層級</span><span class="sxs-lookup"><span data-stu-id="6a023-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="6a023-367">固定 WDFilter 版本資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="6a023-368"> (PUA) 提升通知</span><span class="sxs-lookup"><span data-stu-id="6a023-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="6a023-369">新增 MRT.LOG 記錄以支援檔案</span><span class="sxs-lookup"><span data-stu-id="6a023-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="6a023-370">已知問題</span><span class="sxs-lookup"><span data-stu-id="6a023-370">Known Issues</span></span>
<span data-ttu-id="6a023-371">安裝此更新時，裝置需要「跳過套件4.18.2001.10」才能更新為最新的平臺版本。</span><span class="sxs-lookup"><span data-stu-id="6a023-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="6a023-372">Microsoft Defender 防毒軟體平臺支援</span><span class="sxs-lookup"><span data-stu-id="6a023-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="6a023-373">平臺和引擎更新是以每月節奏提供。</span><span class="sxs-lookup"><span data-stu-id="6a023-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="6a023-374">若要完全支援，請使用最新的平臺更新來保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="6a023-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="6a023-375">我們的支援結構是動態的，而且會根據最新平臺版本的可用性而演變成兩個階段：</span><span class="sxs-lookup"><span data-stu-id="6a023-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="6a023-376">**安全性和重要更新服務階段** -執行最新的平臺版本時，您將有資格收到反惡意程式碼平臺的安全性和重要更新。</span><span class="sxs-lookup"><span data-stu-id="6a023-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="6a023-377">**僅限) 階段的技術支援 (** 。發行新的平臺版本之後，支援較舊版本 (n-1) 只會降低技術支援。</span><span class="sxs-lookup"><span data-stu-id="6a023-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="6a023-378">不再支援非 N-2 版本的平臺。</span><span class="sxs-lookup"><span data-stu-id="6a023-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="6a023-379">\*將繼續提供技術支援，以供從 Windows 10 發行版本本升級 (請參閱[Windows 10 版本隨附的平臺版本](#platform-version-included-with-windows-10-releases)) 至最新的平臺版本。</span><span class="sxs-lookup"><span data-stu-id="6a023-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="6a023-380">在技術支援 (只有) 階段，將會透過 Microsoft 客戶服務 & 支援和 Microsoft 受管理的支援服務， (例如 Premier Support) ，供應商業上合理的支援事件。</span><span class="sxs-lookup"><span data-stu-id="6a023-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="6a023-381">如果支援事件需要升級開發以取得進一步的指導方針、需要非安全性更新，或需要安全性更新，則系統會要求客戶升級至最新的平臺版本或中級更新 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="6a023-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="6a023-382">Windows 10 版本隨附的平臺版本</span><span class="sxs-lookup"><span data-stu-id="6a023-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="6a023-383">下表提供隨附于最新 Windows 10 版本的 Microsoft Defender 防毒軟體平臺和引擎版本：</span><span class="sxs-lookup"><span data-stu-id="6a023-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="6a023-384">Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="6a023-384">Windows 10 release</span></span>  |<span data-ttu-id="6a023-385">平臺版本</span><span class="sxs-lookup"><span data-stu-id="6a023-385">Platform version</span></span>  |<span data-ttu-id="6a023-386">引擎版本</span><span class="sxs-lookup"><span data-stu-id="6a023-386">Engine version</span></span> |<span data-ttu-id="6a023-387">支援階段</span><span class="sxs-lookup"><span data-stu-id="6a023-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="6a023-388">2004 (20H1/20H2) </span><span class="sxs-lookup"><span data-stu-id="6a023-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="6a023-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="6a023-389">4.18.1909.6</span></span> |<span data-ttu-id="6a023-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="6a023-390">1.1.17000.2</span></span> | <span data-ttu-id="6a023-391">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="6a023-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="6a023-392">1909 (19H2) </span><span class="sxs-lookup"><span data-stu-id="6a023-392">1909  (19H2)</span></span> |<span data-ttu-id="6a023-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="6a023-393">4.18.1902.5</span></span> |<span data-ttu-id="6a023-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="6a023-394">1.1.16700.3</span></span> | <span data-ttu-id="6a023-395">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="6a023-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="6a023-396">1903 (19H1) </span><span class="sxs-lookup"><span data-stu-id="6a023-396">1903  (19H1)</span></span> |<span data-ttu-id="6a023-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="6a023-397">4.18.1902.5</span></span> |<span data-ttu-id="6a023-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="6a023-398">1.1.15600.4</span></span> | <span data-ttu-id="6a023-399">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="6a023-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="6a023-400">1809 (RS5) </span><span class="sxs-lookup"><span data-stu-id="6a023-400">1809  (RS5)</span></span> |<span data-ttu-id="6a023-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="6a023-401">4.18.1807.18075</span></span> |<span data-ttu-id="6a023-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="6a023-402">1.1.15000.2</span></span> | <span data-ttu-id="6a023-403">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="6a023-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="6a023-404">1803 (RS4) </span><span class="sxs-lookup"><span data-stu-id="6a023-404">1803  (RS4)</span></span> |<span data-ttu-id="6a023-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="6a023-405">4.13.17134.1</span></span> |<span data-ttu-id="6a023-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="6a023-406">1.1.14600.4</span></span> | <span data-ttu-id="6a023-407">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="6a023-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="6a023-408">1709 (RS3) </span><span class="sxs-lookup"><span data-stu-id="6a023-408">1709  (RS3)</span></span> |<span data-ttu-id="6a023-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="6a023-409">4.12.16299.15</span></span> |<span data-ttu-id="6a023-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="6a023-410">1.1.14104.0</span></span> | <span data-ttu-id="6a023-411">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="6a023-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="6a023-412">1703 (RS2) </span><span class="sxs-lookup"><span data-stu-id="6a023-412">1703  (RS2)</span></span> |<span data-ttu-id="6a023-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="6a023-413">4.11.15603.2</span></span> |<span data-ttu-id="6a023-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="6a023-414">1.1.13504.0</span></span> | <span data-ttu-id="6a023-415">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="6a023-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="6a023-416">1607 (RS1) </span><span class="sxs-lookup"><span data-stu-id="6a023-416">1607 (RS1)</span></span> |<span data-ttu-id="6a023-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="6a023-417">4.10.14393.3683</span></span> |<span data-ttu-id="6a023-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="6a023-418">1.1.12805.0</span></span> | <span data-ttu-id="6a023-419">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="6a023-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="6a023-420">如需 Windows 10 版本資訊，請參閱[Windows 生命週期事實資料表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="6a023-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="6a023-421">更新部署映像服務與管理 (DISM) </span><span class="sxs-lookup"><span data-stu-id="6a023-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="6a023-422">建議您更新 Windows 10 (Enterprise、Pro 及 Home edition) 、Windows Server 2019，以及 Windows Server 2016 OS 安裝影像與最新的防病毒和反惡意軟體更新。</span><span class="sxs-lookup"><span data-stu-id="6a023-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="6a023-423">將您的作業系統安裝影像保持在最新狀態，可協助避免保護方面的缺口。</span><span class="sxs-lookup"><span data-stu-id="6a023-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="6a023-424">如需詳細資訊，請參閱[Microsoft Defender update for Windows 作業系統安裝影像](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="6a023-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="6a023-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="6a023-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="6a023-426">&ensp;套件版本： **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="6a023-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="6a023-427">&ensp;平臺版本： **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="6a023-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="6a023-428">&ensp;引擎版本： **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="6a023-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="6a023-429">&ensp;簽章版本： **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="6a023-430">修復</span><span class="sxs-lookup"><span data-stu-id="6a023-430">Fixes</span></span>
- <span data-ttu-id="6a023-431">無</span><span class="sxs-lookup"><span data-stu-id="6a023-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="6a023-432">其他資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-432">Additional information</span></span>
- <span data-ttu-id="6a023-433">無</span><span class="sxs-lookup"><span data-stu-id="6a023-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="6a023-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="6a023-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="6a023-435">&ensp;套件版本： **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="6a023-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="6a023-436">&ensp;平臺版本： **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="6a023-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="6a023-437">&ensp;引擎版本： **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="6a023-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="6a023-438">&ensp;簽章版本： **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="6a023-439">修復</span><span class="sxs-lookup"><span data-stu-id="6a023-439">Fixes</span></span>
- <span data-ttu-id="6a023-440">無</span><span class="sxs-lookup"><span data-stu-id="6a023-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="6a023-441">其他資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-441">Additional information</span></span>
- <span data-ttu-id="6a023-442">無</span><span class="sxs-lookup"><span data-stu-id="6a023-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="6a023-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="6a023-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="6a023-444">&ensp;套件版本： **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="6a023-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="6a023-445">&ensp;平臺版本： **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="6a023-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="6a023-446">&ensp;引擎版本： **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="6a023-447">&ensp;簽章版本： **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="6a023-448">修復</span><span class="sxs-lookup"><span data-stu-id="6a023-448">Fixes</span></span>
- <span data-ttu-id="6a023-449">無</span><span class="sxs-lookup"><span data-stu-id="6a023-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="6a023-450">其他資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-450">Additional information</span></span>
- <span data-ttu-id="6a023-451">無</span><span class="sxs-lookup"><span data-stu-id="6a023-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="6a023-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="6a023-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="6a023-453">&ensp;套件版本： **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="6a023-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="6a023-454">&ensp;平臺版本： **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="6a023-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="6a023-455">&ensp;引擎版本： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="6a023-456">&ensp;簽章版本： **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="6a023-457">修復</span><span class="sxs-lookup"><span data-stu-id="6a023-457">Fixes</span></span>
- <span data-ttu-id="6a023-458">無</span><span class="sxs-lookup"><span data-stu-id="6a023-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="6a023-459">其他資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-459">Additional information</span></span>
- <span data-ttu-id="6a023-460">無</span><span class="sxs-lookup"><span data-stu-id="6a023-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="6a023-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="6a023-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="6a023-462">&ensp;套件版本： **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="6a023-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="6a023-463">&ensp;平臺版本： **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="6a023-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="6a023-464">&ensp;引擎版本： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="6a023-465">&ensp;簽章版本： **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="6a023-466">修復</span><span class="sxs-lookup"><span data-stu-id="6a023-466">Fixes</span></span>
- <span data-ttu-id="6a023-467">無</span><span class="sxs-lookup"><span data-stu-id="6a023-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="6a023-468">其他資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-468">Additional information</span></span>
- <span data-ttu-id="6a023-469">無</span><span class="sxs-lookup"><span data-stu-id="6a023-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="6a023-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="6a023-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="6a023-471">&ensp;套件版本： **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="6a023-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="6a023-472">&ensp;平臺版本： **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="6a023-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="6a023-473">&ensp;引擎版本： **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="6a023-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="6a023-474">&ensp;簽章版本： **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="6a023-475">修復</span><span class="sxs-lookup"><span data-stu-id="6a023-475">Fixes</span></span>
- <span data-ttu-id="6a023-476">無</span><span class="sxs-lookup"><span data-stu-id="6a023-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="6a023-477">其他資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-477">Additional information</span></span>
- <span data-ttu-id="6a023-478">無</span><span class="sxs-lookup"><span data-stu-id="6a023-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="6a023-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="6a023-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="6a023-480">&ensp;套件版本： **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="6a023-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="6a023-481">&ensp;平臺版本： **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="6a023-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="6a023-482">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="6a023-483">&ensp;簽章版本： **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="6a023-484">修復</span><span class="sxs-lookup"><span data-stu-id="6a023-484">Fixes</span></span>
- <span data-ttu-id="6a023-485">無</span><span class="sxs-lookup"><span data-stu-id="6a023-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="6a023-486">其他資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-486">Additional information</span></span>
- <span data-ttu-id="6a023-487">無</span><span class="sxs-lookup"><span data-stu-id="6a023-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="6a023-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="6a023-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="6a023-489">&ensp;套件版本： **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="6a023-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="6a023-490">&ensp;平臺版本： **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="6a023-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="6a023-491">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="6a023-492">&ensp;簽章版本： **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="6a023-493">修復</span><span class="sxs-lookup"><span data-stu-id="6a023-493">Fixes</span></span>
- <span data-ttu-id="6a023-494">無</span><span class="sxs-lookup"><span data-stu-id="6a023-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="6a023-495">其他資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-495">Additional information</span></span>
- <span data-ttu-id="6a023-496">更新 Microsoft Defender 防毒軟體簽章</span><span class="sxs-lookup"><span data-stu-id="6a023-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="6a023-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="6a023-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="6a023-498">&ensp;套件版本： **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="6a023-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="6a023-499">&ensp;平臺版本： **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="6a023-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="6a023-500">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="6a023-501">&ensp;簽章版本： **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="6a023-502">修復</span><span class="sxs-lookup"><span data-stu-id="6a023-502">Fixes</span></span>
- <span data-ttu-id="6a023-503">無</span><span class="sxs-lookup"><span data-stu-id="6a023-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="6a023-504">其他資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-504">Additional information</span></span>
- <span data-ttu-id="6a023-505">無</span><span class="sxs-lookup"><span data-stu-id="6a023-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="6a023-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="6a023-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="6a023-507">&ensp;套件版本： **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="6a023-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="6a023-508">&ensp;平臺版本： **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="6a023-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="6a023-509">&ensp;引擎版本： **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="6a023-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="6a023-510">&ensp;簽章版本： **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="6a023-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="6a023-511">修復</span><span class="sxs-lookup"><span data-stu-id="6a023-511">Fixes</span></span>
- <span data-ttu-id="6a023-512">無</span><span class="sxs-lookup"><span data-stu-id="6a023-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="6a023-513">其他資訊</span><span class="sxs-lookup"><span data-stu-id="6a023-513">Additional information</span></span>
- <span data-ttu-id="6a023-514">新增對 Windows 10 RS1 或更新版本作業系統安裝影像的支援。</span><span class="sxs-lookup"><span data-stu-id="6a023-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="6a023-515">其他資源</span><span class="sxs-lookup"><span data-stu-id="6a023-515">Additional resources</span></span>

| <span data-ttu-id="6a023-516">文章</span><span class="sxs-lookup"><span data-stu-id="6a023-516">Article</span></span> | <span data-ttu-id="6a023-517">描述</span><span class="sxs-lookup"><span data-stu-id="6a023-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="6a023-518">適用于 Windows 作業系統安裝映射的 Microsoft Defender 更新</span><span class="sxs-lookup"><span data-stu-id="6a023-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="6a023-519">查看您 OS 安裝映射的反惡意軟體更新軟體包 (WIM 和 VHD 檔案) 。</span><span class="sxs-lookup"><span data-stu-id="6a023-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="6a023-520">取得 Windows 10 (Enterprise、Pro 和家用版的 Microsoft Defender 防毒軟體更新) 、Windows Server 2019 及 Windows Server 2016 安裝影像。</span><span class="sxs-lookup"><span data-stu-id="6a023-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="6a023-521">管理如何下載及套用保護更新</span><span class="sxs-lookup"><span data-stu-id="6a023-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="6a023-522">保護更新可透過許多來源傳遞。</span><span class="sxs-lookup"><span data-stu-id="6a023-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="6a023-523">管理應下載及套用防護更新的時間</span><span class="sxs-lookup"><span data-stu-id="6a023-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="6a023-524">您可以排程應下載保護更新的時間。</span><span class="sxs-lookup"><span data-stu-id="6a023-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="6a023-525">管理已過期端點的更新</span><span class="sxs-lookup"><span data-stu-id="6a023-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="6a023-526">如果端點未接更新或排程的掃描，您可以在下次使用者登入時強制更新或掃描。</span><span class="sxs-lookup"><span data-stu-id="6a023-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="6a023-527">管理事件型強制更新</span><span class="sxs-lookup"><span data-stu-id="6a023-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="6a023-528">您可以設定保護更新，以在啟動時或在某些雲端提供的保護事件之後下載。</span><span class="sxs-lookup"><span data-stu-id="6a023-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="6a023-529">管理行動裝置和虛擬機器 (VM) 的更新</span><span class="sxs-lookup"><span data-stu-id="6a023-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="6a023-530">您可以指定設定，例如是否應該在電池電源上進行更新，對行動裝置和虛擬機器尤其有用。</span><span class="sxs-lookup"><span data-stu-id="6a023-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
