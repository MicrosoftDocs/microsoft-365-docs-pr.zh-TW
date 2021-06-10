---
title: Windows 10 定位服務
description: 如何開啟裝置的 Windows 位置服務
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929475"
---
# <a name="windows-10-location-service"></a>Windows 10 定位服務

Microsoft 受管理的電腦中的裝置會使用 Windows Autopilot 進行註冊。 此程式可讓我們使用 Azure Active Directory 和 Microsoft Intune 進行管理。 預設會在裝置第一次開啟時停用 Windows 10 位置服務，除非在「全新體驗」期間的隱私權設定中啟用此功能。 在 Microsoft 受管理的電腦中 Autopilot 登記期間會隱藏這些設定。 如需如何設定 Autopilot 的詳細資訊，請參閱 [使用 Autopilot 的第一次執行體驗和註冊狀態頁面](esp-first-run.md)。

因此，Microsoft 受管理的電腦裝置無法取得其裝置位置，這會限制許多 Windows 功能的功能，例如時區。 如需 Windows 10 位置服務的詳細資訊，請參閱[Windows 10 位置服務和隱私權](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。

您不需要使用 location 服務來參與 Microsoft 受管理的電腦，但會限制使用者體驗。 例如，當使用者在不同的時區中工作時，裝置將無法自動判斷其所在時區。

## <a name="enable-the-location-service"></a>啟用位置服務

您可以選擇在將裝置登記至 Microsoft 受管理的電腦服務時使用 location 服務，也可以在註冊後開啟或關閉服務。

### <a name="opt-in-during-enrollment"></a>在註冊期間自願加入

您可以讓 Microsoft 受管理的電腦服務啟用位置服務。 在註冊順序期間，系統會要求您選取是否要允許在裝置上啟用 Windows 10 位置服務。

### <a name="control-the-location-service-after-enrollment"></a>在註冊後控制位置服務

您可以隨時 (或關閉) 的位置服務，方法是透過[管理入口網站](access-admin-portal.md)提交[支援要求](../working-with-managed-desktop/admin-support.md)。

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Microsoft 受管理的電腦如何設定 Windows 10 位置服務

如果您選擇使用位置服務，我們會使用必要的最低設定，而不會影響使用者的隱私權。 如需詳細資訊，請參閱[Windows 10 位置服務和隱私權](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。

Microsoft 受管理的電腦會在 **Windows 設定** 中啟用 **位置隱私權** 設定，以 **允許存取此裝置上的位置**。 使用者介面如下所示：

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Windows 設定中的位置設定":::

> [!NOTE]
> 如果您選擇使用位置服務，這只適用于 Windows 作業系統本身。 不允許應用程式使用位置服務。 每個使用者都可以選擇是否允許應用程式存取其位置。