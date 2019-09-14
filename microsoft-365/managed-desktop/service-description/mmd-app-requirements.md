---
title: Microsoft 受管理的電腦應用程式需求
description: ''
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e0ca142e2ef84f198ee154c5b7c7f4f6621c37c
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982454"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="71bb0-103">Microsoft 受管理的電腦應用程式需求</span><span class="sxs-lookup"><span data-stu-id="71bb0-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="71bb0-104">為了確保效能、 可靠性和服務性的 Microsoft 受管理的電腦裝置的商務應用程式的客戶的行必須不嚴重影響使用者體驗，或修改安全性轉變成為。</span><span class="sxs-lookup"><span data-stu-id="71bb0-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="71bb0-105">因此，您想要部署至 Microsoft 受管理的電腦裝置的商務應用程式必須符合本主題中的需求。</span><span class="sxs-lookup"><span data-stu-id="71bb0-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="71bb0-106">應用程式的狀況</span><span class="sxs-lookup"><span data-stu-id="71bb0-106">Application condition</span></span>

<span data-ttu-id="71bb0-107">請務必應用程式不產生負面影響 Microsoft 受管理的桌上型電腦環境。</span><span class="sxs-lookup"><span data-stu-id="71bb0-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="71bb0-108">以下是要部署的應用程式的應用程式必須符合的需求。</span><span class="sxs-lookup"><span data-stu-id="71bb0-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="71bb0-109">對於任何指定應用程式或驅動程式，Microsoft 可能撤回提及提供任何需求。</span><span class="sxs-lookup"><span data-stu-id="71bb0-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="71bb0-110">Microsoft 可能決定要移除的任何應用程式或造成負面影響效能和可靠性的 Microsoft 受管理的電腦裝置的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="71bb0-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="71bb0-111">集中管理的應用程式</span><span class="sxs-lookup"><span data-stu-id="71bb0-111">Centrally managed apps</span></span>

<span data-ttu-id="71bb0-112">透過 Microsoft Intune、 Microsoft 網上商店或 Microsoft 網上商店商務;，則必須部署所有應用程式和 Microsoft 受管理的裝置上安裝驅動程式如果有的話驅動程式也會透過 Windows Update 服務部署。</span><span class="sxs-lookup"><span data-stu-id="71bb0-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="71bb0-113">禁止之應用程式的類別</span><span class="sxs-lookup"><span data-stu-id="71bb0-113">Prohibited app classes</span></span>

<span data-ttu-id="71bb0-114">Microsoft 受管理的電腦裝置上不允許特定應用程式類型：</span><span class="sxs-lookup"><span data-stu-id="71bb0-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="71bb0-115">3rd 廠商防病毒、 安全性或稽核軟體</span><span class="sxs-lookup"><span data-stu-id="71bb0-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="71bb0-116">在 Office 365 專業增強版之前的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="71bb0-116">Versions of Microsoft Office prior to Office 365 ProPlus</span></span>
- <span data-ttu-id="71bb0-117">安裝或將彙整其他 3rd 廠商軟體應用程式</span><span class="sxs-lookup"><span data-stu-id="71bb0-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="71bb0-118">受限制的應用程式行為</span><span class="sxs-lookup"><span data-stu-id="71bb0-118">Restricted app behaviors</span></span>

<span data-ttu-id="71bb0-119">某些應用程式行為產生負面影響的使用者經驗，或可能呈現 Microsoft 受管理的電腦裝置安全性風險。</span><span class="sxs-lookup"><span data-stu-id="71bb0-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="71bb0-120">若要執行而不從 Microsoft 特定豁免 Microsoft 受管理的桌上型電腦環境中不允許具有下列行為的應用程式。</span><span class="sxs-lookup"><span data-stu-id="71bb0-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific exemption from Microsoft.</span></span>

<span data-ttu-id="71bb0-121">使用者經驗：</span><span class="sxs-lookup"><span data-stu-id="71bb0-121">User Experience:</span></span>
- <span data-ttu-id="71bb0-122">安裝背景服務</span><span class="sxs-lookup"><span data-stu-id="71bb0-122">Install background services</span></span>
- <span data-ttu-id="71bb0-123">將自己新增至 Windows 啟動路徑</span><span class="sxs-lookup"><span data-stu-id="71bb0-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="71bb0-124">取決於驅動程式的應用程式</span><span class="sxs-lookup"><span data-stu-id="71bb0-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="71bb0-125">3rd 廠商網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="71bb0-125">3rd party web browsers</span></span>

<span data-ttu-id="71bb0-126">安全性：</span><span class="sxs-lookup"><span data-stu-id="71bb0-126">Security:</span></span>
- <span data-ttu-id="71bb0-127">提高使用者的權限</span><span class="sxs-lookup"><span data-stu-id="71bb0-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="71bb0-128">做為應用程式存放區，或具有內建的擴充管理員</span><span class="sxs-lookup"><span data-stu-id="71bb0-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="71bb0-129">有已知的安全性弱點</span><span class="sxs-lookup"><span data-stu-id="71bb0-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="71bb0-130">加密或限制存取使用者資料</span><span class="sxs-lookup"><span data-stu-id="71bb0-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="71bb0-131">是不帶正負號，或使用不會縮合至受信任的根憑證簽署</span><span class="sxs-lookup"><span data-stu-id="71bb0-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="71bb0-132">驅動程式部署</span><span class="sxs-lookup"><span data-stu-id="71bb0-132">Driver deployment</span></span>

<span data-ttu-id="71bb0-133">Microsoft 受管理電腦只支援可透過 Windows Update 或收件匣隨 Microsoft 受管理裝置的裝置驅動程式。</span><span class="sxs-lookup"><span data-stu-id="71bb0-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="71bb0-134">如果應用程式需要特定執行它的驅動程式會被視為受限制的應用程式，並要求豁免部署至 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="71bb0-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an exemption to be deployed to Microsoft Managed Desktop.</span></span> 

