---
title: Office 365 ATP 安全附件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
description: '[安全附件] 功能可提供電子郵件附件的點擊時驗證。 使用安全附件可保護貴組織不受他人在電子郵件中傳送或接收惡意檔案的危害。'
ms.openlocfilehash: c95287b3dd05cce28bad6761ca7e69ce9cc2f914
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599810"
---
# <a name="office-365-atp-safe-attachments"></a>Office 365 ATP 安全附件

## <a name="overview-of-office-365-atp-safe-attachments"></a>Office 365 ATP 安全附件的概觀

ATP 安全附件 (隨附於 [ATP 安全連結](atp-safe-links.md)) 是 [Office 365 進階威脅防護](office-365-atp.md) (ATP) 的一部分。 「ATP 安全附件」功能會檢查電子郵件附件是否為惡意，然後採取行動來保護貴組織。 「ATP 安全附件」功能會根據您的 Office 365 全域或安全性系統管理員所設定 [ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)，保護貴組織。

ATP 保護也會延伸到 SharePoint Online、商務用 OneDrive 和 Microsoft Teams 中的檔案。 若要深入了解，請參閱[為 SharePoint、OneDrive 和 Microsoft Teams 啟用了 Office 365 進階威脅防護](atp-for-spo-odb-and-teams.md)。

## <a name="how-to-get-atp-safe-attachments"></a>如何取得 ATP 安全附件

首先，請確定您的訂用帳戶包含[進階威脅防護](office-365-atp.md)。 下列訂用帳戶中包含 ATP：[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、[Microsoft 365 商務版](https://www.microsoft.com/microsoft-365/business)、Office 365 E5 和 Office 365 A5 等。如果您組織擁有的 Office 365 訂用帳戶不包含 Office 365 ATP，您可能會以附加元件的形式購買 ATP。 如需詳細資訊，請參閱 [Office 365 進階威脅防護方案和定價](https://products.office.com/exchange/advance-threat-protection)和 [Office 365 進階威脅防護服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (部分機器翻譯)。

接下來，請確定您的 ATP 安全附件原則已定義。 (請參閱[設定 Office 365 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md))。ATP 安全附件功能會在下列情況中運作：

- 已設定 ATP 安全附件原則。 (請參閱[在 Office 365 中設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)。)

- 使用者已使用其公司或學校帳戶登入 Office 365。 (請參閱[登入 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)。)

若要定義 (或編輯) ATP 原則，您必須獲派適當的角色。 下表中有一些範例描述：

|角色|指派位置/條件|
|---------|---------|
|Office 365 全域系統管理員|註冊購買 Office 365 的人會預設為為全域系統管理員。 (請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) (部分機器翻譯) 以深入了解。)|
|安全性系統管理員|Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理|Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>如何得知 ATP 安全附件保護已實作

在您[定義 (或檢閱) 您的 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)之後，若要了解服務的運作方式，請[檢閱進階威脅防護的報告](view-reports-for-atp.md)。

下表將列舉幾個案例。 在這些情況下，我們假設組織擁有包含「進階威脅防護」的 Office 365 訂閱。

|**範例案例**|**此案例中是否套用 ATP 安全附件保護？**|
|:-----|:-----|
|Pat 的組織擁有 Office 365 E5，但尚未為 ATP 安全附件定義任何原則。|否。 雖然功能可供使用，但是必須定義至少一個 ATP 安全附件原則，才能使用「ATP 安全附件」保護。|
|Lee 是 Contoso 銷售部門的員工。 Lee 的組織已實作 ATP 安全附件原則，僅套用至財務部門員工。|否。 在此情況下，財務部門員工將擁有 ATP 安全附件保護，但是其他員工 (包括銷售部門) 在定義包含這些群組的原則之前沒有保護。|
|昨天，Jean 組織的 Office 365 系統管理員設定適用於所有員工的 ATP 安全附件原則。 Jean 在今天稍早收到包含附件的電子郵件訊息。|是。 在此範例中，Jean 有「進階威脅防護」的授權，且包含 Jean 的 ATP 安全附件原則已定義。 新原則通常需要 30 分鐘的時間才會在資料中心之間生效；在此案例中已經過了一天，所以原則應該會生效。|
|Chris 的組織擁有 Office 365 E5，並且已針對組織中的所有人實作 ATP 安全附件原則。 Chris 會收到包含附件的電子郵件，並將郵件轉寄給組織外部的其他人。|ATP 安全附件保護已針對 Chris 所收到的訊息實作。 如果收件者的組織還實作了「ATP 安全附件」原則，則 Chris 轉寄的郵件在抵達時受限於這些原則。|
|Jamie 的組織已實作 ATP 安全附件原則，並且已開啟 [適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)。 Jamie 假設 SharePoint Online 中的每個檔案都已掃描，並且可以安全開啟或下載。|ATP 安全附件保護已根據定義的原則進行實作，但是這並非表示 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的每個個別檔案都已經過掃描。 (若要深入了解，請參閱[適用於 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)。)|

## <a name="submitting-files-for-malware-analysis"></a>提交檔案以進行惡意程式碼分析

- 如果您想要對收到的檔案要求 Microsoft 進行分析，請造訪[提交檔案以進行惡意程式碼分析](https://aka.ms/wdsi/submit) (英文)。

- 如果您想要將收到的電子郵件訊息 (包含或不含附件) 提交給 Microsoft 進行分析，請使用[報告訊息增益集](enable-the-report-message-add-in.md)。
