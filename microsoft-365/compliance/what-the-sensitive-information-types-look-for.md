---
title: 敏感資訊類型在找什麼
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 安全&amp;合规性中心中的数据丢失防护 （DLP） 包括 80 种敏感信息类型，可供您在 DLP 策略中使用。 本主题列出所有这些敏感信息类型，并显示 DLP 策略在检测每种类型时查找的内容。
ms.openlocfilehash: 820bab0a128f952cf5d96208f5d561f4994bd859
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077639"
---
# <a name="what-the-sensitive-information-types-look-for"></a>敏感資訊類型在找什麼

Office 365 安全&amp;合规性中心中的数据丢失防护 （DLP） 包括许多敏感信息类型，可供您在 DLP 策略中使用。 本主题列出所有这些敏感信息类型，并显示 DLP 策略在检测每种类型时查找的内容。 敏感信息类型由由正则表达式或函数标识的模式定义。 此外，关键字和校验和等确凿证据可用于识别敏感信息类型。 置信度和接近度也用于评估过程。
  
## <a name="aba-routing-number"></a>ABA 路由号码

### <a name="format"></a>格式

9 位数字，可能采用格式化或未格式化的模式

### <a name="pattern"></a>模式

格式 化：
- 四位数字以 0、1、2、3、6、7 或 8 开头
- 连字符
- 四位数字
- 连字符
- 数字

未格式化：9 个连续数字，以 0、1、2、3、6、7 或 8 开头 

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_aba_路由查找与模式匹配的内容。
- 找到关键字_ABA_路由的关键字。

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>關鍵字

#### <a name="keyword_aba_routing"></a>关键字_ABA_路由

- 阿坝
- 阿坝#
- aba 路由#
- aba 路由编号
- 阿坝#
- 阿巴路由#
- 阿巴数
- aba路由编号
- 美国银行协会路由#
- 美国银行协会路由号码
- 美国银行协会路由#
- 美国银行协会路由号码
- 银行路由编号
- 银行路由#
- 银行路由编号
- 路由传输编号
- RTN 
   
## <a name="argentina-national-identity-dni-number"></a>阿根廷国民身份 （DNI） 编号

### <a name="format"></a>格式

按句点分隔的八位数字

### <a name="pattern"></a>模式

八位数字：
- 两位数字
- 一个期间
- 三位数字
- 一个期间
- 三位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_argentina_national_id 查找与模式匹配的内容。
- 找到关键字_argentina_national_id 的关键字。

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_argentina_national_id"></a>关键字_argentina_national_id

- 阿根廷国民身份号码 
- 身分識別 
- 身份证明国民身份证 
- DNI 
- 国家个人登记处 
- 国家身份文献 
- 国家个人登记局 
- 身份 
- 身份识别 
   
## <a name="australia-bank-account-number"></a>澳大利亚银行帐号

### <a name="format"></a>格式

6-10 位数字，带或不带银行州分行号码

### <a name="pattern"></a>模式

帐号为 6-10 位。
澳大利亚银行州分行编号：
- 三位数字 
- 连字符 
- 三位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_australia_bank_帐户_编号查找与模式匹配的内容。
- 找到关键字_澳大利亚_银行_帐户_编号的关键字。
- 正则表达式 Regex_australia_bank_帐户_number_bsb 查找与模式匹配的内容。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_australia_bank_帐户_编号查找与模式匹配的内容。
- 找到关键字_澳大利亚_银行_帐户_编号的关键字。

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_bank_account_number"></a>关键词_澳大利亚_银行_帐户_编号

- 快速银行代码
- 代理银行
- 基础货币
- usa 帐户
- 持有人地址
- 银行地址
- 信息账户
- 资金转账
- 银行手续费
- 银行详细信息
- 银行信息
- 全名
- 国际 原子能 机构

   
## <a name="australia-drivers-license-number"></a>澳大利亚驾照号码

### <a name="format"></a>格式

九个字母和数字

### <a name="pattern"></a>模式

九个字母和数字： 

- 两位数字或字母（不区分大小写） 
- 两位数字 
- 五位数字或字母（不区分大小写）

或

- 1-2 个可选字母（不区分大小写） 
- 4-9 位

或

- 九位数字或字母（不区分大小写）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_australia_驱动程序_许可证_编号查找与模式匹配的内容。
- 找到关键字_澳大利亚_驱动程序_许可证_编号的关键字。
- 找不到关键字_澳大利亚_驱动程序_许可证_数字_排除项中未找到关键字。

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_drivers_license_number"></a>关键词_澳大利亚_驱动程序_许可证_编号

- 国际驾驶证
- 澳大利亚汽车协会
- 国际驾照
- 驾驶执照
- 驾驶执照
- 司机李克
- 驾驶执照
- 驾驶执照
- 驱动程序
- 司机执照
- 驾驶执照
- 司机许可证
- 司机利茨
- 驾驶执照
- 驾驶执照
- 司机'Lic
- 司机的Lics
- 驾驶执照
- 驾驶执照
- 司机的许可证
- 司机的Lics
- 驾驶执照
- 驾驶执照
- 驾驶员的
- 驾驶员的
- 驾驶执照
- 驾驶执照
- 驾驶员的许可证
- 司机的许可证
- 驾驶执照
- 驾驶执照
- 司机#
- 司机#
- 驾驶执照#
- 驾驶执照#
- 司机李克#
- 司机利茨#
- 驾驶执照#
- 驾驶执照#
- 驱动程序#
- 司机Lics#
- 司机执照#
- 驾驶执照#
- 司机许可证#
- 司机利茨#
- 驾驶执照#
- 驾驶执照#
- 司机'Lic#
- 司机的Lics#
- 驾驶执照#
- 驾驶执照#
- 司机的许可证#
- 司机的Lics#
- 驾驶执照#
- 驾驶执照#
- 驾驶员的#
- 驾驶员的#
- 驾驶执照#
- 驾驶执照#
- 驾驶员的许可证#
- 司机的许可证#
- 驾驶执照#
- 驾驶执照# 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>关键词_澳大利亚_驱动程序_许可证_数字_排除

- Aaa
- 驾驶执照
- 驾驶执照
- 驾照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照#
- 驾驶执照#
- 驾照#
- 驾驶执照#
- 驾驶执照#
- 驾驶执照#
- 驾驶执照#
- 驾驶执照#
- 驾驶执照#
- 驾驶执照#
- 驾驶执照#
- 驾驶执照#
- 驾驶执照#
- 驾驶执照#
- 驾驶执照#
- 驾驶执照#
   
## <a name="australia-medical-account-number"></a>澳大利亚医疗帐号

### <a name="format"></a>格式

10-11 位

### <a name="pattern"></a>模式

10-11 位：
- 第一个数字在 2-6 范围内
- 第九位数字是校验数字
- 第十位是问题数字
- 第十一位（可选）是单个数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 95% 确信检测到这种类型的敏感信息：
- 函数 Func_australian_medical_帐户_编号查找与模式匹配的内容。
- 找到关键字"澳大利亚"_医疗+帐户_编号的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_australian_medical_帐户_编号查找与模式匹配的内容。
- 校验和通过。

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_medical_account_number"></a>关键词_澳大利亚_医疗+帐户_号码

- 银行账户详细信息
- 医疗保险付款
- 抵押帐户
- 银行付款
- 信息分支
- 信用卡贷款
- 人类服务部
- 本地服务
- 医疗

   
## <a name="australia-passport-number"></a>澳大利亚护照号码

### <a name="format"></a>格式

后跟七位数字的字母

### <a name="pattern"></a>模式

字母（不区分大小写）后跟七位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_australia_Passport_number 查找与模式匹配的内容。
- 找到关键字_护照或关键字_澳大利亚_护照_号码的关键字。

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_passport"></a>关键词_护照

- 护照号码
- 护照号
- 护照#
- 护照#
- 护照ID
- 护照诺
- 护照号码
- ·
- ·\\\\\\\\\\\\\\\\\\\\\\
- * * * *
- [ ] 
- 努梅罗·德·德费波特
- 路路港 n |
- 路路港非
- 帕塞波特#
- 帕塞波特#
- 帕塞波特农
- 帕塞波特 |

#### <a name="keyword_australia_passport_number"></a>关键词_澳大利亚_护照_号码

- 护照
- 护照详情
- 移民和公民身份
- 澳大利亚联邦
- 移民部
- 住宅地址
- 移民和公民部
- 签证
- 国民身份证
- 护照号码
- 旅行证件
- 颁发机构
   
## <a name="australia-tax-file-number"></a>澳大利亚税务档案号码

### <a name="format"></a>格式

8-9 位

### <a name="pattern"></a>模式

8-9 位数字通常以空格显示，如下所示：
- 三位数字 
- 可选空间 
- 三位数字 
- 可选空间 
- 2-3 位数字，其中最后一个数字是校验数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_australian_tax_file_number 查找与模式匹配的内容。
- 找不到关键字"澳大利亚_澳大利亚"_税务_文件_数字或关键字_数字_排除项中未找到关键字。
- 校验和通过。

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_australia_tax_file_number"></a>关键词_澳大利亚_税_文件_数字

- 澳大利亚业务编号
- 边际税率
- 医疗保险税
- 投资组合编号
- 服役退伍军人
- 预扣税
- 个人纳税申报表
- 税文件编号

#### <a name="keyword_number_exclusions"></a>关键字_数字_排除

- 00000000
- 11111111
- 22222222
- 33333333
- 44444444
- 55555555
- 66666666
- 77777777
- 88888888
- 99999999
- 000000000
- 111111111
- 222222222
- 333333333
- 444444444
- 555555555
- 666666666
- 777777777
- 888888888
- 999999999
- 0000000000
- 1111111111
- 2222222222
- 3333333333
- 4444444444
- 5555555555
- 6666666666
- 7777777777
- 8888888888
- 9999999999

## <a name="azure-documentdb-auth-key"></a>Azure 文档 DB Auth 密钥

### <a name="format"></a>格式

字符串"DocumentDb"后跟以下模式中概述的字符和字符串。

### <a name="pattern"></a>模式

- 字符串"文档 Db"
- 3-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 大于符号 （>）、等号 （*）、引号 （）或撇号 （'）
- 86 个小写或大写字母、数字、正斜杠 （/） 或加号 （+） 的任意组合
- 两个相等符号 （*）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureDocumentDBAuthKey 查找与模式匹配的内容。
- 正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_通用示例关键字

（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。

- 康托索
- 法布里卡姆
- 北风
- 沙 箱
- 一个盒子
- 本地 主机
- 127.0.0.1
- 试验。<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->网

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS 数据库连接字符串和 Azure SQL 连接字符串

### <a name="format"></a>格式

字符串"服务器"、"服务器"或"数据源"后跟以下模式中概述的字符和字符串，包括字符串"cloudapp.azure"。<!--no-hyperlink-->com"或"云应用程序.azure"。<!--no-hyperlink-->net"或"数据库.窗口"。<!--no-hyperlink-->net"，以及字符串"密码"或"密码"或"pwd"。

### <a name="pattern"></a>模式

- 字符串"服务器"、"服务器"或"数据源"
- 0-2 空格字符
- 等号 （*）
- 0-2 空格字符
- 1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"cloudapp.azure"。<!--no-hyperlink-->"网络"，"云应用程序.azure"。<!--no-hyperlink-->net"，或"数据库.窗口"。<!--no-hyperlink-->净
- 1-300 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"密码"、"密码"或"密码"
- 0-2 空格字符
- 等号 （*）
- 0-2 空格字符
- 一个或多个不是分号（;)、引号 （） 或撇号 （'） 的字符
- 分号（;)、引号 （）或撇号 （'）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_Azure 连接字符串查找与模式匹配的内容。
- 正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_通用示例关键字

（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。

- 康托索
- 法布里卡姆
- 北风
- 沙 箱
- 一个盒子
- 本地 主机
- 127.0.0.1
- 试验。<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->网

## <a name="azure-iot-connection-string"></a>Azure IoT 连接字符串

### <a name="format"></a>格式

字符串"HostName"后跟以下模式中概述的字符和字符串，包括字符串"azure 设备"。<!--no-hyperlink-->net"和"共享访问密钥"。

### <a name="pattern"></a>模式

- 字符串"主机名"
- 0-2 空格字符
- 等号 （*）
- 0-2 空格字符
- 1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"Azure 设备"。<!--no-hyperlink-->净
- 1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"共享访问密钥"
- 0-2 空格字符
- 等号 （*）
- 0-2 空格字符
- 43 个小写或大写字母、数字、正斜杠 （/） 或加号 （+） 的任意组合
- 等号 （*）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureIoT 连接字符串查找与模式匹配的内容。
- 正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_通用示例关键字

（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。

- 康托索
- 法布里卡姆
- 北风
- 沙 箱
- 一个盒子
- 本地 主机
- 127.0.0.1
- 试验。<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->网

## <a name="azure-publish-setting-password"></a>Azure 发布设置密码

### <a name="format"></a>格式

字符串"userpwd_"后跟字母数字字符串。

### <a name="pattern"></a>模式

- 字符串"userpwd_"
- 60 个小写字母或数字的任意组合
- 引号 （"）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzurePublishSettingPasswords 查找与模式匹配的内容。
- 正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_通用示例关键字

（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。

- 康托索
- 法布里卡姆
- 北风
- 沙 箱
- 一个盒子
- 本地 主机
- 127.0.0.1
- 试验。<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->网

## <a name="azure-redis-cache-connection-string"></a>Azure Redis 缓存连接字符串

### <a name="format"></a>格式

字符串"redis.cache.windows"。<!--no-hyperlink-->net"后跟以下模式中概述的字符和字符串，包括字符串"密码"或"pwd"。

### <a name="pattern"></a>模式

- 字符串"redis.cache.windows"。<!--no-hyperlink-->净
- 1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"密码"或"密码"
- 0-2 空格字符
- 等号 （*）
- 0-2 空格字符
- 43 个字符的任意组合，这些字符是小写或大写字母、数字、正斜杠 （/） 或加号 （+）
- 等号 （*）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureRedisCache 连接字符串查找与模式匹配的内容。
- 正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_通用示例关键字

（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。

- 康托索
- 法布里卡姆
- 北风
- 沙 箱
- 一个盒子
- 本地 主机
- 127.0.0.1
- 试验。<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->网

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>格式

字符串"sig"后跟以下模式中概述的字符和字符串。

### <a name="pattern"></a>模式

- 字符串"sig"
- 0-2 空格字符
- 等号 （*）
- 0-2 空格字符
- 43-53 个字符之间的任意组合，这些字符是小写或大写字母、数字或百分比符号 （%）
- 字符串"%3d"
- 不是小写或大写字母、数字或百分比符号的任何字符 （%）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureSAS 查找与模式匹配的内容。

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure 服务总线连接字符串

### <a name="format"></a>格式

字符串"EndPoint"后跟以下模式中概述的字符和字符串，包括字符串"servicebus.windows"。<!--no-hyperlink-->net"和"共享AccesKey"。

### <a name="pattern"></a>模式

- 字符串"结束点"
- 0-2 空格字符
- 等号 （*）
- 0-2 空格字符
- 1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"服务总线.窗口。<!--no-hyperlink-->净
- 1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"共享访问密钥"
- 0-2 空格字符
- 等号 （*）
- 0-2 空格字符
- 43 个字符的任意组合，这些字符是小写或大写字母、数字、正斜杠 （/） 或加号 （+）
- 等号 （*）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_Azure ServiceBusConnectString 查找与模式匹配的内容。
- 正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_commonexamplekeywords"></a>CEP_通用示例关键字

（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。

- 康托索
- 法布里卡姆
- 北风
- 沙 箱
- 一个盒子
- 本地 主机
- 127.0.0.1
- 试验。<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->网

## <a name="azure-storage-account-key"></a>Azure 存储帐户密钥

### <a name="format"></a>格式

字符串"DefaultEndpointsProtocol"后跟以下模式中概述的字符和字符串，包括字符串"帐户密钥"。

### <a name="pattern"></a>模式

- 字符串"默认终结点协议"
- 0-2 空格字符
- 等号 （*）
- 0-2 空格字符
- 1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"帐户密钥"
- 0-2 空格字符
- 等号 （*）
- 0-2 空格字符
- 86 个字符的任意组合，这些字符是小写或大写字母、数字、正斜杠 （/） 或加号 （+）
- 两个相等符号 （*）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureStorageAccountKey 查找与模式匹配的内容。
- 正则表达式 CEP_AzureEmulor 存储帐户筛选器**找不到**与模式匹配的内容。
- 正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_azureemulatorstorageaccountfilter"></a>CEP_Azure 仿真器存储帐户筛选器

（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。

- Eby8vdM02xNOcqFluwJpllmetlDX1OUzTFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw_*

#### <a name="cep_commonexamplekeywords"></a>CEP_通用示例关键字

（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。

- 康托索
- 法布里卡姆
- 北风
- 沙 箱
- 一个盒子
- 本地 主机
- 127.0.0.1
- 试验。<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->网

## <a name="azure-storage-account-key-generic"></a>Azure 存储帐户密钥（通用）

### <a name="format"></a>格式

86 个小写或大写字母、数字、正斜杠 （/） 或加号 （+）的任意组合，前面或后面是下图中概述的字符。

### <a name="pattern"></a>模式

- 大于符号 （>）、撇号 （'）、等号 （+）、引号 （）或数字符号 （*） 的 0-1
- 86 个字符的任意组合，这些字符是小写或大写字母、数字、正斜杠 （/） 或加号 （+）
- 两个相等符号 （*）


### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureStorageKey 一般查找与模式匹配的内容。

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a>比利時國民編碼

### <a name="format"></a>格式

11 位数字加上分隔符

### <a name="pattern"></a>模式

11 位数字加上分隔符：
- 格式 YY 的六位数字和两个句点。毫米。出生日期的 DD 
- 连字符 
- 三个连续数字（男性的奇数，甚至女性） 
- 一个期间 
- 作为校验位数的两位数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_belgium_national_number 查找与模式匹配的内容。
- 找到关键字_belgium_national_编号的关键字。
- 校验和通过。

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_belgium_national_number"></a>关键字_belgium_国家_数字

- 身分識別
- 注册
- 识别 
- ID 
- 身份识别
- 注册人努默 
- 身份识别 nummer 
- 身份识别
- 注册人
- 身份识别 
- 卡特·德·标识特 
- numéro d'itriculation
- numéro d'标识
- 身份* 
- 题词 
- 标识
- 身份识别
- 识别nummer
- 个人
- 注册人
- 注册斯努默

   
## <a name="brazil-cpf-number"></a>巴西公积金号码

### <a name="format"></a>格式

包含校验数字的 11 位数字，可以格式化或未格式化

### <a name="pattern"></a>模式

格式 化：
- 三位数字 
- 一个期间 
- 三位数字 
- 一个期间 
- 三位数字 
- 连字符 
- 两位数字是支票数字

未格式化：
- 11 位数字，其中最后两位数字为支票数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_brazil_cpf 查找与模式匹配的内容。
- 找到关键字_brazil_cpf 的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_brazil_cpf 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_brazil_cpf"></a>关键字_巴西_cpf

- 公积金
- 识别
- 注册
- 收入
- 卡德斯特罗·德佩索亚斯·费西卡斯 
- 因波托 
- 身份识别 
- 因斯克里尼奥 
- 雷切塔 
   
## <a name="brazil-legal-entity-number-cnpj"></a>巴西法人编号

### <a name="format"></a>格式

14 位数字，包括注册号、分支编号和支票数字，以及分隔符

### <a name="pattern"></a>模式
14 位数字加上分隔符：
- 两位数字 
- 一个期间 
- 三位数字 
- 一个期间 
- 三位数字（前八位数字是注册号码） 
- 正向斜杠 
- 四位分支编号 
- 连字符 
- 两位数字是支票数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_brazil_cnpj 查找与模式匹配的内容。
- 找到关键字_brazil_cnpj的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_brazil_cnpj 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_brazil_cnpj"></a>关键词_巴西\cnpj

- CNPJ 
- CNPJ/MF 
- CNPJ-MF 
- 国家法人登记处 
- 纳税人登记处 
- 法人 
- 法人 
- 注册状态 
- 商務版 
- Company
- CNPJ 
- 国家佩索阿·朱利亚 
- 卡德斯特罗·杰拉尔·德·康特里特 
- CGC 
- 佩索阿·法里迪卡 
- 佩索亚斯·法里卡 
- 西图塔奥地籍 
- 因斯克里尼奥 
- 埃姆普雷萨 
   
## <a name="brazil-national-id-card-rg"></a>巴西国民身份证

### <a name="format"></a>格式

注册人杰拉尔（旧格式）：九位数字

注册（RIC）（新格式）：11 位

### <a name="pattern"></a>模式

注册人杰拉尔（旧格式）：
- 两位数字 
- 一个期间 
- 三位数字 
- 一个期间 
- 三位数字 
- 连字符 
- 一个数字，即校验数字

注册（RIC）（新格式）：
- 10 位 
- 连字符 
- 一个数字，即校验数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_brazil_rg 查找与模式匹配的内容。
- 找到关键字_brazil_rg 的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_brazil_rg 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_brazil_rg"></a>关键字_巴西\rg

Cédula de identidade 身份证 国民 ID n_mero de 注册注册注册 GERal RG （此关键字是区分大小写） RIC （此关键字是区分大小写） 
   
## <a name="canada-bank-account-number"></a>加拿大银行帐号

### <a name="format"></a>格式

七或十二位

### <a name="pattern"></a>模式

加拿大银行帐号为七位或十二位数字。

加拿大银行账户中转号码为：
- 五位数字 
- 连字符 
- 三位或
- 零"0" 
- 八位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_canada_bank_帐户_编号查找与模式匹配的内容。
- 找到关键字_加拿大_银行_帐户_编号的关键字。
- 正则表达式 Regex_canada_bank_帐户_传输_编号查找与模式匹配的内容。

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_canada_bank_帐户_编号查找与模式匹配的内容。
- 找到关键字_加拿大_银行_帐户_编号的关键字。

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_canada_bank_account_number"></a>关键词_加拿大_银行_帐户_编号

- 加拿大储蓄债券
- 加拿大税务局
- 加拿大金融机构
- 直接存款表格
- 加拿大公民
- 法定代表人
- 公证
- 宣誓专员
- 儿童保育津贴
- 普遍儿童保育
- 加拿大儿童税收优惠
- 所得税优惠
- 统一销售税
- 社会保险号
- 所得税退税
- 儿童税收优惠
- 领土付款
- 机构编号
- 存款请求
- 银行信息
- 直接存款
   
## <a name="canada-drivers-license-number"></a>加拿大驾照号码

### <a name="format"></a>格式

因省而异

### <a name="pattern"></a>模式

各种模式涵盖艾伯塔省、不列颠哥伦比亚省、马尼托巴省、新不伦瑞克省、纽芬兰/拉布拉多省、新斯科舍省、安大略省、爱德华王子岛省、魁北克省和萨斯喀彻温省

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_省_名称_驱动程序_许可证_编号查找与模式匹配的内容。
- 找到关键字_省名_驱动程序_许可证名称的关键字。
- 找到关键字_canada_驱动程序_许可证的关键字。

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_province_name_drivers_license_name"></a>关键词_省名_驱动程序_许可证_名称

- 省缩写，例如 AB
- 省名称，例如艾伯塔省

#### <a name="keyword_canada_drivers_license"></a>关键词_加拿大_驱动程序_许可证

- Dl
- Dls
- 民盟
- CDLS
- 司机
- 司机
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 司机李克
- 司机利茨
- 驾照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驱动程序
- 司机Lics
- 司机执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 司机许可证
- 司机利茨
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 司机'Lic
- 司机的Lics
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 司机的许可证
- 司机的Lics
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶员的
- 驾驶员的
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶员的许可证
- 司机的许可证
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾驶执照
- 佩米斯·德孔杜瓦雷
- id
- Id
- 身份证号码
- 身份证号码
- 身份证#
- 身份证#s
- 身份证
- 身份证
- 身份证
- 识别号
- 识别号
- 识别#
- 识别#s
- 身份证
- 身份证
- 识别 
- Dl#
- Dls# 
- 民盟# 
- CDLS# 
- 司机# 
- 司机# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 司机李克#
- 司机利茨# 
- 驾照# 
- 驾驶执照# 
- 驾照# 
- 驾驶执照# 
- 驱动程序# 
- 司机Lics# 
- 驾驶执照# 
- 驾驶执照# 
- 司机执照# 
- 驾驶执照# 
- 司机许可证# 
- 司机利茨# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 司机'Lic# 
- 司机的Lics# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 司机的许可证# 
- 司机的Lics# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶员的# 
- 驾驶员的# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶员的许可证# 
- 司机的许可证# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶执照# 
- 佩米斯·德孔杜瓦雷# 
- Id# 
- Id# 
- 身份证# 
- 身份证# 
- 身份证# 
- 身份证# 
- 身份证# 
- 识别# 
   
## <a name="canada-health-service-number"></a>加拿大健康服务号码

### <a name="format"></a>格式

10 位

### <a name="pattern"></a>模式

10 位

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_canada_health_service_number 查找与模式匹配的内容。
- 找到关键字_canada_health_service_编号的关键字。

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_canada_health_service_number"></a>关键词_加拿大+健康+服务_编号

- 个人健康号码
- 患者信息
- 保健服务
- 专业服务
- 车祸
- 病人医院
- 心理医生
- 工人补偿
- 残疾
      
## <a name="canada-passport-number"></a>加拿大护照号码

### <a name="format"></a>格式

两个大写字母后跟六位数字

### <a name="pattern"></a>模式

两个大写字母后跟六位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_canada_Passport_number 查找与模式匹配的内容。
- 找到关键字_canada_passport_编号或关键字_Passport 的关键字。

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_canada_passport_number"></a>关键词_加拿大_护照_编号

- 加拿大国籍
- 加拿大护照
- 护照申请
- 护照照片
- 认证翻译
- 加拿大公民
- 处理时间
- 续约申请

#### <a name="keyword_passport"></a>关键词_护照

- 护照号码
- 护照号
- 护照#
- 护照#
- 护照ID
- 护照诺
- 护照号码
- ·
- ·\\\\\\\\\\\\\\\\\\\\\\
- * * * *
- ·
- 努梅罗·德·德费波特
- 路路港 n |
- 路路港非
- 帕塞波特#
- 帕塞波特#
- 帕塞波特农
- 帕塞波特 |
   
## <a name="canada-personal-health-identification-number-phin"></a>加拿大个人健康识别号

### <a name="format"></a>格式

九位数字

### <a name="pattern"></a>模式

九位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果正则表达式 Regex_canada_phin 查找与模式匹配的内容，则 DLP 策略 75% 确信检测到这种类型的敏感信息。
找到至少两个关键字_canada_phin 或关键字_加拿大_省。

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_canada_phin"></a>关键词_加达内

- 社会保险号
- 健康信息法
- 所得税信息
- 马尼托巴健康
- 健康注册
- 处方购买
- 福利资格
- 个人健康
- 委托书
- 注册号
- 个人健康号码
- 执业者转诊
- 健康专业人士
- 患者转诊
- 健康与健康

#### <a name="keyword_canada_provinces"></a>关键词_加拿大_省

- 努纳武特
- 魁北克
- 西北地区
- 安大略省
- 不列颠哥伦比亚省
- 艾伯塔省
- 萨斯喀彻温省
- 马尼托巴省
- 育 空
- 纽芬兰和拉布拉多
- 新不伦瑞克省
- 新斯科舍省
- 爱德华王子岛
- 加拿大
   
## <a name="canada-social-insurance-number"></a>加拿大社会保险号

### <a name="format"></a>格式

九位数字，带可选连字符或空格

### <a name="pattern"></a>模式

格式 化：
- 三位数字 
- 连字符或空格 
- 三位数字 
- 连字符或空格 
- 三位数字

未格式化：九位数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_canadian_sin 查找与模式匹配的内容。
- 以下任意组合中至少有两个：
    - 找到关键字_sin 中的关键字。
    - 找到来自关键字_sin_协作的关键字。
    - 函数 Func_eu_date 以正确的日期格式查找日期。
- 校验和通过。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_无格式化_加拿大_sin 查找与模式匹配的内容。
- 找到关键字_sin 中的关键字。
- 校验和通过。

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_sin"></a>关键字_辛

- 罪 
- 社会保险 
- numero d'保证社会 
- 罪 
- Ssn 
- sns 
- 社会保障 
- numero d'保证社会 
- 国家身份证号码 
- 国家 ID 
- 罪# 
- 索克因斯 
- 社会参与 

#### <a name="keyword_sin_collaborative"></a>关键字_辛_协作

- 驾驶执照 
- 驾驶执照 
- 驾驶执照 
- 驾驶执照 
- DOB 
- 出生日期 
- 生日 
- 出生日期 
   
## <a name="chile-identity-card-number"></a>智利身份证号码

### <a name="format"></a>格式

7-8 位数字加上分隔符，校验数字或字母

### <a name="pattern"></a>模式

7-8 位数字加上分隔符：
- 1-2 位 
- 一个期间 
- 三位数字 
- 一个期间 
- 三位数字 
- 破折号 
- 一个数字或字母（不区分大小写），这是一个校验数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_chile_id_card 查找与模式匹配的内容。
- 找到关键字_chile_id_card 的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_chile_id_card 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_chile_id_card"></a>关键词_chile_id_卡

- 国家识别号码 
- 身份证 
- ID 
- 识别 
- 罗尔·奥尼科·国家 
- 运行 
- 罗尔·奥尼科支流 
- 车辙 
- 奇杜拉·德·伊登迪达 
- 国家身份研究所 
- 塔杰塔·德·卡蒂西翁 
- 身份识别 
   
## <a name="china-resident-identity-card-prc-number"></a>中国居民身份证号码

### <a name="format"></a>格式

18 位

### <a name="pattern"></a>模式

18 位：
- 六位数字是地址代码 
- 表格 YYYYMMDD 中的八位数字，即出生日期 
- 三位数字是订单代码 
- 一个数字，即校验数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_china_驻留_id 查找与模式匹配的内容。
- 找到关键字_china_居民\id的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_china_驻留_id 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

### <a name="keyword_china_resident_id"></a>关键字_中国_居民_id

- 居民身份证 
- 中国 
- 国民身份证 
- · 
- · 
- ·00年 
- · 
- · 
- ·
- ·* 
   
## <a name="credit-card-number"></a>信用卡號碼

### <a name="format"></a>格式

16 位数字，可格式化或未格式化（ddddddddddddd），并且必须通过 Luhn 测试。

### <a name="pattern"></a>模式

非常复杂和强大的模式，可检测来自全球所有主要品牌的卡，包括 Visa、万事达卡、发现卡、JCB、美国运通卡、礼品卡和餐卡。

### <a name="checksum"></a>校验

是，卢恩校验和

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_credit_card 查找与模式匹配的内容。
- 下列情况之一是正确的：
    - 找到关键字_cc_验证的关键字。
    - 找到关键字_cc_name的关键字。
    - 函数 Func_date_date 以正确的日期格式查找日期。
- 校验和通过。

如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：
- 函数 Func_credit_card 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_cc_verification"></a>关键字_cc_验证

- 卡验证
- 卡标识号
- cvn
- cid
- cvc2
- cvv2
- 引脚块
- 安全代码
- 安全号码
- 安全否
- 问题编号
- 问题否
- 密码语法
- numéro de sécurité
- numero de Securite
- 克雷迪克特卡滕普吕夫努默
- 克雷迪克特卡滕普鲁夫努默
- 普雷夫齐弗
- 普鲁夫齐弗
- 希切赫海茨·科德
- sicherheits码
- 希切赫赫努默
- 弗法尔达图姆
- 科迪斯·迪维蒂卡
- Cod。 西库雷扎
- 鳕鱼西库雷扎
- n autorizzazione
- 塞迪戈
- 科迪戈
- Cod。 Seg
- 鳕鱼赛格
- 塞古拉尼亚
- 科迪戈·德塞古兰卡
- 科迪戈·德塞古拉尼亚
- 塞古兰卡
- c_d. 塞古拉尼亚
- Cod。 塞古兰卡鳕鱼。 塞古拉尼亚
- c_d. 塞古兰卡
- 塞古拉尼亚
- 鳕鱼塞古兰卡鳕鱼塞古拉尼亚
- 塞古兰卡
- 努梅罗·德维萨奥
- numero de 验证卡考
- 阿布拉夫
- 盖尔蒂格·比斯
- 盖尔蒂格凯茨达图姆
- 古尔蒂格·比斯
- 古尔蒂格凯茨达图姆
- 沙登扎
- 数据 scad
- 过期
- 费查·德·韦克
- 文西门托
- 瓦利多·哈斯塔
- valido hasta
- vto
- 数据到期
- 数据到期
- 数据 em que 到期
- 有效
- 勇气
- 文奇门托
- 文奇 

#### <a name="keyword_cc_name"></a>关键字_cc_名称

- 阿姆克斯
- 美国快递
- 美国快递
- 签证
- 万事 达
- 主卡
- Mc 
- 万事达卡
- 主卡
- 餐厅俱乐部
- 食客俱乐部
- 食客俱乐部
- 发现卡
- 发现卡
- 发现卡片
- JCB
- 日本卡局
- 点菜布兰奇
- 卡特布兰奇
- 信用卡
- Cc#
- cc#：
- 有效期
- exp 日期
- 有效期
- 过期日期
- 日期 d'exp
- 日期过期
- 银行卡
- 银行卡
- 卡号
- 卡数
- 卡号
- 牌号
- 卡号
- 信用卡
- 信用卡
- 信用卡
- ccn
- 持卡人
- 持 卡 人
- 持卡人
- 持 卡 人
- 支票卡
- 支票卡
- 支票卡
- 支票卡
- 借记卡
- 借记卡
- 借记卡
- 借记卡
- atm 卡
- atmcard
- atm 卡
- atmcards
- 路线
- 途中
- 卡类型
- 卡特·班凯雷
- 点菜
- 点菜信贷
- numéro de carte
- numero de carte
- 点菜号
- 点菜
- 克雷迪克特卡特
- 卡尔特
- 卡尔特宁哈伯
- 卡尔特宁哈伯斯
- 克雷迪克特卡特宁哈伯
- 克雷蒂特卡滕特研究所
- 克雷蒂特卡滕蒂普
- 艾根特·梅尔南
- 卡尔滕内尔 
- 卡尔滕努默
- 克雷迪克特卡滕努默
- 克雷迪克特卡滕-努默
- 卡塔迪信贷
- 卡塔·卡托
- 宪章
- n 卡塔
- 星期日。 宪章
- nr carta
- 努梅罗·卡塔
- numero dela carta
- numero di carta
- 塔耶塔信贷
- 塔耶塔·德·信贷
- 塔耶塔·克雷迪托
- 塔耶塔·德·克雷迪托
- 塔耶塔·德阿特姆
- 塔耶塔 atm
- 塔耶塔·比托
- 塔耶塔·德·比乔
- 塔耶塔·德比托
- 塔耶塔·德德比托
- 诺德塔耶塔
- 不。 德塔耶塔
- 没有塔里塔
- numero de tarjeta
- 内梅罗·德塔耶塔
- 塔耶塔没有
- 塔尔杰塔哈比恩特
- 卡特奥·德·卡迪托
- 卡特尼奥·德信贷
- 卡尔陶·德·克雷迪托
- 卡尔陶·德·信贷
- 卡尔多·德德比托
- 卡尔陶·德德比托
- 卡特尼奥·德·比托
- 卡尔陶·德·比乔
- 德比托·自治蒂科
- 比托自动
- 内梅罗·多·卡托
- numero do cartío 
- 内梅罗·多·卡托
- numero do Cartao
- némero de cartéo
- numero de cartío
- 内梅罗·德卡托
- 努梅罗·德·卡陶
- no do cartéo
- no do Cartao
- no. 多卡托
- 没有做卡特奥
- 没有做卡陶
- 不。 多卡托
- 不。 多卡陶 
   
## <a name="croatia-identity-card-number"></a>克羅埃西亞身分證號碼

### <a name="format"></a>格式

九位数字

### <a name="pattern"></a>模式

连续九位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_croatia_id_card 查找与模式匹配的内容。
- 找到关键字_croatia_id_card 的关键字。

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_croatia_id_card"></a>关键字_克罗地亚_id_卡

- 克罗地亚身份证
- 奥索布纳·卡兹尼察

   
## <a name="croatia-personal-identification-oib-number"></a>克羅埃西亞個人識別 (OIB) 碼

### <a name="format"></a>格式

11 位

### <a name="pattern"></a>模式

11 位：
- 10 位 
- 最终数字是一个校验数字 用于国际数据交换，字母 HR 添加到 11 位数字之前。

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_croatia_oib_number 查找与模式匹配的内容。
- 找到关键字_croatia_oib_编号的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_croatia_oib_number 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_croatia_oib_number"></a>关键字_克罗地亚_oib_数字

- 个人识别号码
- 奥索布尼·伊登蒂比卡奇斯基·布罗伊 
- OIB 

   
## <a name="czech-personal-identity-number"></a>捷克个人身份号码

### <a name="format"></a>格式

九位数字，可选前斜杠（旧格式）10 位数字，可选前斜杠（新格式）

### <a name="pattern"></a>模式

九位数字（旧格式）：
- 九位数字

或

- 表示出生日期的六位数字
- 正向斜杠
- 三位数字

10 位数字（新格式）：
- 10 位

或

- 表示出生日期的六位数字
- 正向斜杠 
- 四位数字，其中最后一位数字是校验数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果 DLP 策略在 300 个字符的接近范围内检测到这种类型的敏感信息，则 DLP 策略有 85% 的置心度：如果函数 Func_捷克_id_card 查找与模式匹配的内容。
找到来自关键字_捷克_id_card的关键字。
校验和通过。

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a>關鍵字

- 捷克人个人身份号码
- 罗德内·什洛
   
## <a name="denmark-personal-identification-number"></a>丹麥個人識別碼

### <a name="format"></a>格式

包含连字符的 10 位数字

### <a name="pattern"></a>模式

10 位：
- DDMMYY 格式中的六位数字，即出生日期 
- 连字符 
- 四位数字，其中最终数字为校验数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果正则表达式 Regex_d_d_id 查找与模式匹配的内容，则 DLP 策略 75% 确信检测到这种类型的敏感信息。
找到关键字_丹麦_id的关键字。
校验和通过。

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_denmark_id"></a>关键字_丹麦_id

- 个人识别号码
- Cpr
- 德特中央人登记册
- 人物
   
## <a name="drug-enforcement-agency-dea-number"></a>缉毒署

### <a name="format"></a>格式

两个字母后跟七位数字

### <a name="pattern"></a>模式

模式必须包括以下所有内容：
- 一个字母（不区分大小写）从这组可能的字母：abcdefghjklmnprstux，这是一个注册代码 
- 一个字母（不区分大小写），这是注册人姓氏的第一个字母 
- 七位数字，最后一位是校验数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_dea_number 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無

   
## <a name="eu-debit-card-number"></a>歐盟轉帳卡號碼

### <a name="format"></a>格式

16 位

### <a name="pattern"></a>模式

非常复杂且强大的模式

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_eu_借记卡查找与模式匹配的内容。
- 以下至少一项是正确的：
    - 找到关键字_eu_借记卡_card 的关键字。
    - 找到关键字_卡片_字距_dict的关键字。
    - 找到关键字_卡片_安全_术语_dict的关键字。
    - 找到关键字_卡片_过期_字距_dict的关键字。
    - 函数 Func_date_date 以正确的日期格式查找日期。
- 校验和通过。

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_eu_debit_card"></a>关键字_eu_借记卡

- 帐号 
- 卡号 
- 卡号。 
- 安全号码 
- Cc# 

#### <a name="keyword_card_terms_dict"></a>关键字_卡片_字词_dict

- acct nbr 
- acct num 
- acct 否 
- 美国快递 
- 美国快递 
- 美洲咖啡 
- 阿姆克斯 
- atm 卡 
- atm 卡 
- 阿特姆·卡特 
- atmcard 
- atmcards 
- 阿特姆卡特 
- 阿滕卡滕 
- 班接触 
- 银行卡 
- 班克卡尔 
- 持卡人 
- 持卡人 
- 卡数 
- 卡号 
- 卡号 
- 卡类型 
- 卡尔达诺数字 
- 持 卡 人 
- 持 卡 人 
- 卡号 
- 牌号 
- 卡塔比安卡 
- 卡塔·卡托 
- 卡塔迪信贷 
- 卡尔陶·德·信贷 
- 卡尔陶·德·克雷迪托 
- 卡尔陶·德·比乔 
- 卡尔陶·德德比托 
- 卡特·班凯雷 
- 点菜布兰奇 
- 卡特布勒 
- 点菜信贷 
- 点菜 
- 卡特迪信贷 
- 卡特布兰奇 
- 卡特尼奥·德信贷 
- 卡特奥·德·卡迪托 
- 卡特尼奥·德·比托 
- 卡尔多·德德比托 
- cb 
- ccn 
- 支票卡 
- 支票卡 
- 支票卡
- 支票卡 
- 切卡尔 
- 卷云 
- cirrus-edc-maestro 
- 控件卡 
- 控件卡滕 
- 信用卡 
- 信用卡 
- 信用卡 
- 信用卡 
- 德贝特卡特 
- 德贝特卡尔滕 
- 借记卡 
- 借记卡 
- 借记卡 
- 借记卡 
- 比托自动 
- 食客俱乐部 
- 食客俱乐部 
- 发现 
- 发现卡 
- 发现卡片 
- 发现卡 
- 发现卡 
- 德比托·自治蒂科
- 埃德克 
- 艾根特·梅尔南 
- 欧洲借记卡 
- 霍夫德卡特 
- 霍夫德卡滕 
- 在维乔 
- 日本卡局 
- 日本·卡特迪恩斯特 
- jcb 
- 卡尔特 
- 卡特·努姆 
- 卡尔塔安塔尔 
- 卡尔塔安塔伦 
- 卡尔图德 
- 卡尔特霍德斯 
- 卡尔特  
- 卡尔特宁哈伯 
- 卡尔特宁哈伯斯
- 卡尔滕内尔 
- 卡尔滕努默 
- 克雷迪克特卡特 
- 克雷迪克特卡滕-努默 
- 克雷迪克特卡特宁哈伯 
- 克雷蒂特卡滕特研究所 
- 克雷迪克特卡滕努默 
- 克雷蒂特卡滕蒂普 
- 大师 
- 主卡 
- 主卡 
- 万事 达 
- 万事达卡 
- Mc 
- 先生现金 
- n 卡塔 
- 宪章 
- 没有塔里塔 
- 没有做卡陶 
- 没有做卡特奥 
- 不。 德塔耶塔 
- 不。 多卡陶 
- 不。 多卡托 
- nr carta 
- 星期日。 宪章 
- 努梅里·迪·沙达 
- 努梅罗·卡塔 
- 努梅罗·德·卡陶 
- numero de carte 
- numero de cartío 
- numero de tarjeta
- numero dela carta 
- numero di carta 
- 努梅罗·迪·沙达 
- numero do Cartao 
- numero do cartío 
- numéro de carte 
- no o 卡特拉 
- 点菜 
- 点菜号 
- 诺德塔耶塔 
- no do Cartao 
- no do cartéo 
- no. 多卡托 
- 内梅罗·德卡托 
- némero de cartéo 
- 内梅罗·德塔耶塔 
- 内梅罗·多·卡托 
- 谢达·德尔阿塞格诺 
- 沙达·德尔阿莫斯费拉 
- 沙达·德尔阿莫斯费拉 
- 沙达德拉班卡 
- 沙达迪控制洛 
- 沙达迪比托 
- 沙达矩阵 
- 舍德·德尔阿莫斯费拉 
- 舍德迪控制洛 
- 舍德·迪·比乔 
- 舍德·马特里基 
- 斯科普罗诺·拉沙达 
- 斯科普罗诺·勒舍德 
- 独奏 
- 支持迪沙达 
- 支持迪沙达 
- 开关 
- 塔耶塔 atm 
- 塔耶塔信贷 
- 塔耶塔·德阿特姆 
- 塔耶塔·德·信贷 
- 塔耶塔·德·比乔 
- 塔耶塔·比托 
- 塔耶塔没有
- 塔尔杰塔哈比恩特 
- 蒂波·德拉·沙达 
- 乌菲西奥·贾波内斯·德拉 
- 沙达 
- v 支付 
- v-支付 
- 签证 
- 签证加 
- 签证电子 
- 内托 
- 维苏姆 
- vpay   

#### <a name="keyword_card_security_terms_dict"></a>关键词_卡片+安全+术语

- 卡标识号
- 卡验证 
- 卡迪拉维维卡 
- cid 
- 鳕鱼赛格 
- 鳕鱼塞古兰卡 
- 鳕鱼塞古拉尼亚 
- 鳕鱼西库雷扎 
- Cod。 Seg 
- Cod。 塞古兰卡 
- Cod。 塞古拉尼亚 
- Cod。 西库雷扎 
- 科迪迪斯·迪·西库雷扎 
- 科迪斯·迪维蒂卡 
- 科迪戈 
- 科迪戈·德塞古兰卡 
- 科迪戈·德塞古拉尼亚 
- 克米托格拉姆马 
- 密码 
- 密码语法 
- cv2 
- Cvc 
- cvc2 
- cvn 
- cvv 
- cvv2 
- 塞古兰卡 
- 塞古拉尼亚 
- c_d. 塞古兰卡 
- c_d. 塞古拉尼亚 
- 塞迪戈 
- 塞古兰卡 
- 塞古拉尼亚 
- 德卡特控制 
- 吉夫特·里乌特 
- 问题否 
- 问题编号 
- 卡尔蒂登蒂卡蒂阿努默 
- 克雷迪克特卡滕普鲁夫努默 
- 克雷迪克特卡滕普吕夫努默 
- 克韦斯特亚安塔尔 
- 不。 德尔伊迪齐奥内 
- 不。 迪西库雷扎 
- numero de Securite 
- numero de 验证卡考 
- numero del'edizione 
- numero di identicazione dela 
- 沙达 
- numero di sicurezza 
- 努梅罗·范·韦莱格海德 
- numéro de sécurité 
- 诺·奥特里扎齐内 
- 努梅罗·德维萨奥 
- 佩尔诺·伊尔·布洛克 
- 引脚块 
- 普鲁夫齐弗 
- 普雷夫齐弗 
- 安全代码 
- 安全否 
- 安全号码 
- 希切海茨·科德 
- sicherheits码 
- 希切赫赫努默 
- 斯佩尔德布洛克 
- 韦利格海德·内尔 
- 维伊格海德桑塔尔 
- 韦利格海德斯码 
- 韦利格海德斯努默 
- 弗法尔达图姆 

#### <a name="keyword_card_expiration_terms_dict"></a>关键字_卡片_过期_术语_dict

- 阿布拉夫 
- 数据到期 
- 数据到期 
- 数据德尔exp 
- 数据 di exp 
- 数据迪斯卡登扎 
- 数据 em que 到期 
- 数据 scad 
- 数据斯卡登扎 
- 有效日期* 
- 基准 afloop 
- 达图姆·范exp 
- 德阿夫卢普 
- 埃斯皮拉 
- 埃斯皮拉 
- exp 日期 
- exp 基准 
- 到期 
- 到期 
- 到期 
- 届满 
- 过期 
- 费查·德·韦克 
- 古尔蒂格·比斯 
- 古尔蒂格凯茨达图姆 
- 盖尔蒂格·比斯 
- 盖尔蒂格凯茨达图姆 
- 拉斯卡登扎 
- 沙登扎 
- 瓦尔维 
- 有效 
- valido hasta 
- 勇气 
- 韦克 
- 文奇门托 
- 文西门托 
- 弗鲁普特 
- 韦尔瓦尔达格 
- 韦尔瓦尔达图姆 
- vto 
- 瓦利多·哈斯塔 
   
## <a name="eu-drivers-license-number"></a>欧盟驾照号码

要了解更多信息，请参阅[欧盟驾照号码敏感信息类型](eu-driver-s-license-number.md)。
  
## <a name="eu-national-identification-number"></a>欧盟国家身份证号码

要了解更多信息，请参阅[欧盟国家标识号敏感信息类型](eu-national-identification-number.md)。
  
## <a name="eu-passport-number"></a>欧盟护照号码

要了解更多信息，请参阅[欧盟护照号码敏感信息类型](eu-passport-number.md)。
  
## <a name="eu-social-security-number-or-equivalent-id"></a>欧盟社会保险号或等效 ID

要了解更多信息，请参阅[欧盟社会安全号码或等效 ID 敏感信息类型](eu-social-security-number-or-equivalent-id.md)。
  
## <a name="eu-tax-identification-number"></a>欧盟税务识别号

要了解更多信息，请参阅[欧盟税务识别号敏感信息类型](eu-tax-identification-number.md)。
  
## <a name="finland-national-id"></a>芬蘭國民身分證

### <a name="format"></a>格式

六位数字加上一个字符，表示一个世纪加上三位数字加上一个校验数字

### <a name="pattern"></a>模式

模式必须包括以下所有内容：
- 格式 DDMMYY 格式的六位数字，即出生日期 
- 世纪标记（"-"，"+"或"a"） 
- 三位个人识别号码 
- 数字或字母（不区分大小写），这是校验数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_finnish_national_id 查找与模式匹配的内容。
- 找到来自关键字_芬兰_国家_id的关键字。
- 校验和通过。

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

- 关键字_芬兰_国家_id
- 索西亚利图瓦图努斯
- 索图·亨基勒图努斯·赫图
- 人物贝塞克宁
- 人物
   
## <a name="finland-passport-number"></a>芬蘭護照號碼

格式 9 个字母和数字模式组合 9 个字母和数字：两个字母（不区分大小写）七位数字校验和无定义 DLP 策略是 75% 的置信，它检测到这种类型的敏感信息，如果，300 个字符的邻近性：正则表达式 Regex_finland_Passport_number 查找与模式匹配的内容。
找到关键字_芬兰_护照_号码的关键字。
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity>
关键词关键字_芬兰人_护照_数字护照帕西
   
## <a name="france-drivers-license-number"></a>法國駕照編號

### <a name="format"></a>格式

12 位

### <a name="pattern"></a>模式

12 位数字，可验证以折扣类似模式（如法语电话号码）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_french_驱动程序_许可证查找与模式匹配的内容。
- 以下至少一项是正确的：
- 找到关键字_french_驱动程序_许可证的关键字。
- 函数 Func_eu_date 以正确的日期格式查找日期。

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_french_drivers_license"></a>关键词_法语_驱动程序_许可证

- 驾驶执照
- 驾驶执照
- 驾驶执照
- 驾照
- 佩尔米斯·德孔杜瓦
- 牌照号码
- 许可证号
- 许可证号码
- 许可证号

## <a name="france-national-id-card-cni"></a>法國國民身分證 (CNI)

### <a name="format"></a>格式

12 位

### <a name="pattern"></a>模式

12 位

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：
- 正则表达式 Regex_france_cni 查找与模式匹配的内容。

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無
   
## <a name="france-passport-number"></a>法國護照號碼

### <a name="format"></a>格式

九位数字和字母

### <a name="pattern"></a>模式

九位数字和字母：
- 两位数字 
- 两个字母（不区分大小写） 
- 五位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_fr_passport 查找与模式匹配的内容。
- 找到关键字_Passport中一个关键字。

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_passport"></a>关键词_护照

- 护照号码
- 护照号
- 护照#
- 护照#
- 护照ID
- 护照诺
- 护照号码
- ·
- ·\\\\\\\\\\\\\\\\\\\\\\
- * * * *
- [ ] 
- 努梅罗·德·德费波特
- 路路港 n |
- 路路港非
- 帕塞波特#
- 帕塞波特#
- 帕塞波特农
- 帕塞波特 |

      
## <a name="france-social-security-number-insee"></a>法國社會安全號碼 (INSEE)

### <a name="format"></a>格式

15 位

### <a name="pattern"></a>模式

必须匹配两种模式之一：
- 13 位数字后跟空格后跟两位数字<br/>
或
- 15 个连续数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 95% 确信检测到这种类型的敏感信息：
- 函数 Func_french_insee 或 Func_fr_insee 查找与模式匹配的内容。
- 找到来自关键字_fr_insee的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_french_insee 或 Func_fr_insee 查找与模式匹配的内容。
- 找不到来自关键字_fr_insee 的关键字。
- 校验和通过。

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_fr_insee"></a>关键字_fr_insee

- 因西
- 安全* 社会
- 安全社会
- 国家 ID
- 国家标识
- numéro d'identité
- 无 d'identit_
- 不。 d'identit®
- numero d'identite
- 无 d'identite
- 不。 d'identite
- 社会安全号码
- 社会保障代码
- 社会保险号
- 国家识别
- d'identité 国家
- 社会社会
- 社会法典
- numéro d'保证社会
- numéro de sécu
- 代码 s_cu 
   
## <a name="german-drivers-license-number"></a>德国驾照号码

### <a name="format"></a>格式

11 位数字和字母的组合

### <a name="pattern"></a>模式

11 位数字和字母（不区分大小写）：
- 数字或字母 
- 两位数字 
- 六位数字或字母 
- 数字 
- 数字或字母

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_german_驱动程序_许可证查找与模式匹配的内容。
- 以下至少一项是正确的：
    - 找到关键字_german_驱动程序_许可证_编号的关键字。
    - 找到关键字_german_驱动程序_许可证_协作的关键字。
    - 找到关键字_german_驱动程序_许可证的关键字。
- 校验和通过。

```xml
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_german_drivers_license_number"></a>关键词_德国_驱动程序_许可证_编号

- 费勒斯切因
- 富赫勒谢因
- 富埃勒谢因
- 费勒斯切因努默
- 富勒舍因努默
- 富埃勒什金努默
- 费勒斯切因- 
- 富勒尔切因- 
- 富埃勒谢因- 
- 费勒斯切因努默纳
- 富勒什金努默纳
- 富埃勒什金努默纳
- 费勒斯切因努默·克拉塞
- 富勒什金努默·克拉塞
- 富埃勒什金努默·克拉塞
- 费勒斯切因- Nr
- 富勒尔切因- Nr
- 富埃勒谢因- Nr 
- 费勒斯切因-克拉塞 
- 富勒斯切因-克拉塞 
- 富埃勒谢因-克拉塞
- 费勒斯切因努默纳 
- 富勒什金努默纳 
- 富埃勒什金努默纳 
- 费勒斯切因努默·克拉塞 
- 富勒什金努默·克拉塞 
- 富埃勒什金努默·克拉塞 
- 费勒斯切因- Nr 
- 富勒尔切因- Nr 
- 富埃勒谢因- Nr 
- 费勒斯切因-克拉塞 
- 富勒斯切因-克拉塞 
- 富埃勒谢因-克拉塞 
- Dl 
- Dls
- 德里夫·利奇 
- 德里夫·利森 
- Driv 许可证
- Driv 许可证 
- Driv 许可证 
- Driv 许可证 
- 德里夫·利奇 
- 司机利森 
- 驾照 
- 驾驶执照 
- 驾驶执照 
- 驾驶执照 
- 司机许可证 
- 司机利森 
- 驾驶执照 
- 驾驶执照 
- 驾驶执照 
- 驾驶执照 
- 驾驶员的许可证 
- 司机的利森 
- 驾驶执照 
- 驾驶执照 
- 驾驶执照 
- 驾驶执照 
- 驾驶许可证 
- 驾驶利森 
- 驾照 
- 驾驶执照 
- 驾驶执照 
- 驾驶执照

#### <a name="keyword_german_drivers_license_collaborative"></a>关键词_德国_驱动程序_许可证_协作

- Nr-Führerschein 
- Nr-Fuhrerschein 
- 恩-富赫勒谢因 
- 无费勒斯切因 
- 无富勒舍因 
- 无富赫勒谢因 
- N-费勒斯川 
- N-富勒舍因 
- N-富埃勒谢因
- Nr-Führerschein 
- Nr-Fuhrerschein 
- 恩-富赫勒谢因 
- 无费勒斯切因 
- 无富勒舍因 
- 无富赫勒谢因 
- N-费勒斯川 
- N-富勒舍因 
- N-富埃勒谢因 

#### <a name="keyword_german_drivers_license"></a>关键词_德国_驱动程序_许可证

- 澳斯特伦达图姆
- 欧斯泰隆排序
- 奥斯特伦德·贝赫德
- 欧斯泰伦德·比霍德
- 欧斯泰伦德·贝霍德
   
## <a name="german-passport-number"></a>德國護照號碼

### <a name="format"></a>格式

10 位数字或字母

### <a name="pattern"></a>模式

模式必须包括以下所有内容：
- 第一个字符是此集的数字或字母（C、F、G、H、J、K） 
- 三位数字 
- 此集的五位数字或字母（C、-H、J-N、P、R、T、V-Z） 
- 数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_german_Passport 查找与模式匹配的内容。
- 找到五个关键字列表中任何一个的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_german_Passport_数据查找与模式匹配的内容。
- 找到五个关键字列表中任何一个的关键字。
- 校验和通过。

```xml
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_german_passport"></a>关键词_德语_护照

- 雷塞帕斯
- 雷塞帕塞
- 雷塞帕塞努默
- 护照
- 护照

#### <a name="keyword_german_passport_collaborative"></a>关键词_德语_护照_协作

- 格布尔茨达图姆
- 澳斯特伦达图姆
- 欧斯泰隆排序

#### <a name="keyword_german_passport_number"></a>关键词_德语_护照_号码

无雷塞帕斯 Nr-Reisepass

#### <a name="keyword_german_passport1"></a>关键词_德语_护照1

莱塞帕斯-Nr

#### <a name="keyword_german_passport2"></a>关键词_德语_护照2

比特特
   
## <a name="germany-identity-card-number"></a>德國身分證號碼

### <a name="format"></a>格式

自 2010 年 11 月 1 日起：9 个字母和数字

1987年4月1日至2010年10月31日：10位

### <a name="pattern"></a>模式

自2010年11月1日起：
- 一个字母（不区分大小写） 
- 八位数字

1987年4月1日至2010年10月31日：
- 10 位

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：
- 正则表达式 Regex_germany_id_card 查找与模式匹配的内容。
- 找到关键字_germany_id_card 的关键字。

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_germany_id_card"></a>关键字_德杰德_id_卡

- 身份证
- ID
- 识别
- 个人
- 身份识别者
- 澳斯威
- 标识
   
## <a name="greece-national-id-card"></a>希臘國民身分證

### <a name="format"></a>格式

7-8 个字母和数字的组合加上破折号

### <a name="pattern"></a>模式

七个字母和数字（旧格式）：
- 一个字母（希腊字母的任何字母） 
- 破折号 
- 六位数字

八个字母和数字（新格式）：
- 两个字母的大写字符出现在希腊字母和拉丁字母 （ABEZHIKMNOPTYX） 
- 破折号 
- 六位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_希腊_id_card 查找与模式匹配的内容。
- 找到关键字_希腊_id_card 的关键字。

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_greece_id_card"></a>关键词_希腊_id_卡

- 希腊身份证
- 陶托蒂塔
- [][][][][
- [ ]
   
## <a name="hong-kong-identity-card-hkid-number"></a>香港身份证号码

### <a name="format"></a>格式

8-9 个字母和数字的组合加上围绕最终字符的可选括号

### <a name="pattern"></a>模式

8-9 个字母的组合：
- 1-2 个字母（不区分大小写） 
- 六位数字 
- 最后一个字符（任何数字或字母 A），这是校验数字，可选括在括号中。

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_kong_kong_id_card 查找与模式匹配的内容。
- 找到关键字_kong_kong_id_card 的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：
- 函数 Func_kong_kong_id_card 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_hong_kong_id_card"></a>关键词_洪_孔_id_卡

- 香港身份证
- 香港国际数据中心
- 身份证
- 身份证
- 香港身份证
- 香港 ID
- ·
- ·
- ·
- ·000年
- ·
- ·*
- ·*
- ·
- *
- ·
- ·
- ·00.
- ·
- ·*
- ·
- ·
- ·*
- ·
- ·
- ·
- ·
- ·[
- ·[
- ·[
- ·[
- ·0·11
- ·[
- [了）
- ·[
- ·000年
   
## <a name="india-permanent-account-number-pan"></a>印度永久帐号 （PAN）

### <a name="format"></a>格式

10 个字母或数字

### <a name="pattern"></a>模式

10 个字母或数字：
- 五个字母（不区分大小写） 
- 四位数字 
- 字母检查数字的字母

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_india_永久_帐户_编号查找与模式匹配的内容。
- 找到关键字_印度_永久_帐户_编号中的关键字。
- 校验和通过。

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_india_permanent_account_number"></a>关键词_印度_永久_帐户_编号

- 永久帐号 
- 泛 
   
## <a name="india-unique-identification-aadhaar-number"></a>印度唯一识别（阿达哈尔）编号

### <a name="format"></a>格式

包含可选空格或破折号的 12 位数字

### <a name="pattern"></a>模式

12 位：
- 四位数字 
- 可选空格或破折号 
- 四位数字 
- 可选空格或破折号 
- 最后一个数字，即校验数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果 DLP 策略在 300 个字符的接近范围内检测到这种类型的敏感信息，则 DLP 策略有 85% 的置相信度：如果函数 Func_india_aadhaar 找到与模式匹配的内容。
找到关键字_印度_阿达哈尔中的关键字。
校验和通过。
如果 DLP 策略在 300 个字符的接近范围内检测到这种类型的敏感信息，则 DLP 策略有 75% 的置相信度：如果函数 Func_india_aadhaar 找到与模式匹配的内容， 则该策略已检测到此类敏感信息。
校验和通过。
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_india_aadhar"></a>关键词_印度_阿达达尔
- 阿达尔
- 阿达尔
- Uid
- ·但
   
## <a name="indonesia-identity-card-ktp-number"></a>印度尼西亚身份证号码

### <a name="format"></a>格式

包含可选周期的 16 位数字

### <a name="pattern"></a>模式

16 位：
- 两位省代码 
- 期间（可选） 
- 两位数校验或城市代码 
- 两位数分区代码 
- 期间（可选） 
- DDMMYY 格式中的六位数字，即出生日期 
- 期间（可选） 
- 四位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_indonesia_id_card 查找与模式匹配的内容。
- 找到关键字_indonesia_id_card 的关键字。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_indonesia_id_card 查找与模式匹配的内容。

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_indonesia_id_card"></a>关键字_indonesia_id_card

- Ktp
- 卡尔图·丹达·彭杜杜克 
- 诺莫尔·因杜克·凯彭杜坎 
   
## <a name="international-banking-account-number-iban"></a>國際銀行帳號 (IBAN)

### <a name="format"></a>格式

国家/地区代码（两个字母）加上支票数字（两位数字）加上 bban 数字（最多 30 个字符）

### <a name="pattern"></a>模式

模式必须包括以下所有内容：

- 双字母国家代码
- 两个检查数字（后跟可选空格） 
- 1-7组四个字母或数字（可以用空格分隔）
- 1-3 个字母或数字

每个国家/地区的格式略有不同。 IBAN 敏感信息类型涵盖以下 60 个国家/地区：

广告， ae， al， 在， 在， az， ba， be， b， bh， ch， c， cy， cz， de， dk， 做， ee， es， fi， fo， fr， gb， ge， gi， g， gr， hr， hu， i， il， 是， 它， kw， kz， lb， li， lt， lu， lv， mc， md， me， m， m， m， m， m， m，， nl， 不， pl， pt， ro， rs， sa， se， si， sk， sm， tn， tr， vg

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_iban 查找与模式匹配的内容。
- 校验和通过。

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無

   
## <a name="ip-address"></a>IP 位址

### <a name="format"></a>格式

#### <a name="ipv4"></a>IPv4：
复杂模式，它用于 IPv4 地址的格式化（期间）和未格式化（无期间）版本

#### <a name="ipv6"></a>IPv6：
复杂模式，它表示格式化的 IPv6 数字（包括冒号）

### <a name="pattern"></a>模式

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

对于 IPv6，如果接近 300 个字符，则 DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_ipv6_地址查找与模式匹配的内容。
- 找不到来自关键字\ip 地址的关键字。

对于 IPv4，如果接近 300 个字符，则 DLP 策略 95% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_ipv4_地址查找与模式匹配的内容。
- 找到关键字\ip地址的关键字。

对于 IPv6，如果接近 300 个字符，则 DLP 策略 95% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_ipv6_地址查找与模式匹配的内容。
- 找不到来自关键字\ip 地址的关键字。

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_ipaddress"></a>关键字_ip地址

- IP（此关键字区分大小写）
- ip 地址 
- ip 地址
- 互联网协议
- IP - 的 、 的 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a>国际疾病分类（ICD-10-CM）

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 找到字典_icd_10_更新的关键字。
- 找到字典_icd_10_代码中的关键字。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 找到字典[icd_10]更新的关键字。

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

關鍵字

字典[icd_10]更新关键字词典的任何术语，它基于[国际疾病分类，第十修订，临床修改（ICD-10-CM）。](https://go.microsoft.com/fwlink/?linkid=852604) 此类型仅查找术语，而不是保险代码。

任何术语从字典_icd_10_代码关键字字典，这是基于[国际疾病分类，第十修订，临床修改（ICD-10-CM）](https://go.microsoft.com/fwlink/?linkid=852604)。 此类型只查找保险代码，而不是说明。

## <a name="international-classification-of-diseases-icd-9-cm"></a>国际疾病分类（ICD-9-CM）

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

關鍵字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 找到字典_icd_9_更新的关键字。
- 找到字典_icd_9_代码中的关键字。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 找到字典_icd_9_更新的关键字。

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>關鍵字

字典[icd_9_更新关键字词典》中的任何术语，它基于[国际疾病分类，第九修订版，临床修改（ICD-9-CM）。](https://go.microsoft.com/fwlink/?linkid=852605) 此类型仅查找术语，而不是保险代码。

任何术语从字典_icd_9_代码关键字字典，这是基于[国际疾病分类，第九修订，临床修改（ICD-9-CM）](https://go.microsoft.com/fwlink/?linkid=852605)。 此类型只查找保险代码，而不是说明。

## <a name="ireland-personal-public-service-pps-number"></a>愛爾蘭個人公用服務 (PPS) 號碼

### <a name="format"></a>格式

旧格式（至 2012 年 12 月 31 日）：
- 七位数字后跟 1-2 个字母 

新格式（2013 年 1 月 1 日及以后）：
- 七位数字后跟两个字母

### <a name="pattern"></a>模式

旧格式（至 2012 年 12 月 31 日）：
- 七位数字 
- 1-2 个字母（不区分大小写） 

新格式（2013 年 1 月 1 日及以后）：
- 七位数字 
- 字母（不区分大小写），这是字母检查数字 
- 字母"A"或"H"（不区分大小写）

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_ireland_pps 查找与模式匹配的内容。
- 下列情况之一是正确的：
    - 找到关键字_ireland_pps 的关键字。
    - 函数 Func_eu_date 以正确的日期格式查找日期。
- 校验和通过。

如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：
- 函数 Func_ireland_pps 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_ireland_pps"></a>关键字_爱尔兰_pps

- 个人公共服务号码 
- PPS 编号 
- PPS 数字 
- PPS 号 
- Pps# 
- Pps# 
- PPSN 
- 公共服务卡 
- 乌伊姆希尔·佩尔桑塔·塞尔布塞·波伊布勒 
- 乌伊姆 Psp 
- Psp 
   
## <a name="israel-bank-account-number"></a>以色列银行帐号

### <a name="format"></a>格式

13 位

### <a name="pattern"></a>模式

格式 化：
- 两位数字 
- 破折号 
- 三位数字 
- 破折号 
- 八位数字

未格式化：
- 13 个连续数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_israel_bank_帐户_编号查找与模式匹配的内容。
- 找到关键字_israel_bank_帐户_编号的关键字。

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_israel_bank_account_number"></a>关键词_israel_银行_帐户_编号

- 银行帐号 
- 银行账户 
- 帐号 
- 《》 
   
## <a name="israel-national-id"></a>以色列国民身份证

### <a name="format"></a>格式

九位数字

### <a name="pattern"></a>模式

连续九位数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_israeli_national_id_number 查找与模式匹配的内容。
- 找到关键字_以色列_国家_ID的关键字。
- 校验和通过。

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_israel_national_id"></a>关键词_以色列_国家_ID

- 《》 
- 国家身份证号码
   
## <a name="italy-drivers-license-number"></a>意大利驾照号码

### <a name="format"></a>格式

10 个字母和数字的组合

### <a name="pattern"></a>模式

- 10 个字母和数字的组合：
- 一个字母（不区分大小写） 
- 字母"A"或"V"（不区分大小写） 
- 七个字母（不区分大小写）、数字或下划线字符 
- 一个字母（不区分大小写）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_italy_驱动程序_许可证_编号查找与模式匹配的内容。
- 找到关键字_italy_驱动程序_许可证_编号的关键字。

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_italy_drivers_license_number"></a>关键词_意大利_驱动程序_许可证_编号

- numero di 专利迪吉达 
- 专利迪吉达 
   
## <a name="japan-bank-account-number"></a>日本银行帐号

### <a name="format"></a>格式

七或八位

### <a name="pattern"></a>模式

银行帐号：
- 七或八位
- 银行账户分行代码：
- 四位数字 
- 空格或破折号（可选） 
- 三位数字

校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_jp_bank_帐户查找与模式匹配的内容。
- 找到关键字_jp_bank_帐户的关键字。
- 下列情况之一是正确的：
- 函数 Func_jp_bank_帐户_分支_代码查找与模式匹配的内容。
- 找到关键字_jp_bank_分支_code中一个关键字。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_jp_bank_帐户查找与模式匹配的内容。
- 找到关键字_jp_bank_帐户的关键字。

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_bank_account"></a>关键字_jp_银行_帐户

- 支票帐号 
- 支票帐户 
- 支票帐户# 
- 检查 Acct 编号 
- 检查 Acct# 
- 检查 Acct 号 
- 支票帐户号 
- 银行帐号 
- 银行账户 
- 银行账户# 
- 银行编号 
- 银行 Acct# 
- 银行增加号 
- 银行账户号 
- 储蓄帐号 
- 储蓄账户 
- 储蓄账户# 
- 节省费用编号 
- 节省费用# 
- 节省费用 
- 储蓄账户号 
- 借方帐号 
- 借方帐户 
- 借方帐户# 
- 借方扣号 
- 借方 Acct# 
- 借方确认号 
- 借方帐户号 
- ·* 
- #アカウントの確認 
- #勘定の確認 
- · 
- · 
- ·* 
- · 
- · 
- ·* 
- [acct] 
- · 
- ·*
- ·* 
- · 
- · 
- ·* 
- · 
- ·* 
- ·* 
- ·* 
- * 
- [ 
- * 
- [ ] 
- * * * 
- ·* 

#### <a name="keyword_jp_bank_branch_code"></a>关键字_jp_bank_分支_代码

奥特马基

## <a name="japan-drivers-license-number"></a>日本驾照号码

### <a name="format"></a>格式

12 位

### <a name="pattern"></a>模式

12 个连续数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_jp_驱动程序_许可证_编号查找与模式匹配的内容。
- 找到关键字_jp_驱动程序_许可证号码的关键字。

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_drivers_license_number"></a>关键字_jp_驱动程序_许可证_编号

- Dl# 
- DL# 
- Dls# 
- DLS* 
- 驾照 
- 驾驶执照 
- 驾驶执照 
- 驾驶执照 
- 驾驶执照 
- 驾驶执照 
- 驾驶执照 
- 利利奇# 
- LIC* 
- 利茨# 
- 状态 ID 
- 状态标识 
- 状态标识号 
- · 
- ·007· 
- *ID
- * * 
- · 
- ·000年 
- · 
- ·* 
   
## <a name="japan-passport-number"></a>日本护照号码

### <a name="format"></a>格式

两个字母后跟七位数字

### <a name="pattern"></a>模式

两个字母（不区分大小写）后跟七位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_jp_passport 查找与模式匹配的内容。
- 找到关键字_jp_Passport中一个关键字。

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_passport"></a>关键词_jp_护照

- · 
- ·\\\\\\\\\\\\\\\\\\\\\\ 
- * * * * 
- · 
   
## <a name="japan-resident-registration-number"></a>日本居民登记号

### <a name="format"></a>格式

11 位

### <a name="pattern"></a>模式

11 个连续数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_jp_驻留_注册_编号查找与模式匹配的内容。
- 找到关键字_jp_居民_注册_编号的关键字。

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_resident_registration_number"></a>关键字_jp_居民_注册_编号

- 居民登记号
- 居民登记号 
- 居民基本登记号码 
- 居民登记号 
- 居民登记号 
- 居民基本登记处号 
- 基本居民登记册号 
- [][][ 
- 住民基本登録番号、登録番号 
- ·\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\ 
- ·000年 

   
## <a name="japan-social-insurance-number-sin"></a>日本社会保险号

### <a name="format"></a>格式

7-12 位

### <a name="pattern"></a>模式

7-12 位：
- 四位数字 
- 连字符（可选） 
- 六位或
- 7-12 个连续数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_jp_sin 查找与模式匹配的内容。
- 找到关键字_jp_sin 中的关键字。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_jp_sin_pre_1997 查找与模式匹配的内容。
- 找到关键字_jp_sin 中的关键字。

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_sin"></a>关键字_jp_sin

- 社会保险号 
- 社会保险数字 
- 社会保险号 
- * 
- ·* 

## <a name="japanese-residence-card-number"></a>日本居留卡号

### <a name="format"></a>格式

12 个字母和数字

### <a name="pattern"></a>模式

12 个字母和数字：
- 两个字母（不区分大小写）
- 八位数字 
- 两个字母（不区分大小写）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_jp_暂留_card_number 查找与模式匹配的内容。
- 找到关键字_jp_居住_卡_号码的关键字。

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_jp_residence_card_number"></a>关键字_jp_居住_卡_编号

- 居住卡号
- 居住卡无
- 居住卡#
- ·[
   
## <a name="malaysia-id-card-number"></a>马来西亚身份证号码

### <a name="format"></a>格式

包含可选连字符的 12 位数字

### <a name="pattern"></a>模式

12 位：
- 格式为 YYMMDD 的六位数字，即出生日期 
- 破折号（可选） 
- 双字母出生地代码 
- 破折号（可选） 
- 三个随机数字 
- 一位性别代码

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_malaysia_id_card_number 查找与模式匹配的内容。
- 找到关键字_马马\id_card_编号的关键字。

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_malaysia_id_card_number"></a>关键词_马来西亚_id_卡_编号

- 数字应用卡
- i/c
- i/c 否
- Ic
- ic 无
- 身份证
- 身份证
- 身份证
- k/p
- k/p 否
- 卡德·阿库恩·迪里
- 卡德·阿普利卡西数字
- 卡德彭纳兰马来西亚
- Kp
- kp 否
- 迈卡德
- 迈卡斯
- 迈基德
- 迈普尔
- 迈门特拉
- 马来西亚身份证
- 马来西亚身份证
- 恩里克
- 个人身份证
   
## <a name="netherlands-citizens-service-bsn-number"></a>荷兰公民服务 （BSN） 号码

### <a name="format"></a>格式

包含可选空格的 8-9 位数字

### <a name="pattern"></a>模式

8-9 位：
- 三位数字 
- 空格（可选） 
- 三位数字 
- 空格（可选） 
- 2-3 位

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_荷兰_bsn 查找与模式匹配的内容。
- 找到关键字_荷兰_bsn的关键字。
- 函数 Func_eu_date2 以正确的日期格式查找日期。
- 校验和通过。

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_netherlands_bsn"></a>关键字_荷兰\bsn

- 公民服务号码 
- BSN 
- 汉堡服务努默 
- 苏武努默 
- 佩松斯格邦登·努默 
- 佩松斯努默    

   
## <a name="new-zealand-ministry-of-health-number"></a>新西兰卫生部编号

### <a name="format"></a>格式

三个字母、一个空格（可选）和四位数字

### <a name="pattern"></a>模式

三个字母（不区分大小写）空格（可选）四位数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_new___________health_s_health_s_s_health_s_s_health_s_health_s_s_health_s_s 查找与模式匹配的内容。
- 找到关键字_nz_字词的关键字。
- 校验和通过。

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

關鍵字

关键字_nz_字词

- 国家卫生报告 
- JPRatingExplicitAllowed 
- 健康情況 
- 治疗 
   
## <a name="norway-identification-number"></a>挪威身份证号码

### <a name="format"></a>格式

11 位

### <a name="pattern"></a>模式

11 位：
- DDMMYY 格式中的六位数字，即出生日期 
- 三位个人号码 
- 两个检查数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_norway_id_number 查找与模式匹配的内容。
- 找到关键字_norway_id_号码的关键字。
- 校验和通过。
- 如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_norway_id_numbe 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_norway_id_number"></a>关键字_norway_id_编号

- 个人识别号码
- 挪威身份证号码
- 身份证号码
- 识别
- 人物
- 费德塞尔斯努默

   
## <a name="philippines-unified-multi-purpose-id-number"></a>菲律宾统一多用途身份证号码

### <a name="format"></a>格式

12 位数字由连字符分隔

### <a name="pattern"></a>模式

12 位：
- 四位数字 
- 连字符 
- 七位数字 
- 连字符 
- 一位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_philippines_unified_id 查找与模式匹配的内容。
- 找到关键字_philippines_id 的关键字。

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_philippines_id"></a>关键字_菲律宾_id

- 统一多用途 ID 
- UMID 
- 身份证 
- 皮纳格-伊桑多莱宁 ID
   
## <a name="poland-identity-card"></a>波蘭身分證明卡

### <a name="format"></a>格式

三个字母和六位数字

### <a name="pattern"></a>模式

三个字母（不区分大小写）后跟六位数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果 DLP 策略在 300 个字符的接近范围内检测到这种类型的敏感信息，则 DLP 策略有 75% 的置相信度：如果函数 Func_polish_national_id 查找与模式匹配的内容。
找到关键字_波兰_国家_id_passport_号码的关键字。
校验和通过。

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_polish_national_id_passport_number"></a>关键字_波兰_国家_id_护照_编号

- 多埃德·奥索比斯蒂
- 努默·多沃杜·奥索比斯特戈
- 纳兹瓦伊·努塞尔·多沃杜·奥索比斯特戈
- 纳兹瓦·伊·多沃杜·奥索比斯特戈
- 纳兹瓦·伊·里·多沃杜·托萨莫奇
- 多埃德·托萨莫奇
- 道琼斯指数。 操作系统。

   
## <a name="poland-national-id-pesel"></a>波蘭國民身分證 (PESEL)

### <a name="format"></a>格式

11 位

### <a name="pattern"></a>模式

11 个连续数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_pesel_标识_编号查找与模式匹配的内容。
- 找到关键字_pesel_标识_编号的关键字。
- 校验和通过。

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_pesel_identification_number"></a>关键字_pesel_标识_数字

- Nr PESEL
- 佩塞尔   

   
## <a name="poland-passport"></a>波蘭護照

### <a name="format"></a>格式

两个字母和七位数字

### <a name="pattern"></a>模式

两个字母（不区分大小写）后跟七位数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_polish_Passport_number 查找与模式匹配的内容。
- 找到关键字_波兰_国家_id_passport_号码的关键字。
- 校验和通过。

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_polish_national_id_passport_number"></a>关键字_波兰_国家_id_护照_编号

- 努默·帕斯波特
- 星期日。 帕什波特
- 帕什波特

   
## <a name="portugal-citizen-card-number"></a>葡萄牙公民證號碼

### <a name="format"></a>格式

八位数字

### <a name="pattern"></a>模式

八位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_portugal_citizen_card_card 查找与模式匹配的内容。
- 找到关键字_portugal_公民卡的关键字。

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_portugal_citizen_card"></a>关键词_portugal_公民_卡片

- 公民卡
- 国民身份证
- 副本
- 卡托·德西达多
- 比埃尔特·德·伊登达德
   
## <a name="saudi-arabia-national-id"></a>沙特阿拉伯国民身份证

### <a name="format"></a>格式

10 位

### <a name="pattern"></a>模式

10 个连续数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_saudi_arabia_national_id 查找与模式匹配的内容。
- 找到关键字_saudi_arabia_national_id 的关键字。

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_saudi_arabia_national_id"></a>关键字_沙特_阿拉伯\国家_id

- 身份证 
- I 卡号 
- 識別碼 
- 《》 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>新加坡国民登记身份证号码

### <a name="format"></a>格式

九个字母和数字

### <a name="pattern"></a>模式

- 九个字母和数字：
- 字母"F"、"G"、"S"或"T"（不区分大小写） 
- 七位数字 
- 字母检查数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_singapore_nric 查找与模式匹配的内容。
- 找到来自关键字_新加坡\nric的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_singapore_nric 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_singapore_nric"></a>关键字_新加坡\nric

- 国民登记身份证 
- 身份证号码 
- 国家 
- Ic 
- 外国身份证号码 
- 翅 
- · 
- · 
   
## <a name="south-africa-identification-number"></a>南非身份证号码

### <a name="format"></a>格式

13 位可能包含空格的数字

### <a name="pattern"></a>模式

13 位：
- 格式为 YYMMDD 的六位数字，即出生日期 
- 四位数字 
- 单位数公民身份指标 
- 数字"8"或"9" 
- 一个数字，即校验和数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_south_africa_id_number 查找与模式匹配的内容。
- 找到关键字_南非_非洲_标识_编号的关键字。
- 校验和通过。

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_south_africa_identification_number"></a>关键词_南非_非洲_识别_数字

- 身份证
- ID
- 识别 
   
## <a name="south-korea-resident-registration-number"></a>韩国居民登记号

### <a name="format"></a>格式

包含连字符的 13 位数字

### <a name="pattern"></a>模式

13 位：
- 格式为 YYMMDD 的六位数字，即出生日期 
- 连字符 
- 由世纪和性别决定的一个数字 
- 四位出生区域代码 
- 一个数字，用于区分上述数字相同的人员 
- 校验数字。

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_south_korea_驻留_数字查找与模式匹配的内容。
- 找到关键字_南_韩国_居民号码的关键字。
- 校验和通过。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_south_korea_驻留_数字查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_south_korea_resident_number"></a>关键词_南_韩国_居民_号码

- 国民身份证 
- 公民登记号码 
- 朱明·德翁诺克·贝尼奥 
- RRN 
- 《 》
   
## <a name="spain-social-security-number-ssn"></a>西班牙社會安全號碼 (SSN)

### <a name="format"></a>格式

11-12 位

### <a name="pattern"></a>模式

11-12 位：
- 两位数字 
- 正向斜杠（可选） 
- 7-8 位 
- 正向斜杠（可选） 
- 两位数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_spanish_social_安全_编号查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

無

## <a name="sql-server-connection-string"></a>SQL 服务器连接字符串

### <a name="format"></a>格式

字符串"用户 ID"、"用户 ID"、"uid"或"UserId"后跟以下模式中概述的字符和字符串。

### <a name="pattern"></a>模式

- 字符串"用户 ID"、"用户 ID"、"uid"或"用户 Id"
- 1-200 个小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"密码"或"pwd"，其中"pwd"前面没有小写字母
- 等号 （*）
- 任何不是美元符号 （$）、百分比符号 （%））的字符（），大于符号 （>），在符号 （*）、 引号 （）、分号 （;)、左大括号 （*） 或左括号 （*）
- 非分号（;)、正斜杠 （/） 或引号 （"））的 7-128 个字符的任意组合
- 分号 （;)或引号 （"）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_SQLServer 连接字符串查找与模式匹配的内容。
- **找不到**来自 CEP_全局筛选的关键字。
- 正则表达式 CEP_Password PlaceHolder**找不到**与模式匹配的内容。
- 正则表达式 CEP_Common 示例关键字**找不到**与模式匹配的内容。

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="cep_globalfilter"></a>CEP_全局筛选

- 一些密码
- 一些密码
- 秘密密码
- 样品

#### <a name="cep_passwordplaceholder"></a>CEP_密码放置器

（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。

- 密码或 pwd 后跟 0-2 空格、等号 （+）、0-2 空格和星号 （*） -- OR --
- 密码或密码后跟：
    - 等号 （*）
    - 小于符号 （<）
    - 1-200 个字符的任意组合，这些字符是大写或小写字母、数字、星号 （*）、连字符 （-）、下划线 （*） 或空格字符
    - 大于符号 （>）

#### <a name="cep_commonexamplekeywords"></a>CEP_通用示例关键字

（请注意，从技术上讲，此敏感信息类型使用正则表达式而不是关键字列表来标识这些关键字。

- 康托索
- 法布里卡姆
- 北风
- 沙 箱
- 一个盒子
- 本地 主机
- 127.0.0.1
- 试验。<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->网

## <a name="sweden-national-id"></a>瑞典國民身分證號

### <a name="format"></a>格式

10 或 12 位数字和可选分隔符

### <a name="pattern"></a>模式

10 或 12 位数字和可选分隔符：
- 2-4 位（可选） 
- 日期格式 YYMMDD 的六位数字 
- "-"或"+"（可选）的分隔符，加上
- 四位数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_swedish_national_identifier 查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

否
   
## <a name="sweden-passport-number"></a>瑞典護照號碼

### <a name="format"></a>格式

八位数字

### <a name="pattern"></a>模式

连续八位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_sweden_Passport_number 查找与模式匹配的内容。
- 下列情况之一是正确的：
    - 找到关键字_Passport中一个关键字。
    - 找到关键字_sweden_Passport 的关键字。

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_sweden_passport"></a>关键词_瑞典护照

- 签证要求 
- 外国人登记卡 
- 申根签证 
- 申根签证 
- 签证处理 
- 签证类型 
- 单个条目 
- 多个条目 
- G3 手续费 

#### <a name="keyword_passport"></a>关键词_护照

- 护照号码 
- 护照号 
- 护照# 
- 护照# 
- 护照ID 
- 护照诺 
- 护照号码 
- · 
- ·\\\\\\\\\\\\\\\\\\\\\\ 
- * * * * 
- · 
- 努梅罗·德·德费波特 
- 路路港 n | 
- 路路港非 
- 帕塞波特# 
- 帕塞波特# 
- 帕塞波特农 
- 帕塞波特 | 
   
## <a name="swift-code"></a>SWIFT 代码

### <a name="format"></a>格式

四个字母后跟 5-31 个字母或数字

### <a name="pattern"></a>模式

四个字母后跟 5-31 个字母或数字：
- 四个字母的银行代码（不区分大小写） 
- 可选空间 
- 4-28 个字母或数字（基本银行帐号 （BBAN）） 
- 可选空间 
- 1-3 个字母或数字（BBAN 的余数）

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_swift 查找与模式匹配的内容。
- 找到关键字_swift 的关键字。

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_swift"></a>关键字_swift

- 国际标准化组织 9362 
- iso 9362 
- iso9362 
- 迅速\# 
- 快速码 
- 快速数 
- 快速路由编号 
- 快速代码 
- 快速数# 
- 快速路由编号 
- 二元数 
- 二元代码 
- 比奇\# 
- 比奇\# 
- 银行标识符代码 
- ·09362 
- * 
- SWIFT | 
- 斯威夫特 
- * 
- BIC_ 
- BIC | 
- ** * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * 
- 国际正常化组织 9362 
- 快速\# 
- 代码 SWIFT 
- 勒努梅罗·德·斯威夫特 
- 迅速的numéro d'acheminement 
- 勒努梅罗BIC 
- \#BIC 
- 代码识别器 de banque 
   
## <a name="taiwan-national-id"></a>台湾国民身份证

### <a name="format"></a>格式

一个字母（英文）后跟九位数字

### <a name="pattern"></a>模式

一个字母（英文）后跟九位数字：
- 一个字母（英文，不区分大小写） 
- 数字"1"或"2" 
- 八位数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_t_t_national_id 查找与模式匹配的内容。
- 找到关键字_台湾_国家_id的关键字。
- 校验和通过。

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_taiwanese_national_id"></a>关键字_台湾_国家_id

- ·007年 
- · 
- · 
- | 
- · 
- · 
- · 
- | 
- [ ] 
- [ ] 
- · 
- ·000年 
- * 
- ·000年   
   
## <a name="taiwan-passport-number"></a>台湾护照号码

### <a name="format"></a>格式

- 生物识别护照号码：九位数字
- 非生物护照号码：九位数字

### <a name="pattern"></a>模式
生物识别护照号码：
- 数字"3" 
- 八位数字

非生物护照号码：
- 九位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_taiwan_Passport 查找与模式匹配的内容。
- 找到关键字_taiwan_Passport的关键字。

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_taiwan_passport"></a>关键词_台湾护照

- 中华民国护照号码 
- 护照号码 
- 护照无 
- 护照数量 
- 护照# 
- · 
- · 
- 赞胡埃·明古什·哈佐
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>台湾居民证（ARC/TARC）号码

### <a name="format"></a>格式

10 个字母和数字

### <a name="pattern"></a>模式

10 个字母和数字：
- 两个字母（不区分大小写） 
- 八位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_TAIWAN_驻留_证书查找与模式匹配的内容。
- 找到关键字_taiwan_居民\证书中的关键字。

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_taiwan_resident_certificate"></a>关键词_台湾_居民_证书

- 居民证 
- 居民证书 
- 居民证书。 
- 身份证 
- 外国人居住证明 
- 弧 
- 台湾地区居民证 
- TARC 
- · 
- ·* 
- [ 

## <a name="thai-population-identification-code"></a>泰国人口识别码

### <a name="format"></a>格式

13 位

### <a name="pattern"></a>模式

13 位：
- 第一个数字不是 0 或 9 
- 12 位

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_Thai_Citizen_Id 查找与模式匹配的内容。
- 找到关键字_泰语_公民\Id的关键字。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_Thai_Citizen_Id 查找与模式匹配的内容。

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_thai_citizen_id"></a>关键词_泰语+公民\ID

- 身份证号码
- 识别号
- 《》
- 《》
- 《》
- 《》
  
## <a name="turkish-national-identification-number"></a>土耳其国民身份证号码

### <a name="format"></a>格式

11 位

### <a name="pattern"></a>模式

11 位

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_土耳其_National_Id 查找与模式匹配的内容。
- 找到关键字_土耳其语_国家_Id的关键字。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_土耳其_National_Id 查找与模式匹配的内容。

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_turkish_national_id"></a>关键字_土耳其语_国家_ID

- TC 金利克 否
- TC 金利克·努马拉斯
- 瓦坦达莱克·努马拉斯
- 瓦坦达莱克 否

## <a name="uk-drivers-license-number"></a>英国。 驾驶执照号码

### <a name="format"></a>格式

指定格式的 18 个字母和数字的组合

### <a name="pattern"></a>模式

18 个字母和数字：
- 五个字母（不区分大小写）或数字"9"代替字母 
- 一位数字 
- 出生日期日期格式 DDMMY 中的五位数字 
- 两个字母（不区分大小写）或数字"9"代替字母 
- 五位数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_uk_驱动程序_许可证查找与模式匹配的内容。
- 找到关键字_uk_驱动程序_许可证的关键字。
- 校验和通过。

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_uk_drivers_license"></a>关键字_uk_驱动程序_许可证

- DVLA 
- 轻型货车 
- 四轮摩托车 
- 汽车 
- 125cc 
- 侧车 
- 三轮车 
- 摩托车 
- 照片卡许可证 
- 学员驱动程序 
- 牌照持有人 
- 牌照持有人 
- 驾驶执照 
- 驾驶执照 
- 双控制车 
   
## <a name="uk-electoral-roll-number"></a>英国。 选举人名册号码

### <a name="format"></a>格式

两个字母后跟 1-4 位

### <a name="pattern"></a>模式

两个字母（不区分大小写）后跟 1-4 个数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_uk_选举查找与模式匹配的内容。
- 找到关键字_uk_选举的关键字。

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_uk_electoral"></a>关键字_uk_选举

- 理事会提名 
- 提名表格 
- 选举登记册 
- 选举名册

   
## <a name="uk-national-health-service-number"></a>英国。 国家卫生服务号码

### <a name="format"></a>格式

10-17 位由空格分隔的数字

### <a name="pattern"></a>模式

10-17 位：
- 3 位或 10 位 
- 空间 
- 三位数字 
- 空间 
- 四位数字

### <a name="checksum"></a>校验

是

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_uk_nhs_number 查找与模式匹配的内容。
- 下列情况之一是正确的：
    - 找到关键字_uk_nhs_号码的关键字。
    - 找到关键字_uk_nhs_number1的关键字。
    - 找到关键字_uk_nhs_number_dob 的关键字。
- 校验和通过。

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字
   
#### <a name="keyword_uk_nhs_number"></a>关键字_uk_nhs_数字

- 国家卫生服务 
- Nhs 
- 卫生服务管理局 
- 卫生当局

#### <a name="keyword_uk_nhs_number1"></a>关键字_uk_nhs_数字1

- 患者 ID 
- 患者识别 
- 患者无 
- 患者人数

#### <a name="keyword_uk_nhs_number_dob"></a>关键词_uk_nhs_number_dob

- Gp 
- DOB 
- D.O.B 
- 出生日期 
- 出生日期 
   
## <a name="uk-national-insurance-number-nino"></a>英国。 国民保险号码

### <a name="format"></a>格式

7 个字符或 9 个字符，由空格或破折号分隔

### <a name="pattern"></a>模式

两种可能的模式：

- 两个字母（有效的 NINOs 仅使用前缀中的某些字符，此模式可验证该字符;不区分大小写）
- 六位数字
- "A"、"B"，"C"或"D"（与前缀一样，后缀中只允许某些字符;不区分大小写）

或

- 两个字母
- 空格或破折号
- 两位数字
- 空格或破折号
- 两位数字
- 空格或破折号
- 两位数字
- 空格或破折号
- "A"，"B"，"C"或"D"

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_uk_nino 查找与模式匹配的内容。
- 找到关键字_uk_nino 的关键字。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_uk_nino 查找与模式匹配的内容。
- 找不到来自关键字_uk_nino 的关键字。

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_uk_nino"></a>关键词_uk_nino

- 国民保险号 
- 国家保险缴款 
- 保护法 
- 保险 
- 社会安全号码 
- 保险申请 
- 医疗应用 
- 社会保险 
- 医疗护理 
- 社会保障 
- 英国 
- 保险    
   
## <a name="us--uk-passport-number"></a>美国/英国 护照号码

### <a name="format"></a>格式

九位数字

### <a name="pattern"></a>模式

连续九位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_usa_uk_passport 查找与模式匹配的内容。
- 找到关键字_Passport中一个关键字。

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_passport"></a>关键词_护照

- 护照号码 
- 护照号 
- 护照# 
- 护照# 
- 护照ID 
- 护照诺 
- 护照号码 
- · 
- ·\\\\\\\\\\\\\\\\\\\\\\ 
- * * * * 
- · 
- 努梅罗·德·德费波特 
- 路路港 n | 
- 路路港非 
- 帕塞波特# 
- 帕塞波特# 
- 帕塞波特农 
- 帕塞波特 | 
   
## <a name="us-bank-account-number"></a>美国银行账户号码

### <a name="format"></a>格式

8-17 位

### <a name="pattern"></a>模式

8-17 个连续数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 正则表达式 Regex_usa_bank_帐户_编号查找与模式匹配的内容。
- 找到关键字_usa_Bank_帐户的关键字。

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_usa_bank_account"></a>关键字_usa_银行_帐户

- 支票帐号 
- 支票帐户 
- 支票帐户# 
- 检查 Acct 编号 
- 检查 Acct# 
- 检查 Acct 号 
- 支票帐户号 
- 银行帐号 
- 银行账户# 
- 银行编号 
- 银行 Acct# 
- 银行增加号 
- 银行账户号 
- 储蓄帐号 
- 储蓄账户。 
- 储蓄账户# 
- 节省费用编号 
- 节省费用# 
- 节省费用 
- 储蓄账户号 
- 借方帐号 
- 借方帐户 
- 借方帐户# 
- 借方扣号 
- 借方 Acct# 
- 借方确认号 
- 借方帐户号 
   
## <a name="us-drivers-license-number"></a>美国驾照号码

### <a name="format"></a>格式

取决于状态

### <a name="pattern"></a>模式

取决于州 - 例如，纽约：
- 九位格式为 ddd ddd dd 的数字将匹配。
- 九位数字（如 ddddddddd）将不匹配。

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_new_york_驱动程序_许可证_编号查找与模式匹配的内容。
- 找到关键字_状态_名称_驱动程序_许可证_名称的关键字。
- 找到关键字_us_驱动程序_许可证的关键字。

如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：
- 函数 Func_new_york_驱动程序_许可证_编号查找与模式匹配的内容。
- 找到关键字_状态_名称_驱动程序_许可证_名称的关键字。
- 找到关键字_us_驱动程序_许可证_缩写的关键字。
- 找不到关键字_us_驱动程序_许可证的关键字。

```xml
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_us_drivers_license_abbreviations"></a>关键字_us_驱动程序_许可证_缩写

- Dl 
- Dls 
- 民盟 
- CDLS 
- ID 
- Id 
- Dl# 
- Dls# 
- 民盟# 
- CDLS# 
- Id#
- Id# 
- 識別碼 
- 身份证号码 
- LIC 
- LIC# 

#### <a name="keyword_us_drivers_license"></a>关键字_us_驱动程序_许可证

- 司机 
- 司机 
- 驾驶执照 
- 驾驶执照 
- 司机李克 
- 司机利茨 
- 驾照 
- 驾驶执照 
- 驱动程序 
- 司机Lics 
- 驾驶执照 
- 驾驶执照 
- 司机许可证 
- 司机利茨 
- 驾驶执照 
- 驾驶执照 
- 司机'Lic 
- 司机的Lics 
- 驾驶执照 
- 驾驶执照 
- 司机的许可证 
- 司机的Lics 
- 驾驶执照 
- 驾驶执照
- 驾驶员的 
- 驾驶员的 
- 驾驶执照 
- 驾驶执照 
- 驾驶员的许可证 
- 司机的许可证 
- 驾驶执照 
- 驾驶执照 
- 识别号 
- 识别号 
- 识别# 
- 身份证 
- 身份证 
- 身份证 
- 身份证 
- 司机# 
- 司机# 
- 驾驶执照# 
- 驾驶执照# 
- 司机李克# 
- 司机利茨# 
- 驾照# 
- 驾驶执照# 
- 驱动程序# 
- 司机Lics# 
- 驾驶执照# 
- 驾驶执照# 
- 司机许可证# 
- 司机利茨# 
- 驾驶执照# 
- 驾驶执照# 
- 司机'Lic# 
- 司机的Lics# 
- 驾驶执照# 
- 驾驶执照# 
- 司机的许可证# 
- 司机的Lics# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶员的# 
- 驾驶员的# 
- 驾驶执照# 
- 驾驶执照# 
- 驾驶员的许可证# 
- 司机的许可证# 
- 驾驶执照# 
- 驾驶执照# 
- 身份证# 
- 身份证# 
- 身份证# 
- 身份证# 


#### <a name="keyword_state_name_drivers_license_name"></a>关键字_状态_名称_驱动程序_许可证_名称

- 状态缩写（例如，"NY"） 
- 州名称（例如"纽约"）    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a>美国个人纳税人识别号 （ITIN）

### <a name="format"></a>格式

以"9"开头，包含"7"或"8"作为第四位数字的九位数字，可选用空格或破折号格式

### <a name="pattern"></a>模式

格式 化：
- 数字"9" 
- 两位数字 
- 空格或破折号 
- "7"或"8" 
- 数字 
- 空格或破折号 
- 四位数字

未格式化：
- 数字"9" 
- 两位数字 
- "7"或"8" 
- 五位数字

### <a name="checksum"></a>校验

否

### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_格式化_itin 查找与模式匹配的内容。
- 以下至少一项是正确的：
    - 找到关键字_itin 中的关键字。
    - 函数 Func_us_地址以正确的日期格式查找地址。
    - 函数 Func_us_date 以正确的日期格式查找日期。
    - 找到关键字_itin_协作中的关键字。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_无格式化_itin 查找与模式匹配的内容。
- 以下至少一项是正确的：
    - 找到关键字_itin_协作中的关键字。
    - 函数 Func_us_地址以正确的日期格式查找地址。
    - 函数 Func_us_date 以正确的日期格式查找日期。

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_itin"></a>关键字_itin

- 纳税人 
- 税 ID 
- 税务识别 
- itin 
- Ssn 
- 锡 
- 社会保障 
- 纳税人 
- itins 
- 出租车 
- 个人纳税人 

#### <a name="keyword_itin_collaborative"></a>关键词_itin_协作

- License 
- Dl 
- DOB 
- 出生日期 
- 生日 
- 出生日期 
   
## <a name="us-social-security-number-ssn"></a>美国社会安全号码 （SSN）

### <a name="format"></a>格式

9 位数字，可能采用格式化或未格式化的模式

> [!NOTE]
> 如果在 2011 年年中之前发布，SSN 具有强格式，其中数字的某些部分必须属于有效范围（但没有校验和）。

### <a name="pattern"></a>模式

四种函数以四种不同的模式查找 SSN：
- Func_ssn 查找具有 2011 年前强格式的 SSN，这些格式采用破折号或空格（dd-dd-dd-dd dd dd dd dd dd dd ddd ddd） 格式设置格式
- Func_无格式化_ssn 查找具有 2011 年前强格式的 SSN，这些格式未格式化为九位连续数字 （ddddddd）
- Func_随机_格式化_ssn 查找 2011 年后使用破折号或空格格式化的 SSN（dd-dd-dd-ddd or ddd dd dd dd dd dd dd ddd）
- Func_随机_未格式化_ssn 查找未格式化为九位连续数字的 2011 后 SSN（ddddddd）

### <a name="checksum"></a>校验

否


### <a name="definition"></a>定義

如果接近 300 个字符，DLP 策略 85% 确信检测到这种类型的敏感信息：
- 函数 Func_ssn 查找与模式匹配的内容。
- 找到关键字\sn 的关键字。
- 函数 Func_us_date 以正确的日期格式查找日期。
- 函数 Func_us_地址以正确的格式查找地址。

如果接近 300 个字符，DLP 策略 75% 确信检测到这种类型的敏感信息：
- 函数 Func_无格式化_ssn 查找与模式匹配的内容。
- 找到关键字\sn 的关键字。
- 函数 Func_us_date 以正确的日期格式查找日期。
- 函数 Func_us_地址以正确的格式查找地址。

如果接近 300 个字符，DLP 策略有 65% 的置相信度检测到这种类型的敏感信息：
- 函数 Func_随机_格式化_ssn 查找与模式匹配的内容。
- 找到关键字\sn 的关键字。
- 函数 Func_us_date 以正确的日期格式查找日期。
- 函数 Func_us_地址以正确的格式查找地址。

如果接近 300 个字符，DLP 策略的置量为 55%，它检测到这种类型的敏感信息：
- 函数 Func_随机_未格式化_ssn 查找与模式匹配的内容。
- 找到关键字\sn 的关键字。
- 函数 Func_us_date 以正确的日期格式查找日期。
- 函数 Func_us_地址以正确的格式查找地址。

如果接近 300 个字符，DLP 策略有 40% 的确信检测到这种类型的敏感信息：
- 函数 Func_ssn 查找与模式匹配的内容。
- 函数 Func_无格式化_ssn 找不到与模式匹配的内容。
- 函数 Func_随机_未格式化_ssn 找不到与模式匹配的内容。
- 找不到关键字_sn 中产生的关键字。
 
或

- 函数 Func_随机_格式化_ssn 查找与模式匹配的内容。
- 函数 Func_无格式化_ssn 找不到与模式匹配的内容。
- 函数 Func_随机_未格式化_ssn 找不到与模式匹配的内容。
- 找不到关键字_sn 中产生的关键字。

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>關鍵字

#### <a name="keyword_ssn"></a>关键字\ssn

- 社会保障 
- 社会保障# 
- 索克秒 
- Ssn 
- SSNS 
- Ssn# 
- SS# 
- Ssid 
   

