---
title: 在 Office 365 中建立封鎖寄件者清單
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 封鎖寄件者清單選項包括 Outlook 封鎖寄件者、 反垃圾郵件寄件者/網域封鎖清單、 IP 封鎖清單，以及 Exchange 傳輸規則 (Etr) 也稱為郵件流程規則。
ms.openlocfilehash: 861fa0e47980a6bc295672cf1e8e35954c6f1dfb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077992"
---
# <a name="create-block-sender-lists-in-office-365"></a>在 Office 365 中建立封鎖寄件者清單

有時會需要封鎖寄件者的垃圾電子郵件。 有數種方法可從選擇。 這些選項包括 Outlook 封鎖寄件者、 反垃圾郵件寄件者/網域封鎖清單、 IP 封鎖清單，以及 Exchange 傳輸規則 (Etr，也就是也稱為郵件流程規則)。

> [!NOTE]
> 雖然可用於組織封鎖清單地址 false 負號 （未接的垃圾郵件），這些應徵者應也要送出給 Microsoft 進行分析。 誤判使用管理的封鎖清單會大幅增加您管理的額外負荷。 如果您將會使用封鎖清單達到此目的，您必須同時保留文章[提交垃圾郵件、 非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)，在準備。

若要設定封鎖的寄件者清單的適當方法影響的範圍而有所不同。 單一使用者的影響，右解決方案可能是使用 Outlook 封鎖寄件者，但如果多個使用者或所有使用者正在受影響，其中一個其他選項會更合適。

## <a name="options-from-least-to-broadest-scope"></a>從最小到最大範圍的選項

建立封鎖清單時很重要挑選適合的方法，根據 （會影響多少人） 的影響，範圍，使其符合封鎖方法的廣度。 下面所列的選項會透過範圍和廣度排名。 清單會從窄到廣泛，但*讀取特定內容*的完整的建議。

- Outlook 封鎖的寄件者
- 反垃圾郵件原則： 寄件者/網域封鎖清單
- Exchange 傳輸規則 （Etr 也稱為的郵件流程規則）
- 反垃圾郵件原則： IP 封鎖清單

## <a name="use-outlook-blocked-senders"></a>使用 Outlook 封鎖的寄件者

只有少數使用者會受到影響，這是時，也應該使用 Outlook 封鎖寄件者，因為這只會影響郵件傳送給它們。

> [!IMPORTANT]
> 如果不想要的郵件新聞稿信譽及辨識的來源，取消訂閱電子郵件中是用來停止從未來取得電子郵件使用者的其他選項。

若要設定此案例的步驟是[Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46)和[Outlook 用戶端](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)之間的不同。 **郵件已成功封鎖由於封鎖寄件者時您會看到 sfv: X-Forefront-反垃圾郵件的報告**指出郵件會遭到封鎖。

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a>使用反垃圾郵件原則/網域的寄件者封鎖清單

時所受影響多個使用者，範圍更廣，且您需要使用全公司的寄件者/網域 」 封鎖清單反垃圾郵件原則。 詳細的步驟可以[設定您的垃圾郵件篩選原則](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies)的文件中找到。 已封鎖透過此方法的任何訊息會遵循 [垃圾郵件] 動作，該原則中設定的一樣。

這些清單的最大限制為大約 1000年項目。

## <a name="use-exchange-transport-rules-etrs-to-block-specific-senders"></a>使用 Exchange 傳輸規則 (Etr) 來封鎖特定寄件者

必要時要傳送給特定使用者或整個組織的封鎖郵件，可以使用 Etr （也稱為郵件流程規則）。 Etr 是更有彈性，因為他們可以觸發關閉寄件者電子郵件地址或網域，以及關鍵字和訊息中的其他屬性。 這種彈性可讓您建立或部分-完整區塊。 [請按一下 [建立 ETR，也稱為郵件流程規則的步驟](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages)。

> [!IMPORTANT]
> 很容易建立*過度*積極的規則，因此請務必正在使用的準則會儘可能指定特定。 此外，請務必啟用稽核規則建立並執行測試，以確保每個項目如預期般運作。

## <a name="use-anti-spam-policy-ip-block-lists"></a>使用反垃圾郵件原則 IP 封鎖清單

*然後*反垃圾郵件原則 IP 封鎖清單時不能使用下列其中一個其他選項來封鎖寄件者，都可以使用。 [可以在文章 Configure the connection filter policy > 中找到的詳細的步驟](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy)。 請務必保留到*最小*的 Ip 封鎖清單，並*不*建議在這裡使用的 IP 位址範圍。

您應該*特別*避免新增 IP 位址範圍，屬於消費者服務或共用的基礎結構，也請務必定期維護的一部分檢閱允許的 IP 位址清單。 **因為可讓項目可以開啟攻擊的路由，您必須密切管理這份清單，並定期移除允許的項目，但不再需要。** 此外，如果您將會讓使用者在 [安全寄件者清單中請務必閱讀並瞭解的風險和預防措施來*[建立安全的寄件者列出 Office 365 中](create-safe-sender-lists-in-office-365.md)*。
