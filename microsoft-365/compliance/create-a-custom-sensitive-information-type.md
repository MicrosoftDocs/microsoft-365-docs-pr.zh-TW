---
title: 在安全性與合規性中心建立自訂敏感性資訊類型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在安全性與合規性中心的圖形使用者介面中建立、修改、移除及測試 DLP 的自訂敏感性資訊類型。
ms.openlocfilehash: 7f7c4c787bff6fa9d4c644b5640d05b9320686ed
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596210"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a>在安全性與合規性中心建立自訂敏感性資訊類型

## <a name="summary"></a>摘要

閱讀本文，在安全性與合規性中心建立[自訂敏感性資訊類型](custom-sensitive-info-types.md) ([https://protection.office.com](https://protection.office.com))。 透過使用此方法，您建立的自訂敏感性資訊類型會新增到名為 `Microsoft.SCCManaged.CustomRulePack` 的規則套件。

您也可以使用 PowerShell 和 Exact Data Match 功能建立自訂敏感性資訊類型。 若要深入了解這些方法，請參閱：
- [在安全性與合規性中心 PowerShell 中建立自訂敏感性資訊類型](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [使用 Exact Data Match (EDM) 建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="before-you-begin"></a>開始之前...

> [!NOTE]
> 您必須具備全域管理員或合規性系統管理員的權限，才能透過 UI 建立、測試及部署自訂的敏感性資訊類型。 請參閱 Office 365 中的[關於系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)。

- 您的組織必須擁有包括資料外洩防護 (DLP) 的訂用帳戶，例如 Office 365 企業版。 請參閱[郵件原則及符合性](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)。 

- 自訂機密資訊類型需要熟悉規則運算式 (RegEx)。如需用於處理文字之 Boost.RegEx (先前稱為 RegEx++) 引擎的詳細資訊，請參閱 [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)。

  Microsoft 客戶服務及支援無法協助您建立自訂分類或規則運算式模式。 支援工程師可以提供有限的功能支援，例如，基於測試目的提供範例規則運算式模式，或協助對未如預期般觸發的現有規則運算式模式進行疑難排解，但無法保證任何自訂內容比對開發作業將符合您的需求或義務。

- DLP 會使用搜尋檢索器識別及分類 SharePoint Online 和商務用 OneDrive 中網站中的敏感性資訊。 若要在所有現有內容中識別您的新自訂敏感性資訊類型，必須將內容重新編目。 內容會根據排程進行編目，但您可以手動重新編目網站集合、清單或文件庫的內容。 如需詳細資訊，請參閱[手動要求網站、文件庫或清單進行編目和重新建立索引](https://docs.microsoft.com/sharepoint/crawl-site-content)。

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a>在安全性與合規性中心建立自訂機密資訊類型

在安全性與合規性中心，移至 [**分類**] \> [**機密資訊類型**]，然後按一下 [**建立**]。

這些設定不言而喻，並會在精靈的關聯頁面上加以說明：

- **名稱**

- **描述**

- **近似值**

- **信賴等級**

- **主要模式元素** (關鍵字、規則運算式或字典)

- 選用的**支援模式元素** (關鍵字、規則運算式或字典) 及其對應**最低成本**值。

以下是案例：您想要一個自訂機密資訊類型，偵測內容中 9 位數的員工編號，以及關鍵字 "employee"、"ID" 及 "badge"。若要建立此自訂機密資訊類型，請執行下列步驟：

1. 在安全性與合規性中心，移至 [**分類**] \> [**機密資訊類型**]，然後按一下 [**建立**]。

    ![機密資訊類型及建立按鈕的位置](media/scc-cust-sens-info-type-new.png)

2. 在開啟的 [選擇名稱和描述]**** 頁面中，輸入下列值：

  - **名稱**：員工識別碼。

  - **描述**：偵測九位數 Contoso 員工編號。

    ![名稱與描述頁面](media/scc-cust-sens-info-type-new-name-desc.png)

    完成後，按 [下一步]****。

3. 在 [比對需求]**** 頁面中，按一下 [新增元素]**** 來設定下列設定：

    - **偵測包含下列項目的內容**：
 
      a 按一下 [其中任一個]****，然後選取 [規則運算式]****。

      b. 在規則運算式方塊中，輸入 `(\s)(\d{9})(\s)` (以空格括住九位數的號碼)。
  
    - **支援項目**：按一下 [新增支援項目]****，然後選取 [包含此關鍵字清單]****。

    - 在出現的 [包含此關鍵字清單]**** 區域中，設定下列設定：

      - **關鍵字清單**：輸入下列值：員工、識別碼、徽章。

      - **最小計數**：保留預設值 1。

    - 保留預設**信賴等級**值 60。 

    - 保留預設**字元近似值** 300。

    ![比對要求頁面](media/scc-cust-sens-info-type-new-reqs.png)

    完成後，按 [下一步]****。

4. 在開啟的 [檢閱並完成]**** 頁面上，檢閱設定並按一下 [完成]****。

    ![檢閱並完成頁面](media/scc-cust-sens-info-type-new-review.png)

5. 下一個頁面鼓勵您藉由按一下 [是]****，測試新的自訂機密資訊類型。如需詳細資訊，請參閱[在安全性與合規性中心測試自訂機密資訊類型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。如需稍後再測試規則，請按一下 [否]****。

    ![測試建議頁面](media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已成功建立新的機密資訊類型，請執行下列任一步驟：

  - 移至 [分類]**** \> [機密資訊類型]****，並確認已列出新的自訂機密資訊類型。

  - 測試新的自訂機密資訊類型。如需詳細資訊，請參閱[在安全性與合規性中心測試自訂機密資訊類型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a>在安全性與合規性中心修改自訂機密資訊類型

**附註**：
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- 您只能修改自訂機密資訊類型，不能修改內建的機密資訊類型。但您可以使用 PowerShell 來匯出內建的自訂機密資訊類型、自訂它們，並將其匯入為自訂機密資訊類型。如需詳細資訊，請參閱[自訂內建的機密資訊類型](customize-a-built-in-sensitive-information-type.md)。

- 您只能修改在 UI 中建立的自訂機密資訊類型。如果您使用 [PowerShell 程序](create-a-custom-sensitive-information-type-in-scc-powershell.md)匯入自訂的機密資訊類型規則套件，則會收到錯誤訊息。

在安全性與合規性中心，移至 [分類]**** \> [機密資訊類型]****，選取您想要修改的自訂機密資訊類型，然後按一下 [編輯]****。

  ![機密資訊類型及編輯按鈕的位置](media/scc-cust-sens-info-type-edit.png)

這裡提供與您在安全性與合規性中心建立自訂機密資訊類型時相同的選項。如需詳細資訊，請參閱[在安全性與合規性中心建立自訂機密資訊類型](#create-custom-sensitive-information-types-in-the-security--compliance-center)。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已成功修改機密資訊類型，請執行下列任一步驟：

  - 移至 [分類]**** \> [機密資訊類型]****，以驗證已修改之自訂機密資訊類型的內容。 

  - 測試已修改的自訂機密資訊類型。如需詳細資訊，請參閱[在安全性與合規性中心測試自訂機密資訊類型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a>移除安全性與合規性中心的自訂機密資訊類型 

**附註**：

- 您只能移除自訂機密資訊類型，不能移除內建的機密資訊類型。

- 在您移除自訂機密資訊類型之前，請確認沒有 DLP 原則或 Exchange 郵件流程規則 (也稱為傳輸規則) 仍參照機密資訊類型。

1. 在安全性與合規性中心，移至 [分類]**** \> [機密資訊類型]****，然後選取一或多個您想要移除的自訂機密資訊類型。

2. 在開啟的飛出視窗中，按一下 [刪除]**** (或 [刪除機密資訊類型]****，如果您已選取多個的話)。

    ![機密資訊類型及刪除按鈕的位置](media/scc-cust-sens-info-type-delete.png)

3. 在出現的警告訊息中，按一下 [是]****。

### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認您已成功移除自訂機密資訊類型，請移至 [分類]**** \> [機密資訊類型]****，以確認不再列出自訂機密資訊類型。

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a>在安全性與合規性中心測試自訂機密資訊類型

1. 在安全性與合規性中心，移至 [分類]**** \> [機密資訊類型]****。

2. 選取要測試的一或多個自訂機密資訊類型。在開啟的飛出視窗中，按一下 [測試類型]**** (或 [測試機密資訊類型]****，如果您已選取多個的話)。

    ![機密資訊類型及測試按鈕的位置](media/scc-cust-sens-info-type-test.png)

3. 在開啟的 [上傳檔案進行測試]**** 頁面上，拖放檔案或按一下 [瀏覽]**** 並選取檔案，來上傳要測試的文件。

    ![上傳檔案進行測試頁面](media/scc-cust-sens-info-type-test-upload.png)

4. 按一下 [測試]**** 按鈕，來測試文件以在檔案中進行模式比對。

5. 在 [比對結果]**** 頁面上，按一下 [完成]****。

    ![比對結果](media/scc-cust-sens-info-type-test-results.png)
