---
title: Microsoft 受管理電腦的準備內部部署資源的存取
description: 若要確保 Azure AD 可以與彼此內部部署的重要步驟 AD 以提供驗證
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0f9cbe6712b8d16f435cfdf5fd84875656fa9c2e
ms.sourcegitcommit: ef589025820ddf6edb5f454826b1c12c9bcb8e49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2019
ms.locfileid: "31824463"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="a3340-104">Microsoft 受管理電腦的準備內部部署資源的存取</span><span class="sxs-lookup"><span data-stu-id="a3340-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="a3340-105">在 Microsoft 受管理的電腦，裝置會自動加入至 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="a3340-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory.</span></span> <span data-ttu-id="a3340-106">這表示，如果您使用內部部署 Active Directory，您必須檢查以確保裝置加入 Azure AD 可以與您在內部部署 Active Directory 通訊的一些事項。</span><span class="sxs-lookup"><span data-stu-id="a3340-106">This means that if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="a3340-107">*混合式*Microsoft 受管理的電腦不支援 azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="a3340-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="a3340-108">Azure Active Directory 可讓使用者利用的單一登入 (SSO)，這表示它們通常不需要提供認證，每次他們想要執行某些動作。</span><span class="sxs-lookup"><span data-stu-id="a3340-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they want to do something.</span></span> <span data-ttu-id="a3340-109">如果您是完全新增至 Azure Active Directory，請參閱[How to： 規劃您的 Azure AD 加入實作](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)-不過，您參考 Azure Active Directory 文件，請記住，*混合式*Azure AD 加入不支援 microsoft受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="a3340-109">If you're completely new to Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)--however, as you reference Azure Active Directory documentation, keep in mind that *hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>


<span data-ttu-id="a3340-110">本主題說明您需要檢查以確保應用程式和其他資源，取決於本機 Active Directory 連線會搭配順暢 Microsoft 受管理電腦的事項。</span><span class="sxs-lookup"><span data-stu-id="a3340-110">This topic explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="a3340-111">若要能夠在 Azure Active Directory 中註冊裝置，以及 （所需的 Microsoft 受管理的電腦） 的 Intune 中註冊的使用者，遵循的步驟中[設定您的裝置設定](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings)再繼續進行本主題的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="a3340-111">For users to be able to register devices in Azure Active Directory and enroll in Intune (required for Microsoft Managed Desktop), follow the steps in [Configure your device settings](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) before proceeding with the rest of this topic.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="a3340-112">單一登入內部部署資源</span><span class="sxs-lookup"><span data-stu-id="a3340-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="a3340-113">單一登入 (SSO) 使用 UPN 或密碼 （預設的方法） 裝置已應該依預設會運作。</span><span class="sxs-lookup"><span data-stu-id="a3340-113">Single Sign-On (SSO) for your devices by using UPN or passwords (the default method) should already work by default.</span></span> <span data-ttu-id="a3340-114">但您也可以使用 Windows Hello 商務，需要一些額外設定步驟。</span><span class="sxs-lookup"><span data-stu-id="a3340-114">But you can also use Windows Hello for Business, which requires some extra setup steps.</span></span> <span data-ttu-id="a3340-115">如需 SSO 的背景資訊，請參閱 <<c0>如何在內部資源的 SSO 加入 Azure AD 裝置上運作。</span><span class="sxs-lookup"><span data-stu-id="a3340-115">For background information about SSO, see [How SSO to on-premises resources works on Azure AD joined devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


### <a name="single-sign-on-by-using-upn-and-passwords"></a><span data-ttu-id="a3340-116">單一登入使用 UPN 和密碼</span><span class="sxs-lookup"><span data-stu-id="a3340-116">Single Sign-On by using UPN and passwords</span></span>

<span data-ttu-id="a3340-117">沒有特殊設定，則需要為您的使用者 UPN] 和 [密碼-來驗證您透過這預設 azure。</span><span class="sxs-lookup"><span data-stu-id="a3340-117">No special setup is required for your users to authenticate by UPN and password--you get this by default from Azure.</span></span> <span data-ttu-id="a3340-118">不過，若要確保這將會運作，您應該仔細檢查下列：</span><span class="sxs-lookup"><span data-stu-id="a3340-118">However, to make sure this will work, you should double-check the following:</span></span>

- <span data-ttu-id="a3340-119">確認 [Azure Active Directory (AAD) 連線已設定與內部部署 Active Directory 伺服器執行 Windows Server 2008 R2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="a3340-119">Confirm that Azure Active Directory (AAD) Connect is set up with an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="a3340-120">AAD 連線執行支援的版本，且設為同步處理與 Azure AD 這三個主要屬性：</span><span class="sxs-lookup"><span data-stu-id="a3340-120">AAD Connect is running a supported version and is set to sync these three key attributes with Azure AD:</span></span> 
    - <span data-ttu-id="a3340-121">使用者所在的內部部署 Active Directory 中存在的 DNS 網域名稱</span><span class="sxs-lookup"><span data-stu-id="a3340-121">DNS domain name where the user is present in your on-premises Active Directory</span></span>
    - <span data-ttu-id="a3340-122">使用者所在的內部部署 Active Directory 中存在的 NetBIOS 網域名稱</span><span class="sxs-lookup"><span data-stu-id="a3340-122">NetBIOS domain name where the user is present in your on-premises Active Directory</span></span>
    - <span data-ttu-id="a3340-123">SAM 帳戶名稱的使用者</span><span class="sxs-lookup"><span data-stu-id="a3340-123">SAM account name of the user</span></span>


### <a name="sso-by-using-windows-hello-for-business"></a><span data-ttu-id="a3340-124">使用 Windows Hello 企業的 SSO</span><span class="sxs-lookup"><span data-stu-id="a3340-124">SSO by using Windows Hello for Business</span></span>

<span data-ttu-id="a3340-125">或者，您可以提供您的使用者快速、 passwordless 體驗採用 Windows Hello 企業版。</span><span class="sxs-lookup"><span data-stu-id="a3340-125">Alternately, you can offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="a3340-126">若要設定此案例，請造訪[設定 Azure AD 加入的內部部署單一登入使用 Windows Hello 企業版的裝置](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)檢查的需求，並遵循此處所提供的步驟。</span><span class="sxs-lookup"><span data-stu-id="a3340-126">To set this up, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="a3340-127">應用程式和使用驗證的資源</span><span class="sxs-lookup"><span data-stu-id="a3340-127">Apps and resources that use authentication</span></span>

<span data-ttu-id="a3340-128">Azure 內容設定的完整指南上設定應用程式，以使用 Azure Active Directory 中參照[的應用程式和資源的了解考量](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources)。</span><span class="sxs-lookup"><span data-stu-id="a3340-128">Refer to [Understand considerations for applications and resources](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="a3340-129">摘要： 中</span><span class="sxs-lookup"><span data-stu-id="a3340-129">In summary:</span></span>


- <span data-ttu-id="a3340-130">如果您使用**雲端式應用程式**，例如新增至 Azure AD 應用程式庫中，大部分不需要任何進一步的準備來搭配 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="a3340-130">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="a3340-131">不過，任何未使用 Web 帳戶管理員 (WAM) 的 Win32 應用程式 {確認此縮寫} 仍可能會提示使用者進行驗證。</span><span class="sxs-lookup"><span data-stu-id="a3340-131">However, any Win32 apps that don't use Web Account Manager (WAM) {verify this acronym} might still prompt users for authentication.</span></span>

- <span data-ttu-id="a3340-132">是**裝載內部部署**的應用程式，請務必將這些應用程式新增至您的瀏覽器中的信任的網站清單。</span><span class="sxs-lookup"><span data-stu-id="a3340-132">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="a3340-133">這會啟用 Windows 驗證，才能順利地，而不提示輸入認證的使用者。</span><span class="sxs-lookup"><span data-stu-id="a3340-133">This will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span>

- <span data-ttu-id="a3340-134">如果您使用 Active Directory 同盟服務，請遵循步驟[驗證和管理單一登入與 AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="a3340-134">If you are using Active Directory Federated Services, follow the steps in [Verify and manage single sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="a3340-135">會**在內部部署和使用較舊的通訊協定**的應用程式，沒有額外的設定是必要的只要裝置擁有存取權的內部部署網域控制站。</span><span class="sxs-lookup"><span data-stu-id="a3340-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller.</span></span> <span data-ttu-id="a3340-136">不過，若要提供安全存取這些應用程式，您應該部署 Azure AD 應用程式 Proxy。</span><span class="sxs-lookup"><span data-stu-id="a3340-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="a3340-137">如需詳細資訊，請參閱[遠端存取內部部署應用程式，透過 Azure Active Directory 的應用程式 Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。</span><span class="sxs-lookup"><span data-stu-id="a3340-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="a3340-138">執行**內部部署和依賴機器驗證**的應用程式不支援，所以您應該考慮取代這些較新版本。</span><span class="sxs-lookup"><span data-stu-id="a3340-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing these with newer versions.</span></span>

## <a name="network-shares-that-use-authentication"></a><span data-ttu-id="a3340-139">使用驗證的網路共用</span><span class="sxs-lookup"><span data-stu-id="a3340-139">Network shares that use authentication</span></span>

<span data-ttu-id="a3340-140">沒有額外的設定有使用者存取網路共用，只要裝置透過 UNC 路徑可以存取內部部署網域控制站。</span><span class="sxs-lookup"><span data-stu-id="a3340-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

## <a name="printers"></a><span data-ttu-id="a3340-141">印表機</span><span class="sxs-lookup"><span data-stu-id="a3340-141">Printers</span></span>

<span data-ttu-id="a3340-142">雖然印表機無法自動探索雲端唯一環境中，您的使用者也可以直接將它們新增使用印表機的 UNC 路徑。</span><span class="sxs-lookup"><span data-stu-id="a3340-142">While printers can't be automatically discovered in a cloud only environment, your users can also use the printers’ UNC path to directly add them.</span></span>

<!--add fuller material on printers when available-->