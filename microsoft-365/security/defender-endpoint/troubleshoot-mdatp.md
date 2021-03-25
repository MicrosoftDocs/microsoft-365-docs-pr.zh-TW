---
title: 疑難排解 Microsoft Defender for Endpoint service 問題
description: 尋找已知問題（如嘗試存取服務時的伺服器錯誤）的解決方案和解決方法。
keywords: 疑難排解 microsoft defender for endpoint、疑難排解 Windows ATP、伺服器錯誤、拒絕存取、無效認證、沒有資料、儀表板入口網站、允許事件檢視器
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 112f682836da37ddfb51c103282518ff74563727
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186014"
---
# <a name="troubleshoot-service-issues"></a><span data-ttu-id="144ba-104">疑難排解服務問題</span><span class="sxs-lookup"><span data-stu-id="144ba-104">Troubleshoot service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="144ba-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="144ba-105">**Applies to:**</span></span>
- [<span data-ttu-id="144ba-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="144ba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="144ba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="144ba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="144ba-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="144ba-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="144ba-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="144ba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="144ba-110">本節說明當您使用 Microsoft Defender Advanced 威脅服務時可能會發生的問題。</span><span class="sxs-lookup"><span data-stu-id="144ba-110">This section addresses issues that might arise as you use the Microsoft Defender Advanced Threat service.</span></span>

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a><span data-ttu-id="144ba-111">伺服器錯誤-存取因認證無效而遭到拒絕</span><span class="sxs-lookup"><span data-stu-id="144ba-111">Server error - Access is denied due to invalid credentials</span></span>
<span data-ttu-id="144ba-112">如果您嘗試存取服務時發生伺服器錯誤，您必須變更瀏覽器 cookie 設定。</span><span class="sxs-lookup"><span data-stu-id="144ba-112">If you encounter a server error when trying to access the service, you’ll need to change your browser cookie settings.</span></span>
<span data-ttu-id="144ba-113">設定您的瀏覽器以允許 cookie。</span><span class="sxs-lookup"><span data-stu-id="144ba-113">Configure your browser to allow cookies.</span></span>

## <a name="elements-or-data-missing-on-the-portal"></a><span data-ttu-id="144ba-114">入口網站上遺失的元素或資料</span><span class="sxs-lookup"><span data-stu-id="144ba-114">Elements or data missing on the portal</span></span>
<span data-ttu-id="144ba-115">如果 Microsoft Defender Security Center 上的某些元素或資料遺失，表示 proxy 設定可以封鎖。</span><span class="sxs-lookup"><span data-stu-id="144ba-115">If some elements or data is missing on Microsoft Defender Security Center it’s possible that proxy settings are blocking it.</span></span>

<span data-ttu-id="144ba-116">請確定 `*.securitycenter.windows.com` 已包含 proxy allowlist。</span><span class="sxs-lookup"><span data-stu-id="144ba-116">Make sure that `*.securitycenter.windows.com` is included the proxy allowlist.</span></span>


> [!NOTE]
> <span data-ttu-id="144ba-117">新增下列端點時，您必須使用 HTTPS 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="144ba-117">You must use the HTTPS protocol when adding the following endpoints.</span></span>

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a><span data-ttu-id="144ba-118">Microsoft Defender for Endpoint service 會在事件檢視器中顯示事件或錯誤記錄檔</span><span class="sxs-lookup"><span data-stu-id="144ba-118">Microsoft Defender for Endpoint service shows event or error logs in the Event Viewer</span></span>

<span data-ttu-id="144ba-119">請參閱 [使用事件檢視器查看事件與錯誤](event-error-codes.md) ，以取得 Microsoft Defender for Endpoint service 所報告的事件 IDs 清單。</span><span class="sxs-lookup"><span data-stu-id="144ba-119">See [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="144ba-120">本文也包含事件錯誤的疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="144ba-120">The article also contains troubleshooting steps for event errors.</span></span>

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a><span data-ttu-id="144ba-121">重新開機後，Microsoft Defender for Endpoint service 無法啟動，並顯示錯誤577</span><span class="sxs-lookup"><span data-stu-id="144ba-121">Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577</span></span>

<span data-ttu-id="144ba-122">如果已成功完成上架裝置，但是在重新開機後，Microsoft Defender for Endpoint 不會啟動，並顯示錯誤577，請檢查 Windows Defender 未由原則停用。</span><span class="sxs-lookup"><span data-stu-id="144ba-122">If onboarding devices successfully completes but Microsoft Defender for Endpoint does not start after a reboot and shows error 577, check that Windows Defender is not disabled by a policy.</span></span>

<span data-ttu-id="144ba-123">如需詳細資訊，請參閱 [確定原則未停用 Microsoft Defender 防病毒](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="144ba-123">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

## <a name="known-issues-with-regional-formats"></a><span data-ttu-id="144ba-124">地區格式的已知問題</span><span class="sxs-lookup"><span data-stu-id="144ba-124">Known issues with regional formats</span></span>

<span data-ttu-id="144ba-125">**日期和時間格式**</span><span class="sxs-lookup"><span data-stu-id="144ba-125">**Date and time formats**</span></span><br>
<span data-ttu-id="144ba-126">時間和日期格式有一些已知的問題。</span><span class="sxs-lookup"><span data-stu-id="144ba-126">There are some known issues with the time and date formats.</span></span> 

<span data-ttu-id="144ba-127">支援下列日期格式：</span><span class="sxs-lookup"><span data-stu-id="144ba-127">The following date formats are supported:</span></span>
- <span data-ttu-id="144ba-128">MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="144ba-128">MM/dd/yyyy</span></span>
- <span data-ttu-id="144ba-129">dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="144ba-129">dd/MM/yyyy</span></span>

<span data-ttu-id="144ba-130">目前不支援下列日期和時間格式：</span><span class="sxs-lookup"><span data-stu-id="144ba-130">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="144ba-131">日期格式 yyyy/MM/dd</span><span class="sxs-lookup"><span data-stu-id="144ba-131">Date format yyyy/MM/dd</span></span>
- <span data-ttu-id="144ba-132">日期格式 dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="144ba-132">Date format dd/MM/yy</span></span>
- <span data-ttu-id="144ba-133">日期格式（yy）。</span><span class="sxs-lookup"><span data-stu-id="144ba-133">Date format with yy.</span></span> <span data-ttu-id="144ba-134">只會顯示 yyyy。</span><span class="sxs-lookup"><span data-stu-id="144ba-134">Will only show yyyy.</span></span>
- <span data-ttu-id="144ba-135">時間格式不支援 HH： mm： ss (12 小時 AM/PM 格式不受支援) 。</span><span class="sxs-lookup"><span data-stu-id="144ba-135">Time format HH:mm:ss is not supported (the 12 hour AM/PM format is not supported).</span></span> <span data-ttu-id="144ba-136">只支援24小時格式。</span><span class="sxs-lookup"><span data-stu-id="144ba-136">Only the 24-hour format is supported.</span></span>

<span data-ttu-id="144ba-137">**使用逗號表示千位數**</span><span class="sxs-lookup"><span data-stu-id="144ba-137">**Use of comma to indicate thousand**</span></span><br>
<span data-ttu-id="144ba-138">不支援使用逗點做為數位中的分隔符號。</span><span class="sxs-lookup"><span data-stu-id="144ba-138">Support of use of comma as a separator in numbers are not supported.</span></span> <span data-ttu-id="144ba-139">當地區以逗號隔開以表示一千時，將只會看到使用點做為分隔字元。</span><span class="sxs-lookup"><span data-stu-id="144ba-139">Regions where a number is separated with a comma to indicate a thousand, will only see the use of a dot as a separator.</span></span> <span data-ttu-id="144ba-140">例如，15，「15.5 K」會顯示為 K。</span><span class="sxs-lookup"><span data-stu-id="144ba-140">For example, 15,5K is displayed as 15.5K.</span></span>

><span data-ttu-id="144ba-141">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="144ba-141">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="144ba-142">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="144ba-142">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a><span data-ttu-id="144ba-143">已在歐洲自動建立 Microsoft Defender for Endpoint 租使用者</span><span class="sxs-lookup"><span data-stu-id="144ba-143">Microsoft Defender for Endpoint tenant was automatically created in Europe</span></span>
<span data-ttu-id="144ba-144">當您使用 Azure Security Center 監控伺服器時，會自動建立 Microsoft Defender for Endpoint 租使用者。</span><span class="sxs-lookup"><span data-stu-id="144ba-144">When you use Azure Security Center to monitor servers, a Microsoft Defender for Endpoint tenant is automatically created.</span></span> <span data-ttu-id="144ba-145">Microsoft Defender for Endpoint data 預設會儲存在歐洲。</span><span class="sxs-lookup"><span data-stu-id="144ba-145">The Microsoft Defender for Endpoint data is stored in Europe by default.</span></span>





## <a name="related-topics"></a><span data-ttu-id="144ba-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="144ba-146">Related topics</span></span>
- [<span data-ttu-id="144ba-147">疑難排解 Microsoft Defender 的端點上架問題</span><span class="sxs-lookup"><span data-stu-id="144ba-147">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
- [<span data-ttu-id="144ba-148">使用事件檢視器審閱事件和錯誤</span><span class="sxs-lookup"><span data-stu-id="144ba-148">Review events and errors using Event Viewer</span></span>](event-error-codes.md)
