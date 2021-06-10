---
title: 將使用者從 Office 365 安全性與合規性中心重新導向至 Microsoft 365 規範中心
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: 瞭解如何自動將 Office 365 安全性與合規性中心使用者重新導向至 Microsoft 365 規範中心」。
ms.collection: M365-security-compliance
ms.openlocfilehash: b51b2e225c833ac499379bbee119f8cb6f4216e9
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782834"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="a1ce9-103">將使用者從 Office 365 安全性與合規性中心重新導向至 Microsoft 365 規範中心</span><span class="sxs-lookup"><span data-stu-id="a1ce9-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="a1ce9-104">本文說明從 Office 365 安全性與合規性中心存取相容性解決方案的使用者，自動重新導向的運作方式 (protection.office.com) Microsoft 365 規範中心 (compliance.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="a1ce9-105">預期的專案</span><span class="sxs-lookup"><span data-stu-id="a1ce9-105">What to expect</span></span>

<span data-ttu-id="a1ce9-106">根據預設，在 Office 365 安全性和合規性 (protection.office.com) 中存取下列符合性相關解決方案的所有使用者，都會啟用自動重新導向：</span><span class="sxs-lookup"><span data-stu-id="a1ce9-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="a1ce9-107">資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="a1ce9-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="a1ce9-108">分類</span><span class="sxs-lookup"><span data-stu-id="a1ce9-108">Classification</span></span>
- <span data-ttu-id="a1ce9-109">資訊控管</span><span class="sxs-lookup"><span data-stu-id="a1ce9-109">Information governance</span></span>
- <span data-ttu-id="a1ce9-110">記錄管理</span><span class="sxs-lookup"><span data-stu-id="a1ce9-110">Records management</span></span>
- <span data-ttu-id="a1ce9-111">通訊合規性 (原來的「監督」 ) </span><span class="sxs-lookup"><span data-stu-id="a1ce9-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="a1ce9-112">使用者會在 Microsoft 365 規範中心內自動路由傳送至相同的相容性解決方案 (compliance.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

>[!NOTE]
><span data-ttu-id="a1ce9-113">針對 Office 365 安全性與合規性中心包含的其他規範解決方案，使用者會繼續在 Microsoft 365 規範中心或 Office 365 安全性與合規性中心管理這些解決方案。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="a1ce9-114">這些規範解決方案的自動重新導向功能即將推出。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-114">The automatic redirection for these compliance solutions will be available soon.\*</span></span>

<span data-ttu-id="a1ce9-115">這項功能和相關聯的控制項不會啟用 Microsoft Defender Office 365 的安全性功能的自動重新導向。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a1ce9-116">若要啟用安全功能的重新導向，請參閱[將帳戶從 Microsoft Defender 重新導向 Office 365 至 Microsoft 365 安全中心](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="a1ce9-117">可以回復使用先前的入口網站嗎？</span><span class="sxs-lookup"><span data-stu-id="a1ce9-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="a1ce9-118">如果有些專案無法運作，或是您沒有透過「Microsoft 365 規範中心入口網站」完成的任何專案，您可以暫時停用所有使用者的自動重新導向。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a1ce9-119">Microsoft 365 規範中心是目前在 Office 365 安全性與合規性中心中管理之規範解決方案的取代管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="a1ce9-120">所有的 Microsoft 365 規範解決方案都會以完全管理 Microsoft 365 規範中心。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a1ce9-121">停用 Microsoft 365 規範中心的重新導向應該是一項簡短的解決方案。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.\*</span></span>

<span data-ttu-id="a1ce9-122">若要切換回 Office 365 安全性與合規性中心 (所有使用者的 protection.microsoft.com) ，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a1ce9-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="a1ce9-123">以全域管理員身分登入[Microsoft 365 合規性中心](https://compliance.microsoft.com)，或在 Azure Active directory 中使用具有合規性系統管理員許可權的任何帳戶。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="a1ce9-124">流覽至 **設定**  >  **規範中心重新定向**。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="a1ce9-125">將自動重新導向設定切換為 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="a1ce9-126">選取 [ **關閉** 並在出現提示時共用意見反應]。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-126">Select **Turn off** and share feedback when prompted.</span></span>

<span data-ttu-id="a1ce9-127">一旦停用，使用者就不會再傳送至 compliance.microsoft.com，而且會將其導向至 Office 365 安全性與合規性中心 (protection.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="a1ce9-128">全域或合規性系統管理員可以隨時重新啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="a1ce9-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="a1ce9-129">相關資訊</span><span class="sxs-lookup"><span data-stu-id="a1ce9-129">Related information</span></span>

- [<span data-ttu-id="a1ce9-130">Microsoft 365 規範中心概述</span><span class="sxs-lookup"><span data-stu-id="a1ce9-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)
