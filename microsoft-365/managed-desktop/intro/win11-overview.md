---
title: Microsoft 受管理的電腦和 Windows 11
description: 服務中 Windows 11 的使用方式和時間
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1c5f2a7f60097bb02cb11eaabd66cad88657c505
ms.sourcegitcommit: 2abc6bf9939b14a427647e88f319dbb70de49ca6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53457977"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Microsoft 受管理的電腦和 Windows 11

在 Windows 11 的宣告之後，您可能已開始規劃 Windows 11 個遷移，做為保持 Windows 10 裝置的最新狀態的一部分。 本文概述重要考慮，以及 Microsoft 受管理的電腦如何在您的環境中支援平滑轉換。 如需 Windows 11 本身的資訊，請參閱[Windows 11 簡介](/windows/whats-new/windows-11)。

如需遵循 Microsoft 受管理的電腦裝置上安裝 Windows 11 的特定步驟，請參閱[Preview 及 test Windows 11 with Microsoft 受管理的電腦](../working-with-managed-desktop/test-win11-mmd.md)。

## <a name="timeline-for-windows-11"></a>Windows 11 的時程表

Windows 11 預覽版可從2021年6月28日開始，透過 Windows 上的[有問必答計畫](/windows-insider/)。 我們預期發行版本本一般是在行事歷年2021年結束時提供。

您可以在裝置上安裝預覽組建，不論其是否 Microsoft 受管理的電腦管理。 我們將繼續同時支援 Windows 10，直到達到支援的結尾。

當您一般會有 Windows 11 時，我們會進行更多驗證測試。 我們預期2022年1月將會是 Windows 11 的 soonest，將透過我們的標準部署群組 Microsoft 受管理的電腦生產裝置。

我們會根據技術準備工作和您的業務考慮，參考並建議系統管理員針對每個租使用者開發及執行遷移計畫。

## <a name="assessing-pre-release-versions-of-windows-11"></a>評估 Windows 11 的發行前版本

95% 以上的 Microsoft 受管理的電腦裝置可享受 Windows 11，所以您可能想要在實際執行部署之前，先在測試裝置上預覽升級。 如需 Windows 11 系統需求的詳細資訊，請參閱[Windows 11 需求](/windows/whats-new/windows-11-requirements)。 您可以從 Microsoft 受管理的電腦要求裝置的資格狀態的詳細資料。

若為 Microsoft 受管理的電腦裝置，您可以要求將測試裝置新增至 **\[ 新式的 Workplace \] Windows 11 預發行測試裝置**] 裝置群組。 這個群組會接收 Windows 11 的預覽版本，以及 Microsoft 受管理的電腦的基準設定。 Microsoft 受管理的電腦不會管理 Windows 11 預覽版本的版本，所以此裝置群組的成員可能會收到比 Windows 10 裝置群組更頻繁的更新。

對於不是由 Microsoft 受管理的電腦所管理的裝置，您可以加入[Windows 的內幕程式](/windows-insider/)，下載預覽版，並取得部署 Windows 11 的指導方針。 如果您的裝置執行 Windows 11 次版本的版本，稍後將其註冊 Microsoft 受管理的電腦中，則不會回復回 Windows 10。

## <a name="support-for-pre-release-windows-11-devices"></a>支援預發行 Windows 11 裝置

任何平臺的發行前版本都期望包含在正式供貨之前能夠識別及解決的缺陷和應用程式相容性問題。 因此，我們會考慮使用 Windows 11 的發行前版本的裝置來測試裝置，但是我們會與其他環境的安全性威脅一起監控，並與其他 Microsoft 受管理的電腦裝置相同的安全性警示回應。

因為我們致力於協助您在剩餘的工作時，將您遷移至 Windows 11，所以我們建議您向您的發行前版本報告您所遇到的缺陷。 我們決定在 Windows 11 的廣泛部署中封鎖使用者生產力的缺陷，以及在 Windows 10 裝置上封鎖使用者生產力的缺陷。

## <a name="testing-application-compatibility"></a>測試應用程式相容性

應用程式相容性是任何平臺遷移中最常見的考慮，都是由於生產力中斷的可能性。 我們正在使用數種主動性和反應性的措施，協助您自信您對 Windows 11 的應用程式過渡。

### <a name="proactive-measures"></a>主動措施

**一般應用程式：** Microsoft 已廣泛測試最常見的企業應用程式，以及在 Windows 11 的組建上部署的套件。 我們與外部軟體發行者和內部產品小組合作，以解決測試期間發現的任何問題。 如需有關我們主動相容性測試工作的詳細資訊，請參閱 [應用程式相容性博客](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/)。

**企業營運應用程式：** 「[測試基底](https://www.microsoft.com/testbase)」是應用程式發行者和 IT 系統管理員可用於提交應用程式和測試案例，以在安全 Azure 環境中執行 Windows 11 個組建的虛擬機器上執行的資源。 您可以在私人 Azure 入口網站上取得每個測試執行的結果、測試洞察力及迴歸分析。 Microsoft 受管理的電腦會協助您依照應用程式使用狀況和可靠性資料，將您的企業營運應用程式優先順序設定成驗證。 如需測試基底的詳細資訊，請參閱[測試基底 Microsoft 365](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566)。

### <a name="reactive-measures"></a>反應性措施

如果您在測試或生產環境中遇到應用程式相容性問題，您可以視需要讓 [應用程式的保證](/fasttrack/products-and-capabilities) 或 FastTrack 取得支援。 在 Windows 11 中，這包括在最新作業系統組建上執行 Office、Microsoft Edge 和 Teams 應用程式的任何功能。 應用程式可直接接洽應用程式發行者，以優先處理應用程式相容性問題並加以解決。