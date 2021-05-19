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
  
MAPI 定义一组所有表单查看者都应支持的标准动词或当用户选择菜单或单击按钮时采取的操作。 每个动词都有一个与之关联的常量，用于标识，该常量在 EXCHFORM 中定义。H 头文件。 下表列出了标准窗体动词及其关联的常量：
  
|**Verb**|**值**|
|:-----|:-----|
|打开  <br/> |EXCHIVERB_OPEN  <br/> |
|答复  <br/> |EXCHIVERB_REPLYTOSENDER  <br/> |
|全部答复  <br/> |EXCHIVERB_REPLYTOALL  <br/> |
|转发  <br/> |EXCHIVERB_FORWARD  <br/> |
|打印  <br/> |EXCHIVERB_PRINT  <br/> |
|另存为  <br/> |EXCHIVERB_SAVEAS  <br/> |
|答复到文件夹  <br/> |EXCHIVERB_REPLYTOFOLDER  <br/> |
   
当用户选择一个动词时，在调用表单 [的 IMAPIForm：:D oVerb](imapiform-doverb.md) 方法中传递其常量以执行其相应的操作。 
  
除了通过表单查看器访问动词之外，用户有时还可以直接从窗体访问动词。 例如，某些表单对象允许用户通过右键单击表单，然后从上下文相关菜单中选择"打印"来调用 **Print** 动词。 
  

