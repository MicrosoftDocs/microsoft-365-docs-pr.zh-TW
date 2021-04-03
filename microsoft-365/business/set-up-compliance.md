---
title: 增強 Microsoft 365 商務版的威脅防護
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 設定規范功能以避免資料遺失，並協助保護您的和客戶的敏感資訊。
ms.openlocfilehash: c0accc37d3dcda9ba75813f01a98a3233c5a8369
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579947"
---
# <a name="set-up-compliance-features"></a>設定合規性功能

您的 Microsoft 365 商務版特優隨附功能可保護您的資料和裝置，並可協助您保護您的和客戶的敏感資訊。

## <a name="set-up-dlp-features"></a>設定 DLP 功能

請參閱 [從範本建立 DLP 原則](../compliance/create-a-dlp-policy-from-a-template.md) ，以取得如何設定原則以避免個人資料的保護遺失的範例。 
  
DLP 隨附許多可用於許多不同地區設定的現成原則範本。 例如，澳大利亞財務資料、加拿大個人資訊法案、美國財務資料等等。 如需完整清單，請參閱 [DLP 原則範本包含哪些內容](../compliance/what-the-dlp-policy-templates-include.md) 。 您可以啟用上述所有範本，類似 PII 範本範例。 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>設定 Exchange Online 封存的電子郵件保留

 **Exchange Online** 封存授權功能可透過保存 eDiscovery 的電子郵件內容，協助維護法規遵從性和法規標準。 如果有訴訟，也會在安全性破壞或需要復原已刪除的專案時，提供復原資料的方法。 您可以使用訴訟暫止以保留使用者的所有內容，或使用保留原則自訂您想要保留的專案。
  
**訴訟暫止：** 您可以將使用者的整個信箱置於訴訟暫止狀態，以保留包括已刪除專案的所有信箱內容。 
    
若要將信箱設為訴訟暫止狀態，請在系統管理中心：
    
1. 在左側導覽中，移至 [ **使用者**] [作用中 \> **使用者**]。
    
2. 選取您要對其信箱進行訴訟暫止的使用者。 在 [使用者] 窗格中，展開 [ **郵件設定**]，然後按一下 [ **其他設定**] 旁的 [ **編輯 Exchange 屬性**]。
    
3. 在使用者的 [信箱] 頁面上，選擇左側流覽上的 [*] [信箱功能] * *，然後選擇 [**訴訟暫** 止] 下的 [**啟用**] 連結。
    
4. 在 [ **訴訟** 暫止] 對話方塊中，您可以在 [ **訴訟暫止持續時間** ] 欄位中指定訴訟暫止持續時間。 如果您想要進行無限保留，請將此欄位保留空白。 您也可以新增附注，並將信箱擁有者導向至網站，您可能需要進一步說明訴訟暫止。 \>**儲存**。
    
**保留：** 例如，您可以啟用自訂的保留原則，以在保留期間結束時保留特定時間量或永久刪除內容。 若要深入瞭解，請參閱 [保留原則一覽](../compliance/retention.md)。

## <a name="set-up-sensitivity-labels"></a>設定敏感度標籤

敏感度標籤隨附 Azure 資訊保護 (AIP) 方案1，並可選擇性地使用標籤來保護您的檔和電子郵件。 系統管理員可以自動套用標籤，以定義規則和條件、手動由使用者手動套用，或是使用使用者提供建議的組合來套用。

若要設定敏感度標籤，請 view [建立及管理敏感度標籤](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) 影片。



### <a name="install-the-azure-information-protection-client-manually"></a>手動安裝 Azure 資訊保護用戶端

若要手動安裝 AIP 用戶端：

1. 從 [Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=53018)下載 **AzinfoProtection_UL.exe** 。
 
2. 您可以透過查看 Word 檔來驗證安裝是否正常運作，並確定 [**首頁**] 索引標籤上有 [**敏感度**] 選項。
<br/>![在 Word 檔中下拉式清單中的 [保護] 索引標籤。](../media/word-sensitivity.png)

如需詳細資訊，請參閱 [安裝用戶端](/azure/information-protection/infoprotect-tutorial-step3)。