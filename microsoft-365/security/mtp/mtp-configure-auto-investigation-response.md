---
title: 在 Microsoft 365 Defender 中設定自動調查和回應功能
description: 在 Microsoft 365 Defender 中以自我修復方式設定自動調查和回應
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: 3c8477ce16249cb4d21c736da60d619774175041
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123604"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中設定自動調查和回應功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 Defender 包含強大的 [自動化調查和回應功能](mtp-autoir.md) ，可節約您的安全性運作小組許多時間和精力。 透過自我修復，這些功能會模仿安全性分析員調查和回應威脅的採取步驟，只會加快，而且可擴充規模的能力。 本文說明如何在 Microsoft 365 Defender 中設定自動調查和回應。

若要設定自動調查和回應功能，請遵循下列步驟：

1. [複查必要條件](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。
2. [複查或變更裝置群組的自動化層級](#review-or-change-the-automation-level-for-device-groups)。
3. 請[參閱 Office 365 中的安全性和警示原則](#review-your-security-and-alert-policies-in-office-365)。
4. [請確定已開啟 Microsoft 365 Defender](#make-sure-microsoft-365-defender-is-turned-on)。

然後，在完成所有設定後，請 [複查重要訊息中心中的擱置和完成的動作](#review-pending-and-completed-actions-in-the-action-center)。 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 的自動化調查和回應必要條件

|需求 |詳細資料 |
|--|--|
|訂閱需求 |其中一個訂閱： <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5 安全性<br/>-Microsoft 365 A5 安全性<br/>-Office 365 E5 plus Enterprise 可移動性 + Security E5 加上 Windows E5<br/><br/>請參閱 [Microsoft 365 Defender 授權需求](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)。|
|網路需求 |- [Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) 啟用身分識別<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 設定<br/>- [Microsoft Cloud App Security 與 Microsoft Defender 身分識別整合](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows 電腦需求 |-已安裝 windows 10、版本1709或更新版本 (請參閱 [windows 10 版本資訊](https://docs.microsoft.com/windows/release-information/)) 設定下列的威脅防護服務：<br/>- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|電子郵件內容和 Office 檔案的保護 |設定[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
|權限 |-若要設定自動調查和回應功能，您必須在 [Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 中或在 Microsoft 365 系統管理中心 () 中指派全域管理員或安全性管理員角色 [https://admin.microsoft.com](https://admin.microsoft.com) 。<br/><br/>-若要取得使用自動調查和回應功能（例如審閱、核准或拒絕擱置的動作）所需的許可權，請參閱 [動作中心工作所需的許可權](mtp-action-center.md#required-permissions-for-action-center-tasks)。 |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>查看或變更裝置群組的自動化層級

是否要執行自動調查，以及是否自動採取或只在您的裝置核准時採取補救措施，取決於特定設定，例如組織的裝置群組原則。 檢查您的裝置群組原則的自動化層級集。

1. 請移至 Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。

2. 移至 [**設定**  >  **許可權**]  >  **裝置群組**。 

3. 檢查您的裝置群組原則。 具體說來，請查看 [ **修正層級** ] 欄。 建議您 **自動使用完整修正威脅**。  您可能需要建立或編輯裝置群組，以取得您想要的自動化程度。 若要取得此工作的說明，請參閱下列文章：

   - [如何修正威脅](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   
   - [建立及管理裝置群組](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>在 Office 365 中複查您的安全性和警示原則

Microsoft 提供內建的 [警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) ，可協助識別特定風險。 這些風險包括 Exchange 系統管理員許可權濫用、惡意程式碼活動、潛在的外部和內部威脅，以及資訊控管風險。 某些警示可觸發 [Office 365 中的自動調查和回應](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。 請確定您 [的 Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 功能已正確設定。

雖然某些警示和安全性原則可以觸發自動調查，但電子郵件和內容不會自動採取任何修正動作。 相反地，電子郵件和電子郵件內容等候的所有修正動作，都是由您的安全操作小組在重要訊息 [中心](mtp-action-center.md)進行核准。

Office 365 中的安全性設定可協助保護電子郵件和內容。 若要查看或變更這些設定，請遵循 [防範威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)的指導方針。

1. 在 Microsoft 365 security center ([https://security.microsoft.com/](https://security.microsoft.com/)) 中，移至 [**原則**] [  >  **威脅防護**]。

2. 請確定已設定下列所有原則。 若要取得説明和建議，請參閱 [防止威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。

   - [ (Office 365 的反惡意程式碼) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Office 365 的 Defender 中的反網路釣魚) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [ (Office 365 的安全附件) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [ (Office 365 的安全連結) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [反垃圾郵件 (Office 365) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. 請確定已開啟 [Microsoft Defender For Office 365 SharePoint、OneDrive 和 Microsoft 團隊](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) 。

5. 請確定 [電子郵件保護的零小時自動清除](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) 有效。 

8.  (這是選用的。 ) 在 Microsoft 365 規範中心 () 中檢查您的 [Office 365 警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) 。 「威脅管理」類別中有許多預設的警示原則。 其中一些警示可以觸發自動調查和回應。 若要深入瞭解，請參閱 [預設警示原則](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)。
 
## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>確定已開啟 Microsoft 365 Defender

1. 請移至 Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) 並登入。

2. 在功能窗格中，尋找 **事件**、 **動作中心** 及 **搜尋**，如下列影像所示：

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP 開啟":::

   - 如果您看到 **事件**、 **動作中心** 及 **搜尋**，則會開啟 Microsoft 365 Defender。 請參閱本文中 () [的裝置群組，查看或變更其自動化層級](#review-or-change-the-automation-level-for-device-groups) 。

   - 如果您 *未* 看到 **事件**、 **動作中心** 或 **搜尋**，則可能無法開啟 Microsoft 365 Defender。 在此情況下，請繼續進行下一個步驟 (查看本文中的 [擱置和完成的動作](#review-pending-and-completed-actions-in-the-action-center)) 。

3. 在功能窗格中，選擇 [**設定**  >  **Microsoft 365 Defender**]。 確認已開啟 Microsoft 365 Defender。 

   需要協助？ 請參閱 [開啟 Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)。

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>在行動中心複查擱置和完成的動作

在 Microsoft 365 Defender 中設定自動調查和回應之後，下一步是 () 中訪問 [行動中心] [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 。 您可以在這裡複查及核准暫止的動作，並查看自動採取的修復動作。 

[造訪行動中心](mtp-action-center.md)。
