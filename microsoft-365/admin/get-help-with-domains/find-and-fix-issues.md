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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: 在設定自訂網域時，請確定已正確設定 DNS 記錄，以追蹤在設定自訂網域時所執行的任何問題。
ms.openlocfilehash: 1dcc52be68fca11245e1a2437d9fe5a3f23ed694
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393892"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>尋找並修正新增網域或 DNS 記錄之後所發生的問題

 若您找不到所需內容，請 **[查看網域常見問題集](../setup/domains-faq.yml)**。 
  
將您的網域設定為與 Microsoft 365 搭配使用可能是挑戰性的。 使用 DNS 系統的限制頗多，而且您網域的 DNS 設定也會影響到重要的商務活動，例如電子郵件！

> [!NOTE]
> 您可以檢查您的網域的狀態，以查看其是否存在問題。 移至 [**安裝**  >  **網域**]，然後在 [**狀態**] 欄中查看通知。 如果您看到問題，請選取 [三個點 () 其他動作]，然後選擇 [ **檢查健康情況**]。 隨即開啟的窗格會描述您的網域所發生的任何問題。
  
## <a name="whats-going-on"></a>What's going on?

- [無法驗證您的網域？](#cant-verify-your-domain)
    
- [Outlook 無法運作？](#outlook-isnt-working)
    
- [所有人的電子郵件都已切換成 Microsoft 365，您只需要切換您的電子郵件？](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [無法確認非盈利或學校帳戶狀態？](#cant-confirm-non-profit-or-school-account-status)

- [服務無法與您的網域搭配運作？](#services-not-working-with-your-domain)
    
- [存取您的網站無法運作？](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>無法驗證您的網域嗎？
<a name="BKMK_verify"> </a>

網域驗證無法運作的幾個常見原因如下：
  
1. **驗證記錄值錯誤。** 請仔細檢查您複製並貼入 DNS 主機 TXT 驗證記錄的值是否正確。常見的問題是記錄中未包含 "MS="。我們也需要這個！ 
    
2. **尚未儲存記錄。** 在某些 DNS 主機中，您還需要額外採取一個步驟來儲存區域檔案 (DNS 記錄的儲存位置)，以便在網際網路上更新該檔案。 請確認您已儲存您的變更，Microsoft 365 可以查看和驗證記錄。 
    
3. **尚未在網際網路上更新記錄。** 這通常只需要幾分鐘的時間，我們才能看到新的記錄，但是有時候它可能需要數小時的時間。 
    
## <a name="outlook-isnt-working"></a>Outlook 無法運作嗎？
<a name="BKMK_OutlookBroken"> </a>

如果您已為網域設定正確的 MX 記錄及其他 DNS 記錄，但是郵件無法運作，請讓我們協助您 [修正 Outlook 問題](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>所有人的電子郵件都已切換成 Microsoft 365，您只需要切換您的電子郵件？
<a name="BKMK_EmailSwitched"> </a>

當您將網域新增至 Microsoft 365 時，通常您的網域的 MX 記錄會由您 (或 Microsoft 365) 更新為指向 Microsoft 365，而且所有傳送至該網域的電子郵件都會開始 Microsoft 365。 在您變更 MX 記錄之前，請確定您已在 Microsoft 365 中為已在您的網域上擁有電子郵件的每位使用者建立信箱。
  
如果您不想將您網域中的每個人的電子郵件移至 Microsoft 365，該怎麼辦？ 您可以[只使用少量的電子郵件地址，進行試驗 Microsoft 365 的](../setup/domains-faq.yml)步驟。
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>無法確認非盈利或學校帳戶狀態？
<a name="BKMK_validateAcct"> </a>

您只需要驗證組織的網域，而不會設定任何服務時，會有幾種案例。 例如，若要證明您的組織符合學校訂閱的 Microsoft 365。
  
請參閱驗證 Microsoft 365 網域中的指導方針[，以證明擁有權、非贏利或教育狀態，或啟動 Yammer](../setup/domains-faq.yml)以確定您已完成所有必要步驟。 這對於每種情況都有些不同。 
  
## <a name="services-not-working-with-your-domain"></a>您的網域無法使用服務嗎？
<a name="BKMK_Test"> </a>

我們可以協助您追蹤網域的 DNS 設定問題。 Microsoft 365 中的「網域」疑難排解會顯示所有需要修正的記錄，以及記錄需要設定的確切專案。 

> [!TIP]
> 已正確設定您的 DNS，但是郵件無法在桌面版 Outlook 正常運作？ 請參閱[您可以在 Microsoft 365 中使用的不同郵件流程案例](/exchange/mail-flow-best-practices/mail-flow-best-practices)，以確定您已為您的公司正確設定專案。 或透過電子郵件，取得下列更多疑難排解說明：[修正 Outlook 問題](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。 
  
## <a name="accessing-your-website-isnt-working"></a>無法存取您的網站嗎？
<a name="BKMK_Website"> </a>

如果您已修正任何 DNS 問題，但是仍有問題，請嘗試下列其中一項動作。
  
- 人員無法進入您的網站 www.mydomain.com：[追蹤網站問題](../setup/add-domain.md)
    
- 您無法更新 A 記錄或 CNAME 記錄，使其指向您的網站：[更新 Microsoft 365 中的自訂 DNS 記錄](../setup/add-domain.md)

## <a name="related-content"></a>相關內容

[疑難排解：已驗證的網域變更 (篇文章的審計資料](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)) \
[網域常見問題集](../setup/domains-faq.yml) (文章)

