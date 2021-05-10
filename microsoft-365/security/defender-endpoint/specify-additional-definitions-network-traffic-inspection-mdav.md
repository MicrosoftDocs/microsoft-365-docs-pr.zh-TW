---
title: 為 Microsoft Defender 防毒軟體的網路流量檢查指定其他定義集
description: 為 Microsoft Defender 防毒軟體的網路流量檢查指定其他定義集。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，網路流量檢查
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300142"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="50161-104">指定網路流量檢查的其他定義集</span><span class="sxs-lookup"><span data-stu-id="50161-104">Specify additional definition sets for network traffic inspection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="50161-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="50161-105">**Applies to:**</span></span>

- [<span data-ttu-id="50161-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="50161-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="50161-107">您可以使用群組原則，為網路流量檢查指定其他定義集。</span><span class="sxs-lookup"><span data-stu-id="50161-107">You can specify additional definition sets for network traffic inspection using Group Policy.</span></span>

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="50161-108">使用群組原則指定網路流量檢查的其他定義集</span><span class="sxs-lookup"><span data-stu-id="50161-108">Use Group Policy to specify additional definition sets for network traffic inspection</span></span>

1. <span data-ttu-id="50161-109">在您的群組原則管理端點上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]。</span><span class="sxs-lookup"><span data-stu-id="50161-109">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="50161-110">移至 **Windows**  >  **Microsoft Defender 防毒軟體**  >  **網路檢查系統** 的元件。</span><span class="sxs-lookup"><span data-stu-id="50161-110">Go to **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="50161-111">選取 [ **指定網路流量檢查的其他定義集**]。</span><span class="sxs-lookup"><span data-stu-id="50161-111">Select **Specify additional definition sets for network traffic inspection**.</span></span> <span data-ttu-id="50161-112">根據預設，此原則會設定為 [ **未** 設定]。</span><span class="sxs-lookup"><span data-stu-id="50161-112">By default, this policy is set to **Not configured**.</span></span> 

4. <span data-ttu-id="50161-113">若要編輯原則，請選取 [ **編輯原則設定** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="50161-113">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="50161-114">選取 [ **啟用**]，然後在 [ **選項** ] 區段中，選取 [ **顯示 ...**]。</span><span class="sxs-lookup"><span data-stu-id="50161-114">Select **Enabled**, and then in the **Options** section, select **Show...**.</span></span>

6. <span data-ttu-id="50161-115">將專案新增至清單，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="50161-115">Add entries to the list, and then select **OK**.</span></span> 

   <span data-ttu-id="50161-116">每個專案都必須以名稱-值對列出，其中名稱是定義集 GUID 的字串標記法。</span><span class="sxs-lookup"><span data-stu-id="50161-116">Each entry must be listed as a name-value pair, where the name is a string representation of a definition set GUID.</span></span> <span data-ttu-id="50161-117">舉例來說，enable test security 情報的定義集 GUID 是定義為： `{b54b6ac9-a737-498e-9120-6616ad3bf590}` 。</span><span class="sxs-lookup"><span data-stu-id="50161-117">As an example, the definition set GUID to enable test security intelligence is defined as: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`.</span></span> <span data-ttu-id="50161-118">未使用此值，因此建議將其設定為 `0` 。</span><span class="sxs-lookup"><span data-stu-id="50161-118">The value is not used, so we recommend setting it to `0`.</span></span> 

7. <span data-ttu-id="50161-119">請選取 **[確定]**，然後再部署更新的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="50161-119">Select **OK**, and then deploy your updated Group Policy Object.</span></span> <span data-ttu-id="50161-120">請參閱 [群組原則管理主控台](/windows/win32/srvnodes/group-policy)。</span><span class="sxs-lookup"><span data-stu-id="50161-120">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="50161-121">您是否在內部部署使用群組原則物件？</span><span class="sxs-lookup"><span data-stu-id="50161-121">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="50161-122">請參閱他們在雲端中的翻譯方式。</span><span class="sxs-lookup"><span data-stu-id="50161-122">See how they translate in the cloud.</span></span> <span data-ttu-id="50161-123">[在 Microsoft 端點管理員預覽中使用「群組原則分析」分析您的內部部署群組原則物件](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="50161-123">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="50161-124">相關文章</span><span class="sxs-lookup"><span data-stu-id="50161-124">Related articles</span></span>

- [<span data-ttu-id="50161-125">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="50161-125">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="50161-126">啟動雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="50161-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="50161-127">如何建立及部署反惡意程式碼原則： Cloud-protection service</span><span class="sxs-lookup"><span data-stu-id="50161-127">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)