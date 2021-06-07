---
title: 將使用者從 Office 365 安全性與合規性中心重新導向至 Microsoft 365 規範中心
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: 瞭解如何自動將 Office 365 安全性與合規性中心使用者重新導向至 Microsoft 365 規範中心」。
ms.collection: M365-security-compliance
ms.openlocfilehash: fb667e8f19b26cbe229b3aceffe194a86133c261
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772444"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>將使用者從 Office 365 安全性與合規性中心重新導向至 Microsoft 365 規範中心

本文說明從 Office 365 安全性與合規性中心存取相容性解決方案的使用者，自動重新導向的運作方式 (protection.office.com) Microsoft 365 規範中心 (compliance.microsoft.com) 。

## <a name="what-to-expect"></a>預期的專案

根據預設，在 Office 365 安全性和合規性 (protection.office.com) 中存取下列符合性相關解決方案的所有使用者，都會啟用自動重新導向：

- 資料外洩防護 (DLP)
- 分類
- 資訊控管
- 記錄管理
- 通訊合規性 (原來的「監督」 ) 

使用者會在 Microsoft 365 規範中心內自動路由傳送至相同的相容性解決方案 (compliance.microsoft.com) 。

>[!NOTE]
>針對 Office 365 安全性與合規性中心包含的其他規範解決方案，使用者會繼續在 Microsoft 365 規範中心或 Office 365 安全性與合規性中心管理這些解決方案。 這些規範解決方案的自動重新導向功能即將推出。

這項功能和相關聯的控制項不會啟用 Microsoft Defender Office 365 的安全性功能的自動重新導向。 若要啟用安全功能的重新導向，請參閱[將帳戶從 Microsoft Defender 重新導向 Office 365 至 Microsoft 365 安全中心](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)以取得詳細資訊。

## <a name="can-i-go-back-to-using-the-former-portal"></a>可以回復使用先前的入口網站嗎？

如果有些專案無法運作，或是您沒有透過「Microsoft 365 規範中心入口網站」完成的任何專案，您可以暫時停用所有使用者的自動重新導向。

>[!IMPORTANT]
>Microsoft 365 規範中心是目前在 Office 365 安全性與合規性中心中管理之規範解決方案的取代管理入口網站。 所有的 Microsoft 365 規範解決方案都會以完全管理 Microsoft 365 規範中心。 停用 Microsoft 365 規範中心的重新導向應該是一項簡短的解決方案。

若要切換回 Office 365 安全性與合規性中心 (所有使用者的 protection.microsoft.com) ，請完成下列步驟：

1. 以全域管理員身分登入[Microsoft 365 合規性中心](https://compliance.microsoft.com)，或在 Azure Active directory 中使用具有合規性系統管理員許可權的任何帳戶。
2. 流覽至 **設定**  >  **規範中心重新定向**。
3. 將自動重新導向設定切換為 [ **關閉**]。
4. 選取 [ **停** 用並在提示時共用意見反應]。

一旦停用，使用者就不會再傳送至 compliance.microsoft.com，而且會將其導向至 Office 365 安全性與合規性中心 (protection.microsoft.com) 。 全域或合規性系統管理員可以隨時重新啟用此設定。

## <a name="related-information"></a>相關資訊

- [Microsoft 365 規範中心概述](/microsoft-365/compliance/microsoft-365-compliance-center)
