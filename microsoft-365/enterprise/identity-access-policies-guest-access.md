---
title: 身分識別與裝置存取原則允許來賓及外部網路 B2B 存取-Microsoft 365 企業版 |Microsoft Docs
description: 說明建議的條件式存取和保護來賓與外部使用者存取的相關的原則。
author: BrendaCarter
manager: johmar
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 4ef679ed6fef217be112317d03d12c007b1375fd
ms.sourcegitcommit: 7c977771fc295ca1e4e9b16a6d05faee8edeadad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "37913338"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>允許來賓及外部網路 B2B 存取原則
本文說明如何調整建議一般身分識別與裝置存取原則，以允許 B2B 帳戶存取權 （來賓和外部使用者）。 本指南為基礎的[常見身分識別與裝置存取原則](identity-access-policies.md)。

這些建議被設計來套用保護的**基準**層。 不過，您可以調整的建議，根據您所需要的保護**機密**和**高管制**的資料粒度。 

提供 B2B 使用者向您的 Azure AD 租用戶的路徑不會授與這些使用者存取整個環境。 B2B 使用者只需要與他們共用 （例如檔案） 的資源的存取權授與條件式存取原則中的服務內。

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>更新以允許與保護來賓與外部存取的一般原則 

下圖說明常見的身分識別與裝置存取原則，並指出 （與 [鉛筆] 圖示） 來新增或更新來保護來賓與外部存取原則。 

![保護來賓存取原則更新的摘要](../images/identity-access-ruleset-guest.png)

下表列出您需要更新或建立新的原則。 一般原則連結至[常見的身分識別與裝置存取原則](identity-access-policies.md)> 一文中的關聯的設定指示。

|保護層級|原則|詳細資訊|
|:---------------|:-------|:----------------|
|**Baseline**|[來賓與外部使用者一律需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|建立此新規則，它只適用於來賓與外部使用者。 [登入風險，保留所有選項已取消核取一律強制執行 MFA。|
|        |[登入風險*中*] 或 [*高*時需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|修改此規則，以排除來賓與外部使用者。|
|        |[需要相容的電腦](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|修改此規則，以排除來賓與外部使用者。|

若要包含或排除來賓和條件式存取規則中的外部使用者，按一下包含或排除] 索引標籤上，檢查**所有來賓和外部使用者。**

![排除來賓的控制項的螢幕擷取畫面](../images/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>詳細資訊

### <a name="guests-vs-external-users"></a>與外部使用者的來賓
在 Azure AD 中來賓和外部的使用者都相同。 這兩種使用者輸入是來賓。 來賓使用者是 B2B 使用者。

Microsoft Teams 來賓使用者和應用程式內的外部使用者之間的差異，但以下是這兩個 B2B 使用者進行驗證時。 如需 Teams 來賓與外部使用者的詳細資訊，請參閱[啟用來賓和 microsoft Teams 的外部存取](teams-access-policies.md#enabling-guest-and-external-access-for-teams)。

### <a name="require-mfa-always-for-guest-and-external-users"></a>來賓與外部使用者一律需要 MFA
此規則會提示來賓在您的租用戶，不論是否他們正在註冊 MFA 其住家租用戶中註冊的 mfa 功能。 存取您的租用戶中的資源時, 的來賓與外部使用者必須使用 MFA 每一個要求。 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>從風險的 MFA 排除來賓與外部使用者
雖然組織可以強制執行風險型原則 B2B 使用者使用 Identity Protection，有 B2B 共同作業中的使用者由於其首頁中現有其身分識別的資源目錄 Identity Protection 的實作限制目錄。 由於這些限制，Microsoft 建議您排除風險的 MFA 原則中的來賓使用者，且需要這些使用者一律使用 MFA。 

如需詳細資訊，請參閱[Identity Protection 的限制為 B2B 共同作業使用者](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。 

### <a name="excluding-guest-and-external-users-from-device-management"></a>排除來賓與外部使用者從裝置管理 
只有一個組織可以管理裝置。 如果您不需要裝置相容性的原則排除來賓及外部使用者，這些原則會封鎖這些使用者。 

## <a name="next-steps"></a>後續步驟

[了解如何啟用 Teams 條件式存取](teams-access-policies.md)

