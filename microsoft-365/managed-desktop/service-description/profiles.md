---
title: 瞭解裝置設定檔
description: 管理員可指派給裝置的各種設定檔
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 5b5421d2b4001b813d3bcc1e804cae7fb05d0fa7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841999"
---
# <a name="device-profiles"></a><span data-ttu-id="51288-104">裝置設定檔</span><span class="sxs-lookup"><span data-stu-id="51288-104">Device profiles</span></span>

<span data-ttu-id="51288-105">您可以將不同的預先設定設定 ( 「裝置設定檔」 ) 指派給裝置，並針對特定類型的使用者需求進行優化。</span><span class="sxs-lookup"><span data-stu-id="51288-105">You can assign different pre-set configurations ("device profiles") to devices, each optimized for the needs of specific types of users.</span></span> <span data-ttu-id="51288-106">可使用三個裝置設定檔：</span><span class="sxs-lookup"><span data-stu-id="51288-106">Three device profiles are available:</span></span>

- <span data-ttu-id="51288-107">標準版</span><span class="sxs-lookup"><span data-stu-id="51288-107">Standard</span></span>
- <span data-ttu-id="51288-108">機密資料</span><span class="sxs-lookup"><span data-stu-id="51288-108">Sensitive Data</span></span>
- <span data-ttu-id="51288-109">Power user</span><span class="sxs-lookup"><span data-stu-id="51288-109">Power user</span></span>

<span data-ttu-id="51288-110">您可以將裝置設定檔視為裝置設定選項階層的一部分。</span><span class="sxs-lookup"><span data-stu-id="51288-110">You can think of device profiles as being part of a hierarchy of device configuration options.</span></span>

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="以棱錐方式顯示裝置設定。描述如下":::

<span data-ttu-id="51288-112">從根本上而言，每個 Microsoft 受管理的電腦裝置都有一個基礎，其中包含標準安全性基準、相容性原則、Windows 更新設定和群組。</span><span class="sxs-lookup"><span data-stu-id="51288-112">Fundamentally, every Microsoft Managed Desktop device has a foundation that includes a standard security baseline, compliance policies, Windows Update settings, and groups.</span></span> <span data-ttu-id="51288-113">若要使用 Microsoft 受管理的電腦，每個裝置都必須包含所有這些元素，而不需要 Microsoft 受管理的電腦要求，系統管理員無法變更這些元素。</span><span class="sxs-lookup"><span data-stu-id="51288-113">To work with Microsoft Managed Desktop, every device must include all of these elements, which can't be changed by admins without a request to Microsoft Managed Desktop.</span></span>

<span data-ttu-id="51288-114">裝置設定檔會出現在下一個較高的層級。</span><span class="sxs-lookup"><span data-stu-id="51288-114">Device profiles appear at the next higher level.</span></span> <span data-ttu-id="51288-115">每個 Microsoft 受管理的電腦裝置都必須有一個 (，且只指派一個) 設定檔。</span><span class="sxs-lookup"><span data-stu-id="51288-115">Every Microsoft Managed Desktop device must have one (and only one) profile assigned.</span></span> <span data-ttu-id="51288-116">管理員可以選擇要指派裝置的設定檔。</span><span class="sxs-lookup"><span data-stu-id="51288-116">Admins can choose which profile a device is assigned.</span></span>

<span data-ttu-id="51288-117">在另一個較高級別的 [自訂](customizing.md)專案。</span><span class="sxs-lookup"><span data-stu-id="51288-117">At a still higher level are additional [customizations](customizing.md).</span></span> <span data-ttu-id="51288-118">每個裝置可以有一或多個 (或沒有) 自訂。</span><span class="sxs-lookup"><span data-stu-id="51288-118">Each device can have one or more (or no) customizations.</span></span> <span data-ttu-id="51288-119">他們可以修改較低層級的層 (裝置設定檔或基礎設定) ，或是在標準設定之上階層式全新要求。</span><span class="sxs-lookup"><span data-stu-id="51288-119">They can either modify a lower-level layer (Device profiles or the foundational configuration),  or be an entirely new request that’s layered on top of the standard configuration.</span></span>

<span data-ttu-id="51288-120">在頂端是您自己的修改，例如網路詳細資料或應用程式。</span><span class="sxs-lookup"><span data-stu-id="51288-120">At the top are your own modifications, such as network details or applications.</span></span> <span data-ttu-id="51288-121">裝置可以有任何數目的修改，這些修改不受 Microsoft 受管理的電腦管理或封鎖。</span><span class="sxs-lookup"><span data-stu-id="51288-121">A device can have any number of these modifications, which aren't managed or blocked by Microsoft Managed Desktop.</span></span>


## <a name="device-profile-details"></a><span data-ttu-id="51288-122">裝置設定檔詳細資料</span><span class="sxs-lookup"><span data-stu-id="51288-122">Device profile details</span></span>

<span data-ttu-id="51288-123">下表摘要說明裝置設定檔設定之每個設定值的設定及其預設值。</span><span class="sxs-lookup"><span data-stu-id="51288-123">The following table summarizes the settings and their default values for each setting configured by device profiles.</span></span> <span data-ttu-id="51288-124"> (幕後，這些設定會透過 Microsoft 端點管理員中的自訂設定檔來設定 OMA-URIs。 ) </span><span class="sxs-lookup"><span data-stu-id="51288-124">(Behind the scenes, these settings are configured with OMA-URIs by using Custom Configuration Profiles in Microsoft Endpoint Manager.)</span></span>

<br>

****

|<span data-ttu-id="51288-125">功能</span><span class="sxs-lookup"><span data-stu-id="51288-125">Feature</span></span>|<span data-ttu-id="51288-126">機密資料</span><span class="sxs-lookup"><span data-stu-id="51288-126">Sensitive Data</span></span>|<span data-ttu-id="51288-127">Power User</span><span class="sxs-lookup"><span data-stu-id="51288-127">Power User</span></span>|<span data-ttu-id="51288-128">標準版</span><span class="sxs-lookup"><span data-stu-id="51288-128">Standard</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="51288-129">**封鎖外部儲存體**</span><span class="sxs-lookup"><span data-stu-id="51288-129">**Block External Storage**</span></span>|<span data-ttu-id="51288-130">是</span><span class="sxs-lookup"><span data-stu-id="51288-130">Yes</span></span>|<span data-ttu-id="51288-131">是</span><span class="sxs-lookup"><span data-stu-id="51288-131">Yes</span></span>|<span data-ttu-id="51288-132">否</span><span class="sxs-lookup"><span data-stu-id="51288-132">No</span></span>|
|<span data-ttu-id="51288-133">**[雲端封鎖層級](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**</span><span class="sxs-lookup"><span data-stu-id="51288-133">**[Cloud Block Level](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**</span></span>|<span data-ttu-id="51288-134">高</span><span class="sxs-lookup"><span data-stu-id="51288-134">High</span></span>|<span data-ttu-id="51288-135">高</span><span class="sxs-lookup"><span data-stu-id="51288-135">High</span></span>|<span data-ttu-id="51288-136">高</span><span class="sxs-lookup"><span data-stu-id="51288-136">High</span></span>|
|<span data-ttu-id="51288-137">**停用 Microsoft 帳戶**</span><span class="sxs-lookup"><span data-stu-id="51288-137">**Disable Microsoft Accounts**</span></span>|<span data-ttu-id="51288-138">是</span><span class="sxs-lookup"><span data-stu-id="51288-138">Yes</span></span>|<span data-ttu-id="51288-139">是</span><span class="sxs-lookup"><span data-stu-id="51288-139">Yes</span></span>|<span data-ttu-id="51288-140">否</span><span class="sxs-lookup"><span data-stu-id="51288-140">No</span></span>|
|<span data-ttu-id="51288-141">**停用個人 OneDrive**</span><span class="sxs-lookup"><span data-stu-id="51288-141">**Disable personal OneDrive**</span></span>|<span data-ttu-id="51288-142">是</span><span class="sxs-lookup"><span data-stu-id="51288-142">Yes</span></span>|<span data-ttu-id="51288-143">是</span><span class="sxs-lookup"><span data-stu-id="51288-143">Yes</span></span>|<span data-ttu-id="51288-144">否</span><span class="sxs-lookup"><span data-stu-id="51288-144">No</span></span>|
|<span data-ttu-id="51288-145">**切換至保護桌面以進行提升**</span><span class="sxs-lookup"><span data-stu-id="51288-145">**Switch to secure desktop for elevation**</span></span>|<span data-ttu-id="51288-146">否</span><span class="sxs-lookup"><span data-stu-id="51288-146">No</span></span>|<span data-ttu-id="51288-147">是</span><span class="sxs-lookup"><span data-stu-id="51288-147">Yes</span></span>|<span data-ttu-id="51288-148">否</span><span class="sxs-lookup"><span data-stu-id="51288-148">No</span></span>|
|<span data-ttu-id="51288-149">**Microsoft Defender for Endpoint Device 標記**</span><span class="sxs-lookup"><span data-stu-id="51288-149">**Microsoft Defender for Endpoint Device Tag**</span></span>|<span data-ttu-id="51288-150">M365Managed-SensitiveData</span><span class="sxs-lookup"><span data-stu-id="51288-150">M365Managed-SensitiveData</span></span>|<span data-ttu-id="51288-151">M365Managed-PowerUser</span><span class="sxs-lookup"><span data-stu-id="51288-151">M365Managed-PowerUser</span></span>|<span data-ttu-id="51288-152">M365Managed-Standard</span><span class="sxs-lookup"><span data-stu-id="51288-152">M365Managed-Standard</span></span>|
|<span data-ttu-id="51288-153">**裝置上的系統管理員？**</span><span class="sxs-lookup"><span data-stu-id="51288-153">**Admin on the device?**</span></span>|<span data-ttu-id="51288-154">否</span><span class="sxs-lookup"><span data-stu-id="51288-154">No</span></span>|<span data-ttu-id="51288-155">是</span><span class="sxs-lookup"><span data-stu-id="51288-155">Yes</span></span>|<span data-ttu-id="51288-156">否</span><span class="sxs-lookup"><span data-stu-id="51288-156">No</span></span>|
|<span data-ttu-id="51288-157">**Autopilot 設定檔**</span><span class="sxs-lookup"><span data-stu-id="51288-157">**Autopilot Profile**</span></span>|<span data-ttu-id="51288-158">MMD 標準</span><span class="sxs-lookup"><span data-stu-id="51288-158">MMD Standard</span></span>|<span data-ttu-id="51288-159">MMD Power User</span><span class="sxs-lookup"><span data-stu-id="51288-159">MMD Power User</span></span>|<span data-ttu-id="51288-160">MMD 標準</span><span class="sxs-lookup"><span data-stu-id="51288-160">MMD Standard</span></span>|
|<span data-ttu-id="51288-161">**AppLocker**</span><span class="sxs-lookup"><span data-stu-id="51288-161">**AppLocker**</span></span>|<span data-ttu-id="51288-162">是</span><span class="sxs-lookup"><span data-stu-id="51288-162">Yes</span></span>|<span data-ttu-id="51288-163">否</span><span class="sxs-lookup"><span data-stu-id="51288-163">No</span></span>|<span data-ttu-id="51288-164">否</span><span class="sxs-lookup"><span data-stu-id="51288-164">No</span></span>|
|<span data-ttu-id="51288-165">**封鎖公用存放區**</span><span class="sxs-lookup"><span data-stu-id="51288-165">**Block Public Store**</span></span>|<span data-ttu-id="51288-166">是</span><span class="sxs-lookup"><span data-stu-id="51288-166">Yes</span></span>|<span data-ttu-id="51288-167">是</span><span class="sxs-lookup"><span data-stu-id="51288-167">Yes</span></span>|<span data-ttu-id="51288-168">否</span><span class="sxs-lookup"><span data-stu-id="51288-168">No</span></span>|
|

<span data-ttu-id="51288-169">每個裝置設定檔也會包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="51288-169">Each device profile also involves these items:</span></span>

- <span data-ttu-id="51288-170">Azure Active Directory (AAD) 裝置群組的動態成員資格</span><span class="sxs-lookup"><span data-stu-id="51288-170">A dynamic membership Azure Active Directory (AAD) device group</span></span>
- <span data-ttu-id="51288-171">靜態成員 AAD 裝置群組</span><span class="sxs-lookup"><span data-stu-id="51288-171">A static membership AAD device group</span></span>
- <span data-ttu-id="51288-172">Microsoft 端點管理員設定檔</span><span class="sxs-lookup"><span data-stu-id="51288-172">A Microsoft Endpoint Manager Configuration profile</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51288-173">請勿直接修改這些群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="51288-173">Don’t modify the membership of these groups directly.</span></span> <span data-ttu-id="51288-174">使用 [重新指派設定檔](../working-with-managed-desktop/change-device-profile.md)中所述的介面。</span><span class="sxs-lookup"><span data-stu-id="51288-174">Use the interface as described in [Reassign profiles](../working-with-managed-desktop/change-device-profile.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="51288-175">限制</span><span class="sxs-lookup"><span data-stu-id="51288-175">Limitations</span></span>

<span data-ttu-id="51288-176">您可以像對待任何其他原則一樣，向裝置設定檔和其詳細資料要求例外狀況。</span><span class="sxs-lookup"><span data-stu-id="51288-176">You can request exceptions to the device profiles and their details as you would with any other policy.</span></span> <span data-ttu-id="51288-177">請記住，您的 Azure Active Directory 組織中只能有一個裝置設定檔 ( "承租人" ) 。</span><span class="sxs-lookup"><span data-stu-id="51288-177">Keep in mind that you can only have one of each device profile in your Azure Active Directory organization ("tenant").</span></span> <span data-ttu-id="51288-178">例如，您無法要求敏感性資料裝置設定檔只對部分使用者停用 AppLocker。</span><span class="sxs-lookup"><span data-stu-id="51288-178">For example, you can't request that the Sensitive data device profile disables AppLocker for only some of your users.</span></span> <span data-ttu-id="51288-179">具有敏感性資料設定檔的所有裝置都必須具有相同的設定。</span><span class="sxs-lookup"><span data-stu-id="51288-179">All devices with the Sensitive data profile must have the same configuration.</span></span>

<span data-ttu-id="51288-180">每個裝置只能有一個設定檔。</span><span class="sxs-lookup"><span data-stu-id="51288-180">Each device can only have one profile.</span></span> <span data-ttu-id="51288-181">如果有多個使用者使用指定的裝置，該裝置上的所有使用者將會有相同的設定。</span><span class="sxs-lookup"><span data-stu-id="51288-181">If a given device is used by more than one user, all users on that device will have the same configuration.</span></span>
