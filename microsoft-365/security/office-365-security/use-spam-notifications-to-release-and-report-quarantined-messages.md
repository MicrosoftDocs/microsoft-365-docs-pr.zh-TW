---
title: 利用 Office 365 中的使用者垃圾郵件通知來釋放並回報被隔離的郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: 如果您的系統管理員可讓使用者的通知，您會收到通知訊息，其中列出傳送至您的信箱已識別為垃圾郵件、 大量或網路釣魚郵件提交之郵件。 您可以釋出或回報郵件之後收到通知。
ms.openlocfilehash: fbe8a09f7da5df2df4b3b68bd524fa3ef2ed18b8
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/28/2020
ms.locfileid: "41572659"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>利用 Office 365 中的使用者垃圾郵件通知來釋放並回報被隔離的郵件

如果您的系統管理員可讓使用者的垃圾郵件通知，您會收到通知訊息，列出寄送至您信箱的已識別為垃圾郵件而遭到隔離的郵件。

> [!TIP]
> 如果您是系統管理員且想来啟用此功能，您可以選擇選項時您[修改預設的反垃圾郵件原則](configure-your-spam-filter-policies.md)。

您收到的訊息包括清單中的垃圾郵件隔離的郵件，您有的日期和時間 （全球定位時間或 UTC） 的最後一則訊息數目。 清單會包含每一封郵件的下列項目：

- **寄件者**傳送名稱和電子郵件地址將隔離的郵件。

- **主旨** 隔離之郵件的主旨行文字。

- **日期** 郵件遭隔離時的日期和時間 (UTC)。

以下是您可以對隔離的郵件採取的動作：

- **封鎖寄件者**如果您希望 Office 365 將寄件者新增至封鎖的寄件者清單。

- **版本**如果郵件不是垃圾郵件，而且您希望 Office 365 將郵件傳送至您的信箱。

- 如果您想要採取其他動作，例如預覽或版本，瀏覽至隔離區入口網站的安全性與合規性中心內的**檢閱**。

請注意下列事項：

- 因為它們符合郵件流程規則遭到隔離的郵件不會包含在使用者隔離的郵件。 該訊息只會列出因垃圾郵件而遭到隔離的郵件。

- 您只能釋出郵件並將其報告為誤判 (非垃圾郵件)   一次。
