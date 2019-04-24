---
title: Microsoft 受管理的電腦應用程式需求
description: ''
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278333"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="fd744-103">Microsoft 受管理的電腦應用程式需求</span><span class="sxs-lookup"><span data-stu-id="fd744-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="fd744-104">線條的商務應用程式，您想要部署至 Microsoft 受管理的電腦裝置必須符合本主題中的需求。</span><span class="sxs-lookup"><span data-stu-id="fd744-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="fd744-105">應用程式的狀況</span><span class="sxs-lookup"><span data-stu-id="fd744-105">Application condition</span></span>

<span data-ttu-id="fd744-106">請務必應用程式不產生負面影響 Microsoft 受管理的桌上型電腦環境。</span><span class="sxs-lookup"><span data-stu-id="fd744-106">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="fd744-107">以下是應用程式必須符合為了讓 Microsoft，以將它部署的需求。</span><span class="sxs-lookup"><span data-stu-id="fd744-107">The following are the requirements that an application must meet in order for Microsoft to deploy it.</span></span> <span data-ttu-id="fd744-108">對於任何指定應用程式或驅動程式，Microsoft 可能撤回提及提供任何需求。</span><span class="sxs-lookup"><span data-stu-id="fd744-108">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="fd744-109">Microsoft 可能決定要移除的任何應用程式或造成負面影響效能和可靠性的 Microsoft 受管理的電腦裝置的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="fd744-109">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="fd744-110">可使用 Microsoft 技術部署</span><span class="sxs-lookup"><span data-stu-id="fd744-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="fd744-111">Microsoft 受管理的電腦使用 Intune、 Microsoft 網上商店和商務用 Microsoft Store 部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="fd744-111">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications.</span></span> <span data-ttu-id="fd744-112">因此，應用程式必須封裝能夠 then 目前版本，這些服務的部署方式。</span><span class="sxs-lookup"><span data-stu-id="fd744-112">Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="fd744-113">禁止之應用程式的類別</span><span class="sxs-lookup"><span data-stu-id="fd744-113">Prohibited app classes</span></span>

<span data-ttu-id="fd744-114">Microsoft 受管理的電腦裝置上不允許特定應用程式類型：</span><span class="sxs-lookup"><span data-stu-id="fd744-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="fd744-115">3rd 廠商防病毒、 安全性或稽核軟體</span><span class="sxs-lookup"><span data-stu-id="fd744-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="fd744-116">3rd 廠商網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="fd744-116">3rd party web browsers</span></span>
- <span data-ttu-id="fd744-117">在 Office 365 專業增強版之前的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="fd744-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="fd744-118">安裝或將彙整其他 3rd 廠商軟體應用程式</span><span class="sxs-lookup"><span data-stu-id="fd744-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="fd744-119">受限制的應用程式行為</span><span class="sxs-lookup"><span data-stu-id="fd744-119">Restricted app behaviors</span></span>

<span data-ttu-id="fd744-120">某些應用程式行為可能有害的使用者經驗或呈現 Microsoft 受管理的電腦裝置安全性風險。</span><span class="sxs-lookup"><span data-stu-id="fd744-120">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fd744-121">應用程式應該不會出現下列行為或特性：</span><span class="sxs-lookup"><span data-stu-id="fd744-121">Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="fd744-122">使用者經驗：</span><span class="sxs-lookup"><span data-stu-id="fd744-122">User Experience:</span></span>
- <span data-ttu-id="fd744-123">安裝背景服務或即會衍生長時間執行背景處理程序</span><span class="sxs-lookup"><span data-stu-id="fd744-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="fd744-124">將自己新增至 Windows 啟動路徑</span><span class="sxs-lookup"><span data-stu-id="fd744-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="fd744-125">安全性：</span><span class="sxs-lookup"><span data-stu-id="fd744-125">Security:</span></span>
- <span data-ttu-id="fd744-126">呼叫未記載之 Windows 或 Office Api 或採取內部 Windows 或 Office 資料結構相依性</span><span class="sxs-lookup"><span data-stu-id="fd744-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="fd744-127">做為應用程式存放區，或具有內建的擴充管理員</span><span class="sxs-lookup"><span data-stu-id="fd744-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="fd744-128">提高使用者的權限</span><span class="sxs-lookup"><span data-stu-id="fd744-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="fd744-129">有已知的安全性弱點</span><span class="sxs-lookup"><span data-stu-id="fd744-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="fd744-130">使用不會縮合至受信任的根憑證簽署</span><span class="sxs-lookup"><span data-stu-id="fd744-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="fd744-131">加密或限制存取使用者資料</span><span class="sxs-lookup"><span data-stu-id="fd744-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="fd744-132">在執行階段修改作業系統的程式碼</span><span class="sxs-lookup"><span data-stu-id="fd744-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="fd744-133">驅動程式部署</span><span class="sxs-lookup"><span data-stu-id="fd744-133">Driver deployment</span></span>

<span data-ttu-id="fd744-134">除非驅動程式在 Windows Update，或分開簽署 Windows 硬體品質實驗室 (WHQL)，Microsoft 必須核准驅動程式，Microsoft 會部署至 Microsoft 受管理的電腦裝置的驅動程式之前。</span><span class="sxs-lookup"><span data-stu-id="fd744-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
