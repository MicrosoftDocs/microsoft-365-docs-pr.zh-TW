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
ms.date: 06/14/2021
ms.openlocfilehash: 1c7ff52398e048aa34fd9c5ab3d8edd1004ea5ec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929440"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>管理 Microsoft Defender 防毒軟體更新及套用基準

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 防毒軟體

將 Microsoft Defender 防毒軟體保持在最新狀態，是確保您的裝置具備防範新惡意程式碼和攻擊技巧所需的最新技術和功能。 請務必更新防防毒保護，即使 Microsoft Defender 防毒軟體是以[被動模式](microsoft-defender-antivirus-compatibility.md)執行。 有兩種與 Microsoft Defender 防毒軟體保持最新狀態相關的更新：

- 安全性智慧更新
- 產品更新

> [!TIP]
> 若要查看最新的引擎、平臺及簽字日期，請造訪[Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體的安全性情報更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)

## <a name="security-intelligence-updates"></a>安全性智慧更新

Microsoft Defender 防毒軟體使用[雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md) (也稱為 Microsoft Advanced protection 服務或對應) ，定期下載安全性情報更新，以提供保護。

> [!NOTE]
> 更新會在下列 KB 編號之下發行：  
> - Microsoft Defender 防毒軟體： KB2267602  
> - System Center Endpoint Protection： KB2461484

雲端傳送保護功能永遠都是開啟的，且需要網際網路連線才能運作。 安全智慧更新會在排程的節奏上進行， (可透過原則) 設定。 如需詳細資訊，請參閱[在 Microsoft Defender 防毒軟體中使用 Microsoft 雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md)。 

如需最近的安全性情報更新清單，請參閱[Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體的安全性情報更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。

引擎更新包含在安全性智慧更新中，並以每月的節奏發行。

## <a name="product-updates"></a>產品更新

Microsoft Defender 防毒軟體需要 [每月更新 (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (稱為 *平臺更新*) ，而且會在 Windows 10 版本的情況下收到重要的功能更新。

您可以透過下列其中一種方法來管理更新的發佈： 

- [Windows伺服器更新服務 (WSUS) ](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- 您用來部署 Microsoft 和 Windows 網路中端點更新的常用方法。

如需詳細資訊，請參閱[管理來源以取得 Microsoft Defender 防毒軟體保護更新](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。

> [!NOTE]
> 每月更新都會以階段發行，導致您的 [視窗伺服器更新服務](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)中顯示多個套件。

## <a name="monthly-platform-and-engine-versions"></a>每月平臺及引擎版本

如需如何更新或安裝平臺更新的資訊，請參閱[Windows Defender 的反惡意程式碼平臺更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。

我們所有的更新均包含 
- 效能改進;
- 可維護性改進;和 
-  (Cloud [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)) 的整合增強功能。
<br/><br/>
<details>
<summary> 2021年5月 (平臺： 4.18.2105.4 |Engine： 1.1.18200.4) </summary>

&ensp;安全性智慧更新版本： **1.341.8.0**  
&ensp;發行日期： **2021 年6月3日**  
&ensp;Platform： **4.18.2105.4**  
&ensp;Engine： **1.1.18200.4**  
&ensp;支援階段： **安全性和重要更新**
    
### <a name="whats-new"></a>新增功能
- [行為監控](client-behavioral-blocking.md)的增強功能 
- 固定 [網路保護](network-protection.md) 通知篩選功能

### <a name="known-issues"></a>已知問題
無已知問題  
<br/>
</details><details>
<summary> 四月-2021 (平臺： 4.18.2104.14 |Engine： 1.1.18100.5) </summary>

&ensp;安全性智慧更新版本： **1.337.2.0**  
&ensp;發行日期： **2021 年4月26日**  (Engine：發行1.1.18100.6 可能是5、2021) &ensp; Platform： **4.18.2104.14**  
&ensp;Engine： **1.1.18100.5**  
&ensp;支援階段： **安全性和重要更新**
    
### <a name="whats-new"></a>新增功能
- 其他行為監控邏輯
- 改進的核心模式 keylogger 偵測

### <a name="known-issues"></a>已知問題
無已知問題  
<br/>
</details><details>
<summary> 三月份-2021 (平臺： 4.18.2103.7 |Engine： 1.1.18000.5) </summary>

&ensp;安全性智慧更新版本： **1.335.36.0**  
&ensp;發行日期： **2021 年4月2日**  
&ensp;Platform： **4.18.2103.7**  
&ensp;Engine： **1.1.18000.5**  
&ensp;支援階段： **安全性和重要更新**
    
### <a name="whats-new"></a>新增功能

- 改進行為監控引擎 
- 擴充網路暴力攻擊緩解 
- 啟用 [防篡改保護](prevent-changes-to-security-settings-with-tamper-protection.md) 時，其他失敗的篡改嘗試事件產生

### <a name="known-issues"></a>已知問題
無已知問題  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>舊版本更新：僅限技術升級支援

發行新的套件版本之後，支援舊版的兩個版本只會縮小為技術支援。 這一節所列出的版本舊，僅提供支援技術升級。 
<br/><br/>
<details>
<summary> 二月份-2021 (平臺： 4.18.2102.3 |Engine： 1.1.17900.7) </summary>

&ensp;安全性智慧更新版本： **1.333.7.0**  
&ensp;發行日期： **2021 年3月9日**  
&ensp;Platform： **4.18.2102.3**  
&ensp;Engine： **1.1.17900.7**  
&ensp;支援階段： **僅限技術升級支援 ()**
    
### <a name="whats-new"></a>新增功能

- 透過[防篡改保護](prevent-changes-to-security-settings-with-tamper-protection.md)改進服務復原
- 擴充不可篡改的保護範圍

### <a name="known-issues"></a>已知問題
無已知問題  
<br/>
</details><details>
<summary> 2021年1月 (平臺： 4.18.2101.9 |Engine： 1.1.17800.5) </summary>

&ensp;安全性智慧更新版本： **1.327.1854.0**  
&ensp;發行日期： **2021 年2月2日**  
&ensp;Platform： **4.18.2101.9**  
&ensp;Engine： **1.1.17800.5**  
&ensp;支援階段： **僅限技術升級支援 ()**
    
### <a name="whats-new"></a>新增功能

- 外殼代碼利用偵測增強功能
- 增強認證竊取嘗試的知名度
- Microsoft Defender 防毒軟體服務中的 antitampering 功能的增強功能
- 改進支援 ARM x64 模擬
- 修正：在即時保護執行初始偵測後，威脅史中仍會保留 EDR 封鎖通知

### <a name="known-issues"></a>已知問題
無已知問題  
<br/>
</details><details>
<summary> 11月-2020 (平臺： 4.18.2011.6 |Engine： 1.1.17700.4) </summary>

&ensp;安全性智慧更新版本： **1.327.1854.0**  
&ensp;發行日期： **2020 年12月**  
&ensp;Platform： **4.18.2011.6**  
&ensp;Engine： **1.1.17700.4**  
&ensp;支援階段： **僅限技術升級支援 ()**
    
### <a name="whats-new"></a>新增功能

- 改進的 [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 狀態支援記錄

### <a name="known-issues"></a>已知問題
無已知問題  
<br/>
</details><details>
<summary> 十月-2020 (平臺： 4.18.2010.7 |Engine： 1.1.17600.5) </summary>

&ensp;安全性智慧更新版本： **1.327.7.0**  
&ensp;發行日期： **2020 年10月29日**  
&ensp;Platform： **4.18.2010.7**  
&ensp;Engine： **1.1.17600.5**  
&ensp;支援階段： **僅限技術升級支援 ()**
    
### <a name="whats-new"></a>新增功能

- 特殊威脅類別的新描述
- 改進模擬功能
- 改進的主機位址允許/封鎖功能
- 在 Defender CSP 中新增選項，以忽略本機使用者排除的合併

### <a name="known-issues"></a>已知問題

無已知問題  
<br/>
</details><details>
<summary> 九月份-2020 (平臺： 4.18.2009.7 |Engine： 1.1.17500.4) </summary>

&ensp;安全性智慧更新版本： **1.325.10.0**  
&ensp;發行日期： **2020 年10月1日**  
&ensp;Platform： **4.18.2009.7**  
&ensp;Engine： **1.1.17500.4**  
&ensp;支援階段： **僅限技術升級支援 ()**
    
### <a name="whats-new"></a>新增功能

- 需要有系統管理員許可權，才能還原隔離中的檔案
- 現在支援 XML 格式化的事件
- 用於忽略排除合併的 CSP 支援
- 下列專案的新管理介面：
   - UDP 檢查
   - 伺服器2019上的網路保護
   - 網路保護的 IP 位址排除
- 改善 TPM 測量的可見度
- 改進的 Office VBA 模組掃描

### <a name="known-issues"></a>已知問題

無已知問題  
<br/>
</details>
<details>
<summary> 八月-2020 (平臺： 4.18.2008.9 |Engine： 1.1.17400.5) </summary>

&ensp;安全性智慧更新版本： **1.323.9.0**  
&ensp;發行日期： **2020 年8月27日**  
&ensp;Platform： **4.18.2008.9**  
&ensp;Engine： **1.1.17400.5**  
&ensp;支援階段： **僅限技術升級支援 ()**

### <a name="whats-new"></a>新增功能

- 新增更多遙測事件
- 改進的掃描事件遙測
- 改進的記憶體掃描行為監控
- 改進的宏資料流程掃描
- 新增 `AMRunningMode` 至 Get-MpComputerStatus PowerShell Cmdlet
- 會忽略[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 。 Microsoft Defender 防毒軟體會在偵測其他防毒程式時自動開啟自身。


### <a name="known-issues"></a>已知問題
無已知問題  
<br/>
</details>

<details>
<summary> 2020年7月- (平臺： 4.18.2007.8 |Engine： 1.1.17300.4) </summary>

&ensp;安全性智慧更新版本： **1.321.30.0**  
&ensp;發行日期： **2020 年7月28日**  
&ensp;Platform： **4.18.2007.8**  
&ensp;Engine： **1.1.17300.4**  
&ensp;支援階段： **僅限技術升級支援 ()**
    
### <a name="whats-new"></a>新增功能

- 改進的遙測的 BITS
- 改進的驗證碼簽名憑證驗證

### <a name="known-issues"></a>已知問題
無已知問題  
<br/>
</details>

<details>
<summary> 六月-2020 (平臺： 4.18.2006.10 |Engine： 1.1.17200.2) </summary>

&ensp;安全性智慧更新版本： **1.319.20.0**  
&ensp;發行日期： **2020 年6月22日**  
&ensp;Platform： **4.18.2006.10**  
&ensp;Engine： **1.1.17200.2**  
&ensp;支援階段： **僅限技術升級支援 ()**
    
### <a name="whats-new"></a>新增功能

- 可能指定[支援記錄](./collect-diagnostic-data.md)檔的位置
- 在被動模式中略過積極 catchup 掃描。
- 允許 Defender 在流量計費的連線上更新
- 停用快取時的固定效能調整 
- 固定登錄查詢 
- ADMX 中的固定 scantime 隨機化

### <a name="known-issues"></a>已知問題
無已知問題  
<br/>
</details>

<details>
<summary> 2020年5月 (平臺： 4.18.2005.4 |Engine： 1.1.17100.2) </summary>

&ensp;安全性智慧更新版本： **1.317.20.0**  
&ensp;發行日期： **2020 年5月26日**  
&ensp;Platform： **4.18.2005.4**  
&ensp;Engine： **1.1.17100.2**  
&ensp;支援階段： **僅限技術升級支援 ()**
    
### <a name="whats-new"></a>新增功能

- 改進的掃描事件記錄
- 改進的使用者模式損毀處理。
- 新增防篡改保護的事件追蹤
- 修正 AMSI 範例提交
- 固定 AMSI Cloud 封鎖
- 修正的安全性更新安裝記錄檔

### <a name="known-issues"></a>已知問題
無已知問題  
<br/>
</details>

<details>
<summary> 四月-2020 (平臺： 4.18.2004.6 |Engine： 1.1.17000.2) </summary>

&ensp;安全性智慧更新版本： **1.315.12.0**  
&ensp;發行日期： **2020 年4月30日**  
&ensp;Platform： **4.18.2004.6**  
&ensp;Engine： **1.1.17000.2**  
&ensp;支援階段： **僅限技術升級支援 ()**
    
### <a name="whats-new"></a>新增功能
- WDfilter 改進功能
- 新增更具可操作性的事件資料至攻擊面減少偵測事件
- 診斷資料和 WMI 中的固定版本資訊
- 在平臺更新後在 UI 中修復不正確的平臺版本
- 動態 URL intel for Fileless 威脅防護
- UEFI 掃描功能
- 擴充更新記錄

### <a name="known-issues"></a>已知問題
無已知問題  
<br/>
</details>

<details>
<summary> 三月份-2020 (平臺： 4.18.2003.8 |Engine： 1.1.16900.2) </summary>

&ensp;安全性智慧更新版本： **1.313.8.0**  
&ensp;發行日期： **2020 年3月24日**  
&ensp;Platform： **4.18.2003.8**  
&ensp;Engine： **1.1.16900.4**  
&ensp;支援階段： **僅限技術升級支援 ()**
    
### <a name="whats-new"></a>新增功能

- 新增至[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 節流選項
- 改善診斷功能
- 降低安全性情報超時 (5 分鐘) 
- 擴充 AMSI 引擎內部記錄功能
- 改進處理常式封鎖的通知
   
### <a name="known-issues"></a>已知問題
[**Fixed**]Microsoft Defender 防毒軟體會在執行掃描時略過檔案。

<br/>
</details>

<details>

<summary> 二月份-2020 (平臺： |Engine： 1.1.16800.2) </summary>
  

&ensp;安全性智慧更新版本： **1.311.4.0**   
&ensp;發行日期： **2020 年2月25日**  
&ensp;平臺/用戶端： **-**  
&ensp;Engine： **1.1.16800.2**  
&ensp;支援階段： **僅限技術升級支援 ()**
     
### <a name="whats-new"></a>新增功能

  
### <a name="known-issues"></a>已知問題
無已知問題
<br/>
</details>

<details>
<summary> 2020年1月 (平臺： 4.18.2001.10 |Engine： 1.1.16700.2) </summary>
  

安全性智慧更新版本： **1.309.32.0**  
發行日期： **2020 年1月30日**  
Platform/Client： **4.18.2001.10**  
Engine： **1.1.16700.2**  
&ensp;支援階段： **僅限技術升級支援 ()**
     
### <a name="whats-new"></a>新增功能

- 具有 Exchange 的 WS2016 上的固定 BSOD
- 當 TMP 重新導向至網路路徑時支援平臺更新
- 平臺和引擎版本已新增至 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- 將緊急特徵碼更新擴充為 [被動模式](./microsoft-defender-antivirus-compatibility.md)
- 修正4.18.1911.3 懸掛
   
### <a name="known-issues"></a>已知問題

[**Fixed**] 採用 [新式待機模式](/windows-hardware/design/device-experiences/modern-standby)的裝置可能會在 Windows Defender 篩選器驅動程式遇到中斷，從而導致保護的缺口。  受影響的機器會因尚未更新為最新的反惡意程式碼平臺而向客戶呈現。  
<br/>
> [!IMPORTANT]
> 此更新如下：
> - 由執行低版本平臺的 RS1 裝置所需，以支援 SHA2;
> - 具有懸掛問題的系統重新開機標誌;
> - 會在4月2020內重新發佈，而且不會被更新的更新取代以保留未來的可用性;  
> - 因重新開機要求而分類為更新和
> - 只會以[Windows 更新](https://support.microsoft.com/help/4027667/windows-10-update)提供。
<br/>
</details>

<details>
<summary> 11月-2019 (平臺： 4.18.1911.3 |Engine： 1.1.16600.7) </summary>

安全性智慧更新版本： **1.307.13.0**  
發行日期： **2019 月7日**  
Platform： **4.18.1911.3**  
Engine： **1.1.17000.7**  
支援階段： **不支援**  
     
### <a name="whats-new"></a>新增功能

- 固定 MpCmdRun 追蹤層級
- 固定 WDFilter 版本資訊
-  (PUA) 提升通知
- 新增 MRT.LOG 記錄以支援檔案
   
### <a name="known-issues"></a>已知問題
安裝此更新時，裝置需要「跳過套件4.18.2001.10」才能更新為最新的平臺版本。
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Microsoft Defender 防毒軟體平臺支援
平臺和引擎更新是以每月節奏提供。 若要完全支援，請使用最新的平臺更新來保持最新狀態。 我們的支援結構是動態的，而且會根據最新平臺版本的可用性而演變成兩個階段：

- **安全性和重要更新服務階段** -執行最新的平臺版本時，您將有資格收到反惡意程式碼平臺的安全性和重要更新。
 
- **僅限) 階段的技術支援 (** 。發行新的平臺版本之後，支援較舊版本 (n-1) 只會降低技術支援。 不再支援非 N-2 版本的平臺。

\*將繼續提供技術支援，以供從 Windows 10 發行版本本升級 (請參閱[Windows 10 版本隨附的平臺版本](#platform-version-included-with-windows-10-releases)) 至最新的平臺版本。

在技術支援 (只有) 階段，將會透過 Microsoft 客戶服務 & 支援和 Microsoft 受管理的支援服務， (例如 Premier Support) ，供應商業上合理的支援事件。 如果支援事件需要升級開發以取得進一步的指導方針、需要非安全性更新，或需要安全性更新，則系統會要求客戶升級至最新的平臺版本或中級更新 ( * ) 。

### <a name="platform-version-included-with-windows-10-releases"></a>Windows 10 版本隨附的平臺版本
下表提供隨附于最新 Windows 10 版本的 Microsoft Defender 防毒軟體平臺和引擎版本：    

|Windows 10 版本  |平臺版本  |引擎版本 |支援階段 |
|:---|:---|:---|:---|
|2004 (20H1/20H2)  |4.18.1909.6 |1.1.17000.2 | 技術升級只支援 ()  |
|1909 (19H2)  |4.18.1902.5 |1.1.16700.3 | 技術升級只支援 ()  |
|1903 (19H1)  |4.18.1902.5 |1.1.15600.4 | 技術升級只支援 ()  |
|1809 (RS5)  |4.18.1807.18075 |1.1.15000.2 | 技術升級只支援 ()  |
|1803 (RS4)  |4.13.17134.1 |1.1.14600.4 | 技術升級只支援 ()  |
|1709 (RS3)  |4.12.16299.15 |1.1.14104.0 | 技術升級只支援 ()  |
|1703 (RS2)  |4.11.15603.2 |1.1.13504.0 | 技術升級只支援 ()  |
|1607 (RS1)  |4.10.14393.3683 |1.1.12805.0 | 技術升級只支援 ()  |  

如需 Windows 10 版本資訊，請參閱[Windows 生命週期事實資料表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>更新部署映像服務與管理 (DISM) 

建議您更新 Windows 10 (Enterprise、Pro 及 Home edition) 、Windows Server 2019，以及 Windows Server 2016 OS 安裝影像與最新的防病毒和反惡意軟體更新。 將您的作業系統安裝影像保持在最新狀態，可協助避免保護方面的缺口。 

如需詳細資訊，請參閱[Microsoft Defender update for Windows 作業系統安裝影像](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。

<details>
<summary>1.1.2106.01</summary>

&ensp;套件版本： **1.1.2106.01**    
&ensp;平臺版本： **4.18.2104.14**   
&ensp;引擎版本： **1.1.18100.6**  
&ensp;簽章版本： **1.339.1923.0**    
    
### <a name="fixes"></a>修復
- 無

### <a name="additional-information"></a>其他資訊
- 無  
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;套件版本： **1.1.2105.01**    
&ensp;平臺版本： **4.18.2103.7**   
&ensp;引擎版本： **1.1.18100.6**  
&ensp;簽章版本： **1.339.42.0**    
    
### <a name="fixes"></a>修復
- 無

### <a name="additional-information"></a>其他資訊
- 無  
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;套件版本： **1.1.2104.01**    
&ensp;平臺版本： **4.18.2102.4**   
&ensp;引擎版本： **1.1.18000.5**  
&ensp;簽章版本： **1.335.232.0**    
    
### <a name="fixes"></a>修復
- 無

### <a name="additional-information"></a>其他資訊
- 無  
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;套件版本： **1.1.2103.01**    
&ensp;平臺版本： **4.18.2101.9**   
&ensp;引擎版本： **1.1.17800.5**  
&ensp;簽章版本： **1.331.2302.0**    
    
### <a name="fixes"></a>修復
- 無

### <a name="additional-information"></a>其他資訊
- 無  
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;套件版本： **1.1.2102.03**    
&ensp;平臺版本： **4.18.2011.6**   
&ensp;引擎版本： **1.1.17800.5**  
&ensp;簽章版本： **1.331.174.0**    
    
### <a name="fixes"></a>修復
- 無

### <a name="additional-information"></a>其他資訊
- 無  
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;套件版本： **1.1.2101.02**    
&ensp;平臺版本： **4.18.2011.6**   
&ensp;引擎版本： **1.1.17700.4**  
&ensp;簽章版本： **1.329.1796.0**    
    
### <a name="fixes"></a>修復
- 無

### <a name="additional-information"></a>其他資訊
- 無  
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;套件版本： **1.1.2012.01**    
&ensp;平臺版本： **4.18.2010.7**   
&ensp;引擎版本： **1.1.17600.5**  
&ensp;簽章版本： **1.327.1991.0**    
    
### <a name="fixes"></a>修復
- 無

### <a name="additional-information"></a>其他資訊
- 無  
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;套件版本： **1.1.2011.02**    
&ensp;平臺版本： **4.18.2010.7**   
&ensp;引擎版本： **1.1.17600.5**  
&ensp;簽章版本： **1.327.658.0**    
    
### <a name="fixes"></a>修復
- 無

### <a name="additional-information"></a>其他資訊
- 更新 Microsoft Defender 防毒軟體簽章  
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;套件版本： **1.1.2011.01**    
&ensp;平臺版本： **4.18.2009.7**  
&ensp;引擎版本： **1.1.17600.5**  
&ensp;簽章版本： **1.327.344.0**    
    
### <a name="fixes"></a>修復
- 無

### <a name="additional-information"></a>其他資訊
- 無  
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;套件版本： **1.1.2011.01**    
&ensp;平臺版本： **4.18.2008.9**   
&ensp;引擎版本： **1.1.17400.5**  
&ensp;簽章版本： **1.327.2216.0**    
    
### <a name="fixes"></a>修復
- 無

### <a name="additional-information"></a>其他資訊
- 新增對 Windows 10 RS1 或更新版本作業系統安裝影像的支援。  
<br/>
</details>

## <a name="additional-resources"></a>其他資源

| 文章 | 描述  |
|:---|:---|
|[適用于 Windows 作業系統安裝映射的 Microsoft Defender 更新](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | 查看您 OS 安裝映射的反惡意軟體更新軟體包 (WIM 和 VHD 檔案) 。 取得 Windows 10 (Enterprise、Pro 和家用版的 Microsoft Defender 防毒軟體更新) 、Windows Server 2019 及 Windows Server 2016 安裝影像。  |
|[管理如何下載及套用保護更新](manage-protection-updates-microsoft-defender-antivirus.md) | 保護更新可透過許多來源傳遞。 |
|[管理應下載及套用防護更新的時間](manage-protection-update-schedule-microsoft-defender-antivirus.md) | 您可以排程應下載保護更新的時間。 |
|[管理已過期端點的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) | 如果端點未接更新或排程的掃描，您可以在下次使用者登入時強制更新或掃描。 |
|[管理事件型強制更新](manage-event-based-updates-microsoft-defender-antivirus.md) | 您可以設定保護更新，以在啟動時或在某些雲端提供的保護事件之後下載。 |
|[管理行動裝置和虛擬機器 (VM) 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| 您可以指定設定，例如是否應該在電池電源上進行更新，對行動裝置和虛擬機器尤其有用。 |
