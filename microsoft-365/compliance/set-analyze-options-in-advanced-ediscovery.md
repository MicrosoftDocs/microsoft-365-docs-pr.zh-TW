---
title: 在高級電子檔探索中設定分析選項
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 請參閱在高級 eDiscovery 中設定分析程式選項的步驟，包括近乎重複的電子郵件線索和主題。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d622e06cdfe9a46f470be46d1a5b9df98347cc0a
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936880"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a>在高級 eDiscovery （古典）中設定分析選項

> [!NOTE]
> 進階電子文件探索需要具有進階合規性附加元件的 Office 365 E3，或適用於您組織的 E5 訂閱。如果您沒有該方案，且想要嘗試進階電子文件探索，您可以[註冊 Office 365 企業版 E5 試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在 [Advanced eDiscovery] 中，設定 [分析] 選項，再執行 [分析]。
  
## <a name="set-analyze-options"></a>設定分析選項

開啟**準備 \> 分析** \> **設定**。 隨即會顯示下列視窗。
  
![設定分析選項](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **近乎重複的電子郵件執行緒**如果您想要執行分析，請選取此方塊。 此為預設選取的選項。 
  
 **檔相似性**輸入接近重複的臨界值或接受預設值65%。 
  
 **主題**選取此方塊以處理所有檔案，並為其指定主題。 預設不會選取此核取方塊。 如果您想要執行主題處理，請輸入下列選項。
  
- **主題數目上限**輸入或選取要建立的主題數目值。 預設值為 200。 
    
    > [!NOTE]
    > 增加主題數目會影響效能，以及將主題的功能歸納為一般化。 主題的數量越高，其程度就越細微。 例如，如果一組50主題包含 "籃球，Spurs，Clippers，Lakers" 等主題，則300主題可以包含不同的主題： "Spurs"、"Clippers"、"Lakers"。 如果您不知道主題「籃球」，並將此功能用於 ECA，請參閱主題「籃球」會非常有用。 不過，如果處理過程中有太多主題，您可能永遠看不到「籃球」一詞，也可能不知道 Spurs 及 Clippers 是好的籃球主題可供審閱，而不是在開始時和用於頭髮的專案。 
  
- **建議主題**您可以建議主題文字，以控制主題處理。 「高級 eDiscovery」會將重點放在這些建議的文字上，並根據「主題最大數目」設定，嘗試建立一個或多個相關主題。 
    
    例如，如果建議的字為 "computer"，而您指定 "2" 做為「主題的最大數目」，則高級 eDiscovery 會嘗試產生與「電腦」有關的兩個主題。 例如，這兩個主題可能是 "電腦軟體" 和 "電腦硬體"。 
    
    ![新增建議的佈景主題](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. 若要查看、新增或編輯建議的主題，請按一下 [**修改**]。
    
2. 在 [**建議的主題**] 面板中，按一下 [**新增** ![ 加入圖示] ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 圖示以新增主題。 在 [**新增建議的主題**] 面板中，加入以逗號分隔的字。 
    
3. 在 [**主題數目**] 中，選取一個值，以決定「主題」高級 eDiscovery 將嘗試為這些字詞產生的數目（預設為1個主題）。
    
4. 按一下 [**儲存**]，然後關閉對話方塊。 
    
    > [!NOTE]
    > 主題的總數包含建議的主題。 建議的主題總數不能超過整個主題。 如果有許多相對於整個主題的建議主題，系統只會偵測到一些「novel」主題，因為大多數主題都會專用於建議的主題。 
  
- **模式**從下拉式清單中，選取 [**主題**] 選項： 
    
  - **建立及套用模型**：從一段檔的模型計算主題，然後在這些檔案之間散佈檔。
    
  - **建立模型**：計算來自一段檔的主題模型。 [套用分割檔] 的處理常式會個別于另一次完成。
    
  - 套用**模型**：只有在先前建立的模型和尚未套用的模型時，才會顯示此選項。 這會根據主題來分割檔案。
    
您也可以[設定忽略文字](set-ignore-text-in-advanced-ediscovery.md)，並設定分析的 [[分析高級設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)]。 
  
在您設定這些選項之後，請按一下 [**分析**] 以執行。 顯示 [ [View 分析結果](view-analyze-results-in-advanced-ediscovery.md)]。 
  
## <a name="related-topics"></a>相關主題

[進階電子文件探索 (傳統版)](office-365-advanced-ediscovery.md)
  
[瞭解檔相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[設定忽略文字](set-ignore-text-in-advanced-ediscovery.md)
  
[設定分析進階設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[View 分析結果](view-analyze-results-in-advanced-ediscovery.md)

