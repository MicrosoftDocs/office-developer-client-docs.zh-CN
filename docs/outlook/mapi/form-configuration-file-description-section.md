---
title: 表单配置文件 [说明] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4ce91a65-17db-4ee2-ad59-01fd5b1f1ea7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d3673c3b10afb55121339e335163ce9b2e5937e3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774955"
---
# <a name="form-configuration-file-description-section"></a>表单配置文件 [说明] 部分
 
**适用于**： Outlook 
  
**[描述]** 节列出了窗体与窗体的用户界面，以及用于窗体的属性中的控件相关联的所有属性。 **Clsid**， **MessageClass**和**DisplayName**条目，分别标识窗体的邮件类、 其 GUID 和邮件类的显示名称的名称，是用于窗体库中找到的窗体的必填的条目. 剩余的条目是可选的。 **[说明]** 部分的格式为： 
  
**[描述]** 节列出了窗体与窗体的用户界面，以及用于窗体的属性中的控件相关联的所有属性。 **Clsid**， **MessageClass**和**DisplayName**条目，分别标识窗体的邮件类、 其 GUID 和邮件类的显示名称的名称，是用于窗体库中找到的窗体的必填的条目. 剩余的条目是可选的。 **[说明]** 部分的格式为： 
  
 **[描述]MessageClass** =  _字符串_
  
 **Clsid** =  _guid_
  
 **DisplayName** =  _displayedstring_
  
 **SmallIcon** =  _路径_
  
 **视图** =  _路径_
  
是可选的条目：
  
 **类别** =  _显示字符串_
  
 **子类别** =  _显示字符串_
  
 **注释** =  _显示字符串_
  
 **所有者** =  _显示字符串_
  
 **号码** =  _显示字符串_
  
 **版本** =  _整数_
  
 **区域设置** =  _字符串_
  
 **隐藏** =  _整数_
  
 **DesignerToolName** =  _字符串_
  
 **DesignerToolGuid** =  _clsid_
  
 **DesignerRuntimeGuid** =  _clsid_
  
 **ComposeInFolder** =  _0 | 1_
  
 **ComposeCommand** =  _字符串_
  
窗体的安装程序使用**类别**和**子类别**条目设置客户端应用程序的用户界面中的窗体的默认分类。 例如层次结构可以设置"Help Desk"其中是类别和"Software"和"Hardware"已显示子类别。 这种分类然后可查看器应用程序的更多组织方式显示消息。 **注释**、**所有者**和**号码**条目是在客户端应用程序的用户界面中出现的所有注释字符串。 这些是可以自行表单开发人员使用的窗体特定属性。 例如，**注释**项可用于指示用途的窗体、 一起用来指示的人或组织负责维护表单**所有者**条目和用于跟踪不同版本的表单数。 **注释**可以包含项，最多 10 行的注释。 注释的第一行使用 word"注释"键，注释将第二行使用"Comment1"键，等通过"Comment9。" 
  
**视图**和**SmallIcon**条目用于指定用于在客户端应用程序的用户界面中显示图标的图标资源的路径，这通常是用于包括**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 的表格行或**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性列。 可以为相对于窗体配置文件的安装位置的目录的路径名指定图标文件的名称。 **版本**条目用于指示表单的版本号。 **区域设置**是目标表单库的三个字母语言标识符。 _Win32 程序员参考_中找不到这些标识符的列表。
  
**隐藏**条目指示是否应在窗体库提供商的用户界面中显示窗体： 1 表示文件被隐藏，0 表示窗体处于可见。 以下显示窗体配置文件的示例。 
  
**ComposeInFolder**项控制是否表单设计能放置在当前文件夹或用户的收件箱中时用户撰写同时保存邮件： 1 表示表单应转到当前文件夹中，0 指示它应转收件箱中。 
  
**ComposeCommand**条目是要放置在客户端应用程序的字符串的撰写菜单。 如果未指定此参数，将使用的**DisplayName**条目。 
  
```cpp
[Description]
MessageClass = IPM.Help
Clsid = {00020D31-0000-0000-C000-000000000046}
DisplayName = Help Desk Request Form
;optional entries
Category = Help Desk Requests
Subcategory = New Requests
Comment = Use this form to request network assistance
Owner = Help Desk
Number = 1
SmallIcon = C:\WINDOWS|EFORMS\HELPDESK\HDSMALL.ICO
LargeIcon = C:\WINDOWS|EFORMS\HELPDESK\HDLARGE.ICO
Version = 1.00
Locale = enu
Hidden = 0
ComposeInFolder = 0
ComposeCommand = &Help Desk Request
 
```


