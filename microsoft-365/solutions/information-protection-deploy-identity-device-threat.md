---
title: 使用資料隱私權規定的身分識別、裝置和威脅防護
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: 使用 Microsoft 365 的身分識別、裝置和威脅防護服務，避免個人資料遭到破壞。
ms.openlocfilehash: a309b5d0ba5f939cf89a31d7ac91ca3aac25ce0d
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2020
ms.locfileid: "46520978"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>使用資料隱私權規定的身分識別、裝置和威脅防護

Microsoft 365 提供許多身分識別、裝置和威脅防護功能，組織可以採取這些功能來協助遵守資料隱私權相關的相容性法規。 本文說明這些方面的資料隱私權法規所需的內容，並提供相關 Microsoft 365 功能和服務的清單，其中包含可協助您處理實施需求的詳細資訊連結。

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>身分識別、裝置和威脅防護與資料隱私權規定的關聯方式

資料隱私權規定在其明確程度上有所不同時，其所呼叫的實質會包含在 GDPR 的第5（1）（f）專案中，這表明： 

- 個人資料的處理方式是為了確保個人資料的適當安全性，包括防止未經授權或非法處理的保護，以及使用適當的技術或組織量值（「誠信」和「機密性」）以避免意外遺失、損毀或損毀。

由於個人資料損損通常是由系統管理或使用者帳戶損損和惡意的系統存取而造成。 例如，系統管理員帳戶的駭客攻擊可能會導致客戶信用卡號碼或其他個人資訊的 exfiltration。 可能應該實施 Microsoft 365 的所有一般建議身分識別、裝置和威脅防護，這會反映您的合規性分數。

## <a name="using-the-results-of-your-assessment-work-and-compliance-score"></a>使用評估工作和合規性分數的結果

合規性分數包括使用下列類別的身分識別、裝置和威脅防護：

- Identity 會對應至**控制項存取**類別
- 裝置對應于 [**管理裝置**] 類別
- 威脅防護會對應至 [**防護威脅**] 類別
 
如果已在我們四個主要資料隱私權規定的範例集中選取這些選項，則符合性分數會指定90改進動作，大部分的分數為 "27"。 由於這類大量的數位是由這些類別的合規性分數所呼叫，因此這裡會列出一些較為常見的數位，供您參考。

使用[Azure Active Directory （AZURE AD）](https://azure.microsoft.com/services/active-directory/)做為身分識別和**控制存取**類別，您可以：

- 實施重新顯示抵抗驗證（以防止「中間人」攻擊）
- 封鎖舊版驗證。
- 設定使用者風險和使用者登入風險原則。
- 啟用系統管理員和非系統管理員的條件式存取和多重要素驗證（MFA）。
- 設定並強制執行密碼原則。
- 使用 Azure AD 特權身分識別管理限制存取特權帳戶。
- 在終止時停用存取。
- 審核使用者帳戶和狀態變更。
- 審閱角色群組和系統管理變更。

使用適用于裝置的[Microsoft 端點管理員](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)和**管理裝置**類別，您可以：

- 封鎖越獄中斷及根行動裝置。
- 設定 Intune 以進行行動裝置管理。
- 建立 Android、iOS、macOS 和 Windows 裝置的相容性原則。
- 建立適用于 Android、iOS、macOS 和 Windows 裝置的裝置設定檔。
- 建立 iOS 和 Windows 的應用程式保護原則。
- 以鎖定畫面隱藏資訊。
- 為行動裝置實施密碼原則。
- 要求行動裝置在非活動狀態時鎖定。
- 要求行動裝置會在多個登入失敗時擦章。

針對 [**防護威脅**] 類別使用[Exchange Online Protection 和 Office 365 的高級威脅防護（ATP）](../security/office-365-security/office-365-atp.md) ，您可以：

- 啟用寄件者驗證（SPF、DMARC 及 DKIM）。
- 設定 Office 365 高級威脅防護（ATP）反網路釣魚原則。
- 實施 ATP 安全附件。
- 實施 ATP 安全連結。
- 實施惡意程式碼偵測和回應原則。
- 實施輸出和輸入的垃圾郵件原則。

### <a name="references"></a>引用：

- [一般身分識別與裝置存取原則](../enterprise/identity-access-policies.md)
- [保護 Office 365 中的威脅](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [ATP 安全附件](../security/office-365-security/atp-safe-attachments.md)
- [ATP 安全連結](../security/office-365-security/atp-safe-links.md)
- [ATP 安全文件](../security/office-365-security/safe-docs.md)
