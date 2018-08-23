---
title: 实现标准表单谓词
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f89f7c58-6358-4523-9788-676f189b5e69
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 46585859e1dde4ecf38262f99cac5e3a9d29e5db
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568747"
---
# <a name="implementing-standard-form-verbs"></a>实现标准表单谓词

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 定义一组标准谓词或用户选择了菜单或单击按钮时，所有表单查看器应支持时执行的操作。 每个动作具有与之关联的标识，EXCHFORM 中定义的常量。H 头文件。 下表列出的标准窗体谓词和其关联的常量：
  
|**谓词**|**值**|
|:-----|:-----|
|打开  <br/> |EXCHIVERB_OPEN  <br/> |
|答复  <br/> |EXCHIVERB_REPLYTOSENDER  <br/> |
|全部答复  <br/> |EXCHIVERB_REPLYTOALL  <br/> |
|Forward  <br/> |EXCHIVERB_FORWARD  <br/> |
|打印  <br/> |EXCHIVERB_PRINT  <br/> |
|另存为  <br/> |EXCHIVERB_SAVEAS  <br/> |
|答复到文件夹  <br/> |EXCHIVERB_REPLYTOFOLDER  <br/> |
   
当用户选择一个谓词时，传递窗体的[IMAPIForm::DoVerb](imapiform-doverb.md)方法执行其相应的操作将调用其常量。 
  
除了通过您的表单查看器中访问谓词，用户可以有时访问直接从窗体的动作。 例如，某些窗体对象允许用户通过右键单击窗体上并从上下文相关的菜单中选择**打印**调用**打印**动词。 
  

