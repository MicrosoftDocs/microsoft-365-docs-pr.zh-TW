---
title: 行動裝置管理基礎結構允出準則
description: Microsoft 365 企業版包含使用 Microsoft Intune 行動裝置管理。 檢閱需求和先決條件，設定 Intune 使用 Azure Active Directory 資源，註冊 iOS、 macOS、 Android 和 Windows 裝置，部署應用程式、 建立設定檔、 使用合規性政策，並啟用的行動裝置條件式存取使用 Microsoft 365 企業版的裝置管理。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 文件、 行動裝置管理、 Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 3e8013426983584783488e6f937f8ba5b02d7a1a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066782"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>行動裝置管理基礎結構允出準則

![階段 5：行動裝置管理](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*這適用於 Microsoft 365 企業版 E3 和 E5 版本*

請確定您的設定符合下列需求適用於行動裝置管理基礎結構。

- 已設定 Intune，包括建立 Azure Active Directory (Azure AD) 使用者和群組，將套用的裝置貴組織的規則。
- 您已在 Intune 中註冊裝置，以便這些裝置可以收到您建立的原則。
- 已將應用程式新增至裝置，讓您的使用者能夠存取貴組織的 Microsoft 365 雲端服務，例如 Exchange Online 和 Sharepoint。
- 已使用您建立的 Azure AD 使用者和群組，來設定功能和設定，並將它們套用到您的裝置，其中可能包含啟用防毒程式和限制特定應用程式。
- 合規性原則已備妥需要防火牆或裝置上的密碼長度。 如果裝置不相容，條件式存取封鎖您的組織資料的存取權。

## <a name="results-and-next-steps"></a>結果和後續步驟

您的裝置已在 Intune 中註冊，並具有適當的原則設定。

|||
|:-------|:-----|
|![階段 6：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| 如果您正在追蹤的 Microsoft 365 企業版端對端部署階段下, 一個階段是[資訊保護](infoprotect-infrastructure.md)。 |
