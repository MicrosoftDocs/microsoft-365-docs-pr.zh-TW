---
title: Azure Active Directory 中的 Microsoft 365 隔離與存取控制
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 在本文中，您將瞭解隔離和存取控制如何在 Azure Active Directory 中讓多個承租人相互隔離的資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332409"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a>Azure Active Directory 中的 Microsoft 365 隔離與存取控制

Azure Active Directory (Azure AD) 設計為透過邏輯資料隔離以高安全性的方式主控多個承租人。 存取 Azure AD 的方式是透過授權層來封閉。 Azure AD 隔離以租使用者容器為安全性界限的客戶，以保護客戶的內容，使其內容無法透過共同承租人進行存取或破壞。 Azure AD 的授權層會執行三項檢查：

- 是否啟用主體以存取 Azure AD 租使用者？
- 是否已啟用主體來存取此承租人中的資料？
- 此租使用者中的主體角色是否獲得要求的資料存取類型？

沒有任何應用程式、使用者、伺服器或服務可以存取未適當驗證與 token 或憑證的 Azure AD。 若未附帶適當的認證，便會拒絕要求。

實際上，Azure AD 會將每個租使用者放在其本身受保護的容器中，並在容器內和容器內，以完全擁有和管理的原則和許可權為主機。
 
![Azure 容器](../media/office-365-isolation-azure-container.png)

租使用者容器的概念在所有層級的目錄服務中，從入口網站一直到持續儲存的方式，都很深層 ingrained。 即使多個 Azure AD 租使用者中繼資料儲存在同一個實體磁片上，除了目錄服務所定義的容器以外，其他容器之間並沒有任何關係，也是由租使用者管理員所決定。 任何要求的應用程式或服務，都不能直接連線至 Azure AD 儲存體，您必須先進行授權層級的連接。

在下列範例中，Contoso 和 Fabrikam 都有個別、專用的容器，即使這些容器共用某些相同的基礎結構（例如伺服器和儲存區），它們仍然彼此分開且彼此隔離，並依授權和存取控制層來封閉。
 
![Azure 專用容器](../media/office-365-isolation-azure-dedicated-containers.png)

此外，Azure AD 內沒有任何可執行檔應用程式元件，一個承租人不可能強制破壞其他租使用者的完整性、存取另一個租使用者的加密金鑰，或從伺服器讀取原始資料。

根據預設，Azure AD 不允許其他承租人中的身分識別所發出的所有作業。 每個租使用者會透過宣告式的存取控制，在 Azure AD 中以邏輯方式隔離。 目錄資料的讀取和寫入會限定在租使用者容器中，並以內部抽象層來封閉，並以角色為基礎的存取控制 (RBAC) 層，其共同執行租使用者作為安全性界限。 所有的目錄資料存取要求都是由這些層處理，而 Microsoft 365 中的每個存取要求都是透過以上邏輯 policed。

Azure AD 具有北美、美國政府、歐盟、德國及全球通用磁碟分割。 租使用者存在於單一分割區中，而分割區可包含多個承租人。 磁碟分割資訊會從使用者中抽象出來。 指定的分割區 (包括其內的所有承租人) 會複寫至多個資料中心。 租使用者的分割區時，會根據租使用者的屬性來選擇 (例如，國家/地區代碼) 。 每個分割區中的機密和其他敏感資訊都會以專用金鑰加密。 建立新的分割區時，會自動產生機碼。

Azure AD 系統功能是每個使用者會話的唯一實例。 此外，Azure AD 使用加密技術，在網路層級提供共用系統資源的隔離，以防止未經授權和非預期的資訊傳輸。
