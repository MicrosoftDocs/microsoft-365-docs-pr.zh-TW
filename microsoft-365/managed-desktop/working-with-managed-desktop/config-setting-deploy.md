---
title: 部署 Microsoft 受管理的桌上型電腦中的組態設定
description: 部署及追蹤 Microsoft 受管理的桌上型電腦中的組態設定變更。
keywords: Microsoft 受管理的桌上型電腦、 Microsoft 365、 服務、 文件、 部署、 分段的部署組態設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/12/2019
ms.openlocfilehash: fd0e0750332fa8f650cfc4756f8eb108be2a71df
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051124"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>部署及追蹤組態設定-Microsoft 受管理的桌上型電腦

您變更設定類別和階段部署之後，您可以部署及部署狀態追蹤部署進度。此頁面會顯示每個可設定的摘要。開啟 [設定類別以查看每個部署及其詳細資料，來部署所做的變更]。 

## <a name="deployment-statuses"></a>部署狀態 

這些是您會看見的每個部署雕像。

狀態  | 說明 
--- | --- 
部署 | 您的變更正在等待部署至這個響鈴。
進行中 | 變更會套用到此響鈴的裝置。 
完整 | 變更會套用到此響鈴的裝置。 
失敗 | 變更失敗 10%的響鈴的裝置上以便部署已停止。<br><br> 支援要求將會自動開啟 Microsoft 受管理的桌上型電腦每日操作來疑難排解部署。 
Csdeviceupdateconfiguration | 變更已還原成已成功部署至所有部署鈴響的最後一個修訂。

## <a name="deploy-changes"></a>部署的變更

我們將這些指示中顯示桌面背景圖片。您已分段部署之後，您部署從部署狀態的變更。 

**若要部署的變更**

1. 登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)
2. [**設定**] 下選取 [**可設定**]。
3. 在**部署狀態**工作區中，選取您想要部署的設定，然後選取要部署分段的部署。
4. 選取其中一個部署鈴響部署變更的**部署**。

![可設定的設定部署狀態概觀 （英文)](images/deploy-cs-overview.png)

Microsoft 受管理的桌上型電腦建議部署至部署鈴響順序如下： 測試、 第一個、 快速且然後廣泛。 

當每一個環內完成變更時、 狀態變更為**完成**。

![完成部署可設定的設定](images/config-setting-complete.png)

## <a name="revert-deployment"></a>回復部署

我們將這些指示中顯示桌面背景圖片。 

您已部署變更後，您可以回復從**部署狀態**。當您將回復為**進行中**或**完成**的變更時，會停止目前的部署。設定還原至最後一個已部署至所有鈴響的版本。 

**若要將回復變更**
1. 登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)
2. [**設定**] 下選取 [**可設定**]。
3. 在**部署狀態**工作區中，選取想要還原，的設定，然後選取要還原分段的部署。
4. **必須回復此變更**，請選取 [**還原部署**。

![還原組態設定部署](images/config-setting-revert.png) 

## <a name="additional-resources"></a>其他資源
- [組態設定概觀 （英文)](config-setting-overview.md)
- [可設定的設定參考 （英文)](config-setting-ref.md) 