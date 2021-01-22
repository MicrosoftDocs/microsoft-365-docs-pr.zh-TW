---
title: 尋找具有進位搜尋的勒索軟體
description: 使用進一步搜尋來找出可能受勒索軟體影響的裝置。
keywords: 進位搜尋、勒索軟體、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、Microsoft 365、Microsoft Threat Protection、Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f44a649035ef7f5993015142fb65fa29aaf5099f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929502"
---
# <a name="hunt-for-ransomware"></a><span data-ttu-id="7d562-104">搜捕勒索軟體</span><span class="sxs-lookup"><span data-stu-id="7d562-104">Hunt for ransomware</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7d562-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="7d562-105">**Applies to:**</span></span>
- <span data-ttu-id="7d562-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d562-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7d562-107">勒索軟體已從影響個別電腦使用者的簡易惡意惡意攻擊，快速演進為會嚴重影響產業與教育機構的企業威脅。</span><span class="sxs-lookup"><span data-stu-id="7d562-107">Ransomware has rapidly evolved from being simple commodity malware affecting individual computer users to an enterprise threat that is severely impacting industries and government institutions.</span></span> <span data-ttu-id="7d562-108">[雖然 Microsoft 365 Defender](microsoft-threat-protection.md)提供許多可偵測和封鎖勒索軟體及相關入侵活動的功能，但主動檢查入侵符號可協助保護您的網路。</span><span class="sxs-lookup"><span data-stu-id="7d562-108">While [Microsoft 365 Defender](microsoft-threat-protection.md) provides many capabilities that detect and block ransomware and associated intrusion activities, performing proactive checks for signs of compromise can help keep your network protected.</span></span>

> [<span data-ttu-id="7d562-109">閱讀有關以人為方式運作之勒索軟體</span><span class="sxs-lookup"><span data-stu-id="7d562-109">Read about human-operated ransomware</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

<span data-ttu-id="7d562-110">使用[](advanced-hunting-overview.md) Microsoft 365 Defender 中的進進搜尋功能，您可以建立查詢來尋找與勒索軟體活動相關的個別產品。</span><span class="sxs-lookup"><span data-stu-id="7d562-110">With [advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender, you can create queries that locate individual artifacts associated with ransomware activity.</span></span> <span data-ttu-id="7d562-111">您也可以執行更複雜的查詢，以尋找活動符號並衡量這些符號，以尋找需要立即注意的裝置。</span><span class="sxs-lookup"><span data-stu-id="7d562-111">You can also run more sophisticated queries that can look for signs of activity and weigh those signs to find devices that require immediate attention.</span></span>

## <a name="signs-of-ransomware-activity"></a><span data-ttu-id="7d562-112">勒索軟體活動的符號</span><span class="sxs-lookup"><span data-stu-id="7d562-112">Signs of ransomware activity</span></span>
<span data-ttu-id="7d562-113">許多由精密的駭客所啟動的勒索軟體行銷活動中，Microsoft 安全性人員發現各種常見但細微的完成品。</span><span class="sxs-lookup"><span data-stu-id="7d562-113">Microsoft security researchers have observed various common yet subtle artifacts in many ransomware campaigns launched by sophisticated intruders.</span></span> <span data-ttu-id="7d562-114">這些符號大多涉及使用系統工具，以準備加密、防止偵測，以及清除證據。</span><span class="sxs-lookup"><span data-stu-id="7d562-114">These signs mostly involve use of system tools to prepare for encryption, prevent detection, and clear forensic evidence.</span></span>

| <span data-ttu-id="7d562-115">勒索軟體活動</span><span class="sxs-lookup"><span data-stu-id="7d562-115">Ransomware activity</span></span> | <span data-ttu-id="7d562-116">一般工具</span><span class="sxs-lookup"><span data-stu-id="7d562-116">Common tools</span></span> | <span data-ttu-id="7d562-117">Intent</span><span class="sxs-lookup"><span data-stu-id="7d562-117">Intent</span></span> |
|--|--|--|
| <span data-ttu-id="7d562-118">停止程式</span><span class="sxs-lookup"><span data-stu-id="7d562-118">Stop processes</span></span> | <span data-ttu-id="7d562-119">_taskkill.exe，__淨停_</span><span class="sxs-lookup"><span data-stu-id="7d562-119">_taskkill.exe_, _net stop_</span></span> | <span data-ttu-id="7d562-120">確保目標為加密的檔案不會受到各種應用程式鎖定。</span><span class="sxs-lookup"><span data-stu-id="7d562-120">Ensure files targeted for encryption are not locked by various applications.</span></span> |
| <span data-ttu-id="7d562-121">關閉服務</span><span class="sxs-lookup"><span data-stu-id="7d562-121">Turn off services</span></span> | <span data-ttu-id="7d562-122">_sc.exe_</span><span class="sxs-lookup"><span data-stu-id="7d562-122">_sc.exe_</span></span> | <span data-ttu-id="7d562-123">- 確定要加密的檔案並未受到各種應用程式鎖定。</span><span class="sxs-lookup"><span data-stu-id="7d562-123">- Ensure files targeted for encryption are not locked by various applications.</span></span><br><span data-ttu-id="7d562-124">- 防止安全性軟體插斷加密和其他勒索軟體活動。</span><span class="sxs-lookup"><span data-stu-id="7d562-124">- Prevent security software from disrupting encryption and other ransomware activity.</span></span><br><span data-ttu-id="7d562-125">- 停止備份軟體，不建立可復原的複本。</span><span class="sxs-lookup"><span data-stu-id="7d562-125">- Stop backup software from creating recoverable copies.</span></span>  |
| <span data-ttu-id="7d562-126">刪除記錄與檔案</span><span class="sxs-lookup"><span data-stu-id="7d562-126">Delete logs and files</span></span> | <span data-ttu-id="7d562-127">_cipher.exe，_ _wevtutil，_ _fsutil.exe_</span><span class="sxs-lookup"><span data-stu-id="7d562-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span></span> | <span data-ttu-id="7d562-128">移除證據。</span><span class="sxs-lookup"><span data-stu-id="7d562-128">Remove forensic evidence.</span></span> |
| <span data-ttu-id="7d562-129">刪除陰影複本</span><span class="sxs-lookup"><span data-stu-id="7d562-129">Delete shadow copies</span></span>  | <span data-ttu-id="7d562-130">_vsadmin.exe，wmic.exe_ </span><span class="sxs-lookup"><span data-stu-id="7d562-130">_vsadmin.exe_, _wmic.exe_</span></span> | <span data-ttu-id="7d562-131">移除可用來復原加密檔案的光碟機陰影複本。</span><span class="sxs-lookup"><span data-stu-id="7d562-131">Remove drive shadow copies that can be used to recover encrypted files.</span></span> |
| <span data-ttu-id="7d562-132">刪除和停止備份</span><span class="sxs-lookup"><span data-stu-id="7d562-132">Delete and stop backups</span></span> | <span data-ttu-id="7d562-133">_wbadmin.exe_</span><span class="sxs-lookup"><span data-stu-id="7d562-133">_wbadmin.exe_</span></span> | <span data-ttu-id="7d562-134">刪除現有的備份並停止排定的備份工作，防止加密後復原。</span><span class="sxs-lookup"><span data-stu-id="7d562-134">Delete existing backups and stop scheduled backup tasks, preventing recovery after encryption.</span></span> |
| <span data-ttu-id="7d562-135">修改開機設定</span><span class="sxs-lookup"><span data-stu-id="7d562-135">Modify boot settings</span></span> | <span data-ttu-id="7d562-136">_bcdedit.exe_</span><span class="sxs-lookup"><span data-stu-id="7d562-136">_bcdedit.exe_</span></span> | <span data-ttu-id="7d562-137">在加密程式所造成開機失敗後關閉警告和自動修復。</span><span class="sxs-lookup"><span data-stu-id="7d562-137">Turn off warnings and automatic repairs after boot failures that can be caused by the encryption process.</span></span> |
| <span data-ttu-id="7d562-138">關閉修復工具</span><span class="sxs-lookup"><span data-stu-id="7d562-138">Turn off recovery tools</span></span> | <span data-ttu-id="7d562-139"> _schtasks.exe，regedit.exe，_</span><span class="sxs-lookup"><span data-stu-id="7d562-139">_schtasks.exe_, _regedit.exe_,</span></span> | <span data-ttu-id="7d562-140">關閉系統還原和其他系統復原選項。</span><span class="sxs-lookup"><span data-stu-id="7d562-140">Turn off System Restore and other system recovery options.</span></span> |

## <a name="check-for-individual-signs-of-ransomware-activity"></a><span data-ttu-id="7d562-141">檢查勒索軟體活動的個別符號</span><span class="sxs-lookup"><span data-stu-id="7d562-141">Check for individual signs of ransomware activity</span></span>
<span data-ttu-id="7d562-142">許多構成勒索軟體行為的活動，包括上一節所述的活動，都可能是惡意活動。</span><span class="sxs-lookup"><span data-stu-id="7d562-142">Many activities that constitute ransomware behavior, including the activities described in the preceding section, can be benign.</span></span> <span data-ttu-id="7d562-143">使用下列查詢尋找勒索軟體時，請執行多個查詢，檢查相同的裝置是否出現各種可能的勒索軟體活動符號。</span><span class="sxs-lookup"><span data-stu-id="7d562-143">When using the following queries to locate ransomware, run more than one query to check whether the same devices are exhibiting various signs of possible ransomware activity.</span></span>

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a><span data-ttu-id="7d562-144">停止 _使用多個程式taskkill.exe_</span><span class="sxs-lookup"><span data-stu-id="7d562-144">Stopping multiple processes using _taskkill.exe_</span></span>
<span data-ttu-id="7d562-145">此查詢會檢查是否嘗試使用公用程式來停止至少 10 taskkill.exe程式。</span><span class="sxs-lookup"><span data-stu-id="7d562-145">This query checks for attempts to stop at least 10 separate processes using the _taskkill.exe_ utility.</span></span> [<span data-ttu-id="7d562-146">執行查詢</span><span class="sxs-lookup"><span data-stu-id="7d562-146">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a><span data-ttu-id="7d562-147">使用網路 _停止停止停止程式_</span><span class="sxs-lookup"><span data-stu-id="7d562-147">Stopping processes using _net stop_</span></span>
<span data-ttu-id="7d562-148">此查詢會檢查是否嘗試使用 net _stop_ 命令來停止至少 10 個不同的程式。</span><span class="sxs-lookup"><span data-stu-id="7d562-148">This query checks for attempts to stop at least 10 separate processes using the _net stop_ command.</span></span> [<span data-ttu-id="7d562-149">執行查詢</span><span class="sxs-lookup"><span data-stu-id="7d562-149">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a><span data-ttu-id="7d562-150">使用多個磁片磁碟機刪除 _cipher.exe_</span><span class="sxs-lookup"><span data-stu-id="7d562-150">Deletion of data on multiple drives using _cipher.exe_</span></span>
<span data-ttu-id="7d562-151">此查詢會檢查是否嘗試刪除使用多個磁片 _磁碟機的資料_ cipher.exe。</span><span class="sxs-lookup"><span data-stu-id="7d562-151">This query checks for attempts to delete data on multiple drives using _cipher.exe_.</span></span> <span data-ttu-id="7d562-152">此活動通常是由勒索軟體執行，以防止加密後復原資料。</span><span class="sxs-lookup"><span data-stu-id="7d562-152">This activity is typically done by ransomware to prevent recovery of data after encryption.</span></span> [<span data-ttu-id="7d562-153">執行查詢</span><span class="sxs-lookup"><span data-stu-id="7d562-153">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for cipher.exe deleting data from multiple drives
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine),
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1
```

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a><span data-ttu-id="7d562-154">使用 _wevtutil_ 從事件記錄清除證據</span><span class="sxs-lookup"><span data-stu-id="7d562-154">Clearing of forensic evidence from event logs using _wevtutil_</span></span>
<span data-ttu-id="7d562-155">此查詢會檢查是否嘗試使用 _wevtutil_ 從事件記錄清除至少 10 個記錄專案。</span><span class="sxs-lookup"><span data-stu-id="7d562-155">This query checks for attempts to clear at least 10 log entries from event logs using _wevtutil_.</span></span> [<span data-ttu-id="7d562-156">執行查詢</span><span class="sxs-lookup"><span data-stu-id="7d562-156">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a><span data-ttu-id="7d562-157">使用服務關閉 _sc.exe_</span><span class="sxs-lookup"><span data-stu-id="7d562-157">Turning off services using _sc.exe_</span></span>
<span data-ttu-id="7d562-158">此查詢會檢查是否嘗試使用sc.exe關閉至少 10 _個現有sc.exe。_</span><span class="sxs-lookup"><span data-stu-id="7d562-158">This query checks for attempts to turn off at least 10 existing services using _sc.exe_.</span></span> [<span data-ttu-id="7d562-159">執行查詢</span><span class="sxs-lookup"><span data-stu-id="7d562-159">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a><span data-ttu-id="7d562-160">關閉系統還原</span><span class="sxs-lookup"><span data-stu-id="7d562-160">Turning off System Restore</span></span>
<span data-ttu-id="7d562-161">此查詢會識別試圖停止系統還原並防止系統建立還原點，可用於復原勒索軟體加密的資料。</span><span class="sxs-lookup"><span data-stu-id="7d562-161">This query identifies attempts to stop System Restore and prevent the system from creating restore points, which can be used to recover data encrypted by ransomware.</span></span> [<span data-ttu-id="7d562-162">執行查詢</span><span class="sxs-lookup"><span data-stu-id="7d562-162">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
//Pivoting for rundll32  
| where InitiatingProcessFileName =~ 'rundll32.exe'   
//Looking for empty command line   
and InitiatingProcessCommandLine !contains " " and InitiatingProcessCommandLine != ""  
//Looking for schtasks.exe as the created process  
and FileName in~ ('schtasks.exe')  
//Disabling system restore   
and ProcessCommandLine has 'Change' and ProcessCommandLine has 'SystemRestore' 
and ProcessCommandLine has 'disable'
```

### <a name="backup-deletion"></a><span data-ttu-id="7d562-163">備份刪除</span><span class="sxs-lookup"><span data-stu-id="7d562-163">Backup deletion</span></span>
<span data-ttu-id="7d562-164">此查詢會識別資料 _wmic.exe在_ 加密之前刪除陰影複製快照。</span><span class="sxs-lookup"><span data-stu-id="7d562-164">This query identifies use of _wmic.exe_ to delete shadow copy snapshots prior to encryption.</span></span> [<span data-ttu-id="7d562-165">執行查詢</span><span class="sxs-lookup"><span data-stu-id="7d562-165">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a><span data-ttu-id="7d562-166">檢查勒索軟體活動的多個符號</span><span class="sxs-lookup"><span data-stu-id="7d562-166">Check for multiple signs of ransomware activity</span></span>
<span data-ttu-id="7d562-167">您也可以使用完整的查詢來檢查勒索軟體活動的多個符號，以識別受影響的裝置，而不是個別執行多個查詢。</span><span class="sxs-lookup"><span data-stu-id="7d562-167">Instead of running several queries separately, you can also use a comprehensive query that checks for multiple signs of ransomware activity to identify affected devices.</span></span> <span data-ttu-id="7d562-168">下列合併查詢：</span><span class="sxs-lookup"><span data-stu-id="7d562-168">The following consolidated  query:</span></span>
- <span data-ttu-id="7d562-169">尋找勒索軟體活動的相對具體與較低符號</span><span class="sxs-lookup"><span data-stu-id="7d562-169">Looks for both relatively concrete and subtle signs of ransomware activity</span></span>
- <span data-ttu-id="7d562-170">衡量這些符號的顯示狀態</span><span class="sxs-lookup"><span data-stu-id="7d562-170">Weighs the presence of these signs</span></span>
- <span data-ttu-id="7d562-171">識別有較高機會受到勒索軟體攻擊的裝置</span><span class="sxs-lookup"><span data-stu-id="7d562-171">Identifies devices with a higher chance of being targets of ransomware</span></span> 

<span data-ttu-id="7d562-172">執行時，此合併查詢會返回出現多種攻擊符號的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="7d562-172">When run, this consolidated query returns a list of devices that have exhibited multiple signs of attack.</span></span> <span data-ttu-id="7d562-173">也會顯示每種類型的勒索軟體活動計數。</span><span class="sxs-lookup"><span data-stu-id="7d562-173">The count of each type of ransomware activity is also shown.</span></span> <span data-ttu-id="7d562-174">若要執行此合併查詢，請直接複製到進 [位查詢編輯器](https://security.microsoft.com/advanced-hunting)。</span><span class="sxs-lookup"><span data-stu-id="7d562-174">To run this consolidated query, copy it directly to the [advanced hunting query editor](https://security.microsoft.com/advanced-hunting).</span></span> 

```kusto
// Find attempts to stop processes using taskkill.exe
let taskKill = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10;
// Find attempts to stop processes using net stop
let netStop = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10;
// Look for cipher.exe deleting data from multiple drives
let cipher = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine), 
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1;
// Look for use of wevtutil to clear multiple logs
let wevtutilClear = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10;
// Look for sc.exe disabling services
let scDisable = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10;
// Main query for counting and aggregating evidence
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "vssadmin.exe" and ProcessCommandLine has_any("list shadows", "delete shadows")
or FileName =~ "fsutil.exe" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal"
or ProcessCommandLine has("bcdedit") and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures")
or ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup")
or (ProcessCommandLine has "wevtutil" and ProcessCommandLine has "cl") 
or (ProcessCommandLine has "wmic" and ProcessCommandLine has "shadowcopy delete")
or (ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled")
| extend Bcdedit = iff(ProcessCommandLine has "bcdedit" and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures"), 1, 0)
| extend ShadowCopyDelete = iff (ProcessCommandLine has "shadowcopy delete", 1, 0)
| extend VssAdminShadows = iff(ProcessCommandLine has "vssadmin" and ProcessCommandLine has_any("list shadows", "delete shadows"), 1, 0)
| extend Wbadmin = iff(ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup"), 1,0)
| extend Fsutil = iff(ProcessCommandLine has "fsutil" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal", 1, 0)
| summarize FirstActivity = min(Timestamp), ReportId = any(ReportId), Commands = make_set(ProcessCommandLine) by DeviceId, Fsutil, Wbadmin, ShadowCopyDelete, Bcdedit, VssAdminShadows, bin(Timestamp, 6h)
// Joining extra evidence
| join kind=leftouter (wevtutilClear) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (cipher) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (netStop) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (taskKill) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (scDisable) on $left.DeviceId == $right.DeviceId
| extend WevtutilUse = iff(LogClearCount > 10, 1, 0)
| extend CipherUse = iff(CipherCount > 1, 1, 0)
| extend NetStopUse = iff(netStopCount > 10, 1, 0)
| extend TaskkillUse = iff(taskKillCount > 10, 1, 0)
| extend ScDisableUse = iff(ScDisableCount > 10, 1, 0)
// Adding up all evidence
| mv-expand CommandList = NetStopList, TaskKillList, ClearedLogList, CipherList, Commands, ScDisableList
// Format results
| summarize BcdEdit = iff(make_set(Bcdedit) contains "1" , 1, 0), NetStop10PlusCommands = iff(make_set(NetStopUse) contains "1", 1, 0), Wevtutil10PlusLogsCleared = iff(make_set(WevtutilUse) contains "1", 1, 0),
CipherMultipleDrives = iff(make_set(CipherUse) contains "1", 1, 0), Fsutil = iff(make_set(Fsutil) contains "1", 1, 0), ShadowCopyDelete = iff(make_set(ShadowCopyDelete) contains "1", 1, 0),
Wbadmin = iff(make_set(Wbadmin) contains "1", 1, 0), TaskKill10PlusCommand = iff(make_set(TaskkillUse) contains "1", 1, 0), VssAdminShadow = iff(make_set(VssAdminShadows) contains "1", 1, 0), 
ScDisable = iff(make_set(ScDisableUse) contains "1", 1, 0), TotalEvidenceCount = count(CommandList), EvidenceList = make_set(Commands), StartofBehavior = min(FirstActivity) by DeviceId, bin(Timestamp, 1d)
| extend UniqueEvidenceCount = BcdEdit + NetStop10PlusCommands + Wevtutil10PlusLogsCleared + CipherMultipleDrives + Wbadmin + Fsutil + TaskKill10PlusCommand + VssAdminShadow + ScDisable + ShadowCopyDelete
| where UniqueEvidenceCount > 2
```
### <a name="understand-and-tweak-the-query-results"></a><span data-ttu-id="7d562-175">瞭解並調整查詢結果</span><span class="sxs-lookup"><span data-stu-id="7d562-175">Understand and tweak the query results</span></span>
<span data-ttu-id="7d562-176">合併查詢會返回下列結果：</span><span class="sxs-lookup"><span data-stu-id="7d562-176">The consolidated query returns the following results:</span></span>

- <span data-ttu-id="7d562-177">**DeviceId**—識別受影響的裝置</span><span class="sxs-lookup"><span data-stu-id="7d562-177">**DeviceId**—identifies the affected device</span></span> 
- <span data-ttu-id="7d562-178">**TimeStamp**- 第一次在裝置上觀察勒索軟體活動的任何符號</span><span class="sxs-lookup"><span data-stu-id="7d562-178">**TimeStamp**—first time any sign of ransomware activity was observed on the device</span></span>
- <span data-ttu-id="7d562-179">**特定活動符號**-多個欄中顯示的每個符號計數，例如 _BcdEdit_ 或 _FsUtil_</span><span class="sxs-lookup"><span data-stu-id="7d562-179">**Specific signs of activity**—the count for each sign shown in multiple columns, such as _BcdEdit_ or _FsUtil_</span></span>
- <span data-ttu-id="7d562-180">**TotalEvidenceCount**—觀察符號的數量</span><span class="sxs-lookup"><span data-stu-id="7d562-180">**TotalEvidenceCount**—number of observed signs</span></span>
- <span data-ttu-id="7d562-181">**UniqueEvidenceCount**— 觀察符號的類型數目</span><span class="sxs-lookup"><span data-stu-id="7d562-181">**UniqueEvidenceCount**—number of types of observed signs</span></span>

![勒索軟體活動的查詢結果影像](../../media/advanced-hunting-ransomware-query.png)

<span data-ttu-id="7d562-183">*查詢結果顯示受影響的裝置，以及勒索軟體活動的各種符號計數*</span><span class="sxs-lookup"><span data-stu-id="7d562-183">*Query results showing affected devices and counts of various signs of ransomware activity*</span></span>

<span data-ttu-id="7d562-184">根據預設，查詢結果只會列出擁有兩種以上勒索軟體活動的裝置。</span><span class="sxs-lookup"><span data-stu-id="7d562-184">By default, the query result lists only devices that have more than two types of ransomware activity.</span></span> <span data-ttu-id="7d562-185">若要查看所有具有勒索軟體活動符號的裝置，請修改下列運算子，將數位設為零 `where` (0) 。</span><span class="sxs-lookup"><span data-stu-id="7d562-185">To see all devices with any sign of ransomware activity, modify the following `where` operator and set the number to zero (0).</span></span> <span data-ttu-id="7d562-186">若要看到較少的裝置，請設定較高的數量。</span><span class="sxs-lookup"><span data-stu-id="7d562-186">To see fewer devices, set a higher number.</span></span> 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a><span data-ttu-id="7d562-187">相關主題</span><span class="sxs-lookup"><span data-stu-id="7d562-187">Related topics</span></span>
- [<span data-ttu-id="7d562-188">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="7d562-188">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7d562-189">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="7d562-189">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7d562-190">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="7d562-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="7d562-191">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="7d562-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7d562-192">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="7d562-192">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7d562-193">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="7d562-193">Apply query best practices</span></span>](advanced-hunting-best-practices.md)