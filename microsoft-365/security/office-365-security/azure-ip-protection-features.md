---
title: Azure 資訊保護中的保護功能可向現有承租人推出
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 本文說明 Azure 資訊保護中的保護功能所要推出的變更
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77d45c8521e67c480b9e5557b05eed8ba5dd2645
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203684"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Azure 資訊保護中的保護功能可向現有承租人推出

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

若要協助您保護資訊的初始步驟，請從2018年7月開始，所有 Azure 資訊保護合格的承租人都會有預設開啟 Azure 資訊保護中的保護功能。 Azure 資訊保護中的保護功能先前在 Office 365 中稱為 Rights Management 或 Azure RMS。 如果您的組織有 Office E3 服務方案或較高的服務方案，您現在可以在推出這些功能時，透過 Azure 資訊保護來開始保護資訊。

## <a name="changes-beginning-july-1-2018"></a>從2018年7月1日開始的變更

從2018年7月1日開始，Microsoft 會針對具有下列其中一個訂閱計畫的所有組織，啟用 Azure 資訊保護中的保護功能：

- Office 365 郵件加密會提供給 Office 365 E3 和 e5、Microsoft E3 和 e5、Office 365 A1、A3 和 A5，以及 Office 365 G3 和 G5 的一部分。 您不需要其他授權，即可接收 Azure 資訊保護所支援的新保護功能。

- 您也可以將 Azure 資訊保護方案1新增至下列方案，以接收新的 Office 365 郵件加密功能： Exchange Online 計畫1、Exchange Online 方案2、Office 365 F1、Microsoft 365 商務基本版、Microsoft 365 商務標準版或 Office 365 企業版 E1。

- Office 365 郵件加密所受益的每一位使用者都必須獲得授權，才能享受功能。

- 如需完整清單，請參閱[Exchange Online 的 Office 365 郵件加密服務描述](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)。

租使用者管理員可以在 Office 365 管理員入口網站中檢查保護狀態。

![顯示 Office 365 中的版權管理的螢幕擷取畫面。](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>為什麼要進行此變更？

Office 365 郵件加密利用 Azure 資訊保護中的保護功能。 針對 Microsoft 365 中的資訊保護，最新的 Office 365 郵件加密和大量投資的核心，我們為組織開啟和使用我們的保護能力變得更容易，因為在過去，加密技術很難設定。 透過依預設開啟 Azure 資訊保護中的保護功能，您可以快速開始保護您的機密資料。

## <a name="does-this-impact-me"></a>這對我有何影響？

如果您的組織已購買合格的 Office 365 授權，則您的租使用者將會受到此變更的影響。

> [!IMPORTANT]
> 如果您在內部部署環境中使用 Active Directory Rights Management Services (AD RMS) ，您必須立即自願退出這項變更或遷移至 Azure 資訊保護，然後才會在今後30天內推出這項變更。 如需如何自願退出的資訊，請參閱「我使用 AD RMS，如何退出宣告？」 本文稍後。 如果您想要遷移，請參閱 [從 AD RMS 遷移到 Azure 資訊保護。](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>我可以搭配 Active Directory Rights Management Services (AD RMS) 使用 Azure 資訊保護嗎？

否。 這不是支援的部署案例。 若未採取其他自願取消的步驟，有些電腦可能會自動開始使用 Azure Rights Management 服務，而且也會連線到您的 AD RMS 叢集。 此案例不受支援，且結果不可靠，所以請務必在今後30天內選擇此變更，再進行這些新功能。 如需如何自願退出的資訊，請參閱「我使用 AD RMS，如何退出宣告？」 本文稍後。 如果您想要遷移，請參閱 [從 AD RMS 遷移至 Azure 資訊保護。](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>如何知道我使用的是 AD RMS？

[當您也有 Active Directory Rights Management Services (AD rms) ](/azure/information-protection/deploy-use/prepare-environment-adrms)檢查是否已部署 AD rms 時，請使用下列指示，為 Azure Rights Management 準備環境：

1. 雖然選用，大部分的 AD RMS 部署也會發佈服務連線點 (SCP) Active Directory，讓網域電腦能夠探索 AD RMS 叢集。

   使用 ADSI Edit，查看您是否已在 Active Directory 中發佈 SCP： CN=Configuration [server name]，CN=Services，CN = RightsManagementServices，CN = SCP

2. 如果您不是使用 SCP，則必須使用 Windows 登錄]，將連線至 AD RMS 叢集的 Windows 電腦設定為用戶端服務探索或授權重新導向： `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` 。

如需這些登錄設定的詳細資訊，請參閱使用 Windows 登錄和重新導向[授權伺服器流量](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)[來啟用用戶端服務探索](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry)。

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>我使用 AD RMS，我該如何退出宣告？

若要退出宣告即將進行的變更，請完成下列步驟：

1. 使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並連接至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 使用下列語法執行 Set-IRMConfiguration Cmdlet：

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>進行此變更之後，我可以預期什麼？

一旦啟用這項功能，只要您未選擇，您可以開始使用[Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801)中宣佈的新版本 Office 365 郵件加密，並利用 Azure 資訊保護的加密和保護功能。

![螢幕擷取畫面顯示 Outlook 網頁上的 OME 受保護的郵件。](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

如需新增強功能的相關資訊，請參閱[Office 365 郵件加密](../../compliance/ome.md)。