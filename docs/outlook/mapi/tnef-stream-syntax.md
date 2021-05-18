---
title: TNEF 流语法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1353d494-c266-4715-afe7-14543a1bbe1b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 12d2a92ff80897456707c7ab8af8f704605c85d0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423025"
---
# <a name="tnef-stream-syntax"></a>TNEF 流语法

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题提供了一个Bakus-Nauer TNEF 流语法的说明。 在此说明中，具有进一步定义的非终止元素以斜体显示。 常量和文字项以粗体显示。 元素序列在单行上按顺序排列。 例如  _，Stream_ 项由常量 **TNEF_SIGNATURE，后** 跟  _Key，_ 后跟  _Object_。 当一个项目具有多个可能的实现时，替代项将列在连续行上。 例如 _，Object_ 可以包含一个 Message_Seq、Message_Seq后跟一Attach_Seq或 _只包含一_ Attach_Seq 。  
  
 _TNEF_Stream：_
  
> **TNEF_SIGNATURE** _Key_ _对象_
    
 _键：_
  
> 非零 16 位无符号整数
    
启用 TNEF 的传输在使用 TNEF 实现生成 TNEF 流之前生成此值。
  
 _对象：_
  
>  _Message_Seq Message_Seq Attach_Seq Attach_Seq_
    
 _Message_Seq：_
  
>  _attTnefVersion attTnefVersion Msg_Attribute_Seq attTnefVersion attMessageClass attTnefVersion attMessageClass Msg_Attribute_Seq attMessageClass attMessageClass Msg_Attribute_Seq Msg_Attribute_Seq_
    
 _attTnefVersion：_
  
> **LVL_MESSAGE ULONG (的 attTnefVersion) 0x00010000** 校验和 
    
 _attMessageClass：_
  
> **LVL_MESSAGE attMessageClass** _msg_class_length msg_class_ 校验和 
    
 _Msg_Attribute_Seq：_
  
>  _Msg_Attribute Msg_Attribute Msg_Attribute_Seq_
    
 _Msg_Attribute：_
  
> **LVL_MESSAGE** attribute-ID attribute-length 属性-数据校验和 
    
Attribute-ID 是 TNEF 属性标识符之一，例如 **attSubject**。 Attribute-length 是属性数据的长度（以字节为单位）。 Attribute-data 是与属性关联的数据。
  
 _Attach_Seq：_
  
>  _attRenddata attRenddata Att_Attribute_Seq_
    
 _attRenddata：_
  
> LVL_ATTACHMENT **RENDDATA 和 renddata 校验和** (**attRenddata**) 大小 
    
Renddata 是与 **RENDDATA** 结构关联的数据，其中包含相应附件的呈现信息。 **RENDDATA** 结构在 TNEF 中定义。H 头文件。 
  
 _Att_Attribute_Seq：_
  
>  _Att_Attribute Att_Attribute Att_Attribute_Seq_
    
 _Att_Attribute：_
  
> **LVL_ATTACHMENT** attribute-ID attribute-length 属性-数据校验和 
    
Attribute-ID、attribute-length 和 attribute-data 的含义与项目Msg_Attribute相同。
  

