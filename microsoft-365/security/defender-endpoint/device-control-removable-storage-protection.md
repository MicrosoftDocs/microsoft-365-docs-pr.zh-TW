---
title: Microsoft Defender for Endpoint 裝置控制可移除的儲存體保護
description: 瞭解可協助防止使用者或機器或兩者（或兩者）使用未經授權的可移動儲存媒體的功能
keywords: 可移動儲存媒體
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ec5cfa78852d65db808c4e853f90f5639df25d6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300149"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint 裝置控制可移除的儲存體保護

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control Control 儲存體 Protection 可防止使用者或機器或兩者使用未經授權的可移動儲存媒體。

**Microsoft Defender for Endpoint 可移動儲存體保護**


|原則  |功能 |描述  |
|---------|---------|---------|
|裝置安裝    |  防止使用或不含排除的安裝-允許以各種屬性為基礎的特定裝置;如需詳細資訊，請參閱下列的 [裝置屬性](#device-properties) 區段。        |    在電腦上運作：不同的使用者登入相同的機器會受到相同原則的限制。 如需詳細資訊，請參閱 how [to control 使用 Microsoft Defender For Endpoint 的 USB 裝置和其他卸除式媒體](control-usb-devices-using-intune.md)。     |
|可拆卸儲存體存取控制      |  (1) 審核讀取或寫入或執行根據各種裝置屬性（包含或沒有例外）的可移動儲存區存取權。 如需詳細資訊，請參閱下列的 [裝置屬性](#device-properties) 區段。  (2) 防止讀取或寫入或執行存取，但不含排除-允許以不同裝置屬性為基礎的特定裝置;如需裝置屬性的詳細資訊，請參閱下列的 [裝置](#device-properties) 內容一節。     |     可在任何機器或使用者上運作，或在兩者上運作：僅允許特定人員對特定電腦上的特定可移動儲存體執行讀取/寫入/執行存取權;如需 Windows 中的功能，請參閱可[拆卸儲存體存取控制](device-control-removable-storage-access-control.md);如需 Mac 中的功能，請參閱[Device control for macOS](mac-device-control-overview.md)。     |
|Endpoint DLP 可拆卸儲存體      |    審核或警告或防止使用者將專案或資訊複製到卸除式媒體或 USB 裝置。     |  如需詳細資訊，請參閱 [Microsoft ENDPOINT DLP](/compliance/endpoint-dlp-learn-about.md)。       |
|BitLocker    |     封鎖要寫入未受到 BitLocker 保護之抽取式磁碟磁碟機的資料：封鎖對抽取式磁碟磁碟機的存取，除非在組織所擁有的電腦上加密。    |   如需詳細資訊，請參閱 BitLocker –[抽取式磁碟磁碟機設定](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md)。      |

## <a name="device-properties"></a>裝置內容

Microsoft Defender for Endpoint Device Control Control 儲存體 Protection 可讓您根據下表中所述的屬性限制「可拆卸儲存體存取」：


|內容名稱  |適用原則  |適用于作業系統  |描述  |
|---------|---------|---------|---------|
|裝置類別    |     [如何使用 Microsoft Defender for Endpoint 控制 USB 裝置和其他卸除式媒體](control-usb-devices-using-intune.md)     |   Windows      |  如需裝置識別碼格式的相關資訊，請參閱 [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)。 **附注**：裝置安裝可以套用至任何裝置，而不只是可移動儲存裝置。       |
|主要識別碼   |     可拆卸儲存體存取控制    |   Windows      |      主要識別碼包括「可移動儲存」和「CD/DVD」。   |
|裝置識別碼     |  [如何使用 Microsoft Defender For Endpoint 來控制 USB 裝置和其他卸除式媒體](control-usb-devices-using-intune.md);可拆卸儲存體存取控制       |      Windows   |    如需裝置識別碼格式的相關資訊，請參閱 [標準的 USB 識別碼](/windows-hardware/drivers/install/standard-usb-identifiers)，例如，USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8。      |
|硬體識別碼     |     [如何使用 Microsoft Defender For Endpoint 來控制 USB 裝置和其他卸除式媒體](control-usb-devices-using-intune.md);可拆卸儲存體存取控制    |     Windows    |    識別系統中裝置的字串，例如，USBSTOR \ DiskGeneric_Flash_Disk______8 07; **附注**：硬體識別碼不是唯一的;不同裝置可能會共用相同的值。|
|實例識別碼    | 裝置安裝;可拆卸儲存體存取控制     |     Windows    |   字串可唯一識別系統中的裝置，例如，USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8 07 \ 8735B611&0      |
|易記名稱     |     可拆卸儲存體存取控制    |   Windows      |    附加至裝置的字串，例如一般快閃磁片 USB 裝置     |
|廠商識別碼/產品識別碼     |  可拆卸儲存體存取控制       |   WindowsMac      |     [廠商識別碼] 是 USB 委員會指派給廠商的四位數廠商程式碼。 產品識別碼是廠商指派給裝置的四位數產品碼;支援萬用字元。    |
|串列 NumberId     |     可拆卸儲存體存取控制    |      WindowsMac   |     例如， <SerialNumberId>002324B534BCB431B000058A</SerialNumberId>    |

## <a name="related-topic"></a>相關主題

- [Microsoft Defender for Endpoint 裝置控制可移動儲存體存取控制](device-control-removable-storage-access-control.md)
