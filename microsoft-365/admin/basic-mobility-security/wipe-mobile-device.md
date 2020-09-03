---
title: 在基本行動及安全性中清除行動裝置
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 使用內建基本行動性和安全性，以移除已註冊裝置中的資訊。
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336777"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="8d349-103">在基本行動及安全性中清除行動裝置</span><span class="sxs-lookup"><span data-stu-id="8d349-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="8d349-104">您可以使用 Microsoft 365 的內建基本行動及安全性，只移除組織資訊，或執行出廠重設以刪除行動裝置中的所有資訊，並將其還原為出廠設定。</span><span class="sxs-lookup"><span data-stu-id="8d349-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8d349-105">開始之前</span><span class="sxs-lookup"><span data-stu-id="8d349-105">Before you begin</span></span>

<span data-ttu-id="8d349-106">行動裝置可以儲存敏感組織資訊，並提供組織的 Microsoft 365 資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="8d349-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="8d349-107">為了協助保護您組織的資訊，您可以進行原始重設或移除公司資料：</span><span class="sxs-lookup"><span data-stu-id="8d349-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>
    
- <span data-ttu-id="8d349-108">**恢復出廠設定**：刪除使用者行動裝置上的所有資料，包括已安裝的應用程式、相片和個人資訊。</span><span class="sxs-lookup"><span data-stu-id="8d349-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="8d349-109">當清除完成時，裝置會還原為其出廠設定。</span><span class="sxs-lookup"><span data-stu-id="8d349-109">When the wipe is complete, the device is restored to its factory settings.</span></span>
    
- <span data-ttu-id="8d349-110">**移除公司資料**：移除組織中的資料，並在使用者的行動裝置上保留已安裝的應用程式、相片和個人資訊。</span><span class="sxs-lookup"><span data-stu-id="8d349-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>   

- <span data-ttu-id="8d349-111">\*\*在擦除裝置時 (出廠重設或移除公司資料) \*\*中，裝置會從受管理的裝置清單中移除。</span><span class="sxs-lookup"><span data-stu-id="8d349-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="8d349-112">**自動重設裝置**：您可以設定基本行動性和安全性原則，當使用者未成功輸入裝置密碼的特定次數時，自動將裝置重設為自動出廠設定。</span><span class="sxs-lookup"><span data-stu-id="8d349-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="8d349-113">若要這麼做，請遵循以 [基本行動性和安全性建立裝置安全性原則](create-device-security-policies-in-basic-mmobility-and-security.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="8d349-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies-in-basic-mmobility-and-security.md).</span></span>
    
- <span data-ttu-id="8d349-114">**如果您想要知道** 您在擦除其裝置時的使用者體驗，請參閱  [使用者和裝置影響的情況為何？](#whats-the-user-and-device-impact)。</span><span class="sxs-lookup"><span data-stu-id="8d349-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>   

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="8d349-115">清除行動裝置</span><span class="sxs-lookup"><span data-stu-id="8d349-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="8d349-116">移至 [Microsoft 365 系統管理中心](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)。</span><span class="sxs-lookup"><span data-stu-id="8d349-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>
    
2. <span data-ttu-id="8d349-117">在 [搜尋] 欄位中輸入行動裝置管理，並從結果清單中選取 [行動 **裝置管理** ]。</span><span class="sxs-lookup"><span data-stu-id="8d349-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span> 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="基本行動裝置和 Secruity 行動裝置管理選項":::

3. <span data-ttu-id="8d349-119">選取 [ **管理裝置**]。</span><span class="sxs-lookup"><span data-stu-id="8d349-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="8d349-120">選取您要抹除的裝置。</span><span class="sxs-lookup"><span data-stu-id="8d349-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="8d349-121">選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="8d349-121">Select **Manage**.</span></span>

6. <span data-ttu-id="8d349-122">選取您要執行的遠端抹除類型。</span><span class="sxs-lookup"><span data-stu-id="8d349-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="8d349-123">若要執行完整清除並將裝置還原至其出廠設定，請選取 [ **原廠重設**]。</span><span class="sxs-lookup"><span data-stu-id="8d349-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="8d349-124">若要進行選擇性清除並只刪除 Microsoft 365 組織資訊，請選取 [ **移除公司資料**]。</span><span class="sxs-lookup"><span data-stu-id="8d349-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="8d349-125">若要從組織中移除裝置，請選取 [ **移除裝置**]。</span><span class="sxs-lookup"><span data-stu-id="8d349-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="8d349-126">選取 **[是]** 加以確認。</span><span class="sxs-lookup"><span data-stu-id="8d349-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="8d349-127">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="8d349-127">How do I know it worked?</span></span>

<span data-ttu-id="8d349-128">您不再在受管理的裝置清單中看到行動裝置。</span><span class="sxs-lookup"><span data-stu-id="8d349-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="8d349-129">為何要清除裝置？</span><span class="sxs-lookup"><span data-stu-id="8d349-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="8d349-130">請清除裝置，原因如下：</span><span class="sxs-lookup"><span data-stu-id="8d349-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="8d349-131">行動裝置（例如 smartphone 和平板電腦）現在已經變得完全齊全。</span><span class="sxs-lookup"><span data-stu-id="8d349-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="8d349-132">這表示您的使用者更容易儲存敏感的公司資訊，例如個人身分識別或機密通訊，並可在旅途中存取。</span><span class="sxs-lookup"><span data-stu-id="8d349-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="8d349-133">如果其中一位行動裝置遺失或被盜，擦除裝置可協助避免您的組織的資訊在錯誤的手中結束。</span><span class="sxs-lookup"><span data-stu-id="8d349-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="8d349-134">當使用者使用已註冊基本行動性和安全性的個人裝置離開組織時，您可以執行出廠重設，以防止組織資訊與該使用者互動。</span><span class="sxs-lookup"><span data-stu-id="8d349-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="8d349-135">如果您的組織為使用者提供行動裝置，您可能需要重新指派裝置的時間。</span><span class="sxs-lookup"><span data-stu-id="8d349-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="8d349-136">在裝置上進行原廠重設，將其指派給新的使用者，有助於確保刪除先前擁有者的任何機密資訊。</span><span class="sxs-lookup"><span data-stu-id="8d349-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="8d349-137">使用者和裝置影響為何？</span><span class="sxs-lookup"><span data-stu-id="8d349-137">What's the user and device impact?</span></span>

<span data-ttu-id="8d349-138">擦除會立即傳送給行動裝置，而且裝置會在 Azure active directory 中標示為不相容。</span><span class="sxs-lookup"><span data-stu-id="8d349-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="8d349-139">當裝置重設為出廠預設值時，會移除所有資料，下表會說明當您移除公司資料時，裝置會移除每種裝置類型的內容。</span><span class="sxs-lookup"><span data-stu-id="8d349-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="8d349-140">**內容 impace**</span><span class="sxs-lookup"><span data-stu-id="8d349-140">**Content impace**</span></span>|<span data-ttu-id="8d349-141">**iOS 10 和更新版本**</span><span class="sxs-lookup"><span data-stu-id="8d349-141">**iOS 10 and later**</span></span>|<span data-ttu-id="8d349-142">**Android 5 及更新版本**</span><span class="sxs-lookup"><span data-stu-id="8d349-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8d349-143">如果使用 Intune 應用程式保護原則保護裝置，則會清除 Microsoft 365 應用程式資料。</span><span class="sxs-lookup"><span data-stu-id="8d349-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="8d349-144">未移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="8d349-144">The apps aren't removed.</span></span> <span data-ttu-id="8d349-145">對於不是由行動應用程式管理 (MAM) 原則保護的裝置，Outlook 和 OneDrive 不會移除快取的資料。</span><span class="sxs-lookup"><span data-stu-id="8d349-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="8d349-146">**記事** 若要套用 Intune 應用程式保護原則，您必須要有 Intune 授權。</span><span class="sxs-lookup"><span data-stu-id="8d349-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="8d349-147">是</span><span class="sxs-lookup"><span data-stu-id="8d349-147">Yes</span></span>|<span data-ttu-id="8d349-148">是</span><span class="sxs-lookup"><span data-stu-id="8d349-148">Yes</span></span>|
|<span data-ttu-id="8d349-149">已不再執行基本行動性和裝置安全性所套用的原則設定;使用者可以變更設定。</span><span class="sxs-lookup"><span data-stu-id="8d349-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="8d349-150">是</span><span class="sxs-lookup"><span data-stu-id="8d349-150">Yes</span></span>|<span data-ttu-id="8d349-151">是</span><span class="sxs-lookup"><span data-stu-id="8d349-151">Yes</span></span>|
|<span data-ttu-id="8d349-152">已移除基本行動性和安全性所建立的電子郵件設定檔，並刪除裝置上的快取電子郵件。</span><span class="sxs-lookup"><span data-stu-id="8d349-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="8d349-153">是</span><span class="sxs-lookup"><span data-stu-id="8d349-153">Yes</span></span>|<span data-ttu-id="8d349-154">不適用</span><span class="sxs-lookup"><span data-stu-id="8d349-154">N/A</span></span>|
>[!NOTE] 
><span data-ttu-id="8d349-155">您可以在應用程式存放區中的 iOS 和適用于 Android 裝置的播放存放區中取得公司入口網站應用程式。</span><span class="sxs-lookup"><span data-stu-id="8d349-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d349-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="8d349-156">Related topics</span></span>

[<span data-ttu-id="8d349-157">設定基本行動與安全性</span><span class="sxs-lookup"><span data-stu-id="8d349-157">Set up Basic Mobility and Security</span></span>](set-up-basic-mobility-and-security.md)