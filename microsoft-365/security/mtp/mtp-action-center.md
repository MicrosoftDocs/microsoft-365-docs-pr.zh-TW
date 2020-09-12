---
title: 移至重要訊息中心檢視及核准自動化調查和補救工作
description: 使用重要訊息中心檢視自動化調查的詳細資料及核准擱置的動作
keywords: 重要訊息中心, 威脅防護, 調查, 警示, 擱置, 自動化, 偵測
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2dc641d22432e245980b905051bddd3b7dd4ed07
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547983"
---
# <a name="the-action-center"></a>重要訊息中心

**適用於：**
- Microsoft 威脅防護

使用重要訊息中心查看組織的裝置和信箱目前和過去的調查結果。 根據威脅類型和產生的判定，您的組織的安全性運作小組會自動或核准執行 [修正動作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) 。 所有補救動作 (無論是等待核准或已核准) 皆合併在重要訊息中心。 

![重要訊息中心](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>「單一玻璃窗」體驗

重要訊息中心提供工作的「單一玻璃窗」體驗，例如：
- 核准擱置的補救動作；
- 檢視已核准的補救動作的稽核記錄；以及
- 檢閱已完成的補救動作。

由於重要訊息中心可在工作中提供全面檢視 Microsoft 威脅防護，因此您的安全性作業小組可以更有效率地運作。

## <a name="go-to-the-action-center"></a>移至重要訊息中心

1. 移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。 

2. 在功能窗格中，選擇 [控制中心]****。 

3. 在 [操作中心] 中，您會看到兩個索引標籤： **擱置** 和 **記錄**。

    - **[擱置中]** 索引標籤會列出安全作業小組人員需要檢閱及核准才能繼續的調查。 請務必檢閱您在這裡看到的擱置中項目並採取行動。

    - **[歷史記錄]** 索引標籤會列出過去所做的調查和補救動作。 您可以檢視過去一天、一周、一個月或六個月的資料。

4. 若只要顯示需要查看的欄，請選取 **[自訂欄]**。<br/>![Microsoft 威脅防護中的重要訊息中心](../../media/mtp-action-center.png)

5. 選取清單中的項目以檢視更多有關某調查的詳細資料。 調查詳細資料檢視隨即開啟。<br/>![調查詳細資料](../../media/mtp-air-investdetails.png)

    - 如果調查與電子郵件內容相關 (例如，實體為信箱) ，在安全性 & 規範中心中開啟調查詳細資料 ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)) 。 

    - 如果調查涉及裝置，便會在安全中心 ([https://security.microsoft.com](https://security.microsoft.com)) 開啟調查詳細資料。 

> [!TIP]
> 如果您認為 Microsoft 威脅防護中的自動調查和回應功能已錯過或錯誤地偵測到某項功能，請告訴我們！ 請參閱 how [to (AIR) Microsoft 威脅防護中的功能，以自動化調查和回應報告誤報的誤報/負片](mtp-autoir-report-false-positives-negatives.md)。

## <a name="available-actions"></a>可用動作

採取補救措施時，這些動作會列在重要訊息中心的 [記錄] 索引標籤上。 這類動作包括下列各項：

- 收集調查套件 
- 隔離裝置 (此動作可復原)  
- 下架機 
- 發行程式碼執行 
- 從隔離區發行 
- 要求範例 
- 限制程式碼執行 (可以復原此動作)  
- 執行防病毒掃描 
- 停止和隔離 

## <a name="required-permissions-for-action-center-tasks"></a>重要訊息中心的必要權限

若要核准或拒絕重要訊息中心的擱置中動作，您必須具有下表所列的權限：

|補救動作 |必要角色和權限 |
|--|----|
|Microsoft Defender ATP 補救 (裝置) |在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 指派安全性系統管理員角色<br/>--- 或 ---<br/>在 Microsoft Defender ATP 中指派作用中補救動作角色 <br/> <br/> 若要深入了解，請參閱下列資源： <br/>- [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [建立及管理角色型存取控制的角色 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Office 365 ATP 補救 (Office 內容和電子郵件)  |在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 指派安全性系統管理員角色<br/>--- 且 --- <br/>搜尋及清除已指派安全性 & 規範中心 (的角色 [https://protection.office.com](https://protection.office.com))  <br/><br/>**重要**：如果您已將安全性系統管理員角色指派給安全性 & 合規性中心，您將無法存取「行動中心」或「Microsoft 威脅防護」功能。 您必須在 Azure Active Directory 或 Microsoft 365 系統管理中心指派安全性系統管理員角色。 <br/><br/>若要深入了解，請參閱下列資源： <br/>- [Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [安全性 & 規範中心的許可權](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> 在 Azure Active Directory 中指派為全域管理員角色的使用者可核准或拒絕重要訊息中心的任何擱置中動作。 不過，最佳做法是貴組織限制指派為全域管理員角色的人員人數。 我們建議您針對重要訊息中心權限使用安全性系統管理員、作用中補救動作，以及上述「搜尋」和「清除」角色。

## <a name="next-steps"></a>後續步驟 

- [深入了解 Microsoft 威脅防護中的事件](incidents-overview.md)

- [檢視自動調查的結果](mtp-autoir-results.md)

- [深入了解 Microsoft 威脅防護中的搜捕](advanced-hunting-overview.md)

