---
title: Microsoft 規範分數設定
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
search.appverid:
- MOE150
- MET150
description: 瞭解如何設定及開始使用 Microsoft 合規性分數，以協助簡化及自動化風險評估。
ms.openlocfilehash: 4ccd89647540aeda8ba6253f6e5eefab1dc81791
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632388"
---
# <a name="microsoft-compliance-score-preview-setup"></a>Microsoft 規範分數（預覽）設定

## <a name="before-you-begin"></a>開始之前

您組織的 Microsoft 365 全域管理員可能會是第一個存取合規性分數的使用者。 我們建議全域管理員登入，並設定第一次的訪問合規性分數時所述的使用者權限。

## <a name="sign-in"></a>登入

1. 請移至[microsoft 365 規範中心](https://compliance.microsoft.com/)，並使用您的 Microsoft 365 全域管理員帳戶登**入**。
2. 在左導覽窗格上選取 [**合規性分數**]。 您應該會看到您[的評分分數儀表板與您的分數](#understand-the-compliance-score-dashboard)。

存取合規性分數的直接連結為： [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore)。

## <a name="set-user-permissions-and-assign-roles"></a>設定使用者權限並指派角色

合規性分數使用以角色為基礎的存取控制（RBAC）許可權模型。 只有獲指派角色的使用者才可存取合規性分數，而且每個使用者所允許的動作都會受到角色類型的限制。

### <a name="where-to-set-permissions"></a>設定許可權的位置

您組織的全域管理員可以設定 Microsoft 365 規範中心或 Azure Active Directory （Azure AD）中的使用者許可權。 在這兩個位置中設定角色後，使用者即可存取合規性分數及合規性管理員。

請注意，現有的相容性管理員角色**不會**轉移到合規性分數。 如果您在合規性管理員中擁有角色，且其符合性分數是新的，則您的合規性管理員角色不會授與您對合規性分數的存取。 您的全域系統管理員必須在 Microsoft 365 規範中心或 Azure AD 中為您設定許可權和角色，以便您可以存取合規性分數。

### <a name="role-types"></a>角色類型

下表顯示每個 Microsoft 365 規範中心角色如何對應至現有的合規性管理員角色，以及每個角色所允許的功能。


| 使用者可以： | Microsoft 365 規範中心角色 | 合規性管理員角色 | 
| :------------- | :-------------: | :------------: |
| **讀取但不編輯資料**| Azure AD 全域讀取器  | Azure AD 全域讀取器 | 
| **讀取但不編輯資料**| 安全性讀取者 | 合規性管理員讀者  | 
| **編輯資料**| 合規性管理員 | 合規性管理員參與者 | 
| **編輯測試結果**| 合規性管理員 | 合規性管理員 assessor | 
| **管理評估、範本及租使用者資料**| 合規性管理員<br>合規性資料管理員<br>安全性系統管理員 | 合規性管理員 | 
| **指派使用者**| 全域管理員 | 入口網站管理員 | 

> [!NOTE]
> 當您從相容性分數移至合規性管理員以完成工作時（例如，若要管理評估），您的瀏覽器會開啟新的索引標籤，並顯示對話方塊。 在標頭為「已是 Microsoft cloud services 客戶」的上方區段中？ 登入您的帳戶「選取登**入**以存取合規性管理員;您不需要重新輸入您的認證。

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a>如何在 Microsoft 365 規範中心設定許可權和角色

若要設定 Microsoft 365 規範中心的許可權：

1. 請移至[Microsoft 365 規範中心](https://compliance.microsoft.com)，並以您的全域系統管理員帳戶登入。
2. 在左功能窗格上選取 [**許可權**]。 您可以從這裡查看角色及指派許可權。

## <a name="configure-automatic-secure-score-updates"></a>設定自動安全分數更新

根據預設，所有新租使用者皆已開啟「[安全分數](../security/mtp/microsoft-secure-score.md)自動更新」。 所有由安全評分監控的動作，會自動更新合規性分數中相同動作的狀態。

您的全域系統管理員可以管理此設定，以關閉所有動作的自動更新，或個別設定動作的更新。

在公開預覽期間，您需要移至 Microsoft 服務信任入口網站（其中的合規性管理員所在）以管理安全分數更新。

若要管理自動安全分數更新，請遵循下列步驟：

1. 使用您的全域系統管理員帳戶登入[服務信任入口網站](https://servicetrust.microsoft.com)。

2. 在服務信任入口網站頂端功能表列上，按一下 [**其他**] 下的 [系統**管理員**]，然後選擇 [**設定**]。

3. 在 [**安全分數**] 索引標籤中，選取對應的按鈕來**開啟所有動作**、**關閉所有動作**，或**設定每個動作。**

如果您選擇 [**依動作設定]，請**採取下列額外步驟，為個別動作開啟安全分數更新：

4. 從上方功能表中選取 [**合規性管理員**] （不要選取 [合規性管理員（經典）]，這是一種舊版產品）。

5. 在螢幕的右上角選取 [**租使用者管理**]。

6. 在 [**客戶動作**] 窗格上，在 [**受影響的動作**] 欄下，以省略號（**...**）尋找您的預定動作。 按一下省略號，然後選取 [**編輯]。**

7. 將**安全分數連續更新**切換開關切換為 [**開啟]。**

8. 選取 [**儲存]。** 安全分數連續監控現在已開啟該動作。

**附注：** 只有全域系統管理員才能開啟或關閉所有動作的自動更新。 合規性管理員可以為個別動作開啟自動更新，但不能為全域動作開啟所有動作。

深入瞭解[管理安全分數更新](compliance-manager-release-notes.md#secure-score)。

## <a name="understand-the-compliance-score-dashboard"></a>瞭解規範分數儀表板

合規性分數儀表板的設計目的是讓您快速瞭解目前的相容性狀況。

![合規性分數-儀表板](../media/compliance-score-dashboard.png "合規性分數儀表板")

### <a name="overall-compliance-score"></a>整體合規性分數

您的相容性分數主要是在頂端。 它會顯示以點為單位的百分比，可完成解決重要資料保護標準及法規的改進動作。

當您第一次達成法規遵從性分數時，您的初始分數是以內建的 Microsoft 365 資料保護基準（一組包含常見工業法規和標準的控制項）為基礎。 由於合規性分數會掃描現有 Microsoft 365 解決方案的系統，因此它會根據組織目前啟用的隱私權和安全性設定，針對您的相容性狀況，提供初步評估。

當您新增與貴組織相關的評估時，您的分數會變得更有意義。 深入瞭解[如何計算您的分數](compliance-score-methodology.md)。

### <a name="key-improvement-actions"></a>重要改進動作

本節列出您現在可以採取的最大改進動作，以對您的整體合規性分數產生最大的積極影響。

### <a name="solutions-that-affect-your-score"></a>影響分數的解決方案

本節顯示的解決方案包含的動作最有積極影響您分數的機會，以及每個解決方案中未完成的改進動作數目。

### <a name="compliance-score-breakdown"></a>合規性分數細分

本節以兩種不同的方式提供更詳細的分數視圖：

- **類別**：顯示資料保護類別中的整體分數百分比，例如「保護資訊」或「管理裝置」。
- **評估**：顯示針對特定合規性和資料保護標準、法規或法律（如 GDPR 或 NIST 800-53）進行評估的進度百分比。

### <a name="filtering-your-dashboard-view"></a>篩選儀表板視圖

您可以篩選儀表板視圖，只查看與特定規章和標準、解決方案、動作類型、[您設定的評估群組](working-with-compliance-manager.md#groups)或資料保護類別相關的專案。 以這種方式篩選您的視圖也會篩選您儀表板上的分數，以顯示您已從您的篩選準則中取得的總可能點數的點數。

若要套用篩選：

1. 選取儀表板右上方的 [**篩選**]。
2. 從 [**篩選**] 浮出] 窗格**中選取篩選**準則，然後選取 [套用]。

套用篩選後，您會看到即時調整您的分數。 合規性分數百分比和分解資訊，以及改善動作和解決方案，現在只適用于篩選準則所涵蓋的資料。 如果您登出合規性分數，當您登入時，篩選的視圖仍然保留。

若要移除篩選：

- 在 [套用的**篩選**] 標題高於您的合規性分數之外，選取您要移除的個別篩選旁邊的**X** 。或
- 選取儀表板右上方的 [**篩選**]，然後選取 [**清除篩選**]。

## <a name="next-step"></a>下一步

造訪使用[合規性分數](working-with-compliance-score.md)，以瞭解如何採取行動以提升評分的工作流程。