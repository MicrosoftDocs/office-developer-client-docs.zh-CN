---
title: 在 MAPI 中分配和释放内存
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e238f6bc-e9f6-4ea4-a2e4-ff5da2a04bd5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 68250c5cbeaa366ed4555bb469c4e68d62302f28
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419665"
---
# <a name="allocating-and-freeing-memory-in-mapi"></a>在 MAPI 中分配和释放内存

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
除了指定如何分配和释放内存，MAPI 还定义了一个模型，用于了解何时应释放在公共接口方法和 API 函数调用之间传递的内存。 模型仅适用于分配给不是指向接口的指针的参数（如字符串和指向结构的指针）的内存。 接口指针使用通过 **IUnknown** 实现的引用计数机制。 在客户端应用程序或服务提供商内部分配和释放非 MAPI 相关内存时，请使用任何有意义的机制。 
  
模型将参数定义为三种类型之一。 它们可以是输入参数，由调用方设置，以及由被调用的函数或方法使用的信息、输出参数、由调用的函数或方法设置并返回到调用方或输入输出参数（两种类型的组合）。 输出参数通常是指向数据的指针或指向指向数据的指针。 尽管调用的函数负责为输出参数分配数据，但是调用方会为指针分配内存。 
  
下表介绍了为这些类型的参数分配和释放内存的规则。
  
|**类型**|**内存分配**|**内存释放**|
|:-----|:-----|:-----|
|Input  <br/> |呼叫者负责，可以使用任何机制。  <br/> |呼叫者负责，可以使用任何机制。  <br/> |
|输出  <br/> |调用的函数负责，必须使用 **MAPIAllocateBuffer**。 有关详细信息，请参阅 [MAPIAllocateBuffer](mapiallocatebuffer.md)。  <br/> |呼叫者负责，必须使用 **MAPIFreeBuffer**。 有关详细信息，请参阅 [MAPIFreeBuffer](mapifreebuffer.md)。  <br/> |
|输入输出  <br/> |调用方负责初始分配，调用的函数可在必要时使用 **MAPIAllocateBuffer 重新分配**。  <br/> |调用的函数负责在需要重新分配时进行初始释放。 调用方必须释放最终的返回值。  <br/> |
   
在故障期间，接口方法的实现者需要注意输出和输入输出参数，因为调用方通常无法清理它们。 如果返回错误，则必须将每个输出或输入输出参数都保持为调用方初始化的值，或设置为无需调用方的任何操作即可清理的值。 例如，必须将 的输出 pointer-parameter 保留为 在输入时，也可以设置为 NULL (  `void ** ppv`  `*ppv = NULL`) 。
  

