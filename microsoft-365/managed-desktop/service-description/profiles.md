---
title: 瞭解裝置設定檔
description: 管理員可指派給裝置的各種設定檔
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e6b0c96d4e145a2e5df7c7555e262aefe891e483
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690165"
---
# <a name="device-profiles"></a>裝置設定檔

您可以將不同的預先設定設定 ( 「裝置設定檔」 ) 指派給裝置，並針對特定類型的使用者需求進行優化。 可使用三個裝置設定檔：

- 標準版
- 機密資料
- Power user

您可以將裝置設定檔視為裝置設定選項階層的一部分。

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="以棱錐方式顯示裝置設定。描述如下":::

從根本上來說，每家 Microsoft 受管理的桌面裝置都有一個基礎，其中包含標準的安全性基準、規範原則、Windows Update 設定和群組。 若要使用 Microsoft 受管理的電腦，每個裝置都必須包含所有這些元素，但不需要 Microsoft 受管理的電腦要求，系統管理員無法變更這些元素。

裝置設定檔會出現在下一個較高的層級。 每個 Microsoft 受管理的桌面裝置都必須有一個 (，而且只指派一個) 設定檔。 管理員可以選擇要指派裝置的設定檔。

在另一個較高級別的 [自訂](customizing.md)專案。 每個裝置可以有一或多個 (或沒有) 自訂。 他們可以修改較低層級的層 (裝置設定檔或基礎設定) ，或是在標準設定之上階層式全新要求。

在頂端是您自己的修改，例如網路詳細資料或應用程式。 裝置可以有任何數目的修改，因為 Microsoft 受管理的電腦不會管理或封鎖這些修改。


## <a name="device-profile-details"></a>裝置設定檔詳細資料

下表摘要說明裝置設定檔設定之每個設定值的設定及其預設值。  (幕後，這些設定會透過使用 Microsoft 端點管理員中的自訂設定檔來設定 OMA-URIs。 ) 

| 功能 | 機密資料 | Power User | 標準版 |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|------------------------|-----------------------|
| **封鎖外部儲存裝置**                                                                                                                               | 是                       | 是                   | 否                   |
| **[雲端封鎖層級](https://docs.microsoft.com/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)** | 高                      | 高                  | 高                 |
| **停用 Microsoft 帳戶**                                                                                                                           | 是                       | 是                   | 否                   |
| **停用個人 OneDrive**                                                                                                                            | 是                       | 是                   | 否                   |
| **切換至保護桌面以進行提升**                                                                                                               | 否                        | 是                   | 否                   |
| **Microsoft Defender for Endpoint Device 標記**                                                                                                           | M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard |
| **裝置上的系統管理員？**                                                                                                                                 | 否                        | 是                   | 否                   |
| **Autopilot 設定檔**                                                                                                                                     | MMD 標準               | MMD Power User         | MMD 標準          |
| **AppLocker**                                                                                                                                            | 是                       | 否                    | 否                   |
| **封鎖公用存放區**                                                                                                                                   | 是                       | 是                   | 否                   |

每個裝置設定檔也會包含下列專案：

- 動態成員資格 Azure Active Directory (AAD) 裝置群組
- 靜態成員 AAD 裝置群組
- Microsoft 端點管理員設定檔

> [!IMPORTANT]
> 請勿直接修改這些群組的成員資格。 使用 [重新指派設定檔](../working-with-managed-desktop/change-device-profile.md)中所述的介面。

## <a name="limitations"></a>限制

您可以像對待任何其他原則一樣，向裝置設定檔和其詳細資料要求例外狀況。 請記住，您的 Azure Active Directory 組織中，每個裝置設定檔中只有一個會 ( "承租人" ) 。 例如，您無法要求敏感性資料裝置設定檔只對部分使用者停用 AppLocker。 具有敏感性資料設定檔的所有裝置都必須具有相同的設定。

每個裝置只能有一個設定檔。 如果有多個使用者使用指定的裝置，該裝置上的所有使用者將會有相同的設定。
