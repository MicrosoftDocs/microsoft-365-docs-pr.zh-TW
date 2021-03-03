---
title: 管理多地理位置環境中的 Exchange Online 信箱
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: 瞭解如何使用 PowerShell 在您的 Microsoft 365 環境中管理 Exchange Online 多地理位置設定。
ms.openlocfilehash: 83889b4582d2e305b2cb9f07a64307e85d30be77
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406039"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="430bf-103">管理多地理位置環境中的 Exchange Online 信箱</span><span class="sxs-lookup"><span data-stu-id="430bf-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="430bf-104">Exchange Online PowerShell 是在您的 Microsoft 365 環境中查看及設定多地理屬性所需的。</span><span class="sxs-lookup"><span data-stu-id="430bf-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="430bf-105">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="430bf-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="430bf-106">您需要 [Microsoft Azure Active Directory PowerShell 模組](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) 1.1.166.0 版或使用 1.x 版的更新版本，才能查看使用者物件上的 **PreferredDataLocation** 屬性。</span><span class="sxs-lookup"><span data-stu-id="430bf-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="430bf-107">透過 AAD Connect 同步處理至 AAD 的使用者物件，您無法經由 AAD PowerShell 直接修改其 **PreferredDataLocation** 值。</span><span class="sxs-lookup"><span data-stu-id="430bf-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="430bf-108">您可以透過 AAD PowerShell 修改僅雲端的使用者物件。</span><span class="sxs-lookup"><span data-stu-id="430bf-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="430bf-109">若要連線到 Azure AD PowerShell，請參閱[連線至 PowerShell](connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="430bf-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="430bf-110">在 Exchange Online 多地理位置環境中，您不需要執行任何手動步驟，即可將 geos 新增至您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="430bf-110">In Exchange Online multi-geo environments, you don't need to do any manual steps to add geos to your tenant.</span></span> <span data-ttu-id="430bf-111">當您收到「多地理位置已準備好進行 Exchange Online」的訊息中心 post 之後，所有可用的 geos 都會準備好並設定供您使用。</span><span class="sxs-lookup"><span data-stu-id="430bf-111">After you receive the Message Center post that says multi-geo is ready for Exchange Online, all available geos will be ready and configured for you to use.</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="430bf-112">使用 Exchange Online PowerShell 直接連線到地理位置</span><span class="sxs-lookup"><span data-stu-id="430bf-112">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="430bf-113">一般而言，Exchange Online PowerShell 將連線到中央地理位置。</span><span class="sxs-lookup"><span data-stu-id="430bf-113">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="430bf-114">不過，您也可以直接連線到衛星地理位置。</span><span class="sxs-lookup"><span data-stu-id="430bf-114">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="430bf-115">由於效能改善，當您僅管理該位置中的使用者時，建議您直接連線到衛星地理位置。</span><span class="sxs-lookup"><span data-stu-id="430bf-115">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="430bf-116">安裝和使用 EXO V2 模組的需求，請參閱 [安裝及維護 EXO V2 模組](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。</span><span class="sxs-lookup"><span data-stu-id="430bf-116">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="430bf-117">若要將 Exchange Online PowerShell 連線到特定地理位置， *ConnectionUri* 參數與一般連線指示不同。</span><span class="sxs-lookup"><span data-stu-id="430bf-117">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="430bf-118">其餘命令和值則是相同的。</span><span class="sxs-lookup"><span data-stu-id="430bf-118">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="430bf-119">具體說來，您必須將此 `?email=<emailaddress>` 值新增至 _ConnectionUri_ 值的結尾。</span><span class="sxs-lookup"><span data-stu-id="430bf-119">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="430bf-120">`<emailaddress>` 是目標地理位置中 **任何** 信箱的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="430bf-120">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="430bf-121">您對該信箱的許可權或您的認證的關聯性不是因素;電子郵件地址只會告訴 Exchange Online PowerShell 要連接的地方。</span><span class="sxs-lookup"><span data-stu-id="430bf-121">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="430bf-122">Microsoft 365 或 Microsoft 365 GCC 客戶通常不需要使用 _ConnectionUri_ 參數以連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="430bf-122">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="430bf-123">不過，若要連線至特定地理位置，您必須使用 _ConnectionUri_ 參數，這樣您就可以 `?email=<emailaddress>` 在值中使用。</span><span class="sxs-lookup"><span data-stu-id="430bf-123">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a><span data-ttu-id="430bf-124">連接至 Exchange Online 中的地理位置 PowerShell</span><span class="sxs-lookup"><span data-stu-id="430bf-124">Connect to a geo location in Exchange Online PowerShell</span></span>

<span data-ttu-id="430bf-125">下列連線指示適用于已設定或未針對多重要素驗證 (MFA) 進行的帳戶。</span><span class="sxs-lookup"><span data-stu-id="430bf-125">The following connection instructions work for accounts that are or aren't configured for multi-factor authentication (MFA).</span></span>

1. <span data-ttu-id="430bf-126">在 Windows PowerShell 視窗中，執行下列命令來載入 EXO V2 模組：</span><span class="sxs-lookup"><span data-stu-id="430bf-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="430bf-127">在下列範例中，admin@contoso.onmicrosoft.com 是系統管理員帳戶，而目標地理位置是信箱 olga@contoso.onmicrosoft.com 所在的位置。</span><span class="sxs-lookup"><span data-stu-id="430bf-127">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. <span data-ttu-id="430bf-128">在出現的提示中輸入 admin@contoso.onmicrosoft.com 的密碼。</span><span class="sxs-lookup"><span data-stu-id="430bf-128">Enter the password for the admin@contoso.onmicrosoft.com in the prompt that appears.</span></span> <span data-ttu-id="430bf-129">如果為 MFA 設定帳戶，您也需要輸入安全性代碼。</span><span class="sxs-lookup"><span data-stu-id="430bf-129">If the account is configured for MFA, you also need to enter the security code.</span></span>

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="430bf-130">檢視您的 Exchange Online 組織中設定的可用地理位置</span><span class="sxs-lookup"><span data-stu-id="430bf-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="430bf-131">若要查看 Microsoft 365 多地理位置中設定的地理位置清單，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="430bf-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="430bf-132">檢視您的 Exchange Online 組織的中央地理位置</span><span class="sxs-lookup"><span data-stu-id="430bf-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="430bf-133">若要檢視您的租用戶的中央地理位置，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="430bf-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="430bf-134">尋找信箱的地理位置</span><span class="sxs-lookup"><span data-stu-id="430bf-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="430bf-135">Exchange Online PowerShell 中的 **Get-Mailbox** Cmdlet 會顯示信箱上的下列多地理位置相關屬性：</span><span class="sxs-lookup"><span data-stu-id="430bf-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="430bf-136">**資料庫**：與地理位置代碼對應的資料庫名稱前 3 個字母，它會告知您信箱目前所在的位置。</span><span class="sxs-lookup"><span data-stu-id="430bf-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="430bf-137">若為線上封存信箱，則應該使用 **ArchiveDatabase** 屬性。</span><span class="sxs-lookup"><span data-stu-id="430bf-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="430bf-138">**MailboxRegion**：指定系統管理員所設定的地理位置代碼 (從 Azure AD 中的 **PreferredDataLocation** 同步處理)。</span><span class="sxs-lookup"><span data-stu-id="430bf-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="430bf-139">**MailboxRegionLastUpdateTime**：指出 MailboxRegion 的上次更新時間 (自動或手動)。</span><span class="sxs-lookup"><span data-stu-id="430bf-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="430bf-140">若要查看信箱的這些屬性，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="430bf-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="430bf-141">例如，若要查看信箱 chris@contoso.onmicrosoft.com 的地理位置資訊，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="430bf-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="430bf-142">此命令的輸出看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="430bf-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="430bf-143">如果資料庫名稱中的地理位置代碼不符合 **MailboxRegion** 值，則信箱將會自動放入重新置放佇列中，並移至 **MailboxRegion** 值所指定的地理位置。 (Exchange Online 會在這些屬性值) 之間尋找不相符。</span><span class="sxs-lookup"><span data-stu-id="430bf-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="430bf-144">將現有僅雲端信箱移動至特定的地理位置</span><span class="sxs-lookup"><span data-stu-id="430bf-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="430bf-145">僅限雲端使用者是未透過 AAD Connect 同步處理至租用戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="430bf-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="430bf-146">此使用者是直接在 Azure AD 中建立。</span><span class="sxs-lookup"><span data-stu-id="430bf-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="430bf-147">使用適用於 Windows PowerShell 的 Azure AD 模組中的 **Get-MsolUser** 和 **Set-MsolUser** Cmdlet 來檢視或指定將儲存僅雲端使用者信箱的地理位置。</span><span class="sxs-lookup"><span data-stu-id="430bf-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="430bf-148">若要檢視使用者的 **PreferredDataLocation** 值，請在 Azure AD PowerShell 中使用此語法：</span><span class="sxs-lookup"><span data-stu-id="430bf-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="430bf-149">例如，若要查看使用者 michelle@contoso.onmicrosoft.com 的 **PreferredDataLocation** 值，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="430bf-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="430bf-150">若要修改僅雲端使用者物件的 **PreferredDataLocation** 值，請在 Azure AD PowerShell 中使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="430bf-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="430bf-151">例如，若要將使用者 michelle@contoso.onmicrosoft.com 的 **PreferredDataLocation** 值設定為歐盟 (EUR) 地理位置，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="430bf-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="430bf-152">如先前所述，您無法對內部部署 Active Directory 的同步處理使用者物件使用此程式。</span><span class="sxs-lookup"><span data-stu-id="430bf-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="430bf-153">您必須變更 Active Directory 中的 **PreferredDataLocation** 值，並使用 AAD Connect 將它同步處理。</span><span class="sxs-lookup"><span data-stu-id="430bf-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="430bf-154">如需詳細資訊，請參閱 [Azure Active Directory Connect 同步處理：設定 Microsoft 365 資源的慣用資料位置](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)。</span><span class="sxs-lookup"><span data-stu-id="430bf-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="430bf-155">將信箱重新定位到新的地理位置所需的時間取決於數個因素：</span><span class="sxs-lookup"><span data-stu-id="430bf-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="430bf-156">信箱的大小和類型。</span><span class="sxs-lookup"><span data-stu-id="430bf-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="430bf-157">要移動的信箱數量。</span><span class="sxs-lookup"><span data-stu-id="430bf-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="430bf-158">移動資源的可用性。</span><span class="sxs-lookup"><span data-stu-id="430bf-158">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="430bf-159">將非使用中的信箱移至特定地理位置</span><span class="sxs-lookup"><span data-stu-id="430bf-159">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="430bf-160">您無法移動出於相容性目的所保留的非使用中信箱 (例如，使用訴訟暫止) 中的信箱變更其 **PreferredDataLocation** 值。</span><span class="sxs-lookup"><span data-stu-id="430bf-160">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="430bf-161">若要將非使用中的信箱移至不同的地理位置，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="430bf-161">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="430bf-162">復原非使用中的信箱。</span><span class="sxs-lookup"><span data-stu-id="430bf-162">Recover the inactive mailbox.</span></span> <span data-ttu-id="430bf-163">如需相關指示，請參閱 [復原非使用中的信箱](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="430bf-163">For instructions, see [Recover an inactive mailbox](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).</span></span>

2. <span data-ttu-id="430bf-164">以信箱的名稱、別名、帳戶或電子郵件地址取代，以防止受管理的資料夾助理處理復原的信箱， \<MailboxIdentity\> 並在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="430bf-164">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="430bf-165">將 **Exchange Online Plan 2** 授權指派給復原的信箱。</span><span class="sxs-lookup"><span data-stu-id="430bf-165">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="430bf-166">您必須執行此步驟，才能將信箱還原為訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="430bf-166">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="430bf-167">如需相關指示，請參閱 [將授權指派給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="430bf-167">For instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

4. <span data-ttu-id="430bf-168">如前一節所述，在信箱上設定 **PreferredDataLocation** 值。</span><span class="sxs-lookup"><span data-stu-id="430bf-168">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="430bf-169">在您確認信箱已經移至新的地理位置之後，請將復原的信箱回復回訴訟暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="430bf-169">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="430bf-170">如需相關指示，請參閱 [將信箱設為訴訟暫止狀態](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold)。</span><span class="sxs-lookup"><span data-stu-id="430bf-170">For instructions, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="430bf-171">確認訴訟暫止已到位之後，讓受管理的資料夾助理以 \<MailboxIdentity\> 信箱的名稱、別名、帳戶或電子郵件地址取代，並在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中執行下列命令，以再次處理信箱：</span><span class="sxs-lookup"><span data-stu-id="430bf-171">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="430bf-172">移除與信箱相關聯的使用者帳戶，將信箱停用停用。</span><span class="sxs-lookup"><span data-stu-id="430bf-172">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="430bf-173">如需相關指示，請參閱 [刪除組織中的使用者](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)。</span><span class="sxs-lookup"><span data-stu-id="430bf-173">For instructions, see [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span></span> <span data-ttu-id="430bf-174">此步驟也會為其他用途發佈 Exchange Online Plan 2 授權。</span><span class="sxs-lookup"><span data-stu-id="430bf-174">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="430bf-175">**附注**：當您將非使用中的信箱移至不同的地理位置時，您可能會影響內容的搜尋結果，或從先前的地理位置搜尋該信箱的功能。</span><span class="sxs-lookup"><span data-stu-id="430bf-175">**Note**: When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="430bf-176">如需詳細資訊，請參閱 [在多地理位置環境中搜尋和匯出內容](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)。</span><span class="sxs-lookup"><span data-stu-id="430bf-176">For more information, see [Searching and exporting content in Multi-Geo environments](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="430bf-177">在特定地理位置建立新的雲端信箱</span><span class="sxs-lookup"><span data-stu-id="430bf-177">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="430bf-178">若要在特定地理位置建立新的信箱，您必須執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="430bf-178">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="430bf-179">如先前所述，設定 **PreferredDataLocation** 值。在 Exchange Online 中建立信箱 *之前，先*[將現有的雲端信箱移至特定地理位置](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location)區段。</span><span class="sxs-lookup"><span data-stu-id="430bf-179">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="430bf-180">例如，在您指派授權之前，請先在使用者上設定 **PreferredDataLocation** 值。</span><span class="sxs-lookup"><span data-stu-id="430bf-180">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="430bf-181">在設定 **PreferredDataLocation** 值的同時指派授權。</span><span class="sxs-lookup"><span data-stu-id="430bf-181">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="430bf-182">若要在特定地理位置建立新的僅雲端授權使用者 (未使用 AAD Connect 同步處理)，請在 Azure AD PowerShell 中使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="430bf-182">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="430bf-183">此範例會使用下列值為 Elizabeth Brunner 建立新的使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="430bf-183">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="430bf-184">使用者主體名稱：ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="430bf-184">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="430bf-185">名字：Elizabeth</span><span class="sxs-lookup"><span data-stu-id="430bf-185">First name: Elizabeth</span></span>
- <span data-ttu-id="430bf-186">姓氏：Brunner</span><span class="sxs-lookup"><span data-stu-id="430bf-186">Last name: Brunner</span></span>
- <span data-ttu-id="430bf-187">顯示名稱：Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="430bf-187">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="430bf-188">密碼：隨機產生並在命令的結果中顯示 (因為我們未使用 *Password* 參數)</span><span class="sxs-lookup"><span data-stu-id="430bf-188">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="430bf-189">授權：`contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="430bf-189">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="430bf-190">位置：澳洲 (AUS)</span><span class="sxs-lookup"><span data-stu-id="430bf-190">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="430bf-191">如需建立新的使用者帳戶和在 Azure AD PowerShell 中尋找 LicenseAssignment 值的詳細資訊，請參閱[使用 PowerShell 建立使用者帳戶](create-user-accounts-with-microsoft-365-powershell.md)和[使用 PowerShell 檢視授權與服務](view-licenses-and-services-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="430bf-191">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="430bf-192">如果您使用 Exchange Online PowerShell 來啟用信箱，並且需要直接在 **PreferredDataLocation** 中指定的地理位置建立信箱，則必須直接對雲端服務使用 Exchange Online Cmdlet，例如 **Enable-Mailbox** 或 **New-Mailbox**。</span><span class="sxs-lookup"><span data-stu-id="430bf-192">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="430bf-193">如果您使用內部部署 Exchange PowerShell 中的 **Enable-RemoteMailbox** Cmdlet，則會在中央地理位置建立信箱。</span><span class="sxs-lookup"><span data-stu-id="430bf-193">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="430bf-194">將特定地理位置中的現有內部部署信箱上線</span><span class="sxs-lookup"><span data-stu-id="430bf-194">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="430bf-195">您可以使用標準的上線工具和程序，將信箱從內部部署 Exchange 組織移轉至 Exchange Online，包括 [EAC 中的移轉儀表板](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)，以及 Exchange Online PowerShell 中的 [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="430bf-195">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="430bf-196">第一個步驟是驗證要上線的每個信箱均存在使用者物件，並驗證已在 Azure AD 中設定正確的 **PreferredDataLocation** 值。</span><span class="sxs-lookup"><span data-stu-id="430bf-196">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="430bf-197">上線工具會使用 **PreferredDataLocation** 值，並將信箱直接移轉至指定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="430bf-197">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="430bf-198">或者，您可以使用下列步驟，在特定地理位置直接將信箱上線，方法是在 Exchange Online PowerShell 中使用 [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="430bf-198">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="430bf-199">驗證要上線的每個信箱均存在使用者物件，並且 Azure AD 中的 **PreferredDataLocation** 已設定為需要的值。</span><span class="sxs-lookup"><span data-stu-id="430bf-199">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="430bf-200">**PreferredDataLocation** 的值會同步處理至 Exchange Online 中對應郵件使用者物件的 **MailboxRegion** 屬性。</span><span class="sxs-lookup"><span data-stu-id="430bf-200">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="430bf-201">使用稍早在本主題中的連線指示，直接連線至特定衛星地理位置。</span><span class="sxs-lookup"><span data-stu-id="430bf-201">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="430bf-202">在 Exchange Online PowerShell 中，執行下列命令，將用來執行信箱移轉的內部部署系統管理員認證儲存在變數中：</span><span class="sxs-lookup"><span data-stu-id="430bf-202">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="430bf-203">在 Exchange Online PowerShell 中，建立新的 **New-MoveRequest**，類似以下範例：</span><span class="sxs-lookup"><span data-stu-id="430bf-203">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="430bf-204">針對您要從內部部署 Exchange 移轉至您目前連線的衛星地理位置的每一個信箱重複步驟 4。</span><span class="sxs-lookup"><span data-stu-id="430bf-204">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="430bf-205">如果您需要將其他信箱移轉到其他衛星地理位置，請對每個特定衛星地理位置重複步驟 2 到 4。</span><span class="sxs-lookup"><span data-stu-id="430bf-205">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="430bf-206">多地理位置報告</span><span class="sxs-lookup"><span data-stu-id="430bf-206">Multi-geo reporting</span></span>

<span data-ttu-id="430bf-207">Microsoft 365 系統管理中心的 **多地理位置使用報告** 會依地理位置顯示使用者計數。</span><span class="sxs-lookup"><span data-stu-id="430bf-207">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="430bf-208">該報告會顯示目前月份的使用者分佈，並提供過去 6 個月的歷史資料。</span><span class="sxs-lookup"><span data-stu-id="430bf-208">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="430bf-209">另請參閱</span><span class="sxs-lookup"><span data-stu-id="430bf-209">See also</span></span>

[<span data-ttu-id="430bf-210">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="430bf-210">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
