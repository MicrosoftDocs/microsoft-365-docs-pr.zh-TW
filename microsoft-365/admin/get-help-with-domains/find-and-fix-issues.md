---
title: 尋找並修正新增網域或 DNS 記錄之後所發生的問題
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: 瞭解如何確認 DNS 記錄設定正確，以追蹤在設定自訂網域時所遇到之任何問題。
ms.openlocfilehash: 786df75f3f8a514e9b3c2a7666d715c9abd082bd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926387"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>尋找並修正新增網域或 DNS 記錄之後所發生的問題

 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。 
  
設定您的網域以與 Microsoft 365 一起使用可能十分困難。 使用 DNS 系統的限制頗多，而且您網域的 DNS 設定也會影響到重要的商務活動，例如電子郵件！

> [!NOTE]
> 您可以檢查網域的狀態來檢查網域的問題。 請前往 **設定**  >  **網域**，並查看狀態列中的通知。 如果您看到問題，請選取 (三個點) ，然後選擇檢查健康 **狀態**。 開啟的窗格會描述您的網域發生的任何問題。
  
## <a name="whats-going-on"></a>What's going on?

- [無法驗證您的網域嗎？](#cant-verify-your-domain)
    
- [Outlook 無法正常使用？](#outlook-isnt-working)
    
- [每個人的電子郵件都切換至 Microsoft 365，而您只想切換您的電子郵件嗎？](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [無法確認非營利組織或學校帳戶狀態？](#cant-confirm-non-profit-or-school-account-status)

- [服務無法與網域一起使用嗎？](#services-not-working-with-your-domain)
    
- [無法存取您的網站嗎？](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>無法驗證您的網域嗎？
<a name="BKMK_verify"> </a>

網域驗證無法運作的幾個常見原因如下：
  
1. **驗證記錄值錯誤。** 請仔細檢查您複製並貼入 DNS 主機 TXT 驗證記錄的值是否正確。常見的問題是記錄中未包含 "MS="。我們也需要這個！ 
    
2. **尚未儲存記錄。** 在某些 DNS 主機中，您還需要額外採取一個步驟來儲存區域檔案 (DNS 記錄的儲存位置)，以便在網際網路上更新該檔案。 請確認您儲存了變更，Microsoft 365 才能查看並驗證記錄。 
    
3. **記錄尚未在網際網路上更新。** 通常只需要幾分鐘的時間，我們才能看到新記錄，但有時可能需要幾個小時。 
    
## <a name="outlook-isnt-working"></a>Outlook 無法運作嗎？
<a name="BKMK_OutlookBroken"> </a>

如果您已為網域設定正確的 MX 記錄及其他 DNS 記錄，但是郵件無法運作，請讓我們協助您 [修正 Outlook 問題](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>每個人的電子郵件都切換至 Microsoft 365，而您只想切換您的電子郵件嗎？
<a name="BKMK_EmailSwitched"> </a>

當您將網域新增到 Microsoft 365 時，網域的 MX 記錄通常會由您或 Microsoft 365) 更新 (以指向 Microsoft 365，而所有寄至該網域的電子郵件都會開始送往 Microsoft 365。 變更 MX 記錄之前，請確認您為網域中擁有電子郵件的每個人，在 Microsoft 365 中建立信箱。
  
如果您不想將您網域中的每個人的電子郵件移至 Microsoft 365，會如何？ 您可以採取一些步驟，只以幾個電子郵件地址試驗[Microsoft 365。](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>無法確認非營利組織或學校帳戶狀態？
<a name="BKMK_validateAcct"> </a>

當您只需要驗證貴組織的網域，而不需要設定任何服務時，有幾個情況。 例如，向 Microsoft 365 證明貴組織符合學校訂閱的資格。
  
查看驗證 [您的 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) 網域以證明擁有權、非營利組織版或教育版狀態的指引，或啟用 Yammer 以確保您已完成所有必要的步驟。 這在每個情況中會有些不同。 
  
## <a name="services-not-working-with-your-domain"></a>您的網域無法使用服務嗎？
<a name="BKMK_Test"> </a>

我們可以協助您追蹤網域的 DNS 設定問題。 Microsoft 365 中的網域疑難排解員會顯示任何需要修正的記錄，以及記錄所需的設定。 

> [!TIP]
> 已正確設定您的 DNS，但是郵件無法在桌面版 Outlook 正常運作？ 查看您可以使用 [Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) 使用的不同郵件流程案例，以確保您的公司設定正確。 或透過電子郵件，取得下列更多疑難排解說明：[修正 Outlook 問題](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。 
  
## <a name="accessing-your-website-isnt-working"></a>無法存取您的網站嗎？
<a name="BKMK_Website"> </a>

如果您已修正任何 DNS 問題，但是仍有問題，請嘗試下列其中一項動作。
  
- 人員無法進入您的網站 www.mydomain.com：[追蹤網站問題](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- 無法更新 A 記錄或 CNAME 記錄以指向您的網站：更新[Microsoft 365](../dns/add-or-edit-custom-dns-records.md)中的自訂 DNS 記錄

## <a name="related-content"></a>相關內容

[疑難排解：稽核已驗證網域變更的資料](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
