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
ms.openlocfilehash: ddc6db2303d9d5f114fdb27b6e15e699a04e73f4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774968"
---
# <a name="form-configuration-file-platforms-section"></a>表单配置文件 [平台] 部分

**适用于**： Outlook 
  
**[平台]** 节列出了由此窗体支持的平台的完整集合。 每个平台项包含前缀**平台。** _字符串_，其中_字符串_是平台的任意字符串代码。 每个字符串对应于单个 **[平台]** 节的**CPU**条目。 每个条目 **[平台]** 节中的定义的引用的后续_平台字符串_ **[平台。** _平台字符串_**]** 部分如下所示。 
  
**[平台]** 节列出了由此窗体支持的平台的完整集合。 每个平台项包含前缀**平台。** _字符串_，其中_字符串_是平台的任意字符串代码。 每个字符串对应于单个 **[平台]** 节的**CPU**条目。 每个条目 **[平台]** 节中的定义的引用的后续_平台字符串_ **[平台。** _平台字符串_**]** 部分如下所示。 
  
**[平台]**
  
**平台**。 _字符串_ =  _平台字符串_
  
以下是 **[平台]** 部分的示例。 
  
```cpp
[Platforms]
Platform.1 = NTx86
Platform.2 = Win95

```

每个 **[平台。** _平台字符串_**]** 部分包含**CPU**和**OSVersion**两个必填的条目。 **CPU**条目指定处理器和**OSVersion**条目指定操作系统。 **CPU**有效值如下表所述。 
  
|**CPU 条目**|**处理器**|
|:-----|:-----|
|Ix86  <br/> |Intel 80 条 x86 和奔腾系列处理器，以及从 AMD、 Cyrix、 NextGen 和其他制造商提供的等效处理器。  <br/> |
|MIPS  <br/> |MIPS R4000 系列处理器。  <br/> |
|AXP  <br/> |数字设备 Corporation Alpha AXP 处理器。  <br/> |
|PPC  <br/> |Motorola 电源 PC 系列处理器。  <br/> |
|M68  <br/> |Mororola 68 x 00 系列处理器。  <br/> |
   
**OSVersion**有效值如下表所述。 
  
|**OSVersion 条目**|**操作系统**|
|:-----|:-----|
|Win3.1  <br/> |Windows 3.1 和 Windows for 工作组 3.11。  <br/> |
|WinNT3.5  <br/> |Windows NT 3.5 或更低。  <br/> |
|Win95  <br/> |Windows 95。  <br/> |
|WinNT4.0  <br/> |Windows NT 4.0。  <br/> |
|Mac7  <br/> |Macintosh 系统 7。  <br/> |
   
此外， **[平台。** _平台字符串_**]** 节必须包含**文件**或**LinkTo**项。 **文件**项列出的窗体服务器应用程序可执行文件的表单库维护和窗体启动时加载到磁盘缓存中的新子目录。 如果改为使用**LinkTo**条目，则它包含的**文件**信息就摘自该不同的平台字符串的名称。 这很有用，如果一个版本的窗体支持多个平台。 
  
每次使用的**文件**项时使用的**注册表**项，它标识存储窗体服务器应用程序的可执行文件的表单库的注册表项。 前加反斜杠 (\) 的字符串被放置注册表的根目录。 字符串反斜杠前面没有处于 HKEY_CLASSES_ROOT\CLSID\ _GUID_\ 注册表项，其中_GUID_是窗体的**GUID** 。 可以使用字符"%d"，以指示从中读取窗体配置文件的目录的路径名。 这是用于指定使用相对于窗体配置文件的路径名其他文件。 可以通过使用作为前缀跟任何其他文本的文件或注册表中指定**多个文件**或**注册表**项。 格式为 **[平台。** _平台字符串_**]** 部分是： 
  
- **[Platform。** _平台字符串_**]**
    
- **CPU** =  _字符串_
    
- **OSVersion** =  _字符串_
    
- **文件** =  _路径_
    
- **LinkTo** =  _字符串_
    
- **注册表** =  _字符串_
  
以下是两个示例 **[平台。** _平台字符串_**]** 各节，一个使用的**文件**项，一个使用**LinkTo**条目。 
  
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

**[平台。** _平台字符串_到本地窗体库中，添加窗体时安装程序已设置为在 OLE 注册表中的处理程序的部分名为可用的本地存储到构成的邮件类处理的文件，并已完成，则假定其值时，将忽略 **]** 节OLE 系统注册表中注册。 
  

