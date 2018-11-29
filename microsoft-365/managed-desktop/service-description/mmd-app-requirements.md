---
title: Microsoft 受管理的桌面應用程式需求
description: ''
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 71952a8b073f002890cc95883e717aeb04c0cd68
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866103"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="29ca4-103">Microsoft 受管理的桌面應用程式需求</span><span class="sxs-lookup"><span data-stu-id="29ca4-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="29ca4-104">您想要部署至 Microsoft 受管理的桌上型電腦裝置的企業營運系統應用程式必須符合本主題中的需求。</span><span class="sxs-lookup"><span data-stu-id="29ca4-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="29ca4-105">應用程式的狀況</span><span class="sxs-lookup"><span data-stu-id="29ca4-105">Application condition</span></span>

<span data-ttu-id="29ca4-p101">請務必應用程式不不良影響的 Microsoft 受管理的桌上型電腦環境。以下是應用程式必須符合為了讓 Microsoft 將其部署的需求。對於任何指定的應用程式或驅動程式，Microsoft 可能本指射提供任何需求。Microsoft 可能會決定要移除任何應用程式或造成負面影響效能與可靠性的 Microsoft 受管理的桌上型電腦裝置的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="29ca4-p101">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment. The following are the requirements that an application must meet in order for Microsoft to deploy it. For any given application or driver, Microsoft may waive any requirement provided herein. Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="29ca4-110">可使用 Microsoft 技術部署</span><span class="sxs-lookup"><span data-stu-id="29ca4-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="29ca4-p102">Microsoft 受管理的桌上型電腦使用 Intune、 Microsoft 存放區及 Microsoft Store for Business 部署應用程式。因此，應用程式必須封裝能夠部署由加上 then 目前版本的那些服務的方式。</span><span class="sxs-lookup"><span data-stu-id="29ca4-p102">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications. Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="29ca4-113">禁止的 app 類別</span><span class="sxs-lookup"><span data-stu-id="29ca4-113">Prohibited app classes</span></span>

<span data-ttu-id="29ca4-114">Microsoft 受管理的桌上型電腦裝置上不允許的特定應用程式類型：</span><span class="sxs-lookup"><span data-stu-id="29ca4-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="29ca4-115">3rd 的廠商防毒、 安全性或稽核軟體</span><span class="sxs-lookup"><span data-stu-id="29ca4-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="29ca4-116">在 Office 365 Pro Plus 之前的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="29ca4-116">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="29ca4-117">安裝或將彙整其他 3rd 廠商軟體應用程式</span><span class="sxs-lookup"><span data-stu-id="29ca4-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="29ca4-118">受限制的應用程式行為</span><span class="sxs-lookup"><span data-stu-id="29ca4-118">Restricted app behaviors</span></span>

<span data-ttu-id="29ca4-p103">某些應用程式的行為可以前者的使用者經驗或呈現 Microsoft 受管理的桌上型電腦裝置安全性風險。下列行為或特性，不應會呈現應用程式：</span><span class="sxs-lookup"><span data-stu-id="29ca4-p103">Certain application behaviors can be either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices. Applications shall not exhibit the following behaviors or characteristics:</span></span> 
- <span data-ttu-id="29ca4-121">安裝背景服務或即會衍生長時間執行背景處理程序</span><span class="sxs-lookup"><span data-stu-id="29ca4-121">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="29ca4-122">將其本身加入 Windows 啟動路徑</span><span class="sxs-lookup"><span data-stu-id="29ca4-122">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="29ca4-123">呼叫未記載之 Windows 或 Office Api 或採取內部 Windows 或 Office 資料結構相依性</span><span class="sxs-lookup"><span data-stu-id="29ca4-123">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="29ca4-124">做為應用程式商店或具有內建的擴充管理員</span><span class="sxs-lookup"><span data-stu-id="29ca4-124">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="29ca4-125">提高使用者的權限</span><span class="sxs-lookup"><span data-stu-id="29ca4-125">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="29ca4-126">有已知安全性弱點</span><span class="sxs-lookup"><span data-stu-id="29ca4-126">Have known security vulnerabilities</span></span>
- <span data-ttu-id="29ca4-127">使用不彙總為受信任的根憑證簽署</span><span class="sxs-lookup"><span data-stu-id="29ca4-127">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="29ca4-128">加密或限制存取使用者資料</span><span class="sxs-lookup"><span data-stu-id="29ca4-128">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="29ca4-129">在執行階段修改作業系統的程式碼</span><span class="sxs-lookup"><span data-stu-id="29ca4-129">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="29ca4-130">驅動程式部署</span><span class="sxs-lookup"><span data-stu-id="29ca4-130">Driver deployment</span></span>

<span data-ttu-id="29ca4-131">除非驅動程式在 Windows Update 或分開簽署 Windows 硬體品質實驗室 (WHQL)、 Microsoft 必須在 Microsoft 會部署至 Microsoft 受管理的桌上型電腦裝置的驅動程式之前核准驅動程式。</span><span class="sxs-lookup"><span data-stu-id="29ca4-131">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>