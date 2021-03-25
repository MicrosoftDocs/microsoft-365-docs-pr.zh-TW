---
title: 移至重要訊息中心檢視及核准自動化調查和補救工作
description: 使用重要訊息中心檢視自動化調查的詳細資料及核准擱置的動作
keywords: 重要訊息中心, 威脅防護, 調查, 警示, 擱置, 自動化, 偵測
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 02/01/2021
ms.openlocfilehash: c91e5152fc7a64c8d26363383192d6b8d74611b8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186758"
---
# <a name="the-action-center"></a>重要訊息中心

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

## <a name="a-single-pane-of-glass-experience"></a>「單一玻璃窗」體驗

重要訊息中心提供工作的「單一玻璃窗」體驗，例如：
- 核准擱置的補救動作；
- 檢視已核准的補救動作的稽核記錄；以及
- 檢閱已完成的補救動作。

您的安全性運作小組可以更有效率地運作，因為行動中心會在工作中提供完整的 Microsoft 365 Defender 的觀點。

## <a name="a-new-unified-action-center"></a>新的整合的動作中心

我們很樂意宣告新的整合的動作中心 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) ！ 

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Microsoft 365 Defender 的整合行動中心":::

改進的動作中心會列出裝置的擱置和完成的修正動作、電子郵件 & 共同作業內容，以及在一個位置的身分識別。
- 如果您先前使用的是 Office 365 安全性 & 規範中心 ([https://protection.office.com](https://protection.office.com)) ，請嘗試使用 Microsoft 365 安全性中心的新的整合動作中心 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 。
- 如果您是使用 Microsoft Defender Security Center () 中的 [重要訊息中心] [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) ，請嘗試使用 microsoft 365 安全性中心的新的整合動作中心 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 。
- 如果您已使用 Microsoft 365 的安全性中心 ([https://security.microsoft.com](https://security.microsoft.com)) 中，您將會在 [重要訊息中心] 中看到許多改進功能 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 。

整合的動作中心會跨 Defender 的 Defender 和 Defender for Office 365，將修正動作彙集在一起。 它會定義所有修正動作的共同語言，並提供統一的調查經驗。 「行動中心」為您的安全性運作小組提供「單一窗格的玻璃」經驗，以查看和管理修正動作。  

如果您有適當的許可權以及下列一或多項訂閱，您可以使用統一的行動中心：

- [適用於端點的 Defender](../defender-endpoint/microsoft-defender-endpoint.md)
- [適用於 Office 365 的 Defender](/microsoft-365/security/defender-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> 若要深入瞭解，請參閱 [需求](./prerequisites.md)。

## <a name="using-the-action-center"></a>使用動作中心

1. 移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。 
2. 在功能窗格中，選擇 [控制中心]。 

當您造訪「行動中心」時，您會看到兩個索引標籤：擱置的動作和歷程記錄。 下表摘要顯示每個索引標籤的內容：

|索引標籤  |描述  |
|---------|---------|
|**等待**     | 顯示需要注意的動作清單。 您可以一次核准或拒絕其中一項動作，或選取多個動作的動作為相同類型的動作 (例如隔離檔案) 。 <p>**秘訣**：請務必立即複查及核准 (或拒絕) 擱置的動作，以便您的自動化調查可以及時完成。       |
|**歷程記錄**     | 做為已採取動作的審計記錄，例如： <br/>-自動調查導致採取的修正動作 <br/>-針對可疑或惡意電子郵件、檔案或 URLs 所採取的修正動作<br/>-您的安全作業小組已核准的修正動作 <br/>-已執行的命令和在即時回應會話期間所套用的修正動作<br/>-您的防防毒保護採取的修正動作 <p>提供一種方法來復原特定動作 (請參閱 [復原已完成的動作](m365d-autoir-actions.md#undo-completed-actions)) 。        |

您可以在「行動中心」中自訂、排序、篩選和匯出資料。

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="操作中心可讓您排序、篩選和自訂動作清單":::

- 選取欄標題，以遞增或遞減順序排序專案。
- 使用 [時段] 篩選，以查看過去一天、一周、30天或6個月的資料。
- 選擇您要查看的欄。
- 指定每個資料頁面上要包含的專案數。
- 請使用篩選器，只查看您想要查看的專案。
- 選取 [ **匯出** ]，將結果匯出至 .csv 檔案。

## <a name="actions-tracked-in-the-action-center"></a>在行動中心追蹤的動作

在行動中心追蹤所有動作（不論是待核准或已經採取的動作）。 可用的動作包括下列專案：

- 收集調查套件 
- 隔離裝置 (此動作可復原)  
- 下架機 
- 發行程式碼執行 
- 從隔離區發行 
- 要求範例 
- 限制程式碼執行 (可以復原此動作)  
- 執行防病毒掃描 
- 停止和隔離 

除了自動 [調查](m365d-autoir.md)所做的修正動作之外，「動作中心」也會追蹤安全小組採取的動作，以解決偵測到的威脅，以及 Microsoft 365 Defender 中威脅防護功能的結果所採取的動作。 如需自動和手動修正動作的相關資訊，請參閱 [修復動作](m365d-remediation-actions.md)。

## <a name="viewing-action-source-details"></a>查看動作來源詳細資料

 (**NEW！**) 改進的動作中心現在會包含 [ **動作來源** ] 欄，可告訴您每個動作來自何處。 下表說明可能的 **動作來源** 值：

| 動作來源值 | 描述 |
|:-----|:---|
| **手動裝置動作** | 在裝置上執行的手動動作。 範例包括 [裝置隔離](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) 或 [檔隔離](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files)。 |
| **手動電子郵件動作** | 手動對電子郵件採取的動作。 包含虛刪除電子郵件訊息或 [修正電子郵件訊息](../defender-365-security/remediate-malicious-email-delivered-office-365.md)的範例。 |
| **自動裝置動作** | 對實體（如檔案或處理常式）採取的自動動作。 自動動作的範例包括將檔案傳送至隔離區、停止處理常式，以及移除登錄機碼。  (查看 [Microsoft Defender For Endpoint 中的修復動作](../defender-endpoint/manage-auto-investigation.md#remediation-actions)。 )  |
| **自動化的電子郵件動作** | 對電子郵件內容採取的自動動作，例如電子郵件訊息、附件或 URL。 自動動作的範例包括虛刪除的電子郵件、封鎖 URLs 和關閉外部郵件轉發。  (參閱 [適用于 Office 365 的 Microsoft Defender 中的修復動作](../defender-365-security/air-remediation-actions.md)。 )  |
| **高級搜尋動作** | 使用 [高級搜尋](./advanced-hunting-overview.md)對裝置或電子郵件採取的動作。 |
| **Explorer 動作** | 使用 [Explorer](../defender-365-security/threat-explorer.md)對電子郵件內容採取的動作。 |
| **手動即時回應動作** | 在具有 [即時回應](../defender-endpoint/live-response.md)的裝置上採取的動作。 範例包括刪除檔案、停止程式及移除排程的任務。 |
| **即時回應動作** | 使用 [Microsoft Defender For Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)對裝置執行的動作。 動作範例包括隔離裝置、執行防病毒掃描，以及取得檔案的相關資訊。 |

## <a name="required-permissions-for-action-center-tasks"></a>重要訊息中心的必要權限

若要執行工作，例如核准或拒絕動作中心中的擱置中的動作，您必須將許可權指派給下表所列：

|補救動作 |必要角色和權限 |
|--|----|
|Microsoft Defender for Endpoint 修復 (裝置)  |在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 指派 **安全性系統管理員** 角色<br/>--- 或 ---<br/>在 Microsoft Defender for Endpoint 中指派作用中的 **修正動作** 角色 <br/> <br/> 若要深入了解，請參閱下列資源： <br/>- [Azure Active Directory 中的系統管理員角色權限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [建立及管理角色型存取控制 (Microsoft Defender for Endpoint) ](../defender-endpoint/user-roles.md)  |
|Microsoft Defender for Office 365 修正 (Office 內容和電子郵件)   |在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 指派 **安全性系統管理員** 角色<br/>--- 且 --- <br/>**搜尋及清除** 已指派安全性 & 規範中心 (的角色 [https://protection.office.com](https://protection.office.com))  <br/><br/>**重要**：如果您已在 Office 365 安全性 & 合規性中心內指派 **安全性系統管理員** 角色 ([https://protection.office.com](https://protection.office.com)) ，您將無法存取「行動中心」或「Microsoft 365 Defender」功能。 您必須具有在 Azure Active Directory 或 Microsoft 365 系統管理中心中指派的 **安全性系統管理員** 角色。 <br/><br/>若要深入了解，請參閱下列資源： <br/>- [Azure Active Directory 中的系統管理員角色權限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [安全性 & 規範中心的許可權](/microsoft-365/security/defender-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> 在 Azure Active Directory 中指派為 **全域管理員** 角色的使用者可核准或拒絕重要訊息中心的任何擱置中動作。 不過，最佳作法是，您的組織應該限制已指派 **全域系統管理員** 角色的人員人數。 建議使用 **安全性系統管理員**、作用中的 **修復動作**，以及上表中所列的「動作中心」許可權所列的 **搜尋及清除** 角色。

## <a name="next-step"></a>下一步 

- [複查和管理修正動作](m365d-autoir-actions.md)
