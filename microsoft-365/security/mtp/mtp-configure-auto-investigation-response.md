---
title: 在 Microsoft 365 Defender 中設定自動調查和回應功能
description: 在 Microsoft 365 Defender 中以自我修復方式設定自動調查和回應
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.date: 02/08/2021
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 05170c212e5e35d328e50dc0ee48d5f37e72869e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928661"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中設定自動調查和回應功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender 包含強大的 [自動化調查和回應功能](mtp-autoir.md) ，可節約您的安全性運作小組許多時間和精力。 透過 [自我修復](mtp-autoir.md#how-automated-investigation-and-self-healing-works)，這些功能會模仿安全性分析員調查和回應威脅的採取步驟，只會加快，而且可擴充規模的能力。 本文說明如何在 Microsoft 365 Defender 中設定自動調查和回應。

若要設定自動調查和回應功能，請遵循下列步驟：

1. [複查必要條件](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。
2. [複查或變更裝置群組的自動化層級](#review-or-change-the-automation-level-for-device-groups)。
3. 請[參閱 Office 365 中的安全性和警示原則](#review-your-security-and-alert-policies-in-office-365)。
4. [請確定已開啟 Microsoft 365 Defender](#make-sure-microsoft-365-defender-is-turned-on)。

當您全部設定後，請在重要訊息 [中心中查看和管理動作](mtp-autoir-actions.md)。

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 的自動化調查和回應必要條件

|需求 |詳細資料 |
|:----|:----|
|訂閱需求 |其中一項訂閱： <br/>-Microsoft 365 E5<br/>-Microsoft 365 A5<br/>-Microsoft 365 E5 安全性<br/>-Microsoft 365 A5 安全性<br/>-Office 365 E5 plus Enterprise 可移動性 + Security E5 加上 Windows E5<p> 請參閱 [Microsoft 365 Defender 授權需求](./prerequisites.md#licensing-requirements)。|
|網路需求 |- [Microsoft Defender](/azure-advanced-threat-protection/what-is-atp) 啟用身分識別<br/>- [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) 設定<br/>- [Microsoft Defender 用於身分識別整合](/cloud-app-security/mdi-integration) |
|Windows 電腦需求 |- Windows 10，安裝版本 1709 或更新版本 (請參閱 [Windows 10 版本資訊](/windows/release-information/)) <br/>-已設定下列威脅防護服務：<br/>- [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)<br/>- [Microsoft Defender 防病毒](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|電子郵件內容和 Office 檔案的保護 |設定[Microsoft Defender For Office 365](../office-365-security/office-365-atp.md#configure-atp-policies) |
|權限 | 若要設定自動調查和回應功能，您必須在 [Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 中或在 Microsoft 365 系統管理中心 () 中指派全域管理員或安全性系統管理員角色 [https://admin.microsoft.com](https://admin.microsoft.com) 。<p>若要取得使用自動調查和回應功能（例如審閱、核准或拒絕擱置的動作）所需的許可權，請參閱 [動作中心工作所需的許可權](mtp-action-center.md#required-permissions-for-action-center-tasks)。 |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>查看或變更裝置群組的自動化層級

是否要執行自動調查，以及是否自動採取或只在您的裝置核准時採取補救措施，取決於特定設定，例如組織的裝置群組原則。 檢查您的裝置群組原則的自動化層級集。

1. 請移至 Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。
2. 移至 [**設定**  >  **許可權**]  >  **裝置群組**。
3. 檢查您的裝置群組原則。 具體說來，請查看 [ **修正層級** ] 欄。 建議您 **自動使用完整修正威脅**。  您可能需要建立或編輯裝置群組，以取得您想要的自動化程度。 若要取得此工作的說明，請參閱下列文章：
   - [如何修正威脅](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [建立及管理裝置群組](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>在 Office 365 中複查您的安全性和警示原則

Microsoft 提供內建的 [警示原則](../../compliance/alert-policies.md) ，可協助識別特定風險。 這些風險包括 Exchange 系統管理員許可權濫用、惡意程式碼活動、潛在的外部和內部威脅，以及資訊控管風險。 某些警示可觸發 [Office 365 中的自動調查和回應](../office-365-security/office-365-air.md)。 請確定您 [的 Microsoft Defender For Office 365](../office-365-security/office-365-atp.md) 功能已正確設定。

雖然某些警示和安全性原則可以觸發自動調查，但電子郵件和內容不會自動採取任何修正動作。 相反地，電子郵件和電子郵件內容等候的所有修正動作，都是由您的安全操作小組在重要訊息 [中心](mtp-action-center.md)進行核准。

Office 365 中的安全性設定可協助保護電子郵件和內容。 若要查看或變更這些設定，請遵循 [防範威脅](../office-365-security/protect-against-threats.md)的指導方針。

1. 在 Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) 中，移至 [**原則**] [  >  **威脅防護**]。
2. 請確定已設定下列所有原則。 若要取得説明和建議，請參閱 [防止威脅](../office-365-security/protect-against-threats.md)。
   - [ (Office 365 的反惡意程式碼) ](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection)
   - [Office 365 的 Defender 中的反網路釣魚) ](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection)
   - [ (Office 365 的安全附件) ](../office-365-security/protect-against-threats.md#atp-safe-attachments-policies)
   - [ (Office 365 的安全連結) ](../office-365-security/protect-against-threats.md#atp-safe-links-policies)
   - [反垃圾郵件 (Office 365) ](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection)
3. 請確定已開啟 [Microsoft Defender For Office 365 SharePoint、OneDrive 和 Microsoft 團隊](../office-365-security/protect-against-threats.md#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) 。
4. 請確定 [電子郵件保護的零小時自動清除](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) 有效。
5.  (此步驟是選用的。 ) 在 Microsoft 365 規範中心 () 中檢查您的 [Office 365 警示原則](../../compliance/alert-policies.md) [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) 。 「威脅管理」類別中有許多預設的警示原則。 其中一些警示可以觸發自動調查和回應。 若要深入瞭解，請參閱 [預設警示原則](../../compliance/alert-policies.md#default-alert-policies)。

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>確定已開啟 Microsoft 365 Defender

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP 開啟":::

1. 請移至 Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) 並登入。
2. 在功能窗格中，尋找 **事件**、 **動作中心** 及 **搜尋**，如上圖所示。
   - 如果您看到 **事件**、 **動作中心** 及 **搜尋**，則會開啟 Microsoft 365 Defender。 請參閱本文中 () [的裝置群組，查看或變更其自動化層級](#review-or-change-the-automation-level-for-device-groups) 。
   - 如果您 *未* 看到 **事件**、 **動作中心** 或 **搜尋**，則可能無法開啟 Microsoft 365 Defender。 在此情況下，請繼續 [前往) 的「動作中心](mtp-action-center.md) 」。
3. 在功能窗格中，選擇 [**設定**  >  **Microsoft 365 Defender**]。 確認已開啟 Microsoft 365 Defender。 

> [!TIP]
> 需要協助？ 請參閱 [開啟 Microsoft 365 Defender](./mtp-enable.md)。

## <a name="next-steps"></a>後續步驟

- [Microsoft 365 Defender 中的修正動作](mtp-remediation-actions.md)
- [造訪重要訊息中心](mtp-action-center.md)