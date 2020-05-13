---
title: 在獨立 EOP 中審核報告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 管理員可以深入瞭解 Exchange Online Protection （EOP）中提供的系統管理員審核報告
ms.openlocfilehash: 33bed333c9ea71077b976d0a83612de127053e24
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208932"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="ace7c-103">在獨立 EOP 中審核報告</span><span class="sxs-lookup"><span data-stu-id="ace7c-103">Auditing reports in standalone EOP</span></span>

<span data-ttu-id="ace7c-104">在沒有 Exchange Online 信箱的獨立 Exchange Online Protection （EOP）組織中，審核報告可協助您符合組織的法規、規範和訴訟需求。</span><span class="sxs-lookup"><span data-stu-id="ace7c-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="ace7c-105">您可以隨時取得稽核報告，來判斷已對 EOP 組態所做的變更。</span><span class="sxs-lookup"><span data-stu-id="ace7c-105">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="ace7c-106">這些報告可協助您疑難排解組態問題，或找出安全性相關或規範相關問題的原因。</span><span class="sxs-lookup"><span data-stu-id="ace7c-106">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="ace7c-107">EOP 中有兩種可用的稽核報告：</span><span class="sxs-lookup"><span data-stu-id="ace7c-107">There are two auditing reports available in EOP:</span></span>

- <span data-ttu-id="ace7c-108">**系統管理員**角色群組報告：系統管理員角色群組報告可讓您查看使用者何時新增或移除系統管理員角色群組中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="ace7c-108">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="ace7c-109">您可以使用此報告，來監視已指派給貴組織中使用者之系統管理權限的變更。</span><span class="sxs-lookup"><span data-stu-id="ace7c-109">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="ace7c-110">如需詳細資訊，請參閱[在獨立 EOP 中執行系統管理員角色群組報告](run-an-administrator-role-group-report-in-eop-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="ace7c-110">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="ace7c-111">**管理員審核記錄**：系統管理員審核記錄會記錄系統管理員或具有系統管理許可權之使用者的任何動作（以 Exchange Online Protection PowerShell Cmdlet 為基礎）。</span><span class="sxs-lookup"><span data-stu-id="ace7c-111">**Administrator audit log**: The administrator audit log records any action (based on Exchange Online Protection PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="ace7c-112">如需詳細資訊，請參閱[在 Exchange Online 中查看系統管理員審核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)。</span><span class="sxs-lookup"><span data-stu-id="ace7c-112">For more information, see [View the Administrator Audit Log in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>
