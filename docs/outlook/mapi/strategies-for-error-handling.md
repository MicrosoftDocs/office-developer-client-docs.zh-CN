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
  
由于接口方法是虚拟的，因此作为调用方，无法知道可以从任何一个调用返回的完整值集。 方法的一个实现可能返回五个值;另一个可能返回 8。 MAPI 文档中的参考条目列出了可以针对每个方法返回的一些值;这些是客户端或服务提供商可以检查和处理的值，因为它们具有特殊的含义。 可以返回其他值，但由于这些值没有意义，因此不需要处理这些值的特殊代码。 只需简单检查成功还是失败就足够了。
  
一些接口方法返回警告。 如果客户端或服务提供商调用的方法可以返回警告，请使用 HR_FAILED 宏来测试返回值，而不是检查返回值是零还是非零。 警告虽然不是零，但不同于错误代码，因为它们没有设置高位。 如果您的客户端或服务提供商不使用该宏，则可能会因为失败而错误地显示一条警告。 
  
虽然大多数接口方法和函数都返回 HRESULT 值，但某些函数返回无符号长数值。 此外，MAPI 环境中使用某些方法来自 COM 并返回 COM 错误值，而不是 MAPI 错误值。 进行呼叫时，请记住以下准则：
  
- 绝不依赖或使用 **IUnknown：：AddRef** 或 **IUnknown：：Release 中的返回值**。 这些返回值仅供诊断使用。 
    
- **IUnknown：：QueryInterface** 始终返回常规 COM 错误，其中设备是FACILITY_NULL或FACILITY_RPC，而不是 MAPI 错误。 
    
- 所有其他接口方法都返回 MAPI 接口错误，这些接口FACILITY_ITF或FACILITY_RPC或FACILITY_NULL错误。
    
当调用不受支持的 MAPI 方法时，可能会返回以下四个可能的错误之一： 
  
MAPI_E_NO_SUPPORT
  
MAPI_E_INTERFACE_NOT_SUPPORTED
  
MAPI_E_INVALID_PARAMETER
  
MAPI_E_VERSION。 
  

