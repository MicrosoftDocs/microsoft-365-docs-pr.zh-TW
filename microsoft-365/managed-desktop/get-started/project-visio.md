---
title: Microsoft 受管理的電腦裝置上安裝 Microsoft Project 或 Microsoft Visio
description: Microsoft 受管理的電腦裝置上安裝 Microsoft Project 或 Microsoft Visio 的資訊
keywords: Microsoft 受管理的電腦，Microsoft 365、 Microsoft Project，Microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c820e36b7b397fe770216ee229e38a1da5b034d
ms.sourcegitcommit: aba6d1b81e4c579e82e6fad90daec65d775b450a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/14/2019
ms.locfileid: "30573417"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="25c00-104">Microsoft 受管理的電腦裝置上安裝 Microsoft Project 或 Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="25c00-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="25c00-105">Microsoft Project 和 Microsoft Visio 需要安裝 Microsoft 受管理的電腦裝置上的特定步驟。</span><span class="sxs-lookup"><span data-stu-id="25c00-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="25c00-106">本主題記載的先決條件和安裝程序，為這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="25c00-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25c00-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="25c00-107">Prerequisites</span></span>

<span data-ttu-id="25c00-108">系統管理員應該驗證其符合下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="25c00-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="25c00-109">必須可供您的使用者**授權數量**正確的 Microsoft Project 和 Microsoft Visio 的授權數量。</span><span class="sxs-lookup"><span data-stu-id="25c00-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="25c00-110">Microsoft 受管理的電腦時，目前僅支援 64 位元版本的這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="25c00-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="25c00-111">**授權名稱**這些應用程式的適當授權名稱如下：</span><span class="sxs-lookup"><span data-stu-id="25c00-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="25c00-112">**Microsoft Project** -Project Online 專業版或 Project Online 進階版</span><span class="sxs-lookup"><span data-stu-id="25c00-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="25c00-113">**Microsoft Visio** Visio Online 方案 2</span><span class="sxs-lookup"><span data-stu-id="25c00-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="25c00-114">**公司入口網站**的公司入口網站必須能夠使用租用戶中為您的使用者安裝這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="25c00-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="25c00-115">如果公司入口網站不部署在您的租用戶，請參閱 <<c0>的公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="25c00-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="25c00-116">部署 Project 和 Visio 版 Microsoft 受管理的電腦裝置</span><span class="sxs-lookup"><span data-stu-id="25c00-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="25c00-117">您提交支援要求之後，Microsoft 受管理的電腦會建立三個 Azure AD 群組和三個應用程式部署透過 Microsoft Intune 部署至您的租用戶的應用程式。</span><span class="sxs-lookup"><span data-stu-id="25c00-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="25c00-118">**部署 Project 及 Visio**</span><span class="sxs-lookup"><span data-stu-id="25c00-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="25c00-119">**支援要求的檔案**IT 系統管理員必須支援服務歸檔，讓這些應用程式可以使用自己的使用者。</span><span class="sxs-lookup"><span data-stu-id="25c00-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="25c00-120">連絡 Microsoft 受管理電腦的詳細資訊，請參閱[支援 Microsoft 受管理電腦的系統管理員](../working-with-managed-desktop/admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="25c00-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="25c00-121">**將使用者指派給新的 Azure AD 群組**Microsoft 受管理的電腦會建立租用戶中的 3 Azure AD 群組及 3 對應的應用程式部署。</span><span class="sxs-lookup"><span data-stu-id="25c00-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="25c00-122">IT 系統管理員必須將使用者指派給適當的群組。</span><span class="sxs-lookup"><span data-stu-id="25c00-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="25c00-123">將使用者指派給其中一個 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="25c00-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="25c00-124">Azure AD 群組名稱</span><span class="sxs-lookup"><span data-stu-id="25c00-124">Azure AD Group name</span></span> | <span data-ttu-id="25c00-125">若要指派哪個使用者？</span><span class="sxs-lookup"><span data-stu-id="25c00-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="25c00-126">Microsoft Office Project 的安裝</span><span class="sxs-lookup"><span data-stu-id="25c00-126">Microsoft-Office-Project-Install</span></span> | <span data-ttu-id="25c00-127">使用者需要只有專案</span><span class="sxs-lookup"><span data-stu-id="25c00-127">Users needing only Project</span></span>
<span data-ttu-id="25c00-128">Microsoft Office Visio-安裝</span><span class="sxs-lookup"><span data-stu-id="25c00-128">Microsoft-Office-Visio-Install</span></span> | <span data-ttu-id="25c00-129">需要僅 Visio 的使用者</span><span class="sxs-lookup"><span data-stu-id="25c00-129">Users needing only Visio</span></span>
<span data-ttu-id="25c00-130">Microsoft Office Project 和 Visio 安裝</span><span class="sxs-lookup"><span data-stu-id="25c00-130">Microsoft-Office-Project and Visio-Install</span></span> | <span data-ttu-id="25c00-131">需要 Project 及 Visio 的使用者</span><span class="sxs-lookup"><span data-stu-id="25c00-131">Users needing both Project and Visio</span></span>

<span data-ttu-id="25c00-132">一旦指派給這些群組，應用程式則可在公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="25c00-132">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="25c00-133">可能需要數分鐘才能同步處理，但然後使用者可以從公司入口網站安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="25c00-133">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="25c00-134">傳達變更</span><span class="sxs-lookup"><span data-stu-id="25c00-134">Communicate changes</span></span>
<span data-ttu-id="25c00-135">請務必讓 IT 系統管理員可讓他們知道如何安裝 Project 及 Visio 的使用者。</span><span class="sxs-lookup"><span data-stu-id="25c00-135">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="25c00-136">其中包括：</span><span class="sxs-lookup"><span data-stu-id="25c00-136">This includes:</span></span> 
- <span data-ttu-id="25c00-137">提供給他們這些應用程式時，請通知使用者。</span><span class="sxs-lookup"><span data-stu-id="25c00-137">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="25c00-138">關於如何從公司入口網站安裝這些應用程式的指示。</span><span class="sxs-lookup"><span data-stu-id="25c00-138">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="25c00-139">使用者必須關閉所有 Office 應用程式，再從公司入口網站安裝 Microsoft Project 或 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="25c00-139">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
