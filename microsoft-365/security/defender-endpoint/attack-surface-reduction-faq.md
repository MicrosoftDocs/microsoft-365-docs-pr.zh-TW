---
title: '攻擊面減少常見問題解答 (常見問題) '
description: 尋找有關 Microsoft Defender for Endpoint 的攻擊面降低規則的常見問題答案。
keywords: 攻擊面減少規則，asr，hips，主機入侵防護系統，保護規則，反侵入，antiexploit，exploit，感染防護，microsoft defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: martyav
ms.author: v-maave
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cf41dda4ff61137d6b60b2fc735227f15418477e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935590"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>攻擊面減少常見問題解答 (常見問題) 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a> (ASR) 部分 Windows 中是否要減少攻擊面？

ASR 最初是一項利用方式防護功能套件，在 Windows 10 版本1709中做為 Microsoft Defender 防毒軟體的主要更新。 Microsoft Defender 防病毒是 Windows 的原生反惡意軟體元件。 不過，只有 Windows 企業版授權才能使用完整的 ASR 功能集。 另請注意，ASR 規則排除項會與 Microsoft Defender 防病毒排除項分開管理。

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>我需要有企業版授權才能執行 ASR 規則嗎？

只有具備 Windows 10 企業版授權時，才支援完整的 ASR 規則和功能集。 在沒有企業版授權的情況下，有限的規則數目可以運作。 如果您有 Microsoft 365 業務，請將 Microsoft Defender 防病毒設定為主要的安全性解決方案，並透過 PowerShell 啟用規則。 未正式支援使用沒有企業版授權的 ASR，而且您將無法使用 ASR 的完整功能。

若要深入瞭解 Windows 授權，請參閱 [windows 10 授權](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) 並取得 [Windows 10 的大量授權指南](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)。

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>如果我有 E3 授權，是否支援 ASR？

是。 Windows Enterprise E3 和更新版本支援 ASR。 

## <a name="which-features-are-supported-with-an-e5-license"></a>E5 授權支援哪些功能？

E5 也支援使用 E3 支援的所有規則。

E5 增加了與 Defender for Endpoint 的整合。 透過 E5，您可以即時查看提醒、微調規則排除、設定 ASR 規則，以及查看附隨報告清單。

## <a name="what-are-the-currently-supported-asr-rules"></a>目前支援的 ASR 規則為何？
ASR 目前支援下列所有規則。

## <a name="what-rules-to-enable-all-or-can-i-turn-on-individual-rules"></a>要啟用哪些規則？ 全部，還是可以開啟個別規則？
為了協助您找出最適合您環境的功能，建議您在 [稽核模式](audit-windows-defender.md)中啟用 ASR 規則。 使用此方法時，您將會決定組織的可能影響。 例如，您的企業營運應用程式。

## <a name="how-do-asr-rules-exclusions-work"></a>ASR 規則排除的運作方式？
針對 ASR 規則，如果您新增一個排除，它會影響每個 ASR 規則。
下列兩個特定的規則不支援排除：

|規則名稱|GUID|File & 資料夾排除|
|:--|:--|:--|
|從啟動下載的可執行內容封鎖 JavaScript 或 VBScript|D3E037E1-3EB8-44C8-A917-57927947596D|不支援|
|透過 WMI 事件訂閱封鎖持久性|e6db77e5-3df2-4cf1-b95a-636979351e5b|不支援|

ASR 規則排除支援萬用字元、路徑及環境變數。 如需如何在 ASR 規則中使用萬用字元的詳細資訊，請參閱 [根據副檔名和資料夾位置來設定及驗證排除](/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus)。

請注意下列有關 ASR 規則排除 (（包括萬用字元和 env）的專案。 變數) ：

- ASR 規則排除獨立于 Defender AV 排除
- 不能使用萬用字元來定義磁碟機號
- 如果您想要排除一個以上的資料夾，請在路徑中使用多個 \* \ 實例來表示多個嵌套資料夾 (例如，C:\Folder \* \* \Test) 
- Microsoft 端點 *Configuration Manager 不* 支援萬用字元 ( * 或？ ) 
- 如果您想要排除的檔案中包含隨機字元 (自動檔案產生) ，您可以使用 '？ ' 符號 (例如，C:\Folder\fileversion？。.docx) 
- 群組原則中的 ASR 排除項不支援引號 (引擎會以本機方式處理長路徑、空格等，因此不需要使用引號) 
- ASR 規則會在 NT AUTHORITY\SYSTEM 帳戶下執行，所以環境變數會限制于電腦變數。



## <a name="how-do-i-know-what-i-need-to-exclude"></a>如何知道我需要排除哪些專案？
不同的 ASR 規則會有不同的保護流程。 請務必考慮您要設定的 ASR 規則的保護方式，以及實際執行流程的平移方式。

範例：封鎖從從本機安全授權子系統讀取 **的 Windows 本機安全性群組子系統** (LSASS) 程式可能會造成安全性風險，因為這可能會造成公司認證。

此規則可防止不受信任的處理常式直接存取 LSASS 記憶體。 每當處理常式嘗試使用 OpenProcess () 函數存取 LSASS 時（PROCESS_VM_READ 的存取權），該規則會特別封鎖該存取許可權。

:::image type="content" source="images/asrfaq1.png" alt-text="封鎖認證竊取 LSASS":::

查看上述範例，如果您確實需要為封鎖存取權的處理常式建立例外狀況，新增檔案名及完整路徑會使其不會遭到封鎖，並且允許存取 LSASS 處理常式記憶體。 值為0表示 ASR 規則將忽略此檔案/進程，但不會封鎖/審計。

:::image type="content" source="images/asrfaq2.png" alt-text="排除檔 asr":::

## <a name="what-are-the-rules-microsoft-recommends-enabling"></a>Microsoft 建議啟用的規則為何？

建議您啟用每一種可能的規則。 不過，在某些情況下，您不應啟用規則。 例如，如果您使用的是 Microsoft 端點設定管理員 (或 System Center Configuration Manager-SCCM) 以管理您的端點，我們不建議啟用從 PSExec 和 WMI 命令規則產生的封鎖處理常式建立。

我們強烈建議您閱讀我們 [公開檔](/microsoft-365/security/defender-endpoint/attack-surface-reduction.md)中提供的每一個規則特定資訊和/或警告。
跨越多個保護的一個支柱，例如 Office、認證、腳本、E-Mail 等等。Windows 1709 和更新版本都支援所有 ASR 規則（封鎖和透過 WMI 事件訂閱除外）：

* [從電子郵件客戶程式和 web 郵件封鎖可執行檔內容](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [封鎖所有 Office 應用程式以建立子流程](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [封鎖 Office 應用程式建立可執行檔內容](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [封鎖 Office 應用程式將程式碼注入其他程式](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [從啟動下載的可執行內容封鎖 JavaScript 或 VBScript](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [封鎖可能混淆的腳本執行](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [從 Office 宏封鎖 WIN32 API 呼叫](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [使用勒索軟體的高級防護](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [從 Windows local security 機關子系統封鎖認證竊取](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) (lsass.exe) 
* [封鎖來自 PSExec 和 WMI 命令的進程建立](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [封鎖從 USB 執行的不受信任和未簽署程式](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [封鎖可執行檔，除非符合流行、age 或受信任的清單準則](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [封鎖 Office 通訊應用程式建立子流程](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [封鎖 Adobe Reader，以建立子流程](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [透過 WMI 事件訂閱封鎖持久性](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a>「ASR」快速入門的一些好的建議是什麼？

測試 ASR 規則在啟用之前如何影響您的組織，在一段短暫的時間內，以稽核模式執行 ASR 規則。 當您在稽核模式中執行規則時，您可以識別任何可能會遭到錯誤封鎖的企業營運應用程式，並將其從 ASR 中排除。

較大的組織應考慮在「環」中推出 ASR 規則，方法是在更廣泛的裝置子集內審核和啟用規則。 您可以使用 Intune 或群組原則管理工具，將組織的裝置安排在環中。

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a>我應該多久在稽核模式中測試 ASR 規則，再啟用它？

在稽核模式中讓規則保持大約30天，以取得規則在整個組織中起作用的良好基準。 在審核期間內，您可以識別任何可能會被規則封鎖的企業營運應用程式，並將規則設定為排除。

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a>我正在將協力廠商的安全性解決方案切換為端點的 Defender。 是否有「輕鬆」的方法可將規則從其他安全性解決方案匯出為 ASR？

在大多數情況下，從使用 [Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection) 建議的基準建議開始，比嘗試從其他安全性解決方案匯入規則更為簡單且更好。 然後，使用審計模式、監控和分析等工具，設定新的解決方案，以符合您的獨特需求。 

大部分 ASR 規則的預設設定（結合使用「Endpoint」端點的即時保護）都會針對大量的入侵和弱點進行保護。

您可以在 Defender for Endpoint 中使用自訂指示器更新您的防禦，以允許和封鎖某些軟體行為。 ASR 也允許某些規則的自訂，其格式為檔案和資料夾排除。 一般來說，最好是在一段時間內審核規則，並為任何可能會遭到封鎖的企業營運應用程式設定排除。

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a>ASR 是否支援在路徑中包含系統變數和萬用字元的檔案或資料夾排除專案？

是。 如需從 ASR 規則中排除檔案或資料夾的詳細資訊，請參閱 [從 asr 規則排除檔案和資料夾](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) ，並根據 [副檔名和資料夾位置來設定及驗證排除](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) ，以瞭解如何在排除的檔案路徑中使用系統變數和萬用字元。

## <a name="do-asr-rules-cover-all-applications-by-default"></a>是否依預設，ASR 規則涵蓋所有應用程式？

這取決於規則。 大多數的 ASR 規則都會涵蓋 Microsoft Office 產品和服務的行為，例如 Word、Excel、PowerPoint 及 OneNote 或 Outlook。 範圍中的某些 ASR 規則（如 *區塊執行可能模糊腳本*）較為常見。

## <a name="does-asr-support-third-party-security-solutions"></a>ASR 是否支援協力廠商的安全性解決方案？

ASR 使用 Microsoft Defender 防病毒來封鎖應用程式。 目前無法將 ASR 設定為使用另一個安全性解決方案來封鎖。

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a>我有 E5 授權，並已將部分 ASR 規則與 Defender for Endpoint 一起啟用。 在端點的事件時程表中，ASR 事件是否可顯示在所有的更新中？

每當 ASR 規則以本機方式觸發通知時，事件的報告也會傳送至端點入口網站的 Defender。 如果您找不到該事件，您可以使用 [搜尋] 方塊來篩選事件時程表。 您也可以從 [安全性中心] 工作列中的 [設定 **管理**]**圖示，查看** ASR 事件。 「攻擊面管理」頁面包含報告偵測的索引標籤，其中包括報告給 Defender for Endpoint 之 ASR 規則事件的完整清單。

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a>我使用 GPO 套用規則。 現在當我嘗試檢查 Microsoft Outlook 中的規則索引選項時，收到一則訊息，說明「拒絕存取」。

請嘗試直接從 Windows 10 開啟索引選項。

1. 選取 Windows 工作列上的 **搜尋** 圖示。

1. 在搜尋方塊中輸入 **索引選項** 。

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>規則使用的準則是「封鎖可執行檔的執行，除非它們符合傳播、時期或受信任的清單準則」（由系統管理員加以設定）。

不對。 此規則所用的準則是由 Microsoft cloud protection 所維護，可讓信任的清單持續更新世界各地收集的資料。 本機系統管理員沒有變更此資料的寫入權限。 如果您想要設定此規則以針對您的企業進行量身定制，您可以將特定的應用程式新增至排除清單，以避免觸發規則。

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>我已啟用 ASR 規則， *封鎖可執行檔，除非符合流行、age 或受信任的清單準則*。 經過一段時間後，我就會更新某項軟體，而且規則現在會封鎖它，即使之前並未這樣。 發生問題？

此規則取決於每個具有已知信譽的應用程式，例如流行、age 或包含在信任的應用程式清單中。 此規則決定封鎖或允許應用程式，最終是由 Microsoft cloud protection 評估這些準則所決定。

通常，cloud protection 可以判斷應用程式的新版本與舊版 reassessed 的應用程式，不需要有足夠的長度。 不過，此應用程式可能需要一些時間，才能在切換版本之後建立信譽，尤其是在主要更新之後。 在此期間，您可以將應用程式新增至排除清單，以防止此規則封鎖重要的應用程式。 如果您經常更新及使用新版本的應用程式，您可以選擇改為在稽核模式中執行這項規則。

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>我最近啟用了 ASR 規則， *封鎖從 Windows local security 機關子系統 (lsass.exe) 的認證*，而且我收到大量通知。 這是怎麼回事？

此規則產生的通知不一定表示惡意活動;不過，此規則對於封鎖惡意活動仍然有用，因為惡意程式碼通常會以 lsass.exe 來取得帳戶的非法存取權。 lsass.exe 處理常式會在使用者登入後，將使用者認證儲存在記憶體中。 Windows 會使用這些認證來驗證使用者，並套用本機安全性原則。

由於在一般的一天內，許多合法的處理常式會呼叫憑證的 lsass.exe，因此此規則特別可能會有噪音。 如果已知合法的應用程式導致此規則產生過量的通知數目，您可以將它新增至排除清單。 因為呼叫 lsass.exe 一般是許多應用程式正常運作，所以大多數其他的 ASR 規則會產生相對較少的通知數目（與此不同）。

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>建議您是否要啟用此規則、 *封鎖從 Windows local security 機關子系統 (lsass.exe) 中的認證*，以及 LSA 防護？

若您也啟用了 [LSA 保護](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) ，啟用此規則將不會提供額外的保護。 規則和 LSA 保護的運作方式都很多，所以同時執行這兩個動作都是多餘的。 不過，有時候您可能無法啟用 LSA 保護。 在這種情況下，您可以啟用此規則，針對針對 lsass.exe 的惡意程式碼提供同等防護。

## <a name="see-also"></a>另請參閱

* [攻擊面減少綜述](attack-surface-reduction.md)
* [評估受攻擊面縮小規則](evaluate-attack-surface-reduction.md)
* [自訂受攻擊面縮小規則](customize-attack-surface-reduction.md)
* [啟用受攻擊面縮小規則](enable-attack-surface-reduction.md)
* [Microsoft Defender 與其他防病毒/反惡意程式碼的相容性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
