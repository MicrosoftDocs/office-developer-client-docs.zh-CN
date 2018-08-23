---
title: 表单配置文件 [谓词] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e7e1f371-9e9a-4bec-a0b3-87753a16f5e0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6a06283e3eb072e1f502d0b1bd303ce9f0733578
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583972"
---
# <a name="form-configuration-file-verbs-section"></a>表单配置文件 [谓词] 部分

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
**[谓词]** 节列出了支持表单谓词的完整集合。 **[谓词]** 节的格式为： 
  
 **[谓词]**
  
 **Verb1** =  _字符串_
  
以下是 **[谓词]** 部分的示例。 
  
```cpp
[Verbs]
Verb1=1
Verb2=2

```

每个动作定义在单独 **[动词。** _字符串_**]** 部分。 A **[动词。** _字符串_**]** 部分介绍单个动词形式提供。 中的**DisplayName**条目 **[动词。** _字符串_**]** 节指定在用户界面中显示的命令名称。 [IMAPIForm::DoVerb](imapiform-doverb.md)方法中传递的动词编号相对应的**代码**条目。 语法为 **[动词。** _字符串_**]** 部分是： 
  
 **[动词。** _字符串_**]**
  
 **DisplayName** =  _显示字符串_
  
 **代码** =  _整数_
  
 **Flags** =  _整数_
  
 **Attribs** =  _整数_
  
下面是示例 **[动词。** _字符串_**]** 部分。 
  
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

本节中列出的动作将检索客户端使用[IMAPIFormInfo::CalcVerbSet 方法](imapiforminfo-calcverbset.md)。 通过调用窗体的[IMAPIForm::DoVerb](imapiform-doverb.md)方法并将其传递要执行的动作代码号激活动词。 
  

