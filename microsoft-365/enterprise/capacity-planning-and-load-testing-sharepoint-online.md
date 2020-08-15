---
title: SharePoint Online 容量規劃和負載測試
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: 本文說明如何在不允許傳統負載測試的情況下，在不執行傳統負載測試的情況下，部署至 SharePoint Online。
ms.openlocfilehash: a20ed3b5f9b3108d90ec912ec78efa348d4281b1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688700"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>SharePoint Online 容量規劃和負載測試
本文說明如何在未使用傳統負載測試的情況下，部署至 SharePoint Online，因為 SharePoint 線上上不允許進行負載測試。 SharePoint 線上是雲端服務，且服務的負載、健康情況和整體平衡是由 Microsoft 所管理。
  
確保啟動網站成功的最佳方法，就是遵循 [您的入口網站啟動向外設計](planportallaunchroll-out.md)中所述的基本原則、作法和建議。

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>SharePoint 線上如何執行容量規劃的概述 
在內部部署環境中 SharePoint 線上的主要好處之一是雲端的彈性，以及針對分散式區域中的使用者進行優化。 我們將大規模的環境設定為每天為數百萬的使用者提供服務，因此我們必須透過平衡和展開伺服器陣列，有效地處理容量。
  
在任何一個伺服器陣列中的任何一個租使用者的成長都不可預測的情況下，累積的要求總數可在一段時間後預測。 透過找出 SharePoint 線上中的成長趨勢，我們可以規劃未來的擴充。
  
為了有效地使用容量並處理未預期的成長，在任何伺服器陣列中，我們都有可讓您追蹤和監視服務各專案的自動化。 使用多個計量，其中一個主要是 CPU 負載，它是用來向上擴充前端伺服器的信號。 此外，我們也建議使用 [分階段/wave 的方法](planportallaunchroll-out.md)，因為 SQL 環境會隨著時間的負載和成長而縮放，而且遵循階段和波形可讓該負載和成長正確地散佈。 

容量不僅僅是在連續新增更多硬體，也適用于管理和控制該容量，以確保其可提供有效的負載要求。 我們建議客戶遵循建議的指導方針，以確保獲得最佳的體驗。 這也表示我們有節流模式和控制措施，以確保我們不允許在服務中執行「濫用」行為。 雖然並非所有「不良」行為是特意的，但我們卻必須確定會限制該行為的影響。 如需節流的進一步資訊和避免，請參閱 how [to to the to to to to](https://docs.microsoft.com/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)

## <a name="why-you-cannot-load-test-sharepoint-online"></a>為何無法將測試 SharePoint 線上載入
使用內部部署環境時，負載測試是用來驗證規模的設想，並最終找到伺服器陣列的中中斷點;透過負載飽和。 

隨著 SharePoint 線上，我們需要以不同的方式執行，因為比例相對於特定的試探法而相對流動和調整、節流和控制負載。 如此大規模的多租使用者環境，我們必須保護相同伺服器陣列中的所有承租人，因此我們會自動節流任何負載測試。 不過，如果您在嘗試載入測試時，除了受到限制以外，您將會收到 disappointing 及可能誤導的結果，因為您現在所測試的伺服器陣列可能會在測試時段或在測試之後的時段內，隨著規模和伺服器陣列的平衡動作不斷執行。

不是嘗試將測試 SharePoint 當做服務，而是著重于遵循建議的做法，並遵循 [建立、啟動及維護健康的入口網站](https://go.microsoft.com/fwlink/?linkid=2105838) 指導方針。
