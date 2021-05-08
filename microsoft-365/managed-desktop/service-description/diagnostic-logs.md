---
title: 診斷記錄
description: 疑難排解時可能會從裝置收集的記錄，以及如何儲存這些記錄
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272886"
---
# <a name="diagnostic-logs"></a>診斷記錄

當我們對 Microsoft 受管理的電腦所管理的裝置進行疑難排解時，無論您是否已報告或由我們服務識別的裝置，我們可能必須從該裝置收集特定的診斷記錄，而不需要使用者介入。 我們不會從使用者目錄收集任何使用者產生的內容或資訊。 我們只收集關心裝置健康情況和狀態的診斷和記錄資料。

我們會將任何收集的記錄儲存一28天，然後加以刪除。 我們處理 [資料處理標準](privacy-personal-data.md)之後從裝置收集到的任何記錄。

## <a name="data-collected"></a>收集的資料

此清單包含 Microsoft 受管理的電腦可能收集診斷記錄的所有資料夾、事件記錄檔、可執行檔或登錄位置。 收集的實際資料會是此清單的子集，視已識別的問題而定。

### <a name="registry-keys"></a>登錄機碼

- HKLM \\ 系統 \\ CurrentControlSet \\ 服務
- HKLM \\ 軟體 \\ Microsoft \\ Surface
- HKLM \\ 軟體 \\ 原則 \\ Microsoft \\ Windows \\ WindowsUpdate
- HKLM \\ 系統 \\ CurrentControlSet \\ 控制 \\ MUI \\ UILanguages
- HKLM \\ 軟體 \\ 原則 \\ Microsoft \\ WindowsStore
- HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate
- HKLM \\ 軟體 \\ Microsoft \\ Windows NT \\ CurrentVersion
- HKLM \\ 軟體 \\ Microsoft \\ Windows NT \\ CurrentVersion
- HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ AppModel
- HKLM \\ SYSTEM \\ CurrentControlSet \\ 控制 \\ FirmwareResources
- HKLM \\ 軟體 \\ Microsoft \\ WindowsSelfhost
- HKLM \\ 軟體 \\ Microsoft \\ WindowsUpdate
- HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ Appx
- HKLM \\ 軟體 \\ Microsoft \\ Windows NT \\ CurrentVersion \\ Superfetch
- HKLM \\ 系統 \\ 設定
- HKLM \\ 軟體 \\ Microsoft \\ IntuneManagementExtension
- HKLM \\ 軟體 \\ Microsoft \\ SystemCertificates \\ AuthRoot
- HKLM \\ 軟體 \\ Microsoft \\ Windows 高級威脅防護
- HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ 驗證 \\ LogonUI
- HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ Internet 設定
- HKLM \\ 軟體 \\ Microsoft \\ Windows \\ CurrentVersion \\ 卸載
- HKLM \\ 軟體 \\ 原則
- HKLM \\ 軟體 \\ 原則 \\ Microsoft \\ 加密 \\ 設定 \\ SSL
- HKLM \\ 軟體 \\ 原則 \\ Microsoft \\ Windows 高級威脅防護
- HKLM \\ 軟體 \\ WOW6432Node \\ Microsoft \\ Windows \\ CurrentVersion \\ 卸載
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL

### <a name="commands"></a>命令

- % programfiles% \\ windows defender \\mpcmdrun.exe-GetFiles
- % windir% \\ system32 \\certutil.exe-儲存區
- % windir% \\ system32 \\certutil.exe-store-使用者 my
- % windir% \\ system32 \\Dsregcmd.exe/status
- % windir% \\ system32 \\ipconfig.exe/all
- % windir% \\ system32 \\ipconfig.exe/displaydns
- % windir% \\ system32 \\mdmdiagnosticstool.exe
- % windir% \\ system32 \\msinfo32.exe/report% temp% \\ MDMDiagnostics \\ msinfo32，記錄檔
- % windir% \\ system32 \\netsh.exe advfirewall show allprofiles
- % windir% \\ system32 \\netsh.exe advfirewall show global
- % windir% \\ system32 \\netsh.exe lan 顯示設定檔
- % windir% \\ system32 \\netsh.exe winHTTP 顯示 proxy
- % windir% \\ system32 \\netsh.exe wlan 顯示設定檔
- % windir% \\ system32 \\netsh.exe wlan show wlanreport
- % windir% \\ system32 \\ping.exe-n 50 localhost
- % windir% \\ system32 \\powercfg.exe/batteryreport/output% temp% \\ MDMDiagnostics \\battery-report.html
- % windir% \\ system32 \\powercfg.exe/energy/output% temp% \\ MDMDiagnostics \\energy-report.html
- bitsadmin/list/allusers/verbose
- fltMC.exe
- bcdedit/enum all/v
- manage-bde-保護-取得
- Windows PowerShell 命令：
    - Appxpackage-allusers
    - Appxpackage-packagetype 型捆綁
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject 類別的 win32 \_ 產品
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32 \_ PnPSignedDriver

### <a name="event-logs"></a>事件記錄檔

- 應用程式
- Microsoft-Windows-AppLocker/EXE 和 DLL
- Microsoft-Windows-AppLocker/MSI 及腳本
- Microsoft-Windows-AppLocker/封裝應用程式部署
- Microsoft-Windows-AppLocker/封裝應用程式-執行
- Microsoft-Windows-bitlocker/bitlocker 管理
- Microsoft-Windows 感知/運作
- Microsoft-Windows SenseIR/運作
- 設定
- 系統

### <a name="files"></a>檔案

- % ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ 收集器 \\ \* .etl
- % ProgramData% \\ Microsoft \\ IntuneManagementExtension \\ 記錄檔 \\ \* 。\*
- % ProgramData% \\ Microsoft \\ Windows Defender \\ 支援 \\MpSupportFiles.cab
- % ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html
- % ProgramData% \\ Microsoft \\ Windows \\ WlanReport-SourceFileName wlan-report-latest.html
- % windir% \\ ccm \\ 記錄檔 \* 記錄檔
- % windir% \\ ccmsetup \\ 記錄檔 \* 記錄檔
- % windir% \\ 記錄 \\ CBS \\ cbs 記錄
- % windir% \\ 記錄檔 \\ measuredboot \* 。\*
- % windir% \\ 記錄 \\ WindowsUpdate \*
- % windir% \\ inf \\ \* .log
- % windir% \\ 服務 \\ 會話 \\ActionList.xml
- % windir% \\ 服務 \\ 會話 \\Sessions.xml
- % windir% \\ SoftwareDistribution \\ 資料存儲 \\ 記錄 \\ edb 記錄
- % windir% \\ SoftwareDistribution \\ 資料存儲 \\ edb
- % windir% \\ 記錄 \\ dism \\ dism .log 記錄檔
- % SystemRoot% \\ System32 \\ Winevt \\ 記錄\\
- % appdata% \\ Microsoft \\ Teams \\ 媒體堆疊 \\ \* 。 blog
- % appdata% \\ Microsoft \\ Teams \\ skylib \\ \*
- % appdata% \\ Microsoft \\ Teams \\ 媒體-堆疊 \\ \*
- % appdata% \\ Microsoft \\ Teams \\logs.txt
- % windir% \\ Windows \\ System32 \\ winevt \\ \* 。\*