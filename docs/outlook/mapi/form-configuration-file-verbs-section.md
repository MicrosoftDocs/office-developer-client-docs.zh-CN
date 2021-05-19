---
title: Form Configuration File [Verbs] Section
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e7e1f371-9e9a-4bec-a0b3-87753a16f5e0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bb7d49d69fadab54212ff7e8b50ac969e4890c0a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417782"
---
# <a name="form-configuration-file-verbs-section"></a>Form Configuration File [Verbs] Section

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**[Verbs]** 节列出了表单支持的完整动词集。 **[Verbs]** 节的格式为： 
  
 **[谓词]**
  
 **Verb1**  =  _string_
  
下面是 [ **谓词] 部分** 的示例。 
  
```cpp
[Verbs]
Verb1=1
Verb2=2

```

每个动词在单独的 [谓词中 **定义。** _string_ **]** section. 一 **个 [谓词。** _string_ **]** 节描述表单提供的单个动词。 [ **谓词中的 DisplayName** **条目。** _string_ **]** 节指定用户界面中显示的命令名称。 Code **条目** 对应于 [IMAPIForm：:D oVerb 方法中传递](imapiform-doverb.md) 的动词编号。 **[Verb.** _string_ **]** section is： 
  
 **[动词。** _string_ **]**
  
 **DisplayName**  =  _显示的字符串_
  
 **代码**  =  _integer_
  
 **Flags**  =  _integer_
  
 **Attribs**  =  _integer_
  
下面是一个 **[谓词示例。** _string_ **]** section. 
  
```cpp
[Verb.1]
DisplayName=Reply
code=1
Flags=0
Attribs=2
[Verb.2]
DisplayName=Delete
Code=2
Flags=0
Attribs=2

```

本节中列出的谓词由客户端使用 [IMAPIFormInfo：：CalcVerbSet](imapiforminfo-calcverbset.md)方法检索。 通过调用表单的 [IMAPIForm：:D oVerb](imapiform-doverb.md) 方法，并传递给它要执行谓词的代码编号，可激活动词。 
  

