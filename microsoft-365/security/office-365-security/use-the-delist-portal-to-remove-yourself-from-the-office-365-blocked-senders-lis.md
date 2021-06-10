---
title: 將您自己從封鎖的寄件者清單中移除
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何使用取消列出入口網站，將您自己從 Microsoft 365 封鎖的寄件者清單中移除。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4488f5e5607d71da35b2921e863fb02195467e2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203705"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>使用取消列出入口網站，將您自己從封鎖寄件者清單中移除

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

當您嘗試將電子郵件傳送給其電子郵件地址為 Microsoft 365 的收件者時，您收到錯誤訊息嗎？ 如果您認為您不應該收到錯誤訊息，您可以使用取消列出入口網站，將您自己從 [封鎖的寄件者] 清單中移除。

## <a name="what-is-the-blocked-senders-list"></a>什麼是封鎖的寄件者清單？

Microsoft 會使用封鎖寄件者清單，來保護其客戶避免垃圾郵件、詐騙和網路釣魚攻擊。 您的郵件伺服器的 IP 位址（亦即，郵件伺服器用來在網際網路上識別自己的位址）已標記為因各種原因之一而 Microsoft 365 的潛在威脅。 當 Microsoft 365 將 ip 位址新增至清單時，它會防止 ip 位址與我們所有客戶透過我們的資料中心之間的進一步通訊。

當您收到包含錯誤如下的郵件訊息時，您就會知道您已新增至清單：

> 550 5.7.606-649 拒絕存取，禁止傳送 IP _位址 [ip 位址_];若要向此清單要求移除，請流覽 <https://sender.office.com/> 並依照指示執行。 如需詳細資訊，請參閱[Exchange Online 中的電子郵件未傳遞](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)回報。

其中  _IP address_ 是郵件伺服器執行所在之電腦的 IP 位址。

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>若要使用取消列出入口網站，將您自己從封鎖的寄件者清單中移除

1. 在 Web 瀏覽器中，移至 <https://sender.office.com>。

2. 遵循頁面中的指示。請確定您使用被傳送錯誤訊息的電子郵件地址，以及在錯誤訊息中指定的 IP 位址。您每次造訪只能輸入一個電子郵件地址及一個 IP 位址。

3. 按一下 **[送出]**。

    入口網站會將電子郵件傳送至您提供的電子郵件地址。 電子郵件看起來如下所示： ![ 透過取消列出入口網站提交要求時，收到的電子郵件螢幕擷取畫面](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. 按一下取消列出入口網站傳送給您的電子郵件中的確認連結。

    這可以讓您回到取消列出入口網站。

5. 在取消列出入口網站中，按一下 **[取消列出 IP]**。

    從封鎖的寄件者清單中移除 IP 位址之後，來自該 IP 位址的電子郵件將會傳遞給使用 Microsoft 365 的收件者。 因此，請確認您確信從該 IP 位址傳送的電子郵件沒有不當或惡意，否則，可能會再度封鎖 IP 位址。

    > [!NOTE]
    > 最多可能需要24小時的時間，否則結果會在移除限制之前有很大的差異。

請參閱 [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md) 和 [EOP 的輸出垃圾郵件保護](outbound-spam-controls.md) ，以防止 IP 遭到封鎖。