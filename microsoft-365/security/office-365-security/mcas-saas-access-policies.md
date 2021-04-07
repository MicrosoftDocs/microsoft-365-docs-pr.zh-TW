---
title: 建議的 Microsoft Cloud App Security 原則 SaaS app-Microsoft 365 Enterprise |Microsoft 檔
description: 說明整合 Microsoft Cloud App Security 的建議原則。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: Admin
ms.author: bcarter
ms.date: 03/22/2021
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 61509c88ea2289509abd5ec7b6c0dcd54395d5f0
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599968"
---
# <a name="recommended-microsoft-cloud-app-security-policies-for-saas-apps"></a>SaaS 應用程式的建議 Microsoft Cloud App 安全性原則
Microsoft Cloud App Security 組建于 Azure AD 條件式存取原則上，以啟用即時監控，並使用 SaaS 的應用程式（例如封鎖下載、上傳、複製及貼上）來控制細微動作。 此功能會將安全性新增至具有固有風險的會話，例如從未受管理的裝置存取公司資源或來賓使用者。

Microsoft Cloud App Security 也會以 Microsoft 資訊保護為內部整合，提供即時內容檢查，以根據敏感資訊類型和敏感度標籤尋找敏感性資料，並採取適當的動作。

本指南包含下列案例的建議：

- 將 SaaS 的應用程式引入 IT 管理
- 針對特定的 SaaS 應用程式調整保護
- 設定資料遺失防護 (DLP) 以協助遵守資料保護法規

## <a name="bring-saas-apps-into-it-management"></a>將 SaaS 的應用程式引入 IT 管理

使用 Microsoft Cloud App Security 管理 SaaS 應用程式的第一步，是探索這些應用程式，然後將其新增至您的 Azure AD 租使用者。 如果您需要探索協助，請參閱 [探索和管理您網路中的 SaaS 應用程式](/cloud-app-security/tutorial-shadow-it)。 在您探索應用程式之後， [將它們新增至您的 AZURE AD 租](/azure/active-directory/manage-apps/add-application-portal)使用者。

您可以執行下列動作來開始管理：

1. 首先，在 Azure AD 中建立新的條件式存取原則，並將其設定為「使用條件式存取應用程式控制」。 這會將要求重新導向至 Cloud App Security。 您可以建立一個原則，並將所有 SaaS 應用程式新增至此原則。
1. 接下來，在 Cloud App Security 中建立會話原則。 針對每個您想要套用的控制項建立一個原則。

SaaS 應用程式的許可權通常是以業務存取應用程式的需求為基礎。 這些許可權可以是高度動態的。 使用雲端 App 安全性策略可確保對應用程式資料的保護，不論是否將使用者指派至與基線、敏感或高度管制保護相關聯的 Azure AD 群組。

為了保護您的 SaaS 應用程式集合中的資料，下列圖表說明必要的 Azure AD 條件式存取原則，以及您可以在 Cloud App Security 中建立的建議原則。 在此範例中，Cloud App Security 中建立的原則會套用至所有所管理的 SaaS 應用程式。 這些設計目的是根據裝置是否受管理，以及已套用至檔案的靈敏度標籤，套用適當的控制項。

![在 Cloud App Security 中管理 SaaS 應用程式的原則](../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png)

下表列出您必須在 Azure AD 中建立的新條件式存取原則。

|保護層級|原則|其他資訊|
|---|---|---|
|所有保護層級|[在 Cloud App Security 中使用條件式存取應用程式控制](/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad)|這會將您的 IdP 設定 (Azure AD) ，以與 Cloud App Security 搭配使用。|
||||

下表列出您可以建立的範例原則，以保護所有的 SaaS 應用程式。 請務必評估您自己的商務、安全性和合規性目標，然後建立可為您的環境提供最適當保護的原則。

|保護層級|原則|
|---|---|
|基準|監視非管理裝置的流量 <p> 從未受管理的裝置新增檔下載保護|
|敏感性|封鎖以敏感或分類方式從未受管理的裝置下載的檔案 (這只會提供瀏覽器的存取) |
|高管制|封鎖所有裝置中標示為 [已分類的檔案] (這只會提供瀏覽器的存取) |
|||

如需設定條件式存取應用程式控制的端對端指示，請參閱 [部署特色應用程式的條件式存取應用程式控制](/cloud-app-security/proxy-deployment-aad)。 本文將引導您完成在 Azure AD 中建立必要的條件式存取原則，並測試您的 SaaS 應用程式。

如需詳細資訊，請參閱 [使用 Microsoft Cloud App Security 條件式 Access 應用程式控制保護應用](/cloud-app-security/proxy-intro-aad)程式。

## <a name="tune-protection-for-specific-saas-apps"></a>針對特定的 SaaS 應用程式調整保護

您可能想要將其他監控和控制套用至環境中的特定 SaaS 應用程式。 Cloud App Security 可讓您完成此作業。 例如，如果您環境中經常使用像像這樣的應用程式，就可以套用其他控制項。 或者，如果您的法律或財務部門是針對敏感的商務資料使用特定的 SaaS 應用程式，您可以針對這些應用程式設定額外的保護。

例如，您可以使用下列內建的反常狀況偵測原則範本，保護 Box 環境：

- 匿名 IP 位址的活動
- 非常見國家的活動
- 可疑 IP 位址的活動
- 不可能的移動
- 終止的使用者 (所執行的活動需要 AAD 視為 IdP) 
- 惡意程式碼偵測
- 多次失敗的登入嘗試
- 勒索軟體活動
- 危險的 Oauth 應用程式
- 不尋常的檔案共用活動

這些都是範例。 其他原則範本會定期新增。 如需如何對特定 app 套用其他保護的範例，請參閱 [保護連線的應用程式](/cloud-app-security/protect-connected-apps)。

[Cloud App Security 如何協助您保護 box 環境](/cloud-app-security/protect-box) 示範的控制項類型可協助您保護 box 中的商務資料，以及其他具有敏感性資料的應用程式。

## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a>設定資料遺失防護 (DLP) 以協助遵守資料保護法規

Cloud App Security 可能是設定規范保護規範的一個極具價值的工具。 在此情況下，您可以建立特定的原則來尋找法規套用的特定資料，並設定每個原則採取適當的動作。

下列圖解和 table 提供一些原則範例，可設定這些原則，以協助遵循一般資料保護法規 (GDPR) 。 在這些範例中，原則會尋找特定的資料。 根據資料的靈敏度，每個原則都設定為採取適當的動作。

![資料遺失防護範例 Cloud App Security 原則](../../media/microsoft-365-policies-configurations/mcas-dlp.png)

|保護層級|範例原則|
|---|---|
|基準|當包含此機密資訊類型的檔案 ( 「信用卡號碼」 ) 會在組織外共用時發出警示 <p> >封鎖包含此機密資訊類型的檔案下載 ( "信用卡號碼" ) 非管理裝置|
|敏感性|保護包含此機密資訊類型的檔案下載 ( 「信用卡號碼」 ) 受管理的裝置 <p> 封鎖包含此機密資訊類型的檔案下載 ( 「信用卡號碼」 ) 非受管理的裝置 <p> 當具有下列標籤的檔案上傳至 OneDrive for Business or Box (客戶資料，人力資源：薪資資料、人力資源、員工資料) |
|高管制|當具有此標籤的檔案 ( 「高分類」 ) 下載到受管理的裝置時發出警示 <p> 封鎖此標籤的下載檔案 ( 「高分類」 ) 非受管理裝置|
|||

## <a name="next-steps"></a>後續步驟

如需使用 Cloud App Security 的詳細資訊，請參閱 [Microsoft Cloud App security 檔](//cloud-app-security/)。
