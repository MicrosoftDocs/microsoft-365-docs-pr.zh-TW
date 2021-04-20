---
title: 移除裝置
description: 從 Microsoft 受管理的桌面管理移除裝置
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
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893734"
---
# <a name="remove-devices"></a>移除裝置

您可以使用管理入口網站，從 Microsoft Managed Desktop management 移除裝置。 此巨集指令是永久的，但是您可以遵循 [註冊步驟](../get-started/register-devices-self.md)，將其註冊至 Microsoft Managed Desktop。

當您移除裝置時，會發生下列所有情況：

- 我們會從 Autopilot 移除裝置。
- 我們會從所有「新式工作」裝置群組中移除裝置。
- 我們會從系統管理入口網站的 [ **裝置** ] 刀片式伺服器中移除裝置。

當您移除裝置時，您可以選擇同時從 Azure Active Directory (Azure AD) 和 Microsoft Intune 中移除它。
 
> [!CAUTION]
> 從 Azure AD 和 Microsoft Intune 中移除與裝置相關的物件是永久的。 如果您移除物件，您將無法從 Intune 和 Azure 入口網站中查看或管理裝置。 裝置將無法存取公司的公司資源。 如果裝置嘗試在刪除之後登入，公司資料可能會從這些資料中刪除。

1. 在 [Microsoft 端點管理員](https://endpoint.microsoft.com/)的左導覽窗格中，選取 [ **裝置** ]。
2. 尋找功能表中的 [ **Microsoft 受管理的桌面** ] 區段，然後選取 [ **裝置**]。
3. 在 [Microsoft 受管理的電腦裝置] 工作區中，選取您要刪除的裝置。
4. 選取 [ **裝置動作**]，然後選取 [刪除即時的 **裝置** ] 以移除裝置。
5. 在 [飛入] 中，複查選取的裝置，然後選取 [ **移除裝置**]。 若要同時移除 Azure AD 及 Intune 物件，請選取核取方塊。 裝置移除可能需要數分鐘才能完成。

> [!NOTE]
> 您無法移除處於 **擱置** 中註冊狀態的裝置。