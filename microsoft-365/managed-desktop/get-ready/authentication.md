---
title: Microsoft 受管理電腦的準備內部部署資源的存取
description: 若要確保 Azure AD 可以與彼此內部部署的重要步驟 AD 以提供驗證
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c4ebe0c7ad3d1e197cf90cc975366df61d3b0cb5
ms.sourcegitcommit: db52a11eb192a28dbec827c565e36ad4a81d8e3f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901207"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="a2228-104">Microsoft 受管理電腦的準備內部部署資源的存取</span><span class="sxs-lookup"><span data-stu-id="a2228-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="a2228-105">在 Microsoft 受管理的電腦，裝置會自動加入至 Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="a2228-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="a2228-106">這表示，如果您使用內部部署 Active Directory，您必須檢查以確保裝置加入 Azure AD 可以與您在內部部署 Active Directory 通訊的一些事項。</span><span class="sxs-lookup"><span data-stu-id="a2228-106">This means that if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="a2228-107">*混合式*Microsoft 受管理的電腦不支援 azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="a2228-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="a2228-108">Azure Active Directory 可讓您利用的單一登入 (SSO)，這表示它們通常不需要提供認證，每次使用資源的使用者。</span><span class="sxs-lookup"><span data-stu-id="a2228-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they use resources.</span></span>

<span data-ttu-id="a2228-109">如需加入 Azure Active Directory 資訊，請參閱 < <b0>How to： 規劃您的 Azure AD 加入實作</b0>。</span><span class="sxs-lookup"><span data-stu-id="a2228-109">For information about joining Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="a2228-110">加入到 Azure AD 裝置上背景資訊關於單一登入 (SSO)，請參閱[如何在內部資源的 SSO 加入 Azure AD 裝置上運作](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)。</span><span class="sxs-lookup"><span data-stu-id="a2228-110">For background information about Single Sign-On (SSO) on devices joined to Azure AD, see [How SSO to on-premises resources works on Azure AD joined devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


<span data-ttu-id="a2228-111">本主題說明您需要檢查以確保應用程式和其他資源，取決於本機 Active Directory 連線會搭配順暢 Microsoft 受管理電腦的事項。</span><span class="sxs-lookup"><span data-stu-id="a2228-111">This topic explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="a2228-112">單一登入內部部署資源</span><span class="sxs-lookup"><span data-stu-id="a2228-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="a2228-113">Microsoft 受管理的電腦裝置上的預設會啟用單一登入 (SSO) 使用 UPN 和密碼。</span><span class="sxs-lookup"><span data-stu-id="a2228-113">Single Sign-On (SSO) by using UPN and password is enabled by default on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="a2228-114">但您的使用者也可以使用 Windows Hello 商務，需要一些額外設定步驟。</span><span class="sxs-lookup"><span data-stu-id="a2228-114">But your users can also use Windows Hello for Business, which requires some extra setup steps.</span></span> 

### <a name="single-sign-on-by-using-upn-and-password"></a><span data-ttu-id="a2228-115">單一登入使用 UPN 和密碼</span><span class="sxs-lookup"><span data-stu-id="a2228-115">Single Sign-On by using UPN and password</span></span>

<span data-ttu-id="a2228-116">在大多數的組織，您的使用者能夠使用 SSO 進行驗證的 UPN 與 Microsoft 受管理的電腦裝置上的密碼。</span><span class="sxs-lookup"><span data-stu-id="a2228-116">In most organizations, your users will be able to use SSO to authenticate by UPN and password on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="a2228-117">不過，若要確保這將會運作，您應該仔細檢查下列：</span><span class="sxs-lookup"><span data-stu-id="a2228-117">However, to make sure this will work, you should double-check the following:</span></span>

- <span data-ttu-id="a2228-118">請先確認 Azure AD Connect 設定，並使用內部 Active Directory 伺服器上執行 Windows Server 2008 R2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="a2228-118">Confirm that Azure AD Connect is set up and uses an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="a2228-119">確認 Azure AD Connect 執行支援的版本，且設為同步處理與 Azure AD 這三個屬性：</span><span class="sxs-lookup"><span data-stu-id="a2228-119">Confirm that Azure AD Connect is running a supported version and is set to sync these three attributes with Azure AD:</span></span> 
    - <span data-ttu-id="a2228-120">DNS 網域名稱 （使用者的所在位置） 的內部部署 Active directory</span><span class="sxs-lookup"><span data-stu-id="a2228-120">DNS domain name of the on-premises Active Directory (where the end-users are located)</span></span>
    - <span data-ttu-id="a2228-121">NetBIOS （使用者的所在位置） 您內部部署 Active directory</span><span class="sxs-lookup"><span data-stu-id="a2228-121">NetBIOS of your on-premises Active Directory (where the end-users are located)</span></span>
    - <span data-ttu-id="a2228-122">SAM 帳戶名稱的使用者</span><span class="sxs-lookup"><span data-stu-id="a2228-122">SAM account name of the user</span></span>


### <a name="single-sign-on-by-using-windows-hello-for-business"></a><span data-ttu-id="a2228-123">單一登入藉由使用 Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="a2228-123">Single Sign-On by using Windows Hello for Business</span></span>

<span data-ttu-id="a2228-124">Microsoft 受管理的電腦裝置也可讓使用者快速、 passwordless 體驗採用 Windows Hello 企業版。</span><span class="sxs-lookup"><span data-stu-id="a2228-124">Microsoft Managed Desktop devices also offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="a2228-125">若要確保 Windows Hello 的商務正常沒有您不必提供各自的 UPN 與密碼的使用者，請造訪[設定 Azure AD 加入的內部部署單一登入使用 Windows Hello 企業版的裝置](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)檢查的需求，然後選取依照此處所提供的步驟。</span><span class="sxs-lookup"><span data-stu-id="a2228-125">To ensure Windows Hello for Business will work without your users having to provide respective UPN and password, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="a2228-126">應用程式和使用驗證的資源</span><span class="sxs-lookup"><span data-stu-id="a2228-126">Apps and resources that use authentication</span></span>

<span data-ttu-id="a2228-127">Azure 內容設定的完整指南上設定應用程式，以使用 Azure Active Directory 中參照[的應用程式和資源的了解考量](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources)。</span><span class="sxs-lookup"><span data-stu-id="a2228-127">Refer to [Understand considerations for applications and resources](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="a2228-128">摘要： 中</span><span class="sxs-lookup"><span data-stu-id="a2228-128">In summary:</span></span>


- <span data-ttu-id="a2228-129">如果您使用**雲端式應用程式**，例如新增至 Azure AD 應用程式庫中，大部分不需要任何進一步的準備來搭配 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="a2228-129">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="a2228-130">不過，任何未使用 Web 帳戶管理員 (WAM) 的 Win32 應用程式可能仍提示使用者進行驗證。</span><span class="sxs-lookup"><span data-stu-id="a2228-130">However, any Win32 apps that don't use Web Account Manager (WAM) might still prompt users for authentication.</span></span>

- <span data-ttu-id="a2228-131">是**裝載內部部署**的應用程式，請務必將這些應用程式新增至您的瀏覽器中的信任的網站清單。</span><span class="sxs-lookup"><span data-stu-id="a2228-131">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="a2228-132">這會啟用 Windows 驗證，才能順利地，而不提示輸入認證的使用者。</span><span class="sxs-lookup"><span data-stu-id="a2228-132">This will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span> <span data-ttu-id="a2228-133">若要這麼做，請參閱[組態設定參照](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)中的[信任的網站](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites)。</span><span class="sxs-lookup"><span data-stu-id="a2228-133">To do this, refer to [Trusted sites](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) in the [Configurable settings reference](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).</span></span>

- <span data-ttu-id="a2228-134">如果您使用 Active Directory 同盟服務，請檢查使用中的步驟，啟用 SSO[驗證和管理單一登入與 AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="a2228-134">If you are using Active Directory Federated Services, check that SSO is enabled by using the steps in [Verify and manage single sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="a2228-135">會**在內部部署和使用較舊的通訊協定**的應用程式，沒有額外的設定是必要的只要裝置擁有存取權來驗證內部部署網域控制站。</span><span class="sxs-lookup"><span data-stu-id="a2228-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller to authenticate.</span></span> <span data-ttu-id="a2228-136">不過，若要提供安全存取這些應用程式，您應該部署 Azure AD 應用程式 Proxy。</span><span class="sxs-lookup"><span data-stu-id="a2228-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="a2228-137">如需詳細資訊，請參閱[遠端存取內部部署應用程式，透過 Azure Active Directory 的應用程式 Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。</span><span class="sxs-lookup"><span data-stu-id="a2228-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="a2228-138">執行**內部部署和依賴機器驗證**的應用程式不支援，所以您應該考慮取代這些較新版本。</span><span class="sxs-lookup"><span data-stu-id="a2228-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing these with newer versions.</span></span>

### <a name="network-shares-that-use-authentication"></a><span data-ttu-id="a2228-139">使用驗證的網路共用</span><span class="sxs-lookup"><span data-stu-id="a2228-139">Network shares that use authentication</span></span>

<span data-ttu-id="a2228-140">沒有額外的設定有使用者存取網路共用，只要裝置透過 UNC 路徑可以存取內部部署網域控制站。</span><span class="sxs-lookup"><span data-stu-id="a2228-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

### <a name="printers"></a><span data-ttu-id="a2228-141">印表機</span><span class="sxs-lookup"><span data-stu-id="a2228-141">Printers</span></span>

<span data-ttu-id="a2228-142">Microsoft 受管理的電腦裝置無法連線至已發佈至您的內部部署 Active Directory 中，除非您已設定[混合式雲端列印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)的印表機。</span><span class="sxs-lookup"><span data-stu-id="a2228-142">Microsoft Managed Desktop devices cannot connect to printers that are published to your on-premises Active Directory unless you have configured [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>

<span data-ttu-id="a2228-143">雖然印表機無法自動探索雲端唯一環境中，您的使用者可以使用內部部署印表機所使用的印表機路徑或印表機佇列路徑，，只要裝置擁有存取權的內部部署網域控制站。</span><span class="sxs-lookup"><span data-stu-id="a2228-143">While printers can't be automatically discovered in a cloud only environment, your users can use on-premises printers by using the printer path or printer queue path, as long as the devices have access to an on-premises domain controller.</span></span>

<!--add fuller material on printers when available-->
