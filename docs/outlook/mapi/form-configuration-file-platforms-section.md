---
title: 表单配置文件 [平台] 部分
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3b9b3dc0-4f82-468b-8e77-0374c5b196f4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7439de5b91cefe89eba2f9395595d4a7c8ca3ec5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419126"
---
# <a name="form-configuration-file-platforms-section"></a>表单配置文件 [平台] 部分

**适用于**：Outlook 2013 | Outlook 2016 
  
**[平台]** 一节列出了此窗体支持的完整平台集。 每个平台条目都包含前缀**平台。** _字符串_, 其中_字符串_是平台的任意字符串代码。 每个字符串对应于单个 **[平台]** 部分的**CPU**项。 **[平台]** 部分中的每个条目都定义了一个_平台字符串_, 该字符串引用后续的 **[平台。** _平台字符串_**** "一节, 如下所示。 
  
**[平台]** 一节列出了此窗体支持的完整平台集。 每个平台条目都包含前缀**平台。** _字符串_, 其中_字符串_是平台的任意字符串代码。 每个字符串对应于单个 **[平台]** 部分的**CPU**项。 **[平台]** 部分中的每个条目都定义了一个_平台字符串_, 该字符串引用后续的 **[平台。** _平台字符串_**** "一节, 如下所示。 
  
**平台**
  
**平台**。 _字符串_ =  _平台字符串_
  
下面是 **[平台]** 部分的一个示例。 
  
```cpp
[Platforms]
Platform.1 = NTx86
Platform.2 = Win95

```

每个 **[平台。** _平台字符串_**]** 部分包含两个必需的条目: **CPU**和**OSVersion**。 **CPU**条目指定处理器, **OSVersion**项指定操作系统。 有效的**CPU**值如下表所述。 
  
|**CPU 条目**|**处理器**|
|:-----|:-----|
|Ix86  <br/> |Intel 80x86 和奔腾系列处理器, 以及来自 AMD、Cyrix、NextGen 和其他制造商的等效处理器。  <br/> |
|mip  <br/> |MIPS R4000 系列处理器。  <br/> |
|AXP  <br/> |数字设备公司 Alpha AXP 处理器。  <br/> |
|PPC  <br/> |Motorola 电源 PC 系列处理器。  <br/> |
|M68  <br/> |Mororola 68x00 系列处理器。  <br/> |
   
有效的**OSVersion**值如下表所述。 
  
|**OSVersion 条目**|**操作系统**|
|:-----|:-----|
|win 3。1  <br/> |windows 3.1 和 windows for 工作组3.11。  <br/> |
|winnt 3。5  <br/> |Windows NT 3.5 或更低。  <br/> |
|Win95  <br/> |Windows 95。  <br/> |
|winnt 4。0  <br/> |Windows NT 4.0。  <br/> |
|Mac7  <br/> |Macintosh 系统7。  <br/> |
   
此外, **[Platform.** _平台字符串_**** "部分必须包含**File**或**LinkTo**条目。 **文件**条目列出表单服务器应用程序可执行文件, 表单库在启动该表单时维护并将其加载到磁盘缓存中的新子目录中。 如果改为使用**LinkTo**条目, 则它包含从中提取**文件**信息的不同平台字符串的名称。 如果一个版本的表单支持多个平台, 这将非常有用。 
  
每次使用该**文件**项时, 都会使用**注册表**项, 它标识存储表单服务器应用程序的可执行文件的表单库的注册表项。 前面加反斜杠 (\) 的字符串放置在注册表的根目录中。 不以反斜杠开头的字符串放置在 HKEY_CLASSES_ROOT\CLSID\ _guid_\ 注册表项中, 其中_guid_是表单的**guid** 。 字符 "% d" 可用于指示从中读取表单配置文件的目录的路径名。 这适用于指定具有相对于表单配置文件的路径名的其他文件。 可以使用文件或注册表以前缀后跟任何其他文本的形式指定**多个文件**或**注册表**项。 **[平台**] 的格式。 _平台字符串_**]** 部分为: 
  
- **平台.** _平台字符串_**]**
    
- **CPU** =  _字符串_
    
- **OSVersion** =  _字符串_
    
- **文件** =  _路径_
    
- **LinkTo** =  _字符串_
    
- **注册表** =  _字符串_
  
以下是两个示例 **[Platform.** _平台字符串_**]** 部分, 一种是使用**文件**项, 另一种是使用**LinkTo**项。 
  
```cpp
[Platform.NTx86]
CPU = ix86
OSVersion = WinNT3.5
File = \helpdesk.exe
Registry = Local Server = %d\helpdesk.exe
[Platform.Win95]
CPU = ix86
OSVersion = Win95
LinkTo = NTx86

```

**[Platform.** _平台字符串_**]** 在将表单添加到本地表单库时, 将忽略该部分, 假定安装程序已将邮件类处理程序中的文件 constituting 为在 OLE 注册表中的处理程序部分中命名的可用本地存储, 并已完成系统注册表中的 OLE 注册。 
  

