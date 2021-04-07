---
title: 與組織外部的人員共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: 瞭解如何設定 Microsoft 365 應用程式，如小組、OneDrive 和 SharePoint，以與組織外部的人員進行共同作業。
ms.openlocfilehash: 85aa77982fa15adb62bd587856546d2828edb942
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599816"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="81181-103">與組織外部的人員共同作業</span><span class="sxs-lookup"><span data-stu-id="81181-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="81181-104">Microsoft 365 中的外部共用功能可讓您組織中的人員與合作夥伴、廠商、客戶及其他使用者共同作業，而非您的目錄中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="81181-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="81181-105">您可以與組織外部的人員或只與個別的檔案共用整個小組或網站。</span><span class="sxs-lookup"><span data-stu-id="81181-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="81181-106">與組織外部的人員合作，包含兩個主要元件：</span><span class="sxs-lookup"><span data-stu-id="81181-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="81181-107">**啟用共用** -透過 Azure Active Directory、小組、Microsoft 365 群組和 SharePoint 設定共用控制，以允許您的組織所需的共用層級。</span><span class="sxs-lookup"><span data-stu-id="81181-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="81181-108">**啟用其他安全性** -雖然基本共用功能可設定為要求組織外部的人員進行驗證，但 Microsoft 365 提供許多額外的安全性和合規性功能，可協助您保護您的資料，並在外部共用時維護您的管理原則。</span><span class="sxs-lookup"><span data-stu-id="81181-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

<span data-ttu-id="81181-109">已閱讀 [ [設定與 microsoft 365 和 Microsoft 團隊的安全](/microsoft-365/solutions/setup-secure-collaboration-with-teams) 共同作業]，瞭解外部共用如何與整體 Microsoft 365 共同作業指導方針。</span><span class="sxs-lookup"><span data-stu-id="81181-109">Read [Set up secure collaboration with Microsoft 365 and Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams) to learn how external sharing ties in with the overall Microsoft 365 collaboration guidance.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="81181-110">啟用共用</span><span class="sxs-lookup"><span data-stu-id="81181-110">Enable sharing</span></span>

<span data-ttu-id="81181-111">根據預設，在 Microsoft 365 中，會啟用與組織外部人員共用。</span><span class="sxs-lookup"><span data-stu-id="81181-111">By default, in Microsoft 365, sharing with people outside your organization is enabled.</span></span> <span data-ttu-id="81181-112">許多外部共用案例的運作方式並無進一步設定。</span><span class="sxs-lookup"><span data-stu-id="81181-112">Many external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="81181-113">若要確認您所使用之案例的設定，或是啟用新案例，請從下列選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="81181-113">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="81181-114">檔[共同](collaborate-on-documents.md)作業-瞭解如何設定 Microsoft 365，以允許與組織外部的人員共用和共同作業 (在檔案和資料夾上) 來賓和未驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="81181-114">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="81181-115">[在網站中共同](collaborate-in-site.md) 作業-瞭解如何設定 Microsoft 365，以啟用與來賓共用 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="81181-115">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="81181-116">[以團隊形式共同](collaborate-as-team.md) 作業-瞭解如何設定 Microsoft 365，以在小組中啟用來賓共同作業。</span><span class="sxs-lookup"><span data-stu-id="81181-116">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="81181-117">如需跨 Microsoft 365 提供之來賓共用設定的完整資訊，請參閱 [microsoft 365 來賓共用設定參考](microsoft-365-guest-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="81181-117">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="81181-118">啟用其他安全性</span><span class="sxs-lookup"><span data-stu-id="81181-118">Enable additional security</span></span>

<span data-ttu-id="81181-119">一旦您已啟用要用來與組織外部人員共用的案例，請考慮其他保護措施，以避免意外或故意不當共用的內容。</span><span class="sxs-lookup"><span data-stu-id="81181-119">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="81181-120">以未[驗證的使用者共用檔案和資料夾的最佳作法](best-practices-anonymous-sharing.md)-瞭解與未驗證使用者共用的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="81181-120">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="81181-121">[限制意外曝光](share-limit-accidental-exposure.md) -瞭解如何減少與組織外部人員意外共用機密內容的機率。</span><span class="sxs-lookup"><span data-stu-id="81181-121">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="81181-122">[建立安全來賓共用環境](create-secure-guest-sharing-environment.md) -深入瞭解 Microsoft 365 中提供的工具，以協助確保與組織外部的人員共用，以安全且安全的方式執行，並符合您的管理需求。</span><span class="sxs-lookup"><span data-stu-id="81181-122">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="81181-123">與合作夥伴公司共同作業</span><span class="sxs-lookup"><span data-stu-id="81181-123">Collaborate with partner companies</span></span>

<span data-ttu-id="81181-124">當您在需要其他組織之許多來賓的大型專案中工作時，或是當來賓經常變更的情況下，您可以使用 Azure Active Directory 中的權利管理，以簡化來賓管理，並允許夥伴公司在該責任中共用。</span><span class="sxs-lookup"><span data-stu-id="81181-124">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="81181-125">如需詳細資訊，請參閱 [Create a B2B extranet with managed guests](b2b-extranet.md) 。</span><span class="sxs-lookup"><span data-stu-id="81181-125">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="81181-126">限制共用</span><span class="sxs-lookup"><span data-stu-id="81181-126">Limit sharing</span></span>

<span data-ttu-id="81181-127">如果 Microsoft 365 中的某些共用功能與您的控管原則衝突，請參閱 [限制共用在 microsoft 365 中](microsoft-365-limit-sharing.md) 以瞭解限制共用的選項。</span><span class="sxs-lookup"><span data-stu-id="81181-127">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="81181-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="81181-128">Related topics</span></span>

[<span data-ttu-id="81181-129">在 Microsoft 365 中簡介檔共同作業</span><span class="sxs-lookup"><span data-stu-id="81181-129">Intro to file collaboration in Microsoft 365</span></span>](/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="81181-130">使用 Microsoft 365 規劃 SharePoint 中的檔共同作業</span><span class="sxs-lookup"><span data-stu-id="81181-130">Plan file collaboration in SharePoint with Microsoft 365</span></span>](/sharepoint/deploy-file-collaboration)
