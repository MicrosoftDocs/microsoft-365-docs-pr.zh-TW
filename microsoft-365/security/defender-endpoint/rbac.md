---
title: 使用以角色為基礎的存取控制，以將微調存取權授與 Microsoft Defender 安全中心
description: 在安全性作業內建立角色和群組，以授與入口網站的存取權。
keywords: rbac，角色，基礎，access，control，groups，control，該級，aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058183"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>使用以角色為基礎的存取控制管理入口網站存取

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- Azure Active Directory
- Office 365

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

使用以角色為基礎的存取控制 (RBAC) ，您可以在安全性作業小組中建立角色和群組，以授與入口網站的適當存取權。 您可以根據您建立的角色和群組，精確控制具有入口網站存取權的使用者可以查看及執行的動作。 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

大型地理分散的安全性運作小組通常採用以階層為基礎的模型，以指派及授權對安全性入口網站的存取。 一般層級包括下列三個層級：

層 | 描述
:---|:---
第1層 | **本機安全作業小組/IT 小組** <br> 此小組通常會 triages 並調查包含在其地理位置內的警示，並在需要使用中修復的情況下升級至第2層。
第2層 | **區域安全性運作小組** <br> 此小組可以查看其地區的所有裝置，並執行修正動作。
第3層 | **全域安全性運作小組** <br> 此小組由安全性專家組成，並有權從入口網站查看及執行所有動作。

Defender for Endpoint RBAC 是專門設計用來支援您的分層或以角色為基礎的模型，其可讓您細微地控制哪些角色可以查看、可以存取的裝置，以及可以採取的動作。 RBAC 架構會以下列控制項為中心：

- **控制誰可以採取特定動作**
  - 建立自訂角色並控制其可透過細微性存取的任何 Endpoint 功能。
 
- **控制誰可以查看特定裝置群組或群組的資訊**
  - 依特定準則（例如名稱、標記、網域及其他）[建立裝置群組](machine-groups.md)，然後使用特定 Azure Active Directory (azure AD) 使用者群組，將角色存取權授與這些群組。

若要執行以角色為基礎的存取，您必須定義系統管理員角色、指派對應的許可權，以及指派指派給角色的 Azure AD 使用者群組。


### <a name="before-you-begin"></a>開始之前
使用 RBAC 之前，請務必瞭解可以授與許可權的角色，以及開啟 RBAC 的後果。


> [!WARNING]
> 在啟用該功能之前，請務必先在 Azure AD 中擁有全域系統管理員角色或安全性系統管理員角色，且您的 Azure AD 群組已準備好，以降低鎖定閘道網站的風險。 

當您第一次登入 Microsoft Defender Security Center 時，即會授與「完整存取」或「唯讀」存取權。 使用 Azure AD 中的安全性系統管理員或全域系統管理員角色，可將完整存取權授與使用者。 唯讀存取權授與 Azure AD 中具有安全性讀者角色的使用者。 

具有端點全域系統管理員角色的人員，不論其裝置群組關聯和 Azure AD 使用者群組指派為何，都具有對所有裝置的無限制存取權

> [!WARNING]
> 起初，只有具備 Azure AD 全域系統管理員或安全性管理員許可權的人員才能在 Microsoft Defender 安全中心建立和指派角色，因此，在 Azure AD 中準備好適當的群組是很重要的。
>
> **開啟以角色為基礎的存取控制會使具有唯讀許可權的使用者 (例如，已指派至 Azure AD Security reader 角色的使用者) 會在指派給角色之前喪失存取權。** 
>
>具有系統管理員許可權的使用者會自動為端點全域系統管理員角色指派具有完整許可權的預設內建的 Defender。 在您使用 RBAC 做後，您可以將不是 Azure AD 全域或安全性系統管理員的其他使用者指派給 Defender for Endpoint 全域系統管理員角色。 
>
> 在您登入使用 RBAC 之後，當您第一次登入入口網站時，您無法還原為初始角色。 



## <a name="related-topic"></a>相關主題
- [在 Microsoft Defender for Endpoint 中建立及管理裝置群組](machine-groups.md)
