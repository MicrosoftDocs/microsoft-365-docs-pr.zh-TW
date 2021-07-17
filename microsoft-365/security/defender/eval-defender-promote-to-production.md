---
title: 將 Microsoft 365 Defender 評估環境提升為生產環境、Microsoft 365 Defender 評估、試用評估、保持評估、產品評估
description: 您可以使用本文，將 evals 的 MDI、MDO、MDE 和 MCAS 提升為 Microsoft 365 Defender 或 M365D 的實際執行環境。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457908"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a><span data-ttu-id="3697a-103">將您的 Microsoft 365 Defender 評估環境推廣至實際執行環境</span><span class="sxs-lookup"><span data-stu-id="3697a-103">Promote your Microsoft 365 Defender evaluation environment to production</span></span>

<span data-ttu-id="3697a-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3697a-104">**Applies to:**</span></span>
- <span data-ttu-id="3697a-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3697a-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="3697a-106">若要將 Microsoft 365 Defender 評估環境提升為生產環境，請先購買必要的授權。</span><span class="sxs-lookup"><span data-stu-id="3697a-106">To promote your Microsoft 365 Defender evaluation environment to production, first purchase the necessary license.</span></span> <span data-ttu-id="3697a-107">遵循 [[建立 eval 環境](eval-create-eval-environment.md)] 中的步驟，並購買 Office 365 E5 授權 (，而不是選取 [開始免費試用版) ]。</span><span class="sxs-lookup"><span data-stu-id="3697a-107">Follow the steps in [Create the eval environment](eval-create-eval-environment.md) and purchase the Office 365 E5 license (instead of selecting Start free trial).</span></span>

<span data-ttu-id="3697a-108">接下來，完成任何其他設定，然後展開您的試驗群組，直到這些專案都已到達完整生產環境為止。</span><span class="sxs-lookup"><span data-stu-id="3697a-108">Next, complete any additional configuration and expand your pilot groups until these have reached full production.</span></span> 

## <a name="microsoft-defender-for-identity"></a><span data-ttu-id="3697a-109">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3697a-109">Microsoft Defender for Identity</span></span>
<span data-ttu-id="3697a-110">用於身分識別的 Defender 不需要任何其他設定。</span><span class="sxs-lookup"><span data-stu-id="3697a-110">Defender for Identity doesn't require any additional configuration.</span></span> <span data-ttu-id="3697a-111">請確認您已購買必要的授權，並已在所有 Active Directory 網域控制站和 Active Directory Federation Services (AD FS) 伺服器上安裝了該感應器。</span><span class="sxs-lookup"><span data-stu-id="3697a-111">Just make sure you've purchased the necessary licenses and installed the sensor on all of your Active Directory domain controllers and Active Directory Federation Services (AD FS) servers.</span></span> 

## <a name="microsoft-defender-for-office-365"></a><span data-ttu-id="3697a-112">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3697a-112">Microsoft Defender for Office 365</span></span>
<span data-ttu-id="3697a-113">在成功評估或試驗 MDO 後，可以將它提升至整個實際執行環境。</span><span class="sxs-lookup"><span data-stu-id="3697a-113">After successfully evaluating or piloting MDO, it can be promoted to your entire production environment.</span></span>
1. <span data-ttu-id="3697a-114">購買及布建必要的授權，並將其指派給實際執行使用者。</span><span class="sxs-lookup"><span data-stu-id="3697a-114">Purchase and provision the necessary licenses and assign them to your production users.</span></span>
2. <span data-ttu-id="3697a-115">針對您的實際執行的電子郵件網域或特定使用者群組，重新執行建議的基準原則設定 (標準或嚴格) 。</span><span class="sxs-lookup"><span data-stu-id="3697a-115">Re-run recommended baseline policy configurations (either Standard or Strict) against your production email domain or specific groups of users.</span></span>
3. <span data-ttu-id="3697a-116">（選用）建立及設定您的實際執行電子郵件網域或使用者群組的任何自訂 MDO 原則。</span><span class="sxs-lookup"><span data-stu-id="3697a-116">Optionally create and configure any custom MDO policies against your production email domain or groups of users.</span></span>  <span data-ttu-id="3697a-117">不過，請記住，任何已指定的基準原則，都一定優先于自訂原則。</span><span class="sxs-lookup"><span data-stu-id="3697a-117">However, remember that any assigned baseline policies will always take precedence over custom policies.</span></span>
4. <span data-ttu-id="3697a-118">更新實際執行電子郵件網域的公用 MX 記錄，以直接解析為 EOP。</span><span class="sxs-lookup"><span data-stu-id="3697a-118">Update the public MX record for your production email domain to resolve directly to EOP.</span></span>
5. <span data-ttu-id="3697a-119">解除委任任何協力廠商 SMTP 閘道，並停用或刪除與此轉送相關的任何 EXO 連接器。</span><span class="sxs-lookup"><span data-stu-id="3697a-119">Decommission any third-party SMTP gateways and disable or delete any EXO connectors associated with this relay.</span></span>

## <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="3697a-120">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3697a-120">Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="3697a-121">若要將 Microsoft Defender 用於端點評估環境從試驗提升為生產環境，只需要使用任何 [支援的工具和方法](/defender-endpoint/onboard-configure)，將更多端點放入服務。</span><span class="sxs-lookup"><span data-stu-id="3697a-121">To promote Microsoft Defender for Endpoint evaluation environment from a pilot to production, simply onboard more endpoints to the service using any of the [supported tools and methods](/defender-endpoint/onboard-configure).</span></span>

<span data-ttu-id="3697a-122">請使用下列一般指導方針，將更多裝置板載至 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="3697a-122">Use the following general guidelines to onboard more devices to Microsoft Defender for Endpoint.</span></span> 

1. <span data-ttu-id="3697a-123">確認裝置可滿足 [最低需求](/defender-endpoint/minimum-requirements)。</span><span class="sxs-lookup"><span data-stu-id="3697a-123">Verify that the device fulfills the [minimum requirements](/defender-endpoint/minimum-requirements).</span></span>
2. <span data-ttu-id="3697a-124">視裝置而定，請遵循在端點入口網站的 [上架] 區段中所提供的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="3697a-124">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal.</span></span>
3. <span data-ttu-id="3697a-125">針對您的裝置使用適當的管理工具和部署方法。</span><span class="sxs-lookup"><span data-stu-id="3697a-125">Use the appropriate management tool and deployment method for your devices.</span></span>
4.  <span data-ttu-id="3697a-126">執行偵測測試，確認裝置已正確架及報表服務。</span><span class="sxs-lookup"><span data-stu-id="3697a-126">Run a detection test to verify that the devices are properly onboarded and reporting to the service.</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="3697a-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3697a-127">Microsoft Cloud App Security</span></span>
<span data-ttu-id="3697a-128">Microsoft Cloud App Security 不需要任何其他設定。</span><span class="sxs-lookup"><span data-stu-id="3697a-128">Microsoft Cloud App Security doesn't require any additional configuration.</span></span> <span data-ttu-id="3697a-129">請務必確認您已購買必要的授權。</span><span class="sxs-lookup"><span data-stu-id="3697a-129">Just make sure you've purchased the necessary licenses.</span></span> <span data-ttu-id="3697a-130">如果您已將部署的範圍設定為特定使用者群組，請增加這些群組的範圍，直到您達到實際執行規模為止。</span><span class="sxs-lookup"><span data-stu-id="3697a-130">If you've scoped the deployment to certain user groups, increase the scope of these groups until you reach production scale.</span></span> 

