---
title: 在 Microsoft 受管理的電腦中部署可設定的設定
description: 在 Microsoft 受管理的電腦中部署及追蹤可設定的設定變更。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔、部署、分段部署、可設定的設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: bfa769cab9f8d812fa2533232f66b0d4f8a4edb7
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390510"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>部署及追蹤可設定的設定-Microsoft 受管理的電腦

在您變更設定類別和階段部署之後, 部署狀態頁面可讓您開始將設定部署至群組。 此頁面會顯示每個可設定設定的摘要。 開啟設定類別後, 您就可以將設定部署至群組, 並追蹤這些部署的進度。

## <a name="deployment-statuses"></a>部署狀態 

這些是您將會看到的每個部署的 statues。

狀態  | 說明 
--- | --- 
部署 | 您的變更正等待部署至此群組。
進行中。 | 此群組中的作用中裝置會套用變更。 
已完成 | 此群組中所有使用中裝置的變更都已完成。 
失敗 | 在群組中的 10% 裝置上, 變更失敗, 因此部署已停止。<br><br> 系統會自動使用 Microsoft 受管理的桌面作業開啟支援, 以疑難排解部署。 
回 | 變更已還原至已成功部署至所有部署群組的最後變更。

## <a name="deploy-changes"></a>部署變更

我們會在這些指示中顯示桌面背景圖片。 分段部署後, 您就可以從 [部署狀態] 頁面部署變更。 

**部署變更**

1. 登入[Microsoft 受管理的桌面管理入口網站](http://aka.ms/mwaasportal)
2. 在 [設定] 下, 選取 [**可****設定**]。
3. 在 [**部署狀態**工作區] 中, 選取您要部署的設定, 然後選取要部署的分段部署。
4. 選取 [**部署**], 將變更部署至其中一個部署群組。

![可設定的設定部署狀態概述](images/deploy-cs-overview.png)

Microsoft 受管理的桌面建議依此順序部署至部署群組: Test、First、Fast、後的範圍。 

當每個群組中的變更完成時, 狀態會變更為 [已**完成**]。

![可設定的設定部署完成](images/config-setting-complete.png)

## <a name="revert-deployment"></a>還原部署

在您部署變更之後, 您可以從**部署狀態**回復。 當您回復正在**進行**或已**完成**的變更時, 目前的部署會停止。 此設定會回復至已部署至所有群組的最後一個版本。 

我們將使用桌面背景圖片做為範例, 示範回復變更的步驟。 

**回復變更**
1. 登入[Microsoft 受管理的桌面管理入口網站](http://aka.ms/mwaasportal)
2. 在 [設定] 下, 選取 [**可****設定**]。
3. 在 [**部署狀態**工作區] 中, 選取您要還原的設定, 然後選取要還原的分段部署。
4. 在 [**需要回復此變更**] 下, 選取 [**還原部署**]。

![可設定的設定部署還原](images/config-setting-revert.png) 

## <a name="additional-resources"></a>其他資源
- [可設定的設定概述](config-setting-overview.md)
- [可設定的設定參考](config-setting-ref.md) 
