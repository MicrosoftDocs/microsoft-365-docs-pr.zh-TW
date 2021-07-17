---
title: 將 Microsoft 365 Defender 評估環境提升為生產環境、Microsoft 365 Defender 評估、試用評估、保持評估、產品評估
description: 您可以使用本文，將 evals 的 MDI、MDO、MDE 和 MCAS 提升為 Microsoft 365 Defender 或 M365D 的實際執行環境。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457908"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>將您的 Microsoft 365 Defender 評估環境推廣至實際執行環境

**適用於：**
- Microsoft 365 Defender

若要將 Microsoft 365 Defender 評估環境提升為生產環境，請先購買必要的授權。 遵循 [[建立 eval 環境](eval-create-eval-environment.md)] 中的步驟，並購買 Office 365 E5 授權 (，而不是選取 [開始免費試用版) ]。

接下來，完成任何其他設定，然後展開您的試驗群組，直到這些專案都已到達完整生產環境為止。 

## <a name="microsoft-defender-for-identity"></a>適用於身分識別的 Microsoft Defender
用於身分識別的 Defender 不需要任何其他設定。 請確認您已購買必要的授權，並已在所有 Active Directory 網域控制站和 Active Directory Federation Services (AD FS) 伺服器上安裝了該感應器。 

## <a name="microsoft-defender-for-office-365"></a>適用於 Office 365 的 Microsoft Defender
在成功評估或試驗 MDO 後，可以將它提升至整個實際執行環境。
1. 購買及布建必要的授權，並將其指派給實際執行使用者。
2. 針對您的實際執行的電子郵件網域或特定使用者群組，重新執行建議的基準原則設定 (標準或嚴格) 。
3. （選用）建立及設定您的實際執行電子郵件網域或使用者群組的任何自訂 MDO 原則。  不過，請記住，任何已指定的基準原則，都一定優先于自訂原則。
4. 更新實際執行電子郵件網域的公用 MX 記錄，以直接解析為 EOP。
5. 解除委任任何協力廠商 SMTP 閘道，並停用或刪除與此轉送相關的任何 EXO 連接器。

## <a name="microsoft-defender-for-endpoint"></a>適用於端點的 Microsoft Defender
若要將 Microsoft Defender 用於端點評估環境從試驗提升為生產環境，只需要使用任何 [支援的工具和方法](/defender-endpoint/onboard-configure)，將更多端點放入服務。

請使用下列一般指導方針，將更多裝置板載至 Microsoft Defender for Endpoint。 

1. 確認裝置可滿足 [最低需求](/defender-endpoint/minimum-requirements)。
2. 視裝置而定，請遵循在端點入口網站的 [上架] 區段中所提供的設定步驟。
3. 針對您的裝置使用適當的管理工具和部署方法。
4.  執行偵測測試，確認裝置已正確架及報表服務。

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security 不需要任何其他設定。 請務必確認您已購買必要的授權。 如果您已將部署的範圍設定為特定使用者群組，請增加這些群組的範圍，直到您達到實際執行規模為止。 

