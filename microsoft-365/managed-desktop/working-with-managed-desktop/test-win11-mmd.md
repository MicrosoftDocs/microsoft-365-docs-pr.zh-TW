---
title: 使用 Microsoft 受管理的電腦預覽及測試 Windows 11
description: 如何在您的環境中取得 Windows 11
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8dee18909d82656bcfb3e63fdc078328c678e660
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461384"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a>使用 Microsoft 受管理的電腦預覽及測試 Windows 11

 如何在您的 Microsoft 受管理的電腦環境內註冊並參與 Windows 11 相容性測試程式。 如需 Windows 11 和 Microsoft 受管理的電腦一般的詳細資訊，請參閱[Windows 11 及 Microsoft 受管理的電腦](../intro/win11-overview.md)。 

## <a name="check-device-eligibility"></a>檢查設備的合格性

迄今為止，95% 以上的 Microsoft 受管理的電腦裝置符合[Windows 11 的資格準則](/windows/whats-new/windows-11-requirements)。 您可以從 Microsoft 受管理的電腦要求裝置的資格狀態的詳細資料。 若要將要求歸檔，請遵循下列步驟：

1. 使用 Microsoft 受管理的電腦服務工程小組開啟新的服務要求。 如果您需要有關如何將要求歸檔的詳細資訊，請參閱 [Admin support](admin-support.md)。
2. 使用下欄欄位的值：
    - 職稱： Windows 11 裝置資格
    - 要求類型：資訊的要求
    - 類別：裝置
    - 子類別：其他


## <a name="add-devices-to-the-windows-11-test-group"></a>將裝置新增至 Windows 11 測試群組

開始新增裝置至裝置群組 (新式的 **\[ 工作區 \] Windows 11 個測試** 及評估 Windows 11 的預發行測試) 裝置。 此群組中的裝置會取得新的 Windows 11 建立並 Microsoft 受管理的電腦基準設定可供使用，並且會受到監控可靠性問題。

您可以選擇 Windows 11 個測試的任何現有或新裝置，但您不應該在此群組中登記生產裝置，因為發行前版本中的缺陷或相容性問題的風險較高。 在指派給此群組時，會移除先前的裝置群組指派。

若要在發佈前測試群組中註冊裝置：

1. 使用 Microsoft 受管理的電腦服務工程小組開啟新的服務要求。
2. 使用下欄欄位的值：
    - 職稱： Windows 11 相容性註冊
    - 要求類型：變更要求
    - 類別：裝置
    - 子類別：部署群組指派
3. 在 [描述] 欄位中，列出您要用於 Windows 11 測試的裝置序號碼。 請注意，在 Microsoft 受管理的電腦租使用者中尚未部署指定之裝置的哪一種（如果有的話）。

## <a name="prioritize-applications-to-submit-to-test-base"></a>設定提交至測試基底之應用程式的優先順序

業務關鍵型應用程式是在封閉式 Windows 11 環境中更具驗證的最佳候選人。 我們可以協助您根據使用狀況和可靠性資料，將應用程式的優先順序設為 Windows 11 的測試。 若要要求我們的建議，請遵循下列步驟：

1. 使用 Microsoft 受管理的電腦服務工程小組開啟新的服務要求。 如果您需要有關如何將要求歸檔的詳細資訊，請參閱 [Admin support](admin-support.md)。
2. 使用下欄欄位的值：
    - 職稱： Windows 11 個測試基候選項目
    - 要求類型：資訊的要求
    - 類別：應用程式
    - 子類別：其他

## <a name="report-issues"></a>報告問題

如果您遇到 Windows 11 與您的企業營運或 Microsoft 365 應用程式相容性問題，請向我們報告以進行調查和修復。 若要報告問題，請遵循下列步驟：

1. 使用 Microsoft 受管理的電腦服務工程小組開啟新的服務要求。
2. 使用下欄欄位的值：
    - 職稱： Windows 11 相容性測試
    - 要求類型：事件
    - 類別：裝置
    - 子類別： Windows 升級/更新
3. 描述行為，以及在實際執行環境中降低業務影響的程度。

Microsoft 受管理的電腦 triages，並根據對生產力的影響，處理預先發行版本本的問題。 雖然我們的服務描述並未涵蓋預先發行版本本的問題，我們還是會與客戶系統管理員協商，以確保在任何指定的租使用者中開始遷移之前，會先解決封鎖使用者生產力的問題。
