---
title: 資訊管理原則簡介
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2014
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何使用資訊管理原則來控制及追蹤內容保留多久或使用者可對該內容採取的動作等事項。
ms.openlocfilehash: dfb1aeb3dbd3a2b17f18bbd03d5f4d3e198e4c47
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815510"
---
# <a name="introduction-to-information-management-policies"></a><span data-ttu-id="16319-103">資訊管理原則簡介</span><span class="sxs-lookup"><span data-stu-id="16319-103">Introduction to information management policies</span></span>

<span data-ttu-id="16319-104">資訊管理原則是一種內容的一組規則。</span><span class="sxs-lookup"><span data-stu-id="16319-104">An information management policy is a set of rules for a type of content.</span></span> <span data-ttu-id="16319-105">資訊管理原則可讓組織控制及追蹤內容保留多久或使用者可對該內容採取的動作等事項。</span><span class="sxs-lookup"><span data-stu-id="16319-105">Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content.</span></span> <span data-ttu-id="16319-106">資料管理原則可協助組織符合法律或政府規範，或是只強制執行一些內部業務流程。</span><span class="sxs-lookup"><span data-stu-id="16319-106">Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes.</span></span> 
  
<span data-ttu-id="16319-107">例如，組織必須遵循政府法規要求他們示範其財務報表的「適當的控制」，可能會建立一或多個資訊管理原則，以針對財務檔相關的所有檔，在撰寫和核准程式中審核特定動作。</span><span class="sxs-lookup"><span data-stu-id="16319-107">For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.</span></span>
  
<span data-ttu-id="16319-108">如需詳細資訊，請參閱[Create and apply 資訊管理原則](create-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="16319-108">For how-to information, see [Create and apply information management policies](create-info-mgmt-policies.md).</span></span>
  
## <a name="features-of-information-management-policies"></a><span data-ttu-id="16319-109">資訊管理原則的功能</span><span class="sxs-lookup"><span data-stu-id="16319-109">Features of information management policies</span></span>
<span data-ttu-id="16319-110"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="16319-110"><a name="__top"> </a></span></span>

<span data-ttu-id="16319-111">組織可以個別或結合使用的預先定義的原則功能有四種基本類別，以管理內容與程式。</span><span class="sxs-lookup"><span data-stu-id="16319-111">There are four basic categories of predefined policy features that organizations can use individually or in combination to manage content and processes.</span></span> 
  
![內容原則的類型](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
<span data-ttu-id="16319-113">「審核原則」功能可協助組織分析在檔和清單專案上執行的事件及作業，如何使用其內容管理系統。</span><span class="sxs-lookup"><span data-stu-id="16319-113">The Auditing policy feature helps organizations analyze how their content management systems are used by logging events and operations that are performed on documents and list items.</span></span> <span data-ttu-id="16319-114">您可以設定審核原則功能來記錄事件（例如，當檔或專案編輯、查看、存回、取出、刪除或變更其許可權）。</span><span class="sxs-lookup"><span data-stu-id="16319-114">You can configure the Auditing policy feature to log events such as when a document or item is edited, viewed, checked in, checked out, deleted, or has its permissions changed.</span></span> <span data-ttu-id="16319-115">所有的審計資訊會儲存在伺服器上的單一審核記錄中，網站管理員可以在該伺服器上執行報告。</span><span class="sxs-lookup"><span data-stu-id="16319-115">All of the audit information is stored in a single audit log on the server, and site administrators can run reports on it.</span></span> 
  
<span data-ttu-id="16319-116">到期原則功能可協助組織以一致且 trackable 的方式，從其網站刪除或移除過期的內容。</span><span class="sxs-lookup"><span data-stu-id="16319-116">The Expiration policy feature helps organizations delete or remove out-of-date content from their sites in a consistent, trackable way.</span></span> <span data-ttu-id="16319-117">這可協助您管理保留到期內容相關的成本和風險。</span><span class="sxs-lookup"><span data-stu-id="16319-117">This helps you manage both the cost and risk associated with retaining out-of-date content.</span></span> <span data-ttu-id="16319-118">您可以設定到期原則，以指定特定的內容類型會在特定日期或檔建立或上次修改後的一段時間內到期。</span><span class="sxs-lookup"><span data-stu-id="16319-118">You can configure an Expiration policy to specify that certain types of content expire on a particular date or within a period of time after the document was created or last modified.</span></span>
  
<span data-ttu-id="16319-119">組織也可以建立及部署自訂的原則功能，以滿足特定的需求。</span><span class="sxs-lookup"><span data-stu-id="16319-119">Organizations can also create and deploy custom policy features to meet specific needs.</span></span> <span data-ttu-id="16319-120">例如，製造組織可能會想要為所有草稿產品設計規格檔定義資訊管理原則，禁止使用者在不安全的印表機上列印這些檔的副本。</span><span class="sxs-lookup"><span data-stu-id="16319-120">For example, a manufacturing organization might want to define an information management policy for all draft product-design specification documents that prohibits users from printing copies of these documents on nonsecure printers.</span></span> <span data-ttu-id="16319-121">若要定義這種資訊管理原則，您可以建立及部署列印限制原則功能，以新增至 [產品設計規格] 內容類型的相關資訊管理原則。</span><span class="sxs-lookup"><span data-stu-id="16319-121">To define this kind of information management policy, you can create and deploy a Printing Restriction policy feature that can be added to the relevant information management policy for the product design specification content type.</span></span>
  
## <a name="locations-to-use-an-information-management-policy"></a><span data-ttu-id="16319-122">使用資訊管理原則的位置</span><span class="sxs-lookup"><span data-stu-id="16319-122">Locations to use an information management policy</span></span>
<span data-ttu-id="16319-123"><a name="__toc340213528"> </a></span><span class="sxs-lookup"><span data-stu-id="16319-123"><a name="__toc340213528"> </a></span></span>

<span data-ttu-id="16319-124">若要執行資訊管理原則，您必須將其新增至網站中的清單、文件庫或內容類型。</span><span class="sxs-lookup"><span data-stu-id="16319-124">To implement an information management policy, you must add it to a list, library, or content type in a site.</span></span> <span data-ttu-id="16319-125">您建立或新增資訊管理原則的位置會影響原則的套用範圍或可使用的程度。</span><span class="sxs-lookup"><span data-stu-id="16319-125">The location where you create or add an information management policy affects how broadly the policy applies or how broadly it can be used.</span></span> <span data-ttu-id="16319-126">您可以：</span><span class="sxs-lookup"><span data-stu-id="16319-126">You can:</span></span>
  
 <span data-ttu-id="16319-127">**建立網站集合原則，然後將此原則新增至內容類型、清單或文件庫**您可以在網站集合的最上層網站的 [原則] 清單中建立網站集合原則。</span><span class="sxs-lookup"><span data-stu-id="16319-127">**Create a site collection policy and then add this policy to a content type, list, or library** You can create a site collection policy in the Policies list in the top-level site of a site collection.</span></span> <span data-ttu-id="16319-128">在您建立網站集合原則之後，您可以將其匯出，讓其他網站集合的管理員可以將其匯入其原則清單。</span><span class="sxs-lookup"><span data-stu-id="16319-128">After you create a site collection policy, you can export it so that administrators of other site collections can import it into their Policies list.</span></span> <span data-ttu-id="16319-129">建立可匯出的網站集合原則，可讓您在組織中的各個網站上，將資訊管理原則標準化。</span><span class="sxs-lookup"><span data-stu-id="16319-129">Creating an exportable site collection policy enables you to standardize the information management policies across the sites in your organization.</span></span> 
  
<span data-ttu-id="16319-130">當您將網站集合原則新增至網站內容類型，並將該網站內容類型的實例新增至清單或文件庫中，該清單或文件庫的擁有者便無法修改清單或文件庫的網站集合原則。</span><span class="sxs-lookup"><span data-stu-id="16319-130">When you add a site collection policy to a site content type, and an instance of that site content type is added to a list or library, the owner of that list or library cannot modify the site collection policy for the list or library.</span></span> <span data-ttu-id="16319-131">將網站集合原則新增至網站內容類型是一種很好的方法，可確保網站集合原則在網站階層的每個層級強制執行。</span><span class="sxs-lookup"><span data-stu-id="16319-131">Adding a site collection policy to a site content type is a good way to ensure that site collection policies are enforced at each level of your site hierarchy.</span></span>
  
![網站設定頁面上的內容類型原則範本連結](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 <span data-ttu-id="16319-133">**在最上層網站的網站內容類型庫中為網站內容類型建立資訊管理原則，然後將該內容類型新增至一或多個清單或文件庫**您也可以直接為網站內容類型建立資訊管理原則，然後將該網站內容類型的實例與多個清單或文件庫建立關聯。</span><span class="sxs-lookup"><span data-stu-id="16319-133">**Create an information management policy for a site content type in the top-level site's Site Content Type Gallery, and then add that content type to one or more lists or libraries** You can also create an information management policy directly for a site content type and then associate an instance of that site content type with multiple lists or libraries.</span></span> <span data-ttu-id="16319-134">如果您以這種方式建立資訊管理原則，則該內容類型的網站集合中的每個專案或是繼承自該內容類型的內容類型都具有原則。</span><span class="sxs-lookup"><span data-stu-id="16319-134">If you create an information management policy this way, every item in the site collection of that content type or a content type that inherits from that content type has the policy.</span></span> <span data-ttu-id="16319-135">不過，如果您直接為網站內容類型建立資訊管理原則，則在其他網站集合中重複使用此資訊管理原則會比較困難，因為無法匯出以這種方式建立的原則。</span><span class="sxs-lookup"><span data-stu-id="16319-135">However, if you create an information management policy directly for a site content type, it is more difficult to reuse this information management policy in other site collections, because policies that are created this way cannot be exported.</span></span> 
  
![網站設定頁面上的網站內容類型連結](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![網站內容類型 [設定] 頁面上的資訊管理原則連結](../media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
<span data-ttu-id="16319-138">附注若要控制在網站集合中使用的原則，網站集合管理員可以停用在內容類型上直接設定原則功能的能力。</span><span class="sxs-lookup"><span data-stu-id="16319-138">Note To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a content type.</span></span> <span data-ttu-id="16319-139">當此限制生效時，建立內容類型的使用者限制于從 [網站集合原則] 清單中選取原則。</span><span class="sxs-lookup"><span data-stu-id="16319-139">When this restriction is in effect, users who create content types are limited to selecting policies from the site collection Policies list.</span></span>
  
 <span data-ttu-id="16319-140">**建立清單或文件庫的資訊管理原則**如果您的組織需要將特定的資訊管理原則套用至一組非常有限的內容，您可以建立僅套用至個別清單或文件庫的資訊管理原則。</span><span class="sxs-lookup"><span data-stu-id="16319-140">**Create an information management policy for a list or library** If your organization needs to apply a specific information management policy to a very limited set of content, you can create an information management policy that applies only to an individual list or library.</span></span> <span data-ttu-id="16319-141">這種建立資訊管理原則的方法是最小彈性，因為原則只適用于一個位置，而且無法在其他位置匯出或重複使用。</span><span class="sxs-lookup"><span data-stu-id="16319-141">This method of creating an information management policy is the least flexible, because the policy applies only to one location, and it cannot be exported or reused for other locations.</span></span> <span data-ttu-id="16319-142">不過，在某些情況下，您可能需要使用有限適用性建立唯一的資訊管理原則，以解決特定的情況。</span><span class="sxs-lookup"><span data-stu-id="16319-142">However, sometimes you may need to create unique information management policies with limited applicability to address specific situations.</span></span> 
  
![文件庫設定頁面上的資訊管理原則連結](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
<span data-ttu-id="16319-144">附註</span><span class="sxs-lookup"><span data-stu-id="16319-144">Notes</span></span> 
  
<span data-ttu-id="16319-145">只有當清單或文件庫不支援多個內容類型時，您才可以為清單或文件庫建立資訊管理原則。</span><span class="sxs-lookup"><span data-stu-id="16319-145">You can create an information management policy for a list or library only if that list or library does not support multiple content types.</span></span> <span data-ttu-id="16319-146">如果清單或文件庫支援多個內容類型，您必須為與該清單或文件庫相關聯的每個個別清單內容類型定義資訊管理原則。</span><span class="sxs-lookup"><span data-stu-id="16319-146">If a list or library supports multiple content types, you need to define an information management policy for each individual list content type that is associated with that list or library.</span></span> <span data-ttu-id="16319-147">（與特定清單或文件庫相關聯的網站內容類型實例，稱為清單內容類型。）</span><span class="sxs-lookup"><span data-stu-id="16319-147">(Instances of a site content type that are associated with a specific list or library are known as list content types.)</span></span>
  
<span data-ttu-id="16319-148">若要控制在網站集合中使用的原則，網站集合管理員可以停用在清單或文件庫上直接設定原則功能的功能。</span><span class="sxs-lookup"><span data-stu-id="16319-148">To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a list or library.</span></span> <span data-ttu-id="16319-149">當此限制生效時，管理清單或文件庫的使用者，只限于從 [網站集合原則] 清單中選取原則。</span><span class="sxs-lookup"><span data-stu-id="16319-149">When this restriction is in effect, users who manage lists or libraries are limited to selecting policies from the site collection Policies list.</span></span>
  
[<span data-ttu-id="16319-150">資訊管理原則是一套內容類型的規則。資訊管理原則可讓組織控制及追蹤內容保留多久或使用者可對該內容採取的動作等事項。資訊管理原則可以協助組織遵循法律或政府法規，也可以只強制執行內部商務程式。例如，組織必須遵循政府法規要求他們示範其財務報表的「適當的控制」，可能會建立一或多個資訊管理原則，以針對財務檔相關的所有檔，在撰寫和核准程式中審核特定動作。如需詳細資訊，請參閱 Create and apply 資訊管理原則。</span><span class="sxs-lookup"><span data-stu-id="16319-150">An information management policy is a set of rules for a type of content. Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content. Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes. For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.For how-to information, see Create and apply information management policies.</span></span>](intro-to-info-mgmt-policies.md#__top)
  

