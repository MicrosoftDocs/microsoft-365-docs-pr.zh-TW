---
title: 將應用程式固定至使用者的應用程式啟動器
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: 作為全域系統管理員，您最多可以將三個應用程式上插至使用者的應用程式啟動器。
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310872"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="7d53e-103">將應用程式固定至使用者的應用程式啟動器</span><span class="sxs-lookup"><span data-stu-id="7d53e-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="7d53e-104">您可以使用 Azure Active Directory 入口網站中的控制項，最多可為您組織中的所有使用者上插上三個應用程式，以 Office.com 及應用程式啟動器。</span><span class="sxs-lookup"><span data-stu-id="7d53e-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="7d53e-105">您也可以組織應用程式群組。</span><span class="sxs-lookup"><span data-stu-id="7d53e-105">You can also organize groups of applications.</span></span> <span data-ttu-id="7d53e-106">您新增的任何應用程式以後都可以由使用者取消固定。</span><span class="sxs-lookup"><span data-stu-id="7d53e-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="7d53e-107">若要為您的使用者固定應用程式，您必須是雲端應用程式管理員或 Azure Active Directory 中的應用程式管理員或 Office 365 中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="7d53e-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="7d53e-108">如需系統管理員角色的詳細資訊，請參閱在 Microsoft 365 中 [的 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 和系統 [管理角色](../add-users/about-admin-roles.md)中的系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="7d53e-108">For more information about admin roles, see [admin roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="7d53e-109">如需有關應用程式啟動器和 Office.com 的詳細資訊，請參閱 [符合應用程式啟動器](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) 和 [更新至 Office.com 和-Office 365 應用程式啟動器的](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) 博客文章。</span><span class="sxs-lookup"><span data-stu-id="7d53e-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="7d53e-110">使用 Azure Active Directory 入口網站來固定應用程式</span><span class="sxs-lookup"><span data-stu-id="7d53e-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="7d53e-111">移至 Microsoft 365 系統管理中心，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="7d53e-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="7d53e-112">在左側導覽中，選擇 [ **全部顯示**]，然後在 [系統 **管理中心**] 底下，選擇 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="7d53e-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="7d53e-113">在 [ **Azure Active Directory**] 中，選擇 [**企業應用程式**]  >  **使用者設定**。</span><span class="sxs-lookup"><span data-stu-id="7d53e-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="7d53e-114">在 [ **Office 365 設定** ] 區段中，選擇 [ **新增應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="7d53e-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="7d53e-115">選擇您要固定至使用者應用程式啟動器的應用程式，然後選擇 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="7d53e-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365 設定以固定應用程式。":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="7d53e-117">固定自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="7d53e-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="7d53e-118">使用者介面會指出是否需要購買其他 Azure AD 授權，才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="7d53e-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="7d53e-119">如需詳細資訊，請參閱 [Azure Active Directory 定價](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="7d53e-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="7d53e-120">在**Azure Active Directory**中，選擇 [所有應用程式] 頁面頂端的 [**企業應用程式**] [  >  **新增應用程式**]。 **All applications**</span><span class="sxs-lookup"><span data-stu-id="7d53e-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="7d53e-121">在 [ **新增應用程式** ] 頁面上，選擇 [ **非圖庫] 應用程式** ，如果您在 Azure Active Directory 的預覽版本中，請選擇 [ **建立您自己的應用程式** ]。</span><span class="sxs-lookup"><span data-stu-id="7d53e-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="7d53e-122">輸入應用程式的名稱，然後在 [ **使用者和群組** ] 索引標籤中指派使用者。</span><span class="sxs-lookup"><span data-stu-id="7d53e-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="7d53e-123">使用 [ **屬性** ] 索引標籤可上傳應用程式的圖示。</span><span class="sxs-lookup"><span data-stu-id="7d53e-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="7d53e-124">若要指派應用程式的 URL，請在 [ **單一登入** ] 索引標籤中，選擇 [ **連結** ]，然後輸入 url。</span><span class="sxs-lookup"><span data-stu-id="7d53e-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="7d53e-125">選擇 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7d53e-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="7d53e-126">建立應用程式集合</span><span class="sxs-lookup"><span data-stu-id="7d53e-126">Create application collections</span></span>

<span data-ttu-id="7d53e-127">您也可以為組織中的使用者建立應用程式集合。</span><span class="sxs-lookup"><span data-stu-id="7d53e-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="7d53e-128">如需相關指示，請參閱在 [Azure 入口網站中的我的應用程式入口網站上建立集合](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)。</span><span class="sxs-lookup"><span data-stu-id="7d53e-128">For instructions, see [create collections on the My Apps portal in the Azure portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span></span>