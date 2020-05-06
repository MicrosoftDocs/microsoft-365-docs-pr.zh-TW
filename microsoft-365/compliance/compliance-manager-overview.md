---
title: Microsoft 合規性管理員概述
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
search.appverid:
- MOE150
- MET150
description: 深入瞭解 microsoft 服務信任入口網站中的 Microsoft 合規性管理員（免費的工作流程型風險評估工具）。
ms.openlocfilehash: cc62e989a3ef0a40a05c5f2e34e6e15dc6e7f399
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046281"
---
# <a name="microsoft-compliance-manager-preview"></a>Microsoft 合規性管理員（預覽）

> [!IMPORTANT]
> 合規性管理員無法使用 21Vianet 運作的 Office 365、Office 365 德國、Office 365 U.S. Government Community High (GCC High)，或 Office 365 美國國防部。

**本文**內容：請閱讀本文以瞭解什麼是合規性管理員，並瞭解其主要元件。

**瞭解更新**：我們已于四月2020公開預覽發行中發佈數個更新。 請造訪[合規性管理員版本](compliance-manager-release-notes.md)資訊，以查看最近更新和已知問題。

## <a name="what-is-compliance-manager"></a>何謂合規性管理員

[Microsoft 合規性管理員（預覽）](https://servicetrust.microsoft.com/ComplianceManager)是 Microsoft 服務信任入口網站中的免費工作流程型風險評估工具，用來管理與 Microsoft 雲端服務相關的規章遵循活動。 在 365 365 Microsoft 雲端服務的共用責任模式內，合規性管理員會協助您管理法規遵從性，以協助您在 microsoft 雲端服務的共用責任模式內管理法規遵從性。

您的組織可以使用合規性管理員：
  
- 將針對您的組織適用之標準及規章的相容性自我評估，結合 Microsoft 提供給審計員和監管者的詳細規範資訊。 這些包括國際標準組織（ISO）、全國研究院（NIST）、健康保險流通與責任法案（HIPAA）、一般資料保護規定（GDPR）及其他許多人員所概括的標準和規章。
- 可讓您指派、追蹤及記錄合規性與評估相關的活動，從而協助貴組織跨小組障礙，達成您的合規性目標。
- 提供符合性分數，以協助您追蹤進度，並設定審核控制的優先順序，以協助降低組織面臨風險的風險。
- 為您提供安全的存放庫，以上傳和管理與您的合規性活動相關的證據及其他專案。
- 產生詳盡的 Microsoft Excel 報告，記錄由 Microsoft 和您組織的審計員、管制及其他法規遵從性審查程式所執行的相容性活動。

  
> [!IMPORTANT]
> 您不應將「合規性分數」和「合規性管理員」中的建議視為合規性的保證。 您可以根據法規環境評估和驗證客戶控制措施的效能。 這些服務目前是在預覽中，並受限於[線上服務條款](https://go.microsoft.com/fwlink/?linkid=2108910)中的條款及條件。 另請參閱[Microsoft 365 授權指南以取得安全性和合規性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="relationship-to-compliance-score"></a>與合規性分數的關係

[Microsoft 規範分數（預覽）](compliance-score.md)是 microsoft 365 規範中心中的一項功能，可提供組織的相容性狀況的最上層視圖。 它會計算以風險為基礎的分數，用以衡量您在完成動作方面的進展，以協助降低資料保護和法規標準的風險。 知道您的整體合規性分數可協助您的組織瞭解和管理法規遵從性。 瞭解[如何計算您的合規性分數](compliance-score-methodology.md)。

合規性管理員會與合規性分數共用相同的後端。 在這兩個工具的公開預覽階段中，合規性管理員是您管理評估和自訂控制項實施的所在位置。 深入瞭解[合規性分數和合規性管理員之間的關係](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)。

## <a name="compliance-manager-components"></a>合規性管理員元件

合規性管理員會使用多個元件，協助您進行相容性管理活動。 這些元件可共同運作，為審計員提供完整的管理工作流程和無障礙的符合性報告。

此圖表顯示合規性管理員主要元件之間的關係：

![合規性管理員第3版中的關係](../media/compliance-manager-relationships.png)

## <a name="groups"></a>群組

[群組](working-with-compliance-manager.md#groups)是容器，可讓您組織評估，並在具有相同或相關客戶管理控制措施的評估之間共用一般資訊和工作流程工作。 當同一個群組中的兩個不同評估共用客戶管理控制項時，控制項的執行詳細資料、測試及狀態會自動同步處理至群組中任何其他評估中的相同控制項。 這會為群組中的每個控制項統一所指派的動作專案，並減少重複的工作。 您也可以選擇使用群組進行組織。 依年、區域、規範標準或其他群組進行評估，以協助組織符合性工作。

## <a name="assessments"></a>評估

[評估](working-with-compliance-manager.md#assessments)是容器，可讓您根據 Microsoft 和您的組織在評估雲端服務安全性和合規性風險的組織之間的責任來組織控制。 評估可協助您執行符合標準及適用的資料保護標準、法規或法律所指定的資料保護保護措施。 其可協助您針對選取的 Microsoft 雲端服務，針對所選的工業標準來辨別您的資料保護和合規性狀況。 評估是透過對應至憑證標準的評估中所包含的控制項實施來完成。

根據預設，合規性管理員會為您的組織建立下列評估：

- Office 365 ISO 27001
- Office 365 NIST 800-53
- Office 365 GDPR

評估包含數個元件：
  
- **範圍內的服務**：每個評估適用于一組特定的 Microsoft 服務。
- **Microsoft 受管理的控制項**：針對每個雲端服務，Microsoft 會針對適用的標準和法規，針對每個雲端服務實施和管理一組符合性控制。
- **客戶管理的控制項**：當您針對每個控制項採取動作時，您的組織會執行這些控制項。
- **評估分數**：評估中客戶管理控制項的總可能分數百分比。 這可協助您追蹤指派給每個控制項的動作的實施。

## <a name="controls"></a>控制項

[控制項](working-with-compliance-manager.md#controls-and-actions)是合規性管理員中的合規性程式容器，可定義您管理符合性活動的方式。 這些控制項會組織成與對應憑證或法規之評估架構相符的控制系列。

- **控制項識別碼**：從對應的認證或法規選取的控制項名稱。
- **控制項標題**：對應之憑證或規定中的控制項識別碼的標題。
- **文章識別碼**：此欄位只適用于 GDPR 評估，並指定對應的 GDPR 文章編號。
- **描述**：對應之憑證或規定中的控制項文字。 由於著作許可權制，ISO 標準會列出相關資訊的連結。

![合規性管理員第3版中的控制項](../media/compliance-manager-controls.png)

合規性管理員、 **Microsoft 管理**的控制項、**客戶管理的**控制項和**共用管理控制項**有三種類型的控制項。

### <a name="microsoft-managed-controls"></a>Microsoft 管理的控制項

針對每個雲端服務，Microsoft 會執行並管理一組控制項，成為 Microsoft 遵循各種標準和法規的一部分。 每個控制項都提供 Microsoft 如何執行控制項的相關詳細資訊，以及該執行的方式和方式，以及由 Microsoft 和/或獨立協力廠商審計員進行測試及驗證的方式和方式。

### <a name="customer-managed-controls"></a>客戶管理的控制項

客戶管理的控制項是由您的組織管理。 您的組織負責客戶管理的控制執行，做為指定標準或法規的規範程式的一部分。 客戶管理的控制項會組織成對應的認證或法規的控制系列。 使用客戶管理的控制項，以執行 Microsoft 建議的建議動作做為您的合規性活動的一部分。 您的組織可以在每個客戶管理控制項中使用規範性指南和建議的客戶動作，以管理該控制項的實施和評估程式。

評估中的客戶管理控制項也有內建工作流程管理功能，您可以用來管理和追蹤評估完成的進度。 使用此工作流程功能，您可以：

- 指派每個控制項的動作專案
- 追蹤指派的動作專案
- 上傳控制項的實現證據
- 記錄控制項的測試及驗證
- 將交辦事項標示為已執行和測試

例如，您組織中的合規性監察官會為 IT 管理員指派交辦事項，具有執行建議動作的責任及必要許可權。 IT 系統管理員會上傳執行工作的證據（設定或原則設定的螢幕擷取畫面），並在完成時將交辦事項指派回合規性監察官。 規範監察官會評估收集的證據、測試控制項的實施，並在合規性管理員中記錄執行日期和測試結果。

### <a name="shared-management-controls"></a>共用管理控制項

共用控制項是指任何 Microsoft 和客戶都共用執行責任的控制項。 例如，與個人篩選、帳戶和密碼管理及加密相關的控制項，都需要由 Microsoft 和客戶執行動作。

## <a name="action-items"></a>動作項目

[動作專案](working-with-compliance-manager.md#controls-and-actions)會包含在內建工作流程管理功能的一部分內，以供您用來管理和追蹤評估完成的進度。

您組織中的人員可以使用合規性管理員來從其所指派的所有評估中查看客戶管理的控制項。 當使用者登入「合規性管理員」並開啟 [動作項目]**** 儀表板時，會顯示指派給他們的 [動作項目] 清單。 視使用者獲派的合規性管理員角色而定，他們可以提供實作或測試詳細資料、更新狀態，或是指派動作項目。

認證控制項通常是由一個人執行，並由另一個人測試。 例如，在最初指派給某一人員進行實施時，會將這些動作專案指派給下一個人員，以測試及上傳證據。 任何具有足夠許可權控制指派許可權的使用者都可以指派及重新指派動作專案。 這可讓您集中管理控制項指派，以及在 implementors 與測試人員之間分散的動作專案路由。

請注意，合規性分數中的**改進動作**相當於合規性管理員中的**動作專案**。

## <a name="permissions"></a>權限

合規性管理員使用以角色為基礎的存取控制權限模型。 只有獲指派使用者角色的使用者才能存取合規性管理員，而每位使用者所允許的動作會受角色類型限制。 [查看](working-with-compliance-manager.md#permissions)顯示每個許可權的允許動作的表格。

合規性管理員的入口網站管理員可以遵循下列步驟，在合規性管理員內設定其他使用者的許可權：

1. 從 **[最大**值] 下拉式功能表中，選取 [**管理員**]，然後選取 [**設定**]。
2. 從這裡，選取您要指派的角色，然後新增您要指派給該角色的員工。 然後，使用者將能夠執行某些動作。

[在 Azure Active Directory （AZURE AD）中被指派全域讀取器角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)的使用者，具有存取合規性管理員的唯讀許可權。 不過，他們無法在合規性管理員內編輯資料或執行任何動作。

不再有預設**來賓存取**角色。 每個使用者都必須獲指派角色，才能在合規性管理員中存取及作業。
  
## <a name="manage-evidence"></a>管理證據

合規性管理員可以在測試及驗證客戶管理的控制項時，儲存您的執行工作證據。 證據包括檔、試算表、螢幕擷取畫面、圖像、腳本、腳本輸出檔及其他檔案。 合規性管理員也會自動接收遙測，並為與安全分數整合的動作專案建立證據記錄。 任何上傳到合規性管理員的資料，都是儲存在 Microsoft Cloud Storage sites 的美國地區。 此資料會複製到位於東南亞和西歐的 Azure 地區。

## <a name="templates"></a>範本

合規性管理員提供預先設定的[範本](working-with-compliance-manager.md#templates)進行評估，並可讓您針對符合性需求為客戶管理的控制項建立自訂的範本。 新的範本是透過從 Excel 檔案中匯入控制項資訊來建立，或是您可以從現有範本的複本建立範本。

合規性管理員隨附的預先設定的範本包括：

1. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
2. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
3. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
4. [NIST 800-53 Rev 4](https://go.microsoft.com/fwlink/?linkid=2109075)
5. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
6. [NIST Cybersecurity Framework （CSF）](https://go.microsoft.com/fwlink/?linkid=2108868)
7. [雲端安全性同盟（CSA） Cloud Controls 矩陣（CCM）3.0。1](https://go.microsoft.com/fwlink/?linkid=2109076)
8. [聯邦金融機構檢查委員會（FFIEC）資訊安全性手冊](https://go.microsoft.com/fwlink/?linkid=2109077) 
9. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / 高[科技](https://go.microsoft.com/fwlink/?linkid=2109079)
10. [FedRAMP 適中](https://go.microsoft.com/fwlink/?linkid=2108869)
11. [歐盟 GDPR](https://go.microsoft.com/fwlink/?linkid=2108870)
12. [加州消費者隱私權法案（CCPA）](https://go.microsoft.com/fwlink/?linkid=2108871) （預覽）
13. [IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [澳大利亞政府版 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) （預覽）
14. [Microsoft 365 資料保護基準](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)

## <a name="secure-score-integration"></a>安全分數整合

合規性管理員已與[Microsoft 安全評分](../security/mtp/microsoft-secure-score.md)整合，以自動將安全分數信用用於同步處理動作專案的合規性分數。 這可為個別動作專案或全域動作進行設定，並提供安全分數的更新。

例如，您有在組織中啟用 Azure 版權管理的安全相關需求，也適用于與規範相關的動作專案。 當 Azure Rights Management 以安全分數方式啟動並處理時，合規性管理員會收到更新通知，且措施專案的分數會自動更新為完成信用。

## <a name="ready-to-get-started"></a>準備好開始使用了嗎？

開始[使用合規性管理員](working-with-compliance-manager.md)來管理組織的法規遵從性活動。

## <a name="resources"></a>資源

- [互動式指南：使用合規性管理員評估及增強您的資料保護控制](https://content.cloudguides.com/guides/Compliance%20Manager)
- [Microsoft 安全性、隱私權和規範技術社區](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/ct-p/SecurityPrivacyCompliance)