---
title: 為 Microsoft Defender 身分識別啟用評估環境、設定 MDI 實例、安裝及設定 MDI 感應器，讓 MDI 感應器偵測到本機系統管理員
description: 安裝 & 設定感應器，並在其他電腦上探索本機管理員，以在 Microsoft 365 Defender 試用實驗室或試驗環境中設定 Microsoft Defender 身分識別。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457780"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a><span data-ttu-id="c41ef-103">啟用 Microsoft Defender 身分識別的評估環境</span><span class="sxs-lookup"><span data-stu-id="c41ef-103">Enable the evaluation environment for Microsoft Defender for Identity</span></span>

<span data-ttu-id="c41ef-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c41ef-104">**Applies to:**</span></span>
- <span data-ttu-id="c41ef-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c41ef-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="c41ef-106">本文是設定 Microsoft Defender 身分識別的評估環境過程中， [步驟2之 2](eval-defender-identity-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="c41ef-106">This article is [Step 2 of 2](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="c41ef-107">如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c41ef-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="c41ef-108">使用下列步驟來設定您的 Microsoft Defender 以供身分識別環境使用。</span><span class="sxs-lookup"><span data-stu-id="c41ef-108">Use the following steps to set up your Microsoft Defender for Identity environment.</span></span> 

![在 Microsoft Defender 評估環境中啟用 Microsoft Defender 身分識別的步驟](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [<span data-ttu-id="c41ef-110">步驟1。設定用於身分識別實例的 Defender</span><span class="sxs-lookup"><span data-stu-id="c41ef-110">Step 1. Set up the Defender for Identity Instance</span></span>](#step-1-set-up-the-defender-for-identity-instance)
- [<span data-ttu-id="c41ef-111">步驟2。安裝及設定感應器</span><span class="sxs-lookup"><span data-stu-id="c41ef-111">Step 2. Install and configure the sensor</span></span>](#step-2-install-and-configure-the-sensor)
- [<span data-ttu-id="c41ef-112">步驟3。在具有感應器的電腦上設定事件記錄及 proxy 設定</span><span class="sxs-lookup"><span data-stu-id="c41ef-112">Step 3. Configure event log and proxy settings on machines with the sensor</span></span>](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [<span data-ttu-id="c41ef-113">步驟4。允許 Defender for Identity 識別其他電腦上的本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="c41ef-113">Step 4. Allow Defender for Identity to identify local admins on other computers</span></span>](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a><span data-ttu-id="c41ef-114">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="c41ef-114">Step 1.</span></span> <span data-ttu-id="c41ef-115">設定用於身分識別實例的 Defender</span><span class="sxs-lookup"><span data-stu-id="c41ef-115">Set up the Defender for Identity Instance</span></span>

<span data-ttu-id="c41ef-116">登入用於身分識別入口網站的 Defender，以建立您的實例，然後將此實例連線到您的 Active Directory 環境。</span><span class="sxs-lookup"><span data-stu-id="c41ef-116">Sign in to the Defender for Identity portal to create your instance and then connect this instance to your Active Directory environment.</span></span> 

|  |<span data-ttu-id="c41ef-117">步驟</span><span class="sxs-lookup"><span data-stu-id="c41ef-117">Step</span></span>     |<span data-ttu-id="c41ef-118">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="c41ef-118">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c41ef-119">1 </span><span class="sxs-lookup"><span data-stu-id="c41ef-119">1</span></span>     | <span data-ttu-id="c41ef-120">建立身分識別實例的 Defender</span><span class="sxs-lookup"><span data-stu-id="c41ef-120">Create the Defender for Identity instance</span></span>        | [<span data-ttu-id="c41ef-121">快速入門：建立您的 Microsoft Defender for Identity 實例</span><span class="sxs-lookup"><span data-stu-id="c41ef-121">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/defender-for-identity/install-step1)        |
|<span data-ttu-id="c41ef-122">2 </span><span class="sxs-lookup"><span data-stu-id="c41ef-122">2</span></span>     | <span data-ttu-id="c41ef-123">在 Active Directory 樹系中連線身分識別實例的 Defender</span><span class="sxs-lookup"><span data-stu-id="c41ef-123">Connect the Defender for Identity instance to your Active Directory forest</span></span>   | [<span data-ttu-id="c41ef-124">快速入門：連線至您的 Active Directory 樹系</span><span class="sxs-lookup"><span data-stu-id="c41ef-124">Quickstart: Connect to your Active Directory Forest</span></span>](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a><span data-ttu-id="c41ef-125">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="c41ef-125">Step 2.</span></span> <span data-ttu-id="c41ef-126">安裝及設定感應器</span><span class="sxs-lookup"><span data-stu-id="c41ef-126">Install and configure the sensor</span></span>

<span data-ttu-id="c41ef-127">接下來，在內部部署環境中的網域控制站和 AD FS 伺服器上，下載、安裝和設定適用于身分識別感應器的 Defender。</span><span class="sxs-lookup"><span data-stu-id="c41ef-127">Next, download, install, and configure the Defender for Identity sensor on the domain controllers and AD FS servers in your on-premises environment.</span></span>

|  |<span data-ttu-id="c41ef-128">步驟</span><span class="sxs-lookup"><span data-stu-id="c41ef-128">Step</span></span>     |<span data-ttu-id="c41ef-129">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="c41ef-129">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c41ef-130">1 </span><span class="sxs-lookup"><span data-stu-id="c41ef-130">1</span></span>     | <span data-ttu-id="c41ef-131">決定您需要的身分識別感應器的 Microsoft Defender 數目。</span><span class="sxs-lookup"><span data-stu-id="c41ef-131">Determine how many Microsoft Defender for Identity sensors you need.</span></span>        | [<span data-ttu-id="c41ef-132">規劃 Microsoft Defender 身分識別的容量</span><span class="sxs-lookup"><span data-stu-id="c41ef-132">Plan capacity for Microsoft Defender for Identity</span></span>](/defender-for-identity/capacity-planning)   |
|<span data-ttu-id="c41ef-133">2 </span><span class="sxs-lookup"><span data-stu-id="c41ef-133">2</span></span>     | <span data-ttu-id="c41ef-134">下載感應器安裝套件</span><span class="sxs-lookup"><span data-stu-id="c41ef-134">Download the sensor setup package</span></span>  |  [<span data-ttu-id="c41ef-135">快速入門：下載適用于身分識別感應器安裝套件的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c41ef-135">Quickstart: Download the Microsoft Defender for Identity sensor setup package</span></span>](/defender-for-identity/install-step3)   |
|<span data-ttu-id="c41ef-136">3 </span><span class="sxs-lookup"><span data-stu-id="c41ef-136">3</span></span>     | <span data-ttu-id="c41ef-137">安裝適用于身分識別感應器的 Defender</span><span class="sxs-lookup"><span data-stu-id="c41ef-137">Install the Defender for Identity sensor</span></span>    |  [<span data-ttu-id="c41ef-138">快速入門：安裝 Microsoft Defender for Identity 感應器</span><span class="sxs-lookup"><span data-stu-id="c41ef-138">Quickstart: Install the Microsoft Defender for Identity sensor</span></span>](/defender-for-identity/install-step4)       |
|<span data-ttu-id="c41ef-139">4 </span><span class="sxs-lookup"><span data-stu-id="c41ef-139">4</span></span>     | <span data-ttu-id="c41ef-140">設定感應器</span><span class="sxs-lookup"><span data-stu-id="c41ef-140">Configure the sensor</span></span>       |  [<span data-ttu-id="c41ef-141">設定 Microsoft Defender 的身分識別感應器設定 </span><span class="sxs-lookup"><span data-stu-id="c41ef-141">Configure Microsoft Defender for Identity sensor settings </span></span>](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a><span data-ttu-id="c41ef-142">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="c41ef-142">Step 3.</span></span> <span data-ttu-id="c41ef-143">在具有感應器的電腦上設定事件記錄及 proxy 設定</span><span class="sxs-lookup"><span data-stu-id="c41ef-143">Configure event log and proxy settings on machines with the sensor</span></span>

<span data-ttu-id="c41ef-144">在您安裝感應器的機器上，設定 Windows 事件記錄檔集合及網際網路 proxy 設定，以啟用及增強偵測功能。</span><span class="sxs-lookup"><span data-stu-id="c41ef-144">On the machines that you installed the sensor on, configure Windows event log collection and Internet proxy settings to enable and enhance detection capabilities.</span></span>

|  |<span data-ttu-id="c41ef-145">步驟</span><span class="sxs-lookup"><span data-stu-id="c41ef-145">Step</span></span>     |<span data-ttu-id="c41ef-146">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="c41ef-146">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c41ef-147">1 </span><span class="sxs-lookup"><span data-stu-id="c41ef-147">1</span></span>     | <span data-ttu-id="c41ef-148">設定 Windows 事件記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="c41ef-148">Configure Windows event log collection</span></span>         | [<span data-ttu-id="c41ef-149">設定 Windows 事件集合</span><span class="sxs-lookup"><span data-stu-id="c41ef-149">Configure Windows Event collection</span></span>](/defender-for-identity/configure-windows-event-collection)        |
|<span data-ttu-id="c41ef-150">2 </span><span class="sxs-lookup"><span data-stu-id="c41ef-150">2</span></span>     | <span data-ttu-id="c41ef-151">設定網際網路 proxy 設定</span><span class="sxs-lookup"><span data-stu-id="c41ef-151">Configure Internet proxy settings</span></span>        | [<span data-ttu-id="c41ef-152">為身分識別感應器設定 Microsoft Defender 的端點 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="c41ef-152">Configure endpoint proxy and Internet connectivity settings for your Microsoft Defender for Identity Sensor</span></span>](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a><span data-ttu-id="c41ef-153">步驟 4：</span><span class="sxs-lookup"><span data-stu-id="c41ef-153">Step 4.</span></span> <span data-ttu-id="c41ef-154">允許 Defender for Identity 識別其他電腦上的本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="c41ef-154">Allow Defender for Identity to identify local admins on other computers</span></span>

<span data-ttu-id="c41ef-155">Microsoft Defender for Identity 橫向移動路徑偵測取決於識別特定電腦上的本機系統管理員的查詢。</span><span class="sxs-lookup"><span data-stu-id="c41ef-155">Microsoft Defender for Identity lateral movement path detection relies on queries that identify local admins on specific machines.</span></span> <span data-ttu-id="c41ef-156">使用用於身分識別服務帳戶的 Defender 來執行這些查詢。</span><span class="sxs-lookup"><span data-stu-id="c41ef-156">These queries are performed with the SAM-R protocol, using the Defender for Identity Service account.</span></span> 

<span data-ttu-id="c41ef-157">為了確保 Windows 的用戶端和伺服器能夠讓您的 Defender 身分識別帳戶執行 SAM，除了網路存取原則中所列的已設定帳戶之外，還必須對群組原則進行修改，以新增身分識別服務帳戶的 defender。</span><span class="sxs-lookup"><span data-stu-id="c41ef-157">To ensure Windows clients and servers allow your Defender for Identity account to perform SAM-R, a modification to Group Policy must be made to add the Defender for Identity service account in addition to the configured accounts listed in the Network access policy.</span></span> <span data-ttu-id="c41ef-158">請務必將群組原則套用至 **除網域控制站以外** 的所有電腦。</span><span class="sxs-lookup"><span data-stu-id="c41ef-158">Make sure to apply group policies to all computers **except domain controllers**.</span></span>

<span data-ttu-id="c41ef-159">如需如何進行此作業的指示，請參閱 [Configure Microsoft Defender For Identity to to remote a to a remote 呼叫 TO SAM](/defender-for-identity/install-step8-samr)。</span><span class="sxs-lookup"><span data-stu-id="c41ef-159">For instructions on how to do this, see [Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="c41ef-160">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c41ef-160">Next steps</span></span>

<span data-ttu-id="c41ef-161">步驟3之3： [試驗 Microsoft Defender 身分識別](eval-defender-identity-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="c41ef-161">Step 3 of 3: [Pilot Microsoft Defender for Identity](eval-defender-identity-pilot.md)</span></span>

<span data-ttu-id="c41ef-162">回到概述以 [評估 Microsoft Defender 身分識別](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c41ef-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="c41ef-163">回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述</span><span class="sxs-lookup"><span data-stu-id="c41ef-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>