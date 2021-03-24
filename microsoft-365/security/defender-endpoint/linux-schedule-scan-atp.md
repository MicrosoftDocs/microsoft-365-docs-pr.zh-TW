---
title: '如何使用 Microsoft Defender for Endpoint (Linux 來排程掃描) '
description: 瞭解如何為 Microsoft Defender for Endpoint (Linux) 排程自動掃描時間，以更好地保護組織的資產。
keywords: 'microsoft、defender、atp、linux、掃描、防病毒、microsoft defender for endpoint (linux) '
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d3f5d4c490e28c7985a0420fa5013a8e0f51a167
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059123"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="a9411-104">使用 Microsoft Defender for Endpoint (Linux) 排程掃描</span><span class="sxs-lookup"><span data-stu-id="a9411-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="a9411-105">若要執行 Linux 的掃描，請參閱 [支援的命令](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)。</span><span class="sxs-lookup"><span data-stu-id="a9411-105">To run a scan for Linux, see [Supported Commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="a9411-106">Linux (和 Unix) 有一個稱為 **crontab** (的工具，類似于工作排程器，) 能夠執行排程的任務。</span><span class="sxs-lookup"><span data-stu-id="a9411-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="a9411-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="a9411-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="a9411-108">若要取得所有時區的清單，請執行下列命令： `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="a9411-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="a9411-109">Timezones 的範例：</span><span class="sxs-lookup"><span data-stu-id="a9411-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="a9411-110">設定 Cron 工作</span><span class="sxs-lookup"><span data-stu-id="a9411-110">To set the Cron job</span></span>
<span data-ttu-id="a9411-111">使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="a9411-111">Use the following commands:</span></span>

<span data-ttu-id="a9411-112">**備份 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="a9411-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="a9411-113">其中 200919 = = YRMMDD</span><span class="sxs-lookup"><span data-stu-id="a9411-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="a9411-114">在您編輯或移除之前，請執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a9411-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="a9411-115">若要編輯 crontab，並以根使用者的身分新增工作：</span><span class="sxs-lookup"><span data-stu-id="a9411-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="a9411-116">預設編輯器為 VIM。</span><span class="sxs-lookup"><span data-stu-id="a9411-116">The default editor is VIM.</span></span>

<span data-ttu-id="a9411-117">您可能會看到：</span><span class="sxs-lookup"><span data-stu-id="a9411-117">You might see:</span></span>

<span data-ttu-id="a9411-118">0 \* \* \* \*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="a9411-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="a9411-119">按下「插入」</span><span class="sxs-lookup"><span data-stu-id="a9411-119">Press “Insert”</span></span>

<span data-ttu-id="a9411-120">新增下列專案：</span><span class="sxs-lookup"><span data-stu-id="a9411-120">Add the following entries:</span></span>

<span data-ttu-id="a9411-121">CRON_TZ = 美洲/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="a9411-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="a9411-122">0 2 \* \* 週六/bin/mdatp scan quick > ~/mdatp_cron_job .log</span><span class="sxs-lookup"><span data-stu-id="a9411-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="a9411-123">在此範例中，我們已將它設定為00分鐘，2 a.m。</span><span class="sxs-lookup"><span data-stu-id="a9411-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="a9411-124"> (小時（24小時制）) ，任何月的任何一天，在星期六。</span><span class="sxs-lookup"><span data-stu-id="a9411-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="a9411-125">也就是說，它會在 2:00 a.m. 執行週六。</span><span class="sxs-lookup"><span data-stu-id="a9411-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="a9411-126">太平洋 (UTC – 8) 。</span><span class="sxs-lookup"><span data-stu-id="a9411-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="a9411-127">按下 "Esc"</span><span class="sxs-lookup"><span data-stu-id="a9411-127">Press “Esc”</span></span>

<span data-ttu-id="a9411-128">不加雙引號，請輸入 "： wq"。</span><span class="sxs-lookup"><span data-stu-id="a9411-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="a9411-129">w = = write，q = = quit</span><span class="sxs-lookup"><span data-stu-id="a9411-129">w == write, q == quit</span></span>

<span data-ttu-id="a9411-130">若要查看您的 cron 工作，請輸入 `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="a9411-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

<span data-ttu-id="a9411-132">**檢查 cron 工作執行**</span><span class="sxs-lookup"><span data-stu-id="a9411-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="a9411-133">**檢查 mdatp_cron_job .log**</span><span class="sxs-lookup"><span data-stu-id="a9411-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="a9411-134">針對使用 Ansible、Chef 或 Puppet 的使用者</span><span class="sxs-lookup"><span data-stu-id="a9411-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="a9411-135">使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="a9411-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="a9411-136">若要在 Ansible 中設定 cron 工作</span><span class="sxs-lookup"><span data-stu-id="a9411-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="a9411-137">如需詳細資訊，請參閱 [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html)。</span><span class="sxs-lookup"><span data-stu-id="a9411-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="a9411-138">若要在 Chef 中設定 crontabs</span><span class="sxs-lookup"><span data-stu-id="a9411-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="a9411-139">如需詳細資訊，請參閱 [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/)。</span><span class="sxs-lookup"><span data-stu-id="a9411-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="a9411-140">若要在 Puppet 中設定 cron 工作</span><span class="sxs-lookup"><span data-stu-id="a9411-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="a9411-141">資源類型： cron</span><span class="sxs-lookup"><span data-stu-id="a9411-141">Resource Type: cron</span></span>

<span data-ttu-id="a9411-142">如需詳細資訊，請參閱 [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html)。</span><span class="sxs-lookup"><span data-stu-id="a9411-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="a9411-143">使用 Puppet： Cron 工作和排程任務進行自動化</span><span class="sxs-lookup"><span data-stu-id="a9411-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="a9411-144">如需詳細資訊，請參閱 [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)。</span><span class="sxs-lookup"><span data-stu-id="a9411-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="a9411-145">其他資訊</span><span class="sxs-lookup"><span data-stu-id="a9411-145">Additional information</span></span>

<span data-ttu-id="a9411-146">**使用 crontab 取得協助**</span><span class="sxs-lookup"><span data-stu-id="a9411-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="a9411-147">**若要取得目前使用者的 crontab 檔案清單**</span><span class="sxs-lookup"><span data-stu-id="a9411-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="a9411-148">**若要取得另一個使用者的 crontab 檔案清單**</span><span class="sxs-lookup"><span data-stu-id="a9411-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="a9411-149">**備份 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="a9411-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="a9411-150">在您編輯或移除之前，請執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a9411-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="a9411-151">**還原 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="a9411-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="a9411-152">**編輯 crontab 並以根使用者的身分新增工作**</span><span class="sxs-lookup"><span data-stu-id="a9411-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="a9411-153">**編輯 crontab 並新增工作**</span><span class="sxs-lookup"><span data-stu-id="a9411-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="a9411-154">**編輯其他使用者的 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="a9411-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="a9411-155">**移除所有 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="a9411-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="a9411-156">**移除其他使用者的 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="a9411-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="a9411-157">**說明**</span><span class="sxs-lookup"><span data-stu-id="a9411-157">**Explanation**</span></span>

<span data-ttu-id="a9411-158">+ —————-分鐘 (值：0– 59)  (特殊字元：，– \*/) </span><span class="sxs-lookup"><span data-stu-id="a9411-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="a9411-159">|+ ————-小時 (值：0– 23)  (特殊字元：，– \*/) </span><span class="sxs-lookup"><span data-stu-id="a9411-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="a9411-160">| |———-月中的第幾天 (值：1– 31)  (特殊字元：，– \*/L W C) </span><span class="sxs-lookup"><span data-stu-id="a9411-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="a9411-161">| | |+ ——-月 (值：1– 12)  (特殊字元：，-\*/) </span><span class="sxs-lookup"><span data-stu-id="a9411-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="a9411-162">| | | |+--星期幾 (值：0– 6)  (星期日 = 0 或 7)  (特殊字元：，-\*/L W C) </span><span class="sxs-lookup"><span data-stu-id="a9411-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="a9411-163">| | | | | \* \* \* \* \* command to 執行</span><span class="sxs-lookup"><span data-stu-id="a9411-163">| | | | |\*\*\*\*\*command to be executed</span></span>


