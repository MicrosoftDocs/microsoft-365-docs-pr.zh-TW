---
title: MSOID 的 Office 365 CNAME 記錄的用途為何？
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: 深入了解 Office 365，可將您導向來驗證程序的最佳伺服器，讓您將 getter 中的 'MSOID' 筆 CNAME 記錄較快的回應。
monikerRange: o365-21vianet
ms.openlocfilehash: fdf728dcaebf65485b1eaed9b41e49f5327e9a41
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252396"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>MSOID 的 Office 365 CNAME 記錄的用途為何？

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
> [!NOTE]
> 下列僅適用於 * * 由 21Vianet 運作的 Office 365。
  
您可能會覺得奇怪，為什麼您需要在 Office 365 中新增 "MSOID" CNAME 記錄。 無論您使用何種訂閱，這都是必須針對所有自訂網域而新增的記錄。 為什麼您需要此記錄？ 這是稍有技術性但卻很基本的問題，因為這樣才能將您導向至特定驗證處理程序的最佳伺服器，您因而能更快獲得回應。
  
技術詳細說明：當您執行可與 Office 365 (例如 商務用 Skype Online、Outlook、Windows PowerShell 或 Microsoft Azure Active Directory 同步作業工具) 搭配使用的用戶端應用程式，您的認證必須經過驗證。Office 365 使用 CNAME 記錄以針對您所在位置指向正確的驗證端點，這可確保快速驗證回應時間。
  
如果您的網域已遺失此 CNAME 記錄，這些應用程式會使用美國的預設驗證端點，這表示驗證速度可能會變慢。如果未正確設定此 CNAME 記錄，例如，如果您在 **[指向位址]** 中輸入錯誤，這些應用程式將無法進行驗證。
  
 **如果 Office 365 管理您的網域 DNS 記錄**Office 365 會為您設定此 CNAME 記錄。 
  
 **如果您要管理您的網域，在您的 DNS 主機的 DNS 記錄**建立此記錄自行遵循[您的 DNS 主機的指示進行](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx)。
  
如果您計劃 Office 365 部署，而且想要深入了解您可能需要新增或更新的所有 DNS 記錄，了解他們在[參照： Office 365 的外部網域名稱系統記錄](https://go.microsoft.com/fwlink/?LinkId=579013)。
  

