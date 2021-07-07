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
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>將 Microsoft OneDrive LTI 與畫布整合

將 Microsoft OneDrive LTI 與畫布整合是兩個步驟的處理常式。 第一個步驟會在畫布中啟用 Microsoft OneDrive，第二個步驟會讓 Microsoft OneDrive LTI 可在畫布課程內使用。

## <a name="recommended-browser-settings"></a>建議的瀏覽器設定

- 應該為 Microsoft OneDrive 啟用 Cookies。
- Microsoft OneDrive 不應該封鎖快顯視窗。

> [!NOTE]
> - 在 Chrome 瀏覽器 incognito 模式中，預設不會啟用 cookie，因此必須啟用。
> - Microsoft OneDriveLTI 在 Microsoft Edge 瀏覽器的私人模式中運作。 確定您沒有封鎖 cookie (預設會啟用) 。

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>在畫布中啟用 Microsoft OneDrive LTI

> [!IMPORTANT]
> 執行這項整合的人員應該是畫布的管理員和 Microsoft 365 租使用者的管理員。

1. 登入<a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI 註冊入口網站</a>
1. 選取 [ **管理員同意** ] 按鈕，並接受許可權。

> [!CAUTION]
> 若未執行此步驟，下列步驟將會產生錯誤，而且在您取得錯誤之後，您將無法採取此步驟一小時。

3. 選取 [ **建立新的 LTI 租** 使用者] 按鈕。 在 [LTI 登錄] 頁面上的下拉式清單中選取 [ **畫布** ]，然後輸入您的畫布實例的基底 URL。

> [!NOTE]
> 例如，如果您的畫布實例為 https://contoso.test.instructure.com (， https://contoso.test.instructure.com) 則應輸入完整的 URL。

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="「LTI 租使用者管理」頁面，包含用於選擇 LTI 消費者平臺及 URL 文字欄位的下拉式清單欄位。":::

4. 若要複製 JSON，請選取 [ **複製** ] 按鈕， (右邊的圖示會顯示兩個頁面上，另一個) 上。 這將用來在畫布中產生金鑰。

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="顯示 [複製] 按鈕的圖像，此按鈕會複製顯示的 JSON 文字，並使其可用於畫布中的金鑰產生。":::

5. 以系統管理員身分登入您的畫布實例，然後從頁面左側的功能表中選取 [ **開發人員金鑰** ]。 從下拉式清單中，從頁面右上角的下拉式機碼中選擇 **LTI** 機碼，以建立開發人員機碼。

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="螢幕擷取畫面顯示的左側導覽列與選取的開發人員機碼，以及從頁面右邊的下拉式清單中選取的 LTI 金鑰專案。":::

6. 在 [設定] 頁面上，選取 [ **方法** ] 下拉式清單中的 [ **貼上 json** ] 做為方法，並貼上您在步驟5中複製的 JSON 文字。
7. 儲存機碼，它會在 [ **關閉** ] 狀態的畫布中提供。 在下一個步驟 **中，開啟機碼並複製** [ **詳細資料** ] 欄中所提供的索引鍵。

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="具有停用狀態之按鍵設定的畫布頁面。必須將其開啟，而且必須從此頁面上的 [詳細資料] 欄複製機碼。":::

8. 回到 Microsoft OneDrive LTI 註冊入口網站，然後在 [ **Canvas 用戶端識別碼**] 欄位中貼上金鑰。 當您準備好時，請選取 **[下一步]** 。

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="「LTI 租使用者登錄」頁面，它會顯示 JSON 文字和文字方塊應該複製到的文字方塊。":::

9. 檢查並儲存您的變更。 在成功註冊時，會顯示一則訊息。
10. 您也可以透過選取首頁上的「 **查看 LTI** 租使用者」按鈕，檢查您的註冊詳細資料。

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>在畫布課程中啟用 Microsoft OneDrive LTI

畫布管理員可以為所有課程啟用 Microsoft OneDrive LTI。 如果特定課程需要 Microsoft OneDrive LTI (而且並非所有課程都) ，則課程教師必須遵循課程設定中的相同步驟。

1. 以系統管理員身分登入，然後移至 [**設定**] 區段。
2. 移至 [ **應用** 程式] 區段，然後選取 [ **查看應用程式佈建** ] 按鈕。
3. 選取 [ **新增應用程式** ] 按鈕。
4. 在 [設定 **類型** ] 下拉式清單中，選擇 [ **依據用戶端識別碼** ] 選項。
5. 在 [ **用戶端識別碼** ] 欄位中貼上先前產生的開發人員機碼的值，然後選取 [ **提交** ] 按鈕。

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="[新增應用程式] 頁面，顯示 [設定類型] 下拉式功能表底下的 [依用戶端識別碼] 選項。":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>在畫布課程中 Microsoft OneDrive LTI 的共同作業設定

> [!NOTE]
> 針對教育版和學生的共同作業，您不應啟用 [共同作業] 設定。 若要確定設定未啟用，請遵循下列步驟。

1. 以系統管理員身分登入，然後移至 [**設定**] 區段。
1. 移至 [ **功能選項** ] 區段，然後移至 **課程** 區段。
1. 將 [ **外部協作工具** ] 功能設定為 [未啟用]。

> [!NOTE]
> 共同作業可指派給個別的學生和學生群組。 指派給個別的學生預設會運作。 若要能夠指派共同作業給一組學生，請遵循下列步驟：

1. 以系統管理員身分登入，然後移至 [ **開發人員金鑰** ] 區段。
1. 尋找值為170000000000710的機碼，並將它設為 [ **開啟**]。
