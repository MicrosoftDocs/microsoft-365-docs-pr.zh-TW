---
title: 使用者支援
description: 說明客戶-led 和協力廠商支援的選項。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8cb1b30da84ece597235d8eef674a12208ab6456
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362647"
---
# <a name="user-support"></a>使用者支援

您的 Microsoft 受管理的電腦使用者可從您的組織取得支援 (我們呼叫這項「用戶端 led」支援) 或從選取的合作夥伴 ( 「協力廠商」支援) 。 我們的目的是為了提供使用者的一致體驗，同時讓裝置以這兩種支援選項為安全。 不論選擇哪個選項，都適用下列相同的原則： 

- 以彈性的方式整合 Microsoft 受管理的電腦裝置與您現有的支援處理常式。 
- 清晰的支援提供者、IT 系統管理員和 Microsoft 受管理的電腦之間的角色與責任 
- [定義的升級路徑](#workflow-for-support-providers)
- Microsoft 受管理的電腦提供的檔，以及入口網站，您可以在必要時要求提升裝置存取權及向支援人員上報。
- 每天 Microsoft 受管理的電腦一天內的威脅監控與緩解

## <a name="roles-and-responsibilities"></a>角色和職責

為了確保服務品質不會損除了安全性，支援提供者、IT 系統管理員和 Microsoft 受管理的電腦各有不同的角色與責任。

### <a name="support-provider"></a>支援提供者

誰為用戶端的支援 (提供支援，或為協力廠商) 的合作夥伴負責這些專案：

- 為使用者提供所有使用者支援和第一次連絡人的技術援助
- 針對您的組織或與您所選擇的支援提供者建立關聯的使用者支援，滿足所有服務等級協定
- 執行特定疑難排解動作，例如要求提升的裝置許可權，如[取得使用者的](../working-with-managed-desktop/end-user-support.md)說明所述
- 疑難排解和修正使用者問題，包括：
    - 作業系統 (Windows) 
    - 適用于企業的 Microsoft Apps
    - 瀏覽器功能
    - 裝置問題
    - 基礎結構的問題，例如印表機、驅動程式和 Vpn
    - 企業營運行業應用程式

### <a name="it-admin"></a>IT 系統管理員

您的 IT 系統管理員負責下列專案：

- 與支援提供者合作以設定及管理使用者支援的服務等級協定
- 為核准的支援人員管理更高的存取許可權。 如需詳細資訊，請參閱 [Enable user support features](../get-started/enable-support.md)
- 如果有影響多個使用者的裝置問題，請使用 Microsoft 受管理的電腦系統管理支援程式來升級。 如需詳細資訊，請參閱[Microsoft 受管理的電腦的系統管理員支援](../working-with-managed-desktop/admin-support.md)。
- 將硬體相關問題路由傳送給適當的廠商或供應商
- 防止設定我們所設定的原則，以維護和保護 Microsoft 受管理的電腦裝置上的裝置安全性原則設定。

### <a name="microsoft-managed-desktop"></a>Microsoft 受管理的電腦

身為服務提供者，我們負責下列專案：

- 提供提升裝置存取及問題升級的方法，包括檔
- 將角色與責任保持在最新的資訊中
- 依照嚴重性定義回應系統管理員支援要求
- 每天為所有已註冊的裝置提供威脅監控和緩解。

## <a name="workflow-for-support-providers"></a>支援提供者的工作流程

不論支援是由客戶導向，還是由合作夥伴打頭陣，使用者支援要求的活動流程都會遵循下列路徑：

:::image type="content" source="../../media/mmd-support-flow.png" alt-text="當使用者接觸支援時，他們會透過您設計的分層人員系統來運作。請務必指定一組支援人員，以取得提升和上報能力，稱為支援問題提升小組。針對特定的 Microsoft 受管理的電腦問題，他們可以上報給我們的運作團隊。或是其他 Microsoft 問題，可路由傳送至您現有的支援通道、整合或 Premier。硬體問題應一定會路由傳送至您已建立的提供者或供應商":::

將現有的程式與 Microsoft 受管理的電腦裝置的此工作流程整合很靈活，所以詳細資料可能會不同。 通常，支援提供者會遵循現有的以層級或移交的方式，指定具備提升許可權或將問題提升至 Microsoft 受管理的電腦作業的特定使用者。 最好將此群組保留為小於「廣泛的支援小組。

若使用者的問題需要上報至 Microsoft 受管理的電腦，識別應導向哪個小組的團隊會很有説明。 我們可以適當地傳送案例，但是會節約從開始的位置將其路由傳送至正確位置的時間。

- Microsoft 受管理的電腦 (特有的問題（例如，由服務本身所部署的原則或設定）) ：直接升級至 Operations 團隊。 如需詳細資訊，請參閱 [取得使用者的](../working-with-managed-desktop/end-user-support.md)說明。
- 硬體問題：請直接前往您的硬體廠商或廠商
- 其他問題：透過現有的支援通道上報，不論是統一訂閱還是首要訂閱。

## <a name="provided-support-framework"></a>提供支援架構


### <a name="elevation-portal"></a>提升入口網站 

由於預設會在標準使用者上執行 Microsoft 受管理的電腦裝置，因此某些工作需要提升許可權。  (如需使用者帳戶控制的詳細資訊，請參閱 [user account control](/windows/security/identity-protection/user-account-control/user-account-control-overview)) 為了讓支援人員能夠在疑難排解使用者的問題時 [執行](../working-with-managed-desktop/end-user-support.md#elevation-requests) 工作，我們提供「即時」存取系統管理員帳戶。 此密碼只會安全地以您指定的方式存取，並每隔幾小時就會旋轉。  

如需如何設定使用者存取此入口網站的步驟，請參閱 [Enable user support features](../get-started/enable-support.md)。

如需提交提升要求的步驟，請參閱「 [提升要求](../working-with-managed-desktop/end-user-support.md#elevation-requests)」。

### <a name="escalation-portal"></a>上報入口網站 

如果問題需要上報才能 Microsoft 受管理的電腦作業小組，指定的支援人員可能會直接與 IT 系統管理員支援要求進行類似。  

> [!NOTE]
> 只有嚴重度 C 支援要求可以以這種方式歸檔。 針對符合其他嚴重性描述的問題，建議您聯繫適當的 IT 系統管理員以進行檔案。 如需詳細資訊，請參閱 [支援要求嚴重性定義](../working-with-managed-desktop/admin-support.md#support-request-severity-definitions)。

如需如何設定使用者存取此入口網站的步驟，請參閱 [Enable user support features](../get-started/enable-support.md)。

如需提交呈報要求的步驟，請參閱 [呈報要求](../working-with-managed-desktop/end-user-support.md#escalation-requests)。
