---
title: 當地語系化使用者經驗
description: 如何當地語系化使用者的裝置
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
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
ms.openlocfilehash: 20456ce837be60b707569ae07d4fb00b695b3a98
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445934"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="8051e-104">當地語系化使用者經驗</span><span class="sxs-lookup"><span data-stu-id="8051e-104">Localize the user experience</span></span>

<span data-ttu-id="8051e-105">Microsoft 受管理的桌面裝置的使用者可以在安裝程式期間，選取其選擇的語言。 ) 或之後的 (「全新體驗」。</span><span class="sxs-lookup"><span data-stu-id="8051e-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="8051e-106">在安裝期間 (「全新體驗」 ) </span><span class="sxs-lookup"><span data-stu-id="8051e-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="8051e-107">完成安裝程式的過程中，使用者可以選取其選擇的語言。</span><span class="sxs-lookup"><span data-stu-id="8051e-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="8051e-108">這項選取專案會影響下列屬性：</span><span class="sxs-lookup"><span data-stu-id="8051e-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="8051e-109">Windows 10 語言功能：</span><span class="sxs-lookup"><span data-stu-id="8051e-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="8051e-110">顯示語言</span><span class="sxs-lookup"><span data-stu-id="8051e-110">Display language</span></span>
    - <span data-ttu-id="8051e-111">鍵盤語言</span><span class="sxs-lookup"><span data-stu-id="8051e-111">Keyboard language</span></span>
    - <span data-ttu-id="8051e-112">依需求的語言相關功能</span><span class="sxs-lookup"><span data-stu-id="8051e-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="8051e-113">適用于企業語言功能的 Microsoft 365 應用程式：</span><span class="sxs-lookup"><span data-stu-id="8051e-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="8051e-114">顯示語言</span><span class="sxs-lookup"><span data-stu-id="8051e-114">Display language</span></span>
    - <span data-ttu-id="8051e-115">校對和製作工具</span><span class="sxs-lookup"><span data-stu-id="8051e-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="8051e-116">使用者可以在安裝程式期間選取語言，以根據需要取得與語言相關的功能。</span><span class="sxs-lookup"><span data-stu-id="8051e-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="8051e-117">完成安裝後</span><span class="sxs-lookup"><span data-stu-id="8051e-117">After completing setup</span></span>

<span data-ttu-id="8051e-118">在安裝程式完成之後，使用者可以隨時為 Windows 10 和 Microsoft 365 應用程式選取其選擇的語言。</span><span class="sxs-lookup"><span data-stu-id="8051e-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="8051e-119">特別是：</span><span class="sxs-lookup"><span data-stu-id="8051e-119">Specifically:</span></span>

- <span data-ttu-id="8051e-120">Windows 10 語言功能：</span><span class="sxs-lookup"><span data-stu-id="8051e-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="8051e-121">顯示語言</span><span class="sxs-lookup"><span data-stu-id="8051e-121">Display language</span></span>
    - <span data-ttu-id="8051e-122">鍵盤語言</span><span class="sxs-lookup"><span data-stu-id="8051e-122">Keyboard language</span></span>

- <span data-ttu-id="8051e-123">適用于企業語言功能的 Microsoft 365 應用程式：</span><span class="sxs-lookup"><span data-stu-id="8051e-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="8051e-124">顯示語言</span><span class="sxs-lookup"><span data-stu-id="8051e-124">Display language</span></span>
    - <span data-ttu-id="8051e-125">校對和製作工具</span><span class="sxs-lookup"><span data-stu-id="8051e-125">Proofing and authoring tools</span></span>

<span data-ttu-id="8051e-126">若要讓您的使用者能夠使用 Microsoft 365 應用程式的 [支援語言](#supported-languages) ，請將使用者新增至新式的辦公 **Language_Packs** 群組。</span><span class="sxs-lookup"><span data-stu-id="8051e-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="8051e-127">語言將會出現在 Intune 公司入口網站中。</span><span class="sxs-lookup"><span data-stu-id="8051e-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="8051e-128">支援的語言</span><span class="sxs-lookup"><span data-stu-id="8051e-128">Supported languages</span></span>

<span data-ttu-id="8051e-129">若為新裝置，製造商必須提供包含您所需語言的裝置影像。</span><span class="sxs-lookup"><span data-stu-id="8051e-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="8051e-130">如果製造商的影像包含的語言不是支援的語言清單中所提供的語言，則服務仍然支援該功能。</span><span class="sxs-lookup"><span data-stu-id="8051e-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="8051e-131">若要重複使用現有的裝置，您可能需要與您的 Microsoft 帳戶代表合作，以取得適當的影像。</span><span class="sxs-lookup"><span data-stu-id="8051e-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="8051e-132">如需詳細資訊，請參閱 [裝置影像](../service-description/device-images.md)。</span><span class="sxs-lookup"><span data-stu-id="8051e-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="8051e-133">Microsoft 受管理的桌面所提供的 [通用影像](../service-description/device-images.md#universal-image) 包含下列語言和 Windows 10：</span><span class="sxs-lookup"><span data-stu-id="8051e-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="8051e-134">英文 (US，GB，AU，CA，) </span><span class="sxs-lookup"><span data-stu-id="8051e-134">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="8051e-135">西班牙文 (西班牙，墨西哥) </span><span class="sxs-lookup"><span data-stu-id="8051e-135">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="8051e-136">日文</span><span class="sxs-lookup"><span data-stu-id="8051e-136">Japanese</span></span>
- <span data-ttu-id="8051e-137">法文 (法國，加拿大) </span><span class="sxs-lookup"><span data-stu-id="8051e-137">French (France, Canada)</span></span>
- <span data-ttu-id="8051e-138">德文</span><span class="sxs-lookup"><span data-stu-id="8051e-138">German</span></span>
- <span data-ttu-id="8051e-139">葡萄牙文 (巴西)</span><span class="sxs-lookup"><span data-stu-id="8051e-139">Portuguese (Brazil)</span></span>
- <span data-ttu-id="8051e-140">義大利文</span><span class="sxs-lookup"><span data-stu-id="8051e-140">Italian</span></span>
- <span data-ttu-id="8051e-141">Chinese Simplified</span><span class="sxs-lookup"><span data-stu-id="8051e-141">Chinese Simplified</span></span>
- <span data-ttu-id="8051e-142">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="8051e-142">Dutch</span></span>  
- <span data-ttu-id="8051e-143">瑞典文</span><span class="sxs-lookup"><span data-stu-id="8051e-143">Swedish</span></span>
- <span data-ttu-id="8051e-144">丹麥文</span><span class="sxs-lookup"><span data-stu-id="8051e-144">Danish</span></span>  
- <span data-ttu-id="8051e-145">芬蘭文</span><span class="sxs-lookup"><span data-stu-id="8051e-145">Finnish</span></span> 
- <span data-ttu-id="8051e-146">俄文</span><span class="sxs-lookup"><span data-stu-id="8051e-146">Russian</span></span> 
- <span data-ttu-id="8051e-147">挪威文 (巴克摩)</span><span class="sxs-lookup"><span data-stu-id="8051e-147">Norwegian (Bokmal)</span></span>
- <span data-ttu-id="8051e-148">韓文</span><span class="sxs-lookup"><span data-stu-id="8051e-148">Korean</span></span>
- <span data-ttu-id="8051e-149">Chinese Traditional</span><span class="sxs-lookup"><span data-stu-id="8051e-149">Chinese Traditional</span></span>
- <span data-ttu-id="8051e-150">波蘭文</span><span class="sxs-lookup"><span data-stu-id="8051e-150">Polish</span></span>
- <span data-ttu-id="8051e-151">土耳其文</span><span class="sxs-lookup"><span data-stu-id="8051e-151">Turkish</span></span>
- <span data-ttu-id="8051e-152">阿拉伯文</span><span class="sxs-lookup"><span data-stu-id="8051e-152">Arabic</span></span>
- <span data-ttu-id="8051e-153">希伯來文</span><span class="sxs-lookup"><span data-stu-id="8051e-153">Hebrew</span></span>
- <span data-ttu-id="8051e-154">葡萄牙文 (葡萄牙)</span><span class="sxs-lookup"><span data-stu-id="8051e-154">Portuguese (Portugal)</span></span>
- <span data-ttu-id="8051e-155">捷克文</span><span class="sxs-lookup"><span data-stu-id="8051e-155">Czech</span></span>
- <span data-ttu-id="8051e-156">匈牙利文</span><span class="sxs-lookup"><span data-stu-id="8051e-156">Hungarian</span></span>
- <span data-ttu-id="8051e-157">泰文</span><span class="sxs-lookup"><span data-stu-id="8051e-157">Thai</span></span>
- <span data-ttu-id="8051e-158">印尼文</span><span class="sxs-lookup"><span data-stu-id="8051e-158">Indonesian</span></span>
- <span data-ttu-id="8051e-159">希臘文</span><span class="sxs-lookup"><span data-stu-id="8051e-159">Greek</span></span>
- <span data-ttu-id="8051e-160">斯洛伐克文</span><span class="sxs-lookup"><span data-stu-id="8051e-160">Slovak</span></span>
- <span data-ttu-id="8051e-161">越南文</span><span class="sxs-lookup"><span data-stu-id="8051e-161">Vietnamese</span></span>
- <span data-ttu-id="8051e-162">斯洛維尼亞文</span><span class="sxs-lookup"><span data-stu-id="8051e-162">Slovenian</span></span>
- <span data-ttu-id="8051e-163">克羅埃西亞文</span><span class="sxs-lookup"><span data-stu-id="8051e-163">Croatian</span></span>
- <span data-ttu-id="8051e-164">羅馬尼亞文</span><span class="sxs-lookup"><span data-stu-id="8051e-164">Romanian</span></span>
- <span data-ttu-id="8051e-165">立陶宛文</span><span class="sxs-lookup"><span data-stu-id="8051e-165">Lithuanian</span></span>
- <span data-ttu-id="8051e-166">保加利亞文</span><span class="sxs-lookup"><span data-stu-id="8051e-166">Bulgarian</span></span>
- <span data-ttu-id="8051e-167">塞爾維亞文 (拉丁字母) </span><span class="sxs-lookup"><span data-stu-id="8051e-167">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="8051e-168">拉脫維亞文</span><span class="sxs-lookup"><span data-stu-id="8051e-168">Latvian</span></span>
- <span data-ttu-id="8051e-169">烏克蘭文</span><span class="sxs-lookup"><span data-stu-id="8051e-169">Ukrainian</span></span>
- <span data-ttu-id="8051e-170">愛沙尼亞文</span><span class="sxs-lookup"><span data-stu-id="8051e-170">Estonian</span></span>

<span data-ttu-id="8051e-171">Microsoft 365 應用程式的企業版可能支援稍有不同的清單。</span><span class="sxs-lookup"><span data-stu-id="8051e-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="8051e-172">如果您的使用者不需要這裡所列的語言，請使用系統[管理入口網站](access-admin-portal.md)來歸檔[支援要求](../working-with-managed-desktop/admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="8051e-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="8051e-173">支援和作業的語言</span><span class="sxs-lookup"><span data-stu-id="8051e-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="8051e-174">使用者支援</span><span class="sxs-lookup"><span data-stu-id="8051e-174">User support</span></span>
<span data-ttu-id="8051e-175">Microsoft 受管理的桌面只提供英文版支援。</span><span class="sxs-lookup"><span data-stu-id="8051e-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="8051e-176">如果使用者選擇 [取得説明] 應用程式中的其他語言，他們就能從一般的 Microsoft 支援通道取得支援，而不是直接從 Microsoft Managed Desktop 進行支援。</span><span class="sxs-lookup"><span data-stu-id="8051e-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="8051e-177">如需詳細資訊，請參閱 [取得使用者的](../working-with-managed-desktop/end-user-support.md)說明。</span><span class="sxs-lookup"><span data-stu-id="8051e-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="8051e-178">如果您的使用者需要其他語言的支援，您必須透過非 Microsoft 支援來源或您自己的組織提供此支援。</span><span class="sxs-lookup"><span data-stu-id="8051e-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="8051e-179">系統管理支援和作業</span><span class="sxs-lookup"><span data-stu-id="8051e-179">Admin support and operations</span></span>
<span data-ttu-id="8051e-180">Microsoft 受管理的桌面只會以英文提供系統管理員支援。</span><span class="sxs-lookup"><span data-stu-id="8051e-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="8051e-181">這包括管理員入口網站和所有與 Microsoft 受管理桌面作業的通訊。</span><span class="sxs-lookup"><span data-stu-id="8051e-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="8051e-182">除非另有指定，否則您應假設所有系統管理員相關的互動和介面皆為英文。</span><span class="sxs-lookup"><span data-stu-id="8051e-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


