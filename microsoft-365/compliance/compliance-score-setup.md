---
title: Microsoft 合規性分數安裝程式
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
description: 了解如何登入，設定權限，以及了解 Microsoft 合規性分數，可協助簡化和自動化風險評定儀表板。
ms.openlocfilehash: 8233fb3174d822e4f71115cab2a1a174c1749810
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078610"
---
# <a name="microsoft-compliance-score-preview-setup"></a>Microsoft 合規性分數 （預覽） 安裝程式

## <a name="before-you-begin"></a>開始之前

Microsoft 365 全域系統管理員為您的組織可能會存取合規性分數第一位使用者。 建議的全域管理員身分登入和設定使用者權限，如下所示時第一次造訪合規性分數。

## <a name="sign-in"></a>登入

1. 移至[Microsoft 365 合規性中心](https://compliance.microsoft.com/)及以 Microsoft 365 全域系統管理員帳戶**登入**。
2. 左側的導覽窗格上，選取 [**合規性分數**。 您應該會看到您的[合規性分數儀表板與您的分數](#understand-the-compliance-score-dashboard)。

## <a name="set-user-permissions-and-assign-roles"></a>設定使用者權限，並將角色指派

合規性分數使用角色型存取控制 (RBAC) 權限模型。 只有獲指派角色的使用者可以存取合規性分數，以及每位使用者所允許的動作會受到角色類型。

### <a name="where-to-set-permissions"></a>若要設定權限的位置

在 Microsoft 365 合規性中心或 Azure Active Directory (Azure AD) 中，您組織的全域系統管理員可以設定使用者權限。 一旦角色在這些位置的設定，使用者將能夠存取合規性分數 （以及合規性管理員）。

收件者的現有合規性管理員角色**不**傳輸透過合規性分數。  這表示，如果您先前指派的角色合規性管理員中，該角色會授與您存取合規性分數。 您的全域系統管理員將需要設定權限及角色為您的 Microsoft 365 合規性中心或 Azure AD 中，讓您可以存取合規性分數。

### <a name="role-types"></a>角色類型

下表顯示每個 Microsoft 365 合規性中心角色如何對應至現有的合規性管理員角色及每個角色所允許的函數。


| 使用者可以： | Microsoft 365 合規性中心角色 | 合規性管理員角色 | 
| :------------- | :-------------: | :------------: |
| **讀取但無法編輯資料**| Azure AD 全域讀者  | Azure AD 全域讀者 | 
| **讀取但無法編輯資料**| 安全性讀取者 | 合規性管理員讀取者  | 
| **編輯資料**| 合規性管理員 | 合規性參與者 | 
| **編輯測試結果**| 合規性管理員 | 合規性管理員評估者 | 
| **管理評估以及範本和租用戶資料**| 合規性管理員<br>合規性資料管理員<br>安全性系統管理員 | 合規性管理員的系統管理員 | 
| **指派給使用者**| 全域管理員 | 入口網站管理員 | 

> [!NOTE]
> 從合規性分數移至合規性管理員完成工作時 （例如，若要管理 「 評估 」），您的瀏覽器會開啟新的索引標籤，會出現一個對話方塊。 在 [使用標頭 [top] 區段中，「 已 Microsoft 雲端服務客戶嗎？ 您的帳戶，登入] 選取 [**登入**存取合規性管理員;您將不需要重新輸入您的認證。

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a>如何設定 Microsoft 365 合規性中心中的權限和角色

若要在 Microsoft 365 合規性中心設定權限：

1. 移至[Microsoft 365 合規性中心](https://compliance.microsoft.com)，並使用您的全域系統管理員帳戶登入。
2. 在左側的導覽窗格上，選取 [**權限**。 從這裡開始，您可以檢視角色及指派權限。

## <a name="configure-automatic-secure-score-updates"></a>設定自動安全分數更新

根據預設，所有新租用戶具有自動更新開啟[安全分數](../security/mtp/microsoft-secure-score.md)。 這表示安全分數會監視的所有動作將會自動都更新中合規性分數的相同動作的狀態。

您的全域管理員可以管理此設定設為關閉自動更新的所有動作，或個別地設定更新的動作。

期間公開預覽，您必須移至 Microsoft 服務信任入口網站 （合規性管理員所在） 來管理安全分數會更新。

若要管理自動安全分數更新，請遵循下列步驟：

1. [服務信任入口網站](https://servicetrust.microsoft.com)以全域管理員帳戶登入。

2. 在服務信任入口網站上方的功能表列中，[**更多**，選取 [**系統管理員**，然後選擇**設定**。

3. 在 [**安全分數**] 索引標籤中，選取 [對應] 按鈕，任一**開啟的所有動作**，請**關閉的所有動作**，或**設定每個動作。**

如果您選擇**設定每個動作，** 採取下列額外的步驟，將開啟安全分數更新個別的動作：

4. 從上方的功能表選取 [**合規性管理員**(附註： 請勿選取 「 合規性管理員 （傳統） 」)。

5. 在您的畫面右上角中，選取 [**租用戶管理**。

6. 在 [**客戶動作**] 窗格中，尋找您預定的動作，以在**受影響的動作**] 欄下省略符號 （**...**）。 按一下省略符號，然後選取 [**編輯]。**

7. 切換**連續安全分數更新**切換切換至**上。**

8. 選取 [**儲存。** 安全分數持續監視現在已為該動作。

**附註：** 只有全域系統管理員可以開啟或關閉自動更新的所有動作。 合規性管理員中系統管理員可以全域開啟 [自動更新的個別的動作，但不適用於所有動作。

讀取更多關於[管理安全分數更新](compliance-manager-release-notes.md#secure-score)。

## <a name="understand-the-compliance-score-dashboard"></a>了解合規性分數儀表板

合規性分數儀表板旨在提供您目前的合規性狀態在快速檢視。

![合規性分數-儀表板](../media/compliance-score-dashboard.png "合規性分數儀表板")

### <a name="overall-compliance-score"></a>整體合規性分數

合規性分數，顯著精選頂端，顯示根據點可達成的完成處理索引鍵的資料保護標準與法規的改進動作的百分比。

當您第一次回到合規性分數時，您的初始分數根據內建的 Microsoft 365 的資料保護基準-一組控制項包含一般產業法規及標準。 合規性分數會掃描您的系統的現有的 Microsoft 365 解決方案，因為它可讓您根據隱私權和安全性設定目前已啟用組織的合規性狀態初始評估。

當您新增至您的組織相關的評估，您的分數變得更有意義。 深入了解[您的分數的計算方式](compliance-score-methodology.md)。

### <a name="key-improvement-actions"></a>關鍵的改進動作

此章節將列出上方改進您可以的採取來說，使上整體合規性分數的最大的正面影響。 它會列出未完成或失敗，具有高風險評定的動作。

### <a name="solutions-that-affect-your-score"></a>會影響您的分數的解決方案

您必須在每個方案中的解決方案包含動作與最大有機會帶來正面影響您的分數，以及多少未完成的改進動作此區段顯示。

### <a name="compliance-score-breakdown"></a>合規性分數分解

本節提供詳細的檢視您分數中兩個不同的方式：

- **類別**： 顯示內的資料保護類別，例如 「 保護資訊 」 或 「 管理裝置 」。 您整體分數的百分比
- **「 評估 」**: 管理特定的合規性和資料保護標準、 法令或法律，例如 GDPR 或 NIST 800-53 評定顯示進度百分比。

### <a name="filtering-your-dashboard-view"></a>篩選您的儀表板檢視

您可以篩選您的儀表板檢視，以查看只項目關聯至特定法規與標準、 解決方案、 巨集指令、[評估您所設定的群組](working-with-compliance-manager.md#groups)或資料保護類別類型。 篩選以這種方式檢視也將篩選在儀表板，顯示已達到超出根據篩選準則的總可能點多少點數的分數。

若要套用的篩選器：

1. 選取 [儀表板右上方**篩選器**]。
2. 從彈出式**篩選**] 窗格中，選取您的篩選條件，然後選取 [**套用**]。

一旦套用的篩選，您會看到您調整即時的分數。 合規性分數百分比分解的詳細資訊，以及改進動作與解決方案，現在只適用於所涵蓋的篩選準則的資料。 如果您登出合規性分數時您登入,，也會維持您篩選的檢視。

若要移除的篩選器：

- 在上方合規性分數**套用篩選器**] 標題下，選取您想要移除; 個別篩選器旁邊的**X**或
- 選取**篩選**右上一邊的儀表板，然後選取 [**清除篩選**。

## <a name="next-step"></a>下一步

請造訪以了解如何採取動作，以改善您的分數的工作流程[使用合規性分數](working-with-compliance-score.md)。
