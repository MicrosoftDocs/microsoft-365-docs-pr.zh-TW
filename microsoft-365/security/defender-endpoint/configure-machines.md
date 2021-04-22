---
title: 確保您的裝置已正確設定
description: 適當設定裝置，以提升抵禦威脅的整體能力，並增強您偵測和回應攻擊的能力。
keywords: 板載，Intune management，Microsoft Defender for Endpoint，Microsoft Defender，Windows Defender，攻擊面降低，ASR，安全性基準
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3fd58ee17b2cb86c0bcc858b9b0fd57c12ac501e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932808"
---
# <a name="ensure-your-devices-are-configured-properly"></a>確保您的裝置已正確設定

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

透過適當設定的裝置，您可以提升抵禦威脅的整體能力，並增強您偵測和回應攻擊的能力。 安全性設定管理可協助確保您的裝置：

- 在 Microsoft Defender for Endpoint 上的板載
- 符合或超過 Defender for Endpoint security 基準設定
- 就地進行戰略性的攻擊面遷移

按一下流覽功能表中的 [設定 **管理** ]，以開啟 [裝置設定管理] 頁面。

![安全性設定管理頁面](images/secconmgmt_main.png)<br>
*裝置設定管理頁面*

您可以追蹤組織層級的設定狀態，並快速採取行動，以回應 Microsoft Intune 和 Microsoft 365 security center 上的裝置管理頁面直接連結，以回應不良的內架、法規遵從性問題和優化程度欠佳的攻擊面。

如此一來，您可以：
- 裝置上事件的完整可視性
- 強大的威脅智慧及強大的裝置教學技術，用來處理原始事件及識別違規活動和威脅指示器
- 設定為有效地停止安裝惡意 implants、劫持系統檔案與處理常式、資料 exfiltration 及其他威脅活動的完整安全功能堆疊
- 優化的攻擊面緩解，最大化對威脅活動的戰略性防護，同時將對生產力的影響降至最低

## <a name="enroll-devices-to-intune-management"></a>向 Intune 管理註冊裝置

裝置設定管理與 Intune 裝置管理緊密合作，以建立組織中裝置的清查和基準安全性設定。 您將能夠在 Intune 管理的 Windows 10 裝置上追蹤和管理設定問題。

在您可以確保您的裝置設定正確之前，請先將其註冊至 Intune management。 Intune 註冊很強大，且有許多 Windows 10 裝置的註冊選項。 如需 Intune 註冊選項的詳細資訊，請參閱 [設定 Windows 裝置的註冊](https://docs.microsoft.com/intune/windows-enroll)。

>[!NOTE]
>若要將 Windows 裝置註冊至 Intune，系統管理員必須已獲指派授權。 [閱讀指派裝置註冊的授權](https://docs.microsoft.com/intune/licenses-assign)。

>[!TIP] 
>若要透過 Intune 優化裝置管理，請 [將 Intune 連線至 Defender For Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。

## <a name="obtain-required-permissions"></a>取得必要的許可權
根據預設，只有已獲指派全域管理員的使用者或 Azure AD 上的 Intune 服務系統管理員角色，才能管理及指派上架裝置和部署安全性基準所需的裝置設定設定檔。

如果您已被指派其他角色，請確定您具備必要的許可權：

- 裝置設定的完整許可權
- 安全性基準的完整許可權
- 裝置合規性原則的讀取權限
- 組織的讀取權限

![Intune 上的必要許可權](images/secconmgmt_intune_permissions.png)<br>
*Intune 上的裝置設定許可權*

>[!TIP] 
>若要深入瞭解在 Intune 上指派許可權，請 [參閱建立自訂角色](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role)。

## <a name="in-this-section"></a>本節內容
主題 | 描述
:---|:---
[取得架 to Defender for Endpoint 的裝置](configure-machines-onboarding.md)| 透過 Intune 追蹤 Intune 管理裝置和板載以上裝置的內架狀態。 
[將合規性提升至 Endpoint security 基準的 Defender](configure-machines-security-baseline.md) | 追蹤基準相容性與不符合性。 將安全性基準部署到更多 Intune 管理的裝置。
[優化 ASR 規則的部署和偵測](configure-machines-asr.md) | 使用 Microsoft 365 security center 中的影響分析工具，檢查規則部署及調整偵測。

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
