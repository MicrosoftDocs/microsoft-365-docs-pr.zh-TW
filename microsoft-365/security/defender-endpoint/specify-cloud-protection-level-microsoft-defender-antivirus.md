---
title: 指定雲端傳送的 Microsoft Defender 防毒軟體保護層級
description: 設定 Microsoft Defender 防毒軟體的雲端傳送保護層級。
keywords: Microsoft Defender 防毒軟體，反惡意程式碼，安全性，Defender，cloud，入侵，保護層級
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f441b1bd444cd70fb5b00dfcb5ebcddadf62b220
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274901"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="12494-104">指定雲端提供的保護層級</span><span class="sxs-lookup"><span data-stu-id="12494-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="12494-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="12494-105">**Applies to:**</span></span>

- [<span data-ttu-id="12494-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="12494-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="12494-107">您可以使用 Microsoft 端點管理員 (建議的) 或群組原則，指定 Microsoft Defender 防毒軟體所提供的雲端提供保護層級。</span><span class="sxs-lookup"><span data-stu-id="12494-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="12494-108">雲端保護不只是保護儲存在雲端中的檔案。</span><span class="sxs-lookup"><span data-stu-id="12494-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="12494-109">Microsoft Defender 防毒軟體 cloud service 是一種機制，可將更新的保護傳遞至您的網路和裝置 (也稱為端點) 。</span><span class="sxs-lookup"><span data-stu-id="12494-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="12494-110">Cloud protection with Microsoft Defender 防毒軟體會使用分散式資源和機器教學，以比傳統的安全性智慧更新更快的速率來提供對端點的保護。</span><span class="sxs-lookup"><span data-stu-id="12494-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="12494-111">Microsoft Intune 和 Microsoft 端點管理員現在是[Microsoft 端點管理員](/mem/endpoint-manager-overview)的一部分。</span><span class="sxs-lookup"><span data-stu-id="12494-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="12494-112">使用 Microsoft 端點管理員來指定雲端傳送保護的層級</span><span class="sxs-lookup"><span data-stu-id="12494-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="12494-113">請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="12494-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="12494-114">選擇 [ **Endpoint security**  >  **防病毒**]。</span><span class="sxs-lookup"><span data-stu-id="12494-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="12494-115">選取防病毒設定檔。</span><span class="sxs-lookup"><span data-stu-id="12494-115">Select an antivirus profile.</span></span> <span data-ttu-id="12494-116"> (如果您尚沒有其中一個，或若您想要建立新的設定檔，請參閱[在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="12494-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="12494-117">選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="12494-117">Select **Properties**.</span></span> <span data-ttu-id="12494-118">然後，選擇 [ **設定設定**] 旁的 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="12494-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="12494-119">展開 [ **cloud protection**]，然後在 [ **雲端提供的保護層級** ] 清單中，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="12494-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="12494-120">**High**：套用強層次的偵測。</span><span class="sxs-lookup"><span data-stu-id="12494-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="12494-121">**High plus**：使用 **高階** ，套用其他保護措施 (可能會影響用戶端效能) 。</span><span class="sxs-lookup"><span data-stu-id="12494-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="12494-122">**零容錯**：封鎖所有的未知可執行檔。</span><span class="sxs-lookup"><span data-stu-id="12494-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="12494-123">選擇 [ **審閱 + 儲存**]，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="12494-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="12494-124">需要協助嗎？</span><span class="sxs-lookup"><span data-stu-id="12494-124">Need some help?</span></span> <span data-ttu-id="12494-125">請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="12494-125">See the following resources:</span></span>
> - [<span data-ttu-id="12494-126">設定 Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="12494-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="12494-127">在 Intune 中新增 endpoint protection 設定</span><span class="sxs-lookup"><span data-stu-id="12494-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="12494-128">使用群組原則指定雲端傳送保護的層級</span><span class="sxs-lookup"><span data-stu-id="12494-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="12494-129">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]。</span><span class="sxs-lookup"><span data-stu-id="12494-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="12494-130">以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="12494-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="12494-131">在 [**群組原則管理編輯器**] 中，移至 [電腦設定]**系統**  >  **管理範本**。</span><span class="sxs-lookup"><span data-stu-id="12494-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="12494-132">展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **MpEngine**。</span><span class="sxs-lookup"><span data-stu-id="12494-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="12494-133">按兩下 [ **選取 cloud protection level** ] 設定，並將其設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="12494-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="12494-134">選取保護層級：</span><span class="sxs-lookup"><span data-stu-id="12494-134">Select the level of protection:</span></span>
    - <span data-ttu-id="12494-135">**預設封鎖層級** 提供強偵測，但不會增加偵測合法檔案的風險。</span><span class="sxs-lookup"><span data-stu-id="12494-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="12494-136">**適中的封鎖層級** 只對高度信賴的偵測提供適中功能</span><span class="sxs-lookup"><span data-stu-id="12494-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="12494-137">**高封鎖程度** 會在優化用戶端效能 (時套用強層次的偵測，但也可讓您更有可能) 誤報。</span><span class="sxs-lookup"><span data-stu-id="12494-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="12494-138">**高 + 封鎖層級** 套用額外的保護措施 (可能會影響用戶端效能，並增加誤報) 的機率。</span><span class="sxs-lookup"><span data-stu-id="12494-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="12494-139">**零容忍封鎖層級** 會封鎖所有的未知可執行檔。</span><span class="sxs-lookup"><span data-stu-id="12494-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="12494-140">雖然不太可能，將此參數設定為 **高** 或 **高的 +** 時可能會造成某些合法檔案 (，但您可以選擇取消封鎖或爭議偵測) 。</span><span class="sxs-lookup"><span data-stu-id="12494-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="12494-141">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="12494-141">Click **OK**.</span></span>

7. <span data-ttu-id="12494-142">部署更新的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="12494-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="12494-143">請參閱 [群組原則管理主控台](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="12494-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="12494-144">您是否在內部部署使用群組原則物件？</span><span class="sxs-lookup"><span data-stu-id="12494-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="12494-145">請參閱他們在雲端中的翻譯方式。</span><span class="sxs-lookup"><span data-stu-id="12494-145">See how they translate in the cloud.</span></span> <span data-ttu-id="12494-146">[在 Microsoft 端點管理員預覽中使用「群組原則分析」分析您的內部部署群組原則物件](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="12494-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="12494-147">相關文章</span><span class="sxs-lookup"><span data-stu-id="12494-147">Related articles</span></span>

- [<span data-ttu-id="12494-148">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="12494-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="12494-149">啟動雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="12494-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="12494-150">如何建立及部署反惡意程式碼原則： Cloud-protection service</span><span class="sxs-lookup"><span data-stu-id="12494-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)