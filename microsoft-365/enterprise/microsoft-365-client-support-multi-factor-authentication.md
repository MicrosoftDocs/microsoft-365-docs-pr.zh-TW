---
title: Microsoft 365 用戶端應用程式支援：多重要素驗證
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 在本文中，瞭解哪些平臺、用戶端和 PowerShell 模組支援 Microsoft 365 的多重要素驗證。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80ee370526d17d472cd048cd4d89b862e158b631
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927555"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="4bf18-103">Microsoft 365 用戶端應用程式支援：多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="4bf18-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="4bf18-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="4bf18-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4bf18-105">若要為登入提供額外的安全性層級，用戶端可以設定為使用多重要素驗證 (MFA) ，它會同時使用使用者密碼及另一個使用者驗證方法，其依據如下：</span><span class="sxs-lookup"><span data-stu-id="4bf18-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and another user verification method based on:</span></span>

- <span data-ttu-id="4bf18-106">未輕易重複的內容，例如智慧型電話。</span><span class="sxs-lookup"><span data-stu-id="4bf18-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="4bf18-107">使用者有唯一和 biologically 的專案，例如其指紋、字型或其他生物統計學屬性</span><span class="sxs-lookup"><span data-stu-id="4bf18-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="4bf18-108">深入瞭解 [多重要素驗證](/azure/active-directory/authentication/multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="4bf18-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="4bf18-109">支援的用戶端 & 平臺</span><span class="sxs-lookup"><span data-stu-id="4bf18-109">Supported clients & platforms</span></span>

<span data-ttu-id="4bf18-110">下列用戶端和平臺的最新版本支援多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="4bf18-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="4bf18-111">如需 Microsoft 365 平臺支援的詳細資訊，請參閱 [microsoft 365 的系統需求](/microsoft-365/microsoft-365-and-office-resources)。</span><span class="sxs-lookup"><span data-stu-id="4bf18-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="4bf18-112">支援的 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="4bf18-112">Supported PowerShell modules</span></span>

- [<span data-ttu-id="4bf18-113">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bf18-113">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="4bf18-114">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bf18-114">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="4bf18-115">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bf18-115">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)