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
description: 整合和雲端解決方案提供者 (CSP) 合作夥伴如何使用 Windows PowerShell 來管理 Microsoft 365 客戶承租人。
ms.openlocfilehash: 352a9a01414b94a1593de6a734151b687524fe7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909523"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="29fd1-103">如何利用適用于委派存取權限的 Windows PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29fd1-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="29fd1-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="29fd1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="29fd1-105">委派的存取權限 (DAP) 合作夥伴就是新聞訂閱方式和雲端解決方案提供者 (CSP) 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="29fd1-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="29fd1-106">許多是網路或電信提供者。</span><span class="sxs-lookup"><span data-stu-id="29fd1-106">Many are network or telecom providers.</span></span> <span data-ttu-id="29fd1-107">他們會將 Microsoft 365 訂閱捆綁至其服務產品。</span><span class="sxs-lookup"><span data-stu-id="29fd1-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="29fd1-108">當他們銷售 Microsoft 365 訂閱時，系統會自動授與 (AOBO 的「管理」) 許可權給客戶的租用，讓他們能管理及報告這些租用。</span><span class="sxs-lookup"><span data-stu-id="29fd1-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="29fd1-109">在 Microsoft 365 系統管理中心中，這些工作很困難。</span><span class="sxs-lookup"><span data-stu-id="29fd1-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="29fd1-110">使用 Microsoft 365 PowerShell 來執行系統管理工作，例如：</span><span class="sxs-lookup"><span data-stu-id="29fd1-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="29fd1-111">列出所有客戶 **TenantIds** 及其網域</span><span class="sxs-lookup"><span data-stu-id="29fd1-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="29fd1-112">識別客戶租使用者中的所有使用者及其指派的授權</span><span class="sxs-lookup"><span data-stu-id="29fd1-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="29fd1-113">有些系統管理工作只能在 PowerShell 中完成。</span><span class="sxs-lookup"><span data-stu-id="29fd1-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="29fd1-114">下列文章說明供稿和 CSP 合作夥伴如何使用 PowerShell 管理其客戶租用：</span><span class="sxs-lookup"><span data-stu-id="29fd1-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="29fd1-115">使用 Windows PowerShell 管理適用于委派存取權限的 Microsoft 365 租使用者 (結合) 夥伴</span><span class="sxs-lookup"><span data-stu-id="29fd1-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="29fd1-116">利用適用於委派存取權限 (DAP) 合作夥伴的 Windows PowerShell 新增用戶端租用網域</span><span class="sxs-lookup"><span data-stu-id="29fd1-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="29fd1-117">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="29fd1-117">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [<span data-ttu-id="29fd1-118">利用適用於委派存取權限 (DAP) 合作夥伴的 Windows PowerShell 擷取客戶租用戶報告資料</span><span class="sxs-lookup"><span data-stu-id="29fd1-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
