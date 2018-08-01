---
title: TNEF 流语法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1353d494-c266-4715-afe7-14543a1bbe1b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cbaf37415608dd1d79a06be65b34632f2b4afc89
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779002"
---
# <a name="tnef-stream-syntax"></a>TNEF 流语法

  
  
**适用于**： Outlook 
  
本主题提供类似的 TNEF 流语法说明 Bakus-诺尔。 在此说明，有进一步定义的终结元素是斜体。 常量和文字项目是以粗体显示。 在同一行顺序列出了序列的元素。 例如，_流_项包含常量**TNEF_SIGNATURE**后, 跟一个_键_后, 跟一个_对象_。 当项目具有多个可能的实现时，列出连续线上。 例如， _Message_Seq_后, 跟_Attach_Seq_或只_Attach_Seq_ _Message_Seq_可以包括一个_对象_。
  
 _TNEF_Stream:_
  
> **TNEF_SIGNATURE**_键__对象_
    
 _键：_
  
> 非零值的 16 位无符号的整数
    
TNEF 启用传输使用 TNEF 实现生成 TNEF 流之前生成此值。
  
 _对象：_
  
>  _Message_Seq Message_Seq Attach_Seq Attach_Seq_
    
 _Message_Seq:_
  
>  _attTnefVersion attTnefVersion Msg_Attribute_Seq attTnefVersion attMessageClass attTnefVersion attMessageClass Msg_Attribute_Seq attMessageClass attMessageClass Msg_Attribute_Seq Msg_Attribute_Seq_
    
 _attTnefVersion:_
  
> **LVL_MESSAGE attTnefVersion sizeof(ULONG)****0x00010000**校验和 
    
 _attMessageClass:_
  
> **LVL_MESSAGE attMessageClass**_msg_class_length msg_class_校验和 
    
 _Msg_Attribute_Seq:_
  
>  _Msg_Attribute Msg_Attribute Msg_Attribute_Seq_
    
 _Msg_Attribute:_
  
> **LVL_MESSAGE**属性 ID 属性长度属性数据校验和 
    
属性 ID 是 TNEF 属性标识符，如**attSubject**之一。 属性长度是以字节为单位的属性数据的长度。 属性数据是与属性关联的数据。
  
 _Attach_Seq:_
  
>  _attRenddata attRenddata Att_Attribute_Seq_
    
 _attRenddata:_
  
> **LVL_ATTACHMENT attRenddata****sizeof(RENDDATA)** renddata 校验和 
    
Renddata 是**RENDDATA**结构，其中包含相应的附件的呈现信息相关联的数据。 **RENDDATA**结构 TNEF 中定义。H 头文件。 
  
 _Att_Attribute_Seq:_
  
>  _Att_Attribute Att_Attribute Att_Attribute_Seq_
    
 _Att_Attribute:_
  
> **LVL_ATTACHMENT**属性 ID 属性长度属性数据校验和 
    
属性 ID、 长度、 属性和属性数据，其含义相同 Msg_Attribute 项目。
  

