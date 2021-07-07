---
title: 測試基底的功能測試
description: 如何使用現有的自動功能測試來測試應用程式的詳細資料
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322622"
---
# <a name="functional-testing"></a>功能測試

就像是軟體廠商，您現在可以使用您選擇的測試架構（透過 M365 入口網站的自助測試基底）來執行自訂功能測試。 

當我們初次啟動服務時，我們提供了現成的測試，也就是透過標準化腳本驅動的預先定義的測試集。 不過，您無法在許多獨立軟體廠商 (Isv) 上達成完整的測試範圍。 

因此，為了回應您的意見反應，我們提供的 Isv 具有上傳自動功能測試的能力。

若要使用此功能，請遵循下列步驟：

1. Upload 檔案 (二進位檔案、相依性及腳本) 為單一 .zip 套件。
2. 選擇是否要在執行的各個執行點重新開機測試虛擬機器 (Vm) 。
3. 管理腳本的可用選項。
4. 選擇要在執行期間何時套用 VM 上的 Windows 更新。

下列步驟的詳細描述如下所示：

**Upload 功能測試套件**

若要開始，請流覽至 [Upload] 頁面，在 Azure 中的 M365 入口網站的左側流覽功能表上，選取 [應用程式目錄] 中的 [Upload 新的應用程式]。 來源：

Tab 鍵 1-輸入基本資訊。 提供應用程式的名稱和版本。 在 [測試類型] 選項中，選取 ```Functional tests``` 。 

*請注意，default Out-of-Box (OOB) 選項是預設必要的。*


![選取 [功能測試] 索引標籤](Media/functional_testing_tab1.png)

索引標籤 2-透過將 zip 檔案上傳至整個測試 (二進位檔案、相依性、腳本等) 來 Upload 套件的元件。 

如需詳細資訊，請參閱 aka.ms/usl-package-outline。  (注意： Out-of-Box 測試腳本和功能測試內容都應該置於相同的 zip 檔案) 中。 目前檔案大小限制為2GB。

索引標籤 3-設定 Out-of-Box 和功能測試工作。 在這裡，選擇 (s) 的路徑，以安裝、啟動、關閉和卸載應用程式 (Out-of-Box) 以及您的所有自訂腳本執行您的功能測試的 () 的 PowerShell 腳本。 **(注意：卸載應用程式的腳本是選用的) 。**

目前，您可以上傳1到8個腳本，以進行功能測試。 如果您需要更多腳本， (請貼上批註！ ) 

![Upload 最多8個腳本搭配功能測試](Media/functional_testing_tab3.png)

 (選用) 設定安裝後的重新開機。 某些應用程式需要在安裝之後重新開機。 

```Reboot After Execution```如果您想要在執行該腳本之後重新開機，請選取 [任務] 索引標籤中的特定腳本。

索引標籤 4-選擇何時安裝 Windows 更新： Windows 更新修補程式的應用程式會在您選擇的任何腳本之前完成。 建議您在應用程式安裝之後安裝 Windows 更新，以密切模仿實際應用程式使用案例。

![Windows 更新可在特定腳本之後安裝](Media/functional_testing_tab4.png)

Tab 5-檢查並建立套件。 完成上述步驟之後，請選取 ```Create``` [完成上傳程式]。

建立套件之後，您可以檢查套件的驗證狀態。

我們會執行初始測試，以安裝、啟動、關閉和卸載應用程式。 這可讓我們驗證套件是否可以在服務上安裝錯誤。

驗證程式最多可能需要24小時。 驗證完成後，您可以在功能表上看到 [狀態] ```Manage packages``` ，這是兩個專案之一：

1. 驗證成功：套件將會針對您選取的 OS 組建，自動測試發行 Windows。
或
2. 驗證失敗：您將需要調查失敗的原因，修正問題，然後重新上傳您的套件。

您也會透過 Azure 入口網站中的通知圖示，通知您結果。
