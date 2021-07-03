---
title: Microsoft 365用戶端應用程式支援：憑證型驗證
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
description: 在本文中，將尋找有關憑證型驗證之用戶端應用程式支援 Microsoft 365 的詳細資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bef1a684ba1ebe2eaba90677cd726cc190e342db
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286570"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a><span data-ttu-id="f2570-103">Microsoft 365用戶端應用程式支援：憑證型驗證</span><span class="sxs-lookup"><span data-stu-id="f2570-103">Microsoft 365 Client App Support: Certificate-based Authentication</span></span>

<span data-ttu-id="f2570-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="f2570-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f2570-105">新式驗證是驗證和授權方法組合的傘條款。</span><span class="sxs-lookup"><span data-stu-id="f2570-105">Modern authentication is an umbrella term for a combination of authentication and authorization methods.</span></span> <span data-ttu-id="f2570-106">這些方法包括：</span><span class="sxs-lookup"><span data-stu-id="f2570-106">These methods include:</span></span>

- <span data-ttu-id="f2570-107">**驗證方法**：多重要素驗證;以用戶端憑證為基礎的驗證。</span><span class="sxs-lookup"><span data-stu-id="f2570-107">**Authentication methods**: Multi-factor Authentication; Client Certificate-based authentication.</span></span>
- <span data-ttu-id="f2570-108">**授權方法**： Microsoft 的開啟授權 (OAuth) 的實施方式。</span><span class="sxs-lookup"><span data-stu-id="f2570-108">**Authorization methods**: Microsoft's implementation of Open Authorization (OAuth).</span></span>

<span data-ttu-id="f2570-109">使用驗證程式庫（如 Active Directory 驗證程式庫 (ADAL) 或 Microsoft 驗證程式庫 (MSAL) ）會啟用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="f2570-109">Modern authentication is enabled by using an authentication library, like Active Directory Authentication Library (ADAL) or Microsoft Authentication Library (MSAL).</span></span> <span data-ttu-id="f2570-110">新式驗證是指用戶端用來驗證和授權 Microsoft 365 資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="f2570-110">Modern authentication is what clients use to authenticate and authorize access to Microsoft 365 resources.</span></span> <span data-ttu-id="f2570-111">新式驗證使用 OAuth，並提供一種安全機制，讓用戶端可以存取 Microsoft 365 服務，而不需要存取使用者認證。</span><span class="sxs-lookup"><span data-stu-id="f2570-111">Modern authentication uses OAuth and provides a secure mechanism for clients to access Microsoft 365 services, without requiring access to user credentials.</span></span> <span data-ttu-id="f2570-112">在登入時，使用者會直接驗證 Azure Active Directory，並接收 return 中的存取/重新整理權杖對。</span><span class="sxs-lookup"><span data-stu-id="f2570-112">At sign-in, the user authenticates directly with Azure Active Directory and receives an access/refresh token pair in return.</span></span> <span data-ttu-id="f2570-113">存取權杖會授與用戶端對 Microsoft 365 承租人中適當資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="f2570-113">The access token grants the client access to the appropriate resources in the Microsoft 365 tenant.</span></span> <span data-ttu-id="f2570-114">當目前的存取權杖到期時，會使用重新整理權杖來取得新的 access 或重新整理權杖。</span><span class="sxs-lookup"><span data-stu-id="f2570-114">A refresh token is used to obtain a new access or refresh token pair when the current access token expires.</span></span>

<span data-ttu-id="f2570-115">新式驗證支援不同的驗證機制，類似憑證型驗證。</span><span class="sxs-lookup"><span data-stu-id="f2570-115">Modern authentication supports different authentication mechanisms, like certificate-based authentication.</span></span> <span data-ttu-id="f2570-116">Windows、Android 或 iOS 裝置上的用戶端都可以使用憑證型驗證 (CBA) ，以在裝置上使用用戶端憑證進行驗證，以進行 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="f2570-116">Clients on Windows, Android, or iOS devices can use certificate-based authentication (CBA) to authenticate to Azure Active Directory using a client certificate on the device.</span></span> <span data-ttu-id="f2570-117">憑證是用來從 Azure Active Directory 取得存取/重新整理權杖對，而不是一般的使用者名稱/密碼。</span><span class="sxs-lookup"><span data-stu-id="f2570-117">Instead of a typical username/password, the certificate is used to obtain an access/refresh token pair from Azure Active Directory.</span></span>

<span data-ttu-id="f2570-118">深入瞭解 [憑證型驗證](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)。</span><span class="sxs-lookup"><span data-stu-id="f2570-118">Learn more about [certificate-based authentication](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="f2570-119">支援的用戶端 & 平臺</span><span class="sxs-lookup"><span data-stu-id="f2570-119">Supported clients & platforms</span></span>

<span data-ttu-id="f2570-120">在用戶端 (中登入 Azure Active Directory 帳戶時，下列用戶端和平臺的最新版本都支援憑證型驗證，例如，將帳戶新增至應用程式) 時。</span><span class="sxs-lookup"><span data-stu-id="f2570-120">The latest versions of the following clients and platforms support certificate-based authentication when signing into Azure Active Directory accounts within the client (for example, when adding an account to the app).</span></span> <span data-ttu-id="f2570-121">如需 Microsoft 365 中平臺支援的詳細資訊，請參閱[Microsoft 365 的系統需求](/microsoft-365/microsoft-365-and-office-resources)。</span><span class="sxs-lookup"><span data-stu-id="f2570-121">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

> [!NOTE]
> <span data-ttu-id="f2570-122">在帳戶新增流程中，iOS 和 Android 的 Edge 支援以憑證為基礎的驗證。</span><span class="sxs-lookup"><span data-stu-id="f2570-122">Edge for iOS and Android supports certificate-based authentication during account add flows.</span></span> <span data-ttu-id="f2570-123">在針對網站（通常是內部網路網站）進行驗證時，iOS 和 Android 的 Edge 不支援以憑證為基礎的驗證。</span><span class="sxs-lookup"><span data-stu-id="f2570-123">Edge for iOS and Android does not support certificate-based authentication when performing authentication against web sites, which are typically intranet sites.</span></span> <br><br>  <span data-ttu-id="f2570-124">在此案例中，使用者會流覽至網站 (通常是內部網路) （網站要求使用者透過憑證進行驗證）。</span><span class="sxs-lookup"><span data-stu-id="f2570-124">In this scenario, a user navigates to a web site (usually on the intranet) where the web site requires the user to authenticate via a certificate.</span></span> <span data-ttu-id="f2570-125">這根本不涉及新式驗證，也不會利用 Microsoft 驗證程式庫。</span><span class="sxs-lookup"><span data-stu-id="f2570-125">This does not involve modern authentication at all and does not leverage a Microsoft authentication library.</span></span> <span data-ttu-id="f2570-126">這是因為 iOS 所產生的限制如下： iOS 阻止協力廠商應用程式存取儲存憑證的系統金鑰鏈 (只有 Apple 應用程式和 [Safari web 視圖控制器](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) 可以存取系統金鑰鏈) 。</span><span class="sxs-lookup"><span data-stu-id="f2570-126">This is due to a limitation with iOS: iOS prevents third-party apps from accessing the system keychain where the certificates are stored (only Apple apps and the [Safari webview controller](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) can access the system keychain).</span></span> <br><br> <span data-ttu-id="f2570-127">隨著 Edge 依賴用於呈現網站的 [WebKit](https://developer.apple.com/documentation/webkit) 架構，edge 無法存取系統金鑰鏈，並以憑證選擇顯示使用者。</span><span class="sxs-lookup"><span data-stu-id="f2570-127">As Edge relies on the [WebKit](https://developer.apple.com/documentation/webkit) framework for rendering web sites, Edge is unable to access the system keychain and present the user with a certificate choice.</span></span> <span data-ttu-id="f2570-128">不幸的是，由於 Apple 的架構而設計。</span><span class="sxs-lookup"><span data-stu-id="f2570-128">This, unfortunately, is by design due to Apple's architecture.</span></span>

## <a name="supported-powershell-modules"></a><span data-ttu-id="f2570-129">支援的 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="f2570-129">Supported PowerShell modules</span></span>

- [<span data-ttu-id="f2570-130">Azure Active DirectoryPowerShell:</span><span class="sxs-lookup"><span data-stu-id="f2570-130">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview)
- [<span data-ttu-id="f2570-131">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2570-131">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="f2570-132">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2570-132">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
