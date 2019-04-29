---
title: 表单配置文件 [extension] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4817e446-982d-491c-abcf-cc888a771afa
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 96682dd2bdfedc42ea13c6985cb834f0adffd4df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423753"
---
# <a name="form-configuration-file-extensions-section"></a>表单配置文件 [extension] 部分

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**[extension]** 部分列出了窗体的扩展属性 (通常是一个命名属性集), 它是表单配置文件的 **[Description]** 部分中列出的基本属性以外的任何属性。 扩展属性是通过调用**IMAPIFormInfo**对象的**GetProps**方法返回的属性, 该属性标记中设置了高位。 客户端应用程序可以通过检索这些标记来确定表单的扩展属性 (如果有)。 为此, 客户端调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法, 传入窗体属性的名称并调用[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以获取属性。 
  
 **长度**
  
 **扩展.** _string1_ =  _string2_
  
每个扩展属性部分使用 MAPI 命名属性语法定义一个扩展属性。 属性类型必须是 PT_LONG 或 PT_STRING8。 不支持包含命名字符串的属性集。 **[Extension]** 部分的格式为: 
  
 **扩展.** _string2_**]**
  
 **类型** =  _integer_
  
 **NmidPropset** =  _guid_
  
 **NmidInteger** =  _整数_
  
 **值** =  __ 字符串 |  _integer_
  
下面显示了一个 **[extension]** 部分和一个随后相关的部分的示例。 
  
```
[Extensions]
Extension.A = 1
[Extension.1]
Type = 30
NmidPropset = {00020D0C-0000-0000-C000-000000000046}
NmidInteger = 1
Value = 11220000

```


