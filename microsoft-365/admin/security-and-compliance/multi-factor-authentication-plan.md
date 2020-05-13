---
title: 規劃 Microsoft 365 部署的多重要素驗證
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 深入瞭解 Microsoft 365 中的多重要素驗證，以及設定它時所需遵循的步驟。
ms.openlocfilehash: 6d28e9e7db825aa9030196396ad420028dc1c881
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213125"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a><span data-ttu-id="9db6f-103">規劃 Microsoft 365 部署的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="9db6f-103">Plan for multi-factor authentication for Microsoft 365 deployments</span></span>

<span data-ttu-id="9db6f-104">多重要素驗證 (MFA) 是一種需要使用多種驗證方法並為使用者登入和交易額外添加一層安全性的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="9db6f-104">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="9db6f-105">其運作方式是要求包含使用者帳戶密碼以外資訊的附加驗證步驟，例如：</span><span class="sxs-lookup"><span data-stu-id="9db6f-105">It works by requiring an addition verification step with information beyond the user account password, such as:</span></span>
  
- <span data-ttu-id="9db6f-106">傳送至您 smart phone 的隨機產生的驗證碼</span><span class="sxs-lookup"><span data-stu-id="9db6f-106">A randomly generated verification code sent to your smart phone</span></span>
    
- <span data-ttu-id="9db6f-107">電話</span><span class="sxs-lookup"><span data-stu-id="9db6f-107">A phone call</span></span>
    
- <span data-ttu-id="9db6f-108">智慧卡 (虛擬或實體)</span><span class="sxs-lookup"><span data-stu-id="9db6f-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="9db6f-109">生物特徵辨識裝置</span><span class="sxs-lookup"><span data-stu-id="9db6f-109">A biometric device</span></span> 
    
## <a name="mfa-in-microsoft-365"></a><span data-ttu-id="9db6f-110">Microsoft 365 中的 MFA</span><span class="sxs-lookup"><span data-stu-id="9db6f-110">MFA in Microsoft 365</span></span>

<span data-ttu-id="9db6f-111">Microsoft 365 使用 MFA 協助提供額外的安全性，並從 Microsoft 365 系統管理中心加以管理。</span><span class="sxs-lookup"><span data-stu-id="9db6f-111">Microsoft 365 uses MFA to help provide the extra security and is managed from the Microsoft 365 admin center.</span></span> <span data-ttu-id="9db6f-112">Microsoft 365 提供下列[Azure Multi-Factor 驗證](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)功能的子集做為訂閱的一部分：</span><span class="sxs-lookup"><span data-stu-id="9db6f-112">Microsoft 365 offers the following subset of [Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) capabilities as a part of the subscription:</span></span> 
  
- <span data-ttu-id="9db6f-113">為使用者啟用及強制執行 MFA 的能力</span><span class="sxs-lookup"><span data-stu-id="9db6f-113">The ability to enable and enforce MFA for end users</span></span>
    
- <span data-ttu-id="9db6f-114">使用行動裝置 App (線上和單次密碼 [OTP]) 做為次要驗證因素</span><span class="sxs-lookup"><span data-stu-id="9db6f-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="9db6f-115">使用電話做為次要驗證因素</span><span class="sxs-lookup"><span data-stu-id="9db6f-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="9db6f-116">使用短訊息服務（SMS）短消息作為第二個驗證因素</span><span class="sxs-lookup"><span data-stu-id="9db6f-116">The use of a Short Message Service (SMS) text message as a second authentication factor</span></span>
    
- <span data-ttu-id="9db6f-117">非瀏覽器用戶端的應用程式密碼（例如，Microsoft Lync 2013 通訊軟體）</span><span class="sxs-lookup"><span data-stu-id="9db6f-117">Application passwords for non-browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="9db6f-118">驗證電話期間的預設 Microsoft 問候語</span><span class="sxs-lookup"><span data-stu-id="9db6f-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="9db6f-119">如需新增功能的完整清單，請參閱[Azure Multi-Factor 驗證](https://go.microsoft.com/fwlink/?LinkId=506927)。</span><span class="sxs-lookup"><span data-stu-id="9db6f-119">For the full list of added features, see [Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/?LinkId=506927).</span></span> <span data-ttu-id="9db6f-120">您可以透過購買[Azure Multi-Factor 驗證授權](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing)，永遠取得完整功能。</span><span class="sxs-lookup"><span data-stu-id="9db6f-120">You can always get the full functionality by purchasing [Azure Multi-Factor Authentication licenses](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing).</span></span> 
  
<span data-ttu-id="9db6f-121">您會收到不同的功能子集，具體取決於您使用的是僅限雲端的身分識別，其中的使用者帳戶已存在於 Microsoft 365，或是使用單一登入和 Active Directory Federation Services （AD FS）的混合式設定。</span><span class="sxs-lookup"><span data-stu-id="9db6f-121">You get a different subset of capabilities depending on whether you use cloud-only identity where the user accounts on exist in Microsoft 365, or hybrid set up with single sign-on and Active Directory Federation Services (AD FS).</span></span> 
  
|<span data-ttu-id="9db6f-122">**您在何處管理 Microsoft 365？**</span><span class="sxs-lookup"><span data-stu-id="9db6f-122">**Where do you manage Microsoft 365?**</span></span>|<span data-ttu-id="9db6f-123">**MFA 次要因素選項**</span><span class="sxs-lookup"><span data-stu-id="9db6f-123">**MFA second factor options**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9db6f-124">僅限雲端</span><span class="sxs-lookup"><span data-stu-id="9db6f-124">Cloud only</span></span>  <br/> | <span data-ttu-id="9db6f-125">Azure Multi-Factor 驗證（文字或電話）</span><span class="sxs-lookup"><span data-stu-id="9db6f-125">Azure Multi-Factor Authentication (text or phone call)</span></span>  <br/> |
|<span data-ttu-id="9db6f-126">混合設定、受管理的內部部署</span><span class="sxs-lookup"><span data-stu-id="9db6f-126">Hybrid setup, managed on-premises</span></span>  <br/> | <span data-ttu-id="9db6f-127">如果您透過內部部署管理使用者身分識別，您有下列選擇：</span><span class="sxs-lookup"><span data-stu-id="9db6f-127">If you manage user identity on-premises, you have the following choices:</span></span>  <br/> <span data-ttu-id="9db6f-128">-實體或虛擬智慧卡（AD FS）</span><span class="sxs-lookup"><span data-stu-id="9db6f-128">-  Physical or virtual smart card (AD FS)</span></span>  <br/> <span data-ttu-id="9db6f-129">-Azure Multi-Factor 驗證（AD FS 的模組）</span><span class="sxs-lookup"><span data-stu-id="9db6f-129">- Azure Multi-Factor Authentication (module for AD FS)</span></span>  <br/>  <span data-ttu-id="9db6f-130">-Azure Multi-Factor 驗證</span><span class="sxs-lookup"><span data-stu-id="9db6f-130">- Azure Multi-Factor Authentication</span></span>  <br/> |
   
<span data-ttu-id="9db6f-131">Office 2013 裝置應用程式透過使用[Active Directory 驗證程式庫（ADAL）](https://go.microsoft.com/fwlink/p/?LinkId=526684)來支援 MFA。</span><span class="sxs-lookup"><span data-stu-id="9db6f-131">The Office 2013 device apps support MFA through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684).</span></span> <span data-ttu-id="9db6f-132">Azure Active Directory （Azure AD）主控使用者可以登入的網頁。</span><span class="sxs-lookup"><span data-stu-id="9db6f-132">Azure Active Directory (Azure AD) hosts a web page where users can sign in.</span></span> <span data-ttu-id="9db6f-133">身分識別提供者可以是 Azure AD 或 AD FS 等同盟身分識別提供者。</span><span class="sxs-lookup"><span data-stu-id="9db6f-133">The identity provider can be Azure AD or a federated identity provider like AD FS.</span></span> <span data-ttu-id="9db6f-134">同盟使用者的驗證按下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="9db6f-134">The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="9db6f-135">Azure AD 會將使用者重新導向至由組織之身分識別提供者所主控的登入網頁。</span><span class="sxs-lookup"><span data-stu-id="9db6f-135">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the organization.</span></span> <span data-ttu-id="9db6f-136">身分識別提供者取決於使用者登入名稱中指定的網域。</span><span class="sxs-lookup"><span data-stu-id="9db6f-136">The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="9db6f-137">使用者在他的裝置的登入網頁上登入。</span><span class="sxs-lookup"><span data-stu-id="9db6f-137">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="9db6f-138">使用者成功登入後，身分識別提供者會傳回權杖給 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="9db6f-138">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="9db6f-139">Azure AD 會將 JSON Web Token （JWT）傳回給 Office 裝置應用程式，而且裝置應用程式會透過使用與 Microsoft 365 的 JWT 驗證。</span><span class="sxs-lookup"><span data-stu-id="9db6f-139">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Microsoft 365.</span></span> 
    
  
## <a name="requirements-for-office-2013-client-apps"></a><span data-ttu-id="9db6f-140">Office 2013 用戶端應用程式的需求</span><span class="sxs-lookup"><span data-stu-id="9db6f-140">Requirements for Office 2013 client apps</span></span>

<span data-ttu-id="9db6f-141">若要啟用適用於 Office 2013 用戶端應用程式的 MFA，您必須安裝下列軟體 (以下所列的版本或更新版本)，根據您擁有的是[隨選即用型安裝](#click-to-run-based-installations)或 [MSI 型安裝](#msi-based-installations)而定。</span><span class="sxs-lookup"><span data-stu-id="9db6f-141">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="9db6f-142">若要判斷您的 Office 安裝是否為隨選即用或 MSI 型：</span><span class="sxs-lookup"><span data-stu-id="9db6f-142">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="9db6f-143">啟動 Outlook 2013。</span><span class="sxs-lookup"><span data-stu-id="9db6f-143">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="9db6f-144">**在 [檔案] 功能表上**，選擇 [ **Office 帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="9db6f-144">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="9db6f-145">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed.</span><span class="sxs-lookup"><span data-stu-id="9db6f-145">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed.</span></span> <span data-ttu-id="9db6f-146">For MSI-based installations, the **Update Options** item is not displayed.</span><span class="sxs-lookup"><span data-stu-id="9db6f-146">For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![如何判斷您的 Office 2013 安裝是隨選即用或以 MSI 為基礎的](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

<span data-ttu-id="9db6f-148">Sor 詳細資訊，請參閱[關於新式驗證 wiki 文章的常見問題](https://go.microsoft.com/fwlink/p/?LinkId=530064)。</span><span class="sxs-lookup"><span data-stu-id="9db6f-148">Sor more information, see the [FAQ about Modern Authentication wiki article](https://go.microsoft.com/fwlink/p/?LinkId=530064).</span></span>
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="9db6f-149">隨選即用型安裝</span><span class="sxs-lookup"><span data-stu-id="9db6f-149">Click-to-run based installations</span></span>

<span data-ttu-id="9db6f-150">若為隨選即用安裝，您必須安裝下列軟體，並列出下列檔案版本或更新的檔案版本。</span><span class="sxs-lookup"><span data-stu-id="9db6f-150">For Click-to-run based installations, you must have the following software installed, with the file version listed below or a later file version.</span></span> <span data-ttu-id="9db6f-151">如果您的檔案版本並非大於或等於列出的檔案版本，請使用下列步驟進行更新。</span><span class="sxs-lookup"><span data-stu-id="9db6f-151">If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="9db6f-152">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="9db6f-152">**File name**</span></span>|<span data-ttu-id="9db6f-153">**電腦上的安裝路徑**</span><span class="sxs-lookup"><span data-stu-id="9db6f-153">**Install path on your computer**</span></span>|<span data-ttu-id="9db6f-154">**檔案版本**</span><span class="sxs-lookup"><span data-stu-id="9db6f-154">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9db6f-155">MSO.Dll</span><span class="sxs-lookup"><span data-stu-id="9db6f-155">MSO.DLL</span></span>  <br/> |<span data-ttu-id="9db6f-156">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="9db6f-156">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="9db6f-157">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="9db6f-157">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="9db6f-158">Csi。Dll</span><span class="sxs-lookup"><span data-stu-id="9db6f-158">CSI.DLL</span></span>  <br/> |<span data-ttu-id="9db6f-159">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="9db6f-159">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="9db6f-160">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="9db6f-160">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="9db6f-161">Groove</span><span class="sxs-lookup"><span data-stu-id="9db6f-161">Groove.EXE</span></span>  <br/> |<span data-ttu-id="9db6f-162">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="9db6f-162">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="9db6f-163">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="9db6f-163">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="9db6f-164">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="9db6f-164">Outlook.exe</span></span>  <br/> |<span data-ttu-id="9db6f-165">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="9db6f-165">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="9db6f-166">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="9db6f-166">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="9db6f-167">ADAL.Dll</span><span class="sxs-lookup"><span data-stu-id="9db6f-167">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="9db6f-168">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="9db6f-168">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="9db6f-169">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="9db6f-169">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="9db6f-170">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="9db6f-170">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="9db6f-171">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="9db6f-171">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="9db6f-172">不盡相同</span><span class="sxs-lookup"><span data-stu-id="9db6f-172">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="9db6f-173">MSI 型安裝</span><span class="sxs-lookup"><span data-stu-id="9db6f-173">MSI-based installations</span></span>

<span data-ttu-id="9db6f-p108">若是 MSI 型安裝，您必須安裝下列軟體 (以下所列的檔案版本或更新的檔案版本)。如果您的檔案版本並非大於或等於列出的檔案版本，請使用「更新知識庫文章」一欄中的連結進行更新。</span><span class="sxs-lookup"><span data-stu-id="9db6f-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="9db6f-176">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="9db6f-176">**File name**</span></span>|<span data-ttu-id="9db6f-177">**電腦上的安裝路徑**</span><span class="sxs-lookup"><span data-stu-id="9db6f-177">**Install path on your computer**</span></span>|<span data-ttu-id="9db6f-178">**可於何處取得更新**</span><span class="sxs-lookup"><span data-stu-id="9db6f-178">**Where to get the update**</span></span>|<span data-ttu-id="9db6f-179">**版本**</span><span class="sxs-lookup"><span data-stu-id="9db6f-179">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9db6f-180">MSO.Dll</span><span class="sxs-lookup"><span data-stu-id="9db6f-180">MSO.DLL</span></span>  <br/> |<span data-ttu-id="9db6f-181">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="9db6f-181">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="9db6f-182">KB3085480</span><span class="sxs-lookup"><span data-stu-id="9db6f-182">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="9db6f-183">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="9db6f-183">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="9db6f-184">Csi。Dll</span><span class="sxs-lookup"><span data-stu-id="9db6f-184">CSI.DLL</span></span>  <br/> |<span data-ttu-id="9db6f-185">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="9db6f-185">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="9db6f-186">KB3085504</span><span class="sxs-lookup"><span data-stu-id="9db6f-186">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="9db6f-187">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="9db6f-187">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="9db6f-188">Groove</span><span class="sxs-lookup"><span data-stu-id="9db6f-188">Groove.exe</span></span>  <br/> |<span data-ttu-id="9db6f-189">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="9db6f-189">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="9db6f-190">KB3085509</span><span class="sxs-lookup"><span data-stu-id="9db6f-190">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="9db6f-191">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="9db6f-191">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="9db6f-192">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="9db6f-192">Outlook.exe</span></span>  <br/> |<span data-ttu-id="9db6f-193">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="9db6f-193">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="9db6f-194">KB3085495</span><span class="sxs-lookup"><span data-stu-id="9db6f-194">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="9db6f-195">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="9db6f-195">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="9db6f-196">ADAL.Dll</span><span class="sxs-lookup"><span data-stu-id="9db6f-196">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="9db6f-197">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="9db6f-197">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="9db6f-198">KB3055000</span><span class="sxs-lookup"><span data-stu-id="9db6f-198">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="9db6f-199">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="9db6f-199">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="9db6f-200">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="9db6f-200">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="9db6f-201">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="9db6f-201">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="9db6f-202">MS14-052</span><span class="sxs-lookup"><span data-stu-id="9db6f-202">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="9db6f-203">不適用</span><span class="sxs-lookup"><span data-stu-id="9db6f-203">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="9db6f-204">啟用 MFA</span><span class="sxs-lookup"><span data-stu-id="9db6f-204">Enable MFA</span></span>

<span data-ttu-id="9db6f-205">若要為您的訂閱啟用 MFA，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="9db6f-205">To enable MFA for your subscription, follow these steps:</span></span>
  
1. <span data-ttu-id="9db6f-206">視需要：</span><span class="sxs-lookup"><span data-stu-id="9db6f-206">If needed:</span></span> 

  - <span data-ttu-id="9db6f-207">[在 Windows 裝置上啟用 Office 2013 的新式驗證](enable-modern-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="9db6f-207">[Enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md).</span></span>
    
  - <span data-ttu-id="9db6f-208">使用協力廠商目錄服務設定 Azure Multi-Factor 驗證。</span><span class="sxs-lookup"><span data-stu-id="9db6f-208">Set up Azure Multi-Factor Authentication with third-party directory services.</span></span>
    
    <span data-ttu-id="9db6f-209">請參閱[使用 Azure Multi-Factor 驗證和協力廠商 VPN 解決方案的高級案例](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)，以取得此程式接受之特定身分識別提供者的資訊。</span><span class="sxs-lookup"><span data-stu-id="9db6f-209">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
2. <span data-ttu-id="9db6f-210">[設定 Microsoft 365 的 MFA](set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="9db6f-210">[Set up MFA for Microsoft 365](set-up-multi-factor-authentication.md).</span></span>
    
3. <span data-ttu-id="9db6f-211">告訴個別使用者如何以 MFA 登入。</span><span class="sxs-lookup"><span data-stu-id="9db6f-211">Tell individual users how to sign in by MFA.</span></span> <span data-ttu-id="9db6f-212">請參閱[使用 MFA 登入 Microsoft 365](https://support.office.com/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb)。</span><span class="sxs-lookup"><span data-stu-id="9db6f-212">See [Sign in to Microsoft 365 with MFA](https://support.office.com/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9db6f-213">如果您已對使用者啟用 Azure Multi-Factor 驗證，而且他們的任何執行 Office 2013 的裝置都未啟用新式驗證，則需要在這些裝置上使用應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="9db6f-213">If you have enabled your users for Azure Multi-Factor Authentication and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use app passwords on those devices.</span></span> <span data-ttu-id="9db6f-214">如需詳細資訊，請參閱[本文](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords)。</span><span class="sxs-lookup"><span data-stu-id="9db6f-214">See [this article](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) for more information.</span></span>
  
## <a name="faq"></a><span data-ttu-id="9db6f-215">常見問題集</span><span class="sxs-lookup"><span data-stu-id="9db6f-215">FAQ</span></span>

[<span data-ttu-id="9db6f-216">新式驗證 Wiki 文章的相關常見問題集</span><span class="sxs-lookup"><span data-stu-id="9db6f-216">FAQ about Modern Authentication wiki article</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a><span data-ttu-id="9db6f-217">已知問題</span><span class="sxs-lookup"><span data-stu-id="9db6f-217">Known issues</span></span>

[<span data-ttu-id="9db6f-218">Office 2013 和 Microsoft 365 Apps for enterprise 新式驗證：上架之前所需注意的事項</span><span class="sxs-lookup"><span data-stu-id="9db6f-218">Office 2013 and Microsoft 365 Apps for enterprise modern authentication: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="9db6f-219">**Azure 多重要素驗證疑難排解：**</span><span class="sxs-lookup"><span data-stu-id="9db6f-219">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="9db6f-220">請參閱[Azure Multi-Factor 驗證疑難排解](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)。</span><span class="sxs-lookup"><span data-stu-id="9db6f-220">See [Troubleshoot Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="9db6f-221">如何針對使用 AD FS 時的 Office 2013 新式驗證之登入問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="9db6f-221">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="9db6f-222">**當無法使用替代識別碼時：**</span><span class="sxs-lookup"><span data-stu-id="9db6f-222">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="9db6f-223">如何使用 PowerShell 修正 UPN 重複的問題</span><span class="sxs-lookup"><span data-stu-id="9db6f-223">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
<span data-ttu-id="9db6f-224">[用來修正使用者主體名稱重複問題的指令碼](https://go.microsoft.com/fwlink/p/?LinkId=396725) (英文)</span><span class="sxs-lookup"><span data-stu-id="9db6f-224">[Script to fix duplicate user principal names](https://go.microsoft.com/fwlink/p/?LinkId=396725)</span></span>
  
 <span data-ttu-id="9db6f-225">**用戶端存取篩選：**</span><span class="sxs-lookup"><span data-stu-id="9db6f-225">**Client access filtering:**</span></span>
  
[<span data-ttu-id="9db6f-226">適用于企業新式驗證及用戶端存取篩選原則的 Office 2013 和 Microsoft 365 應用程式：上架須知</span><span class="sxs-lookup"><span data-stu-id="9db6f-226">Office 2013 and Microsoft 365 Apps for enterprise modern authentication and client access filtering policies: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="9db6f-227">**哪些應用程式支援 MFA？**</span><span class="sxs-lookup"><span data-stu-id="9db6f-227">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="9db6f-228">**Windows**</span><span class="sxs-lookup"><span data-stu-id="9db6f-228">**Windows**</span></span>|<span data-ttu-id="9db6f-229">**Mac**</span><span class="sxs-lookup"><span data-stu-id="9db6f-229">**Mac**</span></span>|<span data-ttu-id="9db6f-230">**iOS**</span><span class="sxs-lookup"><span data-stu-id="9db6f-230">**iOS**</span></span>|<span data-ttu-id="9db6f-231">**Android 手機**</span><span class="sxs-lookup"><span data-stu-id="9db6f-231">**Android phone**</span></span>|<span data-ttu-id="9db6f-232">**Android 平板電腦**</span><span class="sxs-lookup"><span data-stu-id="9db6f-232">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9db6f-233">此版本支援 Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013 及商務用 Skype 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="9db6f-233">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="9db6f-234">此版本支援 Mac 版 Word 2016、Mac 版 Excel 2016 及 Mac 版 PowerPoint 2016 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="9db6f-234">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="9db6f-235">此版本支援 iPad 版 Word、iPad 版 Excel 及 iPad 版 PowerPoint 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="9db6f-235">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="9db6f-236">此版本支援 Android 版 Word、Android 版 Excel 及 Android 版 PowerPoint 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="9db6f-236">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="9db6f-237">此版本支援 Android 版 Word、Android 版 Excel 及 Android 版 PowerPoint 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="9db6f-237">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="9db6f-238">此版本支援 Outlook 2013 和 Outlook 2016 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="9db6f-238">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="9db6f-239">此版本支援 Mac 版 Outlook 2016 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="9db6f-239">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="9db6f-240">此版本支援 iPad 版 Outlook 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="9db6f-240">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

