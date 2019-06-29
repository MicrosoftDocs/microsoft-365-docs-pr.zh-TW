---
title: Microsoft 受管理的桌面產品生命週期
description: 本主題列出 Microsoft 受管理的電腦中所使用的裝置規格。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 88abd7bd8b2b4a9af37a1daf5579ac6268a9f927
ms.sourcegitcommit: e5aa684dab9b4dbe92002d31e69e7225bd8f95a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2019
ms.locfileid: "35348867"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a><span data-ttu-id="d081f-104">Microsoft 受管理的桌面產品生命週期</span><span class="sxs-lookup"><span data-stu-id="d081f-104">Microsoft Managed Desktop product lifecycle</span></span>

<span data-ttu-id="d081f-105">Microsoft 受管理的桌面權益使用者可確保他們始終使用提供最佳效能、可靠性、設計及安全性功能的裝置 (例如, 支援 Windows Hello 等功能)。</span><span class="sxs-lookup"><span data-stu-id="d081f-105">Microsoft Managed Desktop benefits end-users assuring that they always use devices that offer the best performance, reliability, design, and security capabilities (such as support for features like Windows Hello).</span></span> <span data-ttu-id="d081f-106">為了達到此目的, Microsoft 受管理的桌面會維護持續更新的[已核准裝置](device-list.md)的簡短目錄。</span><span class="sxs-lookup"><span data-stu-id="d081f-106">To accomplish this, Microsoft Managed Desktop maintains a short catalog of continuously updated [approved devices](device-list.md).</span></span> 
 
<span data-ttu-id="d081f-107">本主題會詳細說明從已核准的目錄中新增及移除裝置時的裝置生命週期。</span><span class="sxs-lookup"><span data-stu-id="d081f-107">This topic details the lifecycle of devices as they are added and removed from the approved catalog.</span></span> 

> [!NOTE]
> <span data-ttu-id="d081f-108">在本主題中, 我們將在「裝置」和「產品」之間進行區分。</span><span class="sxs-lookup"><span data-stu-id="d081f-108">In this topic, we'll make a distinction between a "device" and a "product."</span></span> <span data-ttu-id="d081f-109">根據「裝置」, 我們指的是一個個別的特定電腦。</span><span class="sxs-lookup"><span data-stu-id="d081f-109">By “device,” we mean one individual, specific computer.</span></span> <span data-ttu-id="d081f-110">例如, 「序號碼1234」、「帳單的膝上型電腦」、「共用 VM XYZ」參照特定的裝置。</span><span class="sxs-lookup"><span data-stu-id="d081f-110">For example, “Serial number 1234”, “Bill’s laptop”, “Shared VM XYZ” refer to specific devices.</span></span> <span data-ttu-id="d081f-111">不過, 「產品」指的是裝置的集合或系列。</span><span class="sxs-lookup"><span data-stu-id="d081f-111">A “product”, however, refers to a collection or family of devices.</span></span> <span data-ttu-id="d081f-112">例如, 「Fabrikam 膝上型電腦」、「Adatum ZX450 膝上型電腦」等等。這一點很重要, 因為產品會新增至[核准的清單](device-list.md)或目錄, 而裝置則會註冊至 Microsoft 受管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="d081f-112">For example, “Fabrikam Laptop”, “Adatum ZX450 Laptop”, etc. This is important because products are added to our [approved list](device-list.md), or catalog, and devices are what get enrolled into Microsoft Managed Desktop.</span></span>

## <a name="product-lifecycle"></a><span data-ttu-id="d081f-113">產品生命週期</span><span class="sxs-lookup"><span data-stu-id="d081f-113">Product lifecycle</span></span>

 <span data-ttu-id="d081f-114">一般來說, 產品會在下列生命週期階段中移動:</span><span class="sxs-lookup"><span data-stu-id="d081f-114">Generally, products move through these lifecycle phases:</span></span>

- [<span data-ttu-id="d081f-115">產品版本與評估</span><span class="sxs-lookup"><span data-stu-id="d081f-115">Product release and evaluation</span></span>](#product-release-and-evaluation)
- [<span data-ttu-id="d081f-116">產品主要可用性期間</span><span class="sxs-lookup"><span data-stu-id="d081f-116">Product primary availability period</span></span>](#product-primary-availability-period)
- [<span data-ttu-id="d081f-117">產品寬限期</span><span class="sxs-lookup"><span data-stu-id="d081f-117">Product grace period</span></span>](#product-grace-period)
- [<span data-ttu-id="d081f-118">產品退休</span><span class="sxs-lookup"><span data-stu-id="d081f-118">Product retirement</span></span>](#product-retirement)


<span data-ttu-id="d081f-119">整個順序如下圖所示:</span><span class="sxs-lookup"><span data-stu-id="d081f-119">The entire sequence is depicted in this illustration:</span></span>

![生命週期時程表](images/non-dark1-edits.PNG)

<span data-ttu-id="d081f-121">產品保留在目錄中最多24個月, 但是*裝置*會維持在管理下的個別註冊日期為3年。</span><span class="sxs-lookup"><span data-stu-id="d081f-121">Products remain on the catalog for up to 24 months, but *devices* remain under management for 3 years based on their individual enrollment dates.</span></span> <span data-ttu-id="d081f-122">實際上, 每個產品都有三個重要的日期, 但是每個裝置只有一個。</span><span class="sxs-lookup"><span data-stu-id="d081f-122">Effectively, each product has three important dates, but each device has only one.</span></span> <span data-ttu-id="d081f-123">對於產品, 這三個日期都是根據*核准日期*來計算, 因此我們會在核准時發佈這些日期, 因此您可以隨時對產品的整個生命週期進行適當的查看和規劃。</span><span class="sxs-lookup"><span data-stu-id="d081f-123">For products, all three of these dates are calculated based on the *approval date*, and therefore we publish these dates upon approval so that you can always look ahead and plan appropriately for the product's entire lifecycle.</span></span>

<span data-ttu-id="d081f-124">下表顯示理論產品的範例日期:</span><span class="sxs-lookup"><span data-stu-id="d081f-124">This table shows example dates for a theoretical product:</span></span>


|<span data-ttu-id="d081f-125">Product</span><span class="sxs-lookup"><span data-stu-id="d081f-125">Product</span></span>  |<span data-ttu-id="d081f-126">核准日期</span><span class="sxs-lookup"><span data-stu-id="d081f-126">Approved date</span></span>  |<span data-ttu-id="d081f-127">主要可用性結束</span><span class="sxs-lookup"><span data-stu-id="d081f-127">End of primary availability</span></span>  |<span data-ttu-id="d081f-128">Eligiblity 的結尾</span><span class="sxs-lookup"><span data-stu-id="d081f-128">End of eligiblity</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="d081f-129">Fabrikam 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="d081f-129">Fabrikam Laptop</span></span>    | <span data-ttu-id="d081f-130">1/1/2017</span><span class="sxs-lookup"><span data-stu-id="d081f-130">1/1/2017</span></span> | <span data-ttu-id="d081f-131">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="d081f-131">6/1/2019</span></span> | <span data-ttu-id="d081f-132">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="d081f-132">6/1/2022</span></span> |
|<span data-ttu-id="d081f-133">Adatum 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="d081f-133">Adatum Laptop</span></span>   | <span data-ttu-id="d081f-134">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="d081f-134">1/1/2018</span></span> | <span data-ttu-id="d081f-135">6/1/2020</span><span class="sxs-lookup"><span data-stu-id="d081f-135">6/1/2020</span></span> | <span data-ttu-id="d081f-136">6/1/2023</span><span class="sxs-lookup"><span data-stu-id="d081f-136">6/1/2023</span></span>  |

<span data-ttu-id="d081f-137">下表顯示理論*裝置*的範例日期:</span><span class="sxs-lookup"><span data-stu-id="d081f-137">This table shows example dates for theoretical *devices*:</span></span>


|<span data-ttu-id="d081f-138">裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="d081f-138">Device ID</span></span>  |<span data-ttu-id="d081f-139">註冊日期</span><span class="sxs-lookup"><span data-stu-id="d081f-139">Enrollment date</span></span>  |<span data-ttu-id="d081f-140">退休日期</span><span class="sxs-lookup"><span data-stu-id="d081f-140">Retirement date</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d081f-141">膝上型電腦 #123412</span><span class="sxs-lookup"><span data-stu-id="d081f-141">Laptop #123412</span></span>     |  <span data-ttu-id="d081f-142">2/3/2018</span><span class="sxs-lookup"><span data-stu-id="d081f-142">2/3/2018</span></span>       |  <span data-ttu-id="d081f-143">2/3/2021</span><span class="sxs-lookup"><span data-stu-id="d081f-143">2/3/2021</span></span>       |
|<span data-ttu-id="d081f-144">桌面 #321513</span><span class="sxs-lookup"><span data-stu-id="d081f-144">Desktop #321513</span></span>     | <span data-ttu-id="d081f-145">6/2/2018</span><span class="sxs-lookup"><span data-stu-id="d081f-145">6/2/2018</span></span>        |  <span data-ttu-id="d081f-146">6/2/2021</span><span class="sxs-lookup"><span data-stu-id="d081f-146">6/2/2021</span></span>       |


## <a name="product-release-and-evaluation"></a><span data-ttu-id="d081f-147">產品版本與評估</span><span class="sxs-lookup"><span data-stu-id="d081f-147">Product release and evaluation</span></span>

<span data-ttu-id="d081f-148">當製造商公開發行產品時, 產品生命週期便會開始:</span><span class="sxs-lookup"><span data-stu-id="d081f-148">The product lifecycle starts when a manufacturer publicly releases the product:</span></span>

![顯示發行和評估期間的生命週期時程表](images/non-dark3-edits.PNG)

<span data-ttu-id="d081f-150">在此階段中, Microsoft 受管理的桌面工程小組會做為產品的評估和認證。</span><span class="sxs-lookup"><span data-stu-id="d081f-150">During this stage, the Microsoft Managed Desktop engineering team does their evaluation and certification of a product.</span></span> <span data-ttu-id="d081f-151">此小組會評估與 Windows 的可靠性和效能等事項, 以及與硬體基準、市場 sentiment 以及清查和管道準備的相容性等專案。</span><span class="sxs-lookup"><span data-stu-id="d081f-151">The team evaluates things like reliability and performance with Windows, compliance with a hardware baseline, market sentiment, and inventory and channel readiness, among other things.</span></span> <span data-ttu-id="d081f-152">此程式通常需要大約6周的時間。</span><span class="sxs-lookup"><span data-stu-id="d081f-152">This process typically takes approximately 6 weeks.</span></span>
  
<span data-ttu-id="d081f-153">Microsoft 受管理的桌面只會評估其前6個月內的認證的裝置。</span><span class="sxs-lookup"><span data-stu-id="d081f-153">Microsoft Managed Desktop will only evaluate devices for certification within their first 6 months of availability.</span></span> <span data-ttu-id="d081f-154">這可確保我們永遠致力於最新的硬體產生。</span><span class="sxs-lookup"><span data-stu-id="d081f-154">This ensures that we’re always focusing our efforts on the latest generation of hardware.</span></span>
 
<span data-ttu-id="d081f-155">在這個階段結束時, Microsoft 受管理的桌面會將產品新增至[核准清單](device-list.md), 有效地釋放產品以供客戶註冊。</span><span class="sxs-lookup"><span data-stu-id="d081f-155">At the end of this phase, Microsoft Managed Desktop adds the product to the [approved list](device-list.md), effectively releasing the product for customer enrollments.</span></span> <span data-ttu-id="d081f-156">不論裝置認證的日期為何, 其**核准的日期**都將追溯至產品擁有的正式供貨日期。</span><span class="sxs-lookup"><span data-stu-id="d081f-156">Regardless of the date when a device is certified, its **approved date** is be back-dated to the products own general availability date.</span></span> 


## <a name="product-primary-availability-period"></a><span data-ttu-id="d081f-157">產品主要可用性期間</span><span class="sxs-lookup"><span data-stu-id="d081f-157">Product primary availability period</span></span>

<span data-ttu-id="d081f-158">此期間是產品可用性的核心:</span><span class="sxs-lookup"><span data-stu-id="d081f-158">This period is the core of product availability:</span></span>

![顯示主要 availibility 的生命週期時程表](images/non-dark4-edits.PNG)

<span data-ttu-id="d081f-160">在此期間內註冊的任何裝置都會從 Microsoft 受管理的桌面取得完整的三年支援 (如藍色時程表所示)。</span><span class="sxs-lookup"><span data-stu-id="d081f-160">Any device enrolled during this period receives the full three years of support from Microsoft Managed Desktop (as shown by the blue timeline).</span></span> <span data-ttu-id="d081f-161">此期間會持續到結束日期設為從一般可用日期起的24個月。</span><span class="sxs-lookup"><span data-stu-id="d081f-161">This period lasts until an end date set to 24 months from the general availability date.</span></span>

<span data-ttu-id="d081f-162">您可以將此期間視為有效的「開啟註冊」, 因此若要最大化 Microsoft 受管理電腦的值, 您應該針對您的採購模型及所選產品在此期間內。</span><span class="sxs-lookup"><span data-stu-id="d081f-162">You can think of this period as effectively “open enrollment”, so to maximize the value of Microsoft Managed Desktop, you should target your procurement models and selected products to fall within this period.</span></span> <span data-ttu-id="d081f-163">一小的範例是, 客戶應該避免使用主要可用性的最後一個月份的產品來結算2年的外滾期間, 大多數的裝置將不會收到完整的三年 Microsoft 受管理的桌面管理 (請參閱[寬限period](#product-grace-period)以取得詳細資訊)。</span><span class="sxs-lookup"><span data-stu-id="d081f-163">As a small example, a customer should avoid settling on a two-year roll-out period using a product that is in its final month of primary availability – most of those devices will not receive the full three years of Microsoft Managed Desktop management (see [grace period](#product-grace-period) for more information).</span></span>  

## <a name="product-grace-period"></a><span data-ttu-id="d081f-164">產品寬限期</span><span class="sxs-lookup"><span data-stu-id="d081f-164">Product grace period</span></span>

<span data-ttu-id="d081f-165">產品寬限期是一年三年後的主要可用性。</span><span class="sxs-lookup"><span data-stu-id="d081f-165">The product grace period is a three-year period following primary availability.</span></span> <span data-ttu-id="d081f-166">此階段可讓您註冊來自支援的產品系列的裝置, 但仍保留公司, 以確保 Microsoft 受管理的桌面對現代硬體和裝置效能的承諾。</span><span class="sxs-lookup"><span data-stu-id="d081f-166">This phase allows you to enroll devices that are from a supported product family, but still hold firm to the promises of Microsoft Managed Desktop regarding modern hardware and device performance.</span></span> <span data-ttu-id="d081f-167">此階段適用于在瞭解 Microsoft 受管理的電腦之前進行採購決策的客戶。</span><span class="sxs-lookup"><span data-stu-id="d081f-167">This phase is ideal for customers who have made procurement decisions before knowing about Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="d081f-168">如果您在註冊 Microsoft 受管理的電腦之前, 最近購買過大量的已核准裝置, 您仍然可以註冊它們, 但是您將不會收到完整的三年管理。</span><span class="sxs-lookup"><span data-stu-id="d081f-168">If you've recently bought a number of approved devices prior to enrolling with Microsoft Managed Desktop, you can still enroll them, but you won’t receive a full three years of management.</span></span> <span data-ttu-id="d081f-169">相反地, 它們會因退休日期而不相符, 不管他們何時註冊。</span><span class="sxs-lookup"><span data-stu-id="d081f-169">Instead, they’ll fall out of compliance on the retirement date, regardless of when they were enrolled.</span></span> <span data-ttu-id="d081f-170">在幕後, Microsoft 受管理的桌面會將這些裝置視為在主要可用性的最後一天註冊。</span><span class="sxs-lookup"><span data-stu-id="d081f-170">Behind the scenes, Microsoft Managed Desktop will treat these devices as if they were enrolled on the last day of primary availability.</span></span> <span data-ttu-id="d081f-171">在此圖中, 您可以在下列情況中看到藍屏和綠色裝置都結束于同一天, 但在註冊時有一年的差異:</span><span class="sxs-lookup"><span data-stu-id="d081f-171">In this illustration, you can see this scenario by noting that both the blue and green device end on the same day, despite their one-year difference in enrollment:</span></span>


![顯示寬限期的生命週期時程表](images/non-dark2-edits.PNG)

<span data-ttu-id="d081f-173">上表中的 Fabrikam 膝上型電腦範例說明這種情況:</span><span class="sxs-lookup"><span data-stu-id="d081f-173">The Fabrikam Laptop example from the previous table illustrates this situation:</span></span> 

|<span data-ttu-id="d081f-174">Product</span><span class="sxs-lookup"><span data-stu-id="d081f-174">Product</span></span>  |<span data-ttu-id="d081f-175">核准日期</span><span class="sxs-lookup"><span data-stu-id="d081f-175">Approved date</span></span>  |<span data-ttu-id="d081f-176">主要可用性結束</span><span class="sxs-lookup"><span data-stu-id="d081f-176">End of primary availability</span></span>  |<span data-ttu-id="d081f-177">Eligiblity 的結尾</span><span class="sxs-lookup"><span data-stu-id="d081f-177">End of eligiblity</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="d081f-178">Fabrikam 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="d081f-178">Fabrikam Laptop</span></span>    | <span data-ttu-id="d081f-179">6/1/2017</span><span class="sxs-lookup"><span data-stu-id="d081f-179">6/1/2017</span></span> | <span data-ttu-id="d081f-180">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="d081f-180">6/1/2019</span></span> | <span data-ttu-id="d081f-181">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="d081f-181">6/1/2022</span></span> |

<span data-ttu-id="d081f-182">就像客戶一樣, 您可以在6/1/2022 之前註冊 Fabrikam 膝上型電腦, 直到您在6/1/2019 上註冊它們時, 才會被視為。</span><span class="sxs-lookup"><span data-stu-id="d081f-182">As a customer, you can enroll Fabrikam Laptops all the way until 6/1/2022 – however they will all be treated as though you enrolled them on 6/1/2019.</span></span> <span data-ttu-id="d081f-183">如果您在6/1/2021 上註冊 Fabrikam 膝上型電腦, 您只需要一年的管理。</span><span class="sxs-lookup"><span data-stu-id="d081f-183">If you enroll a Fabrikam Laptop on 6/1/2021 you'll only get one year of management.</span></span> <span data-ttu-id="d081f-184">此原則可讓您從先前支援的產品提取部分生命週期, 而不是提前購買新的裝置。</span><span class="sxs-lookup"><span data-stu-id="d081f-184">This policy allows you to extract partial lifecycles from products that were previously supported, rather than having to procure new devices prematurely.</span></span> 

<span data-ttu-id="d081f-185">最後, 在此階段中, 裝置會從[裝置清單](device-list.md)中移除並移至封存的[裝置清單](archived-device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="d081f-185">Finally, during this phase the device is removed from the [device list](device-list.md) and moved to the [archived device list](archived-device-list.md).</span></span>


## <a name="product-retirement"></a><span data-ttu-id="d081f-186">產品退休</span><span class="sxs-lookup"><span data-stu-id="d081f-186">Product retirement</span></span>

<span data-ttu-id="d081f-187">產品退休是生命週期的最後階段。</span><span class="sxs-lookup"><span data-stu-id="d081f-187">Product retirement is the final phase of the lifecycle.</span></span> <span data-ttu-id="d081f-188">在這個階段中, 無法在 Microsoft 受管理的電腦上註冊該產品類型的新裝置, 而且根據定義, 所有現有的裝置現在都超出允許的三年期限。</span><span class="sxs-lookup"><span data-stu-id="d081f-188">In this phase, no new devices of that product type can be enrolled in Microsoft Managed Desktop and, by definition, all existing devices are now outside their allowed three-year term.</span></span> <span data-ttu-id="d081f-189">在這段時間內, Microsoft 受管理的桌面會將裝置從公用清單中徹底移除。</span><span class="sxs-lookup"><span data-stu-id="d081f-189">During this time, Microsoft Managed Desktop will remove the device from the public list entirely.</span></span> <span data-ttu-id="d081f-190">在這個階段中, 如果您尚未知道取代, 您將會開始向下移動服務, 因為 Microsoft 受管理的桌面會開始向下延展到不符合規範的裝置。</span><span class="sxs-lookup"><span data-stu-id="d081f-190">It’s also during this phase where, if you haven't already procured replacements, you'll start to see diminished services as Microsoft Managed Desktop starts to ramp down on the devices which are out of compliance.</span></span> 

## <a name="devices-that-are-out-of-compliance"></a><span data-ttu-id="d081f-191">不相容的裝置</span><span class="sxs-lookup"><span data-stu-id="d081f-191">Devices that are out of compliance</span></span>

<span data-ttu-id="d081f-192">當 Microsoft 受管理的桌面管理允許的視窗已過, 裝置就不符合規範。</span><span class="sxs-lookup"><span data-stu-id="d081f-192">A device is out of compliance when its allowed window for Microsoft Managed Desktop management has elapsed.</span></span> <span data-ttu-id="d081f-193">當裝置已達到三年的管理, 或從裝置目錄移除該產品類型時, 會發生這種情況, 這會先發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="d081f-193">This occurs when the device has reached three years of management or when that product type is removed from the device catalog, whichever occurs first.</span></span> <span data-ttu-id="d081f-194">您應該一直瞄準您的採購週期, 如此一來, 新的裝置會在目前的裝置不相容的情況之前部署。</span><span class="sxs-lookup"><span data-stu-id="d081f-194">You should always target your procurement cycles such that new devices are deployed prior to current devices going out of compliance.</span></span>

<span data-ttu-id="d081f-195">Microsoft 受管理的桌面小組知道採購週期很長, 而且會圍繞長期執行的預算進行規劃。</span><span class="sxs-lookup"><span data-stu-id="d081f-195">The Microsoft Managed Desktop team knows that procurement cycles are long and planned around long-running budgets.</span></span> <span data-ttu-id="d081f-196">為了確保您始終知道裝置人口的狀態, 我們提供一個[網站](https://aka.ms/mmdportal), 列出管理下的每個裝置、未來的退休日期, 以及指出其合規性的狀態。</span><span class="sxs-lookup"><span data-stu-id="d081f-196">To ensure that you're always aware of the state of your device population, we provide a [website](https://aka.ms/mmdportal) that lists every device under management, its future retirement date, and a status indicating its compliance.</span></span> <span data-ttu-id="d081f-197">這表示您永遠會有裝置保留時間的最新資訊, 並可在任何採購規劃週期中利用報告。</span><span class="sxs-lookup"><span data-stu-id="d081f-197">This means you always have the latest information regarding device age and can leverage the report in any procurement planning cycle.</span></span> 


<span data-ttu-id="d081f-198">此外, 我們也會採取下列自動化動作, 以確保新裝置按時部署:</span><span class="sxs-lookup"><span data-stu-id="d081f-198">In addition, the we will also take the following automated actions to ensure that new devices are deployed on time:</span></span>


|<span data-ttu-id="d081f-199">時間表</span><span class="sxs-lookup"><span data-stu-id="d081f-199">Timeline</span></span>  |<span data-ttu-id="d081f-200">動作</span><span class="sxs-lookup"><span data-stu-id="d081f-200">Action</span></span>  |
|---------|---------|
|<span data-ttu-id="d081f-201">T-90</span><span class="sxs-lookup"><span data-stu-id="d081f-201">T-90</span></span>     | <span data-ttu-id="d081f-202">我們會將此裝置標記為即將**過期**, 並在裝置清查網站上加上黃色標記。</span><span class="sxs-lookup"><span data-stu-id="d081f-202">We'll flag this device as **expiring soon**, with a yellow marker on the device inventory website.</span></span>  |
|<span data-ttu-id="d081f-203">T-60</span><span class="sxs-lookup"><span data-stu-id="d081f-203">T-60</span></span>     | <span data-ttu-id="d081f-204">我們會使用裝置清查網站上的紅色標記, 將此裝置標記為 [已**過期**]。</span><span class="sxs-lookup"><span data-stu-id="d081f-204">We'll flag this device as **expiring** with a red marker on the device inventory website.</span></span>       |
|<span data-ttu-id="d081f-205">T-30</span><span class="sxs-lookup"><span data-stu-id="d081f-205">T-30</span></span>     | <span data-ttu-id="d081f-206">我們會將訊息張貼至系統管理入口網站, 指出裝置的 imminently 已退出規範。</span><span class="sxs-lookup"><span data-stu-id="d081f-206">We'll post a message to the Admin Portal saying that devices are imminently exiting compliance.</span></span>       |
|<span data-ttu-id="d081f-207">零</span><span class="sxs-lookup"><span data-stu-id="d081f-207">0</span></span>     |  <span data-ttu-id="d081f-208">我們會調整系統管理入口網站, 表示裝置現在已過期將系統管理員重新導向裝置清單上的土地。</span><span class="sxs-lookup"><span data-stu-id="d081f-208">We'll adjust the Admin Portal to say that devices are now expired redirect admins to land on the device list first.</span></span>       |
|<span data-ttu-id="d081f-209">T + 30</span><span class="sxs-lookup"><span data-stu-id="d081f-209">T+30</span></span>     |  <span data-ttu-id="d081f-210">在部署新的裝置之前, 我們會降低系統管理入口網站的功能。</span><span class="sxs-lookup"><span data-stu-id="d081f-210">We'll reduce Admin Portal functionality until new devices are deployed.</span></span>       |
|<span data-ttu-id="d081f-211">T + 60</span><span class="sxs-lookup"><span data-stu-id="d081f-211">T+60</span></span>     |  <span data-ttu-id="d081f-212">在部署新的裝置之前, 我們會降低系統管理入口網站的功能。</span><span class="sxs-lookup"><span data-stu-id="d081f-212">We'll reduce Admin Portal functionality until new devices are deployed.</span></span>       |
|<span data-ttu-id="d081f-213">T + 90</span><span class="sxs-lookup"><span data-stu-id="d081f-213">T+90</span></span>     |  <span data-ttu-id="d081f-214">我們從管理移除裝置。</span><span class="sxs-lookup"><span data-stu-id="d081f-214">We remove the device from management.</span></span> <span data-ttu-id="d081f-215">此時, 裝置只是您自己的責任, 您應該不會再認為它是安全的, 也不是最新的。</span><span class="sxs-lookup"><span data-stu-id="d081f-215">At this point, the device is solely your own responsibility and you should no longer consider it secure nor up to date.</span></span> <span data-ttu-id="d081f-216">此外, 裝置也會處於未知狀態, 因為每個設定服務提供者會控制自己的設定。</span><span class="sxs-lookup"><span data-stu-id="d081f-216">Also the device will be in an unknown state since each Configuration Service provider controls its own settings.</span></span>|




