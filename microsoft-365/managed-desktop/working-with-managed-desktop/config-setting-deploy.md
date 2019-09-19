---
title: 部署 Microsoft 受管理電腦中的組態設定
description: 部署及追蹤 Microsoft 受管理電腦中的可設定的設定變更。
keywords: Microsoft 受管理的電腦、 Microsoft 365、 服務、 文件、 部署、 分段的部署中，組態設定
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5b6a2756514e94cb4f96141d6e7c9f6f2a6dd7ff
ms.sourcegitcommit: a4657a499967751d4c2dfc6cd1904258ab8be193
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2019
ms.locfileid: "37040791"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>部署及追蹤可設定-Microsoft 受管理的電腦

變更您設定的分類和階段部署之後，[部署狀態] 頁面可讓您開始部署您的設定群組。 此頁面會顯示每個可設定] 設定的摘要。 藉由開啟設定類別您可以將設定部署至群組，並追蹤這些部署中的進度。

## <a name="deployment-statuses"></a>部署狀態 

這些是您會看到每個部署狀態。

狀態  | 說明 
--- | --- 
部署 | 您的變更正在等候部署至這個群組。
進行中。 | 變更會套用到此群組中的作用中裝置。 
已完成 | 變更此群組中的所有作用中裝置上已完成。 
失敗 | 在群組中的作用中裝置的 10%的變更失敗，導致部署已停止。<br><br> 與 Microsoft 受管理電腦作業來疑難排解部署會自動開啟支援要求。 
還原 | 變更已還原至已成功部署至所有部署群組的最後變更。

## <a name="deploy-changes"></a>將變更部署

我們會在這些指示中顯示桌面背景圖片。 您已分段部署之後，您部署從 [部署狀態] 頁面上的變更。 

**若要部署的變更**

1. 登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)
2. 在 [**設定**] 下選取 [**可設定**]。
3. 在**部署狀態**工作區中，選取您想要部署的設定，然後選取分段的部署，以部署。
4. 選取要將變更部署至其中一個部署群組的**部署**。

![可設定的設定部署狀態概觀](images/1deployedit.png)Microsoft 受管理電腦建議部署至依此順序部署群組： 測試、 第一個、 快速，然後廣泛。 

當變更完成每個群組中時，狀態會變更為**完成**。

![完成部署可設定的設定](images/2completeedit.png)

## <a name="revert-deployment"></a>回復部署

您已部署變更之後，您可以還原從**部署狀態**。 當您還原為**進行中**或**完成**的變更時，會停止目前的部署。 設定會回復至最後一個已部署至所有群組的版本。 

我們將顯示還原使用桌面背景圖片做為範例變更的步驟。 

**若要還原的變更**
1. 登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)
2. 在 [**設定**] 下選取 [**可設定**]。
3. 在**部署狀態**工作區中，選取您想要回復，的設定，然後選取要還原分段的部署。
4. **需要回復此變更**，請選取 [**還原部署**。

![部署可設定的設定還原](images/3revert.png) 

## <a name="additional-resources"></a>其他資源
- [組態設定概觀](config-setting-overview.md)
- [可設定的設定參考](config-setting-ref.md) 
