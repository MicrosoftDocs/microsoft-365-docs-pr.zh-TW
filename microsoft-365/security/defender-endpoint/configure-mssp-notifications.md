---
title: 設定傳送至 MSSPs 的警示通知
description: 設定傳送至 MSSPs 的警示通知
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166050"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a><span data-ttu-id="38707-104">設定傳送至 MSSPs 的警示通知</span><span class="sxs-lookup"><span data-stu-id="38707-104">Configure alert notifications that are sent to MSSPs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="38707-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="38707-105">**Applies to:**</span></span>
- [<span data-ttu-id="38707-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="38707-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="38707-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38707-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="38707-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="38707-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="38707-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="38707-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
><span data-ttu-id="38707-110">此步驟可由 MSSP 客戶或 MSSP 執行。</span><span class="sxs-lookup"><span data-stu-id="38707-110">This step can be done by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="38707-111">MSSPs 必須獲得適當的許可權，才可代表 MSSP 客戶進行這項設定。</span><span class="sxs-lookup"><span data-stu-id="38707-111">MSSPs must be granted the appropriate permissions to configure this on behalf of the MSSP customer.</span></span>

<span data-ttu-id="38707-112">存取入口網站後，就可以建立警示通知規則，以便在建立與租使用者相關聯的提醒時，將電子郵件傳送至 MSSPs，並符合設定的條件。</span><span class="sxs-lookup"><span data-stu-id="38707-112">After access the portal is granted, alert notification rules can to be created so that emails are sent to MSSPs when alerts associated with the tenant are created and set conditions are met.</span></span>

 
<span data-ttu-id="38707-113">如需詳細資訊，請參閱 [建立警示通知的規則](configure-email-notifications.md#create-rules-for-alert-notifications)。</span><span class="sxs-lookup"><span data-stu-id="38707-113">For more information, see [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span></span>
 

<span data-ttu-id="38707-114">必須勾選這些核取方塊：</span><span class="sxs-lookup"><span data-stu-id="38707-114">These check boxes must be checked:</span></span>
- <span data-ttu-id="38707-115">**包含組織名稱** -客戶名稱將新增至電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="38707-115">**Include organization name** - The customer name will be added to email notifications</span></span>
- <span data-ttu-id="38707-116">**包含租使用者的入口網站連結** -警示連結 URL 會有租使用者特定參數 (tid = target_tenant_id) 允許直接存取目標租使用者入口網站</span><span class="sxs-lookup"><span data-stu-id="38707-116">**Include tenant-specific portal link** - Alert link URL will have tenant specific parameter (tid=target_tenant_id) that allows direct access to target tenant portal</span></span>


## <a name="related-topics"></a><span data-ttu-id="38707-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="38707-117">Related topics</span></span>
- [<span data-ttu-id="38707-118">授與 MSSP 存取入口網站</span><span class="sxs-lookup"><span data-stu-id="38707-118">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="38707-119">存取 MSSP 客戶入口網站</span><span class="sxs-lookup"><span data-stu-id="38707-119">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="38707-120">從客戶租使用者提取警示</span><span class="sxs-lookup"><span data-stu-id="38707-120">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
