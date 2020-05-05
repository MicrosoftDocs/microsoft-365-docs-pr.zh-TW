---
title: 在 Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio
description: Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio 的資訊
keywords: Microsoft 受管理的桌面、microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 450dbcb08cd0636dae575ecd2d5e9abadc5ceb25
ms.sourcegitcommit: 44e685a0b193e89de5befb1e1a3740eb31931799
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44022093"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="5f68d-104">在 Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="5f68d-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="5f68d-105">Microsoft Project 和 Microsoft Visio 需要在 Microsoft 受管理的桌面裝置上安裝特定步驟。</span><span class="sxs-lookup"><span data-stu-id="5f68d-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="5f68d-106">本主題說明這些應用程式的必要條件和安裝程式。</span><span class="sxs-lookup"><span data-stu-id="5f68d-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5f68d-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="5f68d-107">Prerequisites</span></span>

<span data-ttu-id="5f68d-108">系統管理員應確認其符合下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="5f68d-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="5f68d-109">**授權數量**-您的使用者必須能夠使用正確的 microsoft Project 和 microsoft Visio 授權金額。</span><span class="sxs-lookup"><span data-stu-id="5f68d-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="5f68d-110">Microsoft 受管理的桌面目前只支援這些應用程式的64位版本。</span><span class="sxs-lookup"><span data-stu-id="5f68d-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="5f68d-111">**授權名稱**-這些應用程式的適當授權名稱是：</span><span class="sxs-lookup"><span data-stu-id="5f68d-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="5f68d-112">**Microsoft project** -Project Online 專業版或 Project online Premium</span><span class="sxs-lookup"><span data-stu-id="5f68d-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="5f68d-113">**Microsoft visio** -Visio Online 方案2</span><span class="sxs-lookup"><span data-stu-id="5f68d-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="5f68d-114">**公司入口網站**-您的租使用者必須具備公司入口網站，您的使用者才可安裝這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f68d-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="5f68d-115">如果未在租使用者中部署公司入口網站，請參閱[公司入口網站](company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="5f68d-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="5f68d-116">部署 Microsoft 受管理桌面裝置的 Project 和 Visio</span><span class="sxs-lookup"><span data-stu-id="5f68d-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="5f68d-117">在您提交支援要求之後，Microsoft 受管理的桌面會透過 Microsoft Intune 建立三個 Azure AD 群組和三個應用程式部署，以將應用程式部署至您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="5f68d-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="5f68d-118">**部署 Project 和 Visio**</span><span class="sxs-lookup"><span data-stu-id="5f68d-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="5f68d-119">檔案**a 支援要求**IT 系統管理員必須將支援要求歸檔，以讓這些應用程式可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="5f68d-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="5f68d-120">如需聯繫 Microsoft 受管理的電腦的詳細資訊，請參閱[Microsoft Managed desktop 的系統管理支援](../working-with-managed-desktop/admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="5f68d-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="5f68d-121">**將使用者指派給新的 AZURE AD 群組**Microsoft 受管理的桌面會在您的租使用者和3對應的應用程式部署中建立3個 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="5f68d-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="5f68d-122">IT 系統管理員必須將使用者指派給適當的群組。</span><span class="sxs-lookup"><span data-stu-id="5f68d-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="5f68d-123">僅將使用者指派給這些 Azure AD 群組中的其中一個。</span><span class="sxs-lookup"><span data-stu-id="5f68d-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="5f68d-124">Azure AD 群組名稱</span><span class="sxs-lookup"><span data-stu-id="5f68d-124">Azure AD Group name</span></span> | <span data-ttu-id="5f68d-125">要指派哪些使用者？</span><span class="sxs-lookup"><span data-stu-id="5f68d-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="5f68d-126">現代辦公 Project_Install</span><span class="sxs-lookup"><span data-stu-id="5f68d-126">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="5f68d-127">需要專案的使用者</span><span class="sxs-lookup"><span data-stu-id="5f68d-127">Users needing Project</span></span>
<span data-ttu-id="5f68d-128">現代辦公 Visio_Install</span><span class="sxs-lookup"><span data-stu-id="5f68d-128">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="5f68d-129">需要 Visio 的使用者</span><span class="sxs-lookup"><span data-stu-id="5f68d-129">Users needing Visio</span></span>

<span data-ttu-id="5f68d-130">一旦指派給這些群組，便可在公司入口網站中取得應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f68d-130">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="5f68d-131">可能需要幾分鐘的時間進行同步處理，但是您的使用者可以從公司入口網站安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f68d-131">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="5f68d-132">交流變更</span><span class="sxs-lookup"><span data-stu-id="5f68d-132">Communicate changes</span></span>
<span data-ttu-id="5f68d-133">讓使用者瞭解如何安裝 Project 和 Visio 很重要。</span><span class="sxs-lookup"><span data-stu-id="5f68d-133">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="5f68d-134">這包括：</span><span class="sxs-lookup"><span data-stu-id="5f68d-134">This includes:</span></span> 
- <span data-ttu-id="5f68d-135">在這些應用程式可供使用時通知使用者。</span><span class="sxs-lookup"><span data-stu-id="5f68d-135">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="5f68d-136">如何從公司入口網站安裝這些應用程式的指示。</span><span class="sxs-lookup"><span data-stu-id="5f68d-136">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="5f68d-137">使用者在從公司入口網站安裝 Microsoft Project 或 Microsoft Visio 之前，必須先關閉所有 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f68d-137">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
