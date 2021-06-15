---
title: Microsoft 受管理的電腦和 ITIL
description: 將 ITIL 階段與 Microsoft 受管理的電腦資訊和文章相關聯
keywords: Microsoft 受管理的電腦、Microsoft 365、服務、檔、ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: f51c99ed39e9f647f3e069c22eb3e37441f57be5
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924468"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft 受管理的電腦和 ITIL

許多組織會發現使用 (ITSM) （如 [ITIL](https://www.axelos.com/best-practice-solutions/itil)）等正規 It 服務模型的各行來組織其 it 服務是很有價值的。 

Microsoft 受管理的電腦可讓您的組織遵循這類正式 ITSM 模型的許多重要層面。 使用 ITIL 做為範例，本文可協助您查看一般 ITIL 階段與程式以及對應 Microsoft 受管理的電腦功能之間的連線（如適用）。 此資訊只適用于您組織的 Microsoft 受管理的電腦部分。

如需 ITIL 及其階段和程式的詳細資訊，請參閱其 [檔](https://www.axelos.com/best-practice-solutions/itil)。


## <a name="service-design"></a>服務設計

此表格會結合主要 ITIL 階段和程式來 Microsoft 受管理的電腦功能，並提供檔相關資訊的連結：



|ITIL 處理常式 |描述  |文件 |
|---------|---------|---------|
|服務層級管理     | 回應時間是針對系統管理支援要求和事件而定義。  |  [Microsoft 受管理的電腦的系統管理員支援](working-with-managed-desktop/admin-support.md)  |
|服務目錄管理     | 服務說明詳述服務的元件，可供所有目前及有興趣的客戶使用，以供服務的狀態。<br><br>先決條件，以瞭解操作服務所需的專案。  | - [Microsoft 受管理的電腦服務說明](service-description/index.md)<br><br>- [準備 Microsoft 受管理的電腦中的註冊](get-ready/index.md)  |
|資訊安全性管理     | 安全性資訊，包括服務的資訊安全性。<br><br> 安全相關原則及如何設定裝置的其他資訊。   | - [Microsoft 受管理的電腦中的安全性](service-description/security.md)<br><br>- [裝置設定](service-description/device-policies.md)  |
|可用性管理     |  Microsoft 受管理的電腦與組織之間的責任，以確保服務的可用性。<br><br>如果有服務或可用性問題，系統管理員和使用者都具有相關支援的路由。 | - [Microsoft 受管理的電腦作業和監控](service-description/operations-and-monitoring.md)<br><br>- [Microsoft 受管理的電腦的系統管理員支援](working-with-managed-desktop/admin-support.md)<br>- [取得使用者的協助](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>服務轉換


|ITIL 處理常式 |描述  |文件 |
|---------|---------|---------|
|變更管理     | 定義的責任、程式概述和可用變更管理相關類型的權衡。  | [Microsoft 受管理的電腦作業和監控](service-description/operations-and-monitoring.md#change-management) |
|發行和部署管理     |  Microsoft 受管理的電腦管理已登記服務中裝置的更新。  | [更新在 Microsoft 受管理的電腦中的處理方式](service-description/updates.md)        |
|服務資產和設定管理     | 有關組織 Microsoft 受管理的電腦部署的資訊可在 IT 系統管理入口網站上取得。  | [Microsoft 受管理的電腦的系統管理員支援](working-with-managed-desktop/admin-support.md) |
|知識管理     | 在此網站上，Microsoft 受管理的電腦服務的資訊會保持在最新狀態。   | [Microsoft 受管理電腦文件的變更歷程記錄](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>服務作業


|ITIL 處理常式 |描述  |文件  |
|---------|---------|---------|
|事件管理     |  提供裝置監控的詳細資料。<br><br>Microsoft 受管理的電腦服務的標準作業程式是詳述的。 |  - [Microsoft 受管理的電腦中的安全性](service-description/security.md)<br>- [Microsoft 受管理的電腦作業和監控](service-description/operations-and-monitoring.md)       |
|事件管理  | Microsoft 受管理的電腦會針對每個定義的嚴重性定義來調查和採取事件。  |  [支援要求嚴重性定義](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|要求履單管理     |  已定義與 Microsoft 受管理的電腦服務相關之資訊和變更要求的處理要求。         |[Microsoft 受管理的電腦的系統管理員支援](working-with-managed-desktop/admin-support.md)         |
|問題管理     | 目前服務的任何問題都應該導向您的本機帳戶小組。 | 開發檔 |
|存取管理     | 存取管理元件和責任，以確保功能的詳細。  | [身分識別和存取管理](service-description/security.md#identity-and-access-management)        |
