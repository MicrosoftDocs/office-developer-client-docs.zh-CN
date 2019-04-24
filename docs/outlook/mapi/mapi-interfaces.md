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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346681"
---
# <a name="mapi-interfaces"></a>MAPI 接口

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每个接口的文档包含一个介绍性部分, 其中包括接口用途的简短说明以及包含以下信息的表。
  
|||
|:-----|:-----|
|标头文件：  <br/> |在编译源代码时, 定义接口的头文件和必须包含的头文件。  <br/> |
|公开者:  <br/> |公开接口的对象。  <br/> |
|实现者：  <br/> |提供接口实现的组件的列表。  <br/> |
|调用者：  <br/> |通常调用接口方法的组件的列表。  <br/> |
|接口标识符:  <br/> |接口标识符 GUID。  <br/> |
|指针类型:  <br/> |公开接口的对象的指针类型。  <br/> |
|事务模型:  <br/> |对于从[IMAPIProp](imapipropiunknown.md)派生的接口。 如果 nontransacted, 更改会立即生效;如果进行了事务处理, 则在[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)调用之前, 更改不会生效。  <br/> |
   
遵循第一个表是另一个表, 它按 vtable 顺序列出此接口的所有方法。 vtable 是由编译器创建的一系列函数指针, 其中包含每个 MAPI 对象方法的函数指针。 这些方法按照声明它们的顺序列出。 从其他接口继承的方法不会显示在 Vtable 顺序表中, 但可以按照在定义它们的接口中记录的相同方式使用。
  
在每个接口主题之后, 将按字母顺序对接口的方法进行记录。 对于每个方法, 文档都包含一个简短的目的语句、一个语法块和以下信息。
  
|**标题**|**Content**|
|:-----|:-----|
|参数  <br/> |方法中的每个参数的说明。  <br/> |
|返回值  <br/> |该方法可以返回的唯一值的说明。 这些是调用方在其代码中应检查的值。  <br/> |
|注解  <br/> |描述使用方法的原因和方式。  <br/> |
|另请参阅  <br/> |本参考中对其他主题的交叉引用。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 引用](mapi-reference.md)

