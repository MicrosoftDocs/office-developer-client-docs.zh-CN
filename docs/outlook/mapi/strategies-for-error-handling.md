---
title: 错误处理的策略
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: be941efd-04b3-48d0-9b9c-8195ad2bb58d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b0ec3ada71a3e604ea71c5d386f1ff0466132081
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594087"
---
# <a name="strategies-for-error-handling"></a>错误处理的策略

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
由于接口方法是虚拟，不能为呼叫者，了解整套可以从任何一个的调用返回的值。 一种方法的实现可能返回五个值;另一个可能返回 8。 MAPI 文档中的引用条目列表几个可针对每种方法; 返回的值这些是您的客户端或服务提供商可以检查和处理，因为它们具有特殊含义的值。 可返回其他值，但因为它们不是有意义，特殊代码以处理那些没有必要。 对成功或失败的简单检查就足够了。
  
几个接口方法返回的警告。 如果您的客户端或服务提供商调用的方法可返回一条警告，请使用**HR_FAILED**宏测试的返回值，而不是零或非零值的检查。 警告，虽然非零值，不同错误代码，它们不具有较高的位设置。 如果您的客户端或服务提供程序不使用宏，很可能的可能失败的错误警告。 
  
尽管大多数接口方法和函数返回 HRESULT 值，但某些函数将返回未签署的长整型值。 此外，MAPI 环境中使用某些方法来自 COM，并返回 COM 错误值，而不是 MAPI 错误值。 发出呼叫时，请记住以下准则：
  
- 不要依赖或使用从**IUnknown::AddRef**或**IUnknown::Release**的返回值。 这些返回值是仅用于诊断。 
    
- **IUnknown::QueryInterface**始终返回其中实用工具是 FACILITY_NULL 或 FACILITY_RPC，一般的 COM 错误，而不是 MAPI 错误。 
    
- 所有其他接口方法返回与 FACILITY_ITF 或 FACILITY_RPC 的设施 MAPI 界面错误或 FACILITY_NULL 错误。
    
时调用了不受支持的 MAPI 方法，可返回四个可能的错误之一： 
  
MAPI_E_NO_SUPPORT
  
MAPI_E_INTERFACE_NOT_SUPPORTED
  
MAPI_E_INVALID_PARAMETER
  
MAPI_E_VERSION。 
  

