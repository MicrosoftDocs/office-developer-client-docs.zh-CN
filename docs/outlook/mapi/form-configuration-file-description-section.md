---
title: 表单配置文件 [说明] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4ce91a65-17db-4ee2-ad59-01fd5b1f1ea7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ddc59d6c503d44a0575679fce694cc34499d8e2a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433092"
---
# <a name="form-configuration-file-description-section"></a>表单配置文件 [说明] 部分
 
**适用于**：Outlook 2013 | Outlook 2016 
  
**[说明]** 部分列出了与窗体的用户界面中的控件关联的窗体的所有属性, 以及用于查找窗体的属性。 " **MessageClass**"、" **Clsid**" 和 " **DisplayName** " 条目分别标识表单的邮件类的名称、其 GUID 和邮件类的显示名称, 这是用于在表单库中查找表单的必需条目。. 其余的项是可选的。 **[Description]** 部分的格式为: 
  
**[说明]** 部分列出了与窗体的用户界面中的控件关联的窗体的所有属性, 以及用于查找窗体的属性。 " **MessageClass**"、" **Clsid**" 和 " **DisplayName** " 条目分别标识表单的邮件类的名称、其 GUID 和邮件类的显示名称, 这是用于在表单库中查找表单的必需条目。. 其余的项是可选的。 **[Description]** 部分的格式为: 
  
 **产品介绍MessageClass** =  _字符串_
  
 **Clsid** =  _guid_
  
 **DisplayName** =  _displayedstring_
  
 **SmallIcon** =  _路径_
  
 **LargeIcon** =  _路径_
  
可选条目为:
  
 **类别** =  _显示字符串_
  
 **子类别** =  _显示字符串_
  
 **注释** =  _显示字符串_
  
 **所有者** =  _显示字符串_
  
 **数字** =  _显示字符串_
  
 **版本** =  _整数_
  
 **区域设置** =  _字符串_
  
 **隐藏** =  _整数_
  
 **DesignerToolName** =  _字符串_
  
 **DesignerToolGuid** =  _clsid_
  
 **DesignerRuntimeGuid** =  _clsid_
  
 **ComposeInFolder** =  _0 | 1_
  
 **ComposeCommand** =  _字符串_
  
"**类别**" 和 "**子**类别" 条目由窗体安装程序用于设置客户端应用程序用户界面中的窗体的默认分类。 例如, 可以设置一个层次结构, 其中 "技术支持" 是类别, "软件" 和 "硬件" 是子类别。 然后, 查看器应用程序可以使用此分类以一种更有条理的方式显示邮件。 **注释**、**所有者**和**编号**条目是在客户端应用程序的用户界面中显示的所有注释字符串。 这些是表单特定的属性, 可由表单开发人员的决定使用。 例如,**注释**条目可用于指示表单的用途、用于指示负责维护表单的人员或组织的**所有者**条目, 以及用于跟踪表单的不同版本的编号。 对于**注释**条目, 最长可包含10行注释。 注释的第一行使用单词 "Comment" 作为键, 第二行注释使用 "Comment1" 作为键, 依此类推, 通过 "Comment9"。 
  
**LargeIcon**和**SmallIcon**项用于指定用于在客户端应用程序的用户界面中显示图标的图标资源的路径, 这通常适用于包含**PR_ICON**的表行 ([PidTagIcon](pidtagicon-canonical-property.md))或**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性列。 可以将图标文件名称指定为相对于安装表单配置文件的目录的路径名。 **版本**条目用于指示表单的版本号。 **区域设置**是目标表单库的三个字母的语言标识符。 可以在_Win32 程序员参考_中找到这些标识符的列表。
  
**隐藏**条目指示表单是否应显示在表单库提供程序的用户界面中: 1 表示文件处于隐藏状态, 0 表示窗体可见。 示例表单配置文件如下所示。 
  
**ComposeInFolder**条目控制在用户保存邮件时是否将窗体放置在当前文件夹或用户的收件箱中: 1 表示该表单应进入当前文件夹, 0 表示应转到 "收件箱"。 
  
**ComposeCommand**条目是要放置在客户端应用程序的撰写菜单中的字符串。 如果未指定此名称, 则使用**DisplayName**条目。 
  
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


