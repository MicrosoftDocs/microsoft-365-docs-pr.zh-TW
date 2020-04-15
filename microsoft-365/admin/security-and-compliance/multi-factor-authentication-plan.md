---
title: Office 365 部署多重要素驗證方案
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
description: 深入瞭解 Office 365 中的多重要素驗證，以及設定所需遵循的步驟。
ms.openlocfilehash: 715baeb0355ab203e890f2c87cf0751eff69e7f8
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503992"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a><span data-ttu-id="ad577-103">Office 365 部署多重要素驗證方案</span><span class="sxs-lookup"><span data-stu-id="ad577-103">Plan for multi-factor authentication for Office 365 Deployments</span></span>

<span data-ttu-id="ad577-104">多重要素驗證 (MFA) 是一種需要使用多種驗證方法並為使用者登入和交易額外添加一層安全性的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="ad577-104">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="ad577-105">其運作方式是要求包含使用者帳戶密碼以外資訊的附加驗證步驟，例如：</span><span class="sxs-lookup"><span data-stu-id="ad577-105">It works by requiring an addition verification step with information beyond the user account password, such as:</span></span>
  
- <span data-ttu-id="ad577-106">隨機產生的密碼</span><span class="sxs-lookup"><span data-stu-id="ad577-106">A randomly generated pass code</span></span>
    
- <span data-ttu-id="ad577-107">電話</span><span class="sxs-lookup"><span data-stu-id="ad577-107">A phone call</span></span>
    
- <span data-ttu-id="ad577-108">智慧卡 (虛擬或實體)</span><span class="sxs-lookup"><span data-stu-id="ad577-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="ad577-109">生物特徵辨識裝置</span><span class="sxs-lookup"><span data-stu-id="ad577-109">A biometric device</span></span> 
    
## <a name="mfa-in-office-365"></a><span data-ttu-id="ad577-110">Office 365 中的 MFA</span><span class="sxs-lookup"><span data-stu-id="ad577-110">MFA in Office 365</span></span>

<span data-ttu-id="ad577-111">Office 365 使用 MFA 進行額外的登入安全性，而且可針對來自 Microsoft 365 系統管理中心的各個使用者帳戶進行管理。</span><span class="sxs-lookup"><span data-stu-id="ad577-111">Office 365 uses MFA for extra sign-in security and can be managed for each individual user account from the Microsoft 365 admin center.</span></span> <span data-ttu-id="ad577-112">Office 365 提供下列 Azure Multi-Factor 驗證功能的子集做為您訂閱的一部分：</span><span class="sxs-lookup"><span data-stu-id="ad577-112">Office 365 offers the following subset of Azure Multi-Factor Authentication capabilities as a part of your subscription:</span></span> 
  
- <span data-ttu-id="ad577-113">為使用者啟用及強制執行 MFA 的能力</span><span class="sxs-lookup"><span data-stu-id="ad577-113">The ability to enable and enforce MFA for end users</span></span>
    
- <span data-ttu-id="ad577-114">使用行動裝置 App (線上和單次密碼 [OTP]) 做為次要驗證因素</span><span class="sxs-lookup"><span data-stu-id="ad577-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="ad577-115">使用電話做為次要驗證因素</span><span class="sxs-lookup"><span data-stu-id="ad577-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="ad577-116">使用簡訊服務 (SMS) 訊息做為次要驗證因素</span><span class="sxs-lookup"><span data-stu-id="ad577-116">The use of a Short Message Service (SMS) message as a second authentication factor</span></span>
    
- <span data-ttu-id="ad577-117">非瀏覽器用戶端的應用程式密碼（例如，Microsoft Lync 2013 通訊軟體）</span><span class="sxs-lookup"><span data-stu-id="ad577-117">Application passwords for non-browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="ad577-118">驗證電話期間的預設 Microsoft 問候語</span><span class="sxs-lookup"><span data-stu-id="ad577-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="ad577-p103">如需新增功能的完整清單，請參閱 [Azure 多重要素驗證版本比較](https://go.microsoft.com/fwlink/?LinkId=506927)。您可以購買 Azure 多重要素驗證服務，隨時獲得完整功能。</span><span class="sxs-lookup"><span data-stu-id="ad577-p103">For the full list of added features, see [the comparison of Azure Multi-Factor Authentication version](https://go.microsoft.com/fwlink/?LinkId=506927). You can always get the full functionality by purchasing the Azure Multi-Factor Authentication service.</span></span> 
  
<span data-ttu-id="ad577-121">您可以根據您是否有雲端或混合式身分識別（適用于 Active Directory Federation Services （AD FS）的 Office 365 或同盟驗證，取得不同的功能子集。</span><span class="sxs-lookup"><span data-stu-id="ad577-121">You get a different subset of capabilities depending on whether you have a cloud-only or hybrid identity for Office 365 or federated authentication with Active Directory Federation Services (AD FS).</span></span> 
  
<span data-ttu-id="ad577-122">|**您在何處管理 Office 365 租使用者？**| **MFA 第二因素選項**|</span><span class="sxs-lookup"><span data-stu-id="ad577-122">|**Where do you manage your Office 365 tenant?**|**MFA second factor options**|</span></span>

<span data-ttu-id="ad577-123">|:-----|:-----| |僅雲端</span><span class="sxs-lookup"><span data-stu-id="ad577-123">|:-----|:-----| |Cloud only</span></span>  <br/> <span data-ttu-id="ad577-124">|Azure Multi-Factor 驗證（文字或電話）</span><span class="sxs-lookup"><span data-stu-id="ad577-124">|Azure Multi-Factor Authentication (text or phone call)</span></span>  <br/> <span data-ttu-id="ad577-125">| |混合式設定，受管理的內部部署</span><span class="sxs-lookup"><span data-stu-id="ad577-125">| |Hybrid setup, managed on-premises</span></span>  <br/> <span data-ttu-id="ad577-126">|如果您管理內部部署使用者身分識別，您可以選擇下列選項：</span><span class="sxs-lookup"><span data-stu-id="ad577-126">| If you manage user identity on-premises, you have the following choices:</span></span>  <br/>  <span data-ttu-id="ad577-127">實體或虛擬智慧卡（使用 AD FS 時）</span><span class="sxs-lookup"><span data-stu-id="ad577-127">Physical or virtual smart card (when using AD FS)</span></span>  <br/> <span data-ttu-id="ad577-128">[Azure Multi-Factor 驗證](https://go.microsoft.com/fwlink/p/?LinkId=526677)（AD FS 的模組）</span><span class="sxs-lookup"><span data-stu-id="ad577-128">[Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=526677) (module for AD FS)</span></span>  <br/>  <span data-ttu-id="ad577-129">Azure Active Directory （Azure AD） Multi-Factor 驗證</span><span class="sxs-lookup"><span data-stu-id="ad577-129">Azure Active Directory (Azure AD) Multi-Factor Authentication</span></span>  <br/> |
   
  
<span data-ttu-id="ad577-130">下圖顯示更新的 Office 2013 裝置 App (Windows 版) 如何讓使用者能夠使用 MFA 登入。</span><span class="sxs-lookup"><span data-stu-id="ad577-130">The following figure shows how the updated Office 2013 device apps (on Windows) enable users to sign in with MFA.</span></span> 

![Office 2013 裝置應用程式的現代化驗證。](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)

<span data-ttu-id="ad577-132">Office 2013 裝置應用程式透過使用[Active Directory 驗證程式庫（ADAL）](https://go.microsoft.com/fwlink/p/?LinkId=526684)來支援多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="ad577-132">The Office 2013 device apps support multi-factor authentication through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684).</span></span> <span data-ttu-id="ad577-133">Azure AD 託管使用者可以登入的網頁。</span><span class="sxs-lookup"><span data-stu-id="ad577-133">Azure AD hosts a webpage where users can sign in.</span></span> <span data-ttu-id="ad577-134">身分識別提供者可以是 Azure AD 或 AD FS 等同盟身分識別提供者。</span><span class="sxs-lookup"><span data-stu-id="ad577-134">The identity provider can be Azure AD or a federated identity provider like AD FS.</span></span> <span data-ttu-id="ad577-135">同盟使用者的驗證按下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="ad577-135">The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="ad577-p105">Azure AD 將使用者重新導向到由 Office 365 租用戶的記錄之身分識別提供者託管的登入網頁。身分識別提供者取決於使用者登入名稱中指定的網域。</span><span class="sxs-lookup"><span data-stu-id="ad577-p105">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the Office 365 tenant. The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="ad577-138">使用者在他的裝置的登入網頁上登入。</span><span class="sxs-lookup"><span data-stu-id="ad577-138">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="ad577-139">使用者成功登入後，身分識別提供者會傳回權杖給 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="ad577-139">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="ad577-140">Azure AD 會傳回 JSON Web 權杖 (JWT) 給 Office 裝置 App，而裝置 App 會搭配 Office 365 使用 JWT 獲得授權。</span><span class="sxs-lookup"><span data-stu-id="ad577-140">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Office 365.</span></span> 
    
  
## <a name="requirements-for-office-2013-client-apps"></a><span data-ttu-id="ad577-141">Office 2013 用戶端應用程式的需求</span><span class="sxs-lookup"><span data-stu-id="ad577-141">Requirements for Office 2013 client apps</span></span>

<span data-ttu-id="ad577-142">若要啟用適用於 Office 2013 用戶端應用程式的 MFA，您必須安裝下列軟體 (以下所列的版本或更新版本)，根據您擁有的是[隨選即用型安裝](#click-to-run-based-installations)或 [MSI 型安裝](#msi-based-installations)而定。</span><span class="sxs-lookup"><span data-stu-id="ad577-142">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="ad577-143">若要判斷您的 Office 安裝是否為隨選即用或 MSI 型：</span><span class="sxs-lookup"><span data-stu-id="ad577-143">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="ad577-144">啟動 Outlook 2013。</span><span class="sxs-lookup"><span data-stu-id="ad577-144">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="ad577-145">**在 [檔案] 功能表上**，選擇 [ **Office 帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="ad577-145">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="ad577-146">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed.</span><span class="sxs-lookup"><span data-stu-id="ad577-146">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed.</span></span> <span data-ttu-id="ad577-147">For MSI-based installations, the **Update Options** item is not displayed.</span><span class="sxs-lookup"><span data-stu-id="ad577-147">For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![如何判斷您的 Office 2013 安裝是隨選即用或以 MSI 為基礎的](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

<span data-ttu-id="ad577-149">Sor 詳細資訊，請參閱[關於新式驗證 wiki 文章的常見問題](https://go.microsoft.com/fwlink/p/?LinkId=530064)。</span><span class="sxs-lookup"><span data-stu-id="ad577-149">Sor more information, see the [FAQ about Modern Authentication wiki article](https://go.microsoft.com/fwlink/p/?LinkId=530064).</span></span>
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="ad577-150">隨選即用型安裝</span><span class="sxs-lookup"><span data-stu-id="ad577-150">Click-to-run based installations</span></span>

<span data-ttu-id="ad577-151">若為隨選即用安裝，您必須安裝下列軟體，並列出下列檔案版本或更新的檔案版本。</span><span class="sxs-lookup"><span data-stu-id="ad577-151">For Click-to-run based installations, you must have the following software installed, with the file version listed below or a later file version.</span></span> <span data-ttu-id="ad577-152">如果您的檔案版本並非大於或等於列出的檔案版本，請使用下列步驟進行更新。</span><span class="sxs-lookup"><span data-stu-id="ad577-152">If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="ad577-153">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="ad577-153">**File name**</span></span>|<span data-ttu-id="ad577-154">**電腦上的安裝路徑**</span><span class="sxs-lookup"><span data-stu-id="ad577-154">**Install path on your computer**</span></span>|<span data-ttu-id="ad577-155">**檔案版本**</span><span class="sxs-lookup"><span data-stu-id="ad577-155">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ad577-156">MSO.Dll</span><span class="sxs-lookup"><span data-stu-id="ad577-156">MSO.DLL</span></span>  <br/> |<span data-ttu-id="ad577-157">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="ad577-157">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="ad577-158">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="ad577-158">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="ad577-159">Csi。Dll</span><span class="sxs-lookup"><span data-stu-id="ad577-159">CSI.DLL</span></span>  <br/> |<span data-ttu-id="ad577-160">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="ad577-160">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="ad577-161">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="ad577-161">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="ad577-162">Groove</span><span class="sxs-lookup"><span data-stu-id="ad577-162">Groove.EXE</span></span>  <br/> |<span data-ttu-id="ad577-163">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="ad577-163">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="ad577-164">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="ad577-164">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="ad577-165">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="ad577-165">Outlook.exe</span></span>  <br/> |<span data-ttu-id="ad577-166">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="ad577-166">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="ad577-167">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="ad577-167">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="ad577-168">ADAL.Dll</span><span class="sxs-lookup"><span data-stu-id="ad577-168">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="ad577-169">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="ad577-169">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="ad577-170">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="ad577-170">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="ad577-171">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="ad577-171">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="ad577-172">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="ad577-172">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="ad577-173">不盡相同</span><span class="sxs-lookup"><span data-stu-id="ad577-173">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="ad577-174">MSI 型安裝</span><span class="sxs-lookup"><span data-stu-id="ad577-174">MSI-based installations</span></span>

<span data-ttu-id="ad577-p108">若是 MSI 型安裝，您必須安裝下列軟體 (以下所列的檔案版本或更新的檔案版本)。如果您的檔案版本並非大於或等於列出的檔案版本，請使用「更新知識庫文章」一欄中的連結進行更新。</span><span class="sxs-lookup"><span data-stu-id="ad577-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="ad577-177">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="ad577-177">**File name**</span></span>|<span data-ttu-id="ad577-178">**電腦上的安裝路徑**</span><span class="sxs-lookup"><span data-stu-id="ad577-178">**Install path on your computer**</span></span>|<span data-ttu-id="ad577-179">**可於何處取得更新**</span><span class="sxs-lookup"><span data-stu-id="ad577-179">**Where to get the update**</span></span>|<span data-ttu-id="ad577-180">**版本**</span><span class="sxs-lookup"><span data-stu-id="ad577-180">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad577-181">MSO.Dll</span><span class="sxs-lookup"><span data-stu-id="ad577-181">MSO.DLL</span></span>  <br/> |<span data-ttu-id="ad577-182">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="ad577-182">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="ad577-183">KB3085480</span><span class="sxs-lookup"><span data-stu-id="ad577-183">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="ad577-184">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="ad577-184">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="ad577-185">Csi。Dll</span><span class="sxs-lookup"><span data-stu-id="ad577-185">CSI.DLL</span></span>  <br/> |<span data-ttu-id="ad577-186">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="ad577-186">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="ad577-187">KB3085504</span><span class="sxs-lookup"><span data-stu-id="ad577-187">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="ad577-188">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="ad577-188">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="ad577-189">Groove</span><span class="sxs-lookup"><span data-stu-id="ad577-189">Groove.exe</span></span>  <br/> |<span data-ttu-id="ad577-190">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="ad577-190">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="ad577-191">KB3085509</span><span class="sxs-lookup"><span data-stu-id="ad577-191">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="ad577-192">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="ad577-192">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="ad577-193">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="ad577-193">Outlook.exe</span></span>  <br/> |<span data-ttu-id="ad577-194">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="ad577-194">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="ad577-195">KB3085495</span><span class="sxs-lookup"><span data-stu-id="ad577-195">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="ad577-196">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="ad577-196">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="ad577-197">ADAL.Dll</span><span class="sxs-lookup"><span data-stu-id="ad577-197">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="ad577-198">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="ad577-198">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="ad577-199">KB3055000</span><span class="sxs-lookup"><span data-stu-id="ad577-199">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="ad577-200">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="ad577-200">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="ad577-201">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="ad577-201">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="ad577-202">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="ad577-202">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="ad577-203">MS14-052</span><span class="sxs-lookup"><span data-stu-id="ad577-203">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="ad577-204">不適用</span><span class="sxs-lookup"><span data-stu-id="ad577-204">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="ad577-205">啟用 MFA</span><span class="sxs-lookup"><span data-stu-id="ad577-205">Enable MFA</span></span>

<span data-ttu-id="ad577-206">若要為您的 Office 365 訂閱啟用 MFA，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ad577-206">To enable MFA for your Office 365 subscription, follow these steps:</span></span>
  
1. <span data-ttu-id="ad577-207">如有需要，[在 Windows 裝置上啟用 Office 2013 的新式驗證](enable-modern-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="ad577-207">If needed, [enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md).</span></span>
    
2. <span data-ttu-id="ad577-208">針對同盟驗證，使用協力廠商目錄服務設定 Azure Multi-Factor 驗證。</span><span class="sxs-lookup"><span data-stu-id="ad577-208">For federated authentication, set up Azure Multi-Factor Authentication with your third-party directory service.</span></span>
    
    <span data-ttu-id="ad577-209">請參閱[使用 Azure Multi-Factor 驗證和協力廠商 VPN 解決方案的高級案例](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)，以取得此程式接受之特定身分識別提供者的資訊。</span><span class="sxs-lookup"><span data-stu-id="ad577-209">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
3. <span data-ttu-id="ad577-210">[設定 Office 365 的多重要素驗證](set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="ad577-210">[Set up multi-factor authentication for Office 365](set-up-multi-factor-authentication.md).</span></span>
    
4. <span data-ttu-id="ad577-211">請告訴您的使用者如何[設定其 Office 365 使用者帳戶的 MFA](https://support.office.com/article/set-up-2-step-verification-for-office-365-ace1d096-61e5-449b-a875-58eb3d74de14)。</span><span class="sxs-lookup"><span data-stu-id="ad577-211">Tell your users how to [set up MFA for their Office 365 user account](https://support.office.com/article/set-up-2-step-verification-for-office-365-ace1d096-61e5-449b-a875-58eb3d74de14).</span></span> <span data-ttu-id="ad577-212">在使用者設定其次要驗證方法之後，他們的未來登入將需要 MFA。</span><span class="sxs-lookup"><span data-stu-id="ad577-212">After they set up their secondary authentication method, their future sign-ins will require MFA.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="ad577-213">如果您已對使用者啟用 Azure Multi-Factor 驗證，而且他們的任何執行 Office 2013 的裝置都未啟用新式驗證，則需要使用應用程式密碼。</span><span class="sxs-lookup"><span data-stu-id="ad577-213">If you have enabled your users for Azure Multi-Factor Authentication and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use App Passwords.</span></span> <span data-ttu-id="ad577-214">如需應用程式密碼的詳細資訊，以及應使用的時間/位置/方式，請參閱下列網址： [Azure Multi_Factor 驗證的應用程式密碼](https://go.microsoft.com/fwlink/p/?LinkId=528178)。</span><span class="sxs-lookup"><span data-stu-id="ad577-214">More information on App Passwords and when/where/how they should be used can be found here: [App Passwords with Azure Multi_Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span> 
  
## <a name="known-issues"></a><span data-ttu-id="ad577-215">已知問題</span><span class="sxs-lookup"><span data-stu-id="ad577-215">Known issues</span></span>
  
[<span data-ttu-id="ad577-216">Office 2013 和 Office 365 ProPlus 新式驗證：上架之前所知道的專案</span><span class="sxs-lookup"><span data-stu-id="ad577-216">Office 2013 and Office 365 ProPlus modern authentication: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="ad577-217">**Azure 多重要素驗證疑難排解：**</span><span class="sxs-lookup"><span data-stu-id="ad577-217">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="ad577-218">請參閱[Azure Multi-Factor 驗證疑難排解](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)。</span><span class="sxs-lookup"><span data-stu-id="ad577-218">See [Troubleshoot Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="ad577-219">如何針對使用 AD FS 時的 Office 2013 新式驗證之登入問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="ad577-219">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="ad577-220">**當無法使用替代識別碼時：**</span><span class="sxs-lookup"><span data-stu-id="ad577-220">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="ad577-221">如何使用 PowerShell 修正 UPN 重複的問題</span><span class="sxs-lookup"><span data-stu-id="ad577-221">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
<span data-ttu-id="ad577-222">[用來修正使用者主體名稱重複問題的指令碼](https://go.microsoft.com/fwlink/p/?LinkId=396725) (英文)</span><span class="sxs-lookup"><span data-stu-id="ad577-222">[Script to fix duplicate user principal names](https://go.microsoft.com/fwlink/p/?LinkId=396725)</span></span>
  
 <span data-ttu-id="ad577-223">**用戶端存取篩選：**</span><span class="sxs-lookup"><span data-stu-id="ad577-223">**Client access filtering:**</span></span>
  
[<span data-ttu-id="ad577-224">Office 2013 和 Office 365 專業增強版新式驗證和用戶端存取篩選原則：上線前的相關須知</span><span class="sxs-lookup"><span data-stu-id="ad577-224">Office 2013 and Office 365 ProPlus modern authentication and client access filtering policies : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="ad577-225">**哪些應用程式支援 MFA？**</span><span class="sxs-lookup"><span data-stu-id="ad577-225">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="ad577-226">**Windows**</span><span class="sxs-lookup"><span data-stu-id="ad577-226">**Windows**</span></span>|<span data-ttu-id="ad577-227">**Mac**</span><span class="sxs-lookup"><span data-stu-id="ad577-227">**Mac**</span></span>|<span data-ttu-id="ad577-228">**iOS**</span><span class="sxs-lookup"><span data-stu-id="ad577-228">**iOS**</span></span>|<span data-ttu-id="ad577-229">**Android 手機**</span><span class="sxs-lookup"><span data-stu-id="ad577-229">**Android phone**</span></span>|<span data-ttu-id="ad577-230">**Android 平板電腦**</span><span class="sxs-lookup"><span data-stu-id="ad577-230">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad577-231">此版本支援 Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013 及商務用 Skype 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="ad577-231">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="ad577-232">此版本支援 Mac 版 Word 2016、Mac 版 Excel 2016 及 Mac 版 PowerPoint 2016 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="ad577-232">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="ad577-233">此版本支援 iPad 版 Word、iPad 版 Excel 及 iPad 版 PowerPoint 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="ad577-233">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="ad577-234">此版本支援 Android 版 Word、Android 版 Excel 及 Android 版 PowerPoint 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="ad577-234">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="ad577-235">此版本支援 Android 版 Word、Android 版 Excel 及 Android 版 PowerPoint 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="ad577-235">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="ad577-236">此版本支援 Outlook 2013 和 Outlook 2016 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="ad577-236">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="ad577-237">此版本支援 Mac 版 Outlook 2016 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="ad577-237">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="ad577-238">此版本支援 iPad 版 Outlook 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="ad577-238">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

