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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410453"
---
# <a name="attmapiprops"></a>attMAPIProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**attMAPIProps** 属性很特殊，可用于对现有的 TNEF 定义属性集内没有对应属性的任何 MAPI 属性进行编码。 属性数据是一组端到端布置的 MAPI 属性。 此编码的格式允许任意一组 MAPI 属性，如下所示：  
  
 _Property_Seq：_
  
> 属性计数  _Property_Value,..._
    
必须存在与属性  _Property_Value_ 值指示的项数一样多。 
  
 _Property_Value：_
  
> property-tag _Property_property-tag  _Proptag_Name Property_
    
property-tag 只是与属性标识符关联的值，例如 0x0037001F **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 。
  
 _属性：_
  
>  _值_ 值计数  _值,..._
    
 _值：_
  
> value-data value-size value-data padding value-size value-IID value-data padding
    
 _Proptag_Name：_
  
> name-guid name-kind name-id name-guid name-kind name-string-length name-string padding
    
每个属性的封装因属性标识符和属性类型而异。 属性标记、标识符和类型在 Mapitags.h 和 Mapidefs.h 头文件中定义。
  
如果该属性是命名属性，则属性标记后紧跟 MAPI 属性名称，由全局唯一标识符 (GUID) 、类型以及标识符或 Unicode 字符串组成。
  
使用可变长度值（如 PT_BINARY、PT_STRING8、PT_UNICODE 或 PT_OBJECT 属性类型）的多值属性和属性将按以下方式处理。 首先，编码为 32 位无符号长的值数放置在 TNEF 流中，后跟各个值。 每个属性的值数据都编码为大小（以字节为单位）后跟值数据本身。 尽管值大小中不包含填充量，但值数据将填充到 4 字节边界。
  
如果属性的类型为 PT_OBJECT，则值大小后跟对象的接口标识符。 TNEF 的当前实现仅支持IID_IMessage、IID_IStorage和IID_Istream标识符。 接口标识符的大小包含在值大小中。
  
如果对象是嵌入 (，即其属性类型为 PT_OBJECT 且接口标识符为 IID_Imessage) ，则值数据将编码为嵌入的 TNEF 流。 在 TNEF 实现中，嵌入邮件的实际编码通过为原始流打开第二个 TNEF 对象并内联处理流完成。
  

