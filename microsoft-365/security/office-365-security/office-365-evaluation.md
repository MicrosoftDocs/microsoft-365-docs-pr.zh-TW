---
title: 評估 Microsoft Defender for Office 365
description: 在評估模式中，Office 365 的 defender 為 Office 365 的電子郵件原則，會記錄 verdicts，例如惡意程式碼，但不會對郵件採取動作。
keywords: 評估 Office 365，Microsoft Defender for Office 365，Office 365 評估，嘗試 Office 365，Microsoft Defender，Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 005c1f6ad7806c8d1ba1d38e4e82edd25034075d
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51942990"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>評估 Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender for Office 365 評估是在公開預覽中。 在沒有服務等級協定的情況下提供此預覽版本。 某些功能可能不受支援，或可能具有有限的功能。

進行完整的安全性產品評估，可協助您瞭解升級和購買的決策。 它可協助您嘗試安全性產品的功能，以評估其日常工作中的安全性操作小組的運作方式。

[Microsoft defender For office 365](defender-for-office-365.md)評估體驗旨在消除裝置和環境設定的複雜性，使您能夠專注于評估 Microsoft Defender for Office 365 的功能。 使用評估模式，可以評估所有傳送至 Exchange Online 信箱的郵件，而不需指向 Microsoft 的 MX 記錄。 此功能僅適用于電子郵件保護，而不適用於 Word、SharePoint 或小組等 Office 用戶端。

如果您還沒有支援 Microsoft Defender for Office 365 的授權，您可以開始 [30 天的試用版評估](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) ，並測試 Office 365 安全性 & 規範中心 (中的功能 https://protection.office.com/homepage) 。 您將會喜歡快速設定，必要時您可以輕鬆關閉此功能。

> [!NOTE]
> 如果您處在整合的 Microsoft 365 安全性入口網站中 (security.microsoft.com) 您可以在這裡啟動 Office 365 評估的試用版：電子郵件 & 共同作業 > 原則 & 規則 > 威脅原則 > 其他原則。

## <a name="how-the-evaluation-works"></a>評估的運作方式

在評估模式中，Office 365 的 defender 為 Office 365 的電子郵件原則，會記錄 verdicts，例如惡意程式碼，但不會對郵件採取動作。 您不需要變更 MX 記錄設定。

使用評估模式時，會替您設定 [安全附件](safe-attachments.md)、 [安全連結](safe-links.md)和 [信箱智慧類比原則](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 。 所有的 Office 365 原則都是在後臺非強制模式中建立，對您看不到。

在設定過程中，評估模式也會為 [連接器設定增強型篩選](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。 它會透過保留 IP 位址和寄件者資訊，提高篩選精確度，當郵件透過電子郵件安全性閘道 (ESG) 在 Office 365 的前端時，就會遺失。 針對連接器的增強篩選也會提升現有 Exchange Online Protection (EOP) 反垃圾郵件和反網路釣魚原則的篩選精確性。

啟用增強型連接器的增強篩選功能可提升篩選精確度，但如果您在 Office 365 的 Defender 上有 ESG，而且目前不會略過 EOP 篩選，則可能會變更特定郵件的 deliverability。 影響限制為 EOP 原則;在評估中建立的 MDO 原則安裝會以非強制模式建立。 若要將潛在的實際影響降至最低，您可以建立傳輸規則，將垃圾郵件信賴等級設定 (SCL) 為-1，以略過所有的 EOP 篩選。 請參閱 [使用 EAC 建立郵件流程規則，設定](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)郵件的 SCL 的   詳細資料。

當評估模式已設定時，每日會更新一份報告，其中包含超過90天的資料，量化當原則實施 (例如「刪除」、「傳送至垃圾、隔離」) 時，可能會封鎖的郵件。 報告是針對所有的 Defender for Office 365 和 EOP 偵測產生。 它們會根據偵測技術匯總 (例如，模擬) ，並且可依時間範圍篩選。 此外，您也可以根據需要建立郵件報告，以建立自訂透視或使用威脅瀏覽器深入瞭解郵件。

透過簡化的設定體驗，您可以將重點放在：

- 執行評估
- 取得詳細報告
- 分析動作報告
- 展示評估結果

## <a name="before-you-begin"></a>開始之前

### <a name="licensing"></a>授權

若要存取評估，您必須符合授權要求。 下列任何授權均可運作：

- 適用於 Office 365 的 Microsoft Defender 方案 1
- 適用於 Office 365 的 Microsoft Defender 方案 2
- Microsoft 365 E5，Microsoft 365 E5 Security
- Office 365 E5

如果您沒有其中一個授權，您必須取得試用版授權。

#### <a name="trial"></a>試用

若要取得 Microsoft Defender for Office 365 的試用版授權，您必須具有「 **帳單管理員」角色** 或「 **全域系統管理員」角色**。 向具有全域系統管理員角色的使用者要求許可權。 [深入瞭解訂閱與授權](../../commerce/licenses/subscriptions-and-licenses.md)

當您擁有適當的角色後，建議的路徑是取得 Microsoft Defender for Office 365 的試用版授權 (方案 2) 在 Microsoft 365 系統管理中心，請移至帳單 > 購買服務。 試用期包括30天的免費試用版，取得25個授權。 [取得 Microsoft Defender For Office 365 的試用版 (方案 2) ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。

您將會有30天的時段，其評估是用來監視和報告高級威脅。 如果您想要完整的 Office 365 功能，您也可以選擇購買付費訂閱。

### <a name="roles"></a>角色

在評估模式中，**需要有 Exchange Online 角色** 才能設定 Office 365 的 Defender。 指派 Microsoft 365 規範或安全性系統管理員角色將無法運作。

- [深入瞭解 Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)
- [深入瞭解指派系統管理員角色](../../admin/add-users/assign-admin-roles.md)

下列角色是必要的：

|工作|Exchange Online 中的角色 () |
|---|---|
|取得免費試用版或購買 Microsoft Defender for Office 365 (方案 2) |計費系統管理員角色或全域系統管理員角色|
|建立評估原則|遠端和公認的網域角色;安全性系統管理員角色|
|編輯評估原則|遠端和公認的網域角色;安全性系統管理員角色|
|刪除評估原則|遠端和公認的網域角色;安全性系統管理員角色 |
|查看評估報告|安全性管理員角色或安全性讀者角色|
|

### <a name="enhanced-filtering"></a>增強型篩選

您的 Exchange Online Protection 原則（如大量和垃圾郵件保護）將保持不變。 不過，評估會針對連接器開啟增強型篩選功能，這可能會影響郵件流程和 Exchange Online Protection 原則，除非略過。

連接器的增強型篩選功能允許承租人使用反欺騙保護。 如果您使用的電子郵件安全性閘道 (ESG) 但未開啟「增強型連接器」篩選，則不支援反欺騙。

### <a name="urls"></a>URL

郵件流程期間會引爆 URLs。 如果您不想要引爆特定的 URLs，請適當地管理您的允許 URLs 清單。 如需詳細資訊，請參閱 [管理租使用者 Allow/封鎖清單](tenant-allow-block-list.md) 。

電子郵件內文中的 URL 連結將不會換行，以減少對客戶的影響。

### <a name="email-routing"></a>電子郵件路由

準備要設定電子郵件目前如何路由的對應詳細資料，包括路由傳送郵件之輸入連接器的名稱。 如果您只是使用 Exchange Online Protection，則不會有連接器。 [深入瞭解郵件流程和電子郵件路由](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

支援的電子郵件路由案例包括：

- **協力廠商的合作夥伴和/或內部部署服務提供者**：您要評估的輸入連接器使用協力廠商提供者和/或您正在使用內部部署電子郵件安全性的解決方案。
- **僅限 Microsoft Exchange Online Protection**：您要評估的承租人使用 Office 365 進行電子郵件安全性和郵件交換 (MX) 記錄指向 Microsoft。

### <a name="email-security-gateway"></a>電子郵件安全性閘道

如果您正在使用協力廠商電子郵件安全性閘道 (ESG) ，您必須知道提供者的名稱。 如果您使用的是 ESG 內部部署或不受支援的廠商，您必須知道裝置的公用 IP 位址 (es) 。

支援的協力廠商合作夥伴包括：

- 梭魚
- IronPort
- Mimecast
- Proofpoint
- Sophos
- 賽門鐵克
- 走向微

### <a name="scoping"></a>範圍

您將能夠將評估的範圍限定為輸入連接器。 若未設定連接器，評估範圍將允許系統管理員從您租使用者中的任何使用者收集資料，以評估 Office 365 的 Defender。

## <a name="get-started-with-the-evaluation"></a>評估入門

在 Office 365 安全性 & 合規性中心 (https://protection.office.com/homepage) 三個存取點中，尋找 Microsoft Defender For office 365 評估設定卡。

- 威脅管理 > 儀表板
- 威脅管理 > 原則
- 報表 > 儀表板

## <a name="setting-up-the-evaluation"></a>設定評估

當您為評估啟動設定流程之後，您會有兩個路由選項。 根據組織的郵件路由設定和評估需求，您可以選擇是否使用協力廠商和/或內部部署服務提供者或僅限 Microsoft Exchange Online。

- 如果您使用協力廠商的合作夥伴和/或內部部署服務提供者，您必須從下拉式功能表中選取廠商的名稱。 提供其他連接器相關的詳細資料。

- 若 MX 記錄指向 Microsoft，而且您有 Exchange Online 信箱，請選取 [Microsoft Exchange Online]。

請複查您的設定，並視需要進行編輯。 然後，選取 [ **建立評估**]。 您應該會收到確認訊息，指出您已完成設定。

您的 Microsoft Defender for Office 365 評估報告每天產生一次。 最多可能需要24小時的時間來填入資料。

### <a name="exchange-rules-optional"></a>Exchange 規則 (選用) 

如果您有現有的閘道，啟用評估模式將會啟用連接器的增強篩選功能。 這會變更傳入寄件者的 IP 位址，以提升篩選精確度。 這可能會變更篩選 verdicts，但如果您不是略過 Exchange Online Protection，這可能會變更特定郵件的 deliverability。 在此情況下，您可能會想要暫時略過篩選以分析影響。 若要略過，請流覽至 Exchange 系統管理中心，並建立 SCL-1 (的原則（如果您尚沒有) ）。 如需規則元件及其運作方式的詳細資訊，請參閱 Mail flow rules (transport rules) in Exchange Online。

## <a name="evaluate-capabilities"></a>評估功能

產生評估報告之後，請查看組織中的電子郵件和共同作業工作區中識別的高級威脅連結、高級威脅附件及可能的 impersonations 數目。

試用期到期後，您可以繼續存取90天的報告。 不過，它不會收集任何其他資訊。 如果您想要在試用期到期後繼續使用 Microsoft Defender for Office 365，請確定您 [購買了適用于 office 365 的 Microsoft defender 訂閱 (方案 2) ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。

您可以在任何時間，移至 [ **設定** ] 以更新您的路由或關閉評估。 不過，如果您決定在關閉評估之後繼續評估，您必須重新執行相同的設定程式。

## <a name="provide-feedback"></a>提供意見反應

您的意見反應可協助我們在保護您的環境時免受高級攻擊。 分享產品功能和評估結果的經驗和印象。

選取 [ **提供意見** 反應]，讓我們知道您的想法。