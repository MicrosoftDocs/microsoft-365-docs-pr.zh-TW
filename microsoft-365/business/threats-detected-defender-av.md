---
title: Microsoft Defender 防毒軟體偵測到的威脅
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 瞭解 Microsoft Defender 防毒軟體如何保護您的 Windows 裝置免受軟體威脅（如病毒、惡意程式碼和間諜軟體的威脅）。
ms.openlocfilehash: 1653aef6967cdf76e6e19acda158fb29758280a8
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870896"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Microsoft Defender 防毒軟體偵測到的威脅

Microsoft Defender 防毒軟體會保護您的 Windows 裝置免受軟體威脅，例如病毒、惡意程式碼和間諜軟體的威脅。

- 病毒通常是透過將其程式碼附加到裝置或網路上的其他檔案來傳播，而且可能會造成受感染的程式無法正常運作。
- 惡意程式碼包含惡意的檔案、應用程式和程式碼，可能會造成損毀，並破壞正常使用裝置。 此外，惡意程式碼也可以允許未經授權的存取、使用系統資源、竊取密碼和帳戶資訊、封鎖您的電腦並要求 ransom 等等。
- 間諜軟體會收集資料，例如網頁流覽活動，並將資料傳送至遠端伺服器。
 
為了提供威脅防護，Microsoft Defender 防病毒會使用數種方法。 這些方法包括雲端提供的保護、即時保護和專用的保護更新。

- 雲端提供的保護可協助提供接近即時的偵測，並封鎖新的和新興的威脅。
- Always on 掃描使用檔案與處理常式行為監控和其他技術 (也稱為 *即時保護*) 。
- 專用的保護更新是以機器學習、人工和自動化大量資料分析，以及深入威脅抵觸調查為基礎。 

若要深入瞭解惡意程式碼和 Microsoft Defender 防病毒，請參閱下列文章： 

- [瞭解惡意程式碼 & 其他威脅](/windows/security/threat-protection/intelligence/understanding-malware)
- [Microsoft 如何識別惡意程式碼和潛在的有害應用程式](/windows/security/threat-protection/intelligence/criteria)
- [Windows 10 中的下一代保護](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>使用非 Microsoft 防病毒解決方案時會發生什麼情況？ 

Microsoft Defender 防病毒是作業系統的一部分，且已在執行 Windows 10 的裝置上啟用。 不過，如果您使用非 Microsoft 防病毒方案，而且不是使用 [Microsoft defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)，則 Microsoft Defender 防毒程式會自動進入停用模式。  

在停用模式下，使用者和客戶仍然可以使用 Microsoft Defender 防毒程式進行排程或隨選即用掃描，以找出威脅;不過，Microsoft Defender 防毒程式將不再執行下列作業：

- 用作預設的防病毒應用程式。
- 主動掃描檔案以取得威脅。
- 修正或解決威脅。

如果您卸載非 Microsoft 防病毒方案，Microsoft Defender 防毒程式將會自動進入主動模式，以保護您的 Windows 裝置免受威脅。

> [!TIP]
> - 如果您使用的是 Microsoft 365，請考慮使用 Microsoft Defender 防病毒做為您的主要防病毒解決方案。 整合可提供更好的保護。 [一起查看： Microsoft Defender 防病毒和 Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)。
> - 請務必將 Microsoft Defender 防病毒保持在最新狀態，即使您使用非 Microsoft 防病毒方案也是一樣。

## <a name="what-to-expect-when-threats-are-detected"></a>偵測到威脅時的預期行為

當 Microsoft Defender 防病毒偵測到威脅時，會發生下列情況：

- 使用者 [在 Windows 中接收通知](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)。 
- 偵測列于 [**保護歷史記錄**] 頁面上的 [ [Windows 安全性] 應用程式](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)中。  
- 如果您已 [保護 Windows 10 裝置](secure-win-10-pcs.md)，並已 [在 Intune 中註冊](/mem/intune/enrollment/windows-enrollment-methods)，而且您的組織已註冊了800或更少的裝置，您會在 [**威脅與防病毒**] 頁面上的 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">microsoft 365 系統管理中心</a>中看到威脅偵測和洞察力，您可以透過選取 **健康** 情況威脅 & 防病毒) 來存取首頁上的 **microsoft Defender 防病毒** 卡 (或流覽窗格  >   。

    如果您的組織已在 Intune 中註冊超過800個裝置，系統會提示您從 [Microsoft 端點管理員](/mem/endpoint-manager-overview) （而不是從 **威脅和防病毒** 頁面）中查看威脅偵測和洞察力。
 
    > [!NOTE]
    > **Microsoft Defender 防毒軟體** 卡和 **威脅和防病毒** 頁面以分階段的方式展開，所以您可能不會立即存取它們。

在大多數情況下，使用者不需要採取任何動作。 在裝置上偵測到惡意檔或程式之後，Microsoft Defender 防毒程式會封鎖它，並防止其執行。 此外，新偵測到的威脅也會新增至防毒軟體和反惡意程式碼引擎，讓其他裝置和使用者也受到保護。  

如果有使用者需要採取的動作，例如核准移除惡意檔，他們會在收到的通知中看到。 若要深入瞭解 Microsoft Defender 防病毒在使用者上採取的動作，或使用者可能需要採取的動作，請參閱 [保護史](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)。 若要瞭解如何以 IT 專業人員/系統管理員的身分管理威脅偵測，請參閱 [查看偵測到的威脅並採取動作](review-threats-take-action.md)。

若要深入瞭解不同威脅，請造訪 <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft Security 情報威脅網站</a>，以供您執行下列動作： 

- 查看有關主要威脅的目前資訊。
- 查看特定區域的最新威脅。
- 搜尋威脅百科全書以取得特定威脅的詳細資料。

## <a name="related-content"></a>相關內容

[保護 Windows 10 裝置](secure-windows-10-devices.md) (文章) \
[評估 Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (文章) \
[如何開啟即時和雲端傳遞的防防毒保護](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (文章) \
[如何在 Windows 安全性 app 中開啟及使用 Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (文章) \
[如何使用群組原則開啟 Microsoft Defender 防病毒](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (文章) \
[如何更新防病毒定義](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (文章) \
[如何將惡意程式碼和非惡意程式碼提交給 Microsoft 進行分析](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (文章) 