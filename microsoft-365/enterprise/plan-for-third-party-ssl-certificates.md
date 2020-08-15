---
title: 規劃 Microsoft 365 的第三方 SSL 憑證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: 摘要：說明 Exchange 內部部署和混合式 SSO （使用 AD FS、Exchange Online 服務和 Exchange Web 服務）所需的 SSL 憑證。
ms.openlocfilehash: 1738e4c316772d928138adc654372bd0b9efae65
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688504"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a><span data-ttu-id="5d741-103">規劃 Microsoft 365 的第三方 SSL 憑證</span><span class="sxs-lookup"><span data-stu-id="5d741-103">Plan for third-party SSL certificates for Microsoft 365</span></span>

<span data-ttu-id="5d741-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="5d741-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5d741-105">若要加密用戶端與 Microsoft 365 環境之間的通訊，協力廠商安全通訊端層 (SSL) 憑證必須安裝在基礎結構伺服器上。</span><span class="sxs-lookup"><span data-stu-id="5d741-105">To encrypt communications between your clients and the Microsoft 365 environment, third-party Secure Socket Layer (SSL) certificates must be installed on your infrastructure servers.</span></span>

<span data-ttu-id="5d741-106">本文是 [Microsoft 365 的網路規劃和效能調整](https://aka.ms/tune)的一部分。</span><span class="sxs-lookup"><span data-stu-id="5d741-106">This article is part of [Network planning and performance tuning for Microsoft 365](https://aka.ms/tune).</span></span>
   
<span data-ttu-id="5d741-107">下列 Microsoft 365 元件需要憑證：</span><span class="sxs-lookup"><span data-stu-id="5d741-107">Certificates are required for the following Microsoft 365 components:</span></span>
  
- <span data-ttu-id="5d741-108">Exchange 內部部署</span><span class="sxs-lookup"><span data-stu-id="5d741-108">Exchange on-premises</span></span>
    
- <span data-ttu-id="5d741-109">適用于 Active Directory Federation Services (AD FS) 同盟伺服器和 AD FS 同盟伺服器 proxy 的單一登入 (SSO)  () </span><span class="sxs-lookup"><span data-stu-id="5d741-109">Single sign-on (SSO) (for both the Active Directory Federation Services (AD FS) federation servers and AD FS federation server proxies)</span></span>
    
- <span data-ttu-id="5d741-110">Exchange Online 服務，例如自動探索、Outlook 無所不在和 Exchange Web 服務</span><span class="sxs-lookup"><span data-stu-id="5d741-110">Exchange Online services, such as Autodiscover, Outlook Anywhere, and Exchange Web Services</span></span>
    
- <span data-ttu-id="5d741-111">Exchange 混合式伺服器</span><span class="sxs-lookup"><span data-stu-id="5d741-111">Exchange hybrid server</span></span>
    
## <a name="certificates-for-exchange-on-premises"></a><span data-ttu-id="5d741-112">Exchange On-Premises 的憑證</span><span class="sxs-lookup"><span data-stu-id="5d741-112">Certificates for Exchange On-Premises</span></span>

<span data-ttu-id="5d741-113">若要瞭解如何使用數位憑證來進行內部部署 Exchange 組織與 Exchange Online 之間的通訊，請參閱 TechNet 文章 [瞭解憑證需求](https://go.microsoft.com/fwlink/p/?LinkID=243657)。</span><span class="sxs-lookup"><span data-stu-id="5d741-113">For an overview about how to use digital certificates to make the communication between the on-premises Exchange organization and Exchange Online secure, see the TechNet article [Understanding Certificate Requirements](https://go.microsoft.com/fwlink/p/?LinkID=243657).</span></span>
  
## <a name="certificates-for-single-sign-on"></a><span data-ttu-id="5d741-114">單一 Sign-On 的憑證</span><span class="sxs-lookup"><span data-stu-id="5d741-114">Certificates for Single Sign-On</span></span>

<span data-ttu-id="5d741-115">若要為您的使用者提供增強的安全性的簡化單一登入體驗，同盟伺服器或同盟伺服器 proxy 上必須要有下表所示的憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-115">To provide your users with a simplified single sign-on experience that includes robust security, the certificates shown in the following table are required on either the federation servers or the federation server proxies.</span></span> <span data-ttu-id="5d741-116">下表著重于 Active Directory Federation Services (AD FS) 上，我們也提供 [使用協力廠商身分識別提供者](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5d741-116">The table below focuses on Active Directory Federation Services (AD FS), we also have more information on [using third-party identity providers](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).</span></span>
  
| <span data-ttu-id="5d741-117">憑證類型</span><span class="sxs-lookup"><span data-stu-id="5d741-117">Certificate Type</span></span> | <span data-ttu-id="5d741-118">描述</span><span class="sxs-lookup"><span data-stu-id="5d741-118">Description</span></span> | <span data-ttu-id="5d741-119">部署之前所需注意的事項</span><span class="sxs-lookup"><span data-stu-id="5d741-119">What you need to know before you deploy</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="5d741-120">\*\*SSL 憑證 (也稱為伺服器驗證憑證) \*\*</span><span class="sxs-lookup"><span data-stu-id="5d741-120">**SSL certificate (also called a server authentication certificate)**</span></span> <br/> |<span data-ttu-id="5d741-121">這是一個標準 SSL 憑證，用來保護同盟伺服器、用戶端與同盟伺服器 proxy 電腦之間的通訊安全。</span><span class="sxs-lookup"><span data-stu-id="5d741-121">This is a standard SSL certificate that is used to make communications between federation servers, clients, and federation server proxy computers secure.</span></span>  <br/> |<span data-ttu-id="5d741-122">AD FS 需要 SSL 憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-122">AD FS requires an SSL certificate.</span></span> <span data-ttu-id="5d741-123">根據預設，AD FS 使用網際網路資訊服務 (IIS) 中設定之預設網站的 SSL 憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-123">By default, AD FS uses the SSL certificate that is configured for the default website in Internet Information Services (IIS).</span></span>  <br/> <span data-ttu-id="5d741-124">此 SSL 憑證的主體名稱是用來判斷您部署之每個 AD FS 實例的同盟服務 (FS) 名稱。</span><span class="sxs-lookup"><span data-stu-id="5d741-124">The subject name of this SSL certificate is used to determine the Federation Service (FS) name for each instance of AD FS that you deploy.</span></span> <span data-ttu-id="5d741-125">請考慮為任何新的憑證授權單位單位的主體名稱選擇 (CA) 頒發的憑證，該憑證最能代表您公司或組織的 Microsoft 365 的名稱。</span><span class="sxs-lookup"><span data-stu-id="5d741-125">Consider choosing a subject name for any new certification authority (CA)-issued certificates that best represents the name of your company or organization to Microsoft 365.</span></span> <span data-ttu-id="5d741-126">此名稱必須是透過網際網路路由傳送。</span><span class="sxs-lookup"><span data-stu-id="5d741-126">This name must be Internet-routable.</span></span>  <br/><span data-ttu-id="5d741-127">**警告：** AD FS 要求此 SSL 憑證沒有無點 (短名稱) 主體名稱。</span><span class="sxs-lookup"><span data-stu-id="5d741-127">**Caution:** AD FS requires that this SSL certificate have no dotless (short-name) subject name.</span></span>          <br/> <span data-ttu-id="5d741-128">**建議：** 由於此憑證必須由 AD FS 的用戶端信任，因此建議您使用公用 (協力廠商) CA 所發出的 SSL 憑證，或是從屬於公開根信任的 CA，使用此憑證;例如，VeriSign 或 Thawte。</span><span class="sxs-lookup"><span data-stu-id="5d741-128">**Recommendation:** Because this certificate must be trusted by clients of AD FS, we recommend that you use an SSL certificate issued by a public (third-party) CA or by a CA that is subordinate to a publicly trusted root; for example, VeriSign or Thawte.</span></span>  <br/> |
|<span data-ttu-id="5d741-129">**權杖簽署憑證**</span><span class="sxs-lookup"><span data-stu-id="5d741-129">**Token-signing certificate**</span></span> <br/> |<span data-ttu-id="5d741-130">這是標準的 x.509 憑證，用來安全簽署同盟伺服器所發行的所有權杖，以及 Microsoft 365 接受和驗證的所有權杖。</span><span class="sxs-lookup"><span data-stu-id="5d741-130">This is a standard X.509 certificate that's used for securely signing all tokens that the federation server issues and that Microsoft 365 accepts and validates.</span></span>  <br/> |<span data-ttu-id="5d741-131">權杖簽章憑證必須包含一個私密金鑰，該私密金鑰會連結至 FS 中的信任的根。</span><span class="sxs-lookup"><span data-stu-id="5d741-131">The token-signing certificate must contain a private key that chains to a trusted root in the FS.</span></span> <span data-ttu-id="5d741-132">AD FS 預設會建立自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-132">By default, AD FS creates a self-signed certificate.</span></span> <span data-ttu-id="5d741-133">不過，您可以根據組織的需求，使用 [AD FS 管理] 嵌入式管理單元，將此憑證變更為 CA 發佈的憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-133">However, depending on the needs of your organization, you can change this certificate to a CA-issued certificate by using the AD FS management snap-in.</span></span>  <br/><span data-ttu-id="5d741-134">**警告：** 權杖簽署憑證對 FS 穩定性很重要。</span><span class="sxs-lookup"><span data-stu-id="5d741-134">**Caution:** The token-signing certificate is critical to the stability of the FS.</span></span> <span data-ttu-id="5d741-135">如果變更了憑證，則必須通知 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5d741-135">If the certificate is changed, Microsoft 365 must be notified of the change.</span></span> <span data-ttu-id="5d741-136">若未提供通知，使用者就無法登入其 Microsoft 365 服務產品。</span><span class="sxs-lookup"><span data-stu-id="5d741-136">If notification is not provided, users can't sign in to their Microsoft 365 service offerings.</span></span><br/><span data-ttu-id="5d741-137">**建議：** 建議您使用 AD FS 所產生的自我簽署權杖簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-137">**Recommendation:** We recommend that you use the self-signed token-signing certificate that is generated by AD FS.</span></span> <span data-ttu-id="5d741-138">這樣一來，它預設會為您管理此憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-138">By doing so, it manages this certificate for you by default.</span></span> <span data-ttu-id="5d741-139">例如，當此憑證即將到期時，AD FS 將會產生新的自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-139">For example, when this certificate is about to expire, AD FS will generate a new self-signed certificate.</span></span>  <br/> |
   
<span data-ttu-id="5d741-140">同盟伺服器 proxy 需要下表所述的憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-140">Federation server proxies require the certificate that is described in the following table.</span></span>
  
| <span data-ttu-id="5d741-141">憑證類型</span><span class="sxs-lookup"><span data-stu-id="5d741-141">Certificate Type</span></span> | <span data-ttu-id="5d741-142">描述</span><span class="sxs-lookup"><span data-stu-id="5d741-142">Description</span></span> | <span data-ttu-id="5d741-143">部署之前所需注意的事項</span><span class="sxs-lookup"><span data-stu-id="5d741-143">What you need to know before you deploy</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="5d741-144">SSL 憑證</span><span class="sxs-lookup"><span data-stu-id="5d741-144">SSL certificate</span></span>  <br/> |<span data-ttu-id="5d741-145">這是一個標準 SSL 憑證，用來保護同盟伺服器、同盟伺服器 proxy 和網際網路用戶端電腦之間的通訊安全。</span><span class="sxs-lookup"><span data-stu-id="5d741-145">This is a standard SSL certificate that is used for securing communications between a federation server, a federation server proxy, and Internet client computers.</span></span>  <br/> |<span data-ttu-id="5d741-146">您必須先將此 SSL 憑證系結至 IIS 中的預設網站，才能成功執行 AD FS 同盟伺服器 Proxy 設定向導。</span><span class="sxs-lookup"><span data-stu-id="5d741-146">This SSL certificate must be bound to the default website in IIS before you can successfully run the AD FS Federation Server Proxy Configuration wizard.</span></span>  <br/> <span data-ttu-id="5d741-147">此憑證必須具有與公司網路中同盟伺服器上設定之 SSL 憑證相同的主體名稱。</span><span class="sxs-lookup"><span data-stu-id="5d741-147">This certificate must have the same subject name as the SSL certificate that was configured on the federation server in the corporate network.</span></span>  <br/> <span data-ttu-id="5d741-148">**建議：** 建議您使用此同盟伺服器 proxy 所連接的同盟伺服器上設定的相同伺服器驗證憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-148">**Recommendation:** We recommend that you use the same server authentication certificate that is configured on the federation server that this federation server proxy connects to.</span></span>  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a><span data-ttu-id="5d741-149">自動探索、Outlook Anywhere 和 Active Directory 同步處理的憑證</span><span class="sxs-lookup"><span data-stu-id="5d741-149">Certificates for Autodiscover, Outlook Anywhere, and Active Directory Synchronization</span></span>

<span data-ttu-id="5d741-150">您的對外 Exchange 2013、Exchange 2010、Exchange 2007 和 Exchange 2003 Client Access server (CASs) 需要協力廠商 SSL 憑證，以進行自動探索、Outlook 無所不在和 Active Directory 同步處理服務的安全連線。</span><span class="sxs-lookup"><span data-stu-id="5d741-150">Your external-facing Exchange 2013, Exchange 2010, Exchange 2007, and Exchange 2003 Client Access servers (CASs) require a third-party SSL certificate for secure connections for Autodiscover, Outlook Anywhere, and Active Directory synchronization services.</span></span> <span data-ttu-id="5d741-151">您可能已在內部部署環境中安裝此憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-151">You may already have this certificate installed in your on-premises environment.</span></span>
  
## <a name="certificate-for-an-exchange-hybrid-server"></a><span data-ttu-id="5d741-152">Exchange 混合式伺服器的憑證</span><span class="sxs-lookup"><span data-stu-id="5d741-152">Certificate for an Exchange Hybrid Server</span></span>

<span data-ttu-id="5d741-153">您的外部 Exchange 混合伺服器或伺服器需要協力廠商 SSL 憑證，以與 Exchange Online 服務進行安全連線。</span><span class="sxs-lookup"><span data-stu-id="5d741-153">Your external-facing Exchange hybrid server or servers require a third-party SSL certificate for secure connectivity with the Exchange Online service.</span></span> <span data-ttu-id="5d741-154">您必須從協力廠商 SSL 提供者取得此憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-154">You need to get this certificate from your third-party SSL provider.</span></span>
  
## <a name="microsoft-365-certificate-chains"></a><span data-ttu-id="5d741-155">Microsoft 365 憑證鏈</span><span class="sxs-lookup"><span data-stu-id="5d741-155">Microsoft 365 Certificate Chains</span></span>

<span data-ttu-id="5d741-156">本文說明您在基礎結構上安裝時可能需要的憑證。</span><span class="sxs-lookup"><span data-stu-id="5d741-156">This article describes the certificates you may need to install on your infrastructure.</span></span> <span data-ttu-id="5d741-157">如需 Microsoft 365 伺服器上安裝之憑證的詳細資訊，請參閱 [microsoft 365 憑證鏈](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)。</span><span class="sxs-lookup"><span data-stu-id="5d741-157">For more information on the certificates installed on our Microsoft 365 servers, see [Microsoft 365 Certificate Chains](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d741-158">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5d741-158">See also</span></span>

[<span data-ttu-id="5d741-159">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="5d741-159">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
