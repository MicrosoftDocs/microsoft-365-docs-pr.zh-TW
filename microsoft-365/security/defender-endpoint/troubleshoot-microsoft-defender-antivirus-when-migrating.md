---
title: 從協力廠商解決方案移轉時疑難排解 Microsoft Defender 防毒軟體
description: 在遷移至 Microsoft Defender 防毒軟體時疑難排解常見的錯誤
keywords: 事件、錯誤代碼、記錄、疑難排解、microsoft defender 防毒程式、windows defender 防毒程式、遷移
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3eb4d01957383efc8df47e9fee6eb6394c80015a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924380"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>從協力廠商解決方案移轉時疑難排解 Microsoft Defender 防毒軟體

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)


如果您在從協力廠商安全性解決方案 Microsoft Defender 防毒軟體進行遷移時遇到問題，您可以在這裡找到 [說明]。

## <a name="review-event-logs"></a>審閱事件記錄檔

在工作列中選取 **搜尋** 圖示，然後搜尋 [ *事件檢視器*]，以開啟 [事件檢視器] 應用程式。

您可以在 [**應用程式及服務記錄**] [  >  **Microsoft**  >  **Windows**  >  **Windows Defender**] 底下找到 Microsoft Defender 防毒軟體的相關資訊。 

從那裡，選取 [在 **運作** 下 **開啟**]。

從 [詳細資料] 窗格選取事件，將會在 [一般] 和 **[** **詳細資料** ] 索引標籤底下的下部窗格中顯示事件的詳細資訊。

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender 防毒軟體不會啟動

此問題的資訊清單可能是數個不同的事件 IDs，所有這些事件都具有相同的基本原因。

### <a name="associated-event-ids"></a>關聯的事件 IDs

 事件識別碼 | 記錄檔名稱 | 描述 | 來源
-|-|-|-
8 | 應用程式 | SECURITY_PRODUCT_STATE_OFF 成功更新 Windows Defender 狀態。 | 安全中心
5007 | Microsoft Windows Windows Defender/Operational | Windows Defender 防毒軟體設定已經變更。  如果這是未預期的事件，您應該檢查設定，因為這可能是惡意程式碼的結果。<br /><br />**舊值：** Default\IsServiceRunning = 0x0<br />**新值：** HKLM\SOFTWARE\Microsoft\ Windows Defender \IsServiceRunning = 0x1 | Windows Defender
5010 | Microsoft Windows Windows Defender/Operational | 已停用對間諜軟體和其他可能有害軟體的 Windows Defender 防毒軟體掃描。 | Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>如何判斷 Microsoft Defender 防毒軟體是否因安裝協力廠商防毒程式而無法啟動

在 Windows 10 裝置上，如果您不是使用 Microsoft Defender for Endpoint，而您已安裝協力廠商的防毒軟體，則 Microsoft Defender 防毒軟體會自動關閉。 如果您使用的是 Microsoft Defender for Endpoint，且已安裝協力廠商防毒軟體，則 Microsoft Defender 防毒軟體會以被動式模式開始，但功能會變少。

> [!TIP]
> 剛才所述的案例只適用于 Windows 10。 其他版本的 Windows 對 Microsoft Defender 防毒軟體所執行的回應和協力廠商的安全性軟體的[回應有所不同](microsoft-defender-antivirus-compatibility.md)。

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>使用服務應用程式檢查 Microsoft Defender 防毒軟體是否關閉

若要開啟服務應用程式，請從工作列選取 **搜尋** 圖示，然後搜尋 *服務*。 您也可以輸入 *services.msc*，從命令列開啟應用程式。

Microsoft Defender 防毒軟體的相關資訊會列在服務應用程式中 **Windows Defender**  >  **運作** 中。 防病毒服務名稱是 *Windows Defender 防毒軟體服務*。

檢查應用程式時，您可能會看到 *Windows Defender 防毒軟體服務* 設定為手動，但是當您嘗試手動啟動此服務時，會收到一則警告，指出 *本機電腦上的 Windows Defender 防毒軟體 service 服務已啟動，且已停止。有些服務不會因為其他服務或程式而自動停止使用。*

這表示 Microsoft Defender 防毒軟體已自動關閉，以保留與協力廠商防病毒的相容性。

#### <a name="generate-a-detailed-report"></a>產生詳細報告

您可以在 [以系統 **管理員模式執行** ] 中開啟命令提示字元，然後輸入下列命令，以產生目前作用中群組原則的詳細報告：

```powershell
GPresult.exe /h gpresult.html
```

這會產生位於 at */gpresult.html* 的報告。 開啟此檔案，視 Microsoft Defender 防毒軟體關閉的方式而定，您可能會看到下列結果。

##### <a name="group-policy-results"></a>群組原則結果

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>若安全設定是透過「群組原則」來實施，請 (網域或本地層級的 GPO) ，或是 System center configuration manager (SCCM) 

在 GPResults 報告中，在標題底下 *Windows 元件/Windows Defender 防毒軟體*，您可能會看到類似下列的專案，表示 Microsoft Defender 防毒軟體已關閉。

原則 | 設定 | 入選 GPO
-|-|-
關閉 Windows Defender 防毒軟體 | 啟用 | Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>如果透過群組原則首選項來執行安全性設定 (GPP) 

在標題、登錄 *專案 (機碼路徑： HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender、值名稱： DisableAntiSpyware)* 中，您可能會看到類似下列的專案，表示 Microsoft Defender 防毒軟體已關閉。

DisableAntiSpyware | -
-|-
入選 GPO | Win10-Workstations
結果：成功 | 
**一般** | 
動作 | Update
**屬性** | 
蜂巢 | HKEY_LOCAL_MACHINE
機碼路徑 | SOFTWARE\Policies\Microsoft\ Windows Defender
數值名稱 | DisableAntiSpyware
值類型 | REG_DWORD
數值資料 | 0x1 (1) 

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>如果透過登錄機碼來執行安全性設定

報告中可能會包含下列文字，表示 Microsoft Defender 防毒軟體已關閉：
 
> Registry (regedit.exe) 
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (十六進位) 

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>在 Windows 或您的 Windows 伺服器映射中設定安全性設定

您的 imagining 系統管理員可能已透過 *GPEdit.exe*、 *LGPO.exe* 或在其任務順序中修改登錄，將安全性原則 **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**、從本機設定。 您可以為 Microsoft Defender 防毒軟體[設定信任的影像識別碼](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender)。

### <a name="turn-microsoft-defender-antivirus-back-on"></a>重新開啟 Microsoft Defender 防毒軟體

如果目前沒有任何使用中的反病毒，Microsoft Defender 防毒軟體會自動開啟。 您必須完全關閉協力廠商防病毒，以確保 Microsoft Defender 防毒軟體可以使用完整功能執行。

> [!WARNING]
> 我們建議您在 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services 中編輯 *wdboot*、 *wdfilter*、 *wdnisdrv*、 *wdnissvc* 和 *windefend* 的 *Windows Defender* start 值都不受支援，並且可能會強制您重新影像您的系統。

如果您開始使用 Microsoft Defender for Endpoint 和協力廠商的防毒軟體搭配 Microsoft Defender 防毒軟體，便可使用被動模式。 被動式模式可讓 Microsoft Defender 掃描檔案並自行更新，但不會修正威脅。 此外，透過 [即時保護](configure-real-time-protection-microsoft-defender-antivirus.md) 進行的行為監視無法在被動模式下使用，除非部署了 [端點資料遺失防護 (DLP) ](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) 。

當 Microsoft Defender 防毒軟體設定為自動關閉時，使用者就可以使用另一個功能（也稱為[有限的定期掃描](limited-periodic-scanning-microsoft-defender-antivirus.md)）。 這項功能可讓 Microsoft Defender 防毒軟體使用有限的偵測數目，在協力廠商防病毒的情況下定期掃描檔案。

> [!IMPORTANT]
> 在企業環境中不建議使用有限的定期掃描。 在此模式下執行 Microsoft Defender 防毒軟體時可用的偵測、管理與報告功能，會隨著與使用中的模式而降低。

### <a name="see-also"></a>另請參閱

* [Microsoft Defender 防毒軟體相容性](microsoft-defender-antivirus-compatibility.md)
* [Windows 安全性應用程式中的 Microsoft Defender 防毒軟體](microsoft-defender-security-center-antivirus.md)