---
title: 安全性原則的設定分析器
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用設定分析器，找出並修正低於標準防護和嚴格保護預設安全性原則的安全性原則。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fd67c93711dc847a25be485b4b016af55e4a31
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203440"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP 和 Microsoft Defender for Office 365 中保護原則的設定分析器

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Security & 合規性中心的設定分析器提供一個集中位置，以找出並修正安全性原則，其中的設定低於標準 [安全性原則](preset-security-policies.md)中的標準防護和嚴格保護設定檔設定。

設定分析器會分析下列類型的原則：

- **Exchange Online Protection (EOP) 原則**：這包括使用 exchange online 信箱的 Microsoft 365 組織和獨立 EOP 組織，但沒有 exchange online 信箱：

  - [反垃圾郵件原則](configure-your-spam-filter-policies.md)。
  - [反惡意程式碼原則](configure-anti-malware-policies.md)。
  - [EOP 反網路釣魚原則](set-up-anti-phishing-policies.md#spoof-settings)。

- **Microsoft Defender For office 365 原則**：這包括具有 Microsoft 365 E5 或 Defender for office 365 附加元件訂閱的組織：

  - Microsoft Defender for Office 365 中的反網路釣魚原則，其中包括：

    - EOP 反網路釣魚原則中提供的相同 [欺騙設定](set-up-anti-phishing-policies.md#spoof-settings) 。
    - [類比設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高級網路釣魚臨界值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [安全連結原則](set-up-safe-links-policies.md)。

  - [安全附件原則](set-up-safe-attachments-policies.md)。

[EOP 和 Microsoft Defender For Office 365 安全性](recommended-settings-for-eop-and-office365.md)中所述做為基準的 **標準** 和 **嚴格** 原則設定值。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至 [設定 **分析器** ] 頁面，請使用 <https://protection.office.com/configurationAnalyzer> 。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 您必須先獲得 [安全性與合規性中心] 指派的權限，才能使用此文章中的程序：
  - 若要使用設定分析器 **並** 更新安全性原則，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要唯讀存取設定分析器，您必須是 **全域讀取器** 或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。

  > [!NOTE]
  >  
  > - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>在安全性 & 規範中心使用設定分析器

在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** 設定 \> **分析器**]。

![[威脅管理原則] 頁面上的設定分析器小工具 \>](../../media/configuration-analyzer-widget.png)

設定分析器有兩個主要的索引標籤：

- **設定和建議**：選擇 [標準] 或 [嚴格]，然後將這些設定與您現有的安全性原則進行比較。 在結果中，您可以調整設定的值，使其具有與標準或嚴格相同的層級。

- 設定 **偏移分析和記錄**：此 view 可讓您追蹤一段時間的原則變更。

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>設定分析器中的 [設定與建議] 索引標籤

依預設，索引標籤會在與標準保護設定檔的比較上開啟。 您可以按一下 [ **查看嚴格建議**] 切換到嚴格保護設定檔的比較。 若要切換回來，請選取 [ **查看標準建議**]。

![設定分析器中的設定和建議視圖](../../media/configuration-analyzer-settings-and-recommendations-view.png)

根據預設，[ **原則群組/設定名稱** ] 欄會包含不同類型的安全性原則及設定數目的折疊模式，如果有任何) 則需要改進 (。 原則類型包括：

- **反垃圾郵件**
- **防網路釣魚**
- **反惡意程式碼**
- 如果您的訂閱包含 Microsoft Defender for Office 365， **ATP 安全附件** () 
- 如果您的訂閱包含 Microsoft Defender for Office 365， **ATP 安全連結** () 

在預設的視圖中，會折疊所有專案。 每個原則旁都有一個原則的比較結果摘要，您可以在您的原則 (中修改) 和設定標準或嚴格保護設定檔對應之原則中的設定， (但不能修改) 。 您將會看到您要比較的保護設定檔的下列資訊：

- **綠色**：所有現有原則中的所有設定，至少都是保護設定檔的安全性。
- **琥珀色**：現有原則中的少量設定，不如保護設定檔的安全性。
- **紅色**：現有原則中的大量設定與保護設定檔的安全性不符。 這可能是許多原則中的一些設定或一個原則中的眾多設定。

就理想的比較而言，您會看到文字： **所有設定都會遵循** \<**Standard** or **Strict**\> **建議**。 否則，您會看到建議設定的變更數目。

如果您展開 [ **原則] 群組/設定名稱**，則會顯示每個需要注意之特定原則中的所有原則和相關設定。 或者，您可以展開特定類型的原則 (例如， **反垃圾郵件**) ，只查看那些需要注意之原則類型中的設定。

如果比較沒有改進 (綠) 的建議，則展開原則會顯示 nothing。 如果有任何數量的改進建議 (琥珀色或紅色) ，則會顯示需要注意的設定，並會顯示下列各欄中的對應資訊：

- 需要注意之設定的名稱。 例如，在先前的螢幕擷取畫面中，它是反垃圾郵件原則中的 **大量電子郵件閾值** 。

- **原則**：包含設定之受影響原則的名稱。

- **適用** 于：受影響的原則所套用的使用者數目。

- **目前** 設定：設定的目前值。

- **上次修改** 日期：上次修改原則的日期。

- **建議**：標準或嚴格保護設定檔中的設定值。 若要變更原則中設定的值，使其符合保護設定檔中的建議值，請按一下 [ **採用**]。 如果變更成功，您會看到訊息： **已成功採用的建議**。 按一下 **[** 重新整理] 以查看減少的建議數量，並從結果中移除特定設定/原則列。

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>設定分析器中的設定偏移分析和記錄] 索引標籤

此索引標籤可讓您追蹤您對自訂安全性原則所做的變更。 根據預設，會顯示下列資訊：

- **上次修改日期**
- **修改者**
- **設定名稱**
- **原則**
- **Type**

若要篩選結果，請按一下 [篩選]。 在出現的 [ **篩選** ] 浮出控制項中，您可以選取下列篩選：

-  (日期) 的 **開始時間** 和 **結束時間**
- **標準保護** 或 **嚴格保護**

若要將結果匯出至 .csv 檔案，請按一下 [ **匯出**]。

![設定分析器中的設定偏移分析和歷程記錄視圖](../../media/configuration-analyzer-configuration-drift-analysis-view.png)