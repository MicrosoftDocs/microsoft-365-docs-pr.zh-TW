---
title: 測試人員風險管理計畫
description: 瞭解如何規劃如何在您的組織中使用內部使用者風險管理原則。
keywords: Microsoft 365、測試人員風險、風險管理、合規性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 8cd9e9a72cd7643238d118fe0aed519db9159470
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820145"
---
# <a name="plan-for-insider-risk-management"></a>測試人員風險管理計畫

在您的組織中開始使用「 [內部使用者風險管理](insider-risk-management.md) 」之前，您的資訊技術和合規性管理小組應該會檢查重要的規劃活動和考慮。 深入瞭解及規劃部署在下列方面，可協助確保您的實施和使用內部部署的風險管理功能，並與解決方案的最佳作法保持一致。

## <a name="work-with-stakeholders-in-your-organization"></a>與組織中的專案關係人合作

在您的組織中識別適當的利益關係人，以共同作業，以進行「內幕風險管理」提醒與案例的動作。 有些建議的專案關係人會考慮包含在初始規劃中，而端對端的 [有問必答風險管理工作流程](insider-risk-management.md#workflow) 是來自組織下列領域的人員：

- 資訊技術
- 合規性
- 隱私權
- 安全性
- 人力資源
- 法律資訊

## <a name="determine-any-regional-compliance-requirements"></a>決定任何區域合規性需求

不同的地理位置和組織區域可能會有不同于組織其他區域的合規性和隱私權需求。 與這些領域中的利益關係人合作，以確保他們瞭解內幕程式風險管理中的合規性和隱私權控制，以及如何跨組織的不同區域使用這些控制。 在某些情況下，法規遵從性和隱私權需求可能需要原則，以根據使用者或規定或地區的原則需求，指定或限制部分的專案關係人調查和案例。

如果您有特定的專案關係人的需求，若要將涉及特定地區、角色或分割之使用者的案例調查納入，您可能會想要執行個別的 (，即使) 具有不同地區和人口的 [有問必答風險管理原則](insider-risk-management-policies.md) 也是一樣的。 這種設定可讓適當的利益關係人更容易地會審及管理與其角色及地區相關的案例。 此外，您可能會考慮針對地區建立程式和原則，讓調查人員和檢閱者與使用者有相同的語言，協助簡化內部測試人員風險管理提醒及案例的升級程式。

## <a name="plan-for-the-review-and-investigation-workflow"></a>規劃審閱和調查工作流程

選取 [專屬的利益關係人]，以在 [Microsoft 365 規範中心](https://compliance.microsoft.com/)內的定期節奏上監視和審閱警示和案例。 請務必瞭解如何將不同的專案關係人指派給「內部使用者風險管理」中可用的不同角色群組。

根據您的規範管理小組的結構，您可以選擇將使用者指派給特定角色群組，以管理不同的集一組內幕風險管理功能。 若要在 Office 365 安全性 & 規範中心及管理角色群組中查看 [ **許可權** ] 索引標籤，您必須被指派至「 *組織管理* 」角色群組，或是必須被指派 *角色管理* 角色。 設定有問必答風險管理時，請從下列角色群組選項中選擇：

| **角色群組** | **角色權限** |
| :------------- | :------------------- |
| **有問必答風險管理** | 使用此角色群組，在單一群組中管理組織的有問必答風險管理。 新增指派管理員、分析員、調查人員和審計員的所有使用者帳戶，您可以在單一群組中設定「有問必答風險管理」許可權。 這個角色群組包含所有的「內幕風險管理」許可權角色和相關聯的許可權。 這項設定是快速開始使用「內幕風險管理」的最簡單方法，而且很適合不需要個別使用者群組定義個別許可權的組織。 |
| **測試人員風險管理系統管理員** | 使用此角色群組開始設定「有問必答風險管理」和更新後的成員，以將內幕風險管理員與定義的群組隔離。 這個角色群組中的使用者可以啟用和查看分析 insights，以及建立、讀取、更新和刪除內部使用者風險管理原則、全域設定和角色群組指派。 |
| **測試人員風險管理分析員** | 使用此群組可將許可權指派給將擔當「有問必答風險案例分析」的使用者。 這個角色群組中的使用者可以存取及流覽所有的內幕人士風險管理提醒、案例、分析真知灼見及通知範本。 他們無法存取「內部使用者風險」內容瀏覽器。 |
| **測試人員風險管理調查員** | 使用此群組可將許可權指派給將充當內部使用者風險資料調查人員的使用者。 在所有情況下，此角色群組中的使用者都可以存取所有的內幕程式風險管理提醒、案例、通知範本及內容瀏覽器。 |
| **內部人員風險管理審計員** | 使用此群組可將許可權指派給使用者，以進行審核的「內幕風險管理」活動。 這個角色群組中的使用者可以存取「內幕人員風險審核記錄」。 |

## <a name="understand-requirements-and-dependencies"></a>瞭解需求和相依性

根據您計畫如何執行有問必答風險管理原則，您必須具備適當的 Microsoft 365 授權訂閱，並瞭解和規劃某些方案必要條件。

**授權：** 在廣泛的 Microsoft 365 授權訂閱中，您可以使用「內幕風險管理」。 如需詳細資訊，請參閱《快速入門的 [內幕風險管理](insider-risk-management-configure.md#subscriptions-and-licensing) 文章。

如果您沒有現有的 Microsoft 365 企業版 E5 計畫，而且想要嘗試擁有者風險管理，您可以 [將 microsoft 365 新增](/office365/admin/try-or-buy-microsoft-365) 至現有的訂閱，或註冊 Microsoft 365 Enterprise E5 的 [試用版](https://www.microsoft.com/microsoft-365/enterprise) 。

**原則範本需求：** 視您所選擇的原則範本而定，您必須先瞭解和規劃這些需求，才能在組織中設定有問必答風險管理：

- 當使用者使用「 **資料竊取** 」的範本時，您必須設定 MICROSOFT 365 HR 連接器，定期為組織中的使用者匯入辭職及終止日期資訊。 如需為組織設定 Microsoft 365 HR connector 的逐步指引，請參閱 [Import data WITH HR connector](import-hr-data.md) 文章。
- 使用 **資料洩漏** 範本時，您必須設定至少一個資料遺失防護 (DLP) 原則，以定義組織中的敏感資訊，並接收高嚴重性 DLP 原則警示的有問必答風險警示。 如需為組織設定 DLP 原則的逐步指引，請參閱 [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md) 文章。
- 使用 **安全性原則侵犯** 範本時，您必須在 Defender security Center 中啟用內部的「內部人員風險管理整合」端點，以匯入安全性違規警示。 請參閱 [設定 Microsoft Defender 文章中的「高級功能](/windows/security/threat-protection/microsoft-defender-atp/advanced-features) 」，以取得啟用 Defender 以與內幕風險管理進行端點整合的逐步指引。
- 使用 **不滿的使用者** 範本時，您必須設定 MICROSOFT 365 HR connector，定期為組織中的使用者匯入效能或降級狀態資訊。 如需為組織設定 Microsoft 365 HR connector 的逐步指引，請參閱 [Import data WITH HR connector](import-hr-data.md) 文章。

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>在實際執行環境中與一小組使用者進行測試

在實際執行環境中啟用廣泛的解決方案之前，您可以考慮在組織中進行必要的規範、隱私權和法律檢查時，與一小部分的實際執行使用者一起測試原則。 在測試環境中評估有問必答風險管理，將需要您產生模擬使用者動作和其他信號，以建立模擬和案例的警示，以進行處理。 這種方法不適用於大多數的組織，所以應該優先使用實際執行環境中的一小組使用者測試有問必答風險管理。

保留原則設定中的匿名功能，以在此測試期間 anonymize 「內幕風險管理」主控台中的使用者顯示名稱，以維護工具內的隱私權。 這項設定可協助保護具有原則相符之使用者的隱私權，並可協助您在資料調查和分析審核 objectivity 中，協助推廣內部專案風險警示。

若在設定「有問必答風險管理」原則之後，未立即看到任何警示，這可能表示尚未滿足最低風險閾值。 若要檢查是否已觸發原則，並如預期般運作，就是查看 **使用者頁面上的原則** 是否屬於範圍的好方法。

## <a name="resources-for-stakeholders"></a>專案關係人的資源

與您組織中包含在管理與修復工作流程中的專案關係人共用有問必答風險管理檔：

- [建立及管理測試人員風險原則](insider-risk-management-policies.md)
- [調查測試人員風險警示](insider-risk-management-alerts.md)
- [對測試人員風險案例採取動作](insider-risk-management-cases.md)
- [使用「內幕風險內容瀏覽器」查看案例資料](insider-risk-management-content-explorer.md)
- [建立測試人員風險通知範本](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>準備好開始使用了嗎？

準備好為您的組織設定測試人員風險管理嗎？ 請參閱下列文章：

- [開始使用「會員風險管理」設定](insider-risk-management-settings.md) 來設定全域原則設定。
- [開始使用「內幕風險管理](insider-risk-management-configure.md) 」來設定必要條件、建立原則及開始接收提醒。
