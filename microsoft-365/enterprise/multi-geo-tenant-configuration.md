---
title: Microsoft 365 多地理位置租用戶組態
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: 在本文中，了解如何為 Microsoft 365 多地理位置新增衛星位置及設定您的租用戶。
ms.openlocfilehash: 9176c66e8d0aa7e893ef137131147f8e0c85d3ac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923645"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a><span data-ttu-id="bbf21-103">Microsoft 365 多地理位置租用戶組態</span><span class="sxs-lookup"><span data-stu-id="bbf21-103">Microsoft 365 Multi-Geo tenant configuration</span></span>

<span data-ttu-id="bbf21-104">為您的租用戶設定 Microsoft 365 多地理位置之前，請確定您已閱讀[規劃 Microsoft 365 多地理位置](plan-for-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf21-104">Before you configure your tenant for Microsoft 365 Multi-Geo, be sure you have read [Plan for Microsoft 365 Multi-Geo](plan-for-multi-geo.md).</span></span> <span data-ttu-id="bbf21-105">若要按照本文中的步驟操作，您需要一個要啟用為衛星位置的地理位置清單，以及您要在這些位置佈建的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="bbf21-105">To follow the steps in this article, you'll need a list of the geo locations that you want to enable as satellite locations, and the test users that you want to provision for those locations.</span></span>

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a><span data-ttu-id="bbf21-106">將 Microsoft 365 方案中的多地理位置功能新增到您的租用戶</span><span class="sxs-lookup"><span data-stu-id="bbf21-106">Add the Multi-Geo Capabilities in your Microsoft 365 plan to your tenant</span></span>

<span data-ttu-id="bbf21-107">若要使用 Microsoft 365 多地理位置，您需要「Microsoft 365 中的多地理位置功能」方案。</span><span class="sxs-lookup"><span data-stu-id="bbf21-107">To use Microsoft 365 Multi-Geo, you need the _Multi-Geo Capabilities in Microsoft 365_ plan.</span></span> <span data-ttu-id="bbf21-108">請與您的帳戶小組合作，將此方案新增到您的租用戶。</span><span class="sxs-lookup"><span data-stu-id="bbf21-108">Work with your account team to add this plan to your tenant.</span></span> <span data-ttu-id="bbf21-109">您的帳戶小組會協助您聯繫適當的授權專員，讓您完成租用戶設定。</span><span class="sxs-lookup"><span data-stu-id="bbf21-109">Your account team will connect you with the appropriate licensing specialist and get your tenant configured.</span></span>

<span data-ttu-id="bbf21-p103">請注意，「Microsoft 365 的多地理位置功能」方案是使用者層級的服務方案。對於您要在衛星位置裝載的每個使用者，您都需要有授權。隨著您在衛星位置中新增使用者，您可以逐漸新增更多授權。</span><span class="sxs-lookup"><span data-stu-id="bbf21-p103">Note that the _Multi-Geo Capabilities in Microsoft 365_ plan are a user-level service plan. You need a license for each user that you want to host in a satellite location. You can add more licenses over time as you add users in satellite locations.</span></span>

<span data-ttu-id="bbf21-113">在租用戶佈建「Microsoft 365 的多地理位置功能」方案後，OneDrive 和 SharePoint 系統管理中心的 [地理位置] 索引標籤會變成可用。</span><span class="sxs-lookup"><span data-stu-id="bbf21-113">Once your tenant has been provisioned with the  _Multi-Geo Capabilities in Microsoft 365_ plan, the **Geo locations** tab will become available in the OneDrive and SharePoint admin centers.</span></span>

## <a name="add-satellite-locations-to-your-tenant"></a><span data-ttu-id="bbf21-114">將衛星位置新增至您的租用戶</span><span class="sxs-lookup"><span data-stu-id="bbf21-114">Add satellite locations to your tenant</span></span>

<span data-ttu-id="bbf21-115">您必須為要儲存資料的每個地理位置新增衛星位置。</span><span class="sxs-lookup"><span data-stu-id="bbf21-115">You must add a satellite location for each geo location where you want to store data.</span></span> <span data-ttu-id="bbf21-116">下表提供可用的地理位置：</span><span class="sxs-lookup"><span data-stu-id="bbf21-116">Available geo locations are shown in the following table:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![SharePoint 系統管理中心中地理位置頁面的螢幕擷取畫面](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="bbf21-118">新增衛星位置</span><span class="sxs-lookup"><span data-stu-id="bbf21-118">To add a satellite location</span></span>

1. <span data-ttu-id="bbf21-119">開啟 SharePoint 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="bbf21-119">Open the SharePoint admin center.</span></span>

2. <span data-ttu-id="bbf21-120">瀏覽至 [地理位置] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bbf21-120">Navigate to the **Geo locations** tab.</span></span>

3. <span data-ttu-id="bbf21-121">按一下 [新增位置]。</span><span class="sxs-lookup"><span data-stu-id="bbf21-121">Click **Add location**.</span></span>

4. <span data-ttu-id="bbf21-122">選取您要新增的位置，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="bbf21-122">Select the location that you want to add, and then click **Next**.</span></span>

5. <span data-ttu-id="bbf21-123">輸入您要搭配地理位置使用的網域，然後按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="bbf21-123">Type the domain that you want to use with the geo location, and then click **Add**.</span></span>

6. <span data-ttu-id="bbf21-124">按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="bbf21-124">Click **Close**.</span></span>

<span data-ttu-id="bbf21-p105">佈建可能需要幾小時，最多 72 小時，視租用戶大小而定。衛星位置的佈建完成後，您將會收到電子郵件確認。當新的地理位置在 OneDrive 系統管理中心的 [**地理位置**] 索引標籤上以藍色顯示在地圖上，您就可以繼續將使用者慣用的資料位置設定到該地理位置。</span><span class="sxs-lookup"><span data-stu-id="bbf21-p105">Provisioning may take from a few hours up to 72 hours, depending on the size of your tenant. Once provisioning of a satellite location has completed, you will receive an email confirmation. When the new geo location appears in blue on the map on the **Geo locations** tab in the OneDrive admin center, you can proceed to set users' preferred data location to that geo location.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="bbf21-p106">您的新衛星位置將會以預設設定進行設定。這可讓您依當地合規性需求來設定該衛星位置。</span><span class="sxs-lookup"><span data-stu-id="bbf21-p106">Your new satellite location will be set up with default settings. This will allow you to configure that satellite location as appropriate for your local compliance needs.</span></span>

## <a name="setting-users-preferred-data-location"></a><span data-ttu-id="bbf21-130">設定使用者的慣用資料位置</span><span class="sxs-lookup"><span data-stu-id="bbf21-130">Setting users' preferred data location</span></span>
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

<span data-ttu-id="bbf21-p107">一旦啟用所需的衛星位置，您就可以更新使用者帳戶以使用適當的慣用資料位置。建議您為每個使用者設定慣用的資料位置，即使該使用者會停留在中央位置。</span><span class="sxs-lookup"><span data-stu-id="bbf21-p107">Once you enable the needed satellite locations, you can update your user accounts to use the appropriate preferred data location. We recommend that you set a preferred data location for every user, even if that user is staying in the central location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbf21-133">如果使用者的慣用資料位置設定為尚未設定衛星位置或中央位置的位置，當佈建 OneDrive 和 SharePoint 網站和群組信箱時，系統將預設其為中央位置。</span><span class="sxs-lookup"><span data-stu-id="bbf21-133">If a user's preferred data location is set to a location that has not been configured as a satellite location or the central location, the system will default to the central location when provisioning OneDrive and SharePoint sites and Group mailboxes.</span></span>

> [!TIP]
> <span data-ttu-id="bbf21-134">建議您從測試使用者或一小群使用者開始進行驗證，再向整個組織推出多地理位置。</span><span class="sxs-lookup"><span data-stu-id="bbf21-134">We recommend that you begin validations with a test user or small group of users before rolling out multi-geo to your broader organization.</span></span>

<span data-ttu-id="bbf21-135">在 Azure Active Directory (Azure AD) 中有兩種使用者物件：雲端專用使用者和同步處理的使用者。</span><span class="sxs-lookup"><span data-stu-id="bbf21-135">In Azure Active Directory (Azure AD) there are two types of user objects: cloud only users and synchronized users.</span></span> <span data-ttu-id="bbf21-136">請依照您的使用者類型採取相應指示。</span><span class="sxs-lookup"><span data-stu-id="bbf21-136">Please follow the appropriate instructions for your type of user.</span></span>

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a><span data-ttu-id="bbf21-137">使用 Azure AD Connect 同步處理使用者的慣用資料位置</span><span class="sxs-lookup"><span data-stu-id="bbf21-137">Synchronize user's Preferred Data Location using Azure AD Connect</span></span> 

<span data-ttu-id="bbf21-138">如果貴公司的使用者已從內部部署的 Active Directory 系統同步處理到 Azure AD，則必須在 AD 中填入 PreferredDataLocation，並同步處理到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="bbf21-138">If your company's users are synchronized from an on-premises Active Directory system to Azure AD, their PreferredDataLocation must be populated in AD and synchronized to Azure AD.</span></span>

<span data-ttu-id="bbf21-139">請依照 [Azure Active Directory Connect 同步處理：設定 Microsoft 365 資源的慣用資料位置](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation)中的程序，將慣用資料位置從您的內部部署 Active Directory Domain Services (AD DS) 同步處理到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="bbf21-139">Follow the process in [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) to configure Preferred Data Location sync from your on-premises Active Directory Domain Services (AD DS) to Azure AD.</span></span>

<span data-ttu-id="bbf21-140">建議您將設定使用者的慣用資料位置納入標準使用者建立工作流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="bbf21-140">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbf21-141">對於未佈建 OneDrive 的新使用者，請在使用者的 PDL 與 Azure AD 同步後至少等待 24 小時，以便在使用者登入商務用 OneDrive 之前傳播變更。</span><span class="sxs-lookup"><span data-stu-id="bbf21-141">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is synchronized to Azure AD for the changes to propagate before the user logs in to OneDrive for Business.</span></span> <span data-ttu-id="bbf21-142">(在使用者登入來佈建其商務用 OneDrive 之前設定慣用資料位置，可確保使用者的新 OneDrive 佈建在正確的位置。)</span><span class="sxs-lookup"><span data-stu-id="bbf21-142">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

### <a name="setting-preferred-data-location-for-cloud-only-users"></a><span data-ttu-id="bbf21-143">為雲端專用使用者設定慣用的資料位置</span><span class="sxs-lookup"><span data-stu-id="bbf21-143">Setting Preferred Data Location for cloud only users</span></span> 

<span data-ttu-id="bbf21-144">如果貴公司的使用者不是從內部部署 Active Directory 系統同步處理到 Azure AD，這表示使用者是在 Microsoft 365 或 Azure AD 中建立，則必須使用適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組設定 PDL。</span><span class="sxs-lookup"><span data-stu-id="bbf21-144">If your company's users are not synchronized from an on-premises Active Directory system to Azure AD, meaning they are created in Microsoft 365 or Azure AD, then the PDL must be set using the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

<span data-ttu-id="bbf21-145">此章節的程序需要[適用於 Windows PowerShell 的 Microsoft Azure Active Directory 模組](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0)。</span><span class="sxs-lookup"><span data-stu-id="bbf21-145">The procedures in this section require the [Microsoft Azure Active Directory Module for Windows PowerShell Module](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0).</span></span> <span data-ttu-id="bbf21-146">如果您已安裝此模組，請確認更新到最新的版本。</span><span class="sxs-lookup"><span data-stu-id="bbf21-146">If you already have this module installed, please ensure you update to the latest version.</span></span>

1.  <span data-ttu-id="bbf21-147">使用租用戶的全域系統管理員認證，[連線並登入](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bbf21-147">[Connect and sign in](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) with a set of global administrator credentials for your tenant.</span></span>

2.  <span data-ttu-id="bbf21-p111">使用 [Set-MsolUser](/powershell/msonline/v1/set-msoluser) Cmdlet 為每個使用者設定慣用資料位置。例如：</span><span class="sxs-lookup"><span data-stu-id="bbf21-p111">Use the [Set-MsolUser](/powershell/msonline/v1/set-msoluser) cmdlet to set the preferred data location for each of your users. For example:</span></span>

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    <span data-ttu-id="bbf21-p112">您可以檢查以確認慣用的資料位置已使用 Get-MsolUser Cmdlet 正確更新。例如：</span><span class="sxs-lookup"><span data-stu-id="bbf21-p112">You can check to confirm that the preferred data location was updated properly by using the Get-MsolUser cmdlet. For example:</span></span>

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![顯示 set-msoluser 的 PowerShell 視窗螢幕擷取畫面](../media/multi-geo-tenant-configuration-image3.png)

<span data-ttu-id="bbf21-153">建議您將設定使用者的慣用資料位置納入標準使用者建立工作流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="bbf21-153">We recommend that you include setting the user's Preferred Data Location as a part of your standard user creation workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbf21-154">對於未佈建 OneDrive 的新使用者，請在使用者的 PDL 設定後至少等待 24 小時，以便在使用者登入 OneDrive 之前傳播變更。</span><span class="sxs-lookup"><span data-stu-id="bbf21-154">For new users with no OneDrive provisioned, wait at least 24 hours after a user's PDL is set for the changes to propagate before the user logs in to OneDrive.</span></span> <span data-ttu-id="bbf21-155">(在使用者登入來佈建其商務用 OneDrive 之前設定慣用資料位置，可確保使用者的新 OneDrive 佈建在正確的位置。)</span><span class="sxs-lookup"><span data-stu-id="bbf21-155">(Setting the preferred data location before the user logs in to provision their OneDrive for Business ensures that the user's new OneDrive will be provisioned in the correct location.)</span></span>

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a><span data-ttu-id="bbf21-156">OneDrive 佈建及 PDL 的影響</span><span class="sxs-lookup"><span data-stu-id="bbf21-156">OneDrive Provisioning and the effect of PDL</span></span>

<span data-ttu-id="bbf21-157">如果使用者的租用戶中已建立 OneDrive 網站，設定其 PDL 不會自動移動其現有的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="bbf21-157">If the user already has a OneDrive site created in the tenant, setting their PDL will not automatically move their existing OneDrive.</span></span> <span data-ttu-id="bbf21-158">若要移動使用者的 OneDrive，請參閱 [OneDrive 進行商務用異地移動](move-onedrive-between-geo-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf21-158">To move a user's OneDrive, see [OneDrive for Business Geo Move](move-onedrive-between-geo-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bbf21-159">Exchange Online 會在 PLD 變更且 MailboxRegion 不再符合信箱資料庫地理位置碼時，自動重新安置使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="bbf21-159">Exchange Online automatically relocates the user's mailbox if the PLD changes and the MailboxRegion no longer matches the Mailbox Database Geo Location code.</span></span> <span data-ttu-id="bbf21-160">如需詳細資訊，請參閱 [在多地理位置環境中管理 Exchange Online 信箱](./administering-exchange-online-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf21-160">For more information, see [Administering Exchange Online mailboxes in a multi-geo environment](./administering-exchange-online-multi-geo.md).</span></span>

<span data-ttu-id="bbf21-161">如果使用者在租用戶中沒有 OneDrive 網站，OneDrive 會根據其 PDL 值進行佈建，並假設使用者的 PDL 符合公司的其中一個衛星位置。</span><span class="sxs-lookup"><span data-stu-id="bbf21-161">If the user does not have a OneDrive site within the tenant, OneDrive will be provisioned for them in accordance to their PDL value, assuming the PDL for the user matches one of the company's satellite locations.</span></span>

## <a name="configuring-multi-geo-search"></a><span data-ttu-id="bbf21-162">設定多地理位置搜尋</span><span class="sxs-lookup"><span data-stu-id="bbf21-162">Configuring Multi-Geo search</span></span>

<span data-ttu-id="bbf21-163">多地理位置租用戶具有彙總搜尋功能，可讓搜尋查詢從租用戶中的任何位置傳回結果。</span><span class="sxs-lookup"><span data-stu-id="bbf21-163">Your multi-geo tenant will have aggregate search capabilities allowing a search query to return results from anywhere within the tenant.</span></span>

<span data-ttu-id="bbf21-164">根據預設，從這些進入點搜尋會傳回彙總的結果，即使每個搜尋索引都位於其相關的地理位置內：</span><span class="sxs-lookup"><span data-stu-id="bbf21-164">By default, searches from these entry points will return aggregate results, even though each search index is located within its relevant geo location:</span></span>

- <span data-ttu-id="bbf21-165">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="bbf21-165">OneDrive for Business</span></span>

- <span data-ttu-id="bbf21-166">Delve</span><span class="sxs-lookup"><span data-stu-id="bbf21-166">Delve</span></span>

- <span data-ttu-id="bbf21-167">SharePoint 首頁</span><span class="sxs-lookup"><span data-stu-id="bbf21-167">SharePoint Home</span></span>

- <span data-ttu-id="bbf21-168">搜尋中心</span><span class="sxs-lookup"><span data-stu-id="bbf21-168">Search Center</span></span>

<span data-ttu-id="bbf21-169">此外，多地理位置搜尋功能可針對使用 SharePoint 搜尋 API 的自訂搜尋應用程式進行設定。</span><span class="sxs-lookup"><span data-stu-id="bbf21-169">Additionally, multi-geo search capabilities can be configured for your custom search applications that use the SharePoint search API.</span></span>

<span data-ttu-id="bbf21-170">請檢閱[為商務用 OneDrive 多地理位置設定搜尋](configure-search-for-multi-geo.md)以取得相關指示，包括任何限制與差異。</span><span class="sxs-lookup"><span data-stu-id="bbf21-170">Please review [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for instructions including any limitations and differences.</span></span>

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a><span data-ttu-id="bbf21-171">驗證 Microsoft 365 多地理位置組態</span><span class="sxs-lookup"><span data-stu-id="bbf21-171">Validating the Microsoft 365 Multi-Geo configuration</span></span>

<span data-ttu-id="bbf21-172">以下是在將 Microsoft 365 多地理位置在貴公司廣泛推出之前，您可能希望在驗證計劃中包含的一些基本使用案例。</span><span class="sxs-lookup"><span data-stu-id="bbf21-172">Below are some basic use cases you may wish to include in your validation plan before broadly rolling out Microsoft 365 Multi-Geo to your company.</span></span> <span data-ttu-id="bbf21-173">完成這些測試以及與貴公司相關的任何其他使用案例後，您可以選擇繼續新增使用者到一開始的試驗組。</span><span class="sxs-lookup"><span data-stu-id="bbf21-173">Once you have completed these tests and any additional use cases that are relevant to your company, you may choose to move on to adding the users in your initial pilot group.</span></span>

<span data-ttu-id="bbf21-174">**商務用 OneDrive**</span><span class="sxs-lookup"><span data-stu-id="bbf21-174">**OneDrive for Business**</span></span>

<span data-ttu-id="bbf21-175">從 Microsoft 365 應用程式啟動器中選取 OneDrive，並根據使用者的 PDL 確認您將自動導向到使用者的相應地理位置。</span><span class="sxs-lookup"><span data-stu-id="bbf21-175">Select OneDrive from the Microsoft 365 app launcher and confirm that you are automatically directed to the appropriate geo location for the user, based on the user's PDL.</span></span> <span data-ttu-id="bbf21-176">商務用 OneDrive 現在應該開始佈建到該位置。</span><span class="sxs-lookup"><span data-stu-id="bbf21-176">OneDrive for Business should now begin provisioning at that location.</span></span> <span data-ttu-id="bbf21-177">佈建之後，請嘗試上傳和下載一些文件。</span><span class="sxs-lookup"><span data-stu-id="bbf21-177">Once provisioned, try uploading and downloading some documents.</span></span>

<span data-ttu-id="bbf21-178">**OneDrive 行動應用程式**</span><span class="sxs-lookup"><span data-stu-id="bbf21-178">**OneDrive Mobile App**</span></span>

<span data-ttu-id="bbf21-179">使用您的測試帳號憑證登入 OneDrive 行動裝置應用程式。</span><span class="sxs-lookup"><span data-stu-id="bbf21-179">Log into your OneDrive mobile App with your test account credentials.</span></span> <span data-ttu-id="bbf21-180">確認您可以看到您的商務用 OneDrive 檔案，並可從行動裝置與檔案互動。</span><span class="sxs-lookup"><span data-stu-id="bbf21-180">Confirm that you can see your OneDrive for Business files and can interact with them from your mobile device.</span></span>

<span data-ttu-id="bbf21-181">**OneDrive 同步處理用戶端**</span><span class="sxs-lookup"><span data-stu-id="bbf21-181">**OneDrive sync client**</span></span>

<span data-ttu-id="bbf21-p119">確認 OneDrive 同步處理用戶端會在登入時自動偵測商務用 OneDrive 的地理位置。如果您要下載同步處理用戶端，請按一下 OneDrive 文件庫中的 [**同步處理**]。</span><span class="sxs-lookup"><span data-stu-id="bbf21-p119">Confirm that the OneDrive sync client automatically detects your OneDrive for Business geo location upon login. If you need to download the sync client, you can click **Sync** in the OneDrive library.</span></span>

<span data-ttu-id="bbf21-184">**Office 應用程式**</span><span class="sxs-lookup"><span data-stu-id="bbf21-184">**Office applications**</span></span>

<span data-ttu-id="bbf21-p120">請確認您可以從 Office 應用程式 (如 Word) 登入，以存取商務用 OneDrive。開啟 Office 應用程式並選取 [OneDrive – <TenantName>]。Office 會偵測您的 OneDrive 位置，並顯示您可以開啟的檔案。</span><span class="sxs-lookup"><span data-stu-id="bbf21-p120">Confirm that you can access OneDrive for Business by logging in from an Office application, such as Word. Open the Office application and select "OneDrive – <TenantName>". Office will detect your OneDrive location and show you the files that you can open.</span></span>

<span data-ttu-id="bbf21-188">**共用**</span><span class="sxs-lookup"><span data-stu-id="bbf21-188">**Sharing**</span></span>

<span data-ttu-id="bbf21-p121">嘗試共用 OneDrive 檔案。確認人員選擇器顯示您的所有 SharePoint 線上使用者，無論其地理位置為何。</span><span class="sxs-lookup"><span data-stu-id="bbf21-p121">Try sharing OneDrive files. Confirm that the people picker shows you all your SharePoint online users regardless of their geo location.</span></span>