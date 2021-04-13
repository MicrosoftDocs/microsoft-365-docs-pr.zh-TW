---
title: '如何將 Microsoft Defender for Endpoint 的更新排程為 (Linux) '
description: 瞭解如何排程 Microsoft Defender for Endpoint (Linux) 的更新，以更好地保護組織的資產。
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
ms.openlocfilehash: a967333a58f74938ea70e32e0c48d2decb597e98
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688798"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="8cfa7-104">為於端點的 Microsoft Defender 排程更新 (Linux)</span><span class="sxs-lookup"><span data-stu-id="8cfa7-104">Schedule an update of the Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="8cfa7-105">若要在 Linux 上的端點上執行 Microsoft Defender 的更新，請參閱在 [linux 上為 Microsoft defender For Endpoint 部署更新](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates)。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-105">To run an update on Microsoft Defender for Endpoint on Linux, see [Deploy updates for Microsoft Defender for Endpoint on Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).</span></span>

<span data-ttu-id="8cfa7-106">Linux (和 Unix) 有一個稱為 **crontab** (的工具，類似于工作排程器，) 能夠執行排程的任務。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="8cfa7-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="8cfa7-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="8cfa7-108">若要取得所有時區的清單，請執行下列命令： `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="8cfa7-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="8cfa7-109">Timezones 的範例：</span><span class="sxs-lookup"><span data-stu-id="8cfa7-109">Examples for timezones:</span></span> <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="8cfa7-110">設定 Cron 工作</span><span class="sxs-lookup"><span data-stu-id="8cfa7-110">To set the Cron job</span></span>
<span data-ttu-id="8cfa7-111">使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="8cfa7-111">Use the following commands:</span></span>

<span data-ttu-id="8cfa7-112">**備份 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> <span data-ttu-id="8cfa7-113">其中 201118 = = YYMMDD</span><span class="sxs-lookup"><span data-stu-id="8cfa7-113">Where 201118 == YYMMDD</span></span>

> [!TIP]
> <span data-ttu-id="8cfa7-114">在您編輯或移除之前，請執行此動作。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="8cfa7-115">若要編輯 crontab，並以根使用者的身分新增工作：</span><span class="sxs-lookup"><span data-stu-id="8cfa7-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="8cfa7-116">預設編輯器為 VIM。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-116">The default editor is VIM.</span></span>

<span data-ttu-id="8cfa7-117">您可能會看到：</span><span class="sxs-lookup"><span data-stu-id="8cfa7-117">You might see:</span></span>

<span data-ttu-id="8cfa7-118">0 \* \* \* \*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="8cfa7-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="8cfa7-119">And</span><span class="sxs-lookup"><span data-stu-id="8cfa7-119">And</span></span>

<span data-ttu-id="8cfa7-120">02 \* \* 週六/bin/mdatp scan quick>~/mdatp_cron_job .log</span><span class="sxs-lookup"><span data-stu-id="8cfa7-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span></span>

<span data-ttu-id="8cfa7-121">請參閱 [使用 Microsoft Defender For Endpoint (Linux 進行排程掃描) ](linux-schedule-scan-atp.md)</span><span class="sxs-lookup"><span data-stu-id="8cfa7-121">See [Schedule scans with Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span></span>

<span data-ttu-id="8cfa7-122">按下「插入」</span><span class="sxs-lookup"><span data-stu-id="8cfa7-122">Press “Insert”</span></span>

<span data-ttu-id="8cfa7-123">新增下列專案：</span><span class="sxs-lookup"><span data-stu-id="8cfa7-123">Add the following entries:</span></span>

<span data-ttu-id="8cfa7-124">CRON_TZ = 美洲/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="8cfa7-124">CRON_TZ=America/Los_Angeles</span></span>

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="8cfa7-125">!RHEL 和變種 (CentOS 和 Oracle Linux) </span><span class="sxs-lookup"><span data-stu-id="8cfa7-125">!RHEL and variants (CentOS and Oracle Linux)</span></span>

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a><span data-ttu-id="8cfa7-126">!SLES 和變種</span><span class="sxs-lookup"><span data-stu-id="8cfa7-126">!SLES and variants</span></span>

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a><span data-ttu-id="8cfa7-127">!Ubuntu 和 Debian 系統</span><span class="sxs-lookup"><span data-stu-id="8cfa7-127">!Ubuntu and Debian systems</span></span>

`06**sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> <span data-ttu-id="8cfa7-128">在上面的範例中，我們會將它設定為00分鐘，以24小時製表示的 (小時，) ，每月的哪一天，在星期日。[$ (date + \% d) -le 15] = = 不會執行，除非其等於或小於第15天)  (第三周。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-128">In the examples above, we are setting it to 00 minutes, 6 a.m.(hour in 24 hour format), any day of the month, any month, on Sundays.[$(date +\%d) -le 15] == Won’t run unless it’s equal or less than the 15th day (3rd week).</span></span> <span data-ttu-id="8cfa7-129">也就是說，每隔第三個星期日會在 6:00 a.m. 執行 (7) 。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-129">Meaning it will run every 3rd Sundays(7) of the month at 6:00 a.m.</span></span> <span data-ttu-id="8cfa7-130">太平洋 (UTC-8) 。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-130">Pacific (UTC -8).</span></span>

<span data-ttu-id="8cfa7-131">按下 "Esc"</span><span class="sxs-lookup"><span data-stu-id="8cfa7-131">Press “Esc”</span></span>

<span data-ttu-id="8cfa7-132">輸入 "： wq" w/o 雙引號。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-132">Type “:wq” w/o the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="8cfa7-133">w = = write，q = = quit</span><span class="sxs-lookup"><span data-stu-id="8cfa7-133">w == write, q == quit</span></span>

<span data-ttu-id="8cfa7-134">若要查看您的 cron 工作，請輸入 `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="8cfa7-134">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="更新 MDE linux":::

<span data-ttu-id="8cfa7-136">若要檢查 cron 工作執行： `sudo grep mdatp /var/log/cron`</span><span class="sxs-lookup"><span data-stu-id="8cfa7-136">To inspect cron job runs: `sudo grep mdatp /var/log/cron`</span></span>

<span data-ttu-id="8cfa7-137">檢查 mdatp_cron_job .log `sudo nano mdatp_cron_job.log`</span><span class="sxs-lookup"><span data-stu-id="8cfa7-137">To inspect the mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span></span>

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="8cfa7-138">針對使用 Ansible、Chef 或 Puppet 的使用者</span><span class="sxs-lookup"><span data-stu-id="8cfa7-138">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="8cfa7-139">使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="8cfa7-139">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="8cfa7-140">若要在 Ansible 中設定 cron 工作</span><span class="sxs-lookup"><span data-stu-id="8cfa7-140">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="8cfa7-141">如需詳細資訊，請參閱 [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html)。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-141">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="8cfa7-142">若要在 Chef 中設定 crontabs</span><span class="sxs-lookup"><span data-stu-id="8cfa7-142">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="8cfa7-143">如需詳細資訊，請參閱 [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/)。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-143">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="8cfa7-144">若要在 Puppet 中設定 cron 工作</span><span class="sxs-lookup"><span data-stu-id="8cfa7-144">To set cron jobs in Puppet</span></span>
<span data-ttu-id="8cfa7-145">資源類型： cron</span><span class="sxs-lookup"><span data-stu-id="8cfa7-145">Resource Type: cron</span></span>

<span data-ttu-id="8cfa7-146">如需詳細資訊，請參閱 [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html)。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-146">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="8cfa7-147">使用 Puppet： Cron 工作和排程任務進行自動化</span><span class="sxs-lookup"><span data-stu-id="8cfa7-147">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="8cfa7-148">如需詳細資訊，請參閱 [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-148">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="8cfa7-149">其他資訊</span><span class="sxs-lookup"><span data-stu-id="8cfa7-149">Additional information</span></span>

<span data-ttu-id="8cfa7-150">**使用 crontab 取得協助**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-150">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="8cfa7-151">**若要取得目前使用者的 crontab 檔案清單**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-151">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="8cfa7-152">**若要取得另一個使用者的 crontab 檔案清單**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-152">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="8cfa7-153">**備份 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-153">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="8cfa7-154">在您編輯或移除之前，請執行此動作。</span><span class="sxs-lookup"><span data-stu-id="8cfa7-154">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="8cfa7-155">**還原 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-155">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="8cfa7-156">**編輯 crontab 並以根使用者的身分新增工作**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-156">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="8cfa7-157">**編輯 crontab 並新增工作**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-157">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="8cfa7-158">**編輯其他使用者的 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-158">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="8cfa7-159">**移除所有 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-159">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="8cfa7-160">**移除其他使用者的 crontab 專案**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-160">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="8cfa7-161">**說明**</span><span class="sxs-lookup"><span data-stu-id="8cfa7-161">**Explanation**</span></span>

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

