---
title: Office 365 ATP 安全連結
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 「安全連結」可在 Office 文件和電子郵件訊息中提供點擊超連結時即進行驗證的功能。 使用安全連結來保護組織不受網路釣魚及其他攻擊的威脅。
ms.openlocfilehash: 5834c3c49529f983d426084a50712c55de92fc63
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599790"
---
# <a name="office-365-atp-safe-links"></a>Office 365 ATP 安全連結

## <a name="overview-of-office-365-atp-safe-links"></a>Office 365 ATP 安全連結的概觀

> [!IMPORTANT]
> 本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。 如果您使用 Outlook.com、Office 365 家用版或 Office 365 個人版，並且在尋找 Outlook 中安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)。

Office 365 ATP 安全連結 ([進階威脅防護](office-365-atp.md)的一部份) 可在[電子郵件訊息](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email)和 [Office 文件](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents)中，針對網址 (URL) 提供點擊即進行驗證的功能，協助您保護組織。 「保護」會透過 Office 365 安全小組設定的 [ATP 安全連結原則](set-up-atp-safe-links-policies.md)來定義。
  
當您的 ATP 安全連結原則就緒之後，Office 365 全域系統管理員、安全性系統管理員和安全性讀取者就可以[檢視進階威脅防護的報告](view-reports-for-atp.md)。 這些報告中的資訊可協助安全性小組採取進一步的步驟來保護您組織或研究安全性事件。

當 [ATP 中加入新功能時](office-365-atp.md#new-features-in-office-365-atp)，您的 Office 365 安全性小組可以新增或編輯您組織的 [ATP 安全連結原則](set-up-atp-safe-links-policies.md)。 此外，您可能會注意到有變更和改善項目，例如我們新修訂的[警告頁面](atp-safe-links-warning-pages.md)和 Outlook 中的原生連結呈現 (如 Office 365 專業增強版 1809 中所述)。
         
## <a name="how-to-get-atp-safe-links-protection"></a>如何取得 ATP 安全連結保護

**首先，請確定您的訂用帳戶包含[進階威脅防護](office-365-atp.md)**。 下列訂用帳戶中包含 ATP：[Microsoft 365 企業版](https://www.microsoft.com/microsoft-365/enterprise/home)、[Microsoft 365 商務版](https://www.microsoft.com/microsoft-365/business)、Office 365 企業版 E5 和 Office 365 教育版 A5 等。如果您組織擁有的 Office 365 訂用帳戶不包含 Office 365 ATP，您可能會以附加元件的形式購買 ATP。 如需詳細資訊，請參閱下列資源： 

- [Office 365 進階威脅防護的方案與定價](https://products.office.com/exchange/advance-threat-protection)

- [Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 
  
**接下來，請確定您的 ATP 安全連結原則已定義**。 (請參閱[設定 Office 365 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。) ATP 安全連結功能會在下列情況中運作：
  
- 電子郵件與 Office 文件中已設定 ATP 安全連結原則。 (請參閱[在 Office 365 中設定 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。)

- Office 365 用戶端應用程式已設定為使用新式驗證 (這會用於 Office 文件中的 ATP 安全連結保護)。 (請參閱[適用於 Office 2016 的新式驗證](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。) 
    
- 使用者已使用其公司或學校帳戶登入 Office 365。 (請參閱[登入 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)。)
    
- 您組織的電子郵件可通過 Exchange Online Protection。  

**也請確定您具有必要權限**。 若要定義 (或編輯) ATP 原則，您必須獲派適當的角色。 下表中有一些範例描述：

|角色  |指派位置/條件  |
|---------|---------|
|Office 365 全域系統管理員 |註冊購買 Office 365 的人會預設為為全域系統管理員。 (請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入了解。)         |
|安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>如何確認是否已設定 ATP 安全連結保護

身為全域管理員或安全性系統管理員，請務必定期檢查您的 [ATP 安全連結原則](set-up-atp-safe-links-policies.md)。 ATP 安全連結原則可決定是否只將保護功能套用至電子郵件中的超連結，或同時套用到 Office 文件中的 URL。

建立 ATP 安全連結原則之後，您組織的安全性小組就能透過[檢視進階威脅防護報告](view-reports-for-atp.md)，了解 ATP 安全連結保護如何在組織中運作。 

## <a name="example-scenarios"></a>範例案例
  
下表說明一些範例案例，這些範例可能有或可能沒有 ATP 安全連結保護。 (在這所有案例中，我們都假設組織擁有 Office 365 企業版 E5)。
  
|**範例案例**|**此案例中是否套用 ATP 安全連結保護？**|
|:-----|:-----|
|Jean 是群組成員，該群組的 ATP 安全連結原則涵蓋電子郵件和 Office 文件中的 URL。 Jean 開啟某人傳送的 PowerPoint 簡報，然後按一下簡報中的 URL。  <br/> |是的。 已定義的 ATP 安全連結原則可套用至 Jean 的群組、Jean 的電子郵件，以及 Jean 開啟的 Word、Excel、PowerPoint 或 Visio 文件，只要 Jean 在 Windows、iOS 或 Android 裝置上登入並使用 Office 365 專業增強版即可。  <br/> |
|在 Chris 的組織中，全域或安全性系統管理員都未定義任何 ATP 安全連結原則。 Chris 收到包含惡意網站 URL 的電子郵件。 Chris 不知道 URL 是惡意的，並且按下連結。  <br/> |否。 適用於組織中所有人且涵蓋 URL 的預設原則都必須加以定義，才能有保護效用。  <br/> |
|在 Pat 的組織中，全域或安全性系統管理員都未定義或編輯任何 ATP 安全連結原則。 Pat 開啟 Word 檔，然後按一下檔案中的 URL。  <br/> |否。 包含 Office 文件的原則必須加以定義，才能有保護效用。 請參閱[在 Office 365 中設定 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。  <br/> |
|Lee 他們組織的 ATP 安全連結原則將 `https://tailspintoys.com` 列為封鎖的網站。 Lee 收到包含 `https://tailspintoys.com/aboutus/trythispage` URL 的郵件訊息。 Lee 按下該 URL。  <br/> |這取決於整個網站及其所有子頁面是否包含在封鎖的 URL 清單中。 請參閱[使用 ATP 安全連結來設定自訂的封鎖 URL 清單](set-up-a-custom-blocked-urls-list-wtih-atp.md)。  <br/> |
|Jean 的同事 Jamie 傳送電子郵件給 Jean，但不知道電子郵件含有惡意的 URL。  <br/> |這取決於在組織內傳送的電子郵件是否已定義 ATP 安全連結原則。 請參閱[在 Office 365 中設定 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。  <br/> |


  

