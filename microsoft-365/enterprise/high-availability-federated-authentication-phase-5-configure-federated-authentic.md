---
title: 高可用性同盟驗證階段5設定 Microsoft 365 的同盟驗證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: 摘要：在 Microsoft Azure 中針對 Microsoft 365 的高可用性同盟驗證設定 Azure AD Connect。
ms.openlocfilehash: f00763487261b62940ac5def38d35158db77a699
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688638"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a><span data-ttu-id="b522d-103">高可用性同盟驗證階段5：設定 Microsoft 365 的同盟驗證</span><span class="sxs-lookup"><span data-stu-id="b522d-103">High availability federated authentication Phase 5: Configure federated authentication for Microsoft 365</span></span>

<span data-ttu-id="b522d-104">在此最後一個在 Azure 基礎結構服務中為 Microsoft 365 部署高可用性同盟驗證的最後階段，您可以取得及安裝公用憑證授權單位單位所發出的憑證、驗證您的設定，然後在目錄同步處理伺服器上安裝並執行 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="b522d-104">In this final phase of deploying high availability federated authentication for Microsoft 365 in Azure infrastructure services, you get and install a certificate issued by a public certification authority, verify your configuration, and then install and run Azure AD Connect on the directory synchronization server.</span></span> <span data-ttu-id="b522d-105">Azure AD Connect 會為同盟驗證設定您的 Microsoft 365 訂閱和 Active Directory Federation Services (AD FS) 和 web 應用程式 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b522d-105">Azure AD Connect configures your Microsoft 365 subscription and your Active Directory Federation Services (AD FS) and web application proxy servers for federated authentication.</span></span>
  
<span data-ttu-id="b522d-106">請參閱 [在 Azure 中部署 Microsoft 365 的高可用性同盟驗證](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) ，以瞭解所有階段。</span><span class="sxs-lookup"><span data-stu-id="b522d-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a><span data-ttu-id="b522d-107">取得公用憑證並將其複製到目錄同步處理伺服器</span><span class="sxs-lookup"><span data-stu-id="b522d-107">Get a public certificate and copy it to the directory synchronization server</span></span>

<span data-ttu-id="b522d-108">從具有下列屬性的公用憑證授權單位單位取得數位憑證：</span><span class="sxs-lookup"><span data-stu-id="b522d-108">Get a digital certificate from a public certification authority with the following properties:</span></span>
  
- <span data-ttu-id="b522d-109">適用于建立 SSL 連線的 x.509 憑證。</span><span class="sxs-lookup"><span data-stu-id="b522d-109">An X.509 certificate suitable for creating SSL connections.</span></span>
    
- <span data-ttu-id="b522d-110">主體替代名稱 (SAN) 擴充屬性設定為您的同盟服務 FQDN (範例： fs.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="b522d-110">The Subject Alternative Name (SAN) extended property is set to your federation service FQDN (example: fs.contoso.com).</span></span>
    
- <span data-ttu-id="b522d-111">憑證必須有私密金鑰，而且可以儲存為 PFX 格式。</span><span class="sxs-lookup"><span data-stu-id="b522d-111">The certificate must have the private key and be stored in PFX format.</span></span>
    
<span data-ttu-id="b522d-112">此外，您的組織電腦和裝置必須信任發行數位憑證的公用憑證授權單位單位。</span><span class="sxs-lookup"><span data-stu-id="b522d-112">Additionally, your organization computers and devices must trust the public certification authority that is issuing the digital certificate.</span></span> <span data-ttu-id="b522d-113">這項信任是透過從您的電腦和裝置上的「受信任的根憑證授權單位」存放區中安裝的公用憑證授權單位單位來建立。</span><span class="sxs-lookup"><span data-stu-id="b522d-113">This trust is established by having a root certificate from the public certification authority installed in the trusted root certification authorities store on your computers and devices.</span></span> <span data-ttu-id="b522d-114">執行 Microsoft Windows 的電腦通常會從一般使用的憑證授權單位單位安裝一組這類憑證。</span><span class="sxs-lookup"><span data-stu-id="b522d-114">Computers running Microsoft Windows typically have a set of these types of certificates installed from commonly-used certification authorities.</span></span> <span data-ttu-id="b522d-115">若尚未安裝您的公用憑證授權單位單位的根憑證，則必須將其部署至您組織的電腦和裝置。</span><span class="sxs-lookup"><span data-stu-id="b522d-115">If the root certificate from your public certification authority is not already installed, you must deploy this to the computers and devices of your organization.</span></span>
  
<span data-ttu-id="b522d-116">如需有關同盟驗證之憑證需求的詳細資訊，請參閱 [同盟安裝和設定的必要條件](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration)。</span><span class="sxs-lookup"><span data-stu-id="b522d-116">For more information about certificate requirements for federated authentication, see [Prerequisites for federation installation and configuration](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span></span>
  
<span data-ttu-id="b522d-117">當您收到憑證時，請將它複製到目錄同步處理伺服器 C：磁片磁碟機上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="b522d-117">When you receive the certificate, copy it to a folder on the C: drive of the directory synchronization server.</span></span> <span data-ttu-id="b522d-118">例如，將檔案命名為 SSL，並將其儲存在目錄同步處理伺服器上的 [C： \\ 證書] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b522d-118">For example, name the file SSL.pfx and store it in the C:\\Certs folder on the directory synchronization server.</span></span>
  
## <a name="verify-your-configuration"></a><span data-ttu-id="b522d-119">驗證您的設定</span><span class="sxs-lookup"><span data-stu-id="b522d-119">Verify your configuration</span></span>

<span data-ttu-id="b522d-120">您現在應該可以為 Microsoft 365 設定 Azure AD Connect 及同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="b522d-120">You should now be ready to configure Azure AD Connect and federated authentication for Microsoft 365.</span></span> <span data-ttu-id="b522d-121">若要確定您是，以下是檢查清單：</span><span class="sxs-lookup"><span data-stu-id="b522d-121">To ensure that you are, here is a checklist:</span></span>
  
- <span data-ttu-id="b522d-122">您的組織的公用網域已新增至您的 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="b522d-122">Your organization's public domain is added to your Microsoft 365 subscription.</span></span>
    
- <span data-ttu-id="b522d-123">您組織的 Microsoft 365 使用者帳戶已設定為您組織的公用功能變數名稱，而且可成功登入。</span><span class="sxs-lookup"><span data-stu-id="b522d-123">Your organization's Microsoft 365 user accounts are configured to your organization's public domain name and can successfully sign in.</span></span>
    
- <span data-ttu-id="b522d-124">您已根據您的公用功能變數名稱判斷同盟服務 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b522d-124">You have determined a federation service FQDN based your public domain name.</span></span>
    
- <span data-ttu-id="b522d-125">您的同盟服務 FQDN 的公用 DNS A 記錄指向 web 應用程式 proxy 伺服器的網際網路對向 Azure 負載平衡器的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b522d-125">A public DNS A record for your federation service FQDN points to the public IP address of the Internet-facing Azure load balancer for the web application proxy servers.</span></span>
    
- <span data-ttu-id="b522d-126">您的同盟服務 FQDN 的私人 DNS A 記錄會指向 AD FS 伺服器內部 Azure 負載平衡器的私人 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b522d-126">A private DNS A record for your federation service FQDN points to the private IP address of the internal Azure load balancer for the AD FS servers.</span></span>
    
- <span data-ttu-id="b522d-127">適用于將 SAN 設定為您的同盟服務 FQDN 之 SSL 連線的公用憑證授權單位單位-isssued 數位憑證是儲存在目錄同步處理伺服器上的 PFX 檔案。</span><span class="sxs-lookup"><span data-stu-id="b522d-127">A public certification authority-isssued digital certificate suitable for SSL connections with the SAN set to your federation service FQDN is a PFX file stored on your directory synchronization server.</span></span>
    
- <span data-ttu-id="b522d-128">公用憑證授權單位單位的根憑證會安裝在電腦和裝置上的「受信任的憑證授權單位單位」存放區中。</span><span class="sxs-lookup"><span data-stu-id="b522d-128">The root certificate for the public certification authority is installed in the Trusted Root Certification Authorities store on your computers and devices.</span></span>
    
<span data-ttu-id="b522d-129">以下是 Contoso 組織的範例：</span><span class="sxs-lookup"><span data-stu-id="b522d-129">Here is an example for the Contoso organization:</span></span>
  
<span data-ttu-id="b522d-130">**Azure 中高可用性同盟驗證基礎結構的範例設定**</span><span class="sxs-lookup"><span data-stu-id="b522d-130">**An example configuration for a high availability federated authentication infrastructure in Azure**</span></span>

![Azure 中高可用性 Microsoft 365 同盟驗證基礎結構的設定範例](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a><span data-ttu-id="b522d-132">執行 Azure AD Connect 以設定同盟驗證</span><span class="sxs-lookup"><span data-stu-id="b522d-132">Run Azure AD Connect to configure federated authentication</span></span>

<span data-ttu-id="b522d-133">Azure AD Connect 工具使用下列步驟來設定 AD FS 伺服器、web 應用程式 proxy 伺服器及 Microsoft 365 進行同盟驗證：</span><span class="sxs-lookup"><span data-stu-id="b522d-133">The Azure AD Connect tool configures the AD FS servers, the web application proxy servers, and Microsoft 365 for federated authentication with these steps:</span></span>
  
1. <span data-ttu-id="b522d-134">使用具有本機系統管理員許可權的網域帳戶，建立目錄同步處理伺服器的遠端桌面連線。</span><span class="sxs-lookup"><span data-stu-id="b522d-134">Create a remote desktop connection to your directory synchronization server with a domain account that has local administrator privileges.</span></span>
    
2. <span data-ttu-id="b522d-135">從目錄同步處理伺服器的桌面，開啟 Internet Explorer，然後移至 [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 。</span><span class="sxs-lookup"><span data-stu-id="b522d-135">From the desktop of the directory synchronization server, open Internet Explorer and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
3. <span data-ttu-id="b522d-136">在 [ **Microsoft Azure Active Directory 連線]** 頁面上，按一下 [ **下載**]，然後按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="b522d-136">On the **Microsoft Azure Active Directory Connect** page, click **Download**, and then click **Run**.</span></span>
    
4. <span data-ttu-id="b522d-137">在 [ **歡迎使用 AZURE AD Connect]** 頁面上，按一下 [ **我同意**]，然後按一下 [ **繼續]。**</span><span class="sxs-lookup"><span data-stu-id="b522d-137">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue.**</span></span>
    
5. <span data-ttu-id="b522d-138">在 [ **快速設定** ] 頁面上，按一下 [ **自訂**]。</span><span class="sxs-lookup"><span data-stu-id="b522d-138">On the **Express Settings** page, click **Customize**.</span></span>
    
6. <span data-ttu-id="b522d-139">在 [ **安裝必要元件** ] 頁面上，按一下 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="b522d-139">On the **Install required components** page, click **Install**.</span></span>
    
7. <span data-ttu-id="b522d-140">在 [使用者登入]\*\*\*\* 頁面上，按一下 [和 AD FS 的同盟]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b522d-140">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="b522d-141">在 [連線 **到 AZURE AD]** 頁面上，輸入您的 Microsoft 365 訂閱全域管理員帳戶的名稱和密碼，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-141">On the **Connect to Azure AD** page, type the name and password of a global administrator account for your Microsoft 365 subscription, and then click **Next**.</span></span>
    
9. <span data-ttu-id="b522d-142">在 [ **連接目錄]** 頁面上，確定已選取 **樹**系中的 [您的內部部署 Active Directory 網域 (服務]) 樹系，輸入網域管理員帳戶的名稱和密碼，按一下 [ **新增目錄**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-142">On the **Connect your directories** page, ensure that your on-premises Active Directory Domain Services (AD DS) forest is selected in **Forest**, type the name and password of a domain administrator account, click **Add Directory**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="b522d-143">在 [ **AZURE AD 登錄** 設定] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-143">On the **Azure AD sign-in configuration** page, click **Next**.</span></span>
    
11. <span data-ttu-id="b522d-144">在 [ **網域與 OU 篩選** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-144">On the **Domain and OU filtering** page, click **Next**.</span></span>
    
12. <span data-ttu-id="b522d-145">在 [ **唯一識別您的使用者** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-145">On the **Uniquely identifying your users** page, click **Next**.</span></span>
    
13. <span data-ttu-id="b522d-146">在 [ **篩選使用者和裝置** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-146">On the **Filter users and devices** page, click **Next**.</span></span>
    
14. <span data-ttu-id="b522d-147">在 [ **選用功能** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-147">On the **Optional features** page, click **Next**.</span></span>
    
15. <span data-ttu-id="b522d-148">在 [ **AD fs 伺服器** 陣列] 頁面上，按一下 [ **設定新的 AD fs 伺服器**陣列]。</span><span class="sxs-lookup"><span data-stu-id="b522d-148">On the **AD FS farm** page, click **Configure a new AD FS farm**.</span></span>
    
16. <span data-ttu-id="b522d-149">按一下 **[流覽]** ，並指定公用憑證授權單位單位之 SSL 憑證的位置和名稱。</span><span class="sxs-lookup"><span data-stu-id="b522d-149">Click **Browse** and specify the location and name of the SSL certificate from the public certification authority.</span></span>
    
17. <span data-ttu-id="b522d-150">出現提示時，請輸入憑證密碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-150">When prompted, type the certificate password, and then click **OK**.</span></span>
    
18. <span data-ttu-id="b522d-151">確認 **主體名稱** 及 **同盟服務名稱** 已設定為您的同盟服務 FQDN，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-151">Verify that the **Subject Name** and **Federation Service Name** are set to your federation service FQDN, and then click **Next**.</span></span>
    
19. <span data-ttu-id="b522d-152">在 [ **AD fs 伺服器** ] 頁面上，輸入您第一個 AD fs 伺服器的名稱 (Table M-專案 4-虛擬機器名稱] 欄) ，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b522d-152">On the **AD FS servers** page, type your first AD FS server's name (Table M - Item 4 - Virtual machine name column), and then click **Add**.</span></span>
    
20. <span data-ttu-id="b522d-153">輸入您第二個 AD FS 伺服器的名稱 (Table M-專案 5-虛擬機器名稱] 欄) ，按一下 [ **新增**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-153">Type your second AD FS server's name (Table M - Item 5 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
21. <span data-ttu-id="b522d-154">在 [ **Web 應用程式 proxy 伺服器** ] 頁面上，輸入您第一個 Web 應用程式 proxy 伺服器的名稱 (Table M-專案 6-虛擬機器名稱] 欄) ，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b522d-154">On the **Web Application Proxy servers** page, type your first web application proxy server's name (Table M - Item 6 - Virtual machine name column), and then click **Add**.</span></span>
    
22. <span data-ttu-id="b522d-155">輸入第二個 web 應用程式 proxy 伺服器的名稱 (Table M-專案 7-虛擬機器名稱] 欄) ，按一下 [ **新增**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-155">Type your second web application proxy server's name (Table M - Item 7 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
23. <span data-ttu-id="b522d-156">在 [ **網域管理員認證** ] 頁面上，輸入網域管理員帳戶的使用者名稱和密碼，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-156">On the **Domain Administrator credentials** page, type the user name and password of a domain administrator account, and then click **Next**.</span></span>
    
24. <span data-ttu-id="b522d-157">在 [ **AD FS 服務帳戶** ] 頁面上，輸入企業系統管理員帳戶的使用者名稱和密碼，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-157">On the **AD FS service account** page, type the user name and password of an enterprise administrator account, and then click **Next**.</span></span>
    
25. <span data-ttu-id="b522d-158">在 [ **AZURE AD 網域** ] 頁面的 [ **網域**] 中，選取您組織的 DNS 功能變數名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b522d-158">On the **Azure AD Domain** page, in **Domain**, select your organization's DNS domain name, and then click **Next**.</span></span>
    
26. <span data-ttu-id="b522d-159">在 [準備設定]\*\*\*\* 頁面上，按一下 [安裝]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b522d-159">On the **Ready to configure** page, click **Install**.</span></span>
    
27. <span data-ttu-id="b522d-160">在 [安裝完成]\*\*\*\* 頁面上，按一下 [驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b522d-160">On the **Installation complete** page, click **Verify**.</span></span> <span data-ttu-id="b522d-161">您應該會看到兩封訊息，指出內部網路和網際網路設定均已成功驗證。</span><span class="sxs-lookup"><span data-stu-id="b522d-161">You should see two messages indicating that both the intranet and Internet configuration was successfully verified.</span></span>
    
  - <span data-ttu-id="b522d-162">內部網路郵件應該會列出您的 AD FS 伺服器之 Azure 內部負載平衡器的私人 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b522d-162">The intranet message should list the private IP address of your Azure internal load balancer for your AD FS servers.</span></span>
    
  - <span data-ttu-id="b522d-163">網際網路訊息應該會列出您的 web 應用程式 proxy 伺服器之 Azure 網際網路對向負載平衡器的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b522d-163">The Internet message should list the public IP address of your Azure Internet-facing load balancer for your web application proxy servers.</span></span>
    
28. <span data-ttu-id="b522d-164">在 [安裝完成]\*\*\*\* 頁面上，按一下 [結束]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b522d-164">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="b522d-165">以下是伺服器的最後設定，具有預留位置名稱。</span><span class="sxs-lookup"><span data-stu-id="b522d-165">Here is the final configuration, with placeholder names for the servers.</span></span>
  
<span data-ttu-id="b522d-166">**第5階段： Azure 中高可用性同盟驗證基礎結構的最終設定**</span><span class="sxs-lookup"><span data-stu-id="b522d-166">**Phase 5: The final configuration of a high availability federated authentication infrastructure in Azure**</span></span>

![Azure 中高可用性 Microsoft 365 同盟驗證基礎結構的最終設定](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="b522d-168">Azure 中 Microsoft 365 的高可用性同盟驗證基礎結構已完成。</span><span class="sxs-lookup"><span data-stu-id="b522d-168">Your high availability federated authentication infrastructure for Microsoft 365 in Azure is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b522d-169">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b522d-169">See Also</span></span>

[<span data-ttu-id="b522d-170">Azure 中的 Microsoft 365 高可用性同盟驗證</span><span class="sxs-lookup"><span data-stu-id="b522d-170">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="b522d-171">Microsoft 365 開發/測試環境的同盟身分識別</span><span class="sxs-lookup"><span data-stu-id="b522d-171">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="b522d-172">Microsoft 365 解決方案與架構中心</span><span class="sxs-lookup"><span data-stu-id="b522d-172">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

[<span data-ttu-id="b522d-173">Microsoft 365 的同盟身分識別</span><span class="sxs-lookup"><span data-stu-id="b522d-173">Federated identity for Microsoft 365</span></span>](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)


