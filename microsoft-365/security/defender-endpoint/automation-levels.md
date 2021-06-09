---
title: 自動化調查和修正中的自動化層級
description: 深入瞭解自動化層級，以及如何在 Microsoft Defender for Endpoint 中運作
keywords: 自動化、調查、層級、Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.date: 10/22/2020
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 6d453a8b6e5c4947c0fb03131c539b083227c28a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844643"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>自動化調查和修正功能的自動化層級

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

自動調查和修正 (Microsoft Defender for Endpoint 中的 AIR) 功能，可設定為下列其中一種自動化層級。 您的自動化層級會影響立即調查是否會自動或只在核准時採取補救措施。  
- *完全自動化* (建議) 表示對惡意的偽像所決定的修復動作會自動執行。
- *半自動* 是指自動採取某些修正動作，但在採取其他修復動作之前，請先進行核准。  (請參閱 [Automation 層次](#levels-of-automation)中的資料表。 ) 
- 所有修正動作（不論是擱置或已完成的動作）都會在「 () 的「動作中心」中追蹤 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。 

> [!TIP]
> 為了獲得最佳結果，建議您在 [設定 AIR](configure-automated-investigations-remediation.md)時使用「完全自動化」。 過去一年收集和分析的資料會顯示，使用「完全自動化」的客戶，已移除超過40% 的高可信度惡意程式碼範例，而不是使用較低的「自動化」層級的客戶。 完全自動化可協助您騰出安全性運作資源，以更多程度地專注于您的戰略性計畫。

## <a name="levels-of-automation"></a>自動化層級

下表說明每個自動化層級及其運作方式。

|自動化層級 | 描述|
|:---|:---|
|**自動修正威脅** <br/> (也稱為「 *完全自動化* 」) | 完全自動化時，會自動執行修正動作。 您可以在 [**記錄**] 索引標籤的 [[動作中心](auto-investigation-action-center.md)] 中查看所有採取的修復動作。如有必要，可復原修復動作。<br/><br/>**_建議使用「完全自動化_* 」，且預設為在2020年8月16日或之後所建立的承租人中，但未定義任何裝置群組。*  |
|**半要求進行任何修正的核准** <br/> (也稱為 *半自動化*) | 有了這一層級的半自動， *任何* 修正動作都必須進行核准。 在 [**暫** 止] 索引標籤上，您可以在 [[行動中心](auto-investigation-action-center.md)] 中查看和核准這類待定的動作。<br/><br/>*預設會為在8月 16 2020 日之前所建立的承租人選取此部分，但不定義任何裝置群組。*|
|**半自動要求核心資料夾修正的核准** <br/>此外，還 (一種 *半自動化*)   | 在具有這種基本自動化的情況下，必須針對核心資料夾中的檔案或可執行檔所需的任何修正動作進行核准。 核心資料夾包括作業系統目錄，例如 **Windows** (`\windows\*`) 。<br/><br/>修正動作可自動在其他 (非核心) 資料夾中的檔案或可執行檔上加以採取。 <br/><br/>在核心資料夾中的檔案或可執行檔的擱置動作，可在 [**擱置**] 索引標籤上的 [[行動中心](auto-investigation-action-center.md)] 中查看和核准。 <br/><br/>在 [**記錄**] 索引標籤上，可以在 [[行動中心](auto-investigation-action-center.md)] 中查看對其他資料夾中的檔案或可執行檔所採取的動作。 |
|**非 temp 資料夾修正的半要求核准** <br/>此外，還 (一種 *半自動化*) | 使用此半高層級時，必須對 *不* 在暫存資料夾中之檔案或可執行檔的任何修正動作進行核准。 <br/><br/>暫存資料夾可包含下列範例： <br/>- `\users\*\appdata\local\temp\*`<br/>- `\documents and settings\*\local settings\temp\*` <br/>- `\documents and settings\*\local settings\temporary\*`<br/>- `\windows\temp\*`<br/>- `\users\*\downloads\*`<br/>- `\program files\` <br/>- `\program files (x86)\*`<br/>- `\documents and settings\*\users\*`<br/><br/>您可以在暫存資料夾中的檔案或可執行檔上自動採取修正動作。 <br/><br/>在 [**暫** 止] 索引標籤的 [動作中心] 中，您可以在「[動作中心](auto-investigation-action-center.md)」中查看並核准未在暫存資料夾中的檔案或可執行檔。<br/><br/>您可以在 [行動中心](auto-investigation-action-center.md)的 [ **記錄** ] 索引標籤上，查看並核准對暫存資料夾中的檔案或可執行檔採取的動作。   |
|**無自動回應** <br/> (也稱為「 *沒有自動化* 」)  | 無自動化，自動化調查不會在您組織的裝置上執行。 因此，由於自動調查，不會採取任何修正動作，也不會擱置。 不過，其他威脅防護功能（例如 [防禦可能有害的應用程式](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)）可能會生效，視如何設定您的防病毒和下一代保護功能而定。<br/><br/>***不建議使用 [ *不自動化* ] 選項**，因為它會降低組織裝置的安全性狀況。 [請考慮將您的自動化層級設定為 [完全 (自動化]，或至少半自動) ](/microsoft-365/security/defender-endpoint/machine-groups)*。 |

## <a name="important-points-about-automation-levels"></a>有關自動化層級的重要事項

- 完全自動化已證實是可靠、有效率且安全的，而且對於所有客戶都建議使用。 完整的自動化功能可釋放您重要的安全性資源，讓他們能專注于您的戰略性計畫。

- 新承租人 (，包含在) 2020 年8月16日之前或之後所建立的承租人，且預設會將 Microsoft Defender for Endpoint 設定為「完全自動化」。

- 如果您的安全小組已經定義了具有「自動化」層級的裝置群組，則所進行的新預設設定不會變更這些設定。 

- 您可以保留預設的自動化設定，或根據組織的需求加以變更。 若要變更您的設定，請 [設定您的自動化層級](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups)。

## <a name="next-steps"></a>後續步驟

- [在 Microsoft Defender for Endpoint 中設定自動調查和修正功能](configure-automated-investigations-remediation.md)

- [流覽行動中心](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
