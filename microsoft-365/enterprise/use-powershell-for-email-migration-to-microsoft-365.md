---
title: 使用 PowerShell 將電子郵件移轉至 Microsoft 365
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 795158e1-7dfc-4d9e-b805-373dd576c4e7
description: 在本文中，您將瞭解如何使用 PowerShell 將電子郵件從現有的系統移轉至 Microsoft 365。
ms.openlocfilehash: afbed872c3cac483c63e8a2d537931220c3c349c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688856"
---
# <a name="use-powershell-for-email-migration-to-microsoft-365"></a><span data-ttu-id="0bf9e-103">使用 PowerShell 將電子郵件移轉至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0bf9e-103">Use PowerShell for email migration to Microsoft 365</span></span>

<span data-ttu-id="0bf9e-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="0bf9e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0bf9e-105">當系統管理員第一次設定 Microsoft 365 時，許多人會從現有系統移轉電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-105">When administrators first set up Microsoft 365, many of them migrate email from existing systems.</span></span> <span data-ttu-id="0bf9e-106">您也可以使用 Microsoft 365 系統管理中心來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-106">You can also do this by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="0bf9e-107">您也可以使用 Windows PowerShell 來移轉電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-107">You can also use Windows PowerShell to migrate email.</span></span>
  
<span data-ttu-id="0bf9e-108">使用 Windows PowerShell 將電子郵件遷移至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-108">Use Windows PowerShell to migrate email to Microsoft 365.</span></span> 
  
- [<span data-ttu-id="0bf9e-109">使用 PowerShell 以完全移轉至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0bf9e-109">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md)
    
- [<span data-ttu-id="0bf9e-110">使用 PowerShell 將 IMAP 移轉至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0bf9e-110">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>](use-powershell-to-perform-an-imap-migration-to-microsoft-365.md)
    
- [<span data-ttu-id="0bf9e-111">使用 PowerShell 以階段移轉至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0bf9e-111">Use PowerShell to perform a staged migration to Microsoft 365</span></span>](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md)
    
## <a name="related-topics"></a><span data-ttu-id="0bf9e-112">相關主題</span><span class="sxs-lookup"><span data-stu-id="0bf9e-112">Related topics</span></span>

[<span data-ttu-id="0bf9e-113">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0bf9e-113">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0bf9e-114">開始使用適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bf9e-114">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0bf9e-115">使用 PowerShell 管理 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0bf9e-115">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
<span data-ttu-id="0bf9e-116">[使用 Windows PowerShell 在 Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md) 
 中建立報告[為什麼您需要使用 Microsoft 365 PowerShell](why-you-need-to-use-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="0bf9e-116">[Use Windows PowerShell to create reports in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)
[Why you need to use Microsoft 365 PowerShell](why-you-need-to-use-microsoft-365-powershell.md)</span></span>
  
[<span data-ttu-id="0bf9e-117">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="0bf9e-117">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

