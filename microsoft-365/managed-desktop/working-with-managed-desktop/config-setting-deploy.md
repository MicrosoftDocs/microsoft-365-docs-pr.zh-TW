---
title: 在 Microsoft 受管理的電腦中部署可設定的設定
description: 在 Microsoft 受管理的電腦中部署及追蹤可設定的設定變更。
keywords: Microsoft 受管理的電腦，Microsoft 365，服務，檔，部署，分段部署，可設定的設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287792"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>部署及追蹤可設定的設定-Microsoft 受管理的電腦

變更您的設定類別及階段部署之後，部署狀態頁面可讓您開始將設定部署至群組。 此頁面會顯示每個可設定設定的摘要。 開啟設定類別後，您就可以將設定部署至群組，並追蹤這些部署的進度。

## <a name="deployment-statuses"></a>部署狀態

您會看到每個部署的狀態。

狀態 | 說明
--- | ---
部署 | 您的變更等候部署至此群組。
進行中。 | 變更會套用到此群組中的使用中裝置。
已完成 | 在此群組中所有作用中裝置上的變更已完成。
失敗 | 變更群組中的10% 作用中裝置時失敗，所以部署已停止。<br><br> 系統會自動開啟支援要求，以進行部署的疑難排解 Microsoft 受管理的電腦作業。
恢復 | 變更已還原為已成功部署至所有部署群組的最後變更。

## <a name="deploy-changes"></a>部署變更

在這些指示中，我們會顯示桌面背景圖片。 在分段部署之後，您可以從 [部署狀態] 頁面部署變更。

**若要部署變更**

1. 登入 [Microsoft 端點管理員](https://endpoint.microsoft.com/)，並流覽至 [**裝置**] 功能表
2. 尋找 [Microsoft 受管理的電腦] 區段中，選取 [**設定**]。
3. 在 [ **部署狀態** ] 工作區中，選取您要部署的設定，然後選取要部署的分段部署。
4. 選取 [ **部署** ]，將變更部署至其中一個部署群組。

> [!NOTE]
> 橙色的警告圖示會指出有一個舊的群組可供部署，因此建議您在順序中執行。

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

建議依照此順序部署至部署群組： Test、First、Fast 及寬泛。 

每個群組中的變更完成時，狀態變更為 [ **完成**]。

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>還原部署

在您部署變更之後，您可以從 **部署狀態** 還原。 當您還原 **進行中** 或 **完成** 的變更時，目前的部署會停止。 設定會還原為所有群組部署的最後一個版本。

我們將使用桌面背景圖片做為範例，顯示還原變更的步驟。 

**還原變更**

1. 登入 [Microsoft 端點管理員](https://endpoint.microsoft.com/)，並流覽至 [**裝置**] 功能表
2. 尋找 [Microsoft 受管理的電腦] 區段中，選取 [**設定**]。
3. 在 [ **部署狀態** ] 工作區中，選取您要還原的設定，然後選取要還原的分段部署。
4. 在 [ **需要回復此變更嗎？**] 下，選取 [ **還原部署**]。

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>其他資源

- [可設定的設定概述](config-setting-overview.md)
- [可設定的設定參考](config-setting-ref.md) 
