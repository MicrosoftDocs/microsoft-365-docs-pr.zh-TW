---
title: 在 Microsoft 365 中查看目錄同步處理狀態
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: 在本文中，您可以瞭解如何檢查 Office 365 中目錄同步處理的狀態。
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924657"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="9383d-103">在 Microsoft 365 中查看目錄同步處理狀態</span><span class="sxs-lookup"><span data-stu-id="9383d-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="9383d-104">如果您已整合內部部署 Active Directory 網域服務 (AD DS) 與 Azure Active Directory (Azure AD) ，只需要同步處理內部部署環境與 Microsoft 365，您也可以檢查同步處理的狀態。</span><span class="sxs-lookup"><span data-stu-id="9383d-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="9383d-105">檢視目錄同步處理狀態</span><span class="sxs-lookup"><span data-stu-id="9383d-105">View directory synchronization status</span></span>

- <span data-ttu-id="9383d-106">登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com) ，然後選擇首頁上的 **DirSync 狀態** 。</span><span class="sxs-lookup"><span data-stu-id="9383d-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="9383d-107">或者，您可以移至 [**使用者** 作用中使用者]， \> 然後在 [作用中 **使用者**] 頁面上，選擇 [**更多** \> **目錄同步** 處理]。</span><span class="sxs-lookup"><span data-stu-id="9383d-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="9383d-108">在 [ **目錄同步** 處理] 窗格中，選擇 [ **移至 DirSync 管理**]。</span><span class="sxs-lookup"><span data-stu-id="9383d-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="9383d-109">「管理目錄同步處理」頁面上的資訊</span><span class="sxs-lookup"><span data-stu-id="9383d-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="9383d-110">下表列出您可以在頁面上取得相關資訊的功能。</span><span class="sxs-lookup"><span data-stu-id="9383d-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="9383d-111">如果您的目錄同步處理有問題，錯誤也會列在此頁面上。</span><span class="sxs-lookup"><span data-stu-id="9383d-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="9383d-112">如需您可能會遇到之不同錯誤的詳細資訊，請參閱 [識別 Microsoft 365 中的目錄同步處理錯誤](identify-directory-synchronization-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="9383d-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="9383d-113">項目</span><span class="sxs-lookup"><span data-stu-id="9383d-113">Item</span></span>|<span data-ttu-id="9383d-114">功能</span><span class="sxs-lookup"><span data-stu-id="9383d-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="9383d-115">**已驗證網域**</span><span class="sxs-lookup"><span data-stu-id="9383d-115">**Domains verified**</span></span> | <span data-ttu-id="9383d-116">您已驗證您的 Microsoft 365 租使用者中的網域數目。</span><span class="sxs-lookup"><span data-stu-id="9383d-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="9383d-117">**未驗證的網域**</span><span class="sxs-lookup"><span data-stu-id="9383d-117">**Domains not verified**</span></span> | <span data-ttu-id="9383d-118">您已新增但未驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="9383d-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="9383d-119">**已啟用目錄同步處理**</span><span class="sxs-lookup"><span data-stu-id="9383d-119">**Directory sync enabled**</span></span> |<span data-ttu-id="9383d-120">TRUE 或 FALSE。</span><span class="sxs-lookup"><span data-stu-id="9383d-120">True or False.</span></span> <span data-ttu-id="9383d-121">指定是否已啟用目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="9383d-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="9383d-122">**最新目錄同步處理**</span><span class="sxs-lookup"><span data-stu-id="9383d-122">**Latest directory sync**</span></span> | <span data-ttu-id="9383d-123">上次執行目錄同步處理的時間。</span><span class="sxs-lookup"><span data-stu-id="9383d-123">Last time directory sync ran.</span></span> <span data-ttu-id="9383d-124">若上次同步處理超過三天以上，將會顯示警告及疑難排解工具的連結。</span><span class="sxs-lookup"><span data-stu-id="9383d-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="9383d-125">**已啟用密碼同步處理**</span><span class="sxs-lookup"><span data-stu-id="9383d-125">**Password sync enabled**</span></span> | <span data-ttu-id="9383d-126">TRUE 或 FALSE。</span><span class="sxs-lookup"><span data-stu-id="9383d-126">True or False.</span></span> <span data-ttu-id="9383d-127">指定您的內部部署與 Microsoft 365 租使用者之間是否有密碼雜湊同步處理。</span><span class="sxs-lookup"><span data-stu-id="9383d-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="9383d-128">**上次密碼同步處理**</span><span class="sxs-lookup"><span data-stu-id="9383d-128">**Last Password Sync**</span></span> | <span data-ttu-id="9383d-129">上次執行密碼雜湊同步處理的時間。</span><span class="sxs-lookup"><span data-stu-id="9383d-129">Last time password hash sync ran.</span></span> <span data-ttu-id="9383d-130">若上次同步處理超過三天以上，將會顯示警告及疑難排解工具的連結。</span><span class="sxs-lookup"><span data-stu-id="9383d-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="9383d-131">**目錄同步處理用戶端版本**</span><span class="sxs-lookup"><span data-stu-id="9383d-131">**Directory sync client version**</span></span> | <span data-ttu-id="9383d-132">會包含下載連結，如果已發行新版本的 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="9383d-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="9383d-133">**目錄同步處理服務帳戶**</span><span class="sxs-lookup"><span data-stu-id="9383d-133">**Directory sync service account**</span></span> | <span data-ttu-id="9383d-134">顯示 Microsoft 365 目錄同步服務帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="9383d-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="9383d-135">監控同步處理健康情況</span><span class="sxs-lookup"><span data-stu-id="9383d-135">Monitor synchronization health</span></span>

<span data-ttu-id="9383d-136">在這一節中，您會在每個內部部署 AD DS 網域控制站上安裝 Azure AD Connect Health 代理程式，以監控您的身分識別基礎結構，以及由 Azure AD Connect 提供的同步處理服務。</span><span class="sxs-lookup"><span data-stu-id="9383d-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="9383d-137">監控資訊會在 Azure AD Connect Health 入口網站提供，您可以在其中檢視警訊、效能監控、使用量分析及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="9383d-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="9383d-138">如何使用 Azure AD Connect Health 的關鍵設計決策取決於您如何使用 Azure AD Connect：</span><span class="sxs-lookup"><span data-stu-id="9383d-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="9383d-139">如果您使用的是 **受管理的驗證** 選項，請先從 [使用 Azure AD Connect Health 搭配同步處理](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)開始，以了解並設定 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="9383d-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="9383d-140">如果您使用 **同盟驗證** 搭配 Active Directory 同盟服務 (AD FS) 來同步處理帳戶及群組名稱，請先從 [使用 Azure AD Connect Health 搭配 AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 開始，以了解並設定 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="9383d-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="9383d-141">完成後，您將會有：</span><span class="sxs-lookup"><span data-stu-id="9383d-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="9383d-142">已在內部部署身分識別提供者伺服器上安裝 Azure AD Connect Health 代理程式。</span><span class="sxs-lookup"><span data-stu-id="9383d-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="9383d-143">Azure AD Connect Health 入口網站會顯示您內部部署基礎結構和同步處理活動的目前狀態以及 Microsoft 365 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="9383d-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>