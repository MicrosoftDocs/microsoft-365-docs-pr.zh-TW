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
ms.openlocfilehash: 1a1bdb449aa1d1ba12cf1de422b3e279df6c1376
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315738"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Microsoft 365 的裝置管理藍圖


Microsoft 365 for enterprise 包含的功能可協助您管理組織內的裝置及其應用程式。 管理行動裝置可協助您保護和保護組織的資源。

裝置管理有兩個選項。

## <a name="microsoft-intune"></a>Microsoft Intune

Intune 可讓您使用行動裝置管理 (MDM) 或行動應用程式管理 (MAM) ，以管理對組織存取的選項。 MDM 是使用者在 Intune 中「註冊」其裝置的時間。 註冊後，他們就是受管理的裝置，而且可以接收組織使用的任何原則、規則和設定。 例如，您可以安裝特定的應用程式、建立密碼原則、安裝 VPN 連線等等。

具有自己個人裝置的使用者可能不想要註冊其裝置，或由 Intune 和您的原則進行管理。 不過，您仍然需要保護組織的資源和資料。 在此案例中，您可以使用 MAM 來保護您的應用程式。 例如，您可以使用需要使用者在存取裝置上的 SharePoint 時輸入 PIN 碼的 MAM 原則。

您也會決定要如何管理個人或組織所擁有的裝置。 您可能想要視裝置的用途而異。 

從 [這裡](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)開始。

## <a name="basic-mobility-and-security"></a>基本行動性和安全性
 
這是 Microsoft 365 內建的，可協助您保護和管理使用者的行動裝置，例如 Iphone、Ipad、Androids 和 Windows phone。 您可以建立及管理裝置安全性原則、遠端抹除裝置資料，以及檢視詳細的裝置報告。 

從 [這裡](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)開始。
 
## <a name="identity-and-device-access-recommendations"></a>身分識別與裝置存取建議

Microsoft 會針對[身分識別與裝置存取](microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。 如需裝置存取，請使用下列文章中的建議和設定：

- [必要條件](identity-access-prerequisites.md)
- [一般身分識別與裝置存取原則](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Contoso 如何對 Microsoft 365 進行裝置管理

請參閱 Contoso Corporation （虛構但有代表性的跨國企業）如何使用 Microsoft 365 雲端服務 [部署行動裝置管理基礎結構](contoso-mdm.md) 。
