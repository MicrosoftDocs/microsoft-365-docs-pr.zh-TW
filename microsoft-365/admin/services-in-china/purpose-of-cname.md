---
title: MSOID 的 Office 365 CNAME 記錄的用途為何？
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: 深入瞭解 Office 365 中的 ' MSOID ' CNAME 記錄，可引導您使用最佳的驗證程式伺服器，讓您能更快速地進行回應。
monikerRange: o365-21vianet
ms.openlocfilehash: f5369b8a723c60691da0e73f2bd8cc32233abbcd
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212218"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>MSOID 的 Office 365 CNAME 記錄的用途為何？

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
> [!NOTE]
> 下列僅適用于由世紀運作的 * * Office 365。
  
您可能會覺得奇怪，為什麼您需要在 Office 365 中新增 "MSOID" CNAME 記錄。 無論您使用何種訂閱，這都是必須針對所有自訂網域而新增的記錄。 為什麼您需要此記錄？ 這是稍有技術性但卻很基本的問題，因為這樣才能將您導向至特定驗證處理程序的最佳伺服器，您因而能更快獲得回應。
  
技術詳細說明：當您執行可與 Office 365 (例如 商務用 Skype Online、Outlook、Windows PowerShell 或 Microsoft Azure Active Directory 同步作業工具) 搭配使用的用戶端應用程式，您的認證必須經過驗證。Office 365 使用 CNAME 記錄以針對您所在位置指向正確的驗證端點，這可確保快速驗證回應時間。
  
如果您的網域已遺失此 CNAME 記錄，這些應用程式會使用美國的預設驗證端點，這表示驗證速度可能會變慢。如果未正確設定此 CNAME 記錄，例如，如果您在 **[指向位址]** 中輸入錯誤，這些應用程式將無法進行驗證。
  
 **如果 Office 365 管理您網域的 DNS 記錄，** Office 365 為您設定此 CNAME 記錄。 
  
 **如果您是在 dns 主機管理網域的 dns 記錄，** 您可以[遵循 DNS 主機的指示](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx)自行建立此記錄。
  
如果您是在規劃 Office 365 部署，並且想要深入瞭解可能需要新增或更新的所有 DNS 記錄，請參閱[下列內容： Office 365 的外部網域名稱系統記錄](https://go.microsoft.com/fwlink/?LinkId=579013)。
  

