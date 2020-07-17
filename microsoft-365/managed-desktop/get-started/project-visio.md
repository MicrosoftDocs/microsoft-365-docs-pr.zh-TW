---
title: 在 Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio
description: Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio 的資訊
keywords: Microsoft 受管理的桌面、microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126824"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="890b4-104">在 Microsoft 受管理的桌面裝置上安裝 Microsoft Project 或 Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="890b4-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="890b4-105">Microsoft Project 和 Microsoft Visio 需要在 Microsoft 受管理的桌面裝置上安裝特定步驟。</span><span class="sxs-lookup"><span data-stu-id="890b4-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="890b4-106">本主題說明這些應用程式的必要條件和安裝程式。</span><span class="sxs-lookup"><span data-stu-id="890b4-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="890b4-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="890b4-107">Prerequisites</span></span>

<span data-ttu-id="890b4-108">系統管理員應確認其符合下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="890b4-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="890b4-109">**授權數量**-您的使用者必須能夠使用正確的 microsoft Project 和 microsoft Visio 授權金額。</span><span class="sxs-lookup"><span data-stu-id="890b4-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="890b4-110">Microsoft 受管理的桌面目前只支援這些應用程式的64位版本。</span><span class="sxs-lookup"><span data-stu-id="890b4-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="890b4-111">**授權名稱**-這些應用程式的適當授權名稱是：</span><span class="sxs-lookup"><span data-stu-id="890b4-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="890b4-112">**Microsoft project** -Project Online 專業版或 Project online Premium</span><span class="sxs-lookup"><span data-stu-id="890b4-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="890b4-113">**Microsoft visio** -Visio Online 方案2</span><span class="sxs-lookup"><span data-stu-id="890b4-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="890b4-114">**公司入口網站**-您的租使用者必須具備公司入口網站，您的使用者才可安裝這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="890b4-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="890b4-115">如果未在租使用者中部署公司入口網站，請參閱[公司入口網站](company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="890b4-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="890b4-116">部署 Microsoft 受管理桌面裝置的 Project 和 Visio</span><span class="sxs-lookup"><span data-stu-id="890b4-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="890b4-117">Microsoft 受管理的桌面會將 Microsoft Project 和 Microsoft Visio 新增為 Microsoft Intune 中的兩個 Win32 應用程式。</span><span class="sxs-lookup"><span data-stu-id="890b4-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="890b4-118">我們也會在 Azure Active Directory 中建立兩個群組，將會指派給對應的應用程式，其具有「可用」的目的。</span><span class="sxs-lookup"><span data-stu-id="890b4-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="890b4-119">**部署 Project 和 Visio**將使用者新增至適當的群組，該應用程式將會出現在公司入口網站中。</span><span class="sxs-lookup"><span data-stu-id="890b4-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="890b4-120">可能需要幾分鐘的時間進行同步處理，但是您的使用者可以從公司入口網站安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="890b4-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="890b4-121">Azure AD 群組名稱</span><span class="sxs-lookup"><span data-stu-id="890b4-121">Azure AD Group name</span></span> | <span data-ttu-id="890b4-122">要指派哪些使用者？</span><span class="sxs-lookup"><span data-stu-id="890b4-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="890b4-123">現代辦公 Project_Install</span><span class="sxs-lookup"><span data-stu-id="890b4-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="890b4-124">需要專案的使用者</span><span class="sxs-lookup"><span data-stu-id="890b4-124">Users needing Project</span></span>
<span data-ttu-id="890b4-125">現代辦公 Visio_Install</span><span class="sxs-lookup"><span data-stu-id="890b4-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="890b4-126">需要 Visio 的使用者</span><span class="sxs-lookup"><span data-stu-id="890b4-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="890b4-127">交流變更</span><span class="sxs-lookup"><span data-stu-id="890b4-127">Communicate changes</span></span>
<span data-ttu-id="890b4-128">讓使用者瞭解如何安裝 Project 和 Visio 很重要。</span><span class="sxs-lookup"><span data-stu-id="890b4-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="890b4-129">這包括：</span><span class="sxs-lookup"><span data-stu-id="890b4-129">This includes:</span></span> 
- <span data-ttu-id="890b4-130">在這些應用程式可供使用時通知使用者。</span><span class="sxs-lookup"><span data-stu-id="890b4-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="890b4-131">如何從公司入口網站安裝這些應用程式的指示。</span><span class="sxs-lookup"><span data-stu-id="890b4-131">Instructions on how to install these applications from the Company Portal.</span></span>
