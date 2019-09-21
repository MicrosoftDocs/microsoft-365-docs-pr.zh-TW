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
ms.openlocfilehash: 1a627a0927d6ffa2244e9f3580867379ff1fbdc5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076782"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="72ecc-102">確認保留通知</span><span class="sxs-lookup"><span data-stu-id="72ecc-102">Acknowledge a hold notification</span></span> 
<span data-ttu-id="72ecc-103">當回應法規要求或調查，您可能需要通知來保留電子儲存的資訊 (ESI)，以及可能是相關法律專家作用中或即將發生任何材料其義務的 custodians。</span><span class="sxs-lookup"><span data-stu-id="72ecc-103">When responding to a regulatory request or investigation, you may be required to  inform custodians of their obligation to preserve electronically stored information (ESI) as well as any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="72ecc-104">一旦傳送，法務小組必須知道每個 custodian 已接收、 讀取、 並瞭解並同意遵守的特定指示。</span><span class="sxs-lookup"><span data-stu-id="72ecc-104">Once sent, legal teams must know that each custodian has received, read, and understood, and agreed to comply with the given instructions.</span></span>

<span data-ttu-id="72ecc-105">若要協助減少時間、 成本和工作的下列設定與您 custodians 進階電子文件可讓您傳送和待處理事項上法律保留透過電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="72ecc-105">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow-up on legal hold notifications through email.</span></span> <span data-ttu-id="72ecc-106">除了電子郵件通知，每個 custodian 也會有存取個別的規範入口網站，讓 custodians 保持做出正確的變更為其義務狀態。</span><span class="sxs-lookup"><span data-stu-id="72ecc-106">In addition to email notices, each custodian will also have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="72ecc-107">電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="72ecc-107">Email notifications</span></span>
<span data-ttu-id="72ecc-108">一旦已經發出法律保留的通知，每個 custodian 將會收到包含您已定義的合法持有通知唯一和個人化電子郵件，並新增指示。</span><span class="sxs-lookup"><span data-stu-id="72ecc-108">Once a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!Tip] 
> <span data-ttu-id="72ecc-109">了解如何使用內建的[通訊編輯器](using-communications-editor.md)允許您 custodians 認可其通知或直接從他們的電子郵件存取其合規性入口網站。</span><span class="sxs-lookup"><span data-stu-id="72ecc-109">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="72ecc-110">根據您的合法持有通知的設定，您 custodians，可能會收到下列注意事項：</span><span class="sxs-lookup"><span data-stu-id="72ecc-110">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="72ecc-111">**請注意發行**-這是傳送給您 custodian 的第一個明。</span><span class="sxs-lookup"><span data-stu-id="72ecc-111">**Issuance notice** - This is the first notice sent to your custodian.</span></span> <span data-ttu-id="72ecc-112">這會包含您發行的指示，以及附加至郵件結尾的保留明。</span><span class="sxs-lookup"><span data-stu-id="72ecc-112">This will contain your issuance instructions as well as the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="72ecc-113">**提醒通知**-如果啟用，提醒通知會傳送至您 custodians 根據指定的頻率和間隔。</span><span class="sxs-lookup"><span data-stu-id="72ecc-113">**Reminder notice** - If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="72ecc-114">提醒會繼續傳送直到 custodian 已認可其通知或之前已經用完的提醒數目。</span><span class="sxs-lookup"><span data-stu-id="72ecc-114">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="72ecc-115">**呈報流程通知**-如果啟用，呈報流程通知會傳送給您 custodian 和其管理員之後已經用完提醒通知。</span><span class="sxs-lookup"><span data-stu-id="72ecc-115">**Escalation notice** - If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="72ecc-116">系統會自動傳送呈報流程通知，直到已完成 alloted 擴大或 custodian 認可其保留通知。</span><span class="sxs-lookup"><span data-stu-id="72ecc-116">The system will automatically send escalation notices until the alloted escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="72ecc-117">**重新發出通知**-調查的過程中如果保留通知的內容更新，然後更新的通知會自動傳送至 custodian。</span><span class="sxs-lookup"><span data-stu-id="72ecc-117">**Re-issue notice** - During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="72ecc-118">**釋放通知**-custodian 發行從這種情況時，他們將會傳送發行通知。</span><span class="sxs-lookup"><span data-stu-id="72ecc-118">**Release notice** - When a custodian is released from the case, they will be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="72ecc-119">合規性入口網站</span><span class="sxs-lookup"><span data-stu-id="72ecc-119">Compliance Portal</span></span>
<span data-ttu-id="72ecc-120">除了電子郵件通知中，每個 custodian 也會有獨特的合規性入口網站的存取。</span><span class="sxs-lookup"><span data-stu-id="72ecc-120">In addition to the email notifications, each custodian will also have access to a unique Compliance Portal.</span></span> <span data-ttu-id="72ecc-121">透過入口網站中，每個 custodian 能夠檢視、 存取，並確認其作用中的保留通知。</span><span class="sxs-lookup"><span data-stu-id="72ecc-121">Through the portal, each custodian will be able to view, access, and acknowledge their active hold notifications.</span></span>

![Custodian 規範入口網站](media/CustodianPortal.jpg)
