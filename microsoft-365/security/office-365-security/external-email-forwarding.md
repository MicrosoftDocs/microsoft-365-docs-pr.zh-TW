---
title: 設定及控制外部電子郵件轉寄、自動轉寄、拒絕5.7.520 存取、停用外部轉寄、系統管理員已停用外部轉寄、輸出反垃圾郵件原則
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 7cb2ab9c6987900f2b53a17c3eda49001bca4d84
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898049"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>在 Office 365 中設定外部電子郵件轉發功能

外部轉送是由 *輸出反垃圾郵件原則* 所控制，並根據設定的設定範圍限定為使用者。 目前支援的設定如下：

- **自動** –在這種模式下，系統負責決定是否允許轉寄的郵件。  這是預設模式，在這種模式下，系統會封鎖自動外部轉送。

- **開啟** -允許和不限制自動外部轉送。

- **Off** –會停用自動外部轉送，並且會產生未傳遞回報 (NDR) 給使用者。

如需如何設定這些設定的詳細資訊，請參閱 [設定 EOP 中的外寄垃圾郵件篩選](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) 。

## <a name="controlling-external-email-forwarding"></a>控制外部電子郵件轉發

做為組織的系統管理員，您可能需要限制或控制誰可以使用收件匣規則或在組織外部的 SMTP 轉寄功能，自動轉寄電子郵件。 電子郵件轉寄可能是一項非常實用的功能，但也可以透過可能披露的資訊來帶來風險，即使是提供可被攻擊者攻擊組織或其合作夥伴的資訊也是一樣的。

Office 365 不允許由收件匣規則或信箱設定自動進行外部轉送，這會提供安全的預設原則。 不過，系統管理員可以針對組織中的所有使用者或部分使用者修改這些設定。 在內部使用者之間轉發郵件不會受到這類修改的影響。

> [!NOTE]
> 停用 Office 365 中的自動轉寄外部地址時，將會逐步顯示詳細資訊透過 [訊息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) 文章進行通訊。 若要協助系統管理員準備這些變更，請提前修改原則，以確保使用者沒有任何中斷。

在您組織中使用自動轉寄 (收件匣規則或 SMTP 轉送) 使用者的詳細資訊，可以在 [ [自動轉寄的郵件] 報告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide)中找到。

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a>這個原則如何與其他自動轉寄控制項搭配使用

身為系統管理員，您可能已經有其他類型的控制項，例如封鎖 [遠端網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) 中的自動轉送，以及使用 Exchange Transport RULE (ETR) 。 這兩個控制項都獨立于此特定功能，例如，如果允許遠端網域的自動轉寄，但透過輸出垃圾郵件原則封鎖自動轉寄，結果將會封鎖自動轉寄的郵件。 同樣地，如果您允許在輸出垃圾郵件原則中自動轉寄，但在 ETR 或遠端網域中封鎖它，則這兩個控制項中的任何一個都會封鎖郵件。 例如，您可以讓您在輸出垃圾郵件原則中允許自動轉寄，並利用遠端網域來控制使用者可以自動轉寄郵件的網域。


## <a name="the-blocked-email-forwarding-message"></a>封鎖的電子郵件轉發郵件

當以自動轉寄方式偵測到郵件 *時，如果* 有未傳遞回報的活動 ** (NDR) ** 會產生給使用者。 報告會指出郵件未傳遞。 NDR 會有下列格式： 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
