---
title: 错误处理策略
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: be941efd-04b3-48d0-9b9c-8195ad2bb58d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9e76ae3f292d8348b9dc64cb54bffae96b96e871
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424145"
---
# <a name="strategies-for-error-handling"></a>错误处理策略

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
由于接口方法是虚拟的, 因此不可能知道可从任何一个调用返回的完整值集。 方法的一个实现可能返回5个值;另一个可能返回8个。 MAPI 文档列表中的引用条目可为每个方法返回几个值;您的客户端或服务提供商可以对其进行检查和处理的值, 因为它们具有特殊含义。 可以返回其他值, 但由于它们没有意义, 因此处理这些值的特殊代码不是必需的。 成功或失败的简单检查就足够了。
  
几种接口方法返回警告。 如果您的客户端或服务提供商调用的方法可以返回警告, 请使用**HR_FAILED**宏来测试返回值, 而不是检查是否为零或非零。 警告 (尽管非零) 与错误代码的不同之处在于, 它们没有设置高位。 如果您的客户端或服务提供商不使用宏, 可能会有警告被误认为失败。 
  
尽管大多数接口方法和函数都返回 HRESULT 值, 但某些函数会返回无符号的 long 值。 此外, MAPI 环境中使用的某些方法来自 com, 并返回 com 错误值, 而不是 MAPI 错误值。 调用时请牢记以下准则:
  
- 从不依赖或使用来自**IUnknown:: AddRef**或**iunknown:: Release**的返回值。 这些返回值仅用于诊断目的。 
    
- **IUnknown:: QueryInterface**总是返回常规 COM 错误, 其中设备为 FACILITY_NULL 或 FACILITY_RPC, 而不是 MAPI 错误。 
    
- 所有其他接口方法返回的 MAPI 接口错误与 FACILITY_ITF 或 FACILITY_RPC 或 FACILITY_NULL 错误的功能。
    
当调用不受支持的 MAPI 方法时, 可能会返回以下四个错误之一: 
  
MAPI_E_NO_SUPPORT
  
MAPI_E_INTERFACE_NOT_SUPPORTED
  
MAPI_E_INVALID_PARAMETER
  
MAPI_E_VERSION。 
  

