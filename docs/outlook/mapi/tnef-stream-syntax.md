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
  
本主题提供了 Bakus-Nauer, 如 TNEF 流语法的说明。 在此说明中, 具有进一步定义的 nonterminal 元素以斜体表示。 常量和文本项以粗体显示。 一条线上按顺序列出元素的顺序。 例如, _Stream_项包含常量**TNEF_SIGNATURE**, 后跟一个_键_, 再加上一个_对象_。 如果某一项具有多个可能的实现, 则可选项在连续行中列出。 例如, 一个_对象_可以由_Message_Seq_、 _Message_Seq_后接一个_Attach_Seq_或一个_Attach_Seq_组成。
  
 _TNEF_Stream:_
  
> **TNEF_SIGNATURE**_键__对象_
    
 _主键_
  
> 非零16位无符号整数
    
启用 tnef 的传输在使用 tnef 实现生成 TNEF 流之前生成此值。
  
 _对象_
  
>  _Message_Seq Message_Seq Attach_Seq Attach_Seq_
    
 _Message_Seq:_
  
>  _attTnefVersion attTnefVersion Msg_Attribute_Seq attTnefVersion attMessageClass attTnefVersion attMessageClass Msg_Attribute_Seq attMessageClass attMessageClass Msg_Attribute_Seq Msg_Attribute_Seq_
    
 _attTnefVersion:_
  
> **LVL_MESSAGE attTnefVersion sizeof (ULONG)****0x00010000**校验和 
    
 _attMessageClass:_
  
> **LVL_MESSAGE attMessageClass**_msg_class_length msg_class_校验和 
    
 _Msg_Attribute_Seq:_
  
>  _Msg_Attribute Msg_Attribute Msg_Attribute_Seq_
    
 _Msg_Attribute:_
  
> **LVL_MESSAGE**属性 ID 属性-长度属性-数据校验和 
    
属性 ID 是 TNEF 属性标识符之一, 例如**attSubject**。 属性-长度是属性数据的长度 (以字节为单位)。 属性 data 是与属性相关联的数据。
  
 _Attach_Seq:_
  
>  _attRenddata attRenddata Att_Attribute_Seq_
    
 _attRenddata:_
  
> **LVL_ATTACHMENT attRenddata****sizeof (RENDDATA)** RENDDATA 校验和 
    
Renddata 是与**Renddata**结构关联的数据, 其中包含相应附件的呈现信息。 **RENDDATA**结构是在 TNEF 中定义的。H 头文件。 
  
 _Att_Attribute_Seq:_
  
>  _Att_Attribute Att_Attribute Att_Attribute_Seq_
    
 _Att_Attribute:_
  
> **LVL_ATTACHMENT**属性 ID 属性-长度属性-数据校验和 
    
属性 ID、属性长度和属性数据与 Msg_Attribute 项具有相同的含义。
  

