---
title: 管理應用程式原則
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 管理您的應用程式控管原則。
ms.openlocfilehash: 756402f86d6b65d48afb02c49b3e5bfc4e73fe3d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420094"
---
# <a name="manage-app-policies"></a>管理應用程式原則

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

為了跟上組織正在使用的最新應用程式、回應新的應用程式型攻擊以及應對應用程式合規性需求的持續變更，您可能需要透過以下方式管理您的應用程式原則：

- 建立針對新應用程式的新原則
- 變更現有原則的狀態 (使用中、非使用中、稽核模式)
- 變更現有原則的條件
- 變更現有原則的動作，以自動補救警示

以下是管理現有原則的程序範例：

1. 編輯原則：

  - 變更原則的設定。
  - 如有必要，將狀態變更為 **[稽核模式]** 以進行測試。

2. 檢查預期的行為，例如產生的警示。
1. 如果這是非預期的行為，請回到步驟 1。
1. 如果這是預期的行為，請編輯該原則，並將其狀態變更為使用中 (如果需要)。

![管理應用程式原則工作流程](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a>編輯應用程式原則設定

若要變更現有應用程式原則的設定：

- 在原則清單中選取原則，然後選取應用程式原則窗格上的 **[編輯]**。
- 在清單中選取原則的垂直省略號，然後選取 **[編輯]**。

在 **[編輯原則]** 頁面，請逐步瀏覽頁面，然後進行適當的變更：

- **描述**：變更描述，以便更容易了解此原則的用途。
- **嚴重性**
- **原則設定**： 變更要套用原則的應用程式集。 您也可以選擇使用現有條件或修改條件
- **動作**：變更由該原則產生之警示的自動補救動作。
- **狀態**：變更原則狀態。

## <a name="deleting-an-app-policy"></a>刪除應用程式原則

若要刪除應用程式原則，您可以：

- 在原則清單中選取原則，然後選取應用程式原則窗格上的 **[刪除]**。
- 在清單中選取原則的垂直省略號，然後選取 **[刪除]**。

刪除應用程式原則的替代方法是將其狀態變更為非使用中。 處於非使用中後，它將不會產生警示。 例如，與其刪除具有一組對未來原則有用之特定條件的應用程式的應用程式原則，不如重命名應用程式原則，以表明其有用性並將其狀態設定為非使用中。 您可以稍後返回到該原則並針對類似應用程式修改該原則，並將其狀態設定為稽核模式或非使用中狀態。
