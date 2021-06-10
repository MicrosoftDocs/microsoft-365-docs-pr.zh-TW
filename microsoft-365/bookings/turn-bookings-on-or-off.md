---
title: 開啟或關閉 Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: 瞭解如何在 Microsoft 365 中取得 Microsoft 預約的存取權。
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913763"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="a4a90-103">開啟或關閉 Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="a4a90-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="a4a90-104">您的整個組織或特定使用者可以開啟或關閉預約。</span><span class="sxs-lookup"><span data-stu-id="a4a90-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="a4a90-105">當您為使用者開啟預約時，他們可以建立預約頁面、建立行事曆，以及允許其他人與他們一起預約時間。</span><span class="sxs-lookup"><span data-stu-id="a4a90-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="a4a90-106">這些區段中所述的系統管理控制措施不適用於由世紀 (中國) 客戶運作的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a4a90-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="a4a90-107">使用 Microsoft 365 系統管理中心為您的組織開啟或關閉預定功能</span><span class="sxs-lookup"><span data-stu-id="a4a90-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a4a90-108">以全域系統管理員身分登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="a4a90-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="a4a90-109">在系統管理中心中，移至  **設定**   \> **Org 設定** 並選取 [**預定**]。</span><span class="sxs-lookup"><span data-stu-id="a4a90-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="a4a90-110">選取 [ **允許貴組織使用預定** 為您的組織啟用或停用預定] 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a4a90-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a4a90-111">關閉預約功能會停用對該服務的所有存取，包括建立及管理預定頁面。</span><span class="sxs-lookup"><span data-stu-id="a4a90-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="a4a90-112">選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="a4a90-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="a4a90-113">使用 PowerShell 為您的組織開啟或關閉預定功能</span><span class="sxs-lookup"><span data-stu-id="a4a90-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="a4a90-114">若要使用 PowerShell Cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)為您的組織開啟或關閉預約，請[連線 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a4a90-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="a4a90-115">為個別使用者開啟或關閉預約功能</span><span class="sxs-lookup"><span data-stu-id="a4a90-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="a4a90-116">您可以為個別使用者停用預定。</span><span class="sxs-lookup"><span data-stu-id="a4a90-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="a4a90-117">移至 Microsoft 365 系統管理中心，然後選取 [**使用者**] [作用中 \> **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="a4a90-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="a4a90-118">選取所需的使用者，然後選取 [ **授權和應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="a4a90-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="a4a90-119">展開 [ **應用程式** ]，然後清除 [Microsoft 預約] 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a4a90-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="a4a90-120">在共用空閒/忙碌資訊之前需要人員核准</span><span class="sxs-lookup"><span data-stu-id="a4a90-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="a4a90-121">系統管理員可以在其可用性資訊透過預約共用之前，讓組織中的員工進入自願加入，然後才能透過預約頁面進行 bookable。</span><span class="sxs-lookup"><span data-stu-id="a4a90-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="a4a90-122">在 [設定預約]**設定** 下的 Microsoft 365 系統管理中心中，可以使用此設定 \>  \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a4a90-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="a4a90-123">啟用此設定時，在預約行事曆中新增為職員的員工，會在收到的電子郵件通知中找到核准/拒絕連結。</span><span class="sxs-lookup"><span data-stu-id="a4a90-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="a4a90-124">這項功能會逐漸向全球範圍推廣 Microsoft 365 的客戶。</span><span class="sxs-lookup"><span data-stu-id="a4a90-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="a4a90-125">如果您在 Microsoft 365 系統管理中心中未看到此選項，請稍後再回來查看。</span><span class="sxs-lookup"><span data-stu-id="a4a90-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="a4a90-126">封鎖社交共用選項</span><span class="sxs-lookup"><span data-stu-id="a4a90-126">Block social sharing options</span></span>

<span data-ttu-id="a4a90-127">系統管理員可以控制在社交網路上共用預約頁面的方式。</span><span class="sxs-lookup"><span data-stu-id="a4a90-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="a4a90-128">在 [設定預約]**設定** 下的 Microsoft 365 系統管理中心中，可以使用此設定 \>  \> \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a4a90-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="a4a90-129">這項功能會逐漸向全球範圍推廣 Microsoft 365 的客戶。</span><span class="sxs-lookup"><span data-stu-id="a4a90-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="a4a90-130">如果您在 Microsoft 365 系統管理中心中未看到此選項，請稍後再回來查看。</span><span class="sxs-lookup"><span data-stu-id="a4a90-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="a4a90-131">只允許選取的使用者建立預定行事曆</span><span class="sxs-lookup"><span data-stu-id="a4a90-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="a4a90-132">透過使用原則限制，您可以限制已授權的使用者無法建立預定的行事曆。</span><span class="sxs-lookup"><span data-stu-id="a4a90-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="a4a90-133">您必須先為整個組織啟用預定。</span><span class="sxs-lookup"><span data-stu-id="a4a90-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="a4a90-134">您組織中的所有使用者都具有預約授權，但只有納入原則的使用者可以建立預約行事曆，而且可以完全控制誰可以存取他們所建立的行事曆。</span><span class="sxs-lookup"><span data-stu-id="a4a90-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="a4a90-135">包含在此原則中的使用者可以建立新的預約行事曆，也可以新增為任何產能的人員， (包括「系統管理員」角色) 現有的預約行事曆。</span><span class="sxs-lookup"><span data-stu-id="a4a90-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="a4a90-136">未包含在此原則中的使用者將無法建立新的預約行事曆，如果他們嘗試這麼做，將會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a4a90-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="a4a90-137">您必須使用 Exchange Online PowerShell 執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="a4a90-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="a4a90-138">如需執行 Exchange Online Cmdlet 的詳細資訊，請參閱[連線 to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a4a90-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4a90-139">下列步驟會假設您的組織中未建立任何其他 Outlook Web App (OWA) 信箱原則。</span><span class="sxs-lookup"><span data-stu-id="a4a90-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="a4a90-140">為應該允許建立預約行事曆的使用者建立新的信箱原則。</span><span class="sxs-lookup"><span data-stu-id="a4a90-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="a4a90-141">預設會使用新的信箱原則， (預定的行事曆建立。 ) </span><span class="sxs-lookup"><span data-stu-id="a4a90-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="a4a90-142">如需詳細資訊，請參閱 [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a4a90-142">For more information, see [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="a4a90-143">針對您想要授與建立預約行事曆許可權的每個使用者執行此命令，將此原則指派給相關的使用者。</span><span class="sxs-lookup"><span data-stu-id="a4a90-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="a4a90-144">如需詳細資訊，請參閱 [Set-CASMailbox](/powershell/module/exchange/set-casmailbox)。</span><span class="sxs-lookup"><span data-stu-id="a4a90-144">For more information, see [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="a4a90-145">選用：如果您想要對組織中的其他所有使用者停用預定，請執行此命令。</span><span class="sxs-lookup"><span data-stu-id="a4a90-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="a4a90-146">如需詳細資訊，請參閱＜[Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)＞。</span><span class="sxs-lookup"><span data-stu-id="a4a90-146">For more information, see [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="a4a90-147">如需 OWA 信箱原則的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="a4a90-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="a4a90-148">在 Exchange Online 中建立 Outlook 網頁版信箱原則</span><span class="sxs-lookup"><span data-stu-id="a4a90-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="a4a90-149">在 Exchange Online 中的信箱上套用或移除網頁信箱原則上的 Outlook</span><span class="sxs-lookup"><span data-stu-id="a4a90-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)