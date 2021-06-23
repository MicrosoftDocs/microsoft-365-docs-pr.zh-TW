---
title: 設定 Microsoft 365 Defender 中的自動化調查和回應功能
description: 在 Microsoft 365 Defender 中以自我修復方式設定自動調查和回應
search.appverid: MET150
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 4275339e048a4197590c91c5904733ce99b22f9f
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083437"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>設定 Microsoft 365 Defender 中的自動化調查和回應功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender 包含強大的[自動化調查和回應功能](m365d-autoir.md)，可讓您的安全性運作小組很長的時間和精力加以儲存。 透過 [自我修復](m365d-autoir.md#how-automated-investigation-and-self-healing-works)，這些功能會模仿安全性分析員調查和回應威脅的採取步驟，只會加快，而且可擴充規模的能力。

本文說明如何使用下列步驟，設定 Microsoft 365 Defender 中的自動化調查和回應：

1. [複查必要條件](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。
2. [複查或變更裝置群組的自動化層級](#review-or-change-the-automation-level-for-device-groups)。
3. [在 Office 365 中檢查您的安全性和警示原則](#review-your-security-and-alert-policies-in-office-365)。
4. [請確定已開啟 Microsoft 365 Defender](#make-sure-microsoft-365-defender-is-turned-on)。

然後，當您全部設定好之後，您就可以 [在「行動中心」中查看及管理修正動作](m365d-autoir-actions.md)。

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的自動化調查和回應必要條件

<br>

****

|需求|詳細資料|
|---|---|
|訂閱需求|其中一項訂閱： <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>使用 Microsoft 365 E5 安全性附加元件 Microsoft 365 E3</li><li>使用 Microsoft 365 A5 安全性附加元件 Microsoft 365 A3</li><li>Office 365 E5 加上 Enterprise Mobility + Security E5 加上 Windows e5</li></ul> <p> 請參閱[Microsoft 365 Defender 授權要求](./prerequisites.md#licensing-requirements)。|
|網路需求|<ul><li>[Microsoft Defender](/azure-advanced-threat-protection/what-is-atp) 啟用身分識別</li><li>設定[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)</li><li>[Microsoft Defender 用於身分識別整合](/cloud-app-security/mdi-integration)</li></ul>|
|Windows 電腦需求|<ul><li>Windows 10，版本1709或更新版本已安裝 (請參閱[Windows 10 版本資訊](/windows/release-information/)) </li><li>已設定下列威脅防護服務：<ul><li>[適用於端點的 Microsoft Defender](../defender-endpoint/configure-endpoints.md)</li><li>[Microsoft Defender 防毒軟體](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|電子郵件內容和 Office 檔案的保護|設定[Office 365 的 Microsoft Defender](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies)|
|權限|若要設定自動調查和回應功能，您必須在 Azure Active Directory (<https://portal.azure.com>) 或 Microsoft 365 系統管理中心 () 中指派全域管理員或安全性系統管理員角色 <https://admin.microsoft.com> 。 <p> 若要取得使用自動調查和回應功能（例如審閱、核准或拒絕擱置的動作）所需的許可權，請參閱 [動作中心工作所需的許可權](m365d-action-center.md#required-permissions-for-action-center-tasks)。|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>查看或變更裝置群組的自動化層級

是否要執行自動調查，以及是否自動採取或只在您的裝置核准時採取補救措施，取決於特定設定，例如組織的裝置群組原則。 針對您的裝置群組原則，複查設定的自動化層級。

1. 移至 Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。

2. 移至 **設定**  >  **許可權**  >  **裝置群組**。

3. 檢查您的裝置群組原則。 具體說來，請查看 [ **修正層級** ] 欄。 建議您 **自動使用完整修正威脅**。  您可能需要建立或編輯裝置群組，以取得您想要的自動化程度。 若要取得此工作的說明，請參閱下列文章：
   - [如何修正威脅](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [建立及管理裝置群組](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>在 Office 365 中檢查您的安全性和警示原則

Microsoft 提供內建的 [警示原則](../../compliance/alert-policies.md) ，可協助識別特定風險。 這些風險包括 Exchange 系統管理許可權濫用、惡意程式碼活動、潛在的外部和內部威脅，以及資訊控管風險。 某些提醒可[在 Office 365 中觸發自動調查和回應](../office-365-security/office-365-air.md)。 請確定已正確設定[Office 365 的 Defender](../office-365-security/defender-for-office-365.md)功能。

雖然某些警示和安全性原則可以觸發自動調查，但 *電子郵件和內容不會自動採取任何修正動作*。 相反地，電子郵件和電子郵件內容等候的所有修正動作，都是由您的安全操作小組在重要訊息 [中心](m365d-action-center.md)進行核准。

Office 365 中的安全性設定可協助保護電子郵件和內容。 若要查看或變更這些設定，請遵循 [防範威脅](../office-365-security/protect-against-threats.md)的指導方針。

1. 在 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 中，移至 [原則] **& 規則** \> **威脅原則**。

2. 請確定已設定下列所有原則。 若要取得説明和建議，請參閱 [防止威脅](/microsoft-365/security/office-365-security/protect-against-threats)。
   - [反惡意程式碼](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [防網路釣魚](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
   - [安全附件](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [安全連結](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [反垃圾郵件](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)

3. 請確定已開啟[SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件](../office-365-security/mdo-for-spo-odb-and-teams.md)。

4. 請確定 Exchange Online 中的 ZAP) 會生效，[以零小時自動清除 (](../office-365-security/zero-hour-auto-purge.md) 。

5.  (此步驟是選用的。 ) 複查 Microsoft 365 合規性中心 () 中的[Office 365 警示原則](../../compliance/alert-policies.md)。 [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) 「威脅管理」類別中有許多預設的警示原則。 其中一些警示可以觸發自動調查和回應。 若要深入瞭解，請參閱 [預設警示原則](../../compliance/alert-policies.md#default-alert-policies)。

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>請確定 Microsoft 365 Defender 已開啟

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP 開啟":::

1.  () 登入 Microsoft 365 Defender 入口網站 [https://security.microsoft.com](https://security.microsoft.com) 。

2. 在功能窗格中，尋找上一個影像中所示的 **事件 & 警示**、 **搜尋** 及 **行動中心** 。
   - 如果您看到 **事件 & 警示**、**搜尋** 及 **行動中心**，Microsoft 365 Defender 會開啟。 請參閱本文的「 [複查或變更裝置群組的自動化層級](#review-or-change-the-automation-level-for-device-groups) 」一節。
   - 如果您沒有 *看到*[**事件**]、[**動作中心**] 或 [**搜尋**]，Microsoft 365 Defender 可能並未開啟。 在此情況下，請 [流覽「行動中心](m365d-action-center.md) 」) 。

3. 在功能窗格中，選擇 [**設定**  >  **Microsoft 365 Defender**]。 確認 Microsoft 365 Defender 已開啟。

> [!TIP]
> 需要協助？ 請參閱[開啟 Microsoft 365 Defender](m365d-enable.md)。

## <a name="next-steps"></a>後續步驟

- [Microsoft 365 Defender 中的修復動作](m365d-remediation-actions.md)
- [造訪重要訊息中心](m365d-action-center.md)
