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
ms.openlocfilehash: a80616b58298ba544b9eab1d19ffb77f0e6825d4
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921347"
---
# <a name="work-with-reports"></a>使用報告

Microsoft Managed Desktop 提供數種報告與儀表板，讓貴組織的 IT 系統管理員能夠使用這些報表和儀表板，瞭解裝置人口的各個層面。您可以在兩個位置找到報告 [：Microsoft Endpoint Manager](https://endpoint.microsoft.com) 和 [Microsoft 365 系統管理中心](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)。 

## <a name="reports-in-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager 中的報告

Microsoft Endpoint Manager 主控台將多個產品的報告彙集到單一位置，可協助監控和調查 Azure AD 組織 ("租使用者") 和裝置的問題。 Microsoft Managed 桌上出版在主功能表中的報表下有一個區段，您可以在此找到 Microsoft Managed Desktop 管理您註冊裝置的特定報告。

這些報告包括：
- **受管理的裝置**  > **功能更新**：此視圖會顯示您 Microsoft 受管理之桌面裝置上功能更新的整體狀態。
- **受管理的裝置**  > **Office 更新**：此視圖會顯示您 Microsoft 受管理之桌面裝置上 Office 更新的整體狀態。

此外，在 Microsoft Endpoint Manager 的數個位置中，您可以篩選來自其他產品群組的報告，以特別包含或排除由 Microsoft Managed Desktop 管理的裝置。 這些報告已整合此篩選功能：

- [所有裝置](https://docs.microsoft.com/mem/intune/remote-actions/device-management#get-to-your-devices)
- [裝置合規性](https://docs.microsoft.com/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [不相容的裝置](https://docs.microsoft.com/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> 自訂 Microsoft Managed Desktop 角色保證只能存取 Microsoft Managed Desktop 報表。 若要存取 Microsoft Endpoint Manager 的其他部分，例如所有裝置，請參閱[使用 Microsoft Intune 的角色型存取控制](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)。 

## <a name="reports-in-microsoft-365-admin-center"></a>Microsoft 365 系統管理中心報告

您可以開啟 Microsoft [365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)系統管理中心，然後流覽至報告並選取 Microsoft Managed  Desktop，以尋找 **Microsoft Managed Desktop 深入資訊報告**。 您也可以從首頁 Microsoft Endpoint Manager 上的 **Microsoft Managed Desktop** Tab，追蹤這些報告 [的直接連結](https://endpoint.microsoft.com)。 

這些報告包括： 

- [使用方式深入資訊](usage-insights.md) - 此視圖提供您 Microsoft 管理之桌面裝置的使用計量。
- [可靠性深入資訊](reliability-insights.md) - 此視圖提供受管理裝置的健康狀態摘要。
- [電池深入資訊](battery-insights.md) - 此視圖會顯示關於您環境中裝置之應用程式和預計電池使用時間的資訊。
- [Windows 安全性更新深入資訊](security-update-insights.md) - 此視圖會顯示您 Microsoft 受管理之桌面裝置安全性更新狀態的資訊。

 ## <a name="inventory-data"></a>庫存資料

除了其他報告之外，您還可以匯出 Microsoft Managed Desktop 所管理之裝置的資訊。 在Microsoft Endpoint Manager 的裝置 **區域** 之裝置視圖中，使用匯出所有的按鈕 [來下載詳細的庫存報告](device-inventory-report.md)。
