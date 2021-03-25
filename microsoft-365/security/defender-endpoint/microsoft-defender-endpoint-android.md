---
title: 適用于 Android 的 Microsoft Defender ATP
ms.reviewer: ''
description: 說明如何安裝和使用適用于 Android 的 Microsoft Defender ATP
keywords: microsoft、defender、atp、android、安裝、部署、卸載、intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e2432dc4aa2c67fadc9112512a080f24c0064df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187610"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="36980-104">適用于 Android 的 Microsoft Defender Endpoint</span><span class="sxs-lookup"><span data-stu-id="36980-104">Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="36980-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="36980-105">**Applies to:**</span></span>
- [<span data-ttu-id="36980-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="36980-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="36980-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36980-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="36980-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="36980-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="36980-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="36980-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="36980-110">本主題說明如何針對 Android 安裝、設定、更新和使用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="36980-110">This topic describes how to install, configure, update, and use Defender for Endpoint for Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="36980-111">針對 Android 的 Endpoint for Endpoint 執行其他協力廠商端點保護產品可能會造成效能問題和不可預期的系統錯誤。</span><span class="sxs-lookup"><span data-stu-id="36980-111">Running other third-party endpoint protection products alongside Defender for Endpoint for Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="36980-112">如何為 Android 安裝 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="36980-112">How to install Microsoft Defender for Endpoint for Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="36980-113">必要條件</span><span class="sxs-lookup"><span data-stu-id="36980-113">Prerequisites</span></span>

-   <span data-ttu-id="36980-114">**使用者的**</span><span class="sxs-lookup"><span data-stu-id="36980-114">**For end users**</span></span>

    -   <span data-ttu-id="36980-115">指派給使用者 (s) 的 Microsoft Defender Endpoint 授權。</span><span class="sxs-lookup"><span data-stu-id="36980-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="36980-116">請參閱 [Microsoft Defender 的 Endpoint 授權需求](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="36980-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="36980-117">Intune 公司入口網站應用程式可從 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 下載，且可用於 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="36980-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="36980-118">此外，裝置 (s) 可以透過 Intune 公司入口網站進行 [註冊](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) ，以強制執行 intune 裝置相容性原則。</span><span class="sxs-lookup"><span data-stu-id="36980-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="36980-119">這需要將使用者指派為 Microsoft Intune 授權。</span><span class="sxs-lookup"><span data-stu-id="36980-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="36980-120">如需如何指派授權的詳細資訊，請參閱 [將授權指派給使用者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="36980-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="36980-121">**針對系統管理員**</span><span class="sxs-lookup"><span data-stu-id="36980-121">**For Administrators**</span></span>

    -   <span data-ttu-id="36980-122">存取 Microsoft Defender Security Center 入口網站。</span><span class="sxs-lookup"><span data-stu-id="36980-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="36980-123">Microsoft Intune 是唯一支援的行動裝置管理 (MDM) 解決方案，可為 Android 部署 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="36980-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for Android.</span></span> <span data-ttu-id="36980-124">目前只有已註冊的裝置才支援在 Intune 中強制執行 Android 相關裝置相容性原則的端點。</span><span class="sxs-lookup"><span data-stu-id="36980-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint for Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="36980-125">存取 [Microsoft 端點管理員管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，將應用程式部署至組織中已註冊的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="36980-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="36980-126">系統需求</span><span class="sxs-lookup"><span data-stu-id="36980-126">System Requirements</span></span>

-   <span data-ttu-id="36980-127">執行 Android 6.0 和更新版本的 android 裝置。</span><span class="sxs-lookup"><span data-stu-id="36980-127">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="36980-128">Intune 公司入口網站應用程式從 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 和安裝中下載。</span><span class="sxs-lookup"><span data-stu-id="36980-128">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="36980-129">需要有裝置註冊，才能強制執行 Intune 裝置合規性原則。</span><span class="sxs-lookup"><span data-stu-id="36980-129">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="36980-130">安裝指示</span><span class="sxs-lookup"><span data-stu-id="36980-130">Installation instructions</span></span>

<span data-ttu-id="36980-131">適用于 Android 的 Microsoft Defender Endpoint 支援在已註冊裝置的兩種模式上安裝-傳統裝置管理員和 Android 企業模式。</span><span class="sxs-lookup"><span data-stu-id="36980-131">Microsoft Defender for Endpoint for Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="36980-132">**目前，在 Android Enterprise 中支援具有工作設定檔及公司所擁有的完整管理使用者裝置 enrolments 的個人擁有裝置。在準備好時，將會宣佈對其他 Android 企業模式的支援。**</span><span class="sxs-lookup"><span data-stu-id="36980-132">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrolments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="36980-133">Microsoft Intune for Android 的部署是透過 Microsoft Intune (MDM) 進行部署。</span><span class="sxs-lookup"><span data-stu-id="36980-133">Deployment of Microsoft Defender for Endpoint for Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="36980-134">如需詳細資訊，請參閱 [使用 Microsoft Intune 部署適用于 Android 的 Microsoft Defender For Endpoint](android-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="36980-134">For more information, see [Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="36980-135">**[Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)現在已提供適用于 Android 的 Microsoft Defender 端點。**</span><span class="sxs-lookup"><span data-stu-id="36980-135">**Microsoft Defender for Endpoint for Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="36980-136">您可以從 Intune 連線到 Google，以部署 Microsoft Defender for Endpoint 應用程式、跨裝置管理員和 Android Enterprise entrollment 模式。</span><span class="sxs-lookup"><span data-stu-id="36980-136">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="36980-137">如何設定適用于 Android 的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="36980-137">How to Configure Microsoft Defender for Endpoint for Android</span></span>

<span data-ttu-id="36980-138">設定適用于 android 功能的 [microsoft](android-configure.md)defender for endpoint 功能的指導方針。</span><span class="sxs-lookup"><span data-stu-id="36980-138">Guidance on how to configure Microsoft Defender for Endpoint for Android features is available in [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="36980-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="36980-139">Related topics</span></span>
- [<span data-ttu-id="36980-140">使用 Microsoft Intune 部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="36980-140">Deploy Microsoft Defender for Endpoint for with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="36980-141">針對 Android 功能設定 Microsoft Defender for Endpoint 功能</span><span class="sxs-lookup"><span data-stu-id="36980-141">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)

