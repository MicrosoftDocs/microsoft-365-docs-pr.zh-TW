---
title: Microsoft Compliance Manager 概觀
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager 是在 Microsoft 服務信任入口網站中的可用工作流程為基礎的風險評估工具。 合規性管理員可讓您追蹤、 指派及驗證與 Microsoft 雲端服務相關的法規合規性活動。
ms.openlocfilehash: 723f1372b9214367985cc6b42c41e94c3f201b89
ms.sourcegitcommit: 544b10cc3abe04a47438085d51c4250c9238f76f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "38685384"
---
# <a name="microsoft-compliance-manager-preview"></a>Microsoft Compliance Manager （預覽）

> [!IMPORTANT]
> 合規性管理員無法使用 21Vianet 運作的 Office 365、Office 365 德國、Office 365 U.S. Government Community High (GCC High)，或 Office 365 美國國防部。

[Microsoft Compliance Manager （預覽）](https://servicetrust.microsoft.com/ComplianceManager)是與 Microsoft 雲端服務相關的屬性可讓您追蹤、 指派，並確認法規合規性活動可用工作流程為基礎的風險評定工具。 您的 Microsoft 365 的一部分、 Office 365 或 Azure Active Directory 訂閱，合規性管理員可協助您管理內共同分擔 Microsoft 雲端服務的法規合規性。 合規性管理員提供集中式的儀表板檢視標準、 法規和控制項實作詳細資料和 Microsoft 服務評估的測試結果。 它還包含可讓您管理自訂控制項實作與追蹤特定給貴組織的合規性的工具。

使用合規性管理員中，您的組織可以：
  
- 結合 Microsoft 提供給稽核者及管理者與您合規性自我評估其雲端服務相關的標準與法規適用，為您的組織的合規性詳細的資訊。 這些包括標準與法規所述的國際標準組織 (ISO)、 National Institute of Standards 和技術 (NIST)、 健康保險流通與責任法案 (HIPAA)，一般資料保護規定 (GDPR) 和其他許多。
- 可讓您指派、 追蹤及記錄合規性與評估相關的活動，可協助貴組織跨小組障礙，達成您的合規性目標。
- 提供可協助您追蹤進度，並排定優先順序稽核控制項，可協助降低您的組織暴露於風險合規性分數。
- 提供安全存放庫，為您要上傳並管理辨識項，以及您合規性活動相關的其他成品。
- 產生豐富的 Microsoft Excel 報告執行由 Microsoft 和您的組織稽核員、 管理者，以及其他規範檢閱者的文件合規性活動。

> [!NOTE]
> 提供合規性管理員中的客戶動作是建議;它是由您的組織來評估在其各自的法規環境之前實作這些建議的有效性。 找到合規性管理員中的建議不應該解譯成保證郵件可以合規性。

## <a name="compliance-manager-relationships"></a>合規性管理員中的關聯

合規性管理員中使用數個元件協助您符合您的合規性管理活動。 這些元件可以搭配使用，以提供完整的管理工作流程及簡明的合規性的稽核員 」 報告。

此圖顯示的合規性管理員中的主要元件之間的關係：

![合規性管理員第 3 版中的關聯性](media/compliance-manager-relationships.png)

## <a name="groups"></a>群組

[群組](working-with-compliance-manager.md#groups)是可讓您組織的評估及共用一般的資訊和之間具有相同或相關客戶管理控制項的 「 評估 」 的工作流程工作的容器。 當兩個不同的 「 評估 」 在相同的群組共用客戶管理控制項時，完成實作詳細資料、 測試和控制項的狀態的自動同步處理至群組中的任何其他評估中的同一個控制項。 此群組間統一指派的動作項目，每個控制項，並減少複製工作。 您也可以選擇要用來組織的群組。 評估年、 區域、 合規性標準，或其他群組，以協助您組織您的合規性工作。

## <a name="assessments"></a>「 評估 」

[「 評估 」](working-with-compliance-manager.md#assessments)是可讓您組織的責任 Microsoft 和您的組織評估雲端服務安全性與合規性風險之間共用基礎的控制項的容器。 評估可協助您實作合規性標準和適用的資料保護標準、 法令或法律所指定的資料保護保護措施。 它們可協助您辨識針對選取的業界標準的所選的 Microsoft 雲端服務，您的資料保護和合規性狀態。 評估完成所實作的評估中包含對應至標準憑證的控制項。

根據預設，合規性管理員會建立組織的下列 「 評估 」:

- Office 365 ISO 27001
- Office 365 NIST 800-53
- Office 365 GDPR

評估包含數個元件：
  
- **範圍內的服務**： 每個評估適用於一組特定的 Microsoft 服務。
- **Microsoft 管理控制措施**： 每個雲端服務，Microsoft 會實作和管理一組適用的標準與法規符合性控制項。
- **客戶管理控制**： 這是由您的組織實作時採取動作的每個控制項, 的控制項的集合。
- **評估分數**： 評估中的 [客戶管理控制措施的總可能分數的百分比。 這可協助您追蹤實作的指派給每個控制項的動作。

## <a name="controls"></a>控制項

[控制項](working-with-compliance-manager.md#controls-and-actions)是定義您要如何管理合規性活動的合規性程序容器合規性管理員中。 這些控制項分為對應認證或規定的評估結構與對齊的控制項系列。

- **控制項 ID**： 從對應認證或規定所選控制項的名稱。
- **控制項標題**： 所對應憑證或規定的標題的控制項識別碼。
- **發行項識別碼**： 此欄位僅適用於 GDPR 評估，並指定對應的 GDPR 文章編號。
- **描述**： 從對應認證或規定的控制項的文字。 由於著作權限制的相關資訊的連結列 ISO 標準。

![合規性管理員第 3 版中的控制項](media/compliance-manager-controls.png)

有三種類型的合規性管理員中， **Microsoft 管理控制措施**，**客戶管理控制措施**和**共用管理控制項**中的控制項

### <a name="microsoft-managed-controls"></a>Microsoft 管理控制措施

每個雲端服務，Microsoft 實作及管理 Microsoft 與各種標準與法規的合規性的一部分的一組控制項。 每個控制項提供 Microsoft 如何實作控制項，及如何及何時該實作已測試及驗證由 Microsoft 和/或獨立第三方稽核的詳細資訊。

### <a name="customer-managed-controls"></a>客戶管理控制措施

這是由您的組織管理控制項的集合。 您的組織負責客戶管理控制項實作特定的標準或法規合規性程序的一部分。 客戶管理控制措施分成控制項系列的對應認證或規定。 使用客戶管理控制措施來實作建議的動作，microsoft 建議您合規性活動的一部分。 您的組織可以使用管理的實作和評估程序，為該控制項，每個客戶管理控制項中的規定指導和建議的客戶動作。

客戶管理控制項評估中的也有內建工作流程管理功能，可用於管理與追蹤您向評估完成的進度。 此工作流程功能，您可以進行下列作業：

- 指派每個控制項動作項目
- 追蹤指派動作項目
- 上傳實作的控制項的辨識項
- 文件的測試和驗證控制項
- 動作項目標示為已實作和測試

例如，法務人員在組織中指派動作項目 IT 系統管理員與責任和執行建議的動作的必要權限。 IT 系統管理員上傳證據的實作工作 （設定] 或 [原則設定的螢幕擷取畫面），並指派動作項目回至法務完成。 法務評估收集的證據、 測試實作的控制項，並記錄合規性管理員中實作日期和測試結果。

### <a name="shared-management-controls"></a>共用管理控制

共用的控制項是指 Microsoft 與客戶共用實作的責任的任意控制項。 例如，過濾的人員、 帳戶及密碼管理和加密相關的控制項需要由 Microsoft 和客戶的動作。

## <a name="action-items"></a>動作項目

[動作項目](working-with-compliance-manager.md#controls-and-actions)會包含在客戶管理控制措施，為您可用來管理及追蹤進度評估完成向內建工作流程管理功能的一部分。

您組織中的人員可以使用合規性管理員來檢閱從其已指派給他們的所有評定的客戶管理控制項。 當使用者登入「合規性管理員」並開啟 [動作項目]**** 儀表板時，會顯示指派給他們的 [動作項目] 清單。 視使用者獲派的合規性管理員角色而定，他們可以提供實作或測試詳細資料、更新狀態，或是指派動作項目。

憑證控制項通常是由一位人員實作和測試另一個。 例如，初始指派給實作一個人的動作項目都完成之後，動作項目指派給下一個人來測試及上傳證據。 具有足夠的權限控制工作分派的任何使用者可以指派，並重新指派動作項目。 這可讓控制項的工作分派的中央管理，而且分散 implementors 和測試人員之間路由的動作項目。

## <a name="permissions"></a>權限

合規性管理員使用以角色為基礎的存取控制權限模型。 只有獲指派使用者角色的使用者才能存取合規性管理員，而每位使用者所允許的動作會受角色類型限制。 [檢視表格](working-with-compliance-manager.md#permissions)顯示每個權限所允許的動作。

入口網站管理員合規性管理員可以設定其他使用者在合規性管理員中的權限，遵循下列步驟：

1. 從頂端**多個**下拉式] 功能表中，選取 [**系統**]，然後**設定**]。
2. 從這裡開始，選取您想要指派，然後新增您想要指派給該角色的員工的角色。 使用者能執行某些動作。

此外，[在 Azure Active Directory (Azure AD) 中的全域讀者角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)所指派的使用者擁有存取合規性管理員中; 的唯讀權限不過他們無法編輯資料，或執行合規性管理員中的任何動作。

請注意，已不再有預設的**來賓存取**角色。 每個使用者都必須獲指派角色，才能在合規性管理員中存取及作業。
  
## <a name="manage-evidence"></a>管理辨識項

合規性管理員中可以儲存辨識您實作工作執行的客戶管理控制措施測試和驗證。 辨識項包含文件、 試算表、 螢幕擷取畫面，影像、 指令碼、 指令碼輸出檔及其他檔案。 合規性管理員也會自動接收遙測，並建立辨識項記錄的動作項目與安全分數整合。 任何以作為證據到合規性管理員上傳的資料會儲存在美國境內 Microsoft Cloud Storage 網站上。 此資料會複寫跨 Azure 位於東南亞及西歐的區域。

## <a name="templates"></a>範本

合規性管理員評估提供預先設定的[範本](working-with-compliance-manager.md#templates)，並可讓您建立的客戶管理控制您的法務遵循需求的自訂的範本。 新範本所建立的控制項資訊從檔案匯入 Excel，或者您可以從現有範本的複本建立範本。

是包含與合規性管理員中預先設定的範本：

1. [ISO 27001: 2013](https://go.microsoft.com/fwlink/?linkid=2109073)
2. [ISO 27018: 2014](https://go.microsoft.com/fwlink/?linkid=2109074)
3. [NIST 800-53 修訂 4](https://go.microsoft.com/fwlink/?linkid=2109075)
4. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
5. [NIST Cybersecurity Framework (CSF)](https://go.microsoft.com/fwlink/?linkid=2108868)
6. [雲端安全聯盟 (CSA) 雲端控制項矩陣 (CCM) 3.0.1](https://go.microsoft.com/fwlink/?linkid=2109076)
8. [聯邦金融機構檢查委員會 (FFIEC) 的資訊安全性手冊](https://go.microsoft.com/fwlink/?linkid=2109077) 
8. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)
9. [FedRAMP 中度](https://go.microsoft.com/fwlink/?linkid=2108869)
10. [歐盟 GDPR](https://go.microsoft.com/fwlink/?linkid=2108870)
11. [加州消費者隱私權法案 (CCPA)-預覽](https://go.microsoft.com/fwlink/?linkid=2108871)
12. [Microsoft 365 的資料保護基準](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)

## <a name="compliance-score"></a>合規性分數

[Microsoft 合規性分數 （預覽）](compliance-score.md)是協助您了解貴組織的合規性狀態 Microsoft 365 合規性中心中的功能。 它會計算測量中完成協助減少資料保護和法規的標準周圍的風險的動作您進行風險分數。 了解整體合規性分數可協助您了解並管理合規性的組織。 了解[您的合規性分數的計算方式](compliance-score-methodology.md)。
  
> [!IMPORTANT]
> 合規性分數不 express 與任何特定的標準或法規的組織符合性絕對量值。 它來表示您要採用的個人資料和個人隱私權降低風險的控制項的程度。 您已符合標準或法規，和合規性分數不應該解譯成保證郵件可以以任何方法，可確保沒有任何服務。

## <a name="secure-score-integration"></a>安全分數整合

[Microsoft 安全分數](../security/mtp/microsoft-secure-score.md)的同步處理的動作項目，自動將安全分數信用套用至合規性分數被整合合規性管理員。 這是全域，可設定個別的動作項目或所有的動作，並從安全分數提供更新。

例如，您有相關的安全性需求來規範相關動作項目也適用於您組織中啟用 Azure Rights Management。 時啟動 Azure Rights Management 和處理安全分數，合規性管理員接收通知的更新，並完成信用自動更新的分數動作項目。

## <a name="ready-to-get-started"></a>準備好要開始了嗎？

開始[使用與合規性管理員](working-with-compliance-manager.md)管理組織的法規合規性活動。

## <a name="resources"></a>資源

- [互動式指南： 評估和增強資料保護控制項與合規性管理員](https://content.cloudguides.com/guides/Compliance%20Manager)
- [Microsoft 安全性、 隱私權和規範技術社群](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/ct-p/SecurityPrivacyCompliance)
