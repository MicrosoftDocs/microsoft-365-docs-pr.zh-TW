---
title: 密碼原則建議
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: 了解如何加強貴組織對密碼攻擊的防護，以及為何應禁用常見密碼並啟用以風險為根據的多重要素驗證。
ms.openlocfilehash: 1d6e399acb83751ec6a45eb0c811dedec394127e
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015920"
---
# <a name="password-policy-recommendations"></a>密碼原則建議
 
身為組織的系統管理員，您必須為貴組織中的使用者設定密碼原則。 設定密碼原則相當複雜且令人困惑，因此本文提供加強貴組織對密碼攻擊的防護的建議。
  
若要判斷貴組織中的 Microsoft 365 密碼到期頻率，請參閱[設定 Microsoft 365 的密碼到期原則](../manage/set-password-expiration-policy.md)。

如需有關 Microsoft 365 密碼的詳細資訊，請參閱這些[相關文章](#related-articles)。
  
## <a name="understanding-password-recommendations"></a>了解密碼建議

良好的密碼實踐分為幾大類：
  
- **抵禦常見攻擊**：這涉及選擇讓使用者在何處輸入密碼 (具有良好惡意程式碼偵測的已知和信任的裝置、經過驗證的網站)，以及選擇要選用哪個密碼 (長度和唯一性)。

- **包含成功的攻擊**：包含成功駭客攻擊是指限制僅向特定服務公開，或在使用者密碼遭竊的情況下完全防止該損失。 例如，確保社交網路認證外洩不會導致銀行帳戶易受攻擊，也不會讓防護較弱的帳戶接受重要帳戶的重設連結。

- **了解人的天性**：許多有效的密碼實踐都在面對自然的人類行為時失敗。 了解人的天性至關重要，因為研究結果顯示，幾乎每條強加於使用者的規則都會導致密碼品質降低。 長度要求、特殊字元要求和密碼變更要求都會導致密碼標準化，讓攻擊者更容易猜測或破解密碼。

## <a name="password-guidelines-for-administrators"></a>系統管理員的密碼指導方針

加強密碼系統安全的主要目標是密碼多樣性。 您希望密碼原則包含許多不同且難以猜測的密碼。 以下是一些讓貴組織盡可能安全的建議。
  
- 維持至少 8 個字元的長度要求 (更長不一定更好)

- 不設定字元構成要求。 例如，\*&amp;(^%$

- 不要求使用者帳戶定期重設密碼

- 禁止常見密碼，使系統中不存在容易受到攻擊的密碼

- 教育使用者不要將其組織密碼重複用於與工作無關的用途

- 強制註冊[多重要素驗證](../security-and-compliance/set-up-multi-factor-authentication.md)

- 克服以風險為根據的多重要素驗證挑戰

### <a name="password-guidance-for-your-users"></a>使用者密碼指導方針

以下是提供貴組織使用者的一些密碼指導方針。 請務必讓您的使用者了解這些建議，並在組織層級強制執行建議的密碼原則。
  
- 請勿使用在任何其他網站上所使用的相同或相似密碼

- 請勿只用一個單字，例如 **password**，也不要使用常用片語，例如 **Iloveyou**

- 使密碼變得難以猜測，讓即使熟悉您的人也難以猜測，例如，不要使用朋友和家人的姓名和生日、喜歡的樂團，以及您喜歡使用的語句

## <a name="some-common-approaches-and-their-negative-impacts"></a>一些常見做法及其負面影響

以下是一些最常使用的密碼管理做法，但是研究結果警告我們注意這些做法的負面影響。
  
### <a name="password-expiration-requirements-for-users"></a>使用者密碼到期要求

密碼到期要求弊大於利，因為這些要求會讓使用者選擇可預測的密碼，即由彼此密切相關的連續字詞和數字組成的密碼。 在這些情況下，下一個密碼可根據先前的密碼來預測。 密碼到期要求不會提供任何控制優勢，因為網路罪犯總會在盜取憑證後立即使用憑證。
  
### <a name="requiring-long-passwords"></a>要求使用長密碼

密碼長度要求 (大於約 10 個字元) 可能會導致可預測且不必要的使用者行為。 例如，必須具有 16 個字元密碼的使用者可能會選擇 **fourfourfourfour** 或 **passwordpassword** 等符合字元長度要求但不難猜測的重複模式。 此外，長度要求會提高使用者採用其他不安全做法的機會，例如將密碼寫下來、重複使用密碼，或將密碼不加密地儲存在文件中。 若要鼓勵使用者考慮使用唯一密碼，建議您維持符合 8 個字元的最小長度要求。 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>要求使用多個字元集

密碼複雜性要求會縮減金鑰空間，並讓使用者以可預測的方式行動，因此弊大於利。 大多數系統都會強制實施一定程度的密碼複雜性要求。 例如，密碼需要使用下列所有三種類別的字元：
  
- 大寫字元 

- 小寫字元

- 非英數字元

大多數使用者都會使用類似的模式，例如，第一個位置使用大寫字母、最後一位使用符號，倒數第 2 位使用數字。 網路罪犯知道這一點，因此他們在執行字典攻擊時會使用最常見的替換，例如：$ 替換為 s、@ 替換為 a，1 替換為 l。 強制使用者選擇大寫、小寫、數字、特殊字元的組合會造成負面影響。 有些複雜性要求甚至會妨礙使用者使用安全易記的密碼，並迫使他們採用安全性較低且更難記住的密碼。
  
## <a name="successful-patterns"></a>成功的模式

相比之下，以下是鼓勵密碼多樣性的一些建議。
  
### <a name="ban-common-passwords"></a>禁用常見密碼

建立密碼時，您應對使用者提出的最重要的密碼要求是禁用常見密碼，使貴組織更不容易受到暴力密碼破解攻擊。 常見的使用者密碼包括 **abdcefg**、**password**、**monkey**。
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>教育使用者不要在其他位置重複使用組織密碼

要傳達給組織內部使用者的最重要訊息之一是不要在任何其他位置重複使用其組織密碼。 在外部網站使用組織密碼會大幅增加網路罪犯盜用這些密碼的可能性。
  
### <a name="enforce-multi-factor-authentication-registration"></a>強制執行多重要素驗證註冊

請確保您的使用者更新連絡人和安全性資訊，例如備用電子郵件地址、電話號碼或註冊接收推播通知的裝置，以便讓使用者應對安全性挑戰及收到安全性事件通知。 更新的連絡人和安全性資訊可協助使用者在忘記密碼時或其他人嘗試接管其帳戶時驗證他們的身分。 並在登入嘗試或變更密碼等安全性事件的情況下提供頻外通知頻道。 
  
若要深入瞭解，請參閱[設定多重要素驗證](../security-and-compliance/set-up-multi-factor-authentication.md)。
  
### <a name="enable-risk-based-multi-factor-authentication"></a>啟用以風險為根據的多重要素驗證

以風險為根據的多重要素驗證可確保系統偵測到可疑活動時，能迫使使用者確保其為合法帳戶擁有者。 
  
## <a name="want-to-know-more-recommended-reading"></a>想要進一步了解嗎？ 建議閱讀

- [Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008) (強大的網站密碼是否有用？)

- [Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014) (密碼組合和努力有限的使用者)

- [Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015) (透過閱讀使用者的思維來防止弱式密碼)

- [Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016) (選擇安全密碼)

- [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) (是時候重新思考強制密碼變更了)

- [Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020) (2015 年最差密碼)

- [Download files from the web](https://go.microsoft.com/fwlink/p/?linkid=861029) (從網頁下載檔案)

## <a name="related-articles"></a>相關文章

[重設密碼](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[設定個別使用者的密碼永不過期](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[讓使用者重設自己的密碼](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[重新傳送使用者的密碼 - 系統管理說明](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
