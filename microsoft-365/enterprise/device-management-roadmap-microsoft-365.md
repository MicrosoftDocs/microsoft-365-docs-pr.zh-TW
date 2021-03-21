---
title: Microsoft 365 的裝置管理藍圖
keywords: Microsoft 365，Microsoft 365 for enterprise，Microsoft 365 檔，行動裝置管理，Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: 設定 Microsoft 365 裝置管理的藍圖。
ms.openlocfilehash: 4c37033898865372fea19ddbb53ec9c8586f27b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918963"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Microsoft 365 的裝置管理藍圖

Microsoft 365 for enterprise 包含的功能可協助您管理組織內的裝置及其應用程式。 管理行動裝置可協助您保護和保護組織的資源。

裝置管理有兩個選項：

- [Microsoft Intune](#microsoft-intune)
- [設定基本行動與安全性](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

您可以使用 Microsoft Intune，利用行動裝置管理或行動應用程式管理來管理組織的存取權。 行動裝置管理是使用者在 Intune 中「註冊」其裝置的時間。 裝置註冊後，即為受管理的裝置;因此，它可以接收您組織的原則、規則和設定。 例如，您可以安裝特定的應用程式、建立密碼原則、安裝 VPN 連線等等。

具有自己個人裝置的使用者可能不想要註冊其裝置，或由 Intune 和您組織的原則進行管理。 不過，您仍然需要保護組織的資源和資料。 在此案例中，您可以使用行動應用程式管理來保護您的應用程式。 例如，您可以使用行動應用程式管理原則，此原則要求使用者在存取裝置上的 SharePoint 線上時輸入 PIN 碼。

您也會決定要如何管理個人裝置和組織所擁有的裝置。 您可能想要視裝置的用途而異。

## <a name="basic-mobility-and-security"></a>設定基本行動與安全性

這是 Microsoft 365 內建的，可協助您保護和管理使用者的行動裝置，例如 Iphone、Ipad、Androids 和 Windows phone。 您可以建立及管理裝置安全性原則、遠端抹除裝置資料，以及檢視詳細的裝置報告。

## <a name="choose-between-the-two-options"></a>選擇兩個選項

為了協助您更進一步評估最適合您的裝置管理選項，請參閱 [Choose Basic 行動性安全性與 Intune](/office365/securitycompliance/choose-between-mdm-and-intune)。

根據您的評估，使用下列專案開始管理您的裝置：

- [Intune](/mem/intune/fundamentals/planning-guide)
- [設定基本行動與安全性](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>身分識別與裝置存取建議

Microsoft 會針對[身分識別與裝置存取](../security/office-365-security/microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。 如需裝置存取，請使用下列文章中的建議和設定：

- [必要條件](../security/office-365-security/identity-access-prerequisites.md)
- [一般身分識別與裝置存取原則](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Contoso 如何對 Microsoft 365 進行裝置管理

如需虛構但具有代表性的多國公司如何使用 Microsoft 365 雲端服務部署行動裝置管理基礎結構的資訊，請參閱 [mobile device management For Contoso](contoso-mdm.md)。