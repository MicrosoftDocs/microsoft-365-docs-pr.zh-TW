---
title: Microsoft 365用戶端應用程式支援：條件式存取
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: 在本文中，瞭解哪些平臺、用戶端和 PowerShell 模組支援條件式 Microsoft 365 Access。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7b0b65ea25091aad01fd8741f9925f2b545e9c4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904959"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="1281c-103">Microsoft 365用戶端應用程式支援：條件式存取</span><span class="sxs-lookup"><span data-stu-id="1281c-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="1281c-104">在新式的工作場所，使用者可以使用各種裝置和應用程式從任何地方存取您組織的資源。</span><span class="sxs-lookup"><span data-stu-id="1281c-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="1281c-105">因此，只關注可以存取資源的人員，已不再足夠。</span><span class="sxs-lookup"><span data-stu-id="1281c-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="1281c-106">您的組織也必須支援在存取控制基礎結構中存取資源的方式和位置。</span><span class="sxs-lookup"><span data-stu-id="1281c-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="1281c-107">使用 Azure Active Directory 裝置、位置及多重要素驗證型條件式存取，您可以符合此新需求。</span><span class="sxs-lookup"><span data-stu-id="1281c-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="1281c-108">條件式存取是 Azure Active Directory 的功能，可讓您強制存取您環境中應用程式的控制，所有這些都是以特定條件為基礎，並從中央位置進行管理。</span><span class="sxs-lookup"><span data-stu-id="1281c-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="1281c-109">深入瞭解[Azure Active Directory 條件式存取](/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="1281c-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="1281c-110">支援的用戶端 & 平臺</span><span class="sxs-lookup"><span data-stu-id="1281c-110">Supported clients & platforms</span></span>

<span data-ttu-id="1281c-111">下列用戶端和平臺的最新版本支援條件式存取。</span><span class="sxs-lookup"><span data-stu-id="1281c-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="1281c-112">如需 Microsoft 365 中平臺支援的詳細資訊，請參閱[Microsoft 365 的系統需求](/microsoft-365/microsoft-365-and-office-resources)。</span><span class="sxs-lookup"><span data-stu-id="1281c-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="1281c-113">支援的 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="1281c-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="1281c-114">Azure Active DirectoryPowerShell:</span><span class="sxs-lookup"><span data-stu-id="1281c-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="1281c-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1281c-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="1281c-116">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1281c-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
