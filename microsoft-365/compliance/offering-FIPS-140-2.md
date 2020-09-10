---
title: 聯邦資訊處理標準 (FIPS) 發佈140-2
description: Microsoft 證明其密碼模組符合聯邦資訊處理標準。
keywords: Microsoft 365, 合規性, 方案
localization_priority: None
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: f193e1846b957a26475cdfc48add6679a951841f
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47415847"
---
# <a name="federal-information-processing-standard-fips-publication-140-2"></a>聯邦資訊處理標準 (FIPS) 發佈140-2

## <a name="fips-140-2-standard-overview"></a>FIPS 140-2 standard 一覽

聯邦資訊處理標準 (FIPS) 發佈140-2 是一種美國政府標準，可定義資訊技術產品中的加密模組最低安全性需求，如資訊技術管理改革的1996法案第5131中所定義。

「 [加密模組驗證](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) 」 (CMVP) （美國國家標準和技術研究院 (NIST) 的共同工作，以及網路安全性 (CCCS) 的加拿大中心），會驗證加密模組的 *安全性需求，以取得加密模組* 標準 (（如 FIPS 140-2) 和相關的 FIPS 密碼編譯標準）。 FIPS 140-2 的安全性需求涵蓋11個與加密模組設計及實施相關的區域。 NIST Information 技術實驗室會運作相關的程式，以驗證模組中的 FIPS 核准的加密演算法。

## <a name="microsofts-approach-to-fips-140-2-validation"></a>Microsoft 的 FIPS 140-2 驗證方法

Microsoft 會維持積極的承諾，以滿足140-2 需求，因為標準是在2001內開始已驗證的加密模組。 Microsoft 會在國家安全局) [加密模組驗證計畫](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) (CMVP) 的標準及 (技術研究院下驗證其加密模組。 多個 Microsoft 產品（包含許多雲端服務）使用這些加密模組。

如需 Microsoft Windows 密碼模組的技術資訊、每個模組的安全性原則，以及 CMVP 憑證詳細資料的目錄，請參閱 [windows 和 Windows SERVER FIPS 140-2 內容](https://aka.ms/AA6ehud)。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 範圍內雲端服務

目前的 CMVP FIPS 140-2 實現指導方針會排除雲端服務本身的 FIPS 140-2 驗證，但雲端服務提供者可以選擇針對組成其雲端服務的計算元素，選擇取得並運作 FIPS 140 驗證的密碼模組。 Microsoft online services （包括已驗證 FIPS 140-2 的元件）包含下列各種：

- [Azure 和 Azure Government](https://docs.microsoft.com/azure/azure-government/documentation-government-plan-security)
- [Dynamics 365 和 Dynamics 365 政府](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-microsoft-dynamics-365)
- [Office 365、Office 365 美國政府和 Office 365 美國政府國防版](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections)

## <a name="frequently-asked-questions"></a>常見問題集

**「FIPS 140 驗證」和「FIPS 140 相容性」的差異為何？**

「FIPS 140 驗證」表示加密模組或內嵌模組的產品已驗證 ( 「已驗證」 ) 由 CMVP 為會議，以滿足 FIPS 140-2 的需求。 「FIPS 140 相容」是 IT 產品的行業術語，其適用于已驗證 FIPS 140 的產品以取得加密功能。

**Microsoft 何時使用 FIPS 140 驗證？**

開始模組驗證的節奏會與 Windows 10 和 Windows Server 的功能更新搭配使用。 隨著軟體行業的演化，作業系統的發行頻率也會隨每月軟體更新。 Microsoft undertakes 的功能版本驗證，但在兩個版本之間，尋找最小化加密模組的變更。

**FIPS 140 驗證中包含哪一部電腦？**

Microsoft 會驗證加密模組，其具有執行 Windows 10 和 Windows Server 的硬體設定範例。 在環境使用硬體時（類似于驗證程式使用的範例），常見的行業作法是接受此 FIPS 140-2 驗證。

**NIST 網站上列出了許多模組。如何知道哪一種適用于我的代理人？**

如果您需要使用透過 FIPS 140-2 驗證的加密模組，您必須確認您所用的版本會出現在 [驗證] 清單中。 CMVP 和 Microsoft 維護已驗證的加密模組清單，依產品版本加以組織，以及識別在 Windows 系統上安裝哪些模組的指示。 如需設定系統相容性的詳細資訊，請參閱 [windows 和 Windows SERVER FIPS 140-2 內容](https://aka.ms/AA6ehud)。

**「在 FIPS 模式中運作」在憑證上的意義為何？**

這項警告會告訴讀者，必須遵循必要的設定及安全性規則，以符合其 FIPS 140-2 安全性原則的方式使用加密模組。 每個模組都有其自己的安全性原則（其運作所依據的安全性規則的確切規格），並採用核准的加密演算法、加密金鑰管理和驗證技術。 安全性規則是定義于每個模組的安全性原則中。 如需詳細資訊，包括透過 CMVP 驗證之每個模組的安全性原則連結，請參閱 [windows 和 Windows SERVER FIPS 140-2 內容](https://aka.ms/AA6ehud)。

**FedRAMP 是否需要 FIPS 140-2 驗證？**

是的，「聯邦風險和授權管理」方案 (FedRAMP) 取決於 [NIST SP 800-53 Revision 4](https://nvd.nist.gov/800-53/Rev4/)所定義的控制基準，包含 [SC-13 加密保護](https://nvd.nist.gov/800-53/Rev4/control/SC-13) ，使用 FIPS 驗證的密碼編譯或 NSA 核准的密碼編譯。

**Microsoft Azure 如何支援 FIPS 140-2？**

Azure 是以硬體、商用作業系統 (Linux 和 Windows) 和 Azure 特有版本的 Windows 所組成。 透過 Microsoft [Security 開發週期](https://www.microsoft.com/securityengineering/sdl/) (SDL) ，所有 Azure 服務都會使用 fips 140-2 核准的演算法進行資料安全性，因為作業系統會使用 fips 140-2 核准的演算法，在超大規模雲端上運作。

**我是否可以在代理人的認證程式中使用 Microsoft 遵守 FIPS 140-2 的功能？**

若要遵守 FIPS 140-2，您的系統必須設定為在作業的 FIPS 核准模式中執行，包括確保密碼模組只使用 FIPS 核准的演算法。 如需設定系統相容性的詳細資訊，請參閱 [windows 和 Windows SERVER FIPS 140-2 內容](https://aka.ms/AA6ehud)。

**FIPS 140-2 與通用準則之間的關係為何？**

這些是兩個不同的安全性標準，但相互互補。 FIPS 140-2 是專門設計用來驗證軟體和硬體密碼模組，而一般的準則是用來評估 IT 軟體和硬體產品中的安全性功能。 常見的準則評估通常會依靠 FIPS 140-2 驗證，以確保基本的加密功能已正確地執行。

## <a name="resources"></a>資源

- [FIPS Pub 140-2 加密模組的安全性需求](https://csrc.nist.gov/publications/fips/fips140-2/fips1402.pdf)
- [NIST 加密模組驗證程式](https://csrc.nist.gov/groups/STM/cmvp/index.html)
- [Windows、Windows Server 及 FIPS 140-2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)
- [Microsoft 信任中心的合規性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
