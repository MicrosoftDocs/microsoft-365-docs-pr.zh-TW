---
title: 使用 PowerShell 管理 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- O365ITProTrain
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 932d57c0-1520-4f0f-8ec9-9966d646480f
description: 瞭解如何使用 PowerShell 來管理 Microsoft 365 使用者、授權和365應用程式。
ms.openlocfilehash: dee8fbce03e38a954ddea5a8ec86248f9209d96c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905101"
---
# <a name="manage-microsoft-365-with-powershell"></a><span data-ttu-id="0540a-103">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0540a-103">Manage Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="0540a-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="0540a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0540a-105">PowerShell Microsoft 365 是一種強大的管理工具，可補充 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="0540a-105">PowerShell for Microsoft 365 is a powerful management tool that complements the Microsoft 365 admin center.</span></span> <span data-ttu-id="0540a-106">例如，您可以使用 PowerShell 自動化來輕鬆管理多個使用者帳戶和授權，以及建立報告。</span><span class="sxs-lookup"><span data-stu-id="0540a-106">For example, you can use PowerShell automation to easily manage multiple user accounts and licenses and to create reports.</span></span>

<span data-ttu-id="0540a-107">從下列主題中進行選取，以瞭解如何使用 PowerShell 來管理 Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="0540a-107">Select from the following topics to learn how to use PowerShell to manage Microsoft 365:</span></span>
  
- [<span data-ttu-id="0540a-108">**快速入門**</span><span class="sxs-lookup"><span data-stu-id="0540a-108">**Get started**</span></span>](getting-started-with-microsoft-365-powershell.md)

    <span data-ttu-id="0540a-109">如果您不熟悉 Microsoft 365 的 PowerShell，而您想要安裝 Microsoft 365 模組並連接到您的訂閱，請從這裡開始。</span><span class="sxs-lookup"><span data-stu-id="0540a-109">Start here if you're not familiar with PowerShell for Microsoft 365, and you want to install the Microsoft 365 modules and connect to your subscription.</span></span>

- [<span data-ttu-id="0540a-110">**使用者帳戶、授權和群組**</span><span class="sxs-lookup"><span data-stu-id="0540a-110">**User accounts, licenses, and groups**</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

    <span data-ttu-id="0540a-111">若要瞭解如何使用自動化命令來管理使用者帳戶、授權和群組，請從這裡開始。</span><span class="sxs-lookup"><span data-stu-id="0540a-111">Start here if want to learn about using automation commands to manage user accounts, licenses, and groups.</span></span>

- [<span data-ttu-id="0540a-112">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="0540a-112">**SharePoint**</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)

    <span data-ttu-id="0540a-113">如果您想要使用自動化命令來管理 SharePoint，請從這裡開始。</span><span class="sxs-lookup"><span data-stu-id="0540a-113">Start here if you want to use automation commands to manage SharePoint.</span></span>

- [<span data-ttu-id="0540a-114">**Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="0540a-114">**Exchange Online**</span></span>](/powershell/exchange/exchange-online-powershell)

    <span data-ttu-id="0540a-115">如果您想要管理 Exchange Online，請從這裡開始。</span><span class="sxs-lookup"><span data-stu-id="0540a-115">Start here if you want to manage Exchange Online.</span></span>

- [<span data-ttu-id="0540a-116">**電子郵件遷移**</span><span class="sxs-lookup"><span data-stu-id="0540a-116">**Email migration**</span></span>](use-powershell-for-email-migration-to-microsoft-365.md)

    <span data-ttu-id="0540a-117">如果您想要從預先存在的系統移轉您的電子郵件，請從這裡開始。</span><span class="sxs-lookup"><span data-stu-id="0540a-117">Start here if you want to migrate your email from pre-existing systems.</span></span>

- [<span data-ttu-id="0540a-118">**安全性與合規性中心**</span><span class="sxs-lookup"><span data-stu-id="0540a-118">**Security & Compliance Center**</span></span>](/powershell/exchange/scc-powershell)

    <span data-ttu-id="0540a-119">如果您想要管理安全性 & 規範中心功能，請從這裡開始。</span><span class="sxs-lookup"><span data-stu-id="0540a-119">Start here if you want to manage Security & Compliance Center features.</span></span>

- [<span data-ttu-id="0540a-120">**(一起) 合作夥伴的委派存取許可權**</span><span class="sxs-lookup"><span data-stu-id="0540a-120">**Delegated Access Permissions (DAP) partners**</span></span>](manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-dap-p.md)

    <span data-ttu-id="0540a-121">如果您想要使用供稿和雲端解決方案提供者 (CSP) 合作夥伴管理您的 Microsoft 365 客戶承租人，請從這裡開始。</span><span class="sxs-lookup"><span data-stu-id="0540a-121">Start here if you want to use Syndication and Cloud Solution Provider (CSP) partners to manage your Microsoft 365 customer tenants.</span></span>

- [<span data-ttu-id="0540a-122">**商務用 Skype Online**</span><span class="sxs-lookup"><span data-stu-id="0540a-122">**Skype for Business Online**</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)

    <span data-ttu-id="0540a-123">從這裡開始管理商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="0540a-123">Start here to manage Skype for Business Online.</span></span>