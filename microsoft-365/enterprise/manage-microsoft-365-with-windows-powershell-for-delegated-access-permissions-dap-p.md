---
title: 使用適用于合作協力廠商的 Windows PowerShell 管理 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: 摘要：整合和雲端解決方案提供者 (CSP) 合作夥伴可以使用 Windows PowerShell 來管理 Microsoft 365 客戶承租人。
ms.openlocfilehash: d4109c09a14fb5644d34daf24383053536440871
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688716"
---
# <a name="manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="a2935-103">使用 Windows PowerShell 管理已委派存取權 (聯) 合作夥伴的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a2935-103">Manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="a2935-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="a2935-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a2935-105">委派的存取權限 (DAP) 合作夥伴就是新聞訂閱方式和雲端解決方案提供者 (CSP) 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="a2935-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="a2935-106">他們通常是其他公司的網路或電信服務提供者。</span><span class="sxs-lookup"><span data-stu-id="a2935-106">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="a2935-107">他們會將 Microsoft 365 訂閱捆綁到其客戶的服務產品中。</span><span class="sxs-lookup"><span data-stu-id="a2935-107">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="a2935-108">當他們銷售 Microsoft 365 訂閱時，系統會自動授與 (AOBO 的「管理」) 許可權給客戶租用，讓他們能管理及報告客戶租用。</span><span class="sxs-lookup"><span data-stu-id="a2935-108">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span> <span data-ttu-id="a2935-109">在 Microsoft 365 系統管理中心中，這是很困難且耗時的做法。</span><span class="sxs-lookup"><span data-stu-id="a2935-109">At best, this is difficult and time consuming to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a2935-110">更容易執行管理工作，例如列出所有客戶 **TenantIds** 及其網域，或使用 Microsoft 365 的 PowerShell 來識別客戶租使用者中的所有使用者，以及這些使用者所指派的授權。</span><span class="sxs-lookup"><span data-stu-id="a2935-110">It is much easier to do administrative tasks like listing all the customer **TenantIds** and their domains or identifying all users in a customer tenancy and what licenses they are assigned by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="a2935-111">在某些情況下，您可以只在 Microsoft 365 的 PowerShell 中執行下列管理工作。</span><span class="sxs-lookup"><span data-stu-id="a2935-111">In some cases, it is possible to do these administrative tasks only in PowerShell for Microsoft 365.</span></span> <span data-ttu-id="a2935-112">以下是新聞訂閱方式和 CSP 合作夥伴最常用來管理客戶租用的範例案例：</span><span class="sxs-lookup"><span data-stu-id="a2935-112">Here are samples of scenarios that Syndication and CSP partners most frequently use to administer their customer tenancies:</span></span>
  
## 

- [<span data-ttu-id="a2935-113">使用 Windows PowerShell 管理適用于委派存取權限的 Microsoft 365 租使用者 (結合) 夥伴</span><span class="sxs-lookup"><span data-stu-id="a2935-113">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="a2935-114">利用適用於委派存取權限 (DAP) 合作夥伴的 Windows PowerShell 新增用戶端租用網域</span><span class="sxs-lookup"><span data-stu-id="a2935-114">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="a2935-115">利用適用於委派存取權限 (DAP) 合作夥伴的遠端 Windows PowerShell 連線至 Exchange Online 租用戶</span><span class="sxs-lookup"><span data-stu-id="a2935-115">Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="a2935-116">利用適用於委派存取權限 (DAP) 合作夥伴的 Windows PowerShell 擷取客戶租用戶報告資料</span><span class="sxs-lookup"><span data-stu-id="a2935-116">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
    

    

