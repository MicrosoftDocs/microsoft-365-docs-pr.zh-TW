---
title: 設定 SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 設定專案 Cortex 中的內容瞭解
ms.openlocfilehash: f0a26f0044e578928730cf4930f1524e86dff9f3
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294840"
---
# <a name="set-up-sharepoint-syntex"></a>設定 SharePoint Syntex

系統管理員可以使用 Microsoft 365 系統管理中心來設定和 Microsoft SharePoint Syntex。 

開始之前，請考慮下列事項：

- 您將在哪些 SharePoint 網站上啟用表單處理？ 所有的網站、部分或選取的網站？
- 您的內容中心及主要網站管理員的名稱為何？

您可以在 Microsoft 365 系統管理中心中的初始設定之後變更您的設定。

本文內容適用于 Project Cortex 私人預覽。 [進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。

設定之前，請務必規劃如何在環境中設定和設定內容瞭解的最佳方式。 例如，您需要考慮下列名稱：

- 您想要啟用表單處理的 SharePoint 網站-所有的網站、部分或選取的網站
- 內容中心及主要網站管理員的名稱

## <a name="requirements"></a>需求 

> [!NOTE]
> 您必須具有全域管理員或 SharePoint 系統管理員許可權，才能存取 Microsoft 365 系統管理中心和設定內容瞭解。

身為系統管理員，您也可以在安裝程式完成之後，在 [Microsoft 365 系統管理中心] 的 [內容瞭解管理] 設定中隨時變更選取的設定。

## <a name="to-set-up-sharepoint-syntex"></a>若要設定 SharePoint Syntex

1. 在 Microsoft 365 系統管理中心中，選取 [ **安裝**]，然後查看 [ **組織知識** ] 區段。

2. 在 [ **組織知識** ] 區段中，選取 [ **自動瞭解內容**]。<br/>

    ![組織知識設定頁面](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. 在 [ **自動化 SharePoint Syntex** ] 頁面上，按一下 [ **開始** 使用] 以逐步執行安裝程式。<br/>

    ![開始安裝程式](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. 在 [開啟圖像標記] 頁面上，選擇是否要允許 [影像標記](image-tagging.md)。

    ![影像標記選項的螢幕擷取畫面](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. 在 [ **設定表單處理** ] 頁面上，您可以選擇是否要讓使用者能夠使用 AI 建立器在特定 SharePoint 文件庫中建立表單處理模型。 [文件庫] 功能區中會提供功能表選項，以在啟用該模型的 SharePoint 文件庫中 **建立表單處理模型** 。
 
     **若要 SharePoint 文件庫應該顯示以建立表單處理模型的選項**，您可以選取：</br>
      - **所有 SharePoint 文件庫** ，讓組織中的所有 SharePoint 文件庫皆可使用。</br>
      - **僅限選取的網站中**的文件庫，然後選取您要讓其可供使用的網站。</br>

   ![設定表單處理](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > 在 SharePoint 文件庫上啟用此設定不會影響已套用至文件庫的現有模型，也不會影響將檔理解模型套用至文件庫的功能。 
    
6. 在 [ **建立內容中心** ] 頁面上，您可以建立 SharePoint 內容中心網站，您的使用者可以在該網站上建立及管理檔理解模型。 </br>
    a. 在 [ **網站名稱**] 中，輸入您要提供給內容中心網站的名稱。</br>
    b. **網站位址**會根據您為網站名稱所選取的內容，顯示網站的 URL。 若要變更，請按一下 [ **編輯**]。</br>

      ![建立內容中心](../media/content-understanding/admin-cu-create-cc.png)</br>

    選取 [下一步]****。

7. 在 [ **檢查和完成]** 頁面上，您可以查看選取的設定，並選擇進行變更。 如果您對選擇滿意，請選取 [ **啟動**]。

8. 在 [確認] 頁面上，按一下 [ **完成**]。

9. 您將會傳回 [ **自動化內容瞭解** ] 頁面。 您可以從這個頁面，選取 [ **管理** ]，對您的設定設定進行任何變更。 

## <a name="assign-licenses"></a>指派授權

在您設定 SharePoint Syntex 後，您必須指派授權給將要使用表單處理及檔理解功能的使用者。

若要指派授權：

1. 在 Microsoft 365 系統管理中心的 [ **使用者**] 下，按一下 [作用中 **使用者**]。

2. 選取您要授權的使用者，然後按一下 [ **管理產品授權**]。

3. 選取 [ **指派更多**]。

4. 選取 [ **智慧內容服務**]。 在 [**應用程式**] 底下，請確定已同時選取 [智慧內容服務] 及 [**智慧內容**服務]**的一般資料服務**。

    ![在 Microsoft 365 系統管理中心中 SharePoint Syntex 授權](../media/content-understanding/sharepoint-syntex-licenses.png)

5. 按一下 [儲存變更]****。

## <a name="ai-builder-credits"></a>AI 產生器學分

如果您的組織中有300或以上 SharePoint Syntex 授權 SharePoint Syntex，您將會被指派 1000000 AI 產生器信用。 如果您的授權少於300個，您必須購買 AI 產生器信用，才能使用表單處理。

您可以使用 Ai 產生器 [計算機](https://powerapps.microsoft.com/ai-builder-calculator)估計最適合您的 ai 產生器容量。

1. 請移至 [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com/resources/capacity) ，檢查您的學分和使用方式。

    > [!NOTE]
    > 在 SharePoint 文件庫上啟用此設定，不會影響已套用至程式庫的現有模型，也不會影響將檔理解模型套用至文件庫的功能。 
    
2. 在 [ **建立內容中心** ] 頁面中，您可以建立 SharePoint 內容中心網站，讓使用者可以建立及管理檔理解模型。 </br>
    a. 在 [ **網站名稱**] 中，輸入您要用於內容中心網站的名稱。</br>
    b. **網站位址**會根據網站名稱顯示網站的 URL。</br>

    > [!NOTE] 
    > 雖然您可以選擇任何支援的語言，但內容瞭解模型只能為英文建立。</br>

      ![建立內容中心](../media/content-understanding/admin-cu-create-cc.png)</br>

3. 選取 [下一步]****。

4. 在 [ **完成與複查]** 頁面上，查看您選取的設定，然後選擇進行變更。 如果您對選擇滿意，請選取 [ **啟動**]。

5. 隨即會顯示 [ **內容瞭解** 已啟動] 頁面，確認系統已新增您的表單處理喜好設定，並建立內容中心網站。 選取 **[完成]**。

6. 您將會傳回 [ **自動化內容瞭解** ] 頁面。 您可以從這個頁面，選取 [ **管理** ]，對您的設定設定進行任何變更。 

## <a name="see-also"></a>請參閱

[表單處理模型概述](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[逐步：如何建立檔理解模型 (影片) ](https://www.youtube.com/watch?v=DymSHObD-bg)

