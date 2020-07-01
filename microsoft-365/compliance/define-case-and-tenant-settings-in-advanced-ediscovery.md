---
title: 在高級電子檔探索中定義案例與租使用者設定
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 383809de-7f5e-4a1d-9098-c525f67b7a9a
description: 深入瞭解您可以在高級 eDiscovery 的案例層級定義的標籤、跨模組和租使用者設定。
ms.openlocfilehash: 6b0030e30e5e3a4f4c77fbcb5fcbd75bf63c1ea8
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936420"
---
# <a name="define-case-and-tenant-settings-in-advanced-ediscovery-classic"></a>在高級 eDiscovery （古典）中定義案例與租使用者設定

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
本主題將說明「高級 eDiscovery 案例」和「租使用者」設定。
  
## <a name="case-settings"></a>案例設定

此節說明可在案例層級定義的設定。
  
> [!NOTE]
> 如果目前未選取 [高級 eDiscovery] 中的任何事例，則 [**案例設定**] 索引標籤為非作用中。 
  
### <a name="cross-module"></a>跨模組

下列跨模組設定是套用至高級 eDiscovery 模組的案例選項。
  
- 登入後的預設頁面：設定啟動「高級 eDiscovery」時所顯示的預設頁面。
    
- 檔案顯示名稱：會顯示在整個高級 eDiscovery 中以識別檔案的檔案識別碼，也就是檔標題/路徑或電子郵件主旨的高級電子檔顯示名稱的替代方式。
    
1. 按一下**Cogwheel**圖示，開啟 [**設定] 和 [公用程式**]。 開啟**設定和公用程式 \> Case 設定**] 索引標籤 \> **跨模組**。 
    
2. 在 **[登入選項之後從預設頁面**中選取： 
    
  - **先前登入的最後一頁**
    
  - **案例頁面**
    
3. 按一下 **[儲存]**。
    
## <a name="tenant-settings"></a>租用戶設定

本節將說明高級 eDiscovery 租使用者設定。
  
### <a name="user-administration"></a>使用者系統管理

在[設定使用者和案例](set-up-users-and-cases-in-advanced-ediscovery.md)時，會說明使用者管理選項。
  
### <a name="event-log"></a>事件記錄檔

事件記錄會在高級 eDiscovery 作業期間提供有關高級 eDiscovery 處理的中繼資料。 例如，它包含主要的高級 eDiscovery 程式（匯入、分析、相關性及匯出）的開始時間，以及結束時間和狀態。 此記錄可用於追蹤及疑難排解資料處理活動，以及用於處理錯誤和警告。
  
1. 按一下**Cogwheel**圖示，開啟 [**設定] 和 [公用程式**]。 
    
2. 在 [**設定與公用程式 \> 租使用者設定**] 索引標籤中，選取 [**事件記錄**]。 隨即會顯示事件記錄檔資料。
    
  - 若要以案例篩選記錄輸出，請從 [**案例**] 清單中選取案例。 
    
  - 若要依列排序記錄檔，請按一下欄標題。 
    
  - 若要修改欄順序，請按一下並拖曳欄標題。
    
  - 若要在記錄頁面之間移動，請按一下 [ **\>** 與 **\<** 圖示]。 
    
### <a name="system-information"></a>系統資訊

[租使用者設定] 索引標籤會顯示高級 eDiscovery 版本系統資訊和作用中的工作。
  
1. 按一下**Cogwheel**圖示，開啟 [**設定] 和 [公用程式**]。 
    
2. 在 [**設定與公用程式 \> 租使用者設定**] 索引標籤中，選取 [**系統資訊**]。 隨即會顯示版本資訊。
    
您可以按一下承租人資訊下方的 [重新整理]**圖示，以**更新顯示。 
  
## <a name="see-also"></a>請參閱

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[使用公用程式](use-advanced-ediscovery-utilities.md)

