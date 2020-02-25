---
title: 尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: 了解如何追蹤您藉由確認 DNS 記錄設定正確設定自訂的網域時遇到任何問題。
ms.openlocfilehash: 277e87ad6b06db0b1ef3b3cb5eaaa45a2e77ed6f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251666"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a>尋找並修正在 Office 365 中新增網域或 DNS 記錄之後所發生的問題

 若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。 
  
設定您的網域與 Office 365 搭配運作可能不太容易。使用 DNS 系統的限制頗多，而且您網域的 DNS 設定也會影響到重要的商務活動，例如電子郵件！

> [!NOTE]
> 您可以透過檢查其狀態檢查您的網域的問題。 移至 [**設定** > **網域**並檢視 [**狀態**] 欄中的通知。 如果您看到此問題，請選取 [更多動作 （三個點），然後選擇 [**檢查健康情況**。 會開啟窗格將描述與您的網域發生的任何問題。
  
## <a name="whats-going-on"></a>What's going on?

- [無法驗證您的網域嗎？](#cant-verify-your-domain)
    
- [Outlook 無法運作嗎？](#outlook-isnt-working)
    
- [所有人的電子郵件 got 切換到 Office 365 和您只想要切換電子郵件？](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [無法確認非營利機構或學校帳戶狀態？](#cant-confirm-non-profit-or-school-account-status)

- [無法使用您的網域服務？](#services-not-working-with-your-domain)
    
- [存取您的網站無法運作嗎？](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>無法驗證您的網域嗎？
<a name="BKMK_verify"> </a>

網域驗證無法運作的幾個常見原因如下：
  
1. **驗證記錄值錯誤。** 請仔細檢查您複製並貼入 DNS 主機 TXT 驗證記錄的值是否正確。常見的問題是記錄中未包含 "MS="。我們也需要這個！ 
    
2. **尚未儲存記錄。** 在某些 DNS 主機中，您還需要額外採取一個步驟來儲存區域檔案 (DNS 記錄的儲存位置)，以便在網際網路上更新該檔案。請確定已儲存您的變更，如此 Office 365 才可以看到並驗證記錄。 
    
3. **記錄尚未在網際網路上更新。** 它通常只需幾分鐘，我們會看到新的記錄，但有時可能需要長達幾個小時。 
    
## <a name="outlook-isnt-working"></a>Outlook 無法運作嗎？
<a name="BKMK_OutlookBroken"> </a>

如果您已為網域設定正確的 MX 記錄及其他 DNS 記錄，但是郵件無法運作，請讓我們協助您 [修正 Outlook 問題](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx)。
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a>所有人的電子郵件 got 切換到 Office 365 和您只想要切換電子郵件？
<a name="BKMK_EmailSwitched"> </a>

當您新增網域至 Office 365 時，通常您網域的 MX 記錄被更新 （依您或 Office 365） 以指向 Office 365，並傳送至該網域的所有電子郵件都會開始送往 Office 365。 請確定您已建立信箱 Office 365 中的每一位使用者變更 MX 記錄之前，您的網域上具有電子郵件。
  
如果不想要移動電子郵件的每個人都在您的網域至 Office 365？ 您可以執行下列步驟，[僅使用一小部分的電子郵件地址試驗 Office 365](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx)。
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>無法確認非營利機構或學校帳戶狀態？
<a name="BKMK_validateAcct"> </a>

當您只需要確認貴組織的網域和未設定任何服務時，有幾個案例。 例如，若要證明您的組織是否符合要求學校訂用帳戶的 Office 365。
  
請參閱[驗證您的 Office 365 網域證明所有權、 非營利組織版或教育版狀態，或啟動 Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) ，確定您已完成所有必要的步驟中的指引。 它是有點不同的每一種狀況。 
  
## <a name="services-not-working-with-your-domain"></a>您的網域無法使用服務嗎？
<a name="BKMK_Test"> </a>

我們可以協助您追蹤網域的 DNS 設定問題。 Office 365 中的網域疑難排解員會為您顯示需要修正的所有記錄，以及記錄所需的具體設定。 

> [!TIP]
> 已正確設定您的 DNS，但是郵件無法在桌面版 Outlook 正常運作？查看 [Office 365 可用的不同郵件流程案例](https://go.microsoft.com/fwlink/?LinkId=787530)，以確定您已為公司正確設定各個項目。或透過電子郵件，取得下列更多疑難排解說明：[修正 Outlook 問題](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx)。 
  
## <a name="accessing-your-website-isnt-working"></a>無法存取您的網站嗎？
<a name="BKMK_Website"> </a>

如果您已修正任何 DNS 問題，但是仍有問題，請嘗試下列其中一項動作。
  
- 人員無法進入您的網站 www.mydomain.com：[追蹤網站問題](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)
    
- 您無法將 A 記錄或 CNAME 記錄更新為指向網站：[在 Office 365 中更新自訂 DNS 記錄](../dns/add-or-edit-custom-dns-records.md)
    
