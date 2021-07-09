---
title: 存取 Microsoft 365 Defender MSSP 客戶入口網站
description: 存取 Microsoft 365 Defender MSSP 客戶入口網站
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
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339583"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a><span data-ttu-id="ac807-104">存取 Microsoft 365 Defender MSSP 客戶入口網站</span><span class="sxs-lookup"><span data-stu-id="ac807-104">Access the Microsoft 365 Defender MSSP customer portal</span></span>

<span data-ttu-id="ac807-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ac807-105">**Applies to:**</span></span>
- [<span data-ttu-id="ac807-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ac807-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ac807-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac807-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ac807-108">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ac807-108">**Applies to:**</span></span>

- [<span data-ttu-id="ac807-109">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ac807-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="ac807-110">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="ac807-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ac807-111">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ac807-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="ac807-112">這些步驟組會向 MSSP 導向。</span><span class="sxs-lookup"><span data-stu-id="ac807-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="ac807-113">根據預設，MSSP 客戶會透過下列 URL: 存取其 Microsoft Defender 資訊安全中心承租人 `https://securitycenter.windows.com` 。</span><span class="sxs-lookup"><span data-stu-id="ac807-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="ac807-114">MSSPs 不過，將需要使用下列格式的承租人特定 URL：  `https://securitycenter.windows.com?tid=customer_tenant_id` 存取 MSSP 客戶入口網站。</span><span class="sxs-lookup"><span data-stu-id="ac807-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="ac807-115">一般說來，MSSPs 將需要新增至他們想要管理的每一個 MSSP 客戶的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="ac807-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="ac807-116">使用下列步驟取得 MSSP 客戶租使用者識別碼，然後使用識別碼來存取租使用者特定的 URL:</span><span class="sxs-lookup"><span data-stu-id="ac807-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="ac807-117">MSSP，使用您的認證登入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="ac807-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="ac807-118">切換目錄至 MSSP 客戶的承租人。</span><span class="sxs-lookup"><span data-stu-id="ac807-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="ac807-119">選取 [ **Azure Active Directory > 屬性**]。</span><span class="sxs-lookup"><span data-stu-id="ac807-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="ac807-120">您會在 [目錄識別碼] 欄位中找到租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="ac807-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="ac807-121">取代下列 URL: 中的值，以存取 MSSP 客戶入口網站 `customer_tenant_id` `https://securitycenter.windows.com?tid=customer_tenant_id` 。</span><span class="sxs-lookup"><span data-stu-id="ac807-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ac807-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="ac807-122">Related topics</span></span>
- [<span data-ttu-id="ac807-123">將入口網站存取權授予 MSSP</span><span class="sxs-lookup"><span data-stu-id="ac807-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="ac807-124">設定警示通知</span><span class="sxs-lookup"><span data-stu-id="ac807-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="ac807-125">從客戶租用戶中抓取警示</span><span class="sxs-lookup"><span data-stu-id="ac807-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
