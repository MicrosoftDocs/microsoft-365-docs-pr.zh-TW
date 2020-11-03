---
title: 外洩通知
description: 了解Microsoft 服務如何防止個人資料外洩，以及若發生外洩 Microsoft 會如何回應和通知您。
keywords: Microsoft 365、Microsoft 365 教育版, Microsoft 365 文件, GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: e94cd9e615ee53827517dd7de02d9c0002532688
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843147"
---
# <a name="gdpr-breach-notification"></a>GDPR 外洩通知

針對為歐盟 (EU) 中的人們提供產品及服務或為歐盟居民收集和分析資料的組織，一般資料保護規定 (GDPR) 推出了新的規則，而無論您或您的企業位於何處。 您可以在 [GDPR 摘要主題](gdpr.md)中找到其他詳細資料。 本文件會引導您了解依據 GDPR 使用 Microsoft 產品和服務時，完成外洩通知的相關資訊。

## <a name="what-constitute-a-breach-of-personal-data-under-the-gdpr"></a>GDPR 規定的個人資料是由什麼所構成？

個人資料表示與個人相關的任何資訊，可用來直接或間接識別他們。 個人資料外洩是「導致意外或非法損毀、遺失、變更、未經授權洩漏或存取所傳輸、儲存或處理的個人資料之安全性缺口」。

## <a name="terminology"></a>術語

本文件中使用的 GDPR 術語的實用定義：

- 資料控制者 (控制者)：法律人員、公開授權單位、公司或其他實體，不論單獨或聯合其他單位，會決定個人資料處理方式的用途及方式。  
- 個人資料和資料主體：與已識別或可識別的自然人 (資料主體) 相關的任何資訊；可識別的自然人為可直接或間接識別的個人。  
- 處理者：自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。  
- 客戶資料：在公司運作的日常作業中產生並儲存的資料。

## <a name="microsoft-and-breach-notification"></a>Microsoft 與外洩通知

Microsoft 很認真看待其在一般資料保護規定 (GDPR) 下所需承擔的責任。 安全性事件/資料外洩是指例如非法存取客戶儲存在 Microsoft 設備上或 Microsoft 設施中資料的事件，或未經授權存取而可能導致客戶資料遺失、揭露或變更的事件。

身為資料處理者，Microsoft 確保服務客戶能夠符合與資料控制者一樣的 GDPR 外洩通知需求。 我們的通知提供進行該評估所需的資訊。 Microsoft 會在有任何個人資料外洩時通知客戶，除了個人資料經確認為無法辨識的情況 (例如，已確認其金鑰完整性的加密資料)。

資料控制者負責評估資料隱私權的風險，並且決定外洩時是否需要客戶 DPA 的通知。 Microsoft 伴隨您的 GDPR 合規性原則提供需要的通知，以進行該評估。

初始通知包含外洩本質、大致使用者影響及風險降低步驟 (如果有的話) 的描述。 如果我們的調查在初始通知時不完整，我們會指出後續通訊的後續步驟和時間表。 如需 Microsoft 如何偵測及回應個人資料外洩的詳細資訊，請參閱服務信任入口網站中的 [GDPR 規定的資料外泄通知](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)。

特定 Microsoft 產品和服務外洩通知相關的詳細資料如下所示。
  
1. **[Office 365](gdpr-breach-Office365.md)**  
    Microsoft 在系統、處理程序及人員上花費許多心思，為求降低個人資料外洩的可能性，以及在資料外洩發生時進行快速偵測，並降低其造成的傷害。 其他詳細資料請參閱 [Office 365 在資料安全性中的投資](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security)。

    客戶可能發現外洩，而且想要連絡 Microsoft。 在此情況下，請通知 Microsoft 支援服務，然後與工程小組接洽以取得詳細資訊。

2. **[Azure 與 Dynamics 365](gdpr-breach-azure-dynamics.md)**  
    Microsoft 有全球全年無休的事件回應服務，降低對於 Microsoft Azure 與 Dynamics 365 攻擊的風險。

    - *外洩偵測* ：因為 Microsoft 和客戶都有維護安全性的義務，因此 Azure 服務使用共用模型來定義安全性與操作的責任。 Microsoft 不會監視或回應客戶責任範圍內的安全性事件。 客戶事件回應可能會牽涉到與 Azure [客戶支援](https://azure.microsoft.com/support/options/)共同作業，前提是有適當的服務合約。 Microsoft Azure 也提供各種不同的服務 (例如，[Azure Defender*](https://azure.microsoft.com/services/security-center/))，客戶可以用來開發和管理安全性事件回應。

        如需 Microsoft Azure 中觸發外洩調查的事件清單，請參閱[偵測潛在缺口](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches)。 [GDPR 規定的 Azure 和外洩通知](gdpr-breach-azure-dynamics.md)進一步詳述 Microsoft 在 Azure 中調查、管理以及回應安全性事件的方式。

    - 資料外洩回應：Microsoft 藉由調查事件的功能影響、恢復能力和資訊影響，決定外洩的適當優先順序和嚴重性層級。 優先順序和嚴重性可能會隨著調查的進行，根據新的發現結果和結論而變更。
    Microsoft 安全性回應小組與全球法律顧問密切合作，以協助確保該鑑識是根據法律義務和對客戶的承諾來執行。 這些程序於 [Azure 的資料外洩回應](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response)中詳述。

    - 客戶通知：Microsoft Azure 視需要通知客戶和監管單位有資料外洩。 客戶通知會在我們宣告外洩的 72 小時內傳遞，除了下列情況：

        - Microsoft 相信執行通知的動作會增加其他客戶的風險。
        - 72 小時的時間表可能會讓某些事件詳細資料可供使用。 這些詳細資料會隨著調查進行提供給您。

        如需進一步的詳細資料，請參閱[客戶通知](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification)。

3. **[Microsoft 支援服務與專業服務](gdpr-breach-Microsoft-Support-Professional-Services.md)**  
    專業服務的本質表示某些資料保護事件可能會落在客戶的責任範圍。 Microsoft 專業服務發現資料保護事件時，它會遵循如[資料保護事件回應程序的範圍與限制](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process)中所述的記載業界標準回應計劃。

## <a name="breach-notification-admin-tools"></a>外洩通知系統管理工具

- **設定貴組織的隱私權連絡人** ：如果 Microsoft 需要與貴組織的隱私權連絡人進行通訊，租用戶系統管理員可以使用 [Azure Active Directory 系統管理入口網站](https://go.microsoft.com/fwlink/p/?linkid=2052736)來定義貴組織的隱私權連絡人。

## <a name="learn-more"></a>深入了解

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
