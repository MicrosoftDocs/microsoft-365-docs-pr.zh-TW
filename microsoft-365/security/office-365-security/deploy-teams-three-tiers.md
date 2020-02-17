---
title: 部署三種檔案保護層級的小組
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 使用 Microsoft Teams 建立和設定以不同層級為其檔案提供資訊保護的小組。
ms.openlocfilehash: 63a4b6763165f38e1de5331324e5a7b3573ea0f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083324"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a>部署三種檔案保護層級的小組

您可以使用本文中的步驟，來設計及部署基準、敏感和高度機密的小組。 如需這三種保護層級的詳細資訊，請參閱[在 Microsoft Teams 中保護檔案](secure-files-in-teams.md)。

## <a name="baseline-teams"></a>基準小組

基準保護包含公開和私人小組。 公開小組可供組織中的任何人探索及存取。 私人網站僅供與小組關聯的 Office 365 群組成員探索及存取。 這兩種類型的小組都可讓成員與其他人共用網站。

### <a name="public"></a>公用

依照[本文](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)中的指示操作，以建立具有公用存取和權限的基準小組。

以下是產生的組態。

![公開小組的基準層級保護。](../../media/baseline-public-team.png)

### <a name="private"></a>私人

依照[本文](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)中的指示操作，以建立具有私用存取和權限的基準小組。

以下是產生的組態。

![私人小組的基準層級保護。](../../media/baseline-private-team.png)

## <a name="sensitive-teams"></a>敏感小組

對於敏感小組，您必須先[建立私人小組](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)。

接著，您必須設定基礎 SharePoint 網站以防止小組成員共用。

1. 在小組的工具列中，按一下 [檔案]****。

2. 按一下省略符號，然後按一下 [在 SharePoint 中開啟]****。

3. 在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]****。

4. 在 [網站權限]**** 窗格的 [共用設定]**** 之下，按一下 [變更共用設定]****。

5. 在 [共用權限]**** 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]****，然後按一下 [儲存]****。

以下是您產生的組態。

![小組的敏感性保護。](../../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a>高度機密小組

對於高度機密小組，您必須先[建立私人小組](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)。

接著，您必須設定基礎 SharePoint 網站，以防止小組成員共用及非小組成員要求存取。

1. 在小組的工具列中，按一下 [檔案]****。

2. 按一下省略符號，然後按一下 [在 SharePoint 中開啟]****。

3. 在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]****。

4. 在 [網站權限]**** 窗格的 [共用設定]**** 之下，按一下 [變更共用設定]****。

5. 在 [共用權限]**** 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]****。

6. 關閉 [允許存取要求]****，然後按一下 [儲存]****。

以下是您產生的組態。

![小組的高度機密保護。](../../media/highly-confidential-team.png)

## <a name="next-step"></a>下一步

[使用保留標籤和 DLP 保護小組中的檔案](deploy-teams-retention-DLP.md)

## <a name="see-also"></a>另請參閱

[在 Microsoft Teams 中保護檔案](secure-files-in-teams.md)

[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
