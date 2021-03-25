---
title: 設定及控制外部電子郵件轉寄、自動轉寄、拒絕5.7.520 存取、停用外部轉寄、系統管理員已停用外部轉寄、輸出反垃圾郵件原則
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0f42da077ca84341824fad01fcb23eae976336a1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203510"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>在 Microsoft 365 中控制自動外部電子郵件轉接

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

身為系統管理員，您可能會有公司需求，以限制或控制自動轉寄的郵件至外部收件者 (組織外) 收件者。 電子郵件轉寄可能非常有用，但由於可能洩漏資訊，也可能會造成安全性風險。 攻擊者可能會利用此資訊來攻擊您的組織或合作夥伴。


Microsoft 365 提供下列自動轉送類型：

- 使用者可以設定 [收件匣規則](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) ，自動將郵件轉寄給外部寄件者 (故意或因遭到破壞的帳戶) 。

- 系統管理員可以設定 [信箱轉送](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (又稱為 _SMTP 轉送_) ，以自動將郵件轉寄給外部收件者。 管理員可以選擇是否只轉寄郵件，或將轉寄郵件的副本保留在信箱中。

您可以使用輸出垃圾郵件篩選原則來控制自動轉寄給外部收件者。 有三個可用的設定：

- **自動**：封鎖自動外部轉送。 內部自動轉送郵件功能將繼續運作。 這是預設設定。
- **開啟**：允許和不限制自動外部轉送。
- **Off**：停用自動外部轉寄，將會造成未傳遞回報 (也稱為 NDR 或退回的郵件) 傳送給寄件者。

如需如何設定這些設定的指示，請參閱 [CONFIGURE EOP 中的外寄垃圾郵件篩選](configure-the-outbound-spam-policy.md)。

> [!NOTE]
>
> - 停用自動轉寄功能會停用 (使用者) 或信箱轉寄 (系統管理員) 將郵件重新導向至外部地址的任何收件匣規則。
>
> - 內部使用者之間的自動轉送郵件不會受到輸出垃圾郵件篩選原則中的設定。
>
> - 您可以在 [ [自動轉寄的郵件] 報告](mfi-auto-forwarded-messages-report.md)中看到自動轉送郵件至外部收件者之使用者的相關資訊。

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>輸出垃圾郵件篩選原則設定如何使用其他自動電子郵件轉接控制項

若您是系統管理員，您可能已經設定其他控制項，以允許或封鎖自動電子郵件轉發。 例如：

- 可允許或封鎖自動將電子郵件轉寄至部分或所有外部網域的[遠端網域](/exchange/mail-flow-best-practices/remote-domains/remote-domains)。

- Exchange [郵件流程規則](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 中的條件和動作 (也稱為傳輸規則) 偵測並封鎖自動轉寄的郵件至外部收件者。

遠端網域設定和郵件流程規則獨立于輸出垃圾郵件篩選原則中的設定。 例如：

- 您允許遠端網域的自動轉寄，但是會封鎖輸出垃圾郵件篩選原則中的自動轉送。 在此範例中，自動轉寄的郵件會遭到封鎖。

- 您可以在輸出垃圾郵件篩選原則中允許自動轉寄，但您可以使用郵件流程規則或遠端網域設定封鎖自動轉寄的電子郵件。 在此範例中，郵件流程規則或遠端網域設定會封鎖自動轉寄的郵件。

這種功能的獨立功能可讓您 (例如，) 允許在輸出垃圾郵件篩選原則中自動轉寄，但使用遠端網域來控制使用者可以轉寄郵件的外部網域。

## <a name="blocked-email-forwarding-messages"></a>封鎖電子郵件轉發郵件

當以自動轉寄方式偵測到郵件，而 [輸出垃圾郵件篩選器](configure-the-outbound-spam-policy.md) 原則 *封鎖* 該活動時，郵件會傳回給寄件者的 NDR 中包含下列資訊：

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`