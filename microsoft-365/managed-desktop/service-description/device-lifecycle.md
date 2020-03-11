---
title: Microsoft 受管理的桌面產品生命週期
description: 本主題列出 Microsoft Managed Desktop 中使用的裝置規格。
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: b65724a1eee35149d473fb69ff646b5ef5751b2c
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583170"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a><span data-ttu-id="b9d3b-104">Microsoft 受管理的桌面產品生命週期</span><span class="sxs-lookup"><span data-stu-id="b9d3b-104">Microsoft Managed Desktop product lifecycle</span></span>

<span data-ttu-id="b9d3b-105">Microsoft 受管理的桌面優點使用者可確保他們永遠使用提供最佳效能、可靠性、設計及安全性功能的裝置（例如支援 Windows Hello 等功能）。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-105">Microsoft Managed Desktop benefits end users assuring that they always use devices that offer the best performance, reliability, design, and security capabilities (such as support for features like Windows Hello).</span></span> <span data-ttu-id="b9d3b-106">為了達到此目的，Microsoft 受管理的桌面會維護連續更新之[認可裝置](device-list.md)的簡短目錄。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-106">To accomplish this, Microsoft Managed Desktop maintains a short catalog of continuously updated [approved devices](device-list.md).</span></span> 
 
<span data-ttu-id="b9d3b-107">此主題會在裝置從已核准的目錄中新增及移除時，詳細說明裝置的生命週期。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-107">This topic details the lifecycle of devices as they are added and removed from the approved catalog.</span></span> 

> [!NOTE]
> <span data-ttu-id="b9d3b-108">在本主題中，我們將區別「裝置」和「產品」。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-108">In this topic, we'll make a distinction between a "device" and a "product."</span></span> <span data-ttu-id="b9d3b-109">"裝置" 是指一部個別的特定電腦。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-109">By "device," we mean one individual, specific computer.</span></span> <span data-ttu-id="b9d3b-110">例如，"數列號碼 1234"，「帳單的膝上型電腦」，"Shared VM XYZ" 是指特定的裝置。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-110">For example, "Serial number 1234", "Bill's laptop", "Shared VM XYZ" refer to specific devices.</span></span> <span data-ttu-id="b9d3b-111">不過，"product" 是指裝置集合或裝置系列。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-111">A "product", however, refers to a collection or family of devices.</span></span> <span data-ttu-id="b9d3b-112">例如「Fabrikam 膝上型電腦」、「Adatum ZX450 膝上型電腦」等等。這一點很重要，因為產品會新增至我們[認可的清單](device-list.md)或目錄，而且裝置會註冊至 Microsoft 受管理的桌面。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-112">For example, "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. This is important because products are added to our [approved list](device-list.md), or catalog, and devices are what get enrolled into Microsoft Managed Desktop.</span></span>

## <a name="product-lifecycle"></a><span data-ttu-id="b9d3b-113">產品生命週期</span><span class="sxs-lookup"><span data-stu-id="b9d3b-113">Product lifecycle</span></span>

 <span data-ttu-id="b9d3b-114">一般來說，產品會經歷下列生命週期階段：</span><span class="sxs-lookup"><span data-stu-id="b9d3b-114">Generally, products move through these lifecycle phases:</span></span>

- [<span data-ttu-id="b9d3b-115">產品版本和評估</span><span class="sxs-lookup"><span data-stu-id="b9d3b-115">Product release and evaluation</span></span>](#product-release-and-evaluation)
- [<span data-ttu-id="b9d3b-116">產品主要可用性週期</span><span class="sxs-lookup"><span data-stu-id="b9d3b-116">Product primary availability period</span></span>](#product-primary-availability-period)
- [<span data-ttu-id="b9d3b-117">產品寬限期</span><span class="sxs-lookup"><span data-stu-id="b9d3b-117">Product grace period</span></span>](#product-grace-period)
- [<span data-ttu-id="b9d3b-118">產品退休</span><span class="sxs-lookup"><span data-stu-id="b9d3b-118">Product retirement</span></span>](#product-retirement)


<span data-ttu-id="b9d3b-119">此圖例顯示整個順序：</span><span class="sxs-lookup"><span data-stu-id="b9d3b-119">This illustration shows the entire sequence:</span></span>

![生命週期時程表：從產品一般可用性開始，「主要可用性」會持續兩年。](../../media/non-dark1-edits.PNG)

<span data-ttu-id="b9d3b-125">產品保留在目錄中，最多24個月，但<em>裝置</em>會維持在管理下，根據其個人登記日期3年。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-125">Products remain on the catalog for up to 24 months, but <em>devices</em> remain under management for 3 years based on their individual enrollment dates.</span></span> <span data-ttu-id="b9d3b-126">每個產品都有三個重要日期，但是每個裝置只有一個。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-126">Effectively, each product has three important dates, but each device has only one.</span></span> <span data-ttu-id="b9d3b-127">在產品中，這三個日期都是根據<em>核准日期</em>計算的，因此，我們會在核准時發佈這些日期，以供您在產品的整個生命週期中進行適當的查看和規劃。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-127">For products, all three of these dates are calculated based on the <em>approval date</em>, and therefore we publish these dates upon approval so that you can always look ahead and plan appropriately for the product's entire lifecycle.</span></span>

<span data-ttu-id="b9d3b-128">下表顯示理論產品的範例日期：</span><span class="sxs-lookup"><span data-stu-id="b9d3b-128">This table shows example dates for a theoretical product:</span></span>


|<span data-ttu-id="b9d3b-129">產品</span><span class="sxs-lookup"><span data-stu-id="b9d3b-129">Product</span></span>  |<span data-ttu-id="b9d3b-130">核准日期</span><span class="sxs-lookup"><span data-stu-id="b9d3b-130">Approved date</span></span>  |<span data-ttu-id="b9d3b-131">主要可用性結束</span><span class="sxs-lookup"><span data-stu-id="b9d3b-131">End of primary availability</span></span>  |<span data-ttu-id="b9d3b-132">資格的終止</span><span class="sxs-lookup"><span data-stu-id="b9d3b-132">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="b9d3b-133">Fabrikam 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="b9d3b-133">Fabrikam Laptop</span></span>    | <span data-ttu-id="b9d3b-134">1/1/2017</span><span class="sxs-lookup"><span data-stu-id="b9d3b-134">1/1/2017</span></span> | <span data-ttu-id="b9d3b-135">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="b9d3b-135">6/1/2019</span></span> | <span data-ttu-id="b9d3b-136">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="b9d3b-136">6/1/2022</span></span> |
|<span data-ttu-id="b9d3b-137">Adatum 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="b9d3b-137">Adatum Laptop</span></span>   | <span data-ttu-id="b9d3b-138">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="b9d3b-138">1/1/2018</span></span> | <span data-ttu-id="b9d3b-139">6/1/2020</span><span class="sxs-lookup"><span data-stu-id="b9d3b-139">6/1/2020</span></span> | <span data-ttu-id="b9d3b-140">6/1/2023</span><span class="sxs-lookup"><span data-stu-id="b9d3b-140">6/1/2023</span></span>  |

<span data-ttu-id="b9d3b-141">下表顯示理論*裝置*的範例日期：</span><span class="sxs-lookup"><span data-stu-id="b9d3b-141">This table shows example dates for theoretical *devices*:</span></span>


|<span data-ttu-id="b9d3b-142">裝置識別碼</span><span class="sxs-lookup"><span data-stu-id="b9d3b-142">Device ID</span></span>  |<span data-ttu-id="b9d3b-143">登記日期</span><span class="sxs-lookup"><span data-stu-id="b9d3b-143">Enrollment date</span></span>  |<span data-ttu-id="b9d3b-144">退休日期</span><span class="sxs-lookup"><span data-stu-id="b9d3b-144">Retirement date</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b9d3b-145">可擕式 #123412</span><span class="sxs-lookup"><span data-stu-id="b9d3b-145">Laptop #123412</span></span>     |  <span data-ttu-id="b9d3b-146">2/3/2018</span><span class="sxs-lookup"><span data-stu-id="b9d3b-146">2/3/2018</span></span>       |  <span data-ttu-id="b9d3b-147">2/3/2021</span><span class="sxs-lookup"><span data-stu-id="b9d3b-147">2/3/2021</span></span>       |
|<span data-ttu-id="b9d3b-148">桌面 #321513</span><span class="sxs-lookup"><span data-stu-id="b9d3b-148">Desktop #321513</span></span>     | <span data-ttu-id="b9d3b-149">6/2/2018</span><span class="sxs-lookup"><span data-stu-id="b9d3b-149">6/2/2018</span></span>        |  <span data-ttu-id="b9d3b-150">6/2/2021</span><span class="sxs-lookup"><span data-stu-id="b9d3b-150">6/2/2021</span></span>       |


## <a name="product-release-and-evaluation"></a><span data-ttu-id="b9d3b-151">產品版本和評估</span><span class="sxs-lookup"><span data-stu-id="b9d3b-151">Product release and evaluation</span></span>

<span data-ttu-id="b9d3b-152">當製造廠商公開發行產品時，產品生命週期即會啟動：</span><span class="sxs-lookup"><span data-stu-id="b9d3b-152">The product lifecycle starts when a manufacturer publicly releases the product:</span></span>

![生命週期時程表顯示發行和評估期間](../../media/non-dark3-edits.PNG)

<span data-ttu-id="b9d3b-154">在此階段中，Microsoft 受管理的桌面工程小組會執行產品的評估與認證。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-154">During this stage, the Microsoft Managed Desktop engineering team does their evaluation and certification of a product.</span></span> <span data-ttu-id="b9d3b-155">小組會評估與 Windows 的可靠性和效能等事項，遵循硬體基準、市場 sentiment、庫存及通道準備等專案等。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-155">The team evaluates things like reliability and performance with Windows, compliance with a hardware baseline, market sentiment, and inventory and channel readiness, among other things.</span></span> <span data-ttu-id="b9d3b-156">此處理程式通常需要大約6周。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-156">This process typically takes approximately 6 weeks.</span></span>
  
<span data-ttu-id="b9d3b-157">Microsoft 受管理的桌面只會評估其第6個月的可用性內的認證裝置。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-157">Microsoft Managed Desktop will only evaluate devices for certification within their first 6 months of availability.</span></span> <span data-ttu-id="b9d3b-158">這可確保我們永遠致力於最新的硬體產生。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-158">This ensures that we're always focusing our efforts on the latest generation of hardware.</span></span>
 
<span data-ttu-id="b9d3b-159">在這個階段結束時，Microsoft 受管理的桌面會將產品新增至[已核准清單](device-list.md)，並有效地發行產品以供客戶登記。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-159">At the end of this phase, Microsoft Managed Desktop adds the product to the [approved list](device-list.md), effectively releasing the product for customer enrollments.</span></span> <span data-ttu-id="b9d3b-160">不論裝置的認證日期為何，其**核准的日期**會回復為產品自身的一般供貨日。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-160">Regardless of the date when a device is certified, its **approved date** is back-dated to the product's own general availability date.</span></span> 


## <a name="product-primary-availability-period"></a><span data-ttu-id="b9d3b-161">產品主要可用性週期</span><span class="sxs-lookup"><span data-stu-id="b9d3b-161">Product primary availability period</span></span>

<span data-ttu-id="b9d3b-162">此期間是產品可用性的核心：</span><span class="sxs-lookup"><span data-stu-id="b9d3b-162">This period is the core of product availability:</span></span>

![生命週期時程表顯示主要可用性](../../media/non-dark4-edits.PNG)

<span data-ttu-id="b9d3b-164">在此期間內註冊的任何裝置都會從 Microsoft Managed Desktop 取得完整三年的支援（如藍色的時程表所示）。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-164">Any device enrolled during this period receives the full three years of support from Microsoft Managed Desktop (as shown by the blue timeline).</span></span> <span data-ttu-id="b9d3b-165">此期間會持續到結束日期設定為從一般可用日期到24個月為止。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-165">This period lasts until an end date set to 24 months from the general availability date.</span></span>

<span data-ttu-id="b9d3b-166">您可以將此期間視為有效的「開啟註冊」，讓 Microsoft Managed Desktop 達到最大的價值，您應該針對您的採購模型和選取的產品在此期間內。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-166">You can think of this period as effectively "open enrollment", so to maximize the value of Microsoft Managed Desktop, you should target your procurement models and selected products to fall within this period.</span></span> <span data-ttu-id="b9d3b-167">舉例來說，客戶應避免使用主要可用性之最後一個月的產品來結算兩年期的外推行，這大部分裝置都不會收到完整三年的 Microsoft 受管理桌面管理（請參閱[寬限期](#product-grace-period)以取得詳細資訊）。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-167">As a small example, a customer should avoid settling on a two-year roll-out period using a product that is in its final month of primary availability – most of those devices will not receive the full three years of Microsoft Managed Desktop management (see [grace period](#product-grace-period) for more information).</span></span>  

## <a name="product-grace-period"></a><span data-ttu-id="b9d3b-168">產品寬限期</span><span class="sxs-lookup"><span data-stu-id="b9d3b-168">Product grace period</span></span>

<span data-ttu-id="b9d3b-169">產品寬限期是一年三年的主要可用性的期限。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-169">The product grace period is a three-year period following primary availability.</span></span> <span data-ttu-id="b9d3b-170">此階段可讓您登記來自支援之產品系列的裝置，但仍可保留公司，以與現代硬體和裝置效能的 Microsoft 受管理的桌上型電腦承諾有關。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-170">This phase allows you to enroll devices that are from a supported product family, but still hold firm to the promises of Microsoft Managed Desktop regarding modern hardware and device performance.</span></span> <span data-ttu-id="b9d3b-171">這一階段非常適合在瞭解 Microsoft 受管理的桌面之前進行採購決策的客戶。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-171">This phase is ideal for customers who have made procurement decisions before knowing about Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="b9d3b-172">如果您最近在使用 Microsoft 受管理的桌上型電腦註冊之前購買了許多已核准的裝置，您仍然可以註冊，但您不會收到完整三年的管理。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-172">If you've recently bought a number of approved devices prior to enrolling with Microsoft Managed Desktop, you can still enroll them, but you won't receive a full three years of management.</span></span> <span data-ttu-id="b9d3b-173">相反地，他們會因退休日期而不符合規範，不論他們登記的時間為何。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-173">Instead, they'll fall out of compliance on the retirement date, regardless of when they were enrolled.</span></span> <span data-ttu-id="b9d3b-174">在幕後，Microsoft Managed Desktop 會將這些裝置視為在主要可用性的最後一天註冊。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-174">Behind the scenes, Microsoft Managed Desktop will treat these devices as if they were enrolled on the last day of primary availability.</span></span> <span data-ttu-id="b9d3b-175">在此圖中，您可以注意到這種情況，只要您注意到藍色和綠色裝置都在同一天結束（不論其註冊的年差異為1年）。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-175">In this illustration, you can see this scenario by noting that both the blue and green device end on the same day, despite their one-year difference in enrollment:</span></span>


![顯示寬限期的生命週期時程表](../../media/non-dark2-edits.PNG)

<span data-ttu-id="b9d3b-177">上表中的 Fabrikam 膝上型電腦範例說明這種情況：</span><span class="sxs-lookup"><span data-stu-id="b9d3b-177">The Fabrikam Laptop example from the previous table illustrates this situation:</span></span> 

|<span data-ttu-id="b9d3b-178">產品</span><span class="sxs-lookup"><span data-stu-id="b9d3b-178">Product</span></span>  |<span data-ttu-id="b9d3b-179">核准日期</span><span class="sxs-lookup"><span data-stu-id="b9d3b-179">Approved date</span></span>  |<span data-ttu-id="b9d3b-180">主要可用性結束</span><span class="sxs-lookup"><span data-stu-id="b9d3b-180">End of primary availability</span></span>  |<span data-ttu-id="b9d3b-181">資格的終止</span><span class="sxs-lookup"><span data-stu-id="b9d3b-181">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="b9d3b-182">Fabrikam 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="b9d3b-182">Fabrikam Laptop</span></span>    | <span data-ttu-id="b9d3b-183">6/1/2017</span><span class="sxs-lookup"><span data-stu-id="b9d3b-183">6/1/2017</span></span> | <span data-ttu-id="b9d3b-184">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="b9d3b-184">6/1/2019</span></span> | <span data-ttu-id="b9d3b-185">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="b9d3b-185">6/1/2022</span></span> |

<span data-ttu-id="b9d3b-186">身為客戶，您可以在6/1/2022 時註冊 Fabrikam 膝上型電腦，但會將它們視為您在6/1/2019 上登記。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-186">As a customer, you can enroll Fabrikam Laptops all the way until 6/1/2022 – however they will all be treated as though you enrolled them on 6/1/2019.</span></span> <span data-ttu-id="b9d3b-187">如果您在6/1/2021 上註冊 Fabrikam 的膝上型電腦，您只會收到一年的管理。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-187">If you enroll a Fabrikam Laptop on 6/1/2021 you'll only get one year of management.</span></span> <span data-ttu-id="b9d3b-188">這個原則可讓您從先前支援的產品提取部分生命週期，而不需要提前購買新的裝置。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-188">This policy allows you to extract partial lifecycles from products that were previously supported, rather than having to procure new devices prematurely.</span></span> 

<span data-ttu-id="b9d3b-189">最後，在此階段中，裝置會從[裝置清單](device-list.md)中移除，並移至封存[裝置清單](archived-device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-189">Finally, during this phase the device is removed from the [device list](device-list.md) and moved to the [archived device list](archived-device-list.md).</span></span>


## <a name="product-retirement"></a><span data-ttu-id="b9d3b-190">產品退休</span><span class="sxs-lookup"><span data-stu-id="b9d3b-190">Product retirement</span></span>

<span data-ttu-id="b9d3b-191">產品退休是生命週期的最後階段。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-191">Product retirement is the final phase of the lifecycle.</span></span> <span data-ttu-id="b9d3b-192">在此階段中，不會在 Microsoft 受管理的電腦中登記該產品類型的新裝置，而且根據定義，所有現有的裝置現在超出其允許的三年期限。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-192">In this phase, no new devices of that product type can be enrolled in Microsoft Managed Desktop and, by definition, all existing devices are now outside their allowed three-year term.</span></span> <span data-ttu-id="b9d3b-193">在這段時間內，Microsoft Managed Desktop 會從公用清單中徹底移除裝置。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-193">During this time, Microsoft Managed Desktop will remove the device from the public list entirely.</span></span> <span data-ttu-id="b9d3b-194">在此階段中也有，如果您尚未開始更換，您將會在 Microsoft 受管理的桌面開始向下逐步向下移動，以降低合規性的裝置。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-194">It's also during this phase where, if you haven't already procured replacements, you'll start to see diminished services as Microsoft Managed Desktop starts to ramp down on the devices which are out of compliance.</span></span> 

## <a name="devices-that-are-out-of-compliance"></a><span data-ttu-id="b9d3b-195">不符合規範的裝置</span><span class="sxs-lookup"><span data-stu-id="b9d3b-195">Devices that are out of compliance</span></span>

<span data-ttu-id="b9d3b-196">當 Microsoft 受管理的桌面管理的允許視窗已過時，裝置不相容。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-196">A device is out of compliance when its allowed window for Microsoft Managed Desktop management has elapsed.</span></span> <span data-ttu-id="b9d3b-197">當裝置已到達三年的管理，或從裝置目錄移除該產品類型時，就會發生這種情況，視第一個原因而來。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-197">This occurs when the device has reached three years of management or when that product type is removed from the device catalog, whichever occurs first.</span></span> <span data-ttu-id="b9d3b-198">您應一定會以您的採購週期為目標，讓新裝置在目前的裝置不相容之前部署。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-198">You should always target your procurement cycles such that new devices are deployed prior to current devices going out of compliance.</span></span>

<span data-ttu-id="b9d3b-199">Microsoft 受管理的桌面小組知道採購週期很長，而且會圍繞長期執行預算進行規劃。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-199">The Microsoft Managed Desktop team knows that procurement cycles are long and planned around long-running budgets.</span></span> <span data-ttu-id="b9d3b-200">為了確保您永遠知道裝置人口的狀態，我們提供的[網站](https://aka.ms/mmdportal)會列出所有管理的裝置、其保留時間，以及指出其符合性的狀態。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-200">To ensure that you're always aware of the state of your device population, we provide a [website](https://aka.ms/mmdportal) that lists every device under management, its age, and a status indicating its compliance.</span></span> <span data-ttu-id="b9d3b-201">這表示您永遠具備裝置保留時間的最新資訊，而且可以在任何採購計畫週期中使用報告。</span><span class="sxs-lookup"><span data-stu-id="b9d3b-201">This means you always have the latest information regarding device age and can use the report in any procurement planning cycle.</span></span> 







