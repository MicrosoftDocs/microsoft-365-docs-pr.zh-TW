---
title: 使用報告
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917679"
---
# <a name="work-with-reports"></a>使用報告

Microsoft 受管理的桌面提供數個報告和儀表板，供組織中的系統管理員用來瞭解各項裝置的各個層面。您可以在兩個位置找到報表：在 [Microsoft 端點管理員](https://endpoint.microsoft.com) 和 [Microsoft 365 系統管理中心](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)中。 

## <a name="reports-in-microsoft-endpoint-manager"></a>Microsoft 端點管理員中的報告

Microsoft 端點管理員主控台會將數個產品的報告彙集到單一位置，以協助您監視和調查您的 Azure AD 組織 ( "租使用者" ) 設定和裝置中的問題。 Microsoft 受管理的桌面在主功能表的 [ **報告** ] 中有一個區段，您可以在此找到您已註冊之裝置的 Microsoft 受管理電腦管理相關報告。

這些報告包括：
- **受管理裝置**  > **功能更新**：此視圖顯示整個 Microsoft 受管理桌面裝置中功能更新的整體狀態。
- **受管理裝置**  > **Office 更新**：此視圖顯示整個 Microsoft 受管理的桌面裝置的 Office 更新的整體狀態。

此外，在 Microsoft 端點管理員的數個位置，您可以從其他產品群組篩選報表，以特別包含或排除 Microsoft Managed Desktop 所管理的裝置。 這些報告已整合此篩選功能：

- [所有裝置](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [裝置合規性](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [不相容的裝置](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> 自訂 Microsoft 管理的桌面角色保證只能存取 Microsoft 受管理的桌面報告。 若要存取 Microsoft Intune 管理員（如 **所有裝置**）的其他部分，請參閱 [以 microsoft Intune 為基礎的角色存取控制](/mem/intune/fundamentals/role-based-access-control)。 

## <a name="reports-in-microsoft-365-admin-center"></a>Microsoft 365 系統管理中心的報告

您可以開啟 [microsoft 365 系統管理中心](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)，然後流覽至 [ **報告** ] 並選取 [ **microsoft managed Desktop**]，以尋找 microsoft 受管理的桌面洞察力報告。 您也可以在 [主頁 [Microsoft 端點管理員](https://endpoint.microsoft.com)] 的 [ **Microsoft 受管理的桌面**] 索引標籤上，追蹤這些報告的直接連結。 

這些報告包括： 

- [使用方式深入](usage-insights.md) 瞭解您的 Microsoft 受管理桌面裝置的使用度量。
- [可靠性真知灼見](reliability-insights.md) -此視圖提供受管理裝置的健康情況摘要。
- [電池使用](battery-insights.md) 情況-此模式可顯示您環境中裝置應用程式和預計電池壽命的能量消耗資訊。
- [Windows 安全性更新真知灼見](security-update-insights.md) -此視圖會顯示 Microsoft 受管理桌面裝置之安全性更新狀態的相關資訊。

 ## <a name="inventory-data"></a>庫存資料

除了其他報告之外，您還可以匯出由 Microsoft Managed Desktop 所管理之裝置的相關資訊。 在 Microsoft **端點管理員的** [ **裝置** ] 區域中，使用 [ **匯出全部** ] 索引標籤 [下載詳細的清查報告](device-inventory-report.md)。