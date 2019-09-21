---
title: 檢視資料外洩防護報告
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 使用 Office 365 中的 DLP 報告，您可以快速檢視 DLP 原則相符項目、 覆寫或誤判; 的數請參閱是否它們在一段時間; 趨勢向上或向下以不同方式; 篩選報表然後選取圖形上線條上的一點檢視其他詳細資料。
ms.openlocfilehash: f3161854a19f9f9a04390eec508ae43e92119f96
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077652"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>檢視資料外洩防護報告

您可以建立您的資料遺失防護 (DLP) 原則之後，您會想確認他們正在為您預期，並協助您符合規範。 使用 DLP 報告中 Office 365 安全性&amp;合規性中心，您可以快速檢視：
  
- **DLP 原則比對**這份報告顯示一段時間的 DLP 原則相符項目計數。 您可以依日期、 位置、 原則或動作篩選報告。 您可以使用此報告來： 
    
  - 調整或調整您的 DLP 原則，當您在測試模式中執行。 您可以檢視符合內容的特定規則。
    
  - 將重點放在特定時段，以了解尖峰和趨勢的原因。
    
  - 探索違反貴組織的 DLP 原則的商務程序。
    
  - 藉由查看哪些動作會套用到內容，了解 DLP 原則的任何業務影響。
    
  - 顯示該原則的任何符合項目來驗證是否符合特定 DLP 原則的規範。
    
  - 檢視的主要使用者清單，然後重複使用者參與您組織中的事件。
    
  - 在您的組織中檢視上方的敏感資訊類型清單。
    
- **DLP 事件**這份報告也會顯示原則相符項目經過一段時間，如原則相符項目報告。 不過，此原則會比對報表顯示相符項目層級規則;例如，若一封電子郵件符合三個不同的規則，原則會比對報表顯示三個不同列項目。 相反地，事件報告 」 可顯示相符項目層級項目;例如，若一封電子郵件符合三個不同的規則，事件報告顯示該份內容單一列項目。 
    
  因為報告計數彙總不同，原則相符項目報告是用來識別與特定規則的相符項目及正常調整 DLP 原則。 事件報告是內容的較適合用來識別會有問題的 DLP 原則的特定部分。
    
- **DLP 誤判和覆寫**如果您的 DLP 原則允許使用者覆寫它，或回報] 誤判，這份報告顯示這類的執行個體計數一段時間。 您可以依日期、 位置或原則篩選報告。 您可以使用此報告來： 
    
  - 調整或調整您的 DLP 原則所看見的原則可能會形成誤判較大數目。
    
  - 檢視他們所覆寫原則以解析原則秘訣時，使用者所提交的理由。
    
  - 探索其中 DLP 原則衝突有效商務程序所產生大量的使用者會覆寫。
    
所有的 DLP 報告可以顯示最近的四個月的時間期間內的資料。 最新的資料可能需要最多 24 小時才會出現在報告。
  
您可以在安全性中找到這些報告&amp;合規性中心\>**報表** \> **儀表板**。
  
![DLP 原則相符項目報告](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>檢視覆寫使用者所提交的理由

如果您的 DLP 原則允許使用者覆寫它，您可以使用誤判和覆寫報告] 來檢視提交的原則提示的文字。
  
![理由欄位中的 DLP 誤判和覆寫報告詳細資料](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>採取動作的見解和建議

報告可以顯示見解和建議您將可以按一下 [請參閱潛在問題的詳細資料，並採取可能的補救措施的紅色警告圖示。
  
![按一下以查看詳細資料，要採取的動作觀點圖示](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>DLP 報告的權限

若要檢視 DLP 報告中安全性 & 合規性中心，您必須被指派:

- 在 Exchange 系統管理中心中的**安全性讀取者**角色。 根據預設，此角色被指派給組織管理和安全性助讀程式在 Exchange 系統管理中心中的角色群組。

- 安全性 & 合規性中心中的**僅限檢視 DLP 符合性管理**角色。 根據預設，此角色被指派給安全性 & 合規性中心的符合性系統管理員、 組織管理、 安全性系統管理員和安全性讀取者角色群組。

- 在 Exchange 系統管理中心**僅檢視收件者**角色。 根據預設，此角色被指派給在 Exchange 系統管理中心相符性管理、 組織管理和 View-Only Organization Management 角色群組。

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>尋找 DLP 報告的 cmdlet

若要使用之 cmdlet 的大部分 security&amp;合規性中心，您需要：
  
1. [使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. 使用下列任何一這些[Office 365 安全性&amp;合規性中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
不過，DLP 報告需要提取資料從 Office 365，包括 Exchange Online。 基於這個理由，DLP 報告指令程式可供 Exchange Online Powershell 中，而不是以安全性&amp;合規性中心 Powershell。 因此，若要使用 cmdlet 的 DLP 報告，您必須：
  
1. [使用遠端 PowerShell 連線到 Exchange Online](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. 使用這些 cmdlet 的任何 DLP 報告：
    
      - [Get-dlpdetectionsreport](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-dlpdetailreport](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

