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
ms.openlocfilehash: e485079de800c63b02d71b3c3ccb90d66101c64b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776261"
---
# <a name="mapi-interfaces"></a>MAPI 接口

  
  
**适用于**： Outlook 
  
每个接口的文档包含介绍性部分，包含后跟一个表，包含以下信息的接口的用途的简要说明。
  
|||
|:-----|:-----|
|头文件：  <br/> |其中定义接口，并且必须包含源代码编译头文件。  <br/> |
|由公开：  <br/> |公开接口的对象。  <br/> |
|通过实现：  <br/> |提供了实现接口的组件列表。  <br/> |
|调用：  <br/> |通常调用接口的方法的组件列表。  <br/> |
|接口标识符：  <br/> |接口标识符 GUID。  <br/> |
|指针类型：  <br/> |公开接口对象的指针类型。  <br/> |
|事务模型：  <br/> |接口派生自[IMAPIProp](imapipropiunknown.md)。 如果 nontransacted，更改将立即生效。如果事务处理，更改执行操作会生效，直到调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md) 。  <br/> |
   
后面的第一个表格是另一个表中列出此接口按 vtable 顺序排列的所有方法。 Vtable 是一个函数指针包含每个方法的 MAPI 对象的一个函数指针编译器所创建的数组。 声明它们的相同顺序列出了的方法。 方法继承自其他接口 Vtable 顺序排列表中未显示，但可使用相同的方式，定义其界面中所述。
  
每个接口主题后接口方法然后记录以字母顺序列出。 针对每种方法，文档中包含的简短用途语句语法块和以下信息。
  
|**标题**|**内容**|
|:-----|:-----|
|参数  <br/> |在方法中的每个参数的说明。  <br/> |
|返回值  <br/> |该方法可返回唯一值的说明。 这些是在其代码应检查呼叫者的值。  <br/> |
|说明  <br/> |为什么以及如何使用该方法的说明。  <br/> |
|请参阅  <br/> |对此引用中的其他主题的交叉引用。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 引用](mapi-reference.md)

