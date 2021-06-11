---
title: iOS 上適用於端點的 Microsoft Defender
ms.reviewer: ''
description: 說明如何在 iOS 上安裝及使用 Microsoft Defender for Endpoint
keywords: microsoft，defender，Microsoft Defender for Endpoint，ios，綜述，安裝，部署，卸載，intune
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b4c2d586cd23a346db1bcebf891689ff648b639b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844703"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="54ed0-104">iOS 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="54ed0-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54ed0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="54ed0-105">**Applies to:**</span></span>
- [<span data-ttu-id="54ed0-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="54ed0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="54ed0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54ed0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="54ed0-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="54ed0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="54ed0-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="54ed0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="54ed0-110">**IOS 上的 Microsoft Defender For Endpoint** 會提供保護，以防範來自網站、電子郵件和應用程式的網路釣魚和不安全網路連線。</span><span class="sxs-lookup"><span data-stu-id="54ed0-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="54ed0-111">所有警示都會透過 Microsoft Defender 資訊安全中心中的單一玻璃窗格獲得。</span><span class="sxs-lookup"><span data-stu-id="54ed0-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="54ed0-112">入口網站讓安全性小組能夠集中查看 iOS 裝置上的威脅及其他平臺。</span><span class="sxs-lookup"><span data-stu-id="54ed0-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="54ed0-113">對 iOS 上的 Endpoint for Endpoint 執行其他協力廠商端點保護產品時，可能會造成效能問題和不可預期的系統錯誤。</span><span class="sxs-lookup"><span data-stu-id="54ed0-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="54ed0-114">先決條件</span><span class="sxs-lookup"><span data-stu-id="54ed0-114">Pre-requisites</span></span>

<span data-ttu-id="54ed0-115">**使用者的**</span><span class="sxs-lookup"><span data-stu-id="54ed0-115">**For End Users**</span></span>

- <span data-ttu-id="54ed0-116">指派給使用者 (s) 的 Microsoft Defender Endpoint 授權。</span><span class="sxs-lookup"><span data-stu-id="54ed0-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="54ed0-117">請參閱 [Microsoft Defender Endpoint 授權需求](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="54ed0-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="54ed0-118">裝置 (s) 會透過 Intune 公司入口網站應用程式進行[註冊](/mem/intune/user-help/enroll-your-device-in-intune-ios)，以強制執行 Intune 裝置相容性原則。</span><span class="sxs-lookup"><span data-stu-id="54ed0-118">Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="54ed0-119">這需要 Microsoft Intune 授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="54ed0-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="54ed0-120">Intune 公司入口網站應用程式可從[Apple 應用程式存放區](https://apps.apple.com/us/app/intune-company-portal/id719171358)下載。</span><span class="sxs-lookup"><span data-stu-id="54ed0-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="54ed0-121">請注意，Apple 不允許重新導向使用者從應用程式存放區下載其他應用程式，因此必須在使用者執行此步驟後，才能上架至 Microsoft Defender for Endpoint 應用程式。</span><span class="sxs-lookup"><span data-stu-id="54ed0-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="54ed0-122">如需如何指派授權的詳細資訊，請參閱 [將授權指派給使用者](/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="54ed0-122">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="54ed0-123">**針對系統管理員**</span><span class="sxs-lookup"><span data-stu-id="54ed0-123">**For Administrators**</span></span>

- <span data-ttu-id="54ed0-124">存取 Microsoft Defender 資訊安全中心入口網站。</span><span class="sxs-lookup"><span data-stu-id="54ed0-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="54ed0-125">Microsoft Intune 是唯一支援的整合端點管理 (UEM) 方案，可在 Intune 中部署 Microsoft Defender for endpoint，並強制執行與 Endpoint 相關之裝置相容性原則的 Defender。</span><span class="sxs-lookup"><span data-stu-id="54ed0-125">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

- <span data-ttu-id="54ed0-126">存取[Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，將應用程式部署至組織中已註冊的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="54ed0-126">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="54ed0-127">**系統需求**</span><span class="sxs-lookup"><span data-stu-id="54ed0-127">**System Requirements**</span></span>

- <span data-ttu-id="54ed0-128">執行 iOS 11.0 和更新版本的裝置 iOS。</span><span class="sxs-lookup"><span data-stu-id="54ed0-128">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="54ed0-129">iPad 的裝置從版本1.1.15010101 向前正式支援。</span><span class="sxs-lookup"><span data-stu-id="54ed0-129">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="54ed0-130">已使用[Intune 公司入口網站 app](https://apps.apple.com/us/app/intune-company-portal/id719171358)註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="54ed0-130">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="54ed0-131">安裝指示</span><span class="sxs-lookup"><span data-stu-id="54ed0-131">Installation instructions</span></span>

<span data-ttu-id="54ed0-132">在 iOS 上部署 Microsoft Defender for Endpoint 是透過 Microsoft Intune (MDM) ，且支援受監視和 unsupervised 裝置。</span><span class="sxs-lookup"><span data-stu-id="54ed0-132">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="54ed0-133">使用者也可以直接從 [Apple app store](https://aka.ms/mdatpiosappstore)安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="54ed0-133">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="54ed0-134">如需詳細資訊，請參閱 [在 iOS 上部署 Microsoft Defender For Endpoint](ios-install.md)。</span><span class="sxs-lookup"><span data-stu-id="54ed0-134">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="54ed0-135">資源</span><span class="sxs-lookup"><span data-stu-id="54ed0-135">Resources</span></span>

- <span data-ttu-id="54ed0-136">在 iOS 或我們的[博客](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)上，造訪[Microsoft Defender for Endpoint 中的新功能](ios-whatsnew.md)，以瞭解即將推出的版本。</span><span class="sxs-lookup"><span data-stu-id="54ed0-136">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="54ed0-137">透過應用程式內的意見反應系統或透過[SecOps 入口網站](https://securitycenter.microsoft.com)提供意見反應</span><span class="sxs-lookup"><span data-stu-id="54ed0-137">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="54ed0-138">後續步驟</span><span class="sxs-lookup"><span data-stu-id="54ed0-138">Next steps</span></span>

- [<span data-ttu-id="54ed0-139">在 iOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="54ed0-139">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="54ed0-140">在 iOS 功能上設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="54ed0-140">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
