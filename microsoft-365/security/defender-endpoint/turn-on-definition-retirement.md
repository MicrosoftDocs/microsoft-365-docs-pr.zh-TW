---
title: 開啟 Microsoft Defender 防毒軟體的定義停用
description: 為 Microsoft Defender 防毒軟體開啟定義停用。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，定義停用
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 505270d319a78de20bf6fed01b7ca79c9fc2b400
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903801"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="9122d-104">開啟定義停用</span><span class="sxs-lookup"><span data-stu-id="9122d-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9122d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9122d-105">**Applies to:**</span></span>

- [<span data-ttu-id="9122d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9122d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9122d-107">您可以使用「群組原則」設定定義停用。</span><span class="sxs-lookup"><span data-stu-id="9122d-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="9122d-108">定義停用檢查是否有必要的安全性更新，以查看電腦是否有必要的必要安全性更新，以防範特定弱點。</span><span class="sxs-lookup"><span data-stu-id="9122d-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="9122d-109">如果系統不容易受到定義所偵測到的入侵，則該定義為「已撤銷」。</span><span class="sxs-lookup"><span data-stu-id="9122d-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="9122d-110">如果已停用指定通訊協定的所有安全性智慧，則不再會分析該通訊協定。</span><span class="sxs-lookup"><span data-stu-id="9122d-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="9122d-111">啟用此功能有助於提升效能。</span><span class="sxs-lookup"><span data-stu-id="9122d-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="9122d-112">在最新安全性更新的最新電腦上，網路保護將不會影響網路效能。</span><span class="sxs-lookup"><span data-stu-id="9122d-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="9122d-113">使用群組原則設定定義退休</span><span class="sxs-lookup"><span data-stu-id="9122d-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="9122d-114">在您的群組原則管理端點上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]。</span><span class="sxs-lookup"><span data-stu-id="9122d-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="9122d-115">移至 [**電腦** 設定]  >  系統 **管理範本**  >  **Windows**  >  **Microsoft Defender 防毒軟體**  >  **網路檢查系統** 的元件。</span><span class="sxs-lookup"><span data-stu-id="9122d-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="9122d-116">選取 [ **開啟定義停** 用]。</span><span class="sxs-lookup"><span data-stu-id="9122d-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="9122d-117">依預設，會啟用此原則。</span><span class="sxs-lookup"><span data-stu-id="9122d-117">By default, this policy is enabled.</span></span> <span data-ttu-id="9122d-118">若設定為 [ **未** 設定]，則會啟用定義停用。</span><span class="sxs-lookup"><span data-stu-id="9122d-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="9122d-119">若要編輯原則，請選取 [ **編輯原則設定** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="9122d-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="9122d-120">選取 [ **啟用**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9122d-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="9122d-121">部署更新的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="9122d-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="9122d-122">請參閱 [群組原則管理主控台](/windows/win32/srvnodes/group-policy)。</span><span class="sxs-lookup"><span data-stu-id="9122d-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="9122d-123">您是否在內部部署使用群組原則物件？</span><span class="sxs-lookup"><span data-stu-id="9122d-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="9122d-124">請參閱他們在雲端中的翻譯方式。</span><span class="sxs-lookup"><span data-stu-id="9122d-124">See how they translate in the cloud.</span></span> <span data-ttu-id="9122d-125">[在 Microsoft 端點管理員預覽中使用「群組原則分析」分析您的內部部署群組原則物件](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="9122d-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
