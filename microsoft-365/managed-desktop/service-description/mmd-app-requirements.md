---
title: Microsoft 受管理的電腦應用程式需求
description: ''
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278333"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft 受管理的電腦應用程式需求

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
線條的商務應用程式，您想要部署至 Microsoft 受管理的電腦裝置必須符合本主題中的需求。 

## <a name="application-condition"></a>應用程式的狀況

請務必應用程式不產生負面影響 Microsoft 受管理的桌上型電腦環境。 以下是應用程式必須符合為了讓 Microsoft，以將它部署的需求。 對於任何指定應用程式或驅動程式，Microsoft 可能撤回提及提供任何需求。 Microsoft 可能決定要移除的任何應用程式或造成負面影響效能和可靠性的 Microsoft 受管理的電腦裝置的驅動程式。

## <a name="deployable-using-microsoft-technologies"></a>可使用 Microsoft 技術部署

Microsoft 受管理的電腦使用 Intune、 Microsoft 網上商店和商務用 Microsoft Store 部署應用程式。 因此，應用程式必須封裝能夠 then 目前版本，這些服務的部署方式。

## <a name="prohibited-app-classes"></a>禁止之應用程式的類別

Microsoft 受管理的電腦裝置上不允許特定應用程式類型：
- 3rd 廠商防病毒、 安全性或稽核軟體
- 3rd 廠商網頁瀏覽器
- 在 Office 365 專業增強版之前的 Microsoft Office 版本
- 安裝或將彙整其他 3rd 廠商軟體應用程式

## <a name="restricted-app-behaviors"></a>受限制的應用程式行為

某些應用程式行為可能有害的使用者經驗或呈現 Microsoft 受管理的電腦裝置安全性風險。 應用程式應該不會出現下列行為或特性： 

使用者經驗：
- 安裝背景服務或即會衍生長時間執行背景處理程序
- 將自己新增至 Windows 啟動路徑

安全性：
- 呼叫未記載之 Windows 或 Office Api 或採取內部 Windows 或 Office 資料結構相依性
- 做為應用程式存放區，或具有內建的擴充管理員
- 提高使用者的權限
- 有已知的安全性弱點
- 使用不會縮合至受信任的根憑證簽署
- 加密或限制存取使用者資料
- 在執行階段修改作業系統的程式碼

## <a name="driver-deployment"></a>驅動程式部署

除非驅動程式在 Windows Update，或分開簽署 Windows 硬體品質實驗室 (WHQL)，Microsoft 必須核准驅動程式，Microsoft 會部署至 Microsoft 受管理的電腦裝置的驅動程式之前。
