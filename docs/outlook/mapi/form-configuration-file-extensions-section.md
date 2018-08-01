---
title: 表单配置文件 [扩展名] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4817e446-982d-491c-abcf-cc888a771afa
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7c26b86ad4d6c7fd565abddbfc76f50ac3dccaf8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774949"
---
# <a name="form-configuration-file-extensions-section"></a>表单配置文件 [扩展名] 部分

  
  
**适用于**： Outlook 
  
**[扩展]** 节列出了窗体，通常命名的属性集的扩展的属性，它们是超出基本窗体配置文件的 **[描述]** 节中列出的任何属性。 扩展的属性是使用较高的位属性标记中设置**GetProps** **IMAPIFormInfo**对象的方法的调用返回的属性。 如果有，通过检索这些标记，客户端应用程序可以确定窗体的扩展的属性。 这样，客户端调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法，传递中窗体的属性的名称，并调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法以获取属性。 
  
 **[扩展]**
  
 **扩展。** _string1_ =  _string2_
  
每个扩展名属性部分定义一个使用 MAPI 命名属性的语法的扩展特性。 属性类型必须是 PT_LONG 或 PT_STRING8。 不支持包含名为的字符串的属性集。 **[扩展]** 节的格式为： 
  
 **[扩展名。** _string2_**]**
  
 **类型** =  _整数_
  
 **NmidPropset** =  _guid_
  
 **NmidInteger** =  _整数_
  
 **值** =  _字符串_ |  _整数_
  
**[扩展]** 一节和后续相关的部分的示例所示关注。 
  
```
[Extensions]
Extension.A = 1
[Extension.1]
Type = 30
NmidPropset = {00020D0C-0000-0000-C000-000000000046}
NmidInteger = 1
Value = 11220000

```


