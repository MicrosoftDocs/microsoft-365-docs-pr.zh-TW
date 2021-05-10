---
title: 開啟 Microsoft Defender 防毒軟體的通訊協定識別
description: 開啟 Microsoft Defender 防毒軟體的通訊協定識別。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，通訊協定識別
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
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296468"
---
# <a name="turn-on-protocol-recognition"></a><span data-ttu-id="f628a-104">開啟通訊協定識別</span><span class="sxs-lookup"><span data-stu-id="f628a-104">Turn on protocol recognition</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f628a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f628a-105">**Applies to:**</span></span>

- [<span data-ttu-id="f628a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f628a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f628a-107">此原則設定可讓您設定網路防護的通訊協定識別，以防範已知的漏洞。</span><span class="sxs-lookup"><span data-stu-id="f628a-107">This policy setting allows you to configure protocol recognition for network protection against exploits of known vulnerabilities.</span></span> <span data-ttu-id="f628a-108">如果您啟用或未設定此設定，則會啟用通訊協定識別。</span><span class="sxs-lookup"><span data-stu-id="f628a-108">If you enable or do not configure this setting, protocol recognition will be enabled.</span></span> <span data-ttu-id="f628a-109">如果停用此設定，就會停用通訊協定識別。</span><span class="sxs-lookup"><span data-stu-id="f628a-109">If you disable this setting, protocol recognition will be disabled.</span></span>

## <a name="use-group-policy-to-configure-protocol-recognition"></a><span data-ttu-id="f628a-110">使用群組原則來設定通訊協定識別</span><span class="sxs-lookup"><span data-stu-id="f628a-110">Use Group Policy to configure protocol recognition</span></span>

1. <span data-ttu-id="f628a-111">在您的群組原則管理端點上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]。</span><span class="sxs-lookup"><span data-stu-id="f628a-111">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="f628a-112">移至 [**電腦** 設定]  >  系統 **管理範本**  >  **Windows**  >  **Microsoft Defender 防毒軟體**  >  **網路檢查系統** 的元件。</span><span class="sxs-lookup"><span data-stu-id="f628a-112">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="f628a-113">選取 [ **通訊協定識別**]。</span><span class="sxs-lookup"><span data-stu-id="f628a-113">Select **protocol recognition**.</span></span> <span data-ttu-id="f628a-114">依預設，會啟用此原則。</span><span class="sxs-lookup"><span data-stu-id="f628a-114">By default, this policy is enabled.</span></span> <span data-ttu-id="f628a-115">若設定為 [ **未** 設定]，則會啟用定義停用。</span><span class="sxs-lookup"><span data-stu-id="f628a-115">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="f628a-116">若要編輯原則，請選取 [ **編輯原則設定** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="f628a-116">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="f628a-117">選取 [ **啟用**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f628a-117">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="f628a-118">部署更新的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="f628a-118">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="f628a-119">請參閱 [群組原則管理主控台](/windows/win32/srvnodes/group-policy)。</span><span class="sxs-lookup"><span data-stu-id="f628a-119">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="f628a-120">您是否在內部部署使用群組原則物件？</span><span class="sxs-lookup"><span data-stu-id="f628a-120">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="f628a-121">請參閱他們在雲端中的翻譯方式。</span><span class="sxs-lookup"><span data-stu-id="f628a-121">See how they translate in the cloud.</span></span> <span data-ttu-id="f628a-122">[在 Microsoft 端點管理員預覽中使用「群組原則分析」分析您的內部部署群組原則物件](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="f628a-122">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="f628a-123">相關文章</span><span class="sxs-lookup"><span data-stu-id="f628a-123">Related articles</span></span>

- [<span data-ttu-id="f628a-124">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="f628a-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="f628a-125">啟動雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="f628a-125">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="f628a-126">如何建立及部署反惡意程式碼原則： Cloud-protection service</span><span class="sxs-lookup"><span data-stu-id="f628a-126">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)