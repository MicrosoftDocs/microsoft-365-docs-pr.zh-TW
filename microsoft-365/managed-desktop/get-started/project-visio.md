---
title: 在 Microsoft 受管理的電腦裝置上安裝 Microsoft Project 或 Microsoft Visio
description: Microsoft 受管理的電腦裝置上的 Microsoft Project 或 Microsoft Visio 安裝資訊
keywords: Microsoft 受管理的電腦、Microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd46410877012d92e847ba7ff8b60cd5acceb1e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925536"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="ca99e-104">在 Microsoft 受管理的電腦裝置上安裝 Microsoft Project 或 Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="ca99e-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="ca99e-105">Microsoft Project 和 Microsoft Visio 需要在 Microsoft 受管理的電腦裝置上安裝特定步驟。</span><span class="sxs-lookup"><span data-stu-id="ca99e-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ca99e-106">本主題說明這些應用程式的必要條件和安裝程式。</span><span class="sxs-lookup"><span data-stu-id="ca99e-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca99e-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="ca99e-107">Prerequisites</span></span>

<span data-ttu-id="ca99e-108">系統管理員應確認其符合下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="ca99e-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="ca99e-109">**授權數量**-您的使用者必須能使用正確的 Microsoft Project 數量和 Microsoft Visio 授權。</span><span class="sxs-lookup"><span data-stu-id="ca99e-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="ca99e-110">Microsoft 受管理的電腦目前只支援這些應用程式的64位版本。</span><span class="sxs-lookup"><span data-stu-id="ca99e-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="ca99e-111">**授權名稱** -這些應用程式的適當授權名稱是：</span><span class="sxs-lookup"><span data-stu-id="ca99e-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="ca99e-112">**Microsoft Project** Project Online 專業版或 Project Online 進階版</span><span class="sxs-lookup"><span data-stu-id="ca99e-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="ca99e-113">**Microsoft Visio** Visio 線上方案2</span><span class="sxs-lookup"><span data-stu-id="ca99e-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="ca99e-114">**公司入口網站**-您的承租人必須可使用公司入口網站，以供您的使用者安裝這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="ca99e-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="ca99e-115">如果公司入口網站未部署在您的租使用者中，請參閱[公司入口網站](company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="ca99e-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="ca99e-116">部署 Microsoft 受管理的電腦裝置的 Project 和 Visio</span><span class="sxs-lookup"><span data-stu-id="ca99e-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="ca99e-117">Microsoft 受管理的電腦會將 Microsoft Project 和 Microsoft Visio 新增為 Microsoft Intune 中的兩個 Win32 應用程式。</span><span class="sxs-lookup"><span data-stu-id="ca99e-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="ca99e-118">我們也會在 Azure Active Directory 中建立兩個群組，將會指派給具有「可用」之對應應用程式的。</span><span class="sxs-lookup"><span data-stu-id="ca99e-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="ca99e-119">**若要部署 Project 和 Visio** 將使用者新增至適當的群組，該應用程式就會出現公司入口網站中。</span><span class="sxs-lookup"><span data-stu-id="ca99e-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="ca99e-120">可能需要幾分鐘的時間進行同步處理，但是您的使用者可以從公司入口網站安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="ca99e-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="ca99e-121">Azure AD 群組名稱</span><span class="sxs-lookup"><span data-stu-id="ca99e-121">Azure AD Group name</span></span> | <span data-ttu-id="ca99e-122">要指派哪些使用者？</span><span class="sxs-lookup"><span data-stu-id="ca99e-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="ca99e-123">新式工作區-Office Project_Install</span><span class="sxs-lookup"><span data-stu-id="ca99e-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="ca99e-124">需要 Project 的使用者</span><span class="sxs-lookup"><span data-stu-id="ca99e-124">Users needing Project</span></span>
<span data-ttu-id="ca99e-125">新式工作區-Office Visio_Install</span><span class="sxs-lookup"><span data-stu-id="ca99e-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="ca99e-126">需要 Visio 的使用者</span><span class="sxs-lookup"><span data-stu-id="ca99e-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="ca99e-127">交流變更</span><span class="sxs-lookup"><span data-stu-id="ca99e-127">Communicate changes</span></span>
<span data-ttu-id="ca99e-128">請務必讓 IT 系統管理員知道如何安裝 Project 和 Visio。</span><span class="sxs-lookup"><span data-stu-id="ca99e-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="ca99e-129">這包括：</span><span class="sxs-lookup"><span data-stu-id="ca99e-129">This includes:</span></span> 
- <span data-ttu-id="ca99e-130">在這些應用程式可供使用時通知使用者。</span><span class="sxs-lookup"><span data-stu-id="ca99e-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="ca99e-131">如何從公司入口網站安裝這些應用程式的指示。</span><span class="sxs-lookup"><span data-stu-id="ca99e-131">Instructions on how to install these applications from the Company Portal.</span></span>
