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
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927285"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="d4fea-103">從商務用 Skype 與 Exchange 移除或停用混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="d4fea-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="d4fea-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="d4fea-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d4fea-105">如果您已啟用混合式新式驗證 (HMA) 找到它不適用於您目前的環境，您可以停用 HMA。</span><span class="sxs-lookup"><span data-stu-id="d4fea-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="d4fea-106">本文說明如何進行。</span><span class="sxs-lookup"><span data-stu-id="d4fea-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="d4fea-107">本文是針對哪些專案神秘的？</span><span class="sxs-lookup"><span data-stu-id="d4fea-107">Who is this article for?</span></span>

<span data-ttu-id="d4fea-108">如果您已在商務用 Skype Online 或內部部署以及（或） Exchange Online 或內部部署中啟用新式驗證，且找到您需要停用 HMA，這些步驟適用于您。</span><span class="sxs-lookup"><span data-stu-id="d4fea-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4fea-109">若您在商務用 Skype 線上或內部部署中使用混合式拓撲 HMA，請參閱「[新式驗證支援的商務用 Skype 拓撲](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)」，並在您開始之前，先查看支援的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d4fea-109">See the '[Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="d4fea-110">如何停用混合式新式驗證 (Exchange) </span><span class="sxs-lookup"><span data-stu-id="d4fea-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="d4fea-111">**Exchange 內部部署**：開啟 Exchange 管理命令介面，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d4fea-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="d4fea-112">**Exchange Online**：[連線 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)使用遠端 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d4fea-112">**Exchange Online**: [Connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="d4fea-113">執行下列命令，將您的  *OAuth2ClientProfileEnabled*  旗標轉換為 "false"：</span><span class="sxs-lookup"><span data-stu-id="d4fea-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="d4fea-114">如何停用混合式新式驗證 (商務用 Skype) </span><span class="sxs-lookup"><span data-stu-id="d4fea-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="d4fea-115">**商務用 Skype 內部部署**：在商務用 Skype 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d4fea-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="d4fea-116">**線上商務用 Skype**：[連線商務用 Skype](manage-skype-for-business-online-with-microsoft-365-powershell.md)使用遠端 PowerShell 線上。</span><span class="sxs-lookup"><span data-stu-id="d4fea-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="d4fea-117">執行下列命令以停用新式驗證：</span><span class="sxs-lookup"><span data-stu-id="d4fea-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="d4fea-118">[連結回新式驗證概述](hybrid-modern-auth-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="d4fea-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
