---
title: 实现标准窗体谓词
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f89f7c58-6358-4523-9788-676f189b5e69
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6360b86dc23a5404b818f76cb1c2cd10747ef3cb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426119"
---
# <a name="implementing-standard-form-verbs"></a>实现标准窗体谓词

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 定义了一组标准谓词, 或在用户做出菜单选择或单击按钮 (所有表单查看器都应支持) 时执行的操作。 每个动词都有一个与之相关联的常量, 用于标识, 在 EXCHFORM 中定义。H 头文件。 下表列出了标准窗体谓词及其关联的常量:
  
|**Verb**|**值**|
|:-----|:-----|
|打开  <br/> |EXCHIVERB_OPEN  <br/> |
|回复  <br/> |EXCHIVERB_REPLYTOSENDER  <br/> |
|全部答复  <br/> |EXCHIVERB_REPLYTOALL  <br/> |
|前后  <br/> |EXCHIVERB_FORWARD  <br/> |
|Print  <br/> |EXCHIVERB_PRINT  <br/> |
|另存为  <br/> |EXCHIVERB_SAVEAS  <br/> |
|答复到文件夹  <br/> |EXCHIVERB_REPLYTOFOLDER  <br/> |
   
当用户选择某个谓词时, 在对该窗体的 IMAPIForm 的调用中传递其常量[::D overb](imapiform-doverb.md)方法执行其对应的操作。 
  
除了通过表单查看器访问谓词之外, 用户有时还可以直接从窗体访问谓词。 例如, 某些表单对象允许用户通过右键单击表单并从上下文相关的菜单中选择 "**打印**" 来调用**打印**谓词。 
  

