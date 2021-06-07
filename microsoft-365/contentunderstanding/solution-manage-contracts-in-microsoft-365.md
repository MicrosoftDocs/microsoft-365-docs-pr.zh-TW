---
title: 使用 Microsoft 365 解決方案管理合約
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: 瞭解如何使用 SharePoint Syntex、SharePoint 清單、Microsoft Teams 及 Power Automate 的 Microsoft 365 解決方案管理合約。
ms.openlocfilehash: d12ccd2d4bc777b05489556f0d96ce9de80954a8
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770814"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>使用 Microsoft 365 解決方案管理合約

本文說明如何使用 Microsoft 365 SharePoint Syntex 和元件為您的組織建立合約管理解決方案。 它為您提供了一個架構，可協助您規劃及建立符合您獨特業務需求的解決方案。 即使此解決方案不能完全符合您的業務需求，您在規劃中也可以採用它的部分，以建立自訂的合約管理解決方案。

*此內容集檔使用 Microsoft Thomas Molbach 與現代的工作解決方案策略小組一起開發的 Microsoft 365 解決方案。*

## <a name="identify-the-business-problem"></a>識別業務問題

規劃合約管理系統的第一步是瞭解您要嘗試解決的問題。 針對此解決方案，需要解決四個重要的問題：

- **識別合約**。 您的組織可以處理許多檔，例如發票、合約、工作說明書等等。  有些是透過電子郵件傳送的數位資產，有些則是透過傳統郵件傳送的紙面資產。 您需要從其他所有檔中識別所有客戶協定的方法，然後再將它們分類。

- **追蹤合約核准** 的歷程記錄。 您的組織需要一種可靠的方式，來尋找是否已核准或拒絕合約，以及是否已處理付款。 

- **管理合約核准的網站**。 您的組織必須設定一個共同作業網站，讓所有必要的專案關係人都能輕鬆地查看合約。 若有必要，專案關係人應能夠查看整個合約，但經常關心每個合約 (中的幾個主要欄位，例如，客戶名稱、PO 編號及總成本) 。 利益關係人應能夠輕易核准或拒絕傳入的合約。

- **路由檢查的合約**。 已核准和拒絕的合約必須透過特定工作流程路由傳送。 已核准的合約必須路由至協力廠商應用程式進行付款處理。 拒絕的合約必須進行路由以供其他複查。

## <a name="overview-of-the-solution"></a>解決方案概述

  ![使用 SharePoint Syntex、SharePoint 清單、Teams 及 Power Automate 的解決方案圖表。](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

此合約管理解決方案指導方針包括四個 Microsoft 365 元件：

- **Microsoft SharePoint Syntex**：建立模型來識別和分類您的合約檔案，然後從這些檔案中解壓縮適當的資料。

- **Microsoft SharePoint 清單**：使用新式 SharePoint 清單中的可用格式，以商業友好的格式呈現合約。

- **Microsoft Teams**：使用 Teams 通道和關聯的索引標籤的功能，讓您的專案關係人複查及管理合約。

- **Power Automate**：使用流程來引導透過核准程式的合約，然後再到協力廠商的付款申請。

### <a name="how-it-all-works"></a>所有的運作方式

  ![解決方案的圖表，顯示可上傳檔、提取資料、通知利益關係人，以及核准或拒絕合約的工作流程。](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. 檔上傳至 SharePoint 文件庫。 已將 SharePoint Syntex 檔理解模型套用至文件庫。 它會檢查每個檔案，以查看是否有任何與「合約」內容類型相符的檔。 如果找到相符的檔案，則會將檔案歸類為「合約」，並更新檔的內容類型。

2. 模型也會從專案關係人所感興趣的每個合約檔中拉出特定資料，例如 *用戶端*、 *合同工* 和 *費用金額*。

    下列頁面是已訓練模型識別的合約範例。

      ![合約的範例。](../media/content-understanding/contract.png)

3. 在 Microsoft Teams 中，所有的專案關係人皆為安全 Teams 通道的成員，在此通道中，文件庫中的所有合約均可供核准或拒絕使用。 透過使用 Teams 功能，當需要檢查新的合約時，所有的專案關係人都會收到通知。
 
4. 透過使用 Power Automate，會透過 Teams 通道中的核准程式移動合約。 當成員核准合約時，合同狀態會變更為 [核准]，所有成員都會透過 Teams 文章通知，並會建立行專案，以顯示合約已準備好進行中的付出。 您可以擴充此程式，以直接寫入協力廠商財務應用程式進行付款。

5.  當成員拒絕合約時，狀態會變更為 [已拒絕]，而且會透過 Teams 文章通知所有成員。

6. 此解決方案的最終結果是您組織的自動化業務程式。 員工可輕鬆使用 Teams 中的自訂磚模式，以啟動及監視檔的核准工作流程。 

     ![[合約] 索引標籤。](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a>授權需求

此方案依賴下列功能（Microsoft 365 企業版 (E1、E3、E5、F3) 或商務 (Basic、Standard 或進階版) 授權）：

-   Microsoft SharePoint Syntex
-   Microsoft Teams
-   Power Automate

## <a name="create-the-solution"></a>建立方案

下一節將詳細說明如何設定您的合約管理解決方案。 其劃分分為三個步驟：

- [步驟1。使用 SharePoint Syntex 來識別合約檔案及提取資料](solution-manage-contracts-step1.md)
- [步驟2。使用 Microsoft Teams 建立您的合約管理通道](solution-manage-contracts-step2.md)
- [步驟3。使用 Power Automate 建立流程以處理您的合約](solution-manage-contracts-step3.md)
