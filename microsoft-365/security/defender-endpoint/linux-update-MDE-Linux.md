---
title: '如何將 Microsoft Defender for Endpoint 的更新排程為 (Linux) '
description: 瞭解如何排程 Microsoft Defender for Endpoint (Linux) 的更新，以更好地保護組織的資產。
keywords: 'microsoft、defender、Microsoft Defender for Endpoint、linux、掃描、防病毒、microsoft defender for endpoint (linux) '
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
ms.openlocfilehash: 9b7699b1a24e7e1d74a48389d02518e814911ecc
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730867"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>為於端點的 Microsoft Defender 排程更新 (Linux)

若要在 Linux 上的端點上執行 Microsoft Defender 的更新，請參閱在 [linux 上為 Microsoft defender For Endpoint 部署更新](/microsoft-365/security/defender-endpoint/linux-updates)。

Linux (和 Unix) 有一個稱為 **crontab** (的工具，類似于工作排程器，) 能夠執行排程的任務。

## <a name="pre-requisite"></a>先決條件

> [!NOTE]
> 若要取得所有時區的清單，請執行下列命令： `timedatectl list-timezones`<br>
> Timezones 的範例： <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>設定 Cron 工作
使用下列命令：

**備份 crontab 專案**

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> 其中 201118 = = YYMMDD

> [!TIP]
> 在您編輯或移除之前，請執行此動作。 <br>

若要編輯 crontab，並以根使用者的身分新增工作： <br>
`sudo crontab -e`

> [!NOTE]
> 預設編輯器為 VIM。

您可能會看到：

0 * * * */etc/opt/microsoft/mdatp/logrorate.sh

And

02 * * 週六/bin/mdatp scan quick>~/mdatp_cron_job .log

請參閱 [使用 Microsoft Defender For Endpoint (Linux 進行排程掃描) ](linux-schedule-scan-atp.md)

按下「插入」

新增下列專案：

CRON_TZ = 美洲/Los_Angeles

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>!RHEL 和變種 (CentOS 和 Oracle Linux) 

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a>!SLES 和變種

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a>!Ubuntu 和 Debian 系統

`0 6 * * sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> 在上面的範例中，我們會將它設定為00分鐘，以24小時製表示的 (小時，) ，每月的哪一天，在星期日。[$ (date + \% d) -le 15] = = 不會執行，除非其等於或小於第15天)  (第三周。 也就是說，每隔第三個星期日會在 6:00 a.m. 執行 (7) 。 太平洋 (UTC-8) 。

按下 "Esc"

輸入 "： wq" w/o 雙引號。

> [!NOTE]
> w = = write，q = = quit

若要查看您的 cron 工作，請輸入 `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="更新 MDE linux":::

若要檢查 cron 工作執行： `sudo grep mdatp /var/log/cron`

檢查 mdatp_cron_job .log `sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>針對使用 Ansible、Chef 或 Puppet 的使用者

使用下列命令：
### <a name="to-set-cron-jobs-in-ansible"></a>若要在 Ansible 中設定 cron 工作

`cron – Manage cron.d and crontab entries`

如需詳細資訊，請參閱 [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html)。

### <a name="to-set-crontabs-in-chef"></a>若要在 Chef 中設定 crontabs
`cron resource`

如需詳細資訊，請參閱 [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/)。

### <a name="to-set-cron-jobs-in-puppet"></a>若要在 Puppet 中設定 cron 工作
資源類型： cron

如需詳細資訊，請參閱 [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html)。

使用 Puppet： Cron 工作和排程任務進行自動化

如需詳細資訊，請參閱 [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/)。

## <a name="additional-information"></a>其他資訊

**使用 crontab 取得協助**

`man crontab`

**若要取得目前使用者的 crontab 檔案清單**

`crontab -l`

**若要取得另一個使用者的 crontab 檔案清單**

`crontab -u username -l`

**備份 crontab 專案**

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> 在您編輯或移除之前，請執行此動作。 <br>

**還原 crontab 專案**

`crontab /var/tmp/cron_backup.dat`

**編輯 crontab 並以根使用者的身分新增工作**

`sudo crontab -e`

**編輯 crontab 並新增工作**

`crontab -e`

**編輯其他使用者的 crontab 專案**

`crontab -u username -e`

**移除所有 crontab 專案**

`crontab -r`

**移除其他使用者的 crontab 專案**

`crontab -u username -r`

**說明**

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

