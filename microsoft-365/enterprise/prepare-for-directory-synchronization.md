---
title: 準備將目錄同步處理至 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 說明如何準備使用目錄同步處理將使用者布建至 Microsoft 365，以及使用此方法的長期優點。
ms.openlocfilehash: 1fe99247a5c50c7bb8fc7eb1347ce6a4cd6aad94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927321"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="4be28-103">準備將目錄同步處理至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4be28-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="4be28-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="4be28-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4be28-105">組織的混合式身分識別與目錄同步處理帶來的好處包括：</span><span class="sxs-lookup"><span data-stu-id="4be28-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="4be28-106">減少組織中的系統管理程式</span><span class="sxs-lookup"><span data-stu-id="4be28-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="4be28-107">選擇性啟用單一登入案例</span><span class="sxs-lookup"><span data-stu-id="4be28-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="4be28-108">自動化 Microsoft 365 中的帳戶變更</span><span class="sxs-lookup"><span data-stu-id="4be28-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="4be28-109">如需使用目錄同步處理之優點的詳細資訊，請參閱 [混合身分識別搭配 Azure Active directory (AZURE AD) ](/azure/active-directory/hybrid/whatis-hybrid-identity) 和 [Microsoft 365 的混合身分識別](plan-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="4be28-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="4be28-110">不過，目錄同步處理需要規劃及準備，以確保您的 Active Directory 網域服務 (AD DS) 同步處理至您的 Microsoft 365 訂閱的 Azure AD 租使用者，但錯誤最低。</span><span class="sxs-lookup"><span data-stu-id="4be28-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="4be28-111">請遵循下列步驟，以取得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="4be28-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="4be28-112">1. 目錄清理任務</span><span class="sxs-lookup"><span data-stu-id="4be28-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="4be28-113">將 AD DS 同步處理到 Azure AD 租使用者之前，您需要清理您的 AD DS。</span><span class="sxs-lookup"><span data-stu-id="4be28-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4be28-114">若您在同步處理之前未執行 AD DS 清除，則可能會對部署程式造成嚴重的負面影響。</span><span class="sxs-lookup"><span data-stu-id="4be28-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="4be28-115">可能需要數天甚至數周才能完成目錄同步處理的週期、識別錯誤，以及重新同步處理。</span><span class="sxs-lookup"><span data-stu-id="4be28-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="4be28-116">在您的 AD DS 中，針對每個將指派 Microsoft 365 授權的使用者帳戶，完成下列清理工作：</span><span class="sxs-lookup"><span data-stu-id="4be28-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="4be28-117">請確定 **proxyAddresses** 屬性中有有效且唯一的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4be28-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="4be28-118">移除 **proxyAddresses** 屬性中的任何重複值。</span><span class="sxs-lookup"><span data-stu-id="4be28-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="4be28-119">如果可能的話，請確認使用者 **使用者** 物件中 **userPrincipalName** 屬性的有效且唯一的值。</span><span class="sxs-lookup"><span data-stu-id="4be28-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="4be28-120">為了獲得最佳同步處理體驗，請確定 AD DS UPN 符合 Azure AD UPN。</span><span class="sxs-lookup"><span data-stu-id="4be28-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="4be28-121">如果使用者沒有 **userPrincipalName** 屬性的值，則 **user** 物件必須包含 **sAMAccountName** 屬性的有效且唯一的值。</span><span class="sxs-lookup"><span data-stu-id="4be28-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="4be28-122">移除 **userPrincipalName** 屬性中的任何重複值。</span><span class="sxs-lookup"><span data-stu-id="4be28-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="4be28-123">為 (GAL) 的全域通訊清單的最佳使用，請確定 AD DS 使用者帳戶的下列屬性資訊正確：</span><span class="sxs-lookup"><span data-stu-id="4be28-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="4be28-124">givenName</span><span class="sxs-lookup"><span data-stu-id="4be28-124">givenName</span></span>
   - <span data-ttu-id="4be28-125">姓</span><span class="sxs-lookup"><span data-stu-id="4be28-125">surname</span></span>
   - <span data-ttu-id="4be28-126">displayName</span><span class="sxs-lookup"><span data-stu-id="4be28-126">displayName</span></span>
   - <span data-ttu-id="4be28-127">職稱</span><span class="sxs-lookup"><span data-stu-id="4be28-127">Job Title</span></span>
   - <span data-ttu-id="4be28-128">部門</span><span class="sxs-lookup"><span data-stu-id="4be28-128">Department</span></span>
   - <span data-ttu-id="4be28-129">辦公室</span><span class="sxs-lookup"><span data-stu-id="4be28-129">Office</span></span>
   - <span data-ttu-id="4be28-130">辦公室電話</span><span class="sxs-lookup"><span data-stu-id="4be28-130">Office Phone</span></span>
   - <span data-ttu-id="4be28-131">行動電話</span><span class="sxs-lookup"><span data-stu-id="4be28-131">Mobile Phone</span></span>
   - <span data-ttu-id="4be28-132">傳真號碼</span><span class="sxs-lookup"><span data-stu-id="4be28-132">Fax Number</span></span>
   - <span data-ttu-id="4be28-133">街道地址</span><span class="sxs-lookup"><span data-stu-id="4be28-133">Street Address</span></span>
   - <span data-ttu-id="4be28-134">城市</span><span class="sxs-lookup"><span data-stu-id="4be28-134">City</span></span>
   - <span data-ttu-id="4be28-135">州/省</span><span class="sxs-lookup"><span data-stu-id="4be28-135">State or Province</span></span>
   - <span data-ttu-id="4be28-136">郵遞區號</span><span class="sxs-lookup"><span data-stu-id="4be28-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="4be28-137">國家或地區</span><span class="sxs-lookup"><span data-stu-id="4be28-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="4be28-138">2. 目錄物件和屬性準備</span><span class="sxs-lookup"><span data-stu-id="4be28-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="4be28-139">在您的 AD DS 和 Microsoft 365 間成功的目錄同步處理，需要您的 AD DS 屬性已正確準備。</span><span class="sxs-lookup"><span data-stu-id="4be28-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="4be28-140">例如，您必須確定特定的字元沒有用於與 Microsoft 365 環境同步處理的某些屬性。</span><span class="sxs-lookup"><span data-stu-id="4be28-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="4be28-141">非預期的字元不會造成目錄同步處理失敗，但可能會傳回警告。</span><span class="sxs-lookup"><span data-stu-id="4be28-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="4be28-142">不正確字元會導致目錄同步處理失敗。</span><span class="sxs-lookup"><span data-stu-id="4be28-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="4be28-143">如果某些 AD DS 使用者有一個或多個重複的屬性，目錄同步處理也會失敗。</span><span class="sxs-lookup"><span data-stu-id="4be28-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="4be28-144">每個使用者都必須有唯一的屬性。</span><span class="sxs-lookup"><span data-stu-id="4be28-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="4be28-145">您需要準備的屬性如下所列：</span><span class="sxs-lookup"><span data-stu-id="4be28-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="4be28-146">**#a1**</span><span class="sxs-lookup"><span data-stu-id="4be28-146">**displayName**</span></span>

  - <span data-ttu-id="4be28-147">如果屬性存在於使用者物件中，則會與 Microsoft 365 同步處理。</span><span class="sxs-lookup"><span data-stu-id="4be28-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="4be28-148">如果此屬性存在於使用者物件中，則必須有一個值。</span><span class="sxs-lookup"><span data-stu-id="4be28-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="4be28-149">也就是說，屬性必須不是空白的。</span><span class="sxs-lookup"><span data-stu-id="4be28-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="4be28-150">字元數上限：256</span><span class="sxs-lookup"><span data-stu-id="4be28-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="4be28-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="4be28-151">**givenName**</span></span>

  - <span data-ttu-id="4be28-152">如果屬性存在於使用者物件中，則會與 Microsoft 365 同步處理，但是 Microsoft 365 不需要或使用它。</span><span class="sxs-lookup"><span data-stu-id="4be28-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="4be28-153">字元數上限：64</span><span class="sxs-lookup"><span data-stu-id="4be28-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="4be28-154">**mail**</span><span class="sxs-lookup"><span data-stu-id="4be28-154">**mail**</span></span>

  - <span data-ttu-id="4be28-155">屬性值在目錄中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4be28-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4be28-156">如果有重複的值，則會同步處理第一個具有值的使用者。</span><span class="sxs-lookup"><span data-stu-id="4be28-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="4be28-157">後續的使用者將不會出現在 Microsoft 365 中。</span><span class="sxs-lookup"><span data-stu-id="4be28-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="4be28-158">您必須修改 Microsoft 365 中的值，或修改 AD DS 中的兩個值，這兩個使用者才能出現在 Microsoft 365 中。</span><span class="sxs-lookup"><span data-stu-id="4be28-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="4be28-159">**mailNickname** (Exchange 別名) </span><span class="sxs-lookup"><span data-stu-id="4be28-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="4be28-160">屬性值不得以句點 ( 開頭。 ) 。</span><span class="sxs-lookup"><span data-stu-id="4be28-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="4be28-161">屬性值在目錄中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4be28-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4be28-162">在同步處理名稱中 ( "_" ) 會指出此屬性的原始值包含不正確字元。</span><span class="sxs-lookup"><span data-stu-id="4be28-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="4be28-163">如需此屬性的詳細資訊，請參閱 [Exchange alias 屬性](/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="4be28-163">For more information on this attribute, see [Exchange alias attribute](/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="4be28-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="4be28-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="4be28-165">多重值屬性</span><span class="sxs-lookup"><span data-stu-id="4be28-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="4be28-166">每個值的字元數上限：256</span><span class="sxs-lookup"><span data-stu-id="4be28-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="4be28-167">屬性值不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="4be28-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="4be28-168">屬性值在目錄中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4be28-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="4be28-169">無效字元： \< \> ( ) ;，[] "'</span><span class="sxs-lookup"><span data-stu-id="4be28-169">Invalid characters: \< \> ( ) ; , [ ] " '</span></span>

    <span data-ttu-id="4be28-170">請注意，不正確字元會套用到類型分隔符號後的字元和 "："，因此允許 SMTP:User@contso.com，但 SMTP:user:M@contoso.com 不是。</span><span class="sxs-lookup"><span data-stu-id="4be28-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4be28-171">所有的簡易郵件傳輸通訊協定 (SMTP) 位址應該符合電子郵件訊息標準。</span><span class="sxs-lookup"><span data-stu-id="4be28-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="4be28-172">移除重複或有害的位址（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="4be28-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="4be28-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="4be28-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="4be28-174">字元數上限：20</span><span class="sxs-lookup"><span data-stu-id="4be28-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="4be28-175">屬性值在目錄中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4be28-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="4be28-176">無效字元： [\ "|，/： \< \> + =;？</span><span class="sxs-lookup"><span data-stu-id="4be28-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="4be28-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="4be28-177">\* ']</span></span>
  - <span data-ttu-id="4be28-178">如果使用者的 **sAMAccountName** 屬性無效，但是具有有效的 **userPrincipalName** 屬性，則會在 Microsoft 365 中建立使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4be28-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="4be28-179">如果 **sAMAccountName** 和 **userPrincipalName** 都無效，則必須更新 AD DS **userPrincipalName** 屬性。</span><span class="sxs-lookup"><span data-stu-id="4be28-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="4be28-180">**sn** (姓) </span><span class="sxs-lookup"><span data-stu-id="4be28-180">**sn** (surname)</span></span>

  - <span data-ttu-id="4be28-181">如果屬性存在於使用者物件中，則會與 Microsoft 365 同步處理，但是 Microsoft 365 不需要或使用它。</span><span class="sxs-lookup"><span data-stu-id="4be28-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="4be28-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="4be28-182">**targetAddress**</span></span>

    <span data-ttu-id="4be28-183">需要 **targetAddress** 屬性 (例如，為使用者填入的 SMTP:tom@contoso.com) 必須出現在 MICROSOFT 365 GAL 中。</span><span class="sxs-lookup"><span data-stu-id="4be28-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="4be28-184">在協力廠商郵件遷移案例中，這需要 AD DS 的 Microsoft 365 架構擴充。</span><span class="sxs-lookup"><span data-stu-id="4be28-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="4be28-185">Microsoft 365 架構擴充也會新增其他有用的屬性，以管理從 AD DS 使用目錄同步處理工具填入的 Microsoft 365 物件。</span><span class="sxs-lookup"><span data-stu-id="4be28-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="4be28-186">例如，將會新增用以管理隱藏信箱或通訊群組的 **msExchHideFromAddressLists** 屬性。</span><span class="sxs-lookup"><span data-stu-id="4be28-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="4be28-187">字元數上限：256</span><span class="sxs-lookup"><span data-stu-id="4be28-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="4be28-188">屬性值不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="4be28-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="4be28-189">屬性值在目錄中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4be28-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="4be28-190">無效字元： \ \< \> ( ) ;，[] "</span><span class="sxs-lookup"><span data-stu-id="4be28-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="4be28-191">所有的簡易郵件傳輸通訊協定 (SMTP) 位址應該符合電子郵件訊息標準。</span><span class="sxs-lookup"><span data-stu-id="4be28-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="4be28-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="4be28-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="4be28-193">**UserPrincipalName** 屬性必須是網際網路樣式的登入格式，其中使用者名稱後面接 @ 符號 ( @ ) 和功能變數名稱：例如，user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="4be28-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="4be28-194">所有的簡易郵件傳輸通訊協定 (SMTP) 位址應該符合電子郵件訊息標準。</span><span class="sxs-lookup"><span data-stu-id="4be28-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="4be28-195">**UserPrincipalName** 屬性的字元數上限為113。</span><span class="sxs-lookup"><span data-stu-id="4be28-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="4be28-196">在 sign ( @ ) 之前和之後均可使用特定的字元數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4be28-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="4be28-197">在 sign ( @ ) 前面的使用者名稱字元數上限：64</span><span class="sxs-lookup"><span data-stu-id="4be28-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="4be28-198">At 符號 ( @ ) 所遵循的功能變數名稱字元數上限：48</span><span class="sxs-lookup"><span data-stu-id="4be28-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="4be28-199">無效字元： \% &amp; \* +/=？</span><span class="sxs-lookup"><span data-stu-id="4be28-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="4be28-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="4be28-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="4be28-201">允許的字元： A–Z，a-z，0–9，'。</span><span class="sxs-lookup"><span data-stu-id="4be28-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="4be28-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="4be28-202">- _ !</span></span> <span data-ttu-id="4be28-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="4be28-203"># ^ ~</span></span>
  - <span data-ttu-id="4be28-204">具有變音符的字母（例如，母音或重音）和否定符號，都是不正確字元。</span><span class="sxs-lookup"><span data-stu-id="4be28-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="4be28-205">每個 **userPrincipalName** 值都需要 @ 字元。</span><span class="sxs-lookup"><span data-stu-id="4be28-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="4be28-206">每個 **userPrincipalName** 值中不能是 @ 字元的第一個字元。</span><span class="sxs-lookup"><span data-stu-id="4be28-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="4be28-207">使用者名稱不得以句點 ( ) 、& 符號 (&amp;) 、空格或 at 符號 ( @ ) 。</span><span class="sxs-lookup"><span data-stu-id="4be28-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="4be28-208">使用者名稱不得包含任何空格。</span><span class="sxs-lookup"><span data-stu-id="4be28-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="4be28-209">必須使用可路由的網域;例如，不能使用本機或內部網域。</span><span class="sxs-lookup"><span data-stu-id="4be28-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="4be28-210">Unicode 會轉換成底線字元。</span><span class="sxs-lookup"><span data-stu-id="4be28-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="4be28-211">**userPrincipalName** 不能包含目錄中的任何重複值。</span><span class="sxs-lookup"><span data-stu-id="4be28-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="4be28-212">3. 準備 userPrincipalName 屬性</span><span class="sxs-lookup"><span data-stu-id="4be28-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="4be28-213">Active Directory 的設計目的是讓您組織中的使用者可以使用 **sAMAccountName** 或 **userPrincipalName** 登入您的目錄。</span><span class="sxs-lookup"><span data-stu-id="4be28-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="4be28-214">同樣地，使用者可以使用使用者主要名稱 (其工作或學校帳戶的 UPN) 登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4be28-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="4be28-215">目錄同步處理嘗試使用 AD DS 中的同一個 UPN，在 Azure Active Directory 中建立新的使用者。</span><span class="sxs-lookup"><span data-stu-id="4be28-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="4be28-216">UPN 的格式就像電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4be28-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="4be28-217">在 Microsoft 365 中，UPN 是用來產生電子郵件地址的預設屬性。</span><span class="sxs-lookup"><span data-stu-id="4be28-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="4be28-218">在 AD DS 和 Azure AD) 中取得 **userPrincipalName** (很容易，將 **proxyAddresses** 中的主要電子郵件地址設定為不同的值。</span><span class="sxs-lookup"><span data-stu-id="4be28-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="4be28-219">當其設定為不同值時，系統管理員和使用者可能會混淆。</span><span class="sxs-lookup"><span data-stu-id="4be28-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="4be28-220">最好對齊這些屬性，以降低混淆。</span><span class="sxs-lookup"><span data-stu-id="4be28-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="4be28-221">為了符合使用 Active Directory Federation Services (AD FS) 2.0 的單一登入需求，您必須確定 Azure Active Directory 和您的 AD DS 中的 Upn 相符，且使用有效的網域命名空間。</span><span class="sxs-lookup"><span data-stu-id="4be28-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="4be28-222">4. 將替代的 UPN 尾碼新增至 AD DS</span><span class="sxs-lookup"><span data-stu-id="4be28-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="4be28-223">您可能需要新增其他 UPN 尾碼，以將使用者的公司認證與 Microsoft 365 環境產生關聯。</span><span class="sxs-lookup"><span data-stu-id="4be28-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="4be28-224">UPN 尾碼是 @ 字元右側的 UPN 部分。</span><span class="sxs-lookup"><span data-stu-id="4be28-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="4be28-225">用於單一登入的 UPN 可包含字母、數字、句號、虛線和底線，但不得包含其他字元類型。</span><span class="sxs-lookup"><span data-stu-id="4be28-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="4be28-226">如需如何將其他 UPN 尾碼新增至 Active Directory 的詳細資訊，請參閱 [Prepare for 目錄同步]( https://go.microsoft.com/fwlink/p/?LinkId=525430)處理。</span><span class="sxs-lookup"><span data-stu-id="4be28-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="4be28-227">5. 搭配使用 Microsoft 365 UPN 的 AD DS UPN</span><span class="sxs-lookup"><span data-stu-id="4be28-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="4be28-228">如果您已設定目錄同步處理，則 Microsoft 365 的使用者 UPN 可能不會符合您在 AD DS 中定義的使用者 AD DS UPN。</span><span class="sxs-lookup"><span data-stu-id="4be28-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="4be28-229">若使用者在網域經過驗證之前即獲得指派授權，就可能發生這種情形。</span><span class="sxs-lookup"><span data-stu-id="4be28-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="4be28-230">若要修正此問題，請使用 [PowerShell 修正重複的 upn](https://go.microsoft.com/fwlink/p/?LinkId=396730) 以更新使用者的 upn，以確保 MICROSOFT 365 UPN 符合公司使用者名稱和網域。</span><span class="sxs-lookup"><span data-stu-id="4be28-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="4be28-231">若要在 AD DS 中更新 UPN，並想要與 Azure Active Directory 身分識別同步，您必須先在 Microsoft 365 中移除使用者的授權，然後才能在 AD DS 中進行變更。</span><span class="sxs-lookup"><span data-stu-id="4be28-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="4be28-232">另請參閱 how [to prepare a 不可路由的網域 (例如，directory 同步處理的 local domain) ](prepare-a-non-routable-domain-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="4be28-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4be28-233">後續步驟</span><span class="sxs-lookup"><span data-stu-id="4be28-233">Next steps</span></span>

<span data-ttu-id="4be28-234">如果您已完成上述步驟1到5，請參閱 [設定目錄同步](set-up-directory-synchronization.md)處理。</span><span class="sxs-lookup"><span data-stu-id="4be28-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>