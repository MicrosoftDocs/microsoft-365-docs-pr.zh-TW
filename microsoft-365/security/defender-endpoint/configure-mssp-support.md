---
title: 設定受管理的安全性服務提供者支援
description: 採取必要的步驟來設定 MSSP 整合與 Microsoft Defender for Endpoint
keywords: 受管理的安全性服務提供者、mssp、configure、integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d82bffd6eea54256f2c6773f843030a19e27275d
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339355"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="b8f64-104">設定受管理的安全性服務提供者整合</span><span class="sxs-lookup"><span data-stu-id="b8f64-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b8f64-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b8f64-105">**Applies to:**</span></span>
- [<span data-ttu-id="b8f64-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b8f64-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b8f64-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8f64-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b8f64-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b8f64-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b8f64-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b8f64-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b8f64-110">您必須採取下列設定步驟，才能啟用受管理的安全性服務提供者 (MSSP) 整合。</span><span class="sxs-lookup"><span data-stu-id="b8f64-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="b8f64-111">本文使用下列術語，以辨別服務提供者和服務使用者：</span><span class="sxs-lookup"><span data-stu-id="b8f64-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="b8f64-112">MSSPs：為組織監控及管理安全裝置的安全性組織。</span><span class="sxs-lookup"><span data-stu-id="b8f64-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="b8f64-113">MSSP 客戶：與 MSSPs 服務接洽的組織。</span><span class="sxs-lookup"><span data-stu-id="b8f64-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="b8f64-114">整合會讓 MSSPs 採取下列動作：</span><span class="sxs-lookup"><span data-stu-id="b8f64-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="b8f64-115">取得 MSSP 客戶 Microsoft 365 Defender 入口網站的存取權</span><span class="sxs-lookup"><span data-stu-id="b8f64-115">Get access to MSSP customer's Microsoft 365 Defender portal</span></span>
- <span data-ttu-id="b8f64-116">取得電子郵件通知，以及</span><span class="sxs-lookup"><span data-stu-id="b8f64-116">Get email notifications, and</span></span> 
- <span data-ttu-id="b8f64-117">透過安全性資訊和事件管理 (SIEM) 工具取得警示</span><span class="sxs-lookup"><span data-stu-id="b8f64-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="b8f64-118">在 MSSPs 可以採取這些動作之前，MSSP 客戶必須將其 Defender 的存取權授與端點租使用者，以便 MSSP 可以存取入口網站。</span><span class="sxs-lookup"><span data-stu-id="b8f64-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="b8f64-119">通常，MSSP 客戶會採取初始設定步驟，授與其 Windows Defender 安全性中央租使用者的 MSSPs 存取權。</span><span class="sxs-lookup"><span data-stu-id="b8f64-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="b8f64-120">授與存取權之後，MSSP 客戶或 MSSP 可以執行其他設定步驟。</span><span class="sxs-lookup"><span data-stu-id="b8f64-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="b8f64-121">一般而言，必須採取下列設定步驟：</span><span class="sxs-lookup"><span data-stu-id="b8f64-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="b8f64-122">**授與 Microsoft 365 Defender 的 MSSP 存取權**</span><span class="sxs-lookup"><span data-stu-id="b8f64-122">**Grant the MSSP access to Microsoft 365 Defender**</span></span> <br>
<span data-ttu-id="b8f64-123">MSSP 客戶必須執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b8f64-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="b8f64-124">它會授與 MSSP 存取權給 MSSP 客戶的端點租使用者的 Defender。</span><span class="sxs-lookup"><span data-stu-id="b8f64-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="b8f64-125">**設定傳送至 MSSPs 的警示通知**</span><span class="sxs-lookup"><span data-stu-id="b8f64-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="b8f64-126">MSSP 客戶或 MSSP 可以採取此項動作。</span><span class="sxs-lookup"><span data-stu-id="b8f64-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="b8f64-127">這可讓 MSSPs 知道他們必須為 MSSP 客戶解決的警示。</span><span class="sxs-lookup"><span data-stu-id="b8f64-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="b8f64-128">**將 MSSP 客戶租使用者的警示納入 SIEM 系統**</span><span class="sxs-lookup"><span data-stu-id="b8f64-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="b8f64-129">MSSP 會採取此動作。</span><span class="sxs-lookup"><span data-stu-id="b8f64-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="b8f64-130">它可讓 MSSPs 取得 SIEM 工具中的警示。</span><span class="sxs-lookup"><span data-stu-id="b8f64-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="b8f64-131">**使用 APIs 從 MSSP 客戶的承租人取得警示**</span><span class="sxs-lookup"><span data-stu-id="b8f64-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="b8f64-132">MSSP 會採取此動作。</span><span class="sxs-lookup"><span data-stu-id="b8f64-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="b8f64-133">它允許 MSSPs 使用 APIs 來取得提醒。</span><span class="sxs-lookup"><span data-stu-id="b8f64-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="b8f64-134">MSSPs 的多承租人存取權</span><span class="sxs-lookup"><span data-stu-id="b8f64-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="b8f64-135">如需如何實施多租使用者委派存取的詳細資訊，請參閱 [受管理的安全性服務提供者的多承租人存取](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)。</span><span class="sxs-lookup"><span data-stu-id="b8f64-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="b8f64-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="b8f64-136">Related topics</span></span>
- [<span data-ttu-id="b8f64-137">將入口網站存取權授予 MSSP</span><span class="sxs-lookup"><span data-stu-id="b8f64-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="b8f64-138">存取 MSSP 客戶入口網站</span><span class="sxs-lookup"><span data-stu-id="b8f64-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="b8f64-139">設定警示通知</span><span class="sxs-lookup"><span data-stu-id="b8f64-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="b8f64-140">從客戶租用戶中抓取警示</span><span class="sxs-lookup"><span data-stu-id="b8f64-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

