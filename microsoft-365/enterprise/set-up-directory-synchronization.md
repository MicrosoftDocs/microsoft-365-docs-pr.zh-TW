---
title: 設定 Microsoft 365 的目錄同步處理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/15/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: 瞭解如何在 Microsoft 365 和您的內部部署 Active Directory 之間設定目錄同步處理。
ms.openlocfilehash: 3a846a6c558f221c1869dce6da27e3d34680f75d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688313"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="a2d7b-103">設定 Microsoft 365 的目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="a2d7b-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="a2d7b-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="a2d7b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a2d7b-105">Microsoft 365 使用 Azure Active Directory (Azure AD) 租使用者來儲存和管理身分驗證的身分識別，以及存取雲端架構資源的許可權。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="a2d7b-106">如果您有內部部署 Active Directory 網域服務 (AD DS) ，您可以使用 Microsoft 365 訂閱的 Azure AD 租使用者來同步處理您的 AD DS 使用者帳戶、群組和連絡人。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-106">If you have an on-premises Active Directory Domain Services (AD DS), you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="a2d7b-107">這是 Microsoft 365 的混合式身分識別。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="a2d7b-108">以下是其元件。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-108">Here are its components.</span></span>

![Microsoft 365 的目錄同步處理元件](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="a2d7b-110">Azure AD Connect 會在內部部署伺服器上執行，並與 Azure AD 租使用者同步處理 AD DS。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="a2d7b-111">除了目錄同步處理之外，您還可以指定下列驗證選項：</span><span class="sxs-lookup"><span data-stu-id="a2d7b-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="a2d7b-112">密碼雜湊同步處理 (PHS) </span><span class="sxs-lookup"><span data-stu-id="a2d7b-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="a2d7b-113">Azure AD 會自行執行驗證。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="a2d7b-114">傳遞驗證 (PTA)</span><span class="sxs-lookup"><span data-stu-id="a2d7b-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="a2d7b-115">Azure AD 具有 AD DS 執行驗證。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="a2d7b-116">同盟驗證</span><span class="sxs-lookup"><span data-stu-id="a2d7b-116">Federated authentication</span></span>

  <span data-ttu-id="a2d7b-117">Azure AD 重新導向要求驗證的用戶端電腦，以與另一個身分識別提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-117">Azure AD redirects the client computer requesting authentication to contact another identity provider.</span></span>

<span data-ttu-id="a2d7b-118">如需詳細資訊，請參閱 [混合式識別碼](plan-for-directory-synchronization.md) 。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="a2d7b-119">1. 檢查 Azure AD Connect 的先決條件</span><span class="sxs-lookup"><span data-stu-id="a2d7b-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="a2d7b-120">您可以使用 Microsoft 365 訂閱取得免費的 Azure AD 訂閱。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="a2d7b-121">當您設定目錄同步處理時，您會在其中一個內部部署伺服器上安裝 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="a2d7b-122">若為 Microsoft 365，您將需要：</span><span class="sxs-lookup"><span data-stu-id="a2d7b-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="a2d7b-123">驗證您的內部部署網域。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-123">Verify your on-premises domain.</span></span> <span data-ttu-id="a2d7b-124">Azure AD Connect 嚮導會引導您完成此步驟。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="a2d7b-125">取得您的 Microsoft 365 租使用者和 AD DS 之系統管理員帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="a2d7b-126">針對您在其上安裝 Azure AD Connect 的內部部署伺服器，您需要：</span><span class="sxs-lookup"><span data-stu-id="a2d7b-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="a2d7b-127">**伺服器作業系統**</span><span class="sxs-lookup"><span data-stu-id="a2d7b-127">**Server OS**</span></span>|<span data-ttu-id="a2d7b-128">**其他軟體**</span><span class="sxs-lookup"><span data-stu-id="a2d7b-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a2d7b-129">Windows Server 2012 R2 和更新版本</span><span class="sxs-lookup"><span data-stu-id="a2d7b-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="a2d7b-130">-預設會安裝 PowerShell，不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="a2d7b-131">-透過 Windows Update 提供 Net 4.5.1 和更新版本。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="a2d7b-132">請確認您已在 [控制台] 中安裝最新的 Windows Server 更新。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="a2d7b-133">Windows Server 2008 R2 Service Pack 1 (SP1) \* \* 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a2d7b-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="a2d7b-134">-Windows Management Framework 4.0 提供 PowerShell 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="a2d7b-135">在 [Microsoft 下載中心](https://go.microsoft.com/fwlink/p/?LinkId=717996)搜尋。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="a2d7b-136">-您可以在 [Microsoft 下載中心](https://go.microsoft.com/fwlink/p/?LinkId=717996)取得 .net 4.5.1 和更新版本。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="a2d7b-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="a2d7b-137">Windows Server 2008</span></span> | <span data-ttu-id="a2d7b-138">-您可以在 [Microsoft 下載中心](https://go.microsoft.com/fwlink/p/?LinkId=717996)上使用 Windows Management Framework 3.0，提供最新支援的 PowerShell 版本。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="a2d7b-139">-您可以在 [Microsoft 下載中心](https://go.microsoft.com/fwlink/p/?LinkId=717996)取得 .net 4.5.1 和更新版本。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="a2d7b-140">請參閱 [Azure Active Directory connect 的必要條件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) ，以取得硬體、軟體、帳戶與許可權需求、SSL 憑證需求，以及 Azure AD Connect 的物件限制等詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-140">See [Prerequisites for Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="a2d7b-141">您也可以查看 Azure AD Connect [版本發行歷程記錄](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) ，以查看每個版本中包含和修正的內容。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-141">You can also review the Azure AD Connect [version release history](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="a2d7b-142">2. 安裝 Azure AD Connect 及設定目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="a2d7b-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="a2d7b-143">開始之前，請確定您已具備下列專案：</span><span class="sxs-lookup"><span data-stu-id="a2d7b-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="a2d7b-144">Microsoft 365 全域管理員的使用者名稱和密碼</span><span class="sxs-lookup"><span data-stu-id="a2d7b-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="a2d7b-145">AD DS 域管理員的使用者名稱和密碼</span><span class="sxs-lookup"><span data-stu-id="a2d7b-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="a2d7b-146">哪種驗證方法 (PHS、PTA、同盟) </span><span class="sxs-lookup"><span data-stu-id="a2d7b-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="a2d7b-147">您是否要使用 [AZURE AD 無縫單一登入 (SSO) ](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)</span><span class="sxs-lookup"><span data-stu-id="a2d7b-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="a2d7b-148">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a2d7b-148">Follow these steps:</span></span>

1. <span data-ttu-id="a2d7b-149">登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) (https://admin.microsoft.com) 並選擇左側導覽中的 [ **使用者**] [作用中 \> **使用者** ]。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="a2d7b-150">在 [作用中 **使用者** ] 頁面上，選擇 [ **其他** (三個點) \> **目錄同步**處理]。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="a2d7b-151">在 [ **Azure Active Directory 準備** ] 頁面上，選取 [ **移至下載中心] 以取得 Azure AD Connect 工具** 連結開始使用。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="a2d7b-152">請遵循 [AZURE Ad connect 和 AZURE Ad Connect Health 安裝藍圖](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="a2d7b-153">3. 完成網域的設定</span><span class="sxs-lookup"><span data-stu-id="a2d7b-153">3. Finish setting up domains</span></span>

<span data-ttu-id="a2d7b-154">當您管理您的 DNS 記錄以完成網域的設定時，請遵循下列步驟，以 [建立 Microsoft 365 的 dns 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 。</span><span class="sxs-lookup"><span data-stu-id="a2d7b-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="a2d7b-155">下一步</span><span class="sxs-lookup"><span data-stu-id="a2d7b-155">Next step</span></span>

[<span data-ttu-id="a2d7b-156">將授權指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="a2d7b-156">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
