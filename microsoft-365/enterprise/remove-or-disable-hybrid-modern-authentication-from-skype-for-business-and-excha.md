---
title: 從商務用 Skype 與 Exchange 移除或停用混合式新式驗證
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 本文說明如何從商務用 Skype 和 Exchange 中移除或停用混合式新式驗證。
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547093"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="a4387-103">從商務用 Skype 與 Exchange 移除或停用混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="a4387-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="a4387-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="a4387-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a4387-105">如果您已啟用混合式新式驗證 (HMA) 找到它不適用於您目前的環境，您可以停用 HMA。</span><span class="sxs-lookup"><span data-stu-id="a4387-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="a4387-106">本文說明如何進行。</span><span class="sxs-lookup"><span data-stu-id="a4387-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="a4387-107">本文的人選是誰？</span><span class="sxs-lookup"><span data-stu-id="a4387-107">Who is this article for?</span></span>

<span data-ttu-id="a4387-108">如果您已在商務用 Skype Online 或內部部署和/或 Exchange Online 或內部部署中啟用新式驗證，且找到您需要停用 HMA，這些步驟適用于您。</span><span class="sxs-lookup"><span data-stu-id="a4387-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4387-109">若您是在商務用 Skype Online 或內部部署中，請參閱「[新式驗證支援的商務用 skype 拓撲](https://technet.microsoft.com/library/mt803262.aspx)」文章，其具有混合拓撲 HMA，您必須先查看支援的拓撲，再開始。</span><span class="sxs-lookup"><span data-stu-id="a4387-109">See the '[Skype for Business topologies supported with Modern Authentication](https://technet.microsoft.com/library/mt803262.aspx)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="a4387-110">如何停用混合式新式驗證 (Exchange) </span><span class="sxs-lookup"><span data-stu-id="a4387-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="a4387-111">**Exchange 內部部署**：開啟 Exchange 管理命令介面，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a4387-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="a4387-112">**Exchange online**：以遠端 PowerShell [連接至 Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="a4387-112">**Exchange Online**: [Connect to Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="a4387-113">執行下列命令，將您的  *OAuth2ClientProfileEnabled*  旗標轉換為 "false"：</span><span class="sxs-lookup"><span data-stu-id="a4387-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="a4387-114">如何停用 (商務用 Skype) 的混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="a4387-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="a4387-115">**商務用 skype 內部部署**：在商務用 Skype 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a4387-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="a4387-116">**商務用 Skype online**：使用遠端 PowerShell [連接至商務用 skype online](manage-skype-for-business-online-with-microsoft-365-powershell.md) 。</span><span class="sxs-lookup"><span data-stu-id="a4387-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="a4387-117">執行下列命令以停用新式驗證：</span><span class="sxs-lookup"><span data-stu-id="a4387-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="a4387-118">[連結回新式驗證概述](hybrid-modern-auth-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="a4387-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
  

