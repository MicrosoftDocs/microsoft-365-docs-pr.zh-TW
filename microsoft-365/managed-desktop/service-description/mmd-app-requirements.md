---
title: Microsoft 受管理的桌面應用程式需求
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: bd775e201f5fec556941ae0e8e7b025744da0419
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529430"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="5a8b8-103">Microsoft 受管理的桌面應用程式需求</span><span class="sxs-lookup"><span data-stu-id="5a8b8-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="5a8b8-104">Microsoft 受管理的桌面要求我們使用特定的方法來管理裝置，以保證裝置的效能、可靠性及可維修性。</span><span class="sxs-lookup"><span data-stu-id="5a8b8-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span> <span data-ttu-id="5a8b8-105">[！注意] 如果您確定 Microsoft 受管理的桌面所採用的功能將無法為您運作，您可以要求[服務方案例外](customizing.md)。</span><span class="sxs-lookup"><span data-stu-id="5a8b8-105">If you’re sure that the approach taken by Microsoft Managed Desktop for the areas below will not work for you, you can request an [exception to the service plan](customizing.md).</span></span>


|<span data-ttu-id="5a8b8-106">管理區域</span><span class="sxs-lookup"><span data-stu-id="5a8b8-106">Management area</span></span>  |<span data-ttu-id="5a8b8-107">Microsoft 受管理的桌面方法</span><span class="sxs-lookup"><span data-stu-id="5a8b8-107">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="5a8b8-108">裝置設定或原則管理</span><span class="sxs-lookup"><span data-stu-id="5a8b8-108">Device configuration or policy management</span></span>     |  <span data-ttu-id="5a8b8-109">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5a8b8-109">Microsoft Intune</span></span>       |
|<span data-ttu-id="5a8b8-110">應用程式管理</span><span class="sxs-lookup"><span data-stu-id="5a8b8-110">Application management</span></span>     | <span data-ttu-id="5a8b8-111">Microsoft Intune 和公司入口網站</span><span class="sxs-lookup"><span data-stu-id="5a8b8-111">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="5a8b8-112">驅動程式部署</span><span class="sxs-lookup"><span data-stu-id="5a8b8-112">Driver deployment</span></span>     |  <span data-ttu-id="5a8b8-113">裝置、Windows Update 或 Intune 隨附的驅動程式</span><span class="sxs-lookup"><span data-stu-id="5a8b8-113">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="5a8b8-114">裝置安全性</span><span class="sxs-lookup"><span data-stu-id="5a8b8-114">Device security</span></span>     | <span data-ttu-id="5a8b8-115">請參閱[裝置安全性](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="5a8b8-115">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="5a8b8-116">身分識別與存取管理</span><span class="sxs-lookup"><span data-stu-id="5a8b8-116">Identity and access management</span></span>     | <span data-ttu-id="5a8b8-117">請參閱身分[識別和存取管理](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="5a8b8-117">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="5a8b8-118">網路安全性</span><span class="sxs-lookup"><span data-stu-id="5a8b8-118">Network security</span></span>     | <span data-ttu-id="5a8b8-119">請參閱[網路安全性](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="5a8b8-119">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="5a8b8-120">資訊安全性</span><span class="sxs-lookup"><span data-stu-id="5a8b8-120">Information security</span></span>     |  <span data-ttu-id="5a8b8-121">請參閱[資訊安全性](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="5a8b8-121">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="5a8b8-122">資料恢復</span><span class="sxs-lookup"><span data-stu-id="5a8b8-122">Data recovery</span></span>     | <span data-ttu-id="5a8b8-123">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="5a8b8-123">OneDrive for Business</span></span>        |
|<span data-ttu-id="5a8b8-124">核心生產力</span><span class="sxs-lookup"><span data-stu-id="5a8b8-124">Core productivity</span></span>     | <span data-ttu-id="5a8b8-125">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="5a8b8-125">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="5a8b8-126">瀏覽器</span><span class="sxs-lookup"><span data-stu-id="5a8b8-126">Browser</span></span>     | <span data-ttu-id="5a8b8-127">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5a8b8-127">Microsoft Edge</span></span>        |




<span data-ttu-id="5a8b8-128">Microsoft 受管理的桌面可能會監視受管理裝置上執行的其他軟體。</span><span class="sxs-lookup"><span data-stu-id="5a8b8-128">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="5a8b8-129">如果對系統安全性、效能或可靠性有負面影響，您可能需要要求服務方案例外。</span><span class="sxs-lookup"><span data-stu-id="5a8b8-129">If it negatively impacts system security, performance, or reliability, you might be required to request an exception to the service plan.</span></span>


