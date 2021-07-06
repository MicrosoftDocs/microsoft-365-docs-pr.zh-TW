---
title: 使用非 Microsoft cloud app 的資料遺失防護原則
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何對非 Microsoft cloud app 使用 dlp 原則。
ms.openlocfilehash: fbba87fc5bb3bbca7e67ba374e202098a22f4a5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300121"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="eebd5-103">使用非 Microsoft cloud app 的資料遺失防護原則 (預覽) </span><span class="sxs-lookup"><span data-stu-id="eebd5-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="eebd5-104">資料遺失防護 (dlp) 原則的非 Microsoft cloud app 屬於 Microsoft 365 DLP 套件的一部分;您可以使用這些功能，在 Microsoft 365 服務中探索和保護機密專案。</span><span class="sxs-lookup"><span data-stu-id="eebd5-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="eebd5-105">如需所有 Microsoft DLP 產品的詳細資訊，請參閱 [瞭解資料遺失防護](dlp-learn-about-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="eebd5-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="eebd5-106">您可以使用 DLP 原則來監視和偵測敏感專案何時使用，並透過非 Microsoft cloud app 加以共用。</span><span class="sxs-lookup"><span data-stu-id="eebd5-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="eebd5-107">使用這些原則可提供您所需的可見度和控制，以確保它們已正確使用和受到保護，並可協助防範可能會損損的危險行為。</span><span class="sxs-lookup"><span data-stu-id="eebd5-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="eebd5-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="eebd5-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="eebd5-109">SKU/訂閱授權</span><span class="sxs-lookup"><span data-stu-id="eebd5-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="eebd5-110">開始使用 DLP 原則至非 Microsoft cloud app 之前，請先確認您的[Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)和任何附加元件。</span><span class="sxs-lookup"><span data-stu-id="eebd5-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="eebd5-111">若要存取及使用此功能，您必須具有下列其中一項訂閱或附加元件：</span><span class="sxs-lookup"><span data-stu-id="eebd5-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="eebd5-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="eebd5-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="eebd5-113">Microsoft 365 E5 合規性</span><span class="sxs-lookup"><span data-stu-id="eebd5-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="eebd5-114">Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="eebd5-114">Microsoft 365 E5 Security</span></span>

### <a name="permissions"></a><span data-ttu-id="eebd5-115">權限</span><span class="sxs-lookup"><span data-stu-id="eebd5-115">Permissions</span></span>
<span data-ttu-id="eebd5-116">建立 DLP 原則的使用者應該是：</span><span class="sxs-lookup"><span data-stu-id="eebd5-116">The user who creates the DLP policy should be a:</span></span>
- <span data-ttu-id="eebd5-117">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="eebd5-117">Global administrator</span></span>
- <span data-ttu-id="eebd5-118">合規性管理員</span><span class="sxs-lookup"><span data-stu-id="eebd5-118">Compliance administrator</span></span>
- <span data-ttu-id="eebd5-119">合規性資料管理員</span><span class="sxs-lookup"><span data-stu-id="eebd5-119">Compliance data administrator</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="eebd5-120">準備您的雲端 App 安全性環境</span><span class="sxs-lookup"><span data-stu-id="eebd5-120">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="eebd5-121">dlp 原則至非 Microsoft cloud app 使用雲端 App 安全性 DLP 功能。</span><span class="sxs-lookup"><span data-stu-id="eebd5-121">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="eebd5-122">若要使用它，您應該準備雲端 App 安全性環境。</span><span class="sxs-lookup"><span data-stu-id="eebd5-122">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="eebd5-123">如需相關指示，請參閱為 [您的應用程式設定立即可視性、保護和](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)控管動作。</span><span class="sxs-lookup"><span data-stu-id="eebd5-123">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="eebd5-124">連線非 Microsoft cloud app</span><span class="sxs-lookup"><span data-stu-id="eebd5-124">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="eebd5-125">若要使用 DLP 原則至特定的非 Microsoft cloud app，應用程式必須連接至雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="eebd5-125">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="eebd5-126">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="eebd5-126">For information, see:</span></span>

- [<span data-ttu-id="eebd5-127">連線箱</span><span class="sxs-lookup"><span data-stu-id="eebd5-127">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="eebd5-128">連線 Dropbox</span><span class="sxs-lookup"><span data-stu-id="eebd5-128">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="eebd5-129">連線G-套件</span><span class="sxs-lookup"><span data-stu-id="eebd5-129">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="eebd5-130">連線Salesforce</span><span class="sxs-lookup"><span data-stu-id="eebd5-130">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="eebd5-131">連線Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="eebd5-131">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="eebd5-132">將雲端應用程式連線至雲端 App 安全性後，您可以為其建立 Microsoft 365 的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="eebd5-132">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

> [!NOTE]
> <span data-ttu-id="eebd5-133">您也可以使用 Microsoft Cloud App Security 來建立 DLP 原則至 Microsoft 雲端應用程式。</span><span class="sxs-lookup"><span data-stu-id="eebd5-133">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="eebd5-134">不過，建議使用 Microsoft 365 來建立及管理 DLP 原則至 Microsoft 雲端應用程式。</span><span class="sxs-lookup"><span data-stu-id="eebd5-134">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="eebd5-135">建立非 Microsoft cloud app 的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="eebd5-135">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="eebd5-136">當您選取 DLP 原則的位置時，請開啟 **Microsoft Cloud App Security** 位置。</span><span class="sxs-lookup"><span data-stu-id="eebd5-136">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="eebd5-137">若要選取特定的應用程式或實例，請選取 **[選擇實例**]。</span><span class="sxs-lookup"><span data-stu-id="eebd5-137">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="eebd5-138">如果您未選取實例，則原則會使用 Microsoft Cloud App Security 租使用者中所有連接的應用程式。</span><span class="sxs-lookup"><span data-stu-id="eebd5-138">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![套用原則的位置](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US 和 Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="eebd5-141">您可以針對每個支援的非 Microsoft cloud app 選擇各種動作。</span><span class="sxs-lookup"><span data-stu-id="eebd5-141">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="eebd5-142">每個應用程式都有不同的可能動作 (取決於雲端應用程式 API) 。</span><span class="sxs-lookup"><span data-stu-id="eebd5-142">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![建立規則](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="eebd5-144">當您在 DLP 原則中建立規則時，您可以選取非 Microsoft cloud app 的動作。</span><span class="sxs-lookup"><span data-stu-id="eebd5-144">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="eebd5-145">若要限制協力廠商應用程式，請選取 [ **限制協力廠商應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="eebd5-145">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![限制協力廠商應用程式](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> <span data-ttu-id="eebd5-147">套用至非 Microsoft 應用程式的 DLP 原則使用 Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="eebd5-147">DLP policies applied to non-Microsoft apps use Microsoft Cloud App Security.</span></span> <span data-ttu-id="eebd5-148">建立非 Microsoft 應用程式的 DLP 原則時，會自動在 Microsoft Cloud App Security 中建立相同的原則。</span><span class="sxs-lookup"><span data-stu-id="eebd5-148">When the DLP policy for a non-Microsoft app is created, the same policy will be automatically created in Microsoft Cloud App Security.</span></span>

<span data-ttu-id="eebd5-149">如需建立及設定 DLP 原則的詳細資訊，請參閱 [Create test and 微調 dlp policy](./create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="eebd5-149">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eebd5-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eebd5-150">See Also</span></span>

- [<span data-ttu-id="eebd5-151">建立測試並調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="eebd5-151">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md)
- [<span data-ttu-id="eebd5-152">預設的 DLP 原則快速入門</span><span class="sxs-lookup"><span data-stu-id="eebd5-152">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="eebd5-153">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="eebd5-153">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md)
