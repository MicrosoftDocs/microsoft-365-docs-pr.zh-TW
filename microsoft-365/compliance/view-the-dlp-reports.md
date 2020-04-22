---
title: 檢視資料外洩防護報告
f1.keywords:
- NOCSH
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
description: 透過 Office 365 的 DLP 報告，您可以快速查看 DLP 原則相符性、覆寫或誤報的數目。查看它們是隨時間向上或向後移動，還是以不同方式篩選報表;然後在圖形上選取線條上的點，以查看其他詳細資料。
ms.openlocfilehash: 6ff8237b1471f10aff3abc40715af7fe538a211c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626289"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>檢視資料外洩防護報告

在您建立資料遺失防護（DLP）原則之後，您可能會想要驗證他們的運作是否正常，並協助您保持相容。 透過安全性&amp;與合規性中心的 DLP 報告，您可以快速查看：
  
- **DLP 原則相符**專案此報告顯示一段時間的 DLP 原則相符計數。 您可以依日期、位置、原則或動作來篩選報告。 您可以使用此報告來： 
    
  - 在測試模式中執行時，請調整或提煉您的 DLP 原則。 您可以查看符合內容的特定規則。
    
  - 將重點放在特定時段，以了解尖峰和趨勢的原因。
    
  - 探索違反貴組織 DLP 原則的商務程序。
    
  - 查看內容所套用的動作，以瞭解 DLP 原則的任何業務影響。
    
  - 顯示該原則的任何符合項目來驗證是否符合特定 DLP 原則的規範。
    
  - 查看主要使用者的清單，並重複參與組織中事件的使用者。
    
  - 在您的組織中查看最上層的敏感資訊類型清單。
    
- **DLP 事件**此報告也顯示一段時間的原則相符專案，就像原則符合報表。 不過，原則符合報表會顯示規則層級的相符專案;例如，如果電子郵件符合三個不同的規則，則原則符合報表會顯示三個不同的行專案。 相反地，附隨報告會顯示專案層級的相符專案;例如，如果電子郵件符合三個不同的規則，則附隨報告會顯示該部分內容的單一行專案。 
    
  由於報告計數的匯總方式不同，因此原則比對報告更適合識別與特定規則的相符專案，以及微調 DLP 原則。 當您識別 DLP 原則有問題的特定內容片段時，附隨報告會比較好。
    
- **DLP 錯誤正值和 overrides**如果您的 DLP 原則允許使用者覆寫它或報告誤報，此報告會顯示一段時間的這類實例計數。 您可以依日期、位置或原則篩選報表。 您可以使用此報告來： 
    
  - 查看哪些原則會產生大量的誤報，以調整或提煉您的 DLP 原則。
    
  - 透過覆寫原則，查看使用者解析原則提示時所提交的理由。
    
  - 透過產生大量的使用者覆寫，探索 DLP 原則與有效商務程式的衝突。
    
所有 DLP 報告都可顯示最近四個月的時間範圍內的資料。 最新的資料可能需要長達24小時才會顯示在報告中。
  
您&amp;可以在安全性與合規性中心\> **報告** \> **儀表板**中找到這些報告。
  
![DLP 原則符合報告](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>查看使用者為覆寫而提交的理由

如果您的 DLP 原則允許使用者覆寫該原則，您可以使用 [誤報] 和 [覆寫] 報告，以查看原則提示中使用者所提交的文字。
  
![DLP false 肯定和覆寫報告詳細資料中的調整欄位](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>對真知灼見和建議採取動作

報告可顯示洞察力和建議，您可以在其中按一下紅色的警告圖示，以查看有關潛在問題的詳細資訊，並採取可能的補救措施。
  
![按一下 insights 圖示，以查看要採取的詳細資料和動作](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>DLP 報告的許可權

若要在安全性 & 規範中心中查看 DLP 報告，您必須被指派下列專案：

- Exchange 系統管理中心中的**安全性讀取器**角色。 根據預設，此角色會指派給 Exchange 系統管理中心內的「組織管理」和「安全性讀者」角色群組。

- 在安全性 & 規範中心**VIEW-ONLY DLP 合規性管理**角色。 根據預設，此角色會指派給安全性 & 合規性中心內的合規性管理員、組織管理、安全性管理員及安全性讀者角色群組。

- 在 Exchange 系統管理中心中**View-Only**收件者角色。 根據預設，此角色會指派給 Exchange 系統管理中心中的規範管理、組織管理和 View-Only 組織管理角色群組。

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>尋找 DLP 報告的 Cmdlet

若要對安全性與合規性中心使用大部分 Cmdlet，您必須：
  
1. [使用遠端 PowerShell 連接&amp;至安全規範中心](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. 使用這些[安全性&amp;與合規性中心 Cmdlet](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)中的任何一個
    
不過，DLP 報告需要從整個 Office 365 擷取資料，包含 Exchange Online。 基於這個理由，在 Exchange Online Powershell 中可以使用 DLP 報告的 Cmdlet，而不是在&amp;安全性與合規性中心 powershell 中。 因此，若要為 DLP 報告使用 Cmdlet，您需要︰
  
1. [使用遠端 PowerShell 連線到 Exchange Online](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. 為 DLP 報告使用下列任何 Cmdlet：
    
      - [Get-DlpDetectionsReport](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

