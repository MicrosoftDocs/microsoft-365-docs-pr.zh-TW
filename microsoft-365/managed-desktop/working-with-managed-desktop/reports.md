---
title: 使用報告
description: Microsoft 受管理的電腦中可用的各種報告
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729965"
---
# <a name="work-with-reports"></a>使用報告

Microsoft 受管理的電腦提供數個報告及儀表板，供組織中的系統管理員用來瞭解各設備的人口的各個層面。您可以在兩個位置找到報表：在[Microsoft 端點管理員](https://endpoint.microsoft.com)和[Microsoft 365 系統管理中心](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)。 

## <a name="reports-in-microsoft-endpoint-manager"></a>Microsoft 端點管理員中的報表

Microsoft 端點管理員主控台將數個產品的報告彙集到單一位置，以協助您監視和調查您的 Azure AD 組織 ( "承租人" ) 設定和裝置的問題。 Microsoft 受管理的桌面在主功能表的 [**報告**] 中有一個區段，您可以在其中找到您已註冊之裝置的 Microsoft 受管理的電腦管理專用報告。

這些報告包括：
- **受管理裝置**  > **功能更新**：此視圖顯示整個 Microsoft 受管理的電腦裝置中功能更新的整體狀態。
- **受管理裝置**  > **Office 更新**：此視圖顯示所有 Microsoft 受管理的電腦裝置中 Office 更新的整體狀態。

此外，在 Microsoft 端點管理員中的數個位置，您可以從其他產品群組篩選報表，以特別包含或排除 Microsoft 受管理的電腦所管理的裝置。 這些報告已整合此篩選功能：

- [所有裝置](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [裝置合規性](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [不相容的裝置](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> 自訂 Microsoft 受管理的電腦角色保證只能存取 Microsoft 受管理的電腦報告。 若要存取 Microsoft 端點管理員的其他部分，例如 **所有裝置**，請參閱 [具有 Microsoft Intune 的角色型存取控制](/mem/intune/fundamentals/role-based-access-control)。 


 ## <a name="inventory-data"></a>庫存資料

除了其他報告之外，您還可以匯出 Microsoft 受管理的電腦所管理之裝置的相關資訊。 在 Microsoft 端點管理員 **的 [** **裝置**] 區域中，使用 [**匯出全部**] 索引標籤 [下載詳細的庫存報告](device-inventory-report.md)。