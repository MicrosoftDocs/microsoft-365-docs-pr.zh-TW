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
ms.openlocfilehash: f44dc509e28c19c320418c28dda6146331669cde
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314473"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>設定 Microsoft 365 Scheduler


若要設定 Microsoft 365 的排程器，請遵循下列必要條件：

| 我需要什麼？ | 描述 |
|-------------------|-------------|
|Cortana 信箱 |租使用者系統管理員必須將信箱設定為「Cortana」信箱 (，也就是 cortana@yourdomain.com) 。         |
|Exchange Online 信箱 |使用者必須要有 Exchange Online 郵件和行事曆         |
|排程程式授權 |如需授權及定價資訊，請參閱排程[程式 Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)。        |

## <a name="create-a-mailbox-for-cortana"></a>建立 Cortana 的信箱

您租使用者中的 Exchange 信箱充當租使用者傳送和接收 Cortana 中的電子郵件的 Cortana 信箱。 所有傳送至 Cortana 的電子郵件會根據您的保留原則，保留在租使用者的 Cortana 信箱中。

- 使用 Microsoft 365 系統管理中心建立使用者信箱。 建議使用30天的保留原則。 
- 使用您信箱的主要 SMTP 位址中 Cortana 的名稱。 名稱，例如 "Cortana @yourdomain .com"、"CortanaScheduler@contoso.com" 或 "Cortana。Scheduler@yourdomain.com ' 是建議的。

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>將信箱指定為計畫程式助理

建立 Cortana 排程器的唯一信箱之後，您必須指定要 Microsoft 365 正式的信箱。 指定 Cortana 排程信箱之後，就可以代表您的使用者排程會議。

若要指定 Cortana 排程信箱，授權的系統管理員必須執行單行 PowerShell 命令。 

1. 連線以 Microsoft 365 組織的遠端 PowerShell 執行空間。

2. 執行下列 PowerShell 腳本，以指定排程器的信箱：

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    在 Cortana 排程者信箱上執行這個「設定」命令之後，會在信箱上設定新的「PersistedCapability」，以附注此信箱是 "SchedulerAssistant"。

> [!NOTE]
> 請遵循下列步驟，將您的組織連接至 PowerShell （如果先前尚未執行此動作）：[連線 Microsoft 365 PowerShell](../enterprise/connect-to-microsoft-365-powershell.md)。

若要找出貴組織中的哪個信箱目前已設定為 Cortana 的排程器助理，請執行 get 函數：

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> 最多可能需要兩個小時的時間，讓計畫程式信箱完成完整布建，以設定 SchedulerAssistant 功能。

## <a name="exchange-online-mailbox"></a>Exchange Online 信箱

排程器是 Microsoft 365 的附加元件。 會議召集人必須有 Exchange Online 的信箱和行事曆，排程才能正常運作。

## <a name="exchange-requirements"></a>Exchange 需求

除了授權排程之外，您必須具有下列其中一個授權：

- Microsoft 365 E3，A3，E5，A5
- Business Basic、商務、商務標準、商務進階版
- Office 365 E1，A1，E3，A3，E5，A5
- 商務基本版、商務進階版
- Exchange Online方案1或計畫2授權。 

> [!Note]
> 目前只有全球多承租人的使用者可以使用 **Microsoft 365** 的排程器，純英文。</br>
>
> 在中國或使用 Telekom 的德語雲端 Microsoft 365 使用者的中，使用者無法使用 Office 365。 德國使用者的資料位置若不在德國資料中心，則適用此工具。
>
> 此功能也不支援政府雲端的使用者，包括 GCC、Consumer、GCC High 或 DoD。
