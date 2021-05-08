---
title: 設定 Microsoft 365 的調度程式。
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: 設定 Microsoft 365 的調度程式。
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286155"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>設定 Microsoft 365 的調度程式

若要設定 Microsoft 365 的排程器，請遵循下列必要條件：

|**我需要什麼？** |**描述** |
|-------------------|-------------|
|Cortana 信箱 |租使用者系統管理員必須將信箱設定為「Cortana」信箱 (，也就是 cortana@yourdomain.com) 。         |
|Exchange Online 信箱 |使用者必須要有 Exchange Online 郵件和行事曆         |
|排程程式授權 |如需授權及定價資訊，請參閱排程[程式 Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)。        |

## <a name="create-a-mailbox-for-cortana"></a>建立 Cortana 的信箱
您租使用者中的 Exchange 信箱充當您租使用者的 cortana 信箱，用以傳送和接收 Cortana 的電子郵件。 傳送至 Cortana 的所有電子郵件都會根據您的保留原則保留在租使用者的 Cortana 信箱中。

- 使用 Microsoft 365 系統管理中心來建立新的信箱。 建議使用30天的保留原則。 在您信箱的主要 SMTP 位址中使用「Cortana 名稱。 建議使用名稱，例如 "Cortana@yourdomain.com"、"CortanaScheduler@contoso.com" 或 "Cortana.Scheduler@yourdomain.com"。
- 請與 Microsoft (scheduler_m365@microsoft.com) 聯繫，以啟用 Cortana 信箱。 

> [!IMPORTANT]
> 您必須與 Microsoft 聯繫才能將您的 Cortana 信箱設定為透過電子郵件 scheduler_m365@microsoft.com 使用排程器服務。 啟用您的 Cortana 信箱可能需要長達兩周。

## <a name="exchange-online-mailbox"></a>Exchange Online 信箱
排程器是 Microsoft 365 的附加元件。 會議召集人必須有 Exchange Online 的信箱和行事曆，排程才能正常運作。

## <a name="exchange-requirements"></a>Exchange 需求

除了授權排程之外，您必須具有下列其中一個授權：

- Microsoft 365 E3，A3，E5，A5
- Business Basic、商務、商務標準、商務進階版
- Office 365E1，A1，E3，A3，E5，A5
- 商務基本版、商務進階版
- Exchange Online方案1或計畫2授權。 

> [!Note]
> 在中國由世紀運作之 Office 365 的使用者都無法使用 **Microsoft 365** 的排程器。 使用 Telekom 的德語 cloud，Microsoft 365 使用者也無法使用此功能。 德國使用者的資料位置若不在德國資料中心，則適用此工具。
>
>此功能也不支援政府雲端的使用者，包括 GCC、Consumer、GCC High 或 DoD。
