---
title: 使用 Office 365 中免費的 Azure Active Directory 訂閱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: 了解如何存取 Azure Active Directory，其隨附於貴組織的 Office 365 的付費訂閱。
ms.openlocfilehash: fe3829d349e5721ebdcf0688c1f5b2bd3c9f7f45
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604090"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a><span data-ttu-id="37292-103">使用 Office 365 中免費的 Azure Active Directory 訂閱</span><span class="sxs-lookup"><span data-stu-id="37292-103">Use your free Azure Active Directory subscription in Office 365</span></span>

<span data-ttu-id="37292-p101">如果貴組織有 Office 365、Microsoft Dynamics CRM Online、Enterprise Mobility Suite 或其他 Microsoft 服務的付費訂閱，則您有 Microsoft Azure Active Directory 的免費訂閱。您和其他系統管理員可以使用 Azure AD，來建立並管理使用者和群組帳戶。若要使用 Azure AD，只需移至 Azure 入口網站，並使用您的 Office 365 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="37292-p101">If your organization has a paid subscription to Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Microsoft Azure Active Directory. You and other admins can use Azure AD to create and manage user and group accounts. To use Azure AD, just go to the Azure portal and sign in using your Office 365 account.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="37292-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="37292-107">Before you begin</span></span>

<span data-ttu-id="37292-p102">使用私人瀏覽工作階段 (不是一般工作階段) 來存取 Azure 入口網站 (下面步驟 1)，因為這會防止您目前登入所用的認證傳遞至 Azure。若要在 Microsoft Edge、Internet Explorer 或 Mozilla FireFox 中開啟 InPrivate 瀏覽工作階段，只需按 CTRL+SHIFT+P。若要在 Google Chrome (稱為無痕視窗) 中開啟私人瀏覽工作階段，請按 CTRL+SHIFT+N。</span><span class="sxs-lookup"><span data-stu-id="37292-p102">Use a private browsing session (not a regular session) to access the Azure portal (in step 1 below) because this will prevent the credential that you are currently logged on with from being passed to Azure. To open an InPrivate Browsing session in Microsoft Edge, Internet Explorer, or Mozilla FireFox, just press CTRL+SHIFT+P. To open a private browsing session in Google Chrome (called an incognito window), press CTRL+SHIFT+N.</span></span>

## <a name="access-azure-active-directory"></a><span data-ttu-id="37292-111">存取 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="37292-111">Access Azure Active Directory</span></span>

1. <span data-ttu-id="37292-112">移至 [portal.azure.com](https://portal.azure.com)，並使用您的 Office 365 工作或學生帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="37292-112">Go to [portal.azure.com](https://portal.azure.com) and sign in with your Office 365 work or student account.</span></span>

2. <span data-ttu-id="37292-113">在 Azure 入口網站的左導覽窗格中，按一下 [Azure Active Directory]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="37292-113">In the left navigation pane in the Azure portal, click **Azure Active Directory**.</span></span>

    ![按一下 Azure 入口網站左導覽窗格中的 Azure Active Directory。](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    <span data-ttu-id="37292-115">即會顯示 [Azure Active Directory]\*\*\*\* 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="37292-115">The **Azure Active Directory** admin center is displayed.</span></span>

## <a name="more-information"></a><span data-ttu-id="37292-116">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="37292-116">More information</span></span>

- <span data-ttu-id="37292-117">免費的 Azure Active Directory 訂用帳戶不包含登入活動報告。</span><span class="sxs-lookup"><span data-stu-id="37292-117">A free Azure Active Directory subscription does not include the Sign-ins activity report.</span></span> <span data-ttu-id="37292-118">若要記錄登入活動 (發生資料外洩時相當實用)，您必須擁有 Azure Active Directory Premium 訂用帳戶。</span><span class="sxs-lookup"><span data-stu-id="37292-118">To record sign-in activity (which can be useful in the event of a data breach), you need an Azure Active Directory Premium subscription.</span></span> <span data-ttu-id="37292-119">如需詳細資訊，請參閱 [Azure AD 會將資料儲存多久？](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).</span><span class="sxs-lookup"><span data-stu-id="37292-119">For more information, see [How long does Azure AD store the data?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).</span></span>

- <span data-ttu-id="37292-120">您也可以從 Microsoft 365 系統管理中心存取 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="37292-120">You can also access the **Azure Active Directory** admin center from the Microsoft 365 admin center.</span></span> <span data-ttu-id="37292-121">在 Microsoft 365 系統管理中心左側瀏覽窗格，按一下 [系統管理中心]\*\*\*\* \> [Azure Active Directory]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="37292-121">In the left navigation pane of the Microsoft 365 admin center, click **Admin centers** \> **Azure Active Directory**.</span></span>

- <span data-ttu-id="37292-122">如需管理使用者和群組以及執行其他目錄管理工作的詳細資訊，請參閱[管理 Azure AD 目錄](https://docs.microsoft.com/azure/active-directory/active-directory-administer)。</span><span class="sxs-lookup"><span data-stu-id="37292-122">For information about managing users and groups and performing other directory management tasks, see [Manage your Azure AD directory](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span></span>
