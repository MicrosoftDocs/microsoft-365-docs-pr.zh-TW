---
title: 流覽行動中心以查看修正動作
description: 使用重要訊息中心來查看自動調查後的詳細資料和結果
keywords: action，center，autoir，自動化，調查，回應，修正
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: af9e9315088a8dd5da9740b33135551d28664ed7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186110"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>流覽行動中心以查看修正動作

在自動調查期間和之後，會識別威脅偵測的修正動作。 根據特定威脅及如何為您的組織設定 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection) ，有些修正動作會自動採取，其他一些要求必須核准。 如果您是組織的安全性運作小組的一部分，您可以在重要訊息 **中心** 中查看暫止及已完成的 [修復動作](manage-auto-investigation.md#remediation-actions)。 


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a> (NEW！ ) 整合的動作中心


我們很樂意宣告新的整合的動作中心 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) ！

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Microsoft 365 security center 中的動作中心":::

下表將新的整合的動作中心與上一個操作中心進行比較。

|新的整合的動作中心  |上一個操作中心  |
|---------|---------|
|列出裝置和電子郵件在一個位置的擱置和完成的動作 <br/> ([Microsoft defender For Endpoint](microsoft-defender-endpoint.md) 加 [Microsoft defender for Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)) |列出裝置的擱置及已完成的動作 <br/> 僅限 [端點的 Microsoft Defender](microsoft-defender-endpoint.md) ()    |
|位於：<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |位於：<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| 在 Microsoft 365 的 [安全性中心] 中，選擇 [ **動作中心**]。 <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="流覽至 Microsoft 365 安全中心的動作中心"::: | 在 Microsoft Defender Security Center 中，選擇 [**自動調查**]  >  **動作中心**。 <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="從 Microsoft Defender Security Center 流覽至 [行動中心]":::  |

整合的動作中心會跨 Defender 的 Defender 和 Defender for Office 365，將修正動作彙集在一起。 它會定義所有修正動作的共同語言，並提供統一的調查經驗。 

如果您有適當的許可權以及下列一或多項訂閱，您可以使用統一的行動中心：
- [適用於端點的 Defender](microsoft-defender-endpoint.md)
- [適用於 Office 365 的 Defender](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> 若要深入瞭解，請參閱 [需求](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)。

## <a name="using-the-action-center"></a>使用動作中心

若要在改進的 Microsoft 365 安全中心進入整合的動作中心：
1. 請移至 Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) 並登入。
2. 在功能窗格中，選取 [ **動作中心**]。 

當您造訪「行動中心」時，您會看到兩個索引標籤： **擱置的動作** 和歷程 **記錄**。 下表摘要顯示每個索引標籤的內容：

|索引標籤  |描述  |
|---------|---------|
|**等待**     | 顯示需要注意的動作清單。 您可以一次核准或拒絕其中一項動作，或選取多個動作的動作為相同類型的動作 (例如 **隔離** 檔案) 。 <br/>**秘訣**：請務必立即 [複查及核准 (或拒絕) 擱置的動作](manage-auto-investigation.md) ，以便您的自動化調查可以及時完成。 |
|**歷程記錄**     | 做為已採取動作的審計記錄，例如： <br/>-自動調查導致採取的修正動作 <br>-您的安全作業小組已核准的修正動作  <br/>-已執行的命令和在即時回應會話期間所套用的修正動作  <br/>-Microsoft Defender 防病毒中威脅防護功能採取的修正動作  <p>提供一種方法來復原特定動作 (請參閱 [復原已完成的動作](manage-auto-investigation.md#undo-completed-actions)) 。       |

您可以在「行動中心」中自訂、排序、篩選和匯出資料。

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="在重要訊息中心中的欄與篩選":::

- 選取欄標題，以遞增或遞減順序排序專案。
- 使用 [時段] 篩選，以查看過去一天、一周、30天或6個月的資料。
- 選擇您要查看的欄。
- 指定每個資料頁面上要包含的專案數。
- 請使用篩選器，只查看您想要查看的專案。
- 選取 [ **匯出** ]，將結果匯出至 .csv 檔案。 

## <a name="next-steps"></a>後續步驟

- [查看和核准修正動作](manage-auto-investigation.md)
- [請參閱互動式指南：使用 Microsoft Defender for Endpoint 調查和修正威脅](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>另請參閱

- [在 Microsoft Defender for Endpoint 中處理誤報/負片](defender-endpoint-false-positives-negatives.md)
