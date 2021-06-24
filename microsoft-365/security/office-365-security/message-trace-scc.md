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
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="f4e74-103">Microsoft 365 Defender 入口網站中的郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="f4e74-103">Message trace in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f4e74-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="f4e74-104">**Applies to**</span></span>
- [<span data-ttu-id="f4e74-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f4e74-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f4e74-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="f4e74-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f4e74-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4e74-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f4e74-108">Microsoft 365 Defender 入口網站中的郵件追蹤會沿著電子郵件訊息傳送 Exchange Online 組織。</span><span class="sxs-lookup"><span data-stu-id="f4e74-108">Message trace in the Microsoft 365 Defender portal follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="f4e74-109">您可以判斷服務是否已經收到、拒絕、延遲或傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="f4e74-109">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="f4e74-110">它也會顯示在郵件到達其最終狀態前，已對郵件執行哪些動作。</span><span class="sxs-lookup"><span data-stu-id="f4e74-110">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="f4e74-111">您可以使用郵件追蹤中的資訊，有效地解答使用者對郵件發生什麼問題、疑難排解郵件流程問題，以及驗證原則變更。</span><span class="sxs-lookup"><span data-stu-id="f4e74-111">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="f4e74-112">Microsoft 365 Defender 入口網站中的郵件追蹤只是 Exchange 系統管理中心內的郵件追蹤。</span><span class="sxs-lookup"><span data-stu-id="f4e74-112">Message trace in the Microsoft 365 Defender portal is just a pass through to Message trace in the Exchange admin center.</span></span> <span data-ttu-id="f4e74-113">如需詳細資訊，請參閱[新式 Exchange 系統管理中心的郵件追蹤](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)。</span><span class="sxs-lookup"><span data-stu-id="f4e74-113">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f4e74-114">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="f4e74-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f4e74-115">您必須是「**組織管理**」、「**合規性管理** **」或「服務台」** 角色群組的成員，才能 **Exchange Online** 使用郵件追蹤。</span><span class="sxs-lookup"><span data-stu-id="f4e74-115">You need to be a member of the **Organization Management**, **Compliance Management** or **Help Desk** role groups in **Exchange Online** to use message trace.</span></span> <span data-ttu-id="f4e74-116">如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="f4e74-116">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="f4e74-117">**附注**： Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色中的成員資格，可為使用者提供 Microsoft 365 中其他功能所需的許可權 _和_ 許可權。</span><span class="sxs-lookup"><span data-stu-id="f4e74-117">**Notes**: Membership in the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f4e74-118">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f4e74-118">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="f4e74-119">在郵件追蹤結果中顯示的訊息數目上限取決於您選取的報告類型 (請參閱 [選擇報告類型](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) 一節，以取得詳細資料) 。</span><span class="sxs-lookup"><span data-stu-id="f4e74-119">The maximum number of messages that are displayed in the results of a message trace depends on the report type you selected (see the [Choose report type](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) section for details).</span></span> <span data-ttu-id="f4e74-120">Exchange Online PowerShell 或獨立 EOP 中的[Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) Cmdlet PowerShell 會傳回結果中的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="f4e74-120">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="f4e74-121">開啟郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="f4e74-121">Open message trace</span></span>

<span data-ttu-id="f4e74-122">在 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 中，移至 [**電子郵件 &** 共同作業 \> **Exchange 郵件追蹤**]。</span><span class="sxs-lookup"><span data-stu-id="f4e74-122">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration** \> **Exchange message trace**.</span></span> <span data-ttu-id="f4e74-123">或者，若要直接移至 [郵件追蹤] 頁面，請使用 <https://admin.exchange.microsoft.com/#/messagetrace> 。</span><span class="sxs-lookup"><span data-stu-id="f4e74-123">Or, to go directly to the message trace page, use <https://admin.exchange.microsoft.com/#/messagetrace>.</span></span>

<span data-ttu-id="f4e74-124">此時，EAC 中的郵件追蹤隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="f4e74-124">At this point, message trace in the EAC opens.</span></span> <span data-ttu-id="f4e74-125">如需詳細資訊，請參閱[新式 Exchange 系統管理中心的郵件追蹤](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)。</span><span class="sxs-lookup"><span data-stu-id="f4e74-125">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>
