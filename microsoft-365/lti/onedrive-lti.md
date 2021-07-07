---
title: 使用 Microsoft OneDrive Learning 工具互通性
ms.author: heidip
author: MicrosoftHeidi
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
description: 建立及評分工作分派、組建及 curate 課程內容，並使用新的 Microsoft OneDrive Learning 工具互通性應用程式即時共同作業。
ms.openlocfilehash: bcb374ed1666f23fa5f3d4692f43a4369670e891
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322218"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="e1674-103">將 Microsoft OneDrive LTI 與畫布整合</span><span class="sxs-lookup"><span data-stu-id="e1674-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="e1674-104">將 Microsoft OneDrive LTI 與畫布整合是兩個步驟的處理常式。</span><span class="sxs-lookup"><span data-stu-id="e1674-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="e1674-105">第一個步驟會在畫布中啟用 Microsoft OneDrive，第二個步驟會讓 Microsoft OneDrive LTI 可在畫布課程內使用。</span><span class="sxs-lookup"><span data-stu-id="e1674-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="e1674-106">建議的瀏覽器設定</span><span class="sxs-lookup"><span data-stu-id="e1674-106">Recommended browser settings</span></span>

- <span data-ttu-id="e1674-107">應該為 Microsoft OneDrive 啟用 Cookies。</span><span class="sxs-lookup"><span data-stu-id="e1674-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="e1674-108">Microsoft OneDrive 不應該封鎖快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="e1674-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="e1674-109">在 Chrome 瀏覽器 incognito 模式中，預設不會啟用 cookie，因此必須啟用。</span><span class="sxs-lookup"><span data-stu-id="e1674-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="e1674-110">Microsoft OneDriveLTI 在 Microsoft Edge 瀏覽器的私人模式中運作。</span><span class="sxs-lookup"><span data-stu-id="e1674-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="e1674-111">確定您沒有封鎖 cookie (預設會啟用) 。</span><span class="sxs-lookup"><span data-stu-id="e1674-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="e1674-112">在畫布中啟用 Microsoft OneDrive LTI</span><span class="sxs-lookup"><span data-stu-id="e1674-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1674-113">執行這項整合的人員應該是畫布的管理員和 Microsoft 365 租使用者的管理員。</span><span class="sxs-lookup"><span data-stu-id="e1674-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="e1674-114">登入<a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI 註冊入口網站</a></span><span class="sxs-lookup"><span data-stu-id="e1674-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="e1674-115">選取 [ **管理員同意** ] 按鈕，並接受許可權。</span><span class="sxs-lookup"><span data-stu-id="e1674-115">Select the **Admin Consent** button and accept the permissions.</span></span>

> [!CAUTION]
> <span data-ttu-id="e1674-116">若未執行此步驟，下列步驟將會產生錯誤，而且在您取得錯誤之後，您將無法採取此步驟一小時。</span><span class="sxs-lookup"><span data-stu-id="e1674-116">If this step isn't performed, the following step will give you an error, and you won't be able to take this step for an hour once you've gotten the error.</span></span>

3. <span data-ttu-id="e1674-117">選取 [ **建立新的 LTI 租** 使用者] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e1674-117">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="e1674-118">在 [LTI 登錄] 頁面上的下拉式清單中選取 [ **畫布** ]，然後輸入您的畫布實例的基底 URL。</span><span class="sxs-lookup"><span data-stu-id="e1674-118">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="e1674-119">例如，如果您的畫布實例為 https://contoso.test.instructure.com (， https://contoso.test.instructure.com) 則應輸入完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="e1674-119">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="「LTI 租使用者管理」頁面，包含用於選擇 LTI 消費者平臺及 URL 文字欄位的下拉式清單欄位。":::

4. <span data-ttu-id="e1674-121">若要複製 JSON，請選取 [ **複製** ] 按鈕， (右邊的圖示會顯示兩個頁面上，另一個) 上。</span><span class="sxs-lookup"><span data-stu-id="e1674-121">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="e1674-122">這將用來在畫布中產生金鑰。</span><span class="sxs-lookup"><span data-stu-id="e1674-122">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="顯示 [複製] 按鈕的圖像，此按鈕會複製顯示的 JSON 文字，並使其可用於畫布中的金鑰產生。":::

5. <span data-ttu-id="e1674-124">以系統管理員身分登入您的畫布實例，然後從頁面左側的功能表中選取 [ **開發人員金鑰** ]。</span><span class="sxs-lookup"><span data-stu-id="e1674-124">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="e1674-125">從下拉式清單中，從頁面右上角的下拉式機碼中選擇 **LTI** 機碼，以建立開發人員機碼。</span><span class="sxs-lookup"><span data-stu-id="e1674-125">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="螢幕擷取畫面顯示的左側導覽列與選取的開發人員機碼，以及從頁面右邊的下拉式清單中選取的 LTI 金鑰專案。":::

6. <span data-ttu-id="e1674-127">在 [設定] 頁面上，選取 [ **方法** ] 下拉式清單中的 [ **貼上 json** ] 做為方法，並貼上您在步驟5中複製的 JSON 文字。</span><span class="sxs-lookup"><span data-stu-id="e1674-127">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="e1674-128">儲存機碼，它會在 [ **關閉** ] 狀態的畫布中提供。</span><span class="sxs-lookup"><span data-stu-id="e1674-128">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="e1674-129">在下一個步驟 **中，開啟機碼並複製** [ **詳細資料** ] 欄中所提供的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e1674-129">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="具有停用狀態之按鍵設定的畫布頁面。必須將其開啟，而且必須從此頁面上的 [詳細資料] 欄複製機碼。":::

8. <span data-ttu-id="e1674-131">回到 Microsoft OneDrive LTI 註冊入口網站，然後在 [ **Canvas 用戶端識別碼**] 欄位中貼上金鑰。</span><span class="sxs-lookup"><span data-stu-id="e1674-131">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="e1674-132">當您準備好時，請選取 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="e1674-132">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="「LTI 租使用者登錄」頁面，它會顯示 JSON 文字和文字方塊應該複製到的文字方塊。":::

9. <span data-ttu-id="e1674-134">檢查並儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="e1674-134">Review and save your changes.</span></span> <span data-ttu-id="e1674-135">在成功註冊時，會顯示一則訊息。</span><span class="sxs-lookup"><span data-stu-id="e1674-135">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="e1674-136">您也可以透過選取首頁上的「 **查看 LTI** 租使用者」按鈕，檢查您的註冊詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e1674-136">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="e1674-137">在畫布課程中啟用 Microsoft OneDrive LTI</span><span class="sxs-lookup"><span data-stu-id="e1674-137">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="e1674-138">畫布管理員可以為所有課程啟用 Microsoft OneDrive LTI。</span><span class="sxs-lookup"><span data-stu-id="e1674-138">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="e1674-139">如果特定課程需要 Microsoft OneDrive LTI (而且並非所有課程都) ，則課程教師必須遵循課程設定中的相同步驟。</span><span class="sxs-lookup"><span data-stu-id="e1674-139">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="e1674-140">以系統管理員身分登入，然後移至 [**設定**] 區段。</span><span class="sxs-lookup"><span data-stu-id="e1674-140">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="e1674-141">移至 [ **應用** 程式] 區段，然後選取 [ **查看應用程式佈建** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e1674-141">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="e1674-142">選取 [ **新增應用程式** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e1674-142">Select the **Add App** button.</span></span>
4. <span data-ttu-id="e1674-143">在 [設定 **類型** ] 下拉式清單中，選擇 [ **依據用戶端識別碼** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="e1674-143">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="e1674-144">在 [ **用戶端識別碼** ] 欄位中貼上先前產生的開發人員機碼的值，然後選取 [ **提交** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e1674-144">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="[新增應用程式] 頁面，顯示 [設定類型] 下拉式功能表底下的 [依用戶端識別碼] 選項。":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="e1674-146">在畫布課程中 Microsoft OneDrive LTI 的共同作業設定</span><span class="sxs-lookup"><span data-stu-id="e1674-146">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="e1674-147">針對教育版和學生的共同作業，您不應啟用 [共同作業] 設定。</span><span class="sxs-lookup"><span data-stu-id="e1674-147">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="e1674-148">若要確定設定未啟用，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="e1674-148">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="e1674-149">以系統管理員身分登入，然後移至 [**設定**] 區段。</span><span class="sxs-lookup"><span data-stu-id="e1674-149">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="e1674-150">移至 [ **功能選項** ] 區段，然後移至 **課程** 區段。</span><span class="sxs-lookup"><span data-stu-id="e1674-150">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="e1674-151">將 [ **外部協作工具** ] 功能設定為 [未啟用]。</span><span class="sxs-lookup"><span data-stu-id="e1674-151">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="e1674-152">共同作業可指派給個別的學生和學生群組。</span><span class="sxs-lookup"><span data-stu-id="e1674-152">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="e1674-153">指派給個別的學生預設會運作。</span><span class="sxs-lookup"><span data-stu-id="e1674-153">Assigning to individual students works by default.</span></span> <span data-ttu-id="e1674-154">若要能夠指派共同作業給一組學生，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e1674-154">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="e1674-155">以系統管理員身分登入，然後移至 [ **開發人員金鑰** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="e1674-155">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="e1674-156">尋找值為170000000000710的機碼，並將它設為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="e1674-156">Find the key with value 170000000000710 and set it to **On**.</span></span>
