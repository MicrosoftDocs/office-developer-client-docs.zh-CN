---
title: attMAPIProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 806270c1-30e4-494e-9b03-7d1f2fc04099
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 185bfbb151c4f8d4e36b40b94393d14d50c33edf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318121"
---
# <a name="attmapiprops"></a>attMAPIProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**attMAPIProps**属性是特别的, 因为它可用于对在现有 TNEF 定义的属性集中没有对应属性的任何 MAPI 属性进行编码。 属性数据是按端到端排列的一组已计数的 MAPI 属性。 此编码的格式 (允许任何 MAPI 属性集) 如下所示:  
  
 _Property_Seq:_
  
> 属性计数_Property_Value,..._
    
必须有与属性-count 值指示的_Property_Value_项目数。 
  
 _Property_Value:_
  
> 属性标记 _Property_property-tag _Proptag_Name 属性_
    
属性标记只是与属性标识符关联的值, 如 0x0037001F for **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md))。
  
 _财产_
  
>  _值_值-计数_值,..._
    
 _值：_
  
> 值-数据值大小值-数据填充值-IID 值-数据填充
    
 _Proptag_Name:_
  
> name-guid 名称-种类名称-id name-guid 名称-种类名称-字符串长度名称-字符串填充
    
每个属性的封装根据属性标识符和属性类型的不同而有所不同。 属性标记、标识符和类型是在 Mapitags 和 mapidefs.h 头文件中定义的。
  
如果属性为命名的属性, 则该属性标记后紧跟 MAPI 属性名称, 由全局唯一标识符 (GUID)、类型以及标识符或 Unicode 字符串组成。
  
多值属性和具有可变长度值的属性 (如 PT_BINARY、PT_STRING8、PT_UNICODE 或 PT_OBJECT 属性类型) 按以下方式处理。 首先, 将编码为32位无符号长的值的数目放在 TNEF 流中, 后跟各个值。 每个属性的值数据都以字节为单位的大小, 后跟值数据本身。 将值数据填充到4字节边界, 尽管填充量不包含在 value-size 中。
  
如果属性的类型为 PT_OBJECT, 则值大小后跟对象的接口标识符。 当前的 TNEF 实现仅支持 IID_IMessage、IID_IStorage 和 IID_Istream 接口标识符。 接口标识符的大小包含在值大小中。
  
如果对象是嵌入的邮件 (即, 它的属性类型为 PT_OBJECT, 接口标识符为 IID_Imessage), 则将值数据编码为嵌入的 TNEF 流。 通过打开原始流的第二个 TNEF 对象并以内嵌方式处理流, 可以完成 TNEF 实现中嵌入邮件的实际编码。
  

