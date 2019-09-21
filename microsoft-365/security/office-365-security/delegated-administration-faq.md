---
title: 委派管理常見問題集
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: 針對想要執行委派的 Office 365 管理工作的 Microsoft 合作夥伴和轉銷售，包括能夠管理其他承租人 (公司) 的 Exchange Online Protection (EOP)，本主題提供常見問題與解答。
ms.openlocfilehash: 8fcc409c9a5705ad824f7f74b3370afa07e650e3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077937"
---
# <a name="delegated-administration-faq"></a>委派管理常見問題集

針對想要執行委派的 Office 365 管理工作的 Microsoft 合作夥伴和轉銷售，包括能夠管理其他承租人 (公司) 的 Exchange Online Protection (EOP)，本主題提供常見問題與解答。
  
 **問：我是轉銷商，需要管理客戶的承租人；該怎麼做？**
  
答：是。 如果您的 Microsoft 合作夥伴或轉銷商，而且您已簽署最多可為 Microsoft 顧問，您可以要求權限管理在系統管理中心內其租用戶。 這稱為委派管理，以及它可讓您管理其 Office 365 租用戶中 （包括 EOP 設定） 如果當您已在組織內系統管理員。 執行委派的管理的步驟如下所示：
  
1. 註冊成為 [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits)。

2. 註冊 Office 365 委派管理。客戶必須將委派管理員的身分授權給您，您才可以開始管理客戶的帳戶。若要取得核准，您需要先[將委派管理的邀請寄給他們](https://go.microsoft.com/fwlink/?LinkId=396829)。(您也可以稍後再提供委派管理給客戶。)

3. 建立委派的管理員帳戶使用中[的 [新增或刪除委派的系統管理員](https://go.microsoft.com/fwlink/?LinkId=396831)的步驟。

請參閱＜[合作夥伴：建立業務以及管理您的 Office 365 合作夥伴帳戶](https://go.microsoft.com/fwlink/?LinkId=301485)＞，以取得如何設定 Office 365 委派管理的詳細資訊。
  
 **問：我是客戶，不是轉銷商，該如何為子承租人設定委派的系統管理員？**
  
答：委派的管理目前僅適用於轉銷商和合作夥伴。不過，我們提供範例 Windows PowerShell 指令碼，可協助您將原則套用到您的子承租人 (公司)。如需詳細資訊，請參閱 [套用 EOP 設定至多個承租人的範例指令碼](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。
  
 **問：可以防止我的子承租人管理員修改我的原則嗎？**
  
答：Office 365 目前不具備這項功能。
  
 **問：我可以取得所有子承租人的彙總報告嗎？**
  
答：是。 跨您管理公司的合併報告不適用於 Microsoft 365 系統管理中心報告這一次。 不過，您可以使用遠端 Windows PowerShell 或[Office 365 報告 web 服務](https://go.microsoft.com/fwlink/?LinkId=279926)。

