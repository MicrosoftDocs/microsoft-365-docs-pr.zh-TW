---
title: Microsoft 365 Defender 入口網站中的郵件追蹤
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以使用 Microsoft 365 Defender 入口網站中的郵件追蹤連結，以找出郵件發生的情況。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108112"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 入口網站中的郵件追蹤

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender 入口網站中的郵件追蹤會沿著電子郵件訊息傳送 Exchange Online 組織。 您可以判斷服務是否已經收到、拒絕、延遲或傳遞郵件。 它也會顯示在郵件到達其最終狀態前，已對郵件執行哪些動作。

您可以使用郵件追蹤中的資訊，有效地解答使用者對郵件發生什麼問題、疑難排解郵件流程問題，以及驗證原則變更。

> [!NOTE]
> Microsoft 365 Defender 入口網站中的郵件追蹤只是 Exchange 系統管理中心內的郵件追蹤。 如需詳細資訊，請參閱[新式 Exchange 系統管理中心的郵件追蹤](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您必須是「**組織管理**」、「**合規性管理** **」或「服務台」** 角色群組的成員，才能 **Exchange Online** 使用郵件追蹤。 如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  **附注**： Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色中的成員資格，可為使用者提供 Microsoft 365 中其他功能所需的許可權 _和_ 許可權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

- 在郵件追蹤結果中顯示的訊息數目上限取決於您選取的報告類型 (請參閱 [選擇報告類型](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) 一節，以取得詳細資料) 。 Exchange Online PowerShell 或獨立 EOP 中的[Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) Cmdlet PowerShell 會傳回結果中的所有郵件。

## <a name="open-message-trace"></a>開啟郵件追蹤

在 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 中，移至 [**電子郵件 &** 共同作業 \> **Exchange 郵件追蹤**]。 或者，若要直接移至 [郵件追蹤] 頁面，請使用 <https://admin.exchange.microsoft.com/#/messagetrace> 。

此時，EAC 中的郵件追蹤隨即開啟。 如需詳細資訊，請參閱[新式 Exchange 系統管理中心的郵件追蹤](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)。
