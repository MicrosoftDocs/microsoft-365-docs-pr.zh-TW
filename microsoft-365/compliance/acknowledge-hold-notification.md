---
title: 確認保留通知
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
description: ''
ms.openlocfilehash: de542ad950fce061b63aa4b2aaf37821582d7466
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2019
ms.locfileid: "39256800"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="40a8c-102">確認保留通知</span><span class="sxs-lookup"><span data-stu-id="40a8c-102">Acknowledge a hold notification</span></span> 
<span data-ttu-id="40a8c-103">當回應法規要求或調查，您可能需要告知他們義務的 custodians 來保留電子儲存資訊 (ESI) 和任何可能會與使用中或即將發生的法律專家相關的材料。</span><span class="sxs-lookup"><span data-stu-id="40a8c-103">When responding to a regulatory request or investigation, you may be required to  inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="40a8c-104">一旦傳送，法務小組必須知道每個 custodian 已接收、 讀取、 並瞭解並同意要遵循的特定的指示。</span><span class="sxs-lookup"><span data-stu-id="40a8c-104">Once sent, legal teams must know that each custodian has received, read, and understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="40a8c-105">若要協助減少時間、 成本和工作的下列設定與您 custodians 進階電子文件可讓您傳送及透過電子郵件的合法持有通知待處理。</span><span class="sxs-lookup"><span data-stu-id="40a8c-105">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="40a8c-106">除了電子郵件通知，每個 custodian 將有權存取個別的規範入口網站，讓 custodians 保持做出正確的變更為其義務狀態。</span><span class="sxs-lookup"><span data-stu-id="40a8c-106">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="40a8c-107">電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="40a8c-107">Email notifications</span></span>
<span data-ttu-id="40a8c-108">一旦已經發出法律保留的通知，每個 custodian 將會收到包含您已定義的合法持有通知唯一和個人化電子郵件，並新增指示。</span><span class="sxs-lookup"><span data-stu-id="40a8c-108">Once a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!Tip] 
> <span data-ttu-id="40a8c-109">了解如何使用內建的[通訊編輯器](using-communications-editor.md)允許您 custodians 認可其通知或直接從他們的電子郵件存取其合規性入口網站。</span><span class="sxs-lookup"><span data-stu-id="40a8c-109">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="40a8c-110">根據您的合法持有通知的設定，您 custodians，可能會收到下列注意事項：</span><span class="sxs-lookup"><span data-stu-id="40a8c-110">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="40a8c-111">**請注意發行**-這是傳送給您 custodian 的第一個明。</span><span class="sxs-lookup"><span data-stu-id="40a8c-111">**Issuance notice** - This is the first notice sent to your custodian.</span></span> <span data-ttu-id="40a8c-112">這會包含您發行指示與附加至郵件結尾的保留明。</span><span class="sxs-lookup"><span data-stu-id="40a8c-112">This will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="40a8c-113">**提醒通知**-如果啟用，提醒通知會傳送至您 custodians 根據指定的頻率和間隔。</span><span class="sxs-lookup"><span data-stu-id="40a8c-113">**Reminder notice** - If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="40a8c-114">提醒會繼續傳送直到 custodian 已認可其通知或之前已經用完的提醒數目。</span><span class="sxs-lookup"><span data-stu-id="40a8c-114">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="40a8c-115">**呈報流程通知**-如果啟用，呈報流程通知會傳送給您 custodian 和其管理員之後已經用完提醒通知。</span><span class="sxs-lookup"><span data-stu-id="40a8c-115">**Escalation notice** - If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="40a8c-116">系統會自動傳送呈報流程通知，直到已完成 alloted 擴大或 custodian 認可其保留通知。</span><span class="sxs-lookup"><span data-stu-id="40a8c-116">The system will automatically send escalation notices until the alloted escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="40a8c-117">**重新發出通知**-調查的過程中如果保留通知的內容更新，然後更新的通知會自動傳送至 custodian。</span><span class="sxs-lookup"><span data-stu-id="40a8c-117">**Reissue notice** - During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="40a8c-118">**釋放通知**-custodian 發行從這種情況時，他們將會傳送發行通知。</span><span class="sxs-lookup"><span data-stu-id="40a8c-118">**Release notice** - When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="40a8c-119">合規性入口網站</span><span class="sxs-lookup"><span data-stu-id="40a8c-119">Compliance Portal</span></span>
<span data-ttu-id="40a8c-120">除了電子郵件通知中，每個 custodian 會有唯一的合規性入口網站的存取。</span><span class="sxs-lookup"><span data-stu-id="40a8c-120">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="40a8c-121">透過入口網站中，每個 custodian 可以檢視、 存取及確認其作用中的保留通知。</span><span class="sxs-lookup"><span data-stu-id="40a8c-121">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Custodian 規範入口網站](media/CustodianPortal.jpg)
