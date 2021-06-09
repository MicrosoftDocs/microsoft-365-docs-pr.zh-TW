---
title: '如何使用 Microsoft Defender for Endpoint (Linux 來排程掃描) '
description: 瞭解如何為 Microsoft Defender for Endpoint (Linux) 排程自動掃描時間，以更好地保護組織的資產。
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
ms.openlocfilehash: 5a4beaefb2fcc12d46cf61c22644217dce1807a6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845363"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>使用 Microsoft Defender for Endpoint (Linux) 排程掃描

若要執行 Linux 的掃描，請參閱 [支援的命令](/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)。

Linux (和 Unix) 有一個稱為 **crontab** (的工具，類似于工作排程器，) 能夠執行排程的任務。

## <a name="pre-requisite"></a>先決條件

> [!NOTE]
> 若要取得所有時區的清單，請執行下列命令： `timedatectl list-timezones`<br>
> Timezones 的範例：
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>設定 Cron 工作
使用下列命令：

**備份 crontab 專案**

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> 其中 200919 = = YRMMDD

> [!TIP]
> 在您編輯或移除之前，請執行此動作。 <br>

若要編輯 crontab，並以根使用者的身分新增工作： <br>
`sudo crontab -e`

> [!NOTE]
> 預設編輯器為 VIM。

您可能會看到：

0 * * * */etc/opt/microsoft/mdatp/logrorate.sh

按下「插入」

新增下列專案：

CRON_TZ = 美洲/Los_Angeles

0 2 * * 週六/bin/mdatp scan quick > ~/mdatp_cron_job .log

> [!NOTE]
>在此範例中，我們已將它設定為00分鐘，2 a.m。  (小時（24小時制）) ，任何月的任何一天，在星期六。 也就是說，它會在 2:00 a.m. 執行週六。 太平洋 (UTC – 8) 。

按下 "Esc"

不加雙引號，請輸入 "： wq"。

> [!NOTE]
> w = = write，q = = quit

若要查看您的 cron 工作，請輸入 `sudo crontab -l`

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

**檢查 cron 工作執行**

`sudo grep mdatp /var/log/cron`

**檢查 mdatp_cron_job .log**

`sudo nano mdatp_cron_job.log`

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

+ —————-分鐘 (值：0– 59)  (特殊字元：，– */)   <br>
|+ ————-小時 (值：0– 23)  (特殊字元：，– */)  <br>
| |———-月中的第幾天 (值：1– 31)  (特殊字元：，– */L W C)   <br>
| | |+ ——-月 (值：1– 12)  (特殊字元：，-*/)   <br>
| | | |+--星期幾 (值：0– 6)  (星期日 = 0 或 7)  (特殊字元：，-*/L W C)  <br>
| | | | | * * * * * command to 執行


