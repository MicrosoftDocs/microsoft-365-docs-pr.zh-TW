---
title: 使用 OneDrive Learning 工具互通性
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 建立及評分工作分派、組建及 curate 課程內容，並使用新的 OneDrive Learning 工具互通性應用程式即時共同作業。
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256937"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="885a0-103">在畫布上使用 Microsoft OneDrive LTI</span><span class="sxs-lookup"><span data-stu-id="885a0-103">Use Microsoft OneDrive LTI with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="885a0-104">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="885a0-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="885a0-105">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="885a0-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="integrate-with-canvas"></a><span data-ttu-id="885a0-106">與畫布整合</span><span class="sxs-lookup"><span data-stu-id="885a0-106">Integrate with Canvas</span></span>

<span data-ttu-id="885a0-107">執行這項整合的人員應該是畫布的系統管理員，以及 Microsoft 365 租使用者的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="885a0-107">The person who performs this integration should be an admin of Canvas and an admin of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="885a0-108">使用租使用者系統管理員帳戶登入 Microsoft Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="885a0-108">Sign in to the Microsoft Azure portal with the tenant admin account.</span></span> <span data-ttu-id="885a0-109">Azure 租使用者管理員也應具有「群組管理員」角色。</span><span class="sxs-lookup"><span data-stu-id="885a0-109">The Azure tenant administrator should also have the Group administrator role.</span></span>

    ![群組管理員高亮顯示](../media/lti-media/lti-group-admin.png)

2. <span data-ttu-id="885a0-111">登入 Microsoft [OneDrive LTI 入口網站](https://odltiappnl.azurewebsites.net/admin)。</span><span class="sxs-lookup"><span data-stu-id="885a0-111">Sign in to the Microsoft [OneDrive LTI portal](https://odltiappnl.azurewebsites.net/admin).</span></span>

3. <span data-ttu-id="885a0-112">接受完成登入的許可權。</span><span class="sxs-lookup"><span data-stu-id="885a0-112">Accept the permissions to complete the sign-in.</span></span>

    ![接受許可權](../media/lti-media/lti-permissions.png)

4. <span data-ttu-id="885a0-114">選取 [ **新增 LTI 租** 使用者]。</span><span class="sxs-lookup"><span data-stu-id="885a0-114">Select **Add LTI Tenant**.</span></span>

     ![新增 LTI 租使用者](../media/lti-media/lti-add-tenant.png)

5. <span data-ttu-id="885a0-116">從下拉式清單中選取 [ **LTI 消費者平臺** ] 做為 **畫布** 。</span><span class="sxs-lookup"><span data-stu-id="885a0-116">Select **LTI Consumer Platform** as **Canvas** from the dropdown.</span></span>

6. <span data-ttu-id="885a0-117">選取 [ **畫布基本 URL** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="885a0-117">Select **Canvas Base URL** and then select **Next**.</span></span>

    ![選取 [畫布] 和 [新增基礎 URL]](../media/lti-media/lti-canvas-base-url.png)

   <span data-ttu-id="885a0-119">下一個畫面會顯示您的機密欄位。</span><span class="sxs-lookup"><span data-stu-id="885a0-119">The next screen shows fields that are confidential to you.</span></span>

7. <span data-ttu-id="885a0-120">從 **[開始] 中選取 [下一步]**</span><span class="sxs-lookup"><span data-stu-id="885a0-120">Select **Next** from ??</span></span> <span data-ttu-id="885a0-121">網頁。</span><span class="sxs-lookup"><span data-stu-id="885a0-121">page.</span></span> <span data-ttu-id="885a0-122">檢閱者是否可以在這裡填入空白？</span><span class="sxs-lookup"><span data-stu-id="885a0-122">CAN REVIEWERS FILL IN THE BLANK HERE?</span></span>

8. <span data-ttu-id="885a0-123">在畫面中選取 **[下一步]** ，顯示您的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="885a0-123">Select **Next** in the screen that shows information that's confidential to you.</span></span>

   <span data-ttu-id="885a0-124">Azure 入口網站的最後一個畫面會顯示新增畫布實例的後續步驟。</span><span class="sxs-lookup"><span data-stu-id="885a0-124">The final screen of the Azure portal shows the next steps for adding your Canvas instance.</span></span>

9. <span data-ttu-id="885a0-125">從此畫面複製開發人員機碼。</span><span class="sxs-lookup"><span data-stu-id="885a0-125">Copy the Developer Keys from this screen.</span></span> <span data-ttu-id="885a0-126">當您建立畫布實例時，您將會使用。</span><span class="sxs-lookup"><span data-stu-id="885a0-126">You'll use when you create the Canvas instance.</span></span>

## <a name="add-the-canvas-instance"></a><span data-ttu-id="885a0-127">新增畫布實例</span><span class="sxs-lookup"><span data-stu-id="885a0-127">Add the Canvas instance</span></span>

1. <span data-ttu-id="885a0-128">在您的畫布實例中，取消選取 [**管理**  >  **開發人員金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="885a0-128">In your Canvas instance, deselect **Admin** > **Developer Keys**.</span></span>

2. <span data-ttu-id="885a0-129">在 [**開發人員**] 機碼的下拉式清單中選擇 **LTI 機碼**。</span><span class="sxs-lookup"><span data-stu-id="885a0-129">Choose **LTI Key** in the dropdown on **Developer Key**.</span></span>

   ![取得 LTI 開發人員金鑰](../media/lti-media/lti-developer-keys.png)

3. <span data-ttu-id="885a0-131">在這裡貼上開發人員機碼。</span><span class="sxs-lookup"><span data-stu-id="885a0-131">Paste the developer keys here.</span></span>

     ![貼上開發人員機碼](../media/lti-media/lti-developer-keys.png)

   <span data-ttu-id="885a0-133">索引鍵是以 **關閉** 模式建立</span><span class="sxs-lookup"><span data-stu-id="885a0-133">The key gets created in **OFF** mode</span></span>

   ![在關閉模式中建立的開發人員機碼](../media/lti-media/lti-copy-developer-keys.png)

4. <span data-ttu-id="885a0-135">複製反白顯示的文字。</span><span class="sxs-lookup"><span data-stu-id="885a0-135">Copy the highlighted text.</span></span>
    <span data-ttu-id="885a0-136">這在 Microsoft OneDrive LTI 入口網站中充當用戶端識別碼。</span><span class="sxs-lookup"><span data-stu-id="885a0-136">This serves as Client ID in Microsoft OneDrive LTI portal.</span></span>

5. <span data-ttu-id="885a0-137">將文字貼 Microsoft OneDrive LTI 入口網站的 [**用戶端識別碼**] 欄位中，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="885a0-137">Paste the text into the **Client ID** field in Microsoft OneDrive LTI portal, and then select **Next**.</span></span>

6. <span data-ttu-id="885a0-138">選取 \*\*\*\*[儲存]。</span><span class="sxs-lookup"><span data-stu-id="885a0-138">Select **Save**.</span></span>

7. <span data-ttu-id="885a0-139">選取 [ **VIEW LTI 承租人**] 以查看設定。</span><span class="sxs-lookup"><span data-stu-id="885a0-139">View the settings by selecting **View LTI Tenants**.</span></span>
