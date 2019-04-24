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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281583"
---
# <a name="allocating-and-freeing-memory-in-mapi"></a>在 MAPI 中分配和释放内存

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
除了指定如何分配和释放内存之外, MAPI 还定义一个模型, 以了解在何时释放公共接口方法和 API 函数调用之间传递的内存。 模型仅适用于为不是指向接口的指针 (如字符串和指向结构的指针) 的参数分配的内存。 接口指针使用通过**IUnknown**实现的引用计数机制。 在客户端应用程序或服务提供程序内部分配和释放与非 MAPI 相关的内存时, 请使用任何有意义的机制。 
  
模型将参数定义为以下三种类型之一。 它们可以是输入参数, 由调用方设置, 由调用的函数或方法、输出参数、被调用的函数或方法设置并返回给调用方或输入输出参数 (这两种类型的组合) 所使用的信息。 输出参数通常是指向数据的数据或指向数据的指针的指针。 虽然被调用的函数负责为输出参数分配数据, 但调用方为指针分配内存。 
  
下表介绍了为这些类型的参数分配和释放内存的规则。
  
|**Type**|**内存分配**|**内存释放**|
|:-----|:-----|:-----|
|Input  <br/> |呼叫者负责, 并且可以使用任何机制。  <br/> |呼叫者负责, 并且可以使用任何机制。  <br/> |
|Output  <br/> |被叫函数负责, 必须使用**MAPIAllocateBuffer**。 有关详细信息, 请参阅[MAPIAllocateBuffer](mapiallocatebuffer.md)。  <br/> |呼叫者负责, 必须使用**MAPIFreeBuffer**。 有关详细信息, 请参阅[MAPIFreeBuffer](mapifreebuffer.md)。  <br/> |
|输入输出  <br/> |如果需要, 调用方负责使用**MAPIAllocateBuffer**来重新分配初始分配和被调用函数。  <br/> |如果需要重新分配, 则调用的函数负责初始化释放。 调用方必须释放最终返回值。  <br/> |
   
在失败情况下, 接口方法的实现者需要注意输出和输入输出参数, 因为调用方通常无法清除它们。 如果返回错误, 则必须将每个输出或输入输出参数保留为调用方初始化的值, 或设置为一个可清除的值, 而不是调用方的任何操作。 例如, 的`void ** ppv`输出指针参数必须保留在输入中, 或可设置为 NULL ( `*ppv = NULL`)。
  

