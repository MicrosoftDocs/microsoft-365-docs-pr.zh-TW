---
title: 反詐騙保護常見問題集
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以在 Exchange Online Protection (EOP) 中，查看有關反欺騙保護的常見問題及解答。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5843ee7f791fbc2c37914194b153fdd05866d0a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059031"
---
# <a name="anti-spoofing-protection-faq"></a>反詐騙保護常見問題集

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

本文針對 Exchange Online 中的信箱，或獨立 Exchange Online Protection (EOP) 組織中的 Microsoft 365 組織，提供有關反欺騙保護的常見問題和解答，但沒有 Exchange Online 信箱。

如需反垃圾郵件保護的相關問題和解答，請參閱 [反垃圾郵件保護常見問題](anti-spam-protection-faq.md)。

如需有關反惡意程式碼保護的問題和解答，請參閱 [反惡意程式碼保護常見問題](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Microsoft 為何選擇未驗證的垃圾輸入電子郵件？

Microsoft 相信，繼續允許未驗證的輸入電子郵件的風險，會高於遺失合法輸入電子郵件的風險。

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Junking 未驗證的輸入電子郵件是否導致合法的電子郵件標示為垃圾郵件？

當 Microsoft 在2018中啟用這項功能時，會發生一些誤報 (良好的郵件會標示為壞) 。 不過，隨著時間的變化，寄件者會調整為要求。 對於大部分的電子郵件路徑，已 misidentified 為欺騙的郵件數目會變得忽略。

Microsoft 本身會在將新的電子郵件驗證需求部署給客戶之前，先採用一周。 一開始會出現一些干擾，但慢慢的會減少。

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>是否有欺騙性智慧可用於不含 Defender for Office 365 的 Microsoft 365 客戶？

是。 從10月2018到10月為止，具有 Exchange Online 信箱的所有組織，以及沒有 Exchange Online 信箱的獨立 EOP 組織皆可取得欺騙智慧。

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>如何向 Microsoft 回報垃圾郵件或非垃圾郵件？

請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>我是系統管理員，但我不知道我的電子郵件網域中的所有郵件來源！

請參閱 [您不知道電子郵件的所有來源](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)。

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>如果我停用組織的反欺騙保護，會發生什麼事？

我們不建議停用反欺詐防護。 停用保護將允許在您的組織中傳遞更多網路釣魚和垃圾郵件。 並非所有網路釣魚皆為欺騙性，而且不會丟失所有的冒牌郵件。 不過，您的風險會更高。

現在可以使用 [增強型連接器篩選](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) ，當您的電子郵件透過另一個服務進行 EOP 之前，我們不再建議您關閉反欺騙保護。

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>反欺騙保護的意思是我會保護所有網路釣魚嗎？

不幸的是，不。 攻擊者會使用其他技術 (例如，在免費的電子郵件服務) 中已遭破壞的帳戶或帳戶。 不過，反網路釣魚保護的運作速度很好于偵測其他類型的網路釣魚方法。 EOP 中的保護層是設計一起運作，彼此上建立。

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>其他大型電子郵件服務會封鎖未驗證的輸入電子郵件嗎？

幾乎所有大型的電子郵件服務都會執行傳統的 SPF、DKIM 及 DMARC 檢查。 有些服務有其他更為嚴格的檢查，但不是 EOP 來封鎖未驗證的電子郵件，並將其視為欺騙性的電子郵件。 不過，該行業正深入瞭解未驗證電子郵件的問題，尤其是由於網路釣魚問題所導致。

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>我還是需要啟用高級垃圾郵件篩選器設定 "SPF record： hard fail" (_MarkAsSpamSpfRecordHardFail_) 如果我啟用反欺騙功能？

否。 不再需要這種 ASF 設定。 反欺騙保護會考慮這兩種 SPF 硬性失敗及一組更豐富的準則。 如果您已啟用反詐騙功能，並且開啟 **SPF 記錄：驗證失敗** (_MarkAsSpamSpfRecordHardFail_)，則可能會發生更多誤判。

我們建議您停用此功能，因為它幾乎不會提供偵測垃圾郵件或網路釣魚郵件的額外權益，而會產生大部分的誤報。 如需詳細資訊，請參閱 [EOP 中的高級垃圾郵件篩選 (ASF) 設定](advanced-spam-filtering-asf-options.md)。

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>寄件者重新寫入架構是否有助於修正轉寄的電子郵件？

SRS 僅能修正轉寄電子郵件的部分問題。 透過重新寫入 SMTP **郵件**，SRS 可確保轉寄的郵件透過下一個目的地的 SPF。 不過，由於反欺騙是以 [寄件者 **] 或 [** DKIM-簽署] (網域中所結合的 [**發件** 人] 和 [] 或 [] （其他）) 的方式來進行反欺騙，所以無法防止 SRS 轉寄的電子郵件被標示為欺騙