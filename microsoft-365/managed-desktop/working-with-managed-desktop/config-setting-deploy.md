---
title: 部署 Microsoft 受管理電腦中的組態設定
description: 部署及追蹤 Microsoft 受管理電腦中的可設定的設定變更。
keywords: Microsoft 受管理的電腦、 Microsoft 365、 服務、 文件、 部署、 分段的部署中，組態設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 62a17c95f5dc6b11f446a27684c507d7aaa95b7b
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414164"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>部署及追蹤可設定-Microsoft 受管理的電腦

您變更您的設定類別和階段部署之後，您可以部署，並在部署狀態追蹤部署進度。 此頁面會顯示每個可設定] 設定的摘要。 開啟 [若要查看每個部署和其詳細資料，若要將變更部署設定類別]。 

## <a name="deployment-statuses"></a>部署狀態 

這些是您會看到每個部署雕像。

狀態  | 說明 
--- | --- 
部署 | 您的變更正在等候部署至這個週期。
進行中。 | 將變更套用至在此週期中的作用中裝置。 
已完成 | 在此週期中的所有作用中裝置上完成變更。 
失敗 | 在 [作用中的裝置通道，10%的變更失敗，導致部署已停止。<br><br> 與 Microsoft 受管理電腦作業來疑難排解部署會自動開啟支援要求。 
還原 | 變更已還原至已成功部署至所有部署週期的最後變更。

## <a name="deploy-changes"></a>將變更部署

我們會在這些指示中顯示桌面背景圖片。 已分段部署之後，您將部署來自部署狀態變更。 

**若要部署的變更**

1. 登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)
2. 在 [**設定**] 下選取 [**可設定**]。
3. 在**部署狀態**工作區中，選取您想要部署的設定，然後選取分段的部署，以部署。
4. 選取要將變更部署至下列其中一個部署週期的**部署**。

![可設定的設定部署狀態概觀](images/deploy-cs-overview.png)

Microsoft 受管理電腦建議部署至部署週期依此順序： 測試、 第一個、 快速，然後廣泛。 

在每個通道中變更完成，狀態會變更為**完成**。

![完成部署可設定的設定](images/config-setting-complete.png)

## <a name="revert-deployment"></a>回復部署

我們會在這些指示中顯示桌面背景圖片。 

您已部署變更之後，您可以還原從**部署狀態**。 當您還原為**進行中**或**完成**的變更時，會停止目前的部署。 設定將會還原至最後一個已部署至所有通道的版本。 

**若要還原的變更**
1. 登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)
2. 在 [**設定**] 下選取 [**可設定**]。
3. 在**部署狀態**工作區中，選取您想要回復，的設定，然後選取要還原分段的部署。
4. **需要回復此變更**，請選取 [**還原部署**。

![部署可設定的設定還原](images/config-setting-revert.png) 

## <a name="additional-resources"></a>其他資源
- [組態設定概觀](config-setting-overview.md)
- [可設定的設定參考](config-setting-ref.md) 