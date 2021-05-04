---
title: '使用非 Microsoft cloud app 的資料遺失防護原則 (預覽) '
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
ms.openlocfilehash: d4c5170cab01b1ca22701b13c7afbf4f2e0ba7da
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114131"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="361df-103">使用非 Microsoft cloud app 的資料遺失防護原則 (預覽) </span><span class="sxs-lookup"><span data-stu-id="361df-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="361df-104">資料遺失防護 (dlp) 原則的非 Microsoft cloud app 屬於 Microsoft 365 DLP 套件的一部分;您可以使用這些功能，在 Microsoft 365 服務中探索和保護機密專案。</span><span class="sxs-lookup"><span data-stu-id="361df-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="361df-105">如需所有 Microsoft DLP 產品的詳細資訊，請參閱 [瞭解資料遺失防護](dlp-learn-about-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="361df-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="361df-106">您可以使用 DLP 原則來監視和偵測敏感專案何時使用，並透過非 Microsoft cloud app 加以共用。</span><span class="sxs-lookup"><span data-stu-id="361df-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="361df-107">使用這些原則可提供您所需的可見度和控制，以確保它們已正確使用和受到保護，並可協助防範可能會損損的危險行為。</span><span class="sxs-lookup"><span data-stu-id="361df-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="361df-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="361df-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="361df-109">SKU/訂閱授權</span><span class="sxs-lookup"><span data-stu-id="361df-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="361df-110">開始使用 DLP 原則至非 Microsoft cloud app 之前，請先確認您的[Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)和任何附加元件。</span><span class="sxs-lookup"><span data-stu-id="361df-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="361df-111">若要存取及使用此功能，您必須具有下列其中一項訂閱或附加元件：</span><span class="sxs-lookup"><span data-stu-id="361df-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="361df-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="361df-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="361df-113">Microsoft 365 E5 合規性</span><span class="sxs-lookup"><span data-stu-id="361df-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="361df-114">Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="361df-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="361df-115">準備您的雲端 App 安全性環境</span><span class="sxs-lookup"><span data-stu-id="361df-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="361df-116">dlp 原則至非 Microsoft cloud app 使用雲端 App 安全性 DLP 功能。</span><span class="sxs-lookup"><span data-stu-id="361df-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="361df-117">若要使用它，您應該準備雲端 App 安全性環境。</span><span class="sxs-lookup"><span data-stu-id="361df-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="361df-118">如需相關指示，請參閱為 [您的應用程式設定立即可視性、保護和](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)控管動作。</span><span class="sxs-lookup"><span data-stu-id="361df-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="361df-119">連線非 Microsoft cloud app</span><span class="sxs-lookup"><span data-stu-id="361df-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="361df-120">若要使用 DLP 原則至特定的非 Microsoft cloud app，應用程式必須連接至雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="361df-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="361df-121">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="361df-121">For information, see:</span></span>

- [<span data-ttu-id="361df-122">連線箱</span><span class="sxs-lookup"><span data-stu-id="361df-122">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="361df-123">連線 Dropbox</span><span class="sxs-lookup"><span data-stu-id="361df-123">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="361df-124">連線G-套件</span><span class="sxs-lookup"><span data-stu-id="361df-124">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="361df-125">連線Salesforce</span><span class="sxs-lookup"><span data-stu-id="361df-125">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="361df-126">連線Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="361df-126">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="361df-127">將雲端應用程式連線至雲端 App 安全性後，您可以為其建立 Microsoft 365 的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="361df-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="361df-128">您也可以使用 Microsoft Cloud App Security 來建立 DLP 原則至 Microsoft 雲端應用程式。</span><span class="sxs-lookup"><span data-stu-id="361df-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="361df-129">不過，建議使用 Microsoft 365 來建立及管理 DLP 原則至 Microsoft 雲端應用程式。</span><span class="sxs-lookup"><span data-stu-id="361df-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="361df-130">建立非 Microsoft cloud app 的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="361df-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="361df-131">當您選取 DLP 原則的位置時，請開啟 **Microsoft Cloud App Security** 位置。</span><span class="sxs-lookup"><span data-stu-id="361df-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="361df-132">若要選取特定的應用程式或實例，請選取 **[選擇實例**]。</span><span class="sxs-lookup"><span data-stu-id="361df-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="361df-133">如果您未選取實例，則原則會使用 Microsoft Cloud App Security 租使用者中所有連接的應用程式。</span><span class="sxs-lookup"><span data-stu-id="361df-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![套用原則的位置](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US 和 Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="361df-136">您可以針對每個支援的非 Microsoft cloud app 選擇各種動作。</span><span class="sxs-lookup"><span data-stu-id="361df-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="361df-137">每個應用程式都有不同的可能動作 (取決於雲端應用程式 API) 。</span><span class="sxs-lookup"><span data-stu-id="361df-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![建立規則](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="361df-139">當您在 DLP 原則中建立規則時，您可以選取非 Microsoft cloud app 的動作。</span><span class="sxs-lookup"><span data-stu-id="361df-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="361df-140">若要限制協力廠商應用程式，請選取 [ **限制協力廠商應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="361df-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![限制協力廠商應用程式](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="361df-142">如需建立及設定 DLP 原則的詳細資訊，請參閱 [Create test and 微調 dlp policy](./create-test-tune-dlp-policy.md?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="361df-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="361df-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="361df-143">See Also</span></span>

- [<span data-ttu-id="361df-144">建立測試並調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="361df-144">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="361df-145">預設的 DLP 原則快速入門</span><span class="sxs-lookup"><span data-stu-id="361df-145">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="361df-146">從範本建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="361df-146">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)