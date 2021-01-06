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
ms.openlocfilehash: d7fe410f114d43d4f6c983aaf23d949298635318
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760100"
---
# <a name="adjust-settings-after-enrollment"></a><span data-ttu-id="0f0b5-104">註冊之後調整設定</span><span class="sxs-lookup"><span data-stu-id="0f0b5-104">Adjust settings after enrollment</span></span>

<span data-ttu-id="0f0b5-105">在 Microsoft Managed Desktop 中完成註冊後，您必須調整某些 Microsoft Intune 和 Azure Active Directory (Azure AD) 設定，以允許管理及維護安全性。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-105">After you've completed enrollment in Microsoft Managed Desktop, you need to adjust certain Microsoft Intune and Azure Active Directory (Azure AD) settings to allow for management and maintain security.</span></span> <span data-ttu-id="0f0b5-106">設定下列設定，以排除包含 Microsoft 受管理桌面裝置和使用者的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-106">Set the following settings to exclude the Azure AD groups that contain Microsoft Managed Desktop devices and users.</span></span> <span data-ttu-id="0f0b5-107">如需排除群組的步驟，請參閱 [條件式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-107">For steps to exclude groups, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).</span></span>

> [!NOTE]
> <span data-ttu-id="0f0b5-108">如果您在註冊 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的原則之後進行任何變更，Microsoft 受管理的桌面可能會停止運作。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-108">If you make any changes after enrollment to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, it's possible that Microsoft Managed Desktop could stop operating properly.</span></span> <span data-ttu-id="0f0b5-109">若要避免 Microsoft 受管理桌面作業的問題，請在變更任何原則之前，先檢查 [準備工作評估工具所發現之修正問題](../get-ready/readiness-assessment-fix.md) 中所述的特定設定。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-109">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in [Fix issues found by the readiness assessment tool](../get-ready/readiness-assessment-fix.md) before you change any policies.</span></span>


## <a name="microsoft-intune-settings"></a><span data-ttu-id="0f0b5-110">Microsoft Intune 設定</span><span class="sxs-lookup"><span data-stu-id="0f0b5-110">Microsoft Intune settings</span></span>

- <span data-ttu-id="0f0b5-111">Autopilot 部署設定檔：排除 **新式的工作裝置-所有**  Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-111">Autopilot deployment profile: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="0f0b5-112">如需步驟，請參閱 [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-112">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span>
- <span data-ttu-id="0f0b5-113">條件式存取原則：排除 **新式的 Workplace Service 帳戶** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-113">Conditional Access policies: exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="0f0b5-114">如需步驟，請參閱 [條件式存取：使用者和群組](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-114">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>
- <span data-ttu-id="0f0b5-115">多重要素驗證：請確定任何需要多重要素驗證的條件式存取原則排除 **新式的 Workplace Service 帳戶** Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-115">Multifactor authentication: make sure any conditional access policies that require multifactor authentication exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="0f0b5-116">如需詳細資訊，請參閱 [條件式存取原則](../get-ready/readiness-assessment-fix.md#conditional-access-policies) 和 [條件式存取：針對所有使用者需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-116">For more information, see [Conditional access policies](../get-ready/readiness-assessment-fix.md#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>
- <span data-ttu-id="0f0b5-117">安全性基準：排除 **新式的工作區裝置-所有**  Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-117">Security baseline: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="0f0b5-118">如需步驟，請參閱 [使用安全性基準在 Intune 中設定 Windows 10 裝置](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-118">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>
- <span data-ttu-id="0f0b5-119">Windows 10 更新環：排除 **現代的工作場所裝置-所有**  Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-119">Windows 10 update ring: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="0f0b5-120">如需步驟，請參閱 [在 Intune 中管理 Windows 10 軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-120">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="0f0b5-121">Azure Active Directory 設定</span><span class="sxs-lookup"><span data-stu-id="0f0b5-121">Azure Active Directory settings</span></span>

<span data-ttu-id="0f0b5-122">自助密碼重設： **選擇 [選取** ] [設定]，然後選取 [ **新式工作區裝置]-[所有** Azure AD 群組]。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-122">Self-service password reset: choose **Selected** setting, and then select **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="0f0b5-123">如需詳細資訊，請參閱 [教學課程：讓使用者可以使用 Azure Active Directory 自助密碼重設來解除鎖定帳戶或重設密碼](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="0f0b5-123">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="0f0b5-124">開始使用 Microsoft 受管理電腦的步驟</span><span class="sxs-lookup"><span data-stu-id="0f0b5-124">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="0f0b5-125">在系統管理入口網站中新增和驗證系統管理員連絡人</span><span class="sxs-lookup"><span data-stu-id="0f0b5-125">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="0f0b5-126"> (本文登記後調整設定) </span><span class="sxs-lookup"><span data-stu-id="0f0b5-126">Adjust settings after enrollment (this article)</span></span>
3. [<span data-ttu-id="0f0b5-127">指派授權</span><span class="sxs-lookup"><span data-stu-id="0f0b5-127">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="0f0b5-128">部署 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="0f0b5-128">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="0f0b5-129">啟用企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="0f0b5-129">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="0f0b5-130">設定裝置</span><span class="sxs-lookup"><span data-stu-id="0f0b5-130">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="0f0b5-131">讓您的使用者準備好使用裝置</span><span class="sxs-lookup"><span data-stu-id="0f0b5-131">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="0f0b5-132">部署應用程式</span><span class="sxs-lookup"><span data-stu-id="0f0b5-132">Deploy apps</span></span>](deploy-apps.md)
