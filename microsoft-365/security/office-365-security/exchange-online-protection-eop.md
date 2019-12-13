---
title: Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 70ab4af2-fec4-4886-8e12-27d348649204
description: 開始使用 EOP 前，您必須先注意下列事項。
ms.openlocfilehash: ae08ff17a3ef25f0b0903d02ffe396cd201bd06c
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970519"
---
# <a name="exchange-online-protection"></a>Exchange Online Protection

歡迎使用 Microsoft Exchange Online Protection (EOP) 託管的電子郵件篩選服務。開始使用 EOP 和此內容前，您必須先注意下列事項：

- 若要深入了解 EOP，請查看 [Exchange Online Protection 服務描述](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。 其他有用的資源包括＜[Exchange Online Protection 概觀](exchange-online-protection-overview.md)＞、＜[EOP 一般常見問題集](eop-general-faq.md)＞和＜[EOP 功能](eop-features.md)＞，以及＜[Exchange Online Protection 首頁](https://products.office.com/exchange/exchange-email-security-spam-protection)＞。

- 若要開始使用 EOP，新客戶請前往[設定 EOP 服務](set-up-your-eop-service.md)。 本主題提供可協助 EOP 順利運作的步驟。

- 如果您需要其他協助或想要分享意見，[EOP 論壇](https://go.microsoft.com/fwlink/?LinkId=285351)是很理想的起點。

## <a name="eop-help-for-administrators"></a>適用於系統管理員的 EOP 幫助

適用於 EOP 系統管理員的幫助內容由下列頂層類別組成：

- [Exchange Online Protection 概觀](exchange-online-protection-overview.md)：介紹 EOP 的運作方式，並提供其他資訊連結。

- [EOP 功能](eop-features.md)：提供一份 EOP 中可用的功能清單。

- [設定 EOP 服務](set-up-your-eop-service.md)：提供 EOP 服務的設定步驟，以及其他資訊的連結。

- [從 Google Postini、Barracuda Spam and Virus Firewall 或 Cisco IronPort 切換到 EOP](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)：說明從其他電子郵件保護產品切換到 EOP 的程序。

- [管理收件者及管理 EOP 中的系統管理員角色](manage-recipients-and-admin-role-groups-in-eop.md)：說明如何管理收件者及如何指派使用者給管理員角色群組。

- [EOP 中的郵件流程](mail-flow-in-eop.md)：說明如何使用連接器來設定自訂郵件流程案例、如何管理與服務相關的網域，以及如何啟用目錄架構邊緣封鎖 (DBEB) 功能。

- [設定 EOP 的最佳作法](best-practices-for-configuring-eop.md)：說明在您設定和佈建服務之後的建議組態設定和考量。

- [EOP 中的郵件原則及符合性](messaging-policy-and-compliance-in-eop.md)：說明如何使用 Exchange 郵件流程規則 (又稱傳輸規則) 來強制執行特定公司規定與政策，以及如何使用稽核報告來追蹤服務發生的設定變更。

- [Office 365 反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)：說明垃圾郵件篩選和惡意程式碼篩選，以及顯示如何進行自訂以滿足貴組織的需求。 此外，還說明系統管理員和使用者可以對隔離郵件執行的工作。

- [Exchange Online Protection 的報告與訊息追蹤](reporting-and-message-trace-in-exchange-online-protection.md)：說明可用的報告和疑難排解工具。

- [Exchange Online Protection 中的 Exchange 系統管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)：說明如何存取和瀏覽 Exchange 管理中心 (EAC) 管理介面，以便管理 EOP 服務。

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)：提供遠端 PowerShell 的相關資訊，讓您可以從命令列管理 EOP 服務。

- [EOP 幫助和支援](help-and-support-for-eop.md) 提供有關取得幫助和技術支援的資訊。

## <a name="eop-help-for-end-users"></a>適用於使用者的 EOP 幫助

可協助 EOP 使用者來管理垃圾郵件的幫助內容包含下列主題：

- [以使用者身分找到並釋放被隔離的郵件](find-and-release-quarantined-messages-as-a-user.md)：說明使用者如何在垃圾郵件隔離使用者介面中尋找和釋出其自己的垃圾隔離郵件，並選擇性地向 Microsoft 報告這些郵件不是垃圾郵件。

- [將垃圾郵件、非垃圾郵件與網路釣魚詐騙郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)：說明可讓使用者向 Microsoft 提交垃圾郵件和非垃圾郵件訊息的不同方式。 本主題包含 Microsoft Outlook 和 Outlook 網頁版 (先前稱為 Outlook Web App) 中可用報告工具的連結。

- [將惡意程式碼與非惡意程式碼提交給 Microsoft 進行分析](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)：描述使用者可以如何提交惡意程式碼使其通過篩選，或者提交錯誤識別為惡意程式碼的檔案。

- 使用者可藉由在 Outlook 或 Outlook 網頁版中設定其垃圾電子郵件設定，將特定使用者或網域加入至安全寄件者清單或封鎖寄件者清單。 請注意，封鎖的寄件者傳來的郵件會被標示為垃圾郵件，但不會遭到拒收，這表示這類郵件會丟到 [垃圾郵件] 資料夾或隔離區中供人擷取 (取決於系統管理員在何處設定服務來傳送垃圾郵件而定)。如需更多資訊，請參閱[使用回報郵件增益集](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

- [EOP 幫助和支援](help-and-support-for-eop.md) 提供有關取得幫助和技術支援的資訊。
