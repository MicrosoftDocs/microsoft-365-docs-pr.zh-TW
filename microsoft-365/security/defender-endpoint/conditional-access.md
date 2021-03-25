---
title: 啟用條件式存取，以更好地保護使用者、裝置和資料
description: 啟用條件式存取，以防止在裝置遭到危險時執行應用程式，並判斷應用程式是否不相容。
keywords: 條件式存取、封鎖應用程式、安全性層級、intune
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166194"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a><span data-ttu-id="e9ec0-104">啟用條件式存取，以更好地保護使用者、裝置和資料</span><span class="sxs-lookup"><span data-stu-id="e9ec0-104">Enable Conditional Access to better protect users, devices, and data</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e9ec0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e9ec0-105">**Applies to:**</span></span>
- [<span data-ttu-id="e9ec0-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e9ec0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e9ec0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9ec0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e9ec0-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e9ec0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e9ec0-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

<span data-ttu-id="e9ec0-110">條件式存取是一項功能，可確保只有安全的裝置能夠存取應用程式，以協助您更好地保護使用者和公司資訊。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-110">Conditional Access is a capability that helps you better protect your users and enterprise information by making sure that only secure devices have access to applications.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

<span data-ttu-id="e9ec0-111">使用條件式存取，您可以根據裝置的風險層級來控制公司資訊的存取。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-111">With Conditional Access, you can control access to enterprise information based on the risk level of a device.</span></span> <span data-ttu-id="e9ec0-112">這有助於讓信任的使用者在信任的裝置上使用受信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-112">This helps keep trusted users on trusted devices using trusted applications.</span></span>

<span data-ttu-id="e9ec0-113">您可以在裝置回到相容狀態時強制執行原則，以阻止應用程式執行並存取網路上的資訊，以定義安全性條件。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-113">You can define security conditions under which devices and applications can run and access information from your network by enforcing policies to stop applications from running until a device returns to a compliant state.</span></span> 

<span data-ttu-id="e9ec0-114">在 Defender for Endpoint 中的條件式存取的實施是以 Microsoft Intune 為基礎， (Intune) 裝置合規性原則和 Azure Active Directory (Azure AD) 條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-114">The implementation of Conditional Access in Defender for Endpoint is based on Microsoft Intune (Intune) device compliance policies and Azure Active Directory (Azure AD) conditional access policies.</span></span> 

<span data-ttu-id="e9ec0-115">相容性原則與條件式存取一起使用，僅允許滿足一或多項裝置合規性原則規則的裝置存取應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-115">The compliance policy is used with Conditional Access to allow only devices that fulfill one or more device compliance policy rules to access applications.</span></span> 

## <a name="understand-the-conditional-access-flow"></a><span data-ttu-id="e9ec0-116">瞭解條件式存取流程</span><span class="sxs-lookup"><span data-stu-id="e9ec0-116">Understand the Conditional Access flow</span></span>
<span data-ttu-id="e9ec0-117">設定條件式存取時，當在裝置上看到威脅時，就會封鎖敏感內容的存取，直到威脅修正為止。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-117">Conditional Access is put in place so that when a threat is seen on a device, access to sensitive content is blocked until the threat is remediated.</span></span> 

<span data-ttu-id="e9ec0-118">流程會從顯示為低、中或高風險的裝置開始。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-118">The flow begins with devices being seen to have a low, medium, or high risk.</span></span> <span data-ttu-id="e9ec0-119">然後這些風險會決定會傳送至 Intune。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-119">These risk determinations are then sent to Intune.</span></span> 

<span data-ttu-id="e9ec0-120">根據您在 Intune 中設定原則的方式，可以設定條件式存取，以便在符合某些條件時，套用原則。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-120">Depending on how you configure policies in Intune, Conditional Access can be set up so that when certain conditions are met, the policy is applied.</span></span>

<span data-ttu-id="e9ec0-121">例如，您可以設定 Intune 在具有高風險的裝置上套用條件式存取。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-121">For example, you can configure Intune to apply Conditional Access on devices that have a high risk.</span></span>

<span data-ttu-id="e9ec0-122">在 Intune 中，裝置相容性原則會搭配 Azure AD 條件式存取使用，以封鎖對應用程式的存取。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-122">In Intune, a device compliance policy is used in conjunction with Azure AD Conditional Access to block access to applications.</span></span> <span data-ttu-id="e9ec0-123">同時會啟動自動化調查和修正處理常式。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-123">In parallel, an automated investigation and remediation process is launched.</span></span>

 <span data-ttu-id="e9ec0-124">當自動調查和修正進行時，使用者仍可使用裝置，但是會封鎖企業資料存取，直到威脅完全得以修正為止。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-124">A user can still use the device while the automated investigation and remediation is taking place, but access to enterprise data is blocked until the threat is fully remediated.</span></span> 

<span data-ttu-id="e9ec0-125">若要解決裝置上發現的風險，您必須將該裝置恢復為相容的狀態。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-125">To resolve the risk found on a device, you'll need to return the device to a compliant state.</span></span> <span data-ttu-id="e9ec0-126">當裝置上未出現任何風險時，裝置會回到相容狀態。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-126">A device returns to a compliant state when there is no risk seen on it.</span></span> 

<span data-ttu-id="e9ec0-127">有三種方法可以解決風險：</span><span class="sxs-lookup"><span data-stu-id="e9ec0-127">There are three ways to address a risk:</span></span>
1. <span data-ttu-id="e9ec0-128">使用手動或自動修復。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-128">Use Manual or automated remediation.</span></span>
2. <span data-ttu-id="e9ec0-129">解決裝置上的主動警示。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-129">Resolve active alerts on the device.</span></span> <span data-ttu-id="e9ec0-130">這將會移除裝置中的風險。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-130">This will remove the risk from the device.</span></span>
3. <span data-ttu-id="e9ec0-131">您可以從作用中的原則移除裝置，因此不會在裝置上套用條件式存取。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-131">You can remove the device from the active policies and consequently, Conditional Access will not be applied on the device.</span></span> 

<span data-ttu-id="e9ec0-132">手動修正需要 secops 管理員才能調查警示，並解決裝置上看到的風險。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-132">Manual remediation requires a secops admin to investigate an alert and address the risk seen on the device.</span></span> <span data-ttu-id="e9ec0-133">自動修正是透過下列各節中提供的設定設定來設定：設定 [條件式存取](configure-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-133">The automated remediation is configured through configuration settings provided in the following section, [Configure Conditional Access](configure-conditional-access.md).</span></span>

<span data-ttu-id="e9ec0-134">透過手動或自動修復來移除風險時，裝置會回到相容狀態，並且會授與應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-134">When the risk is removed either through manual or automated remediation, the device returns to a compliant state and access to applications is granted.</span></span>

<span data-ttu-id="e9ec0-135">下列事件的範例會說明條件式存取的動作：</span><span class="sxs-lookup"><span data-stu-id="e9ec0-135">The following example sequence of events explains Conditional Access in action:</span></span>

1. <span data-ttu-id="e9ec0-136">使用者開啟惡意檔案和 Defender for Endpoint，將裝置旗標為高風險。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-136">A user opens a malicious file and Defender for Endpoint flags the device as high risk.</span></span>
2. <span data-ttu-id="e9ec0-137">將高風險評估傳遞給 Intune。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-137">The high risk assessment is passed along to Intune.</span></span> <span data-ttu-id="e9ec0-138">在並行中，會啟動自動化調查以修正已識別的威脅。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-138">In parallel, an automated investigation is initiated to remediate the identified threat.</span></span> <span data-ttu-id="e9ec0-139">您也可以採取手動修正以修正已識別的威脅。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-139">A manual remediation can also be done to remediate the identified threat.</span></span>
3. <span data-ttu-id="e9ec0-140">根據在 Intune 中建立的原則，裝置會標示為不相容。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-140">Based on the policy created in Intune, the device is marked as not compliant.</span></span> <span data-ttu-id="e9ec0-141">然後，會透過 Intune 條件式存取原則將評估傳遞給 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-141">The assessment is then communicated to Azure AD by the Intune Conditional Access policy.</span></span> <span data-ttu-id="e9ec0-142">在 Azure AD 中，會套用對應的原則，以封鎖對應用程式的存取。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-142">In Azure AD, the corresponding policy is applied to block access to applications.</span></span>
4. <span data-ttu-id="e9ec0-143">手動或自動調查和修正已完成，且威脅已移除。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-143">The manual or automated investigation and remediation is completed and the threat is removed.</span></span> <span data-ttu-id="e9ec0-144">Defender for Endpoint 會看到裝置上沒有任何風險，而且 Intune 會將裝置評估為相容狀態。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-144">Defender for Endpoint sees that there is no risk on the device and Intune assesses the device to be in a compliant state.</span></span> <span data-ttu-id="e9ec0-145">Azure AD 會套用允許存取應用程式的原則。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-145">Azure AD applies the policy which allows access to applications.</span></span>
5. <span data-ttu-id="e9ec0-146">使用者現在可以存取應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9ec0-146">Users can now access applications.</span></span>

 
## <a name="related-topic"></a><span data-ttu-id="e9ec0-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="e9ec0-147">Related topic</span></span>
- [<span data-ttu-id="e9ec0-148">在 Microsoft Defender for Endpoint 中設定條件式存取</span><span class="sxs-lookup"><span data-stu-id="e9ec0-148">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>](configure-conditional-access.md)
