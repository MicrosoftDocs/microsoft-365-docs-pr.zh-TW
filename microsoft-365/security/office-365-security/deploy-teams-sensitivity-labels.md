---
title: 使用敏感度標籤保護小組中的檔案
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
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 摘要：套用敏感度標籤以保護高度機密小組中的檔案。
ms.openlocfilehash: c36daef7f28ad8bd3306fd7f3f7f1558a3594e68
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637613"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a>使用敏感度標籤保護小組中的檔案


適用於高度管制資料的敏感度標籤可讓任何人套用至任何檔案，但是高度機密小組不同，他們需要自己的標籤或子標籤，使指派的檔案能夠：

- 進行個別加密。
- 包含自訂權限，使其只能由小組成員開啟。

若要為儲存在小組的基礎 SharePoint 網站中的檔案達成這個額外的安全性層級，您必須設定自訂的敏感度標籤，而此標籤可以是單獨的標籤，或是高度管制資料之一般標籤的子標籤。 只有小組成員才可在其標籤清單中看到自訂標籤或子標籤。

當您需要少量標籤、可同時用於全域使用和個別的私人小組時，請使用敏感度標籤。 

當您有大量標籤，或想要將高度機密小組的標籤整理到高度管制標籤之下時，請使用敏感度子標籤。

依照[下列指示](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)，設定具有下列設定的不同標籤或子標籤：

- 標籤或子標籤的名稱中包含小組的名稱
- 已啟用加密
- 小組的 Microsoft 365 群組具有共同撰寫權限

建立之後，請為您的使用者發佈新的標籤或子標籤，讓他們能夠在檔案上傳至小組前先在本機的檔案套用標籤，或等到檔案儲存至小組時再套用。

以下是高度機密小組使用敏感度標籤進行檔案加密和權限授與的設定。

![公開小組的基準層級保護。](../../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a>另請參閱

[在 Microsoft Teams 中保護檔案](secure-files-in-teams.md)
  
[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
