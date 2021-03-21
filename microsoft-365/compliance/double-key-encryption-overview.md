---
title: 雙機碼加密概述及常見問題
description: 有關 Microsoft 365 雙金鑰加密的常見問題。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: ed07361f8c433a318342ae3c8ad750549992c285
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922047"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>雙機碼的常見問題

關於雙重金鑰加密的運作方式有疑問嗎？ 在這裡檢查答案。

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>什麼是 Microsoft 365 (DKE) 的雙金鑰加密？

Microsoft 365 的雙金鑰加密可讓客戶保護其高度機密的資料，以符合特殊的需求。 它可協助客戶維護其加密金鑰的「完全控制」。 它會使用兩個鍵來保護資料;您的控制項中有一個索引鍵，另一個會安全地儲存在 Microsoft Azure 中的金鑰。 查看以雙金鑰加密保護的資料時，需要同時存取這兩個金鑰。 因為 Microsoft 只能存取其中一項，所以 Microsoft 無法存取受保護的資料，因此可確保您能夠完全控制您的資料隱私權和安全性。  

您可以在您的選擇 (內部部署金鑰管理伺服器或雲端) 中，主控用來要求金鑰的雙金鑰加密服務。 您可以像維護任何其他應用程式一樣維護服務。 雙金鑰加密可讓您控制對 Double 金鑰加密服務的存取。 您可以將高度機密資料儲存在內部部署中，也可以將它移至雲端。 您可以自信預防協力廠商存取，因為您維護機碼的完全控制權。 雙金鑰加密可讓您將資料和機碼儲存在相同的位置。

DKE 可協助您滿足各項管理法規的需求，例如一般資料保護法規 (GDPR) 、健康保險業便攜性和責任法案 (HIPAA) 、Gramm-Leach-Bliley 法案 (GLBA) ，俄羅斯的資料當地語系化法–聯邦法律否。 242-FZ、澳大利亞的聯邦隱私權法案1988和紐西蘭的隱私權法案1993。

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>我可以搭配 Microsoft Office 內建敏感度標籤使用雙金鑰加密嗎？

您需要使用 Azure 資訊保護統一的標籤用戶端，以雙金鑰加密來保護檔。 目前，您無法使用 Microsoft Office 內建的敏感度標籤。

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>我可以搭配 DKE 使用的 Microsoft 365 應用程式？

您可以使用 DKE 標籤，在 Windows 上使用 Word、Excel 和 PowerPoint 的桌上出版本來保護檔。 確定您使用的是12711或更新版本 (Windows 上的 Word、PowerPoint 和 Excel) 的桌上出版本。

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>雙機碼與現有的金鑰加密有何不同與現有的 (HYOK) 解決方案？

雙按鍵加密會以兩個金鑰來加密您的資料。 您的加密金鑰在您的控制中，而第二個金鑰是儲存在 Microsoft Azure 中，可讓您將加密的資料移至雲端。 HYOK 只會使用一個金鑰來保護您的內容，而且金鑰永遠都是在內部部署。  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>是否可以在外部共用雙金鑰加密檔？

您可以在不同的承租人上，與使用者共用雙機碼檔，只要使用者可以：

- 具備必要的許可權才能存取您的雙重金鑰加密服務中的金鑰。

- 具有存取您的金鑰在 Microsoft Azure 中所需的許可權。

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>以 HYOK 保護的檔會發生什麼事？

部署雙重金鑰加密不會影響現有的 HYOK 設定。 不過，我們建議您開始與 HYOK 同時使用雙金鑰加密。

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>我是否可以在非 Microsoft 不確定環境中執行雙重金鑰加密？

DKE 不支援這些環境，因為服務需要存取 Microsoft Azure。

## <a name="where-can-i-store-double-key-encrypted-documents"></a>我可以在哪裡儲存雙金鑰加密檔？

您可以在內部部署或雲端中儲存雙金鑰加密檔。 在雲端中，您可以將加密內容移至 SharePoint 線上和商務 OneDrive。 因為 Microsoft 沒有私密金鑰的存取權，所以加密的資料會對 Microsoft 保持不透明。 這也表示您無法在 Office Web Apps 中線上查看加密的檔。

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>哪些地區和語言是可用的雙金鑰加密？ 全球是否可使用雙金鑰加密？

DKE 標籤會當地語系化為與 Microsoft 資訊保護中其他敏感度標籤相同的語言。 您可以在全球範圍內使用雙金鑰加密。

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>是否可以將非 DKE 標籤轉換為 DKE 標籤？

否。 您無法在建立標籤之後將 DKE 新增至標籤。 相反地，您必須在建立標籤時，選擇 [ **使用雙重金鑰加密** ]，並提供您的雙金鑰加密服務的 URL。

## <a name="how-do-i-roll-my-dke-keys"></a>我要如何滾我的 DKE 機碼？

如需滾動 (（也稱為「旋轉」或「重新加密」）) 您儲存在 Azure 中的機碼的指示，請參閱 [Azure 資訊保護租使用者金鑰的作業](/azure/information-protection/operations-customer-managed-tenant-key)。

如需為 DKE 服務建立新機碼的資訊，請參閱 [租使用者和重要設定](double-key-encryption.md#tenant-and-key-settings) 。

當您建立機碼時，您會設定名稱及 GUID。 然後，如果您旋轉按鍵，就會保留具有 name 及 GUID 的舊記錄，但新增具有相同名稱但 GUID 的新記錄。 新的機碼會設為作用中，讓公開金鑰 API 開始傳回新的加密。 這兩個金鑰都可用於解密，因此可以解密新的內容和舊的內容。