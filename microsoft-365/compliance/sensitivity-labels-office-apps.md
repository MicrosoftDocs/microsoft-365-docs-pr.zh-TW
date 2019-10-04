---
title: 敏感度標籤在 Office App 中的運作方式
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用敏感度標籤，您可以分類並協助保護敏感內容，同時確保人員的生產力與共同作業能力不會受到阻礙。您可以使用敏感度標籤在標記的內容上強制執行保護設定，例如加密或浮水印。
ms.openlocfilehash: 1de7eadfcf95a54917c1d5e2cc0d42cc1ad486a5
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378647"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a>敏感度標籤在 Office App 中的運作方式

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a>使用 Office 應用程式中的敏感度標籤有何必要條件？

### <a name="common-requirements"></a>常見需求 

- 整合敏感度標籤必須在[安全性與合規性中心中設定和發佈](https://aka.ms/managemip)
- 使用者必須使用其公司帳戶登入 Office。
- 使用者必須獲派 Office 365 E3 或以上版本的授權。

### <a name="additional-requirements-for-office-for-windows"></a>Windows 版 Office 的其他需求 

- 絕對不能在 Office 中執行 Azure 資訊保護用戶端。 另請參閱：[敏感度標籤可以和Windows 版 Office 中的 Azure 資訊保護用戶端一起執行嗎？](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)。

### <a name="additional-requirements-for-outlook-on-all-platforms"></a>所有平台上 Outlook 的其他需求 

- 如果您在標籤設定中開啟了內容標記，則必須使用 Exchange Online，才能在傳輸中插入內容標記。

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a>目前 Office 支援哪些敏感度標籤功能？ 

<table border="1" cellspacing="0" cellpadding="0">
<th><font size="-1">功能<th><font size="-1">Windows<th><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">網頁</tr>
<tr><td>

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook


<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook </b>
</tr>

<tr>
<td><font size="-1">手動套用、變更或移除標籤<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">即將推出<sup>3</sup><td><font size="-1">即將推出<sup>3</sup>

<tr>
<td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">套用預設標籤</a>
<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">即將推出<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">需要變更標籤的理由</a><sup>1</sup>
<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">即將推出<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">提供自訂說明頁面的說明連結</a>
<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">即將推出<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">標記內容</a>
<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font
><td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">即將推出<sup>3</sup>

<tr><td><font size="-1">指派預先定義的權限
<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">即將推出<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">讓使用者指派權限</a>
<td><font size="-1"><b>是</b><sup>2</sup><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><sup>2</sup><br><font size="-1">16.21.0+</font>

<td><font size="-1">未定
<td><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">未定<td
><font size="-1">即將推出<sup>3</sup>
<td><font size="-1">未定
<td><font size="-1">即將推出<sup>3</sup>

<tr><td><font size="-1">傳送<a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">標籤分析</a>資料給系統管理員
<td><font size="-1">未定

<td><font size="-1">未定

<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定

<tr><td><font size="-1">要求使用者在電子郵件和文件中套用標籤
<td><font size="-1">未定

<td><font size="-1">未定

<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">自動將敏感度標籤套用到內容</a>
<td><font size="-1">未定

<td><font size="-1">未定

<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定
<td><font size="-1">未定
</table>

<br><sup>1</sup>如設定，系統會提示使用者說明標籤降級的理由。 但是，理由資料尚未提供給系統管理員。 當支援 [傳送標籤分析資料給系統管理員] 功能時，系統就會提供此功能。
<br><sup>2</sup>目前只有 Windows 版和 Mac 版 Outlook 才能讓使用者指派權限。 Word、Excel 和 PowerPoint 的適用性未定。
<br><sup>3</sup>預計是 2019 年的第四季。

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a>在內容加上敏感度標籤之後，何時會套用內容標記或加密功能？

| 應用程式 | 內容標記 | 加密
| --- | --- | --- |
| 所有平台上的 Word、Excel、PowerPoint | 立即 | 立即 |
| 電腦版和 Mac 版 Outlook | 在 Exchange Online 傳送電子郵件之後 | 立即 |
| 所有平台上的 Word、Excel、PowerPoint | 在 Exchange Online 傳送電子郵件之後 | 在 Exchange Online 傳送電子郵件之後 |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a>敏感度標籤可以和 Windows 版 Office 中的 Azure 資訊保護用戶端一起執行嗎？

不行。 如果在 Windows 版 Office 中載入 Azure 資訊保護用戶端，敏感度標籤即會關閉。

如果您已安裝 Azure 資訊保護用戶端，但想要改用敏感度標籤，您可以：

1. 設定 [在 Office 中使用 [敏感度] 功能以套用並檢視敏感度標籤] **** 的群組原則設定，這個設定可在 **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings** 下找到。

  >注意：這個設定可透過傳統的群組原則部署機制來部署，或是透過 [Office 雲端原則服務][](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)。 
 
  或者，您可以解除安裝或 [停用] [](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) Azure 資訊保護用戶端。 

2. 重新啟動所有 Office 應用程式。

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a>Office 的非訂閱版本是否支援敏感度標籤，例如 Office 2016 或 Office 2019？

不行。 只有 Office 365 訂閱才支援敏感度標籤，所有非訂閱版本均不支援。 不過，可以在 Office 的非訂閱版本中使用 Azure 資訊保護的整合式標籤用戶端。 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a>我在設定敏感度標籤之前已經部署好保護範本。 它們去哪裡了？

啟用敏感度標籤後，系統管理員定義的[保護範本](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)即會隱藏，Office 使用者無法使用，因為靈敏度標籤已啟用加密功能，因此這些範本是多餘的。 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a>檔案或電子郵件是否可以有多個分類？

使用者一次只能為每個文件或電子郵件選取一個標籤，因此就只會有一個分類。 不過，如果使用者選取子標籤，即會同時套用兩個標籤；一個主要標籤和一個次要標籤。 使用子標籤後，檔案可以有兩個分類，分別表示父/子關係，以提供另一層控制。 

例如， **機密** 標籤可能包含 如 **法務** 和 **財務**等子標籤。 您可以將不同的分類視覺標記和不同的版權管理範本套用到這些子標籤。 使用者無法自行選取 **機密** 標籤；只能選取其子標籤，如 **法務**。 因此，他們所見的標籤為 **機密** / **法務**。 該檔案的中繼資料包含一個 **機密**的自訂文字屬性、一個 **法務**的自訂文字屬性，另一個包含這兩個值的自訂文字屬性 (**C機密法務**)。 

當您使用子標籤時，請不要在主要標籤上設定視覺標記、保護和條件。 當您使用子層級時，請只在子標籤上設定這些設定。 如果您在主要標籤和子標籤上設定這些設定，則會優先採用子標籤上的設定。

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a>標記電子郵件後，附件也會自動獲得相同的標記嗎？

不會。 當您標記具有附件的電子郵件時，這些附件不會繼承相同的標籤。 附件會保持為沒有標籤，或者保留個別套用的標籤。 但是，如果電子郵件的標籤套用保護，則該保護將套用至 Office 附件。

## <a name="additional-resources"></a>其他資源

[Azure 資訊保護中分類與標籤的常見問題集](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[在 Office 中將敏感度標籤套用至您的文件和電子郵件](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)