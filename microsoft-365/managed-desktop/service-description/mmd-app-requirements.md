---
title: Microsoft 受管理的電腦應用程式需求
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 322a46ce48cce4d080e51f482178462934d5c8f2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659711"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="68a43-103">Microsoft 受管理的電腦應用程式需求</span><span class="sxs-lookup"><span data-stu-id="68a43-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="68a43-104">Microsoft 受管理的電腦要求我們使用特定的方法來管理裝置，以保證裝置的效能、可靠性及可維修性。</span><span class="sxs-lookup"><span data-stu-id="68a43-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="68a43-105">管理區域</span><span class="sxs-lookup"><span data-stu-id="68a43-105">Management area</span></span>  |<span data-ttu-id="68a43-106">Microsoft 受管理的電腦方法</span><span class="sxs-lookup"><span data-stu-id="68a43-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="68a43-107">裝置設定或原則管理</span><span class="sxs-lookup"><span data-stu-id="68a43-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="68a43-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="68a43-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="68a43-109">應用程式管理</span><span class="sxs-lookup"><span data-stu-id="68a43-109">Application management</span></span>     | <span data-ttu-id="68a43-110">Microsoft Intune 和公司入口網站</span><span class="sxs-lookup"><span data-stu-id="68a43-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="68a43-111">驅動程式部署</span><span class="sxs-lookup"><span data-stu-id="68a43-111">Driver deployment</span></span>     |  <span data-ttu-id="68a43-112">裝置、Windows 更新或 Intune 隨附的驅動程式</span><span class="sxs-lookup"><span data-stu-id="68a43-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="68a43-113">裝置安全性</span><span class="sxs-lookup"><span data-stu-id="68a43-113">Device security</span></span>     | <span data-ttu-id="68a43-114">請參閱 [裝置安全性](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="68a43-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="68a43-115">身分識別與存取管理</span><span class="sxs-lookup"><span data-stu-id="68a43-115">Identity and access management</span></span>     | <span data-ttu-id="68a43-116">請參閱身分 [識別和存取管理](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="68a43-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="68a43-117">網路安全性</span><span class="sxs-lookup"><span data-stu-id="68a43-117">Network security</span></span>     | <span data-ttu-id="68a43-118">請參閱 [網路安全性](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="68a43-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="68a43-119">資訊安全性</span><span class="sxs-lookup"><span data-stu-id="68a43-119">Information security</span></span>     |  <span data-ttu-id="68a43-120">請參閱 [資訊安全性](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="68a43-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="68a43-121">資料恢復</span><span class="sxs-lookup"><span data-stu-id="68a43-121">Data recovery</span></span>     | <span data-ttu-id="68a43-122">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="68a43-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="68a43-123">核心生產力</span><span class="sxs-lookup"><span data-stu-id="68a43-123">Core productivity</span></span>     | <span data-ttu-id="68a43-124">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="68a43-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="68a43-125">瀏覽器</span><span class="sxs-lookup"><span data-stu-id="68a43-125">Browser</span></span>     | <span data-ttu-id="68a43-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="68a43-126">Microsoft Edge</span></span>        |




<span data-ttu-id="68a43-127">Microsoft 受管理的電腦可能會監視受管理裝置上執行的其他軟體。</span><span class="sxs-lookup"><span data-stu-id="68a43-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="68a43-128">如果對裝置管理、裝置安全性、效能或可靠性產生負面影響，您可能需要要求 [服務方案例外](customizing.md)。</span><span class="sxs-lookup"><span data-stu-id="68a43-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
