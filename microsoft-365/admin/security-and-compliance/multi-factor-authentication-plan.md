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
ms.openlocfilehash: e3886387740fe904b9c9458f7b1abf736c3ef83f
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153565"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a><span data-ttu-id="74404-103">Office 365 部署多重要素驗證方案</span><span class="sxs-lookup"><span data-stu-id="74404-103">Plan for multi-factor authentication for Office 365 Deployments</span></span>

<span data-ttu-id="74404-p101">多重要素驗證 (MFA) 是一種需要使用多種驗證方法並為使用者登入和交易額外添加一層安全性的驗證方法。它的運作方式是要求使用下列兩種或更多的驗證方法：</span><span class="sxs-lookup"><span data-stu-id="74404-p101">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions. It works by requiring any two or more of the following verification methods:</span></span>
  
- <span data-ttu-id="74404-106">隨機產生的密碼</span><span class="sxs-lookup"><span data-stu-id="74404-106">A randomly generated pass code</span></span>
    
- <span data-ttu-id="74404-107">電話</span><span class="sxs-lookup"><span data-stu-id="74404-107">A phone call</span></span>
    
- <span data-ttu-id="74404-108">智慧卡 (虛擬或實體)</span><span class="sxs-lookup"><span data-stu-id="74404-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="74404-109">生物特徵辨識裝置</span><span class="sxs-lookup"><span data-stu-id="74404-109">A biometric device</span></span> 
    
## <a name="multi-factor-authentication-in-office-365"></a><span data-ttu-id="74404-110">Office 365中的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="74404-110">Multi-factor authentication in Office 365</span></span>

<span data-ttu-id="74404-111">Office 365 使用多重要素驗證，協助提供額外的安全性，並從 Microsoft 365 系統管理中心加以管理。</span><span class="sxs-lookup"><span data-stu-id="74404-111">Office 365 uses multi-factor authentication to help provide the extra security and is managed from the Microsoft 365 admin center.</span></span> <span data-ttu-id="74404-112">Office 365 提供下列 Azure Multi-Factor 驗證功能的子集做為訂閱的一部分：</span><span class="sxs-lookup"><span data-stu-id="74404-112">Office 365 offers the following subset of Azure Multi-Factor Authentication capabilities as a part of the subscription:</span></span> 
  
- <span data-ttu-id="74404-113">能夠啟用並強制執行使用者的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="74404-113">The ability to enable and enforce multi-factor authentication for end users</span></span>
    
- <span data-ttu-id="74404-114">使用行動裝置 App (線上和單次密碼 [OTP]) 做為次要驗證因素</span><span class="sxs-lookup"><span data-stu-id="74404-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="74404-115">使用電話做為次要驗證因素</span><span class="sxs-lookup"><span data-stu-id="74404-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="74404-116">使用簡訊服務 (SMS) 訊息做為次要驗證因素</span><span class="sxs-lookup"><span data-stu-id="74404-116">The use of a Short Message Service (SMS) message as a second authentication factor</span></span>
    
- <span data-ttu-id="74404-117">非瀏覽器用戶端的應用程式密碼 (例如，Microsoft Lync 2013 通訊軟體)</span><span class="sxs-lookup"><span data-stu-id="74404-117">Application passwords for non browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="74404-118">驗證電話期間的預設 Microsoft 問候語</span><span class="sxs-lookup"><span data-stu-id="74404-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="74404-p103">如需新增功能的完整清單，請參閱 [Azure 多重要素驗證版本比較](https://go.microsoft.com/fwlink/?LinkId=506927)。您可以購買 Azure 多重要素驗證服務，隨時獲得完整功能。</span><span class="sxs-lookup"><span data-stu-id="74404-p103">For the full list of added features, see [the comparison of Azure Multi-Factor Authentication version](https://go.microsoft.com/fwlink/?LinkId=506927). You can always get the full functionality by purchasing the Azure Multi-Factor Authentication service.</span></span> 
  
<span data-ttu-id="74404-121">視您擁有的是 Office 365 之僅限雲端部署或使用單一登入和 Active Directory 同盟服務 (AD FS) 的混合設定而定，您會獲得不同的功能子集。</span><span class="sxs-lookup"><span data-stu-id="74404-121">You get a different subset of capabilities depending on whether you have a cloud-only deployment for Office 365 or a hybrid set up with single sign-on and Active Directory Federation Services (AD FS).</span></span> 
  
|<span data-ttu-id="74404-122">**您在何處管理 Office 365 租用戶？**</span><span class="sxs-lookup"><span data-stu-id="74404-122">**Where do you manage your Office 365 tenant?**</span></span>|<span data-ttu-id="74404-123">**MFA 次要因素選項**</span><span class="sxs-lookup"><span data-stu-id="74404-123">**MFA second factor options**</span></span>|
|:-----|:-----|
|<span data-ttu-id="74404-124">僅限雲端</span><span class="sxs-lookup"><span data-stu-id="74404-124">Cloud only</span></span>  <br/> |<span data-ttu-id="74404-125">Azure Multi-Factor 驗證（文字或電話）</span><span class="sxs-lookup"><span data-stu-id="74404-125">Azure Multi-Factor Authentication (text or phone call)</span></span>  <br/> |
|<span data-ttu-id="74404-126">混合設定、受管理的內部部署</span><span class="sxs-lookup"><span data-stu-id="74404-126">Hybrid setup, managed on-premises</span></span>  <br/> | <span data-ttu-id="74404-127">如果您透過內部部署管理使用者身分識別，您有下列選擇：</span><span class="sxs-lookup"><span data-stu-id="74404-127">If you manage user identity on-premises, you have the following choices:</span></span>  <br/>  <span data-ttu-id="74404-128">實體或虛擬智慧卡（使用 AD FS 時）</span><span class="sxs-lookup"><span data-stu-id="74404-128">Physical or virtual smart card (when using AD FS)</span></span>  <br/> <span data-ttu-id="74404-129">[Azure Multi-Factor 驗證](https://go.microsoft.com/fwlink/p/?LinkId=526677)（AD FS 的模組）</span><span class="sxs-lookup"><span data-stu-id="74404-129">[Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=526677) (module for AD FS)</span></span>  <br/>  <span data-ttu-id="74404-130">Azure Active Directory （Azure AD） Multi-Factor 驗證</span><span class="sxs-lookup"><span data-stu-id="74404-130">Azure Active Directory (Azure AD) Multi-Factor Authentication</span></span>  <br/> |
   
  
<span data-ttu-id="74404-p104">下圖顯示更新的 Office 2013 裝置 App (Windows 版) 如何讓使用者能夠使用 MFA 登入。Office 2013 裝置 App 透過使用 [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684) 支援多重要素驗證。Azure AD 託管使用者可以登入的網頁。身分識別提供者可以是 Azure AD 或 AD FS 等同盟身分識別提供者。同盟使用者的驗證按下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="74404-p104">The following figure shows how the updated Office 2013 device apps (on Windows) enable users to sign in with MFA. TheOffice 2013 device apps support multi-factor authentication through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure AD hosts a webpage where users can sign in. The identity provider can be Azure AD or a federated identity provider like AD FS. The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="74404-p105">Azure AD 將使用者重新導向到由 Office 365 租用戶的記錄之身分識別提供者託管的登入網頁。身分識別提供者取決於使用者登入名稱中指定的網域。</span><span class="sxs-lookup"><span data-stu-id="74404-p105">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the Office 365 tenant. The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="74404-138">使用者在他的裝置的登入網頁上登入。</span><span class="sxs-lookup"><span data-stu-id="74404-138">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="74404-139">使用者成功登入後，身分識別提供者會傳回權杖給 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="74404-139">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="74404-140">Azure AD 會傳回 JSON Web 權杖 (JWT) 給 Office 裝置 App，而裝置 App 會搭配 Office 365 使用 JWT 獲得授權。</span><span class="sxs-lookup"><span data-stu-id="74404-140">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Office 365.</span></span> 
    
<span data-ttu-id="74404-141">請見下圖的詳細說明：</span><span class="sxs-lookup"><span data-stu-id="74404-141">This is detailed in the following figure:</span></span>
  
![Office 2013 裝置應用程式的現代化驗證。](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)
  
## <a name="software-requirements"></a><span data-ttu-id="74404-143">軟體需求</span><span class="sxs-lookup"><span data-stu-id="74404-143">Software requirements</span></span>

<span data-ttu-id="74404-144">若要啟用適用於 Office 2013 用戶端應用程式的 MFA，您必須安裝下列軟體 (以下所列的版本或更新版本)，根據您擁有的是[隨選即用型安裝](#click-to-run-based-installations)或 [MSI 型安裝](#msi-based-installations)而定。</span><span class="sxs-lookup"><span data-stu-id="74404-144">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="74404-145">若要判斷您的 Office 安裝是否為隨選即用或 MSI 型：</span><span class="sxs-lookup"><span data-stu-id="74404-145">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="74404-146">啟動 Outlook 2013。</span><span class="sxs-lookup"><span data-stu-id="74404-146">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="74404-147">**在 [檔案] 功能表上**，選擇 [ **Office 帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="74404-147">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="74404-p106">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed. For MSI-based installations, the **Update Options** item is not displayed.</span><span class="sxs-lookup"><span data-stu-id="74404-p106">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed. For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![Graphic that shows how to tell if Office 2013 install is click-to-run or MSI-based](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="74404-151">隨選即用型安裝</span><span class="sxs-lookup"><span data-stu-id="74404-151">Click-to-run based installations</span></span>

<span data-ttu-id="74404-p107">若是隨選即用型安裝，您必須安裝下列軟體 (以下所列的檔案版本或更新的檔案版本)。如果您的檔案版本並非大於或等於列出的檔案版本，請使用下列步驟進行更新。</span><span class="sxs-lookup"><span data-stu-id="74404-p107">For Click-to-run based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="74404-154">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="74404-154">**File name**</span></span>|<span data-ttu-id="74404-155">**電腦上的安裝路徑**</span><span class="sxs-lookup"><span data-stu-id="74404-155">**Install path on your computer**</span></span>|<span data-ttu-id="74404-156">**檔案版本**</span><span class="sxs-lookup"><span data-stu-id="74404-156">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="74404-157">MSO.Dll</span><span class="sxs-lookup"><span data-stu-id="74404-157">MSO.DLL</span></span>  <br/> |<span data-ttu-id="74404-158">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="74404-158">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="74404-159">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="74404-159">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="74404-160">Csi。Dll</span><span class="sxs-lookup"><span data-stu-id="74404-160">CSI.DLL</span></span>  <br/> |<span data-ttu-id="74404-161">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="74404-161">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="74404-162">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="74404-162">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="74404-163">Groove</span><span class="sxs-lookup"><span data-stu-id="74404-163">Groove.EXE</span></span>  <br/> |<span data-ttu-id="74404-164">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="74404-164">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="74404-165">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="74404-165">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="74404-166">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="74404-166">Outlook.exe</span></span>  <br/> |<span data-ttu-id="74404-167">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="74404-167">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="74404-168">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="74404-168">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="74404-169">ADAL.Dll</span><span class="sxs-lookup"><span data-stu-id="74404-169">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="74404-170">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="74404-170">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="74404-171">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="74404-171">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="74404-172">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="74404-172">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="74404-173">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="74404-173">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="74404-174">不盡相同</span><span class="sxs-lookup"><span data-stu-id="74404-174">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="74404-175">MSI 型安裝</span><span class="sxs-lookup"><span data-stu-id="74404-175">MSI-based installations</span></span>

<span data-ttu-id="74404-p108">若是 MSI 型安裝，您必須安裝下列軟體 (以下所列的檔案版本或更新的檔案版本)。如果您的檔案版本並非大於或等於列出的檔案版本，請使用「更新知識庫文章」一欄中的連結進行更新。</span><span class="sxs-lookup"><span data-stu-id="74404-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="74404-178">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="74404-178">**File name**</span></span>|<span data-ttu-id="74404-179">**電腦上的安裝路徑**</span><span class="sxs-lookup"><span data-stu-id="74404-179">**Install path on your computer**</span></span>|<span data-ttu-id="74404-180">**可於何處取得更新**</span><span class="sxs-lookup"><span data-stu-id="74404-180">**Where to get the update**</span></span>|<span data-ttu-id="74404-181">**版本**</span><span class="sxs-lookup"><span data-stu-id="74404-181">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="74404-182">MSO.Dll</span><span class="sxs-lookup"><span data-stu-id="74404-182">MSO.DLL</span></span>  <br/> |<span data-ttu-id="74404-183">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="74404-183">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="74404-184">KB3085480</span><span class="sxs-lookup"><span data-stu-id="74404-184">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="74404-185">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="74404-185">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="74404-186">Csi。Dll</span><span class="sxs-lookup"><span data-stu-id="74404-186">CSI.DLL</span></span>  <br/> |<span data-ttu-id="74404-187">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="74404-187">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="74404-188">KB3085504</span><span class="sxs-lookup"><span data-stu-id="74404-188">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="74404-189">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="74404-189">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="74404-190">Groove</span><span class="sxs-lookup"><span data-stu-id="74404-190">Groove.exe</span></span>  <br/> |<span data-ttu-id="74404-191">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="74404-191">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="74404-192">KB3085509</span><span class="sxs-lookup"><span data-stu-id="74404-192">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="74404-193">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="74404-193">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="74404-194">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="74404-194">Outlook.exe</span></span>  <br/> |<span data-ttu-id="74404-195">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="74404-195">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="74404-196">KB3085495</span><span class="sxs-lookup"><span data-stu-id="74404-196">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="74404-197">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="74404-197">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="74404-198">ADAL.Dll</span><span class="sxs-lookup"><span data-stu-id="74404-198">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="74404-199">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="74404-199">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="74404-200">KB3055000</span><span class="sxs-lookup"><span data-stu-id="74404-200">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="74404-201">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="74404-201">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="74404-202">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="74404-202">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="74404-203">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="74404-203">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="74404-204">MS14-052</span><span class="sxs-lookup"><span data-stu-id="74404-204">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="74404-205">不適用</span><span class="sxs-lookup"><span data-stu-id="74404-205">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="74404-206">啟用 MFA</span><span class="sxs-lookup"><span data-stu-id="74404-206">Enable MFA</span></span>

<span data-ttu-id="74404-207">若要啟用 MFA，您必須完成下列事項：</span><span class="sxs-lookup"><span data-stu-id="74404-207">To enable MFA, you have to complete the following:</span></span>
  
1. <span data-ttu-id="74404-208">啟用新式驗證的用戶端：</span><span class="sxs-lookup"><span data-stu-id="74404-208">Enable clients for modern authentication:</span></span>
    
  - <span data-ttu-id="74404-209">[在 Windows 裝置上啟用 Office 2013 的新式驗證](enable-modern-authentication.md) 。</span><span class="sxs-lookup"><span data-stu-id="74404-209">[Enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md) .</span></span> 
    
  - <span data-ttu-id="74404-210">使用協力廠商目錄服務設定 Azure Multi-Factor 驗證。</span><span class="sxs-lookup"><span data-stu-id="74404-210">Set up Azure Multi-Factor Authentication with third-party directory services.</span></span>
    
    <span data-ttu-id="74404-211">請參閱[Azure Multi-Factor 驗證和協力廠商 VPN 解決方案的高級案例](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)，以取得此程式接受之特定身分識別提供者的資訊。</span><span class="sxs-lookup"><span data-stu-id="74404-211">See the [Advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
2. [<span data-ttu-id="74404-212">設定 Office 365 的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="74404-212">Set up multi-factor authentication for Office 365</span></span>](set-up-multi-factor-authentication.md)
    
3. <span data-ttu-id="74404-213">告知個別使用者如何使用 MFA 登入：[使用雙步驟驗證登入 Office 365](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)。</span><span class="sxs-lookup"><span data-stu-id="74404-213">Tell individual users how to sign in by MFA: [Sign in to Office 365 with 2-step verification](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="74404-214">如果您已對使用者啟用 Azure Multi-Factor 驗證，而且他們的任何執行 Office 2013 的裝置都未啟用新式驗證，則需要在這些裝置上使用 AppPasswords。</span><span class="sxs-lookup"><span data-stu-id="74404-214">If you have enabled your users for Azure Multi-Factor Authentication and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use AppPasswords on those devices.</span></span> <span data-ttu-id="74404-215">如需更多有關 AppPasswords 以及應使用它們的時機/位置/方式，請參閱：[Azure 多重要素驗證的應用程式密碼](https://go.microsoft.com/fwlink/p/?LinkId=528178)。</span><span class="sxs-lookup"><span data-stu-id="74404-215">More information on AppPasswords and when/where/how they should be used can be found here: [App Passwords with Azure Multi_Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span> 
  
## <a name="faq"></a><span data-ttu-id="74404-216">常見問題集</span><span class="sxs-lookup"><span data-stu-id="74404-216">FAQ</span></span>

[<span data-ttu-id="74404-217">新式驗證 Wiki 文章的相關常見問題集</span><span class="sxs-lookup"><span data-stu-id="74404-217">FAQ about Modern Authentication wiki article</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
 <span data-ttu-id="74404-218">**已知問題：**</span><span class="sxs-lookup"><span data-stu-id="74404-218">**Known issues:**</span></span>
  
[<span data-ttu-id="74404-219">Office 2013 和 Office 365 專業增強版新式驗證：上線前的相關須知</span><span class="sxs-lookup"><span data-stu-id="74404-219">Office 2013 and Office 365 ProPlus modern authentication : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="74404-220">**Azure 多重要素驗證疑難排解：**</span><span class="sxs-lookup"><span data-stu-id="74404-220">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="74404-221">請參閱[Azure Multi-Factor 驗證疑難排解](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)。</span><span class="sxs-lookup"><span data-stu-id="74404-221">See [Troubleshoot Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="74404-222">如何針對使用 AD FS 時的 Office 2013 新式驗證之登入問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="74404-222">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="74404-223">**當無法使用替代識別碼時：**</span><span class="sxs-lookup"><span data-stu-id="74404-223">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="74404-224">如何使用 PowerShell 修正 UPN 重複的問題</span><span class="sxs-lookup"><span data-stu-id="74404-224">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
<span data-ttu-id="74404-225">[用來修正使用者主體名稱重複問題的指令碼](https://go.microsoft.com/fwlink/p/?LinkId=396725) (英文)</span><span class="sxs-lookup"><span data-stu-id="74404-225">[Script to fix duplicate user principal names](https://go.microsoft.com/fwlink/p/?LinkId=396725)</span></span>
  
 <span data-ttu-id="74404-226">**用戶端存取篩選：**</span><span class="sxs-lookup"><span data-stu-id="74404-226">**Client access filtering:**</span></span>
  
[<span data-ttu-id="74404-227">Office 2013 和 Office 365 專業增強版新式驗證和用戶端存取篩選原則：上線前的相關須知</span><span class="sxs-lookup"><span data-stu-id="74404-227">Office 2013 and Office 365 ProPlus modern authentication and client access filtering policies : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="74404-228">**哪些應用程式支援 MFA？**</span><span class="sxs-lookup"><span data-stu-id="74404-228">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="74404-229">**Windows**</span><span class="sxs-lookup"><span data-stu-id="74404-229">**Windows**</span></span>|<span data-ttu-id="74404-230">**Mac**</span><span class="sxs-lookup"><span data-stu-id="74404-230">**Mac**</span></span>|<span data-ttu-id="74404-231">**iOS**</span><span class="sxs-lookup"><span data-stu-id="74404-231">**iOS**</span></span>|<span data-ttu-id="74404-232">**Android 手機**</span><span class="sxs-lookup"><span data-stu-id="74404-232">**Android phone**</span></span>|<span data-ttu-id="74404-233">**Android 平板電腦**</span><span class="sxs-lookup"><span data-stu-id="74404-233">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="74404-234">此版本支援 Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013 及商務用 Skype 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="74404-234">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="74404-235">此版本支援 Mac 版 Word 2016、Mac 版 Excel 2016 及 Mac 版 PowerPoint 2016 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="74404-235">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="74404-236">此版本支援 iPad 版 Word、iPad 版 Excel 及 iPad 版 PowerPoint 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="74404-236">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="74404-237">此版本支援 Android 版 Word、Android 版 Excel 及 Android 版 PowerPoint 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="74404-237">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="74404-238">此版本支援 Android 版 Word、Android 版 Excel 及 Android 版 PowerPoint 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="74404-238">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="74404-239">此版本支援 Outlook 2013 和 Outlook 2016 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="74404-239">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="74404-240">此版本支援 Mac 版 Outlook 2016 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="74404-240">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="74404-241">此版本支援 iPad 版 Outlook 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="74404-241">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

