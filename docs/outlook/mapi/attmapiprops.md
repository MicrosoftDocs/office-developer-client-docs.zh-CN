---
title: attMAPIProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 806270c1-30e4-494e-9b03-7d1f2fc04099
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: eef480e8b024565ab282fb242a36336cd17384a1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774575"
---
# <a name="attmapiprops"></a>attMAPIProps

  
  
**适用于**： Outlook 
  
**AttMAPIProps**属性是特殊的这是的它可以用于对集合中的现有 TNEF 定义的属性没有对应的任何 MAPI 属性进行编码。 属性数据是一组计数排列的端到端的 MAPI 属性。 允许任何 MAPI 属性集合，其中的此编码，格式如下所示：  
  
 _Property_Seq:_
  
> 属性计数_Property_Value，..._
    
必须尽可能多的_Property_Value_项目，如属性数值指示。 
  
 _Property_Value:_
  
> 属性标记 _Property_property tag _Proptag_Name 属性_
    
属性标记就是属性标识符，如 0x0037001F **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 的相关联的值。
  
 _属性：_
  
>  _值_值计数_的值，..._
    
 _值：_
  
> 数值数据值大小值的数据填充值大小值 IID 数值数据填充
    
 _Proptag_Name:_
  
> 名称 guid 名称类型名称 id 名称-guid 名称类型名称字符串长度名称字符串填充
    
每个属性封装异属性标识符和属性类型。 Mapitags.h 和 Mapidefs.h 头文件中定义属性标记、 标识符和类型。
  
如果该属性是命名的属性，然后属性标记紧跟组成的全局唯一标识符 (GUID)、 类型和标识符或 Unicode 字符串的 MAPI 属性名称。
  
多值的属性和具有可变长度值属性，如 PT_BINARY、 PT_STRING8、 PT_UNICODE 或 PT_OBJECT 属性类型，按以下方式处理。 首先数量的值，编码为 32 位无符号长，位于在 TNEF 流中后, 跟的单个值。 每个属性值的数据被编码为以字节为单位的值数据本身后跟尺寸。 数值数据被填充为 4 字节，尽管的填充量不包含值大小。
  
如果该属性的类型 PT_OBJECT，值大小后跟对象的界面标识符。 TNEF 的当前实现仅支持 IID_IMessage、 IID_IStorage 和 IID_Istream 界面标识符。 包含值大小接口标识符的大小。
  
如果对象是嵌入的邮件 （即，它具有 PT_OBJECT 和 IID_Imessage 接口标识符的属性类型，） 的值数据编码为嵌入的 TNEF 流。 邮件嵌入 TNEF 实现中的实际编码是通过打开的原始流的第二个 TNEF 对象和处理流内嵌。
  

