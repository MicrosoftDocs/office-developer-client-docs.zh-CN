---
title: 表单配置文件 [说明] 节
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
# <a name="form-configuration-file-description-section"></a>表单配置文件 [说明] 节
 
**适用于**：Outlook 2013 | Outlook 2016 
  
**[Description]** 节列出与表单用户界面中的控件关联的表单的所有属性，以及用于定位表单的属性。 **MessageClass、Clsid** 和 **DisplayName** 条目（分别标识表单的邮件类名称、其 GUID 和邮件类的 显示名称）是用于在表单库中查找表单的必需条目。  其余条目是可选的。 **[Description] 部分的格式** 为： 
  
**[Description]** 节列出与表单用户界面中的控件关联的表单的所有属性，以及用于定位表单的属性。 **MessageClass、Clsid** 和 **DisplayName** 条目（分别标识表单的邮件类名称、其 GUID 和邮件类的 显示名称）是用于在表单库中查找表单的必需条目。  其余条目是可选的。 **[Description] 部分的格式** 为： 
  
 **[说明] MessageClass**  =  _string_
  
 **Clsid**  =  _guid_
  
 **DisplayName**  =  _displayedstring_
  
 **SmallIcon**  =  _path_
  
 **LargeIcon**  =  _path_
  
可选条目包括：
  
 **类别**  =  _显示的字符串_
  
 **子类别**  =  _显示的字符串_
  
 **注释**  =  _显示的字符串_
  
 **所有者**  =  _显示的字符串_
  
 **Number**  =  _显示的字符串_
  
 **版本**  =  _integer_
  
 **区域设置**  =  _string_
  
 **Hidden**  =  _integer_
  
 **DesignerToolName**  =  _string_
  
 **DesignerToolGuid**  =  _clsid_
  
 **DesignerRuntimeGuid**  =  _clsid_
  
 **ComposeInFolder**  =  _0|1_
  
 **ComposeCommand**  =  _string_
  
表单 **安装程序** 使用 Category 和 **Subcategory** 条目在客户端应用程序的用户界面中设置表单的默认分类。 例如，可以设置层次结构，其中"Help Desk"为类别，"Software"和"Hardware"为子类别。 然后，查看器应用程序可以使用此分类以更加有序的方式显示邮件。 **Comment、Owner** 和 **Number** 条目都是显示在客户端应用程序的用户界面中的注释字符串。  这些属性是表单特定的属性，可自行由表单开发人员使用。 例如 **，"注释** "条目可用于指示表单的用途、用于指示负责维护表单的人或组织的 **"** 所有者"条目，以及用于跟踪不同版本的表单的编号。 对于 **"注释** "条目，最多包含十行注释。 第一行注释使用单词"Comment"作为键，第二行注释使用"Comment1"作为键，以此类代"Comment9"。 
  
**LargeIcon** 和 **SmallIcon** 条目用于指定用于在客户端应用程序的用户界面中显示图标的图标资源的路径，这通常适用于包含 **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 或 **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性列的表行。 图标文件名可指定为相对于安装表单配置文件的目录的路径名。 **"版本**"条目用于指示表单的版本号。 **Locale** 是目标表单库的三个字母的语言标识符。 可以在  _Win32_ 程序员参考中找到这些标识符的列表。
  
" **隐藏** "条目指示是否应该在表单库提供程序的用户界面中显示表单：1 表示文件处于隐藏状态，0 表示表单可见。 下面显示了一个示例表单配置文件。 
  
**ComposeInFolder** 条目控制当用户在撰写邮件时将窗体设计为置于当前文件夹还是用户收件箱中：1 表示该窗体应位于当前文件夹中，0 指示该窗体应位于收件箱中。 
  
**ComposeCommand** 条目是要放在客户端应用程序的撰写菜单中的字符串。 如果未指定，则 **使用 DisplayName** 条目。 
  
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


