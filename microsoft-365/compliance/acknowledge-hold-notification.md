---
title: 確認保留通知
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何使用 Advanced eDiscovery 以透過電子郵件傳送和追蹤法律封存通知，以及監控義務狀態。
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034883"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="c3ab5-103">確認保留通知</span><span class="sxs-lookup"><span data-stu-id="c3ab5-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="c3ab5-104">當您回應法規要求或調查時，您可能需要通知保管人，他們有義務保留電子化儲存的資訊 (ESI) ，以及可能與使用中或可能的法律相關的任何材料。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="c3ab5-105">一旦傳送，法律小組必須知道每位保管人都已接收、閱讀、瞭解並同意遵循指定的指示。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="c3ab5-106">為了協助減少追蹤您的保管人的時間、成本及工作量，Advanced eDiscovery 可讓您透過電子郵件傳送和追蹤法律封存通知。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="c3ab5-107">除了電子郵件通知之外，每位保管人都可以存取個別的合規性入口網站，讓保管人得以及時瞭解其義務狀態的變更。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="c3ab5-108">電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="c3ab5-108">Email notifications</span></span>

<span data-ttu-id="c3ab5-109">發出法律封存通知之後，每位保管人都會收到包含您定義的法律持有通知及新增指示的唯一且個人化電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="c3ab5-110">請參閱如何使用內建的  [通訊編輯器](using-communications-editor.md) ，讓保管人認可其通知，或直接從電子郵件存取其規範入口網站。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="c3ab5-111">根據您的法律封存通知設定，您的保管人可能會收到下列通知：</span><span class="sxs-lookup"><span data-stu-id="c3ab5-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="c3ab5-112">**發行通知：** 傳送給您的保管人的第一個通知。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="c3ab5-113">此通知會包含您的發行指示，以及您的郵件結尾附加的保留通知。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="c3ab5-114">**提醒注意：** 若啟用，便會根據指定的頻率和間隔，將提醒通知傳送給您的保管人。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="c3ab5-115">提醒將繼續傳送，直到保管人已確認其通知，或已耗盡提醒數目為止。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="c3ab5-116">**上報通知：** 若啟用，當提醒通知已用盡時，會將呈報通知傳送給您的管理員和主管。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="c3ab5-117">系統會自動傳送上報通知，直到完成所指定的呈報數目或保管人確認其保留通知為止。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="c3ab5-118">重新 **發起通知：** 在調查過程中，如果更新保留通知的內容，則會自動將更新的通知傳送給系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="c3ab5-119">**發行通知：** 當系統管理員從案例發行時，他們會送出發行通知。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="c3ab5-120">規範入口網站</span><span class="sxs-lookup"><span data-stu-id="c3ab5-120">Compliance Portal</span></span>

<span data-ttu-id="c3ab5-121">除了電子郵件通知之外，每位保管人都可以存取唯一的規範入口網站。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="c3ab5-122">透過入口網站，每位管理員都可以查看、存取及認可其作用中保留通知。</span><span class="sxs-lookup"><span data-stu-id="c3ab5-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![管理員的合規性入口網站](../media/CustodianPortal.jpg)
