---
title: Azure 與 Microsoft 365 整合
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: 如果您想要使用您的內部部署環境進行密碼同步處理或單一登入，請將 Microsoft 365 與 Azure AD 整合。
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905329"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="7e1bb-103">Azure 與 Microsoft 365 整合</span><span class="sxs-lookup"><span data-stu-id="7e1bb-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="7e1bb-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="7e1bb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7e1bb-105">Microsoft 365 會使用 Azure Active Directory (Azure AD) 管理幕後的使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="7e1bb-106">您的 Microsoft 365 訂閱包含免費的 Azure AD 訂閱，因此您可以整合內部部署 Active Directory 網域服務 (AD DS) ，以同步處理使用者帳戶和密碼或設定單一登入。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="7e1bb-107">您也可以購買高級功能，以更好地管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="7e1bb-108">Azure AD 也提供其他功能（如管理整合式應用程式），您可以用來擴充和自訂您的 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="7e1bb-109">您可以在 Microsoft 365 系統管理中心使用 Azure AD 部署顧問，以進行引導安裝和設定體驗 (您必須登入 Microsoft 365) ：</span><span class="sxs-lookup"><span data-stu-id="7e1bb-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="7e1bb-110">Azure AD 連線顧問</span><span class="sxs-lookup"><span data-stu-id="7e1bb-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="7e1bb-111">AD FS 部署顧問</span><span class="sxs-lookup"><span data-stu-id="7e1bb-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="7e1bb-112">Azure AD 安裝指南</span><span class="sxs-lookup"><span data-stu-id="7e1bb-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="7e1bb-113">Azure AD 版本和 Microsoft 365 身分識別管理</span><span class="sxs-lookup"><span data-stu-id="7e1bb-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="7e1bb-114">如果您已付費訂閱 Microsoft 365，您也會有免費的 Azure AD 訂閱。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="7e1bb-115">您可以使用 Azure AD 建立及管理使用者和群群組帳戶。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="7e1bb-116">若要啟動此訂閱，您必須完成一次性註冊。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="7e1bb-117">之後，您就可以從您的 Microsoft 365 系統管理中心存取 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="7e1bb-118">如需註冊免費 Azure AD 訂閱的指示，請參閱 [使用免費 AZURE ad 訂閱](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="7e1bb-119">請勿直接移至 azure.microsoft.com 進行註冊，否則您將會使用試用版或付費訂閱 Microsoft Azure，與免費的 azure AD 訂閱搭配 Microsoft 365 不同。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="7e1bb-120">使用免費訂閱，您可以同步處理內部部署目錄、設定單一登入，並與許多軟體（例如 Salesforce、DropBox 及其他許多軟體）同步處理。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="7e1bb-121">如果您想要增強的 AD DS 功能、雙向同步處理及其他管理功能，您可以將免費訂閱升級為付費的特優訂閱。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="7e1bb-122">如需詳細資訊，請參閱[Azure Active Directory edition](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="7e1bb-123">如需 Microsoft 365 和 Azure AD 的詳細資訊，請參閱[Microsoft 365 識別模型](about-microsoft-365-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="7e1bb-124">擴充 Microsoft 365 租使用者的功能</span><span class="sxs-lookup"><span data-stu-id="7e1bb-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="7e1bb-125">**功能**</span><span class="sxs-lookup"><span data-stu-id="7e1bb-125">**Feature**</span></span>|<span data-ttu-id="7e1bb-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="7e1bb-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7e1bb-127">整合式應用程式</span><span class="sxs-lookup"><span data-stu-id="7e1bb-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="7e1bb-128">您可以將個別應用程式的存取權授與您的 Microsoft 365 資料，例如郵件、行事曆、連絡人、使用者、群組、檔案及資料夾。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="7e1bb-129">您也可以在全域系統管理員層級授權這些應用程式，並在 Azure AD 中註冊應用程式，以將其提供給整個公司。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="7e1bb-130">Formore 資訊，請參閱[Microsoft 365 系統管理員的整合式應用程式和 Azure AD](integrated-apps-and-azure-ads.md)。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="7e1bb-131">另請參閱 [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-131">Also see [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>  <br/> |
|<span data-ttu-id="7e1bb-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="7e1bb-132">PowerApps</span></span>  <br/> | <span data-ttu-id="7e1bb-133">Power app 是可連接到現有資料來源（如 SharePoint 清單和其他資料應用程式）的行動裝置應用程式。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="7e1bb-134">如需詳細資訊，請參閱[在 SharePoint Online 中建立清單的 PowerApp](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab)和[PowerApps 頁面](https://powerapps.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="7e1bb-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7e1bb-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7e1bb-135">See also</span></span>

[<span data-ttu-id="7e1bb-136">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="7e1bb-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)