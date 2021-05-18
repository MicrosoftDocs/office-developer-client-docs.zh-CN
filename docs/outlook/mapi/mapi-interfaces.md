---
title: MAPI 接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 34a66cf0-b4e0-4fd5-b937-cd157888961d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4f5d6a5d2dbb48a86363896bf14b61ed28118330
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422661"
---
# <a name="mapi-interfaces"></a>MAPI 接口

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每个接口的文档都包含一个介绍性部分，其中包括接口用途的简要说明，后跟一个包含以下信息的表。
  
|||
|:-----|:-----|
|标头文件：  <br/> |定义接口且编译源代码时必须包含的标头文件。  <br/> |
|公开者：  <br/> |公开接口的对象。  <br/> |
|实现者：  <br/> |提供接口实现的组件列表。  <br/> |
|调用者：  <br/> |通常调用接口方法的组件列表。  <br/> |
|接口标识符：  <br/> |接口标识符 GUID。  <br/> |
|指针类型：  <br/> |公开接口的对象的指针类型。  <br/> |
|事务模型：  <br/> |对于派生自 [IMAPIProp 的接口](imapipropiunknown.md)。 如果未翻译，更改将立即生效;如果已处理，则更改在 [调用 IMAPIProp：：SaveChanges 之前](imapiprop-savechanges.md) 不会生效。  <br/> |
   
第一个表后是另一个以 vtable 顺序列出此接口的所有方法的表。 vtable 是由编译器创建的函数指针的数组，该数组包含 MAPI 对象的每个方法的一个函数指针。 这些方法的列出顺序与声明方法的顺序相同。 从其他接口继承的方法未显示在 Vtable Order 表中，但可以使用与定义这些方法的接口中记录的方法相同的方式使用。
  
在每个接口主题之后，将按字母顺序记录接口的方法。 对于每种方法，该文档都包括一个简短用途语句、一个语法块和以下信息。
  
|**标题**|**Content**|
|:-----|:-----|
|参数  <br/> |方法中每个参数的说明。  <br/> |
|返回值  <br/> |方法可返回的唯一值的说明。 这些是调用方应在代码中检查的值。  <br/> |
|备注  <br/> |有关使用方法的原因和方式的说明。  <br/> |
|另请参阅  <br/> |此参考中其他主题的交叉引用。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 引用](mapi-reference.md)

