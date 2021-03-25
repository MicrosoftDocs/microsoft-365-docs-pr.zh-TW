---
title: 獨立版 EOP 中的稽核報告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: '系統管理員可以瞭解 Exchange Online Protection (EOP 中可用的系統管理員審計報告) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08432f97d196df8b661d63a5d4cdf3680b78e070
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203535"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="add91-103">獨立版 EOP 中的稽核報告</span><span class="sxs-lookup"><span data-stu-id="add91-103">Auditing reports in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="add91-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="add91-104">**Applies to**</span></span>
-  [<span data-ttu-id="add91-105">Exchange Online Protection 獨立</span><span class="sxs-lookup"><span data-stu-id="add91-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="add91-106">在獨立 Exchange Online Protection (EOP 中) 沒有 Exchange Online 信箱的組織，審核報告可協助您符合組織的法規、規範和訴訟需求。</span><span class="sxs-lookup"><span data-stu-id="add91-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="add91-107">您可以隨時取得稽核報告，來判斷已對 EOP 組態所做的變更。</span><span class="sxs-lookup"><span data-stu-id="add91-107">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="add91-108">這些報告可協助您疑難排解組態問題，或找出安全性相關或規範相關問題的原因。</span><span class="sxs-lookup"><span data-stu-id="add91-108">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="add91-109">獨立 EOP 中有兩個審計報告可供使用：</span><span class="sxs-lookup"><span data-stu-id="add91-109">There are two auditing reports available in standalone EOP:</span></span>

- <span data-ttu-id="add91-110">**系統管理員** 角色群組報告：系統管理員角色群組報告可讓您查看使用者何時新增或移除系統管理員角色群組中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="add91-110">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="add91-111">您可以使用此報告，來監視已指派給貴組織中使用者之系統管理權限的變更。</span><span class="sxs-lookup"><span data-stu-id="add91-111">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="add91-112">如需詳細資訊，請參閱 [在獨立 EOP 中執行系統管理員角色群組報告](run-an-administrator-role-group-report-in-eop-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="add91-112">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="add91-113">**系統管理員審核記錄**：系統管理員審核記錄會根據獨立 EOP PowerShell Cmdlet) 由系統管理員或具有系統管理許可權的使用者，記錄任何動作 (。</span><span class="sxs-lookup"><span data-stu-id="add91-113">**Administrator audit log**: The administrator audit log records any action (based on standalone EOP PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="add91-114">如需詳細資訊，請參閱 [在 Exchange Online 中查看系統管理員審核記錄](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)。</span><span class="sxs-lookup"><span data-stu-id="add91-114">For more information, see [View the Administrator Audit Log in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>