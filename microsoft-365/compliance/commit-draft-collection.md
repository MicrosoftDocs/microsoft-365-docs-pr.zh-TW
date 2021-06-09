---
title: 草稿集合提交至檢閱集
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 建立並重複使用草擬集合之後，您可以將其認可為審閱集。 當您認可草稿集合時，所收集的專案會新增至此案例中的「審閱」集。 收集的專案在考核集中後，您就可以進行分析、檢查及匯出。
ms.openlocfilehash: e28592e7aac289bfc0cc29d312963fa21d9f8fd4
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838855"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery"></a>將草稿集合認可為 Advanced eDiscovery 中的審閱集

當您對您在草稿集合中收集並準備好進行分析、標記及檢查的專案滿意時，您可以在案例中新增集合至審閱集。 當您將草稿集合認可至審閱集時，收集的專案會從其原始內容位置複製到 Microsoft 365 的審閱集。 「審閱集」是 microsoft 雲端中，由 microsoft 提供的安全 Azure 儲存體位置。

## <a name="commit-a-draft-collection-to-a-review-set"></a>草稿集合提交至檢閱集

1. 在 Microsoft 365 規範中心] 中，開啟 Advanced eDiscovery 案例，然後選取 [**集合**] 索引標籤，以顯示案例的集合清單。

   ![案例中的集合清單](../media/CommitDraftCollections1.png)

   > [!TIP]
   > `Estimated`[**狀態**] 欄中的值會識別可以新增至審閱集的草稿集合。 「狀態」 `Committed` 表示集合已經新增至審閱集。

2. 在 [ **集合** ] 頁面上，選取您要認可為審閱集的草稿集合。

3. 在飛入頁面底部，選取 [**動作**  >  **編輯集合**]。

4. 在 [編輯集合] 嚮導中，按 **[下一步** ]，直到顯示 [ **儲存草稿] 或 [收集** ] 頁面。

5. 進行下列設定：

   1. 選取 [ **收集項目並新增至審閱集**]。

   2. 決定是否要將集合新增至新的審閱集 (此集合會在您提交集合) 或現有的審閱集之後建立。 請根據您的決定完成本節。

   3. 設定其他集合設定：

       - **Teams 和 Yammer 郵件**：選取此選項可將討論執行緒新增至集合，此集合包含集合中的搜尋查詢所傳回的聊天室專案。 這表示會重建包含符合搜尋準則之專案的交談交談。 這可讓您查看前後交談內容中的聊天室專案。 如需詳細資訊，請參閱[Advanced eDiscovery 中的交談執行緒](conversation-review-sets.md)。

       - **雲端附件**：選取此選項可在將集合結果新增至審閱集時包含新式附件或連結的檔案。 這表示新式附件或連結檔案的目標檔案會新增至審閱集。

       - **SharePoint 版本**：選取此選項可啟用集合中每個版本限制和搜尋參數的所有版本 SharePoint 檔的集合。 選取此選項會大幅增加新增至審閱集之專案的大小。

   4. 設定設定以定義要新增至審閱集的集合規模：

      - **新增所有集合結果**：選取此選項可將符合集合之搜尋準則的所有專案新增至審閱集。

      - **新增集合結果的範例**：選取此選項可將集合結果的範例新增至審閱集，而不是新增所有結果。 如果您選取此選項，請按一下 [ **編輯範例參數** ]，然後選擇下列其中一個選項：

         - **範例基礎**：將集合中的專案新增至審閱集會由您設定的統計參數所決定。 如果當採樣結果時，通常會使用信賴等級和間隔，請在下拉式方塊中指定這些結果。 否則，請使用預設設定。

         - **隨機範例**：集合中的專案會根據搜尋傳回之總專案數目的指定百分比之隨機選取，新增至審閱集。

6. 在 [ **檢查您的集合** ] 頁面上，您可以查看您在前一頁上設定的集合設定。 若要變更，請按一下 [ **編輯** ]。

7. 按一下 [ **提交** ] 以建立草稿收集。 隨即會顯示一個頁面，確認已建立集合。

## <a name="what-happens-after-you-commit-a-draft-collection"></a>在您認可草稿集合後會發生什麼事

當您將草稿集合認可至審閱集時，會發生下列情況：

- 會再次執行收藏搜尋查詢。 這表示複製到審閱集的實際搜尋結果可能會不同于上次執行集合搜尋時所傳回的估計結果。

- 搜尋結果中的所有專案都會從 live service 中的原始資料來源複製，然後複製至 Microsoft 雲端中的安全 Azure 儲存體位置。

- 所有專案 (包含不位於保管人或非保管人資料來源中的內容和中繼資料) ，會在稱為「 *深度索引*) 」的程式中重新編制索引 (，這樣就能在複查案例資料時完全搜尋評審集中的所有資料。 當您在案例調查期間搜尋或篩選考核集中的內容時，會在集合中的內容進行完整且快速的搜尋。

- 在將集合認可至審閱集時，會解密在搜尋結果中傳回的加密 SharePoint 和 OneDrive 檔與加密檔案。 您可以在複查集中複查及查詢解密的檔案。 如需詳細資訊，請參閱[Microsoft 365 eDiscovery tools 中的解密](ediscovery-decryption.md)。

- 光學字元辨識 (OCR) 功能會從影像析取文字，並包含具有新增至審閱集之內容的影像文字。 如需詳細資訊，請參閱本文中的 [光學字元辨識](#optical-character-recognition) 一節。

- 在成功完成認可之後，[ **集合** ] 索引標籤上的 [狀態] 欄的值會變更為 `Committed` 。

## <a name="optical-character-recognition"></a>光學字元辨識

當您將集合認可至審閱集時，會自動從影像提取文字的光字元識別 (OCR) Advanced eDiscovery 功能，並包含包含在審閱集新增內容的影像文字。 您可以在 [審閱] 集中的選取影像檔的文字檢視器中查看解壓縮的文字。 這可讓您對影像中的文字進行進一步的檢閱和分析。 OCR 支援用於鬆散檔案、電子郵件附件和內嵌影像。 如需 OCR 支援的影像檔格式清單，請參閱[進階電子文件探索中支援的檔案類型](supported-filetypes-ediscovery20.md#image)。

您必須針對在進階電子文件探索中建立的每個案例啟用 OCR 功能。 如需詳細資訊，請參閱 [設定搜尋及分析設定](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。
