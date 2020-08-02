---
title: '設定內容瞭解（預覽） '
description: 如何設定專案 Cortex。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: fca80e45dfa45ee5da9521854c6eebfbd87d8859
ms.sourcegitcommit: 91c82a79962387205c4dd4dd8d61322b79fed55f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2020
ms.locfileid: "46539900"
---
# <a name="set-up-content-understanding-preview"></a>設定內容瞭解（預覽）

> [!Note] 
> 本文內容適用于 Project Cortex 私人預覽。 [進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。

系統管理員可以使用 Microsoft 365 系統管理中心來設定和設定內容瞭解。 

設定之前，請務必規劃如何在環境中設定和設定內容瞭解的最佳方式。 例如，您將需要考慮下列事項：
- 您將在哪些 SharePoint 網站上啟用表單處理？ 所有的網站、部分或選取的網站？
- 內容中心的名稱，以及主要網站管理員的名稱。

系統管理員也可以在安裝程式完成之後，透過 Microsoft 365 系統管理中心的內容瞭解管理設定，對選取的設定進行變更。


## <a name="requirements"></a>需求 
您必須具有全域管理員或 SharePoint 系統管理員許可權，才能存取 Microsoft 365 系統管理中心和設定內容瞭解。


## <a name="to-set-up-content-understanding"></a>設定內容瞭解

1. 在 Microsoft 365 系統管理中心中，選取 [**安裝**]，然後查看 [**組織知識**] 區段。
2. 在 [**組織知識**] 區段中，選取 [**自動瞭解內容**]。<br/>

    ![組織知識設定頁面](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. 在 [**自動化內容瞭解**] 頁面上，按一下 [**快速入門**] 以逐步引導您完成安裝程式。<br/>

    ![開始安裝程式](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. 在 [**設定表單處理**] 頁面上，您可以選擇是否要讓使用者能夠使用 AI 建立器在特定 SharePoint 文件庫中建立表單處理模型。 [文件庫] 功能區中會提供功能表選項，以在啟用該模型的 SharePoint 文件庫中**建立表單處理模型**。
 
     **若要 SharePoint 文件庫應該顯示以建立表單處理模型的選項**，您可以選取：</br>
    - **所有 SharePoint 文件庫**，使其可供您租使用者中的所有 SharePoint 庫使用。</br>
    - **僅限選取的網站中**的文件庫，然後選取您要讓其可供使用的網站。</br>
    - 如果您目前不想要讓任何網站使用，則**無 SharePoint 庫**（您可以在安裝之後加以變更）。
</br>

   ![設定表單處理](../media/content-understanding/admin-configforms.png)
</br>

   > [!Note]
   > 在 SharePoint 文件庫上啟用此設定不會影響已套用至文件庫的現有模型，也不會影響將檔理解模型套用至文件庫的功能。 

    
5. 在 [**建立內容中心**] 頁面上，您可以建立 SharePoint 內容中心網站，您的使用者可以在該網站上建立及管理檔理解模型。 </br>
    a. 在 [**網站名稱**] 中，輸入您要提供給內容中心網站的名稱。</br>
    b. **網站位址**會根據您為網站名稱所選取的內容，顯示網站的 URL。</br>

    > [!Note] 
    > 您可以選擇任何支援的語言，請注意，僅能為英文建立內容瞭解模型。</br>

      ![建立內容中心](../media/content-understanding/admin-cu-create-cc.png)</br>


    選取 [下一步]****。
6. 在 [**完成與複查]** 頁面上，您可以查看選取的設定，並選擇進行變更。 如果您對選擇滿意，請選取 [**啟動**]。



7. 隨即會顯示 [**內容瞭解**已啟動] 頁面，確認系統已新增您的表單處理喜好設定，以及建立內容中心網站。 選取 **[完成]**。

8. 您將會傳回 [**自動化內容瞭解**] 頁面。 您可以從這個頁面，選取 [**管理**]，對您的設定設定進行任何變更。 

## <a name="see-also"></a>另請參閱



  






