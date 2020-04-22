---
title: 從勒索軟體的攻擊中復原
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Microsoft 365 系統管理員可以瞭解如何從勒索軟體的攻擊復原。
ms.openlocfilehash: 49e14e92505f5241828a525aba82a2dc871e6784
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634397"
---
# <a name="recover-from-a-ransomware-attack-in-office-365"></a>從 Office 365 復原勒索軟體攻擊

即使您採取每一種防範措施保護您的組織，您還是可以遭到[勒索軟體](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)攻擊的受害人。 勒索軟體是很大的商務用，攻擊是以複雜的驗證。

本主題中的步驟可讓您最有可能復原由勒索軟體加密的資料，並將協助停止傳播組織中的感染。 在您開始之前，請考慮下列項目：

- 不保證支付 ransom 將會傳回檔案的存取權。 實際上，支付 ransom 可讓您成為更多勒索軟體的目標。 如果您已付費，但您已能夠順利復原檔案，而不需要使用攻擊者的解決方式，則應該撥打您的銀行以查看是否可以封鎖交易。 此外，我們也建議您向法律強制執行（如本主題稍後所述），向法律執行、詐騙報告網站和 Microsoft 報告勒索軟體攻擊。

- 您必須快速回應攻擊及其結果，這一點很重要。 您等候的時間越長，您可以復原受影響資料的可能性也就越低。

## <a name="step-1-verify-your-backups"></a>步驟1：驗證備份

如果您有離線備份，您可能會在從環境中移除勒索軟體的負載（惡意程式碼）**之後**，還原加密的資料。

如果您沒有備份，或是您的備份也受到勒索軟體的影響，您可以略過此步驟。

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>步驟2：停用 ActiveSync 和 OneDrive 同步處理

這裡的關鍵點是停止勒索軟體加密的資料加密。

如果您懷疑電子郵件是目標，您應該暫時停用使用者對信箱的存取權。 Exchange ActiveSync 是由行動裝置用於同步裝置與 Exchange Online 信箱之間的資料。

若要停用信箱的 ActiveSync，請參閱[如何針對 Office 365 中的使用者停用 Exchange ActiveSync](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365)。

若要停用信箱的其他類型的存取，請參閱：

- [啟用或停用信箱的 MAPI](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。

- [啟用或停用使用者 POP3 或 IMAP4 存取權](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

暫停 OneDrive 同步處理會協助保護您的雲端資料，使其不會受到可能受感染的裝置更新。 如需詳細資訊，請參閱 how [To Pause And Resume sync in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>步驟3：從受影響的裝置移除惡意程式碼

在所有可疑電腦和裝置上執行完整的防病毒掃描，並提供最新的更新，以偵測和移除與勒索軟體相關聯的負載。 請勿忘記正在同步處理資料的裝置，或對應網路磁碟機的目標（即必須掃描那些電腦和裝置）。

您可以使用[Windows Defender](https://www.microsoft.com/windows/comprehensive-security)或（適用于舊版用戶端） [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)。

另一種方式也可協助您移除勒索軟體或惡意[軟體是惡意軟體移除工具（MSRT）](https://www.microsoft.com/download/details.aspx?id=9905)。

如果這些選項不起作用，您可以嘗試使用[Windows Defender 離線](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc)或[疑難排解偵測和移除惡意程式碼的問題](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)。

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>步驟4：在已清除的電腦或裝置上復原檔案

在您完成上述步驟以從環境中移除勒索軟體負載（以避免勒索軟體加密或移除檔案）之後，您可以使用 windows 10 和 Windows 8.1 中的檔案歷程[記錄](https://support.microsoft.com/help/17128/windows-8-file-history)，或 windows 7 中的系統保護，以嘗試復原您的本機檔案和資料夾。

**附註**：

- 有些勒索軟體也會加密或刪除備份版本，因此您無法使用檔案記錄或系統保護來還原檔案。 如果發生這種情況，您需要在外部磁片磁碟機或未受勒索軟體或 OneDrive 的裝置上使用備份，如下一節所述。

- 如果資料夾與 OneDrive 同步處理，而且您不是使用最新版的 Windows，則可能會有一些限制使用檔案歷程記錄。

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>步驟5：在您的 OneDrive 商務中復原檔案

在 OneDrive for Business 中還原檔案，可讓您在過去的30天內，將整個 OneDrive 還原至上一個時間點。 如需詳細資訊，請參閱[還原您的 OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15)。

## <a name="step-6-recover-deleted-email"></a>步驟6：復原已刪除的電子郵件

在少數情況下，勒索軟體會刪除所有的電子郵件，您可能會復原已刪除的郵件。 如需詳細資訊，請參閱：

- [復原刪除的郵件使用者的信箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [在 Windows 版 Outlook 復原已刪除的項目](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>步驟7：重新啟用 Exchange ActiveSync 和 OneDrive 同步處理

在您清潔電腦和裝置並復原資料後，您可以重新啟用 ActiveSync，並 OneDrive 您先前在[步驟 2](#step-2-disable-activesync-and-onedrive-sync)中停用的同步處理。

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>步驟8（選用）：封鎖特定檔案副檔名的 OneDrive 同步處理

復原之後，您可以防止商務用戶端的 OneDrive 同步處理此勒索軟體所影響的檔案類型。 如需詳細資訊，請參閱[Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>報告攻擊

### <a name="contact-law-enforcement"></a>連絡人法律強制執行

您應與當地或聯邦執法機構聯繫。 例如，如果您在美國，您可以聯繫[FBI 當地欄位 office](https://www.fbi.gov/contact-us/field)、 [IC3](http://www.ic3.gov/complaint/default.aspx)或[機密服務](http://www.secretservice.gov/)。

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>將報告提交至您的國家/地區的騙局報告網站

騙局報告網站提供如何防止和避免詐騙的相關資訊。 當您是騙局的受害者時，也會提供要報告的機制。

- 澳大利亞： [SCAMwatch](http://www.scamwatch.gov.au/)

- 加拿大：[加拿大反欺詐中心](http://www.antifraudcentre-centreantifraude.ca/)

- 法國： [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- 德國： [Bundesamt Für Sicherheit in Der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- 愛爾蘭： a [Garda Síochána](http://www.garda.ie/)

- 紐西蘭：[使用者事務詐騙](http://www.consumeraffairs.govt.nz/scams)

- 英國：[動作欺詐](http://www.actionfraud.police.uk/)

- 美國：[線上防護](http://www.onguardonline.gov/)

如果您的國家/地區未列出，請諮詢您的當地或聯邦執法機構。

### <a name="submit-email-messages-to-microsoft"></a>將電子郵件提交至 Microsoft

您可以使用下列其中一種方法，報告包含勒索軟體的網路釣魚郵件。 如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。

## <a name="see-also"></a>請參閱

- [軟體](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [勒索軟體回應-支付或不支付費用？](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro 會以透明度回應勒索軟體攻擊](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [勒索軟體偵測和復原 OneDrive 中的檔案](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft Security 情報報告](https://www.microsoft.com/securityinsights/)

- [啟用或停用 Office 檔案中的宏](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [EOP 和 Office 365 ATP 安全性的建議設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [值得升級： Windows 10 上的下一代安全性會為2017中的勒索軟體的爆發，證實其可復原](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [沒有 ma，Samas：在此勒索軟體的 modus operandi 中有哪些？](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Locky 惡意程式碼（幸運）以避免出現](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT 2016 年7月： Cerber 勒索軟體](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Cerberus 的三個機頭（如 Cerber）勒索軟體](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [受（） Da Vinci 程式碼影響的 Troldesh 勒索軟體](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
