---
title: 註冊之後調整設定
description: 如何排除某些 Microsoft 帳戶
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 88a832f6c4e17756bfb25ef5cb7c4c5ecedaf2c0
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794385"
---
# <a name="adjust-settings-after-enrollment"></a><span data-ttu-id="7a4f9-104">註冊之後調整設定</span><span class="sxs-lookup"><span data-stu-id="7a4f9-104">Adjust settings after enrollment</span></span>

<span data-ttu-id="7a4f9-105">在 Microsoft Managed Desktop 中完成註冊後，可能需要調整某些管理設定。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-105">After you’ve completed enrollment in Microsoft Managed Desktop, some management settings might need to be adjusted.</span></span> <span data-ttu-id="7a4f9-106">若要在需要時檢查及調整，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7a4f9-106">To check and adjust if needed, follow these steps:</span></span>

1. <span data-ttu-id="7a4f9-107">查看下一節所述的 Microsoft Intune 和 Azure Active Directory 設定。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-107">Review the Microsoft Intune and Azure Active Directory settings described in the next section.</span></span>
2. <span data-ttu-id="7a4f9-108">如果有任何專案適用于您的環境，請進行所述的調整。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-108">If any of the items apply to your environment, make the adjustments described.</span></span>
3. <span data-ttu-id="7a4f9-109">如果您想要仔細檢查所有設定是否正確，您可以重新執行 [ [準備工作] 評估工具](https://aka.ms/mmdart) ，以確保與 Microsoft 管理的桌面沒有任何衝突。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-109">If you want to double-check that all settings are correct, you can rerun the [readiness assessment tool](https://aka.ms/mmdart) to make sure nothing conflicts with Microsoft Managed Desktop.</span></span>

> [!NOTE]
> <span data-ttu-id="7a4f9-110">當您在下列月份繼續作業時，如果您在登記至 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的原則之後變更 microsoft 受管理的電腦，Microsoft 受管理的桌面可能會停止運作。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-110">As your operations continue in following months, if you make changes after enrollment to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365 that affect Microsoft Managed Desktop, it's possible that Microsoft Managed Desktop could stop operating properly.</span></span> <span data-ttu-id="7a4f9-111">若要避免服務的問題，請在變更所列的原則之前，先檢查 [準備工作評估工具所發現之修正問題](../get-ready/readiness-assessment-fix.md) 中所述的特定設定。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-111">To avoid problems with the service, check the specific settings described in [Fix issues found by the readiness assessment tool](../get-ready/readiness-assessment-fix.md) before you change the policies listed there.</span></span> <span data-ttu-id="7a4f9-112">您也可以隨時重新執行準備工作評估工具。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-112">You can also rerun the readiness assessment tool at any time.</span></span>


## <a name="microsoft-intune-settings"></a><span data-ttu-id="7a4f9-113">Microsoft Intune 設定</span><span class="sxs-lookup"><span data-stu-id="7a4f9-113">Microsoft Intune settings</span></span>

- <span data-ttu-id="7a4f9-114">Autopilot 部署設定檔：如果您使用任何 Autopilot 原則，請將每個原則更新為排除 **現代的工作場所裝置-所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-114">Autopilot deployment profile: if you use any Autopilot policies, update each one to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="7a4f9-115">若要更新這些設定，請在 [**工作分派**] 底下的 [**排除的群組**] 區段中，選取 **新式的工作場所裝置-** 在 Microsoft 管理的桌上型電腦註冊期間建立的所有 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-115">To update them, in the **Excluded groups** section under **Assignments**, select the **Modern Workplace Devices -All** Azure AD group that was created during Microsoft Managed Desktop enrollment.</span></span> <span data-ttu-id="7a4f9-116">Microsoft 受管理的桌面也會建立 Autopilot 設定檔，在 **新式的 Workplace Autopilot 設定檔**) 中，它會有 "新式 workplace" (。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-116">Microsoft Managed Desktop will also have created an Autopilot profile, which will have "Modern Workplace" in the name (the **Modern Workplace Autopilot Profile**).</span></span> <span data-ttu-id="7a4f9-117">當您更新自己的 Autopilot 設定檔時，請確定您 *不會* 排除 **新式的工作區裝置-** 從 Microsoft Managed Desktop 所建立之 **新式 workplace Autopilot 設定檔** 中的所有 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-117">When you update your own Autopilot profiles, make sure that you *do not* exclude the **Modern Workplace Devices -All** Azure AD group from the **Modern Workplace Autopilot Profile** that was created by Microsoft Managed Desktop.</span></span>

- <span data-ttu-id="7a4f9-118">條件式存取原則：針對您已建立的條件式存取原則，請排除 **新式的 Workplace Service 帳戶** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-118">Conditional Access policies: for conditional access policies you've created, exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="7a4f9-119">如需步驟，請參閱 [條件式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-119">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span> <span data-ttu-id="7a4f9-120">Microsoft 受管理的桌面也會建立一些條件式存取原則，其中的名稱 (例如新式工作中的「現代辦公」，例如新式工作中的「 **安全工作站** 」) 。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-120">Microsoft Managed Desktop will also have created some conditional access policies, all of which will have "Modern Workplace" in the name (for example, **Modern Workplace Secure Workstation**).</span></span> <span data-ttu-id="7a4f9-121">當您更新您自己的條件式存取原則時，請確定 *不要* 排除 **現代的工作場所裝置-** 從 Microsoft Managed Desktop 建立的任何原則中的所有 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-121">When you update your own conditional access policies, make sure you *do not* exclude the **Modern Workplace Devices -All** Azure AD group from any policies created by Microsoft Managed Desktop.</span></span>

- <span data-ttu-id="7a4f9-122">多重要素驗證：請確定您需要多重因素驗證的任何條件式存取原則排除 **現代的 Workplace Service 帳戶** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-122">Multifactor authentication: make sure any of your conditional access policies that require multifactor authentication exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="7a4f9-123">如需詳細資訊，請參閱 [條件式存取原則](../get-ready/readiness-assessment-fix.md#conditional-access-policies) 和 [條件式存取：針對所有使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-123">For more information, see [Conditional access policies](../get-ready/readiness-assessment-fix.md#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

- <span data-ttu-id="7a4f9-124">Windows 10 更新環：針對您已建立的任何 Windows 10 更新鈴聲原則，從每個原則中排除 **所有** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-124">Windows 10 update ring: for any Windows 10 update ring policies you've created, exclude the **Modern Workplace Devices -All** Azure AD group from each policy.</span></span> <span data-ttu-id="7a4f9-125">如需步驟，請參閱 [建立和指派更新環](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings)。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-125">For steps, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings).</span></span> <span data-ttu-id="7a4f9-126">Microsoft 受管理的桌面也會建立一些更新環原則，所有的更新環原則，都是「新式工作」的名稱 (例如 **新式的工作區更新原則 [廣泛的]**、 **新式的工作區更新原則 [Fast]**、 **新式的工作區更新原則 [First]**，以及 **新式的工作區更新原則 [Test]**) 。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-126">Microsoft Managed Desktop will also have created some update ring policies, all of which will have "Modern Workplace" in the name (for example **Modern Workplace Update Policy [Broad]**, **Modern Workplace Update Policy [Fast]**, **Modern Workplace Update Policy [First]**, and **Modern Workplace Update Policy [Test]**).</span></span> <span data-ttu-id="7a4f9-127">當您更新您自己的原則時，請確定您 *未* 排除 **新式的工作場所裝置-所有** Azure AD 群組從 Microsoft 受管理的桌面所建立。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-127">When you update your own policies, make sure that you *do not* exclude the **Modern Workplace Devices -All** Azure AD group from those that Microsoft Managed Desktop created.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="7a4f9-128">Azure Active Directory 設定</span><span class="sxs-lookup"><span data-stu-id="7a4f9-128">Azure Active Directory settings</span></span>

<span data-ttu-id="7a4f9-129">自助密碼重設：如果您針對所有使用者使用自助密碼重設，請調整指派，以排除 Microsoft 受管理的桌面服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-129">Self-service password reset: if you use self-service password reset for all users, adjust the assignment to exclude Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="7a4f9-130">若要調整此指派，請為除了 Microsoft Managed Desktop service 帳戶 *以外* 的所有使用者建立 Azure AD 動態群組，然後將該群組用於工作分派，而不是「所有使用者」。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-130">To adjust this assignment, create a Azure AD dynamic group for all users *except* Microsoft Managed Desktop service accounts, and then use that group for assignment instead of "all users."</span></span>

<span data-ttu-id="7a4f9-131">為了協助您尋找及排除服務帳戶，以下是您可以使用的動態查詢範例：</span><span class="sxs-lookup"><span data-stu-id="7a4f9-131">To help you find and exclude the service accounts, here is an example of a dynamic query you can use:</span></span>

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

<span data-ttu-id="7a4f9-132">在此查詢中，以租使用者功能變數名稱取代 @TENANT。</span><span class="sxs-lookup"><span data-stu-id="7a4f9-132">In this query, replace @TENANT with your tenant domain name.</span></span>



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="7a4f9-133">開始使用 Microsoft 受管理電腦的步驟</span><span class="sxs-lookup"><span data-stu-id="7a4f9-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="7a4f9-134">在系統管理入口網站中新增和驗證系統管理員連絡人</span><span class="sxs-lookup"><span data-stu-id="7a4f9-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="7a4f9-135"> (本文登記後調整設定) </span><span class="sxs-lookup"><span data-stu-id="7a4f9-135">Adjust settings after enrollment (this article)</span></span>
3. [<span data-ttu-id="7a4f9-136">指派授權</span><span class="sxs-lookup"><span data-stu-id="7a4f9-136">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="7a4f9-137">部署 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="7a4f9-137">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="7a4f9-138">啟用企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="7a4f9-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="7a4f9-139">設定裝置</span><span class="sxs-lookup"><span data-stu-id="7a4f9-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="7a4f9-140">讓您的使用者準備好使用裝置</span><span class="sxs-lookup"><span data-stu-id="7a4f9-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="7a4f9-141">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="7a4f9-141">Deploy apps</span></span>](deploy-apps.md)
