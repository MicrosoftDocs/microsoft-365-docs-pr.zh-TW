---
title: 將網域使用者同步處理至 Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 同步處理域控制的使用者與 Microsoft 365 for business。
ms.openlocfilehash: 1c939dec7229f02991b15f08c48f184efecaddb0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913247"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="77936-103">將網域使用者同步處理至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="77936-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="77936-104">1. 準備目錄同步處理</span><span class="sxs-lookup"><span data-stu-id="77936-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="77936-105">在您從本機 Active Directory 網域同步處理使用者和電腦之前，請先複查 [準備好目錄同步處理至 Microsoft 365](../enterprise/prepare-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="77936-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span></span> <span data-ttu-id="77936-106">具體說來：</span><span class="sxs-lookup"><span data-stu-id="77936-106">In particular:</span></span>

   - <span data-ttu-id="77936-107">請確定目錄中的下列屬性沒有重複專案： **mail**、 **proxyAddresses** 及 **userPrincipalName**。</span><span class="sxs-lookup"><span data-stu-id="77936-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="77936-108">這些值必須是唯一的，而且必須移除任何重複專案。</span><span class="sxs-lookup"><span data-stu-id="77936-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="77936-109">建議您為每個本機使用者帳戶設定 **userPrincipalName** (UPN) 屬性，使其符合與授權的 Microsoft 365 使用者相對應的主要電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="77936-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="77936-110">例如： *mary.shelley@contoso.com* ，而不是 *mary@contoso。*</span><span class="sxs-lookup"><span data-stu-id="77936-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="77936-111">如果 Active Directory 網域以非可路由的尾碼（如 .com *或* *lan*）結束，請不要依 internet 路由尾碼（如 *.com* 或 *org*）來調整本機使用者帳戶的 UPN 尾碼，如 [準備目錄同步處理的非路由網域](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="77936-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span> 

<span data-ttu-id="77936-112">在下列步驟 4 (4) 中 **執行 IdFix** ，也會確定內部部署 Active Directory 已準備好進行目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="77936-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="77936-113">2. 安裝及設定 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="77936-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="77936-114">若要將您的使用者、群組和連絡人從本機 Active Directory 同步處理至 Azure Active Directory，請安裝 Azure Active Directory Connect，並設定目錄同步作業。</span><span class="sxs-lookup"><span data-stu-id="77936-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="77936-115">在系統 [管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)的左側，選取 [ **安裝程式** ]。</span><span class="sxs-lookup"><span data-stu-id="77936-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="77936-116">在 [登 **入及安全性**] 下，選擇 [**從您的組織的目錄同步處理使用者**] 底下的 [**查看**]。</span><span class="sxs-lookup"><span data-stu-id="77936-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="77936-117">在 [ **從您的組織的目錄同步處理使用者** ] 頁面上，選擇 [ **開始**]。</span><span class="sxs-lookup"><span data-stu-id="77936-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="77936-118">在第一個步驟中執行 IdFix 工具來準備目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="77936-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="77936-119">依照嚮導的步驟下載 Azure AD Connect，並使用它將您的網域控制的使用者同步處理至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="77936-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="77936-120">請參閱 [設定 Microsoft 365 的目錄同步](../enterprise/set-up-directory-synchronization.md) 處理以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="77936-120">See [Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) to learn more.</span></span>

<span data-ttu-id="77936-121">當您設定 Azure AD Connect 的選項時，建議您啟用 **[密碼同步** 處理]、[ **無縫單一 Sign-On**] 及 [ **密碼寫回** 功能]，這是 Microsoft 365 for business 中也支援的功能。</span><span class="sxs-lookup"><span data-stu-id="77936-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="77936-122">在 Azure AD Connect 中，除了核取方塊之外，還有其他一些步驟可用於密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="77936-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="77936-123">如需詳細資訊，請參閱 how [to：設定密碼回寫](/azure/active-directory/authentication/howto-sspr-writeback)。</span><span class="sxs-lookup"><span data-stu-id="77936-123">For more information, see [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="77936-124">如果您也想要管理已加入網域的 Windows 10 裝置，請參閱 [Microsoft 365 商務版 Premium 以啟用已加入網域的 windows 10 裝置](manage-windows-devices.md) 以設定混合式 Azure AD 聯結。</span><span class="sxs-lookup"><span data-stu-id="77936-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span>