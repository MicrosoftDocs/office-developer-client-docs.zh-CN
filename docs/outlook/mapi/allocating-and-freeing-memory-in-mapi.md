---
title: 分配和释放 MAPI 中的内存
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e238f6bc-e9f6-4ea4-a2e4-ff5da2a04bd5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dc97abcb4b316b696032f2788f4e653717e1396b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774533"
---
# <a name="allocating-and-freeing-memory-in-mapi"></a>分配和释放 MAPI 中的内存

  
  
**适用于**： Outlook 
  
除了指定如何分配和释放内存，MAPI 定义了解时应释放调用的公共接口方法和 API 函数之间传递内存模型。 模型仅适用于参数不是到接口，如字符串和结构的指针的指针分配内存。 接口指针使用引用计数通过**IUnknown**实现的机制。 分配和释放非 MAPI 相关的内部在客户端应用程序或服务提供商的内存时, 使用任何机制有意义。 
  
模型定义参数为三种类型之一。 可以输入参数，将呼叫者与信息用于通过调用的函数或方法，将设置输出参数、 通过调用的函数或方法设置和返回给调用方或输入输出参数，两种类型的组合。 输出参数通常是指向数据或指向数据的指针的指针。 尽管调用的函数，负责为输出参数分配数据，呼叫者的指针分配的内存。 
  
下表介绍分配和释放内存为这些类型的参数的规则。
  
|**类型**|**内存分配**|**内存发行版**|
|:-----|:-----|:-----|
|输入  <br/> |呼叫者负责，并且可以使用任何机制。  <br/> |呼叫者负责，并且可以使用任何机制。  <br/> |
|输出  <br/> |调用的函数负责，且必须使用**MAPIAllocateBuffer**。 有关详细信息，请参阅[MAPIAllocateBuffer](mapiallocatebuffer.md)。  <br/> |呼叫者负责，且必须使用**MAPIFreeBuffer**。 有关详细信息，请参阅[MAPIFreeBuffer](mapifreebuffer.md)。  <br/> |
|输入输出  <br/> |呼叫者负责的初始分配和调用的函数可以重新分配必要使用**MAPIAllocateBuffer**。  <br/> |必要时重新分配的初始释放调用的函数。 呼叫者必须释放的最终的返回值。  <br/> |
   
在故障情形接口方法的实施者需要特别注意输出和输入输出参数，因为呼叫者通常无法清除它们。 如果将返回错误，然后每个输出或输入输出参数必须也将保留在初始化呼叫者或设置一个值，而无需任何操作需要呼叫者可以清理为的值。 例如，输出指针-参数的`void ** ppv`它已输入，也可以是设置为 NULL，则必须将保留 ( `*ppv = NULL`)。
  

