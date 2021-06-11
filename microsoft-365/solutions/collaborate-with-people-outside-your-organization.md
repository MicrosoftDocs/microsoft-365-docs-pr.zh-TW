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
recommendations: false
description: 瞭解如何設定 Microsoft 365 的應用程式，如 Teams、OneDrive 和 SharePoint 等共同作業與組織外部的人員進行共同作業。
ms.openlocfilehash: 291a5e6d75ac1b1a12a2403a9aeece9cb658afd0
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537820"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="9047c-103">與組織外部的人員共同作業</span><span class="sxs-lookup"><span data-stu-id="9047c-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="9047c-104">Microsoft 365 的外部共用功能可讓您組織中的人員與合作夥伴、廠商、客戶及其他使用者共同作業，而您的目錄中沒有帳戶。</span><span class="sxs-lookup"><span data-stu-id="9047c-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="9047c-105">您可以與組織外部的人員或只與個別的檔案共用整個小組或網站。</span><span class="sxs-lookup"><span data-stu-id="9047c-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="9047c-106">與組織外部的人員合作，包含兩個主要元件：</span><span class="sxs-lookup"><span data-stu-id="9047c-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="9047c-107">**啟用共用**-設定跨 Azure Active Directory、Teams、Microsoft 365 群組和 SharePoint 的共用控制，以允許組織所需的共用層級。</span><span class="sxs-lookup"><span data-stu-id="9047c-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="9047c-108">**啟用其他安全性**-雖然基本共用功能可設定為要求組織外部人員進行驗證，但 Microsoft 365 提供許多額外的安全性和符合性功能，以協助您在外部共用時保護您的資料，並維護您的管理原則。</span><span class="sxs-lookup"><span data-stu-id="9047c-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

<span data-ttu-id="9047c-109">已閱讀[設定安全共同作業與 Microsoft 365 和 Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams) ，以瞭解外部共用如何與整體 Microsoft 365 共同作業指導一起使用。</span><span class="sxs-lookup"><span data-stu-id="9047c-109">Read [Set up secure collaboration with Microsoft 365 and Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams) to learn how external sharing ties in with the overall Microsoft 365 collaboration guidance.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="9047c-110">啟用共用</span><span class="sxs-lookup"><span data-stu-id="9047c-110">Enable sharing</span></span>

<span data-ttu-id="9047c-111">根據預設，在 Microsoft 365 中，會啟用與組織外部人員共用。</span><span class="sxs-lookup"><span data-stu-id="9047c-111">By default, in Microsoft 365, sharing with people outside your organization is enabled.</span></span> <span data-ttu-id="9047c-112">許多外部共用案例的運作方式並無進一步設定。</span><span class="sxs-lookup"><span data-stu-id="9047c-112">Many external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="9047c-113">若要確認您所使用之案例的設定，或是啟用新案例，請從下列選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="9047c-113">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="9047c-114">檔[共同](collaborate-on-documents.md)作業-瞭解如何設定 Microsoft 365，以允許與組織外部的人員共用和共同作業 (的功能和資料夾) 的來賓和未驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="9047c-114">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="9047c-115">[在網站中共同](collaborate-in-site.md)作業-瞭解如何設定 Microsoft 365 以啟用與來賓共用 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="9047c-115">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="9047c-116">[以團隊形式共同](collaborate-as-team.md)作業-瞭解如何設定 Microsoft 365，以在 Teams 中啟用來賓協同作業。</span><span class="sxs-lookup"><span data-stu-id="9047c-116">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="9047c-117">如需可在 Microsoft 365 中使用之來賓共用設定的完整資訊，請參閱[Microsoft 365 來賓共用設定參考](microsoft-365-guest-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="9047c-117">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="9047c-118">啟用其他安全性</span><span class="sxs-lookup"><span data-stu-id="9047c-118">Enable additional security</span></span>

<span data-ttu-id="9047c-119">一旦您已啟用要用來與組織外部人員共用的案例，請考慮其他保護措施，以避免意外或故意不當共用的內容。</span><span class="sxs-lookup"><span data-stu-id="9047c-119">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="9047c-120">以未[驗證的使用者共用檔案和資料夾的最佳作法](best-practices-anonymous-sharing.md)-瞭解與未驗證使用者共用的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="9047c-120">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="9047c-121">[限制意外曝光](share-limit-accidental-exposure.md) -瞭解如何減少與組織外部人員意外共用機密內容的機率。</span><span class="sxs-lookup"><span data-stu-id="9047c-121">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="9047c-122">[建立安全的來賓共用環境](create-secure-guest-sharing-environment.md)-深入瞭解 Microsoft 365 中提供的工具，協助確保與組織外部的人員共用，以安全且安全的方式進行，並符合您的管理需求。</span><span class="sxs-lookup"><span data-stu-id="9047c-122">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="9047c-123">與合作夥伴公司共同作業</span><span class="sxs-lookup"><span data-stu-id="9047c-123">Collaborate with partner companies</span></span>

<span data-ttu-id="9047c-124">當您在需要其他組織之許多來賓的大型專案中工作時，或如果您有來賓經常變更的現行廠商關聯，您可以在 Azure Active Directory 中使用權利管理，以簡化來賓管理，並讓夥伴公司在該責任中共用。</span><span class="sxs-lookup"><span data-stu-id="9047c-124">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="9047c-125">如需詳細資訊，請參閱 [Create a B2B extranet with managed guests](b2b-extranet.md) 。</span><span class="sxs-lookup"><span data-stu-id="9047c-125">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="9047c-126">限制共用</span><span class="sxs-lookup"><span data-stu-id="9047c-126">Limit sharing</span></span>

<span data-ttu-id="9047c-127">如果 Microsoft 365 中的某些共用功能與您的管理原則發生衝突，請參閱[限制共用 Microsoft 365](microsoft-365-limit-sharing.md)以瞭解限制共用的選項。</span><span class="sxs-lookup"><span data-stu-id="9047c-127">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9047c-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="9047c-128">Related topics</span></span>

[<span data-ttu-id="9047c-129">簡介 Microsoft 365 中的檔共同作業</span><span class="sxs-lookup"><span data-stu-id="9047c-129">Intro to file collaboration in Microsoft 365</span></span>](/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="9047c-130">使用 Microsoft 365 規劃 SharePoint 中的檔案共同作業</span><span class="sxs-lookup"><span data-stu-id="9047c-130">Plan file collaboration in SharePoint with Microsoft 365</span></span>](/sharepoint/deploy-file-collaboration)
