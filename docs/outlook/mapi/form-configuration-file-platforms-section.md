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
  
**[平台]** 部分列出了此表单支持的完整平台集。 每个平台条目由前缀 **Platform 组成。** _string_，其中  _string_ 是平台的任意字符串代码。 每个字符串对应于单个 [**平台]** 节的 **CPU** 条目。 **[Platforms] 节中** 的每个条目都定义一个 _引用_ 后续 **[Platform] 的平台字符串。** _platform string_ **]** 部分，如下所示。 
  
**[平台]** 部分列出了此表单支持的完整平台集。 每个平台条目由前缀 **Platform 组成。** _string_，其中  _string_ 是平台的任意字符串代码。 每个字符串对应于单个 [**平台]** 节的 **CPU** 条目。 **[Platforms] 节中** 的每个条目都定义一个 _引用_ 后续 **[Platform] 的平台字符串。** _platform string_ **]** 部分，如下所示。 
  
**[平台]**
  
**平台**。 _string_  =  _平台字符串_
  
下面是 **[Platforms] 部分** 的示例。 
  
```cpp
[Platforms]
Platform.1 = NTx86
Platform.2 = Win95

```

每个 **[平台。** _platform string_ **]** section contains the two required entries， **CPU** and **OSVersion**. **CPU** 条目指定处理器，**而 OSVersion** 条目指定操作系统。 下表介绍了有效的 **CPU** 值。 
  
|**CPU 条目**|**处理器**|
|:-----|:-----|
|Ix86  <br/> |Intel 80x86 和 Pentium 系列处理器，以及 AMD、Cyrix、NextGen 和其他制造商的等效处理器。  <br/> |
|MIPS  <br/> |MIPS R4000 系列处理器。  <br/> |
|AXP  <br/> |数字设备公司 Alpha AXP 处理器。  <br/> |
|PPC  <br/> |Motorola Power PC 系列处理器。  <br/> |
|M68  <br/> |Mororola 68x00 系列处理器。  <br/> |
   
下表介绍了有效的 **OSVersion** 值。 
  
|**OSVersion 条目**|**操作系统**|
|:-----|:-----|
|Win3.1  <br/> |Windows工作组 3.11 Windows 3.1 和 3.11。  <br/> |
|WinNT3.5  <br/> |Windows NT 3.5 或更低。  <br/> |
|Win95  <br/> |Windows 95.  <br/> |
|WinNT4.0  <br/> |Windows NT 4.0 版。  <br/> |
|Mac7  <br/> |Macintosh 系统 7。  <br/> |
   
此外 **，[Platform.** _platform string_ **]** section must contain either a **File** or **LinkTo** entry. " **文件** "条目列出了表单库维护的表单服务器应用程序可执行文件，并加载在启动表单时磁盘缓存中的新子目录中。 如果 **改为使用 LinkTo** 条目，则它包含从其中获取文件信息的不同 **平台字符串** 的名称。 如果表单的一个版本支持多个平台，这将非常有用。 
  
每当 **使用**"文件"项时，都会使用注册表项，它标识存储表单服务器应用程序的可执行文件的表单库的注册表项。 前面带有反 ( \ ) 的字符串位于注册表的根目录下。 前面没有反杠的字符串放置在 guiD \ 注册表HKEY_CLASSES_ROOT\CLSID\ _GUID_\注册表项中，其中 _GUID_ 是表单 **的 GUID。** 字符"%d"可用于指示已读取表单配置文件的目录的路径名。 这可用于指定具有相对于表单配置文件的路径名的其他文件。 **可以使用 File** **或 Registry** 作为前缀，后跟任何其他文本来指定多个 File 或 Registry 项。 **[Platform.** _platform string_ **]** section is： 
  
- **[平台。** _platform string_ **]**
    
- **CPU**  =  _string_
    
- **OSVersion**  =  _string_
    
- **文件**  =  _path_
    
- **LinkTo**  =  _string_
    
- **注册表**  =  _string_
  
下面是两个示例 **[Platform。** _platform string_ **]** sections， one using the **File** entry and one using the **LinkTo** entry. 
  
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

**[Platform.** _当_ 将表单添加到本地表单库时，如果假定安装程序将包含邮件类处理程序的文件放置到 OLE 注册表中处理程序部分命名的可用本地存储中，并且已完成系统注册表中的 OLE 注册，则忽略 platform string **]** 节。 
  

