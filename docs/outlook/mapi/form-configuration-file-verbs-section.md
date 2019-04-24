---
title: 表单配置文件 [谓词] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e7e1f371-9e9a-4bec-a0b3-87753a16f5e0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bb7d49d69fadab54212ff7e8b50ac969e4890c0a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327494"
---
# <a name="form-configuration-file-verbs-section"></a>表单配置文件 [谓词] 部分

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**[谓词]** 部分列出了窗体支持的完整谓词集。 **[谓词]** 部分的格式为: 
  
 **谓词**
  
 **Verb1** =  _字符串_
  
以下是 **[谓词]** 部分的一个示例。 
  
```cpp
[Verbs]
Verb1=1
Verb2=2

```

每个谓词都在一个单独的 **[谓词**中定义。 _string_**]** 部分。 A **[谓词。** _string_**]** 部分介绍由窗体提供的单个谓词。 **[谓词**] 中的**DisplayName**项。 _string_**]** 部分指定在用户界面中显示的命令名称。 **代码**条目对应于[IMAPIForm::D overb](imapiform-doverb.md)方法中传递的动词编号。 **[谓词**] 的语法。 _string_**]** 部分为: 
  
 **动词.** _string_**]**
  
 **DisplayName** =  _显示字符串_
  
 **代码** =  _integer_
  
 **Flags** =  _integer_
  
 **Attribs** =  _整数_
  
下面是一个 **[谓词**的示例。 _string_**]** 部分。 
  
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

客户端使用[IMAPIFormInfo:: CalcVerbSet 方法](imapiforminfo-calcverbset.md)检索本节中列出的谓词。 通过调用窗体的[IMAPIForm::D overb](imapiform-doverb.md)方法并向其传递要执行的谓词的代码编号来激活谓词。 
  

