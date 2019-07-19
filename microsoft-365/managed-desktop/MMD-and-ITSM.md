---
title: Microsoft 受管理的桌上型電腦和 ITIL
description: ''
keywords: Microsoft 受管理的電腦、 Microsoft 365、 服務、 文件、 ITISM
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: bd03331bc27b68017ced179627ec02cb95616611
ms.sourcegitcommit: c6ee468b4aeb3684d332cb79f5cd121f60f32d3e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "35795927"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft 受管理的桌上型電腦和 ITIL

許多組織會發現寶貴的結構之各行的正式 IT 服務模型 (ITSM)，例如[ITIL](https://www.axelos.com/best-practice-solutions/itil)沿著其 IT 服務。 

Microsoft 受管理的電腦可讓您的組織遵守這類正式 ITSM 模型中的許多重要層面。 使用 ITIL 為例，本主題可協助您適用，請參閱 < 常見 ITIL 階段和處理程序和相等的 Microsoft 受管理電腦功能之間的連線。 這僅適用於貴組織的 Microsoft 受管理電腦部分。

更完善的需 ITIL 與其階段程序，請參閱其[文件](https://www.axelos.com/best-practice-solutions/itil)。


## <a name="service-design"></a>服務設計

此表格相關項目索引鍵 ITIL 階段和處理程序 Microsoft 受管理電腦的功能，我們的說明文件，如需詳細資訊的連結：



|ITIL 程序 |描述  |文件 |
|---------|---------|---------|
|服務層級管理     | 回應時間被定義系統管理員支援要求和事件。  |  [Microsoft 受管理電腦的系統管理員支援](working-with-managed-desktop/admin-support.md)  |
|服務目錄管理     | True 是表示服務，可供所有目前和感客戶的狀態會保留細部元件服務的服務描述。<br><br>若要了解什麼需要營運此項服務的詳細的先決條件。  | - [Microsoft 受管理的電腦服務描述](service-description/index.md)<br><br>- [準備註冊 Microsoft 受管理電腦中](get-ready/index.md)  |
|資訊安全性管理     | 安全性資訊，包括服務的資訊安全性。<br><br> 相關的安全性原則和其他有關如何設定裝置。   | - [Microsoft 受管理電腦中的安全性](service-description/security.md)<br><br>- [裝置設定](service-description/device-policies.md)  |
|可用性管理     |  Microsoft 受管理電腦之間取得平衡責任與您的組織，以確保服務的可用性。<br><br>系統管理員和使用者具有路由到各自的支援，若有任何服務或可用性問題。 | - [Microsoft 受管理電腦作業和監控](service-description/operations-and-monitoring.md)<br><br>- [Microsoft 受管理電腦的系統管理員支援](working-with-managed-desktop/admin-support.md)<br>- [取得使用者的說明](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>服務轉換


|ITIL 程序 |描述  |文件 |
|---------|---------|---------|
|變更管理     | 定義的權衡方式責任、 程序的概觀，並變更 」 管理模型提供與相關的類型。  | [Microsoft 受管理電腦作業和監控](service-description/operations-and-monitoring.md#change-management) |
|發行及部署管理     |  Microsoft 受管理的電腦可管理的服務中註冊裝置的更新。  | [Microsoft 受管理電腦中更新的處理方式](service-description/updates.md)        |
|服務資產和設定管理     | IT 系統管理員入口網站上使用貴組織的 Microsoft 受管理電腦部署有關的資訊。  | [Microsoft 受管理電腦的系統管理員支援](working-with-managed-desktop/admin-support.md) |
|知識管理     | Microsoft 受管理的電腦服務的詳細資訊會保留在此網站上最新狀態。   | [Microsoft 受管理電腦文件的變更歷程記錄](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>服務作業


|ITIL 程序 |描述  |文件  |
|---------|---------|---------|
|事件管理     |  提供監視的裝置的詳細資訊。<br><br>Microsoft 受管理的電腦服務的標準作業程序的詳細資訊。 |  - [Microsoft 受管理電腦中的安全性](service-description/security.md)<br>- [Microsoft 受管理電腦作業和監控](service-description/operations-and-monitoring.md)       |
|事件管理  | Microsoft 受管理的電腦會調查，並對每個已定義的嚴重性定義的事件。  |  [支援要求嚴重性定義](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|要求履行管理     |  定義資訊的要求及變更要求與 Microsoft 受管理的電腦服務相關的程序。         |[Microsoft 受管理電腦的系統管理員支援](working-with-managed-desktop/admin-support.md)         |
|問題管理     | 在這個階段時，應該導向服務的任何問題您的本機的客戶團隊。 | 在開發中的文件 |
|存取管理     | 存取管理元件，以確保功能的客戶的責任的詳細資訊。  | [身分識別與存取管理](service-description/security.md#identity-and-access-management)        |
