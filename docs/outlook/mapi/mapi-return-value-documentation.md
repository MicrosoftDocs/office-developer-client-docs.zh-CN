---
title: MAPI 返回值文档
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c32ee53c-b063-4a00-a6bf-75ce5e07f56a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5bbafe9fda479d951bb20175ab904dc6e241226a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329713"
---
# <a name="mapi-return-value-documentation"></a>MAPI 返回值文档

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
此参考中的引用条目只记录那些需要由客户端应用程序处理的返回值。 返回指示常见错误条件的值, 并且可以通过检查是否有故障来推断, 而不包括在文档中。 例如, 如果调用方为输入参数指定了错误的值, 则许多接口方法可以返回 MAPI_E_INVALID_PARAMETER。 此值通常不会在预期的返回值集中列出, 因为无需专门查找 MAPI_E_INVALID_PARAMETER, 也无需与任何其他错误那样进行处理。 另一方面, 某些服务提供商不支持事件通知, 并将 MAPI_E_NO_SUPPORT 返回到由客户端通过**IMAPISession**发出的**Advise**方法。 由于客户端需要显式检查此值并提供用于处理它所代表的条件的代码, 因此, MAPI_E_NO_SUPPORT 将包含在[IMAPISession:: 建议](imapisession-advise.md)的返回值列表中。
  
下表介绍了通常从方法和函数返回的错误值, 并要求对客户端或服务提供程序的部分进行显式处理。 这些值分为四个类别: 指示无效输入数据的值、指示资源问题的值、指示字符集不兼容的值以及指示未知源失败的值。
  
|**返回值**|**说明**|
|:-----|:-----|
|MAPI_E_INVALID_PARAMETER  <br/> |传递到方法或函数中的一个或多个参数无效。  <br/> |
|MAPI_E_UNKNOWN_FLAGS  <br/> |flags 参数的一个或多个值无效。  <br/> |
|MAPI_E_DISK_ERROR  <br/> |写入或读取磁盘时出现问题。  <br/> |
|MAPI_E_NOT_ENOUGH_DISK  <br/> |可用磁盘空间不足, 无法完成此操作。  <br/> |
|MAPI_E_NOT_ENOUGH_MEMORY  <br/> |可用内存不足, 无法完成操作。  <br/> |
|MAPI_E_NOT_ENOUGH_RESOURCES  <br/> |可用的系统资源不足, 无法完成此操作。  <br/> |
|MAPI_E_BAD_CHARWIDTH  <br/> |调用方和实现支持的字符集中存在不兼容性。  <br/> |
|MAPI_E_CALL_FAILED  <br/> |发生意外或未知源的错误。  <br/> |
   
表示 MAPI 返回值的常量在 MAPICODE 中列出。H 头文件。 某些常量映射到 Win32 错误;可以在 Win32 头文件 winerror.h 中找到这些常量到数字值的映射。水平.
  
可以通过 MAPI 提供的参数验证 API 函数或一组宏来确定有关由呼叫者传入的无效数据的错误。 
  
出现以下情况之一时, 将出现字符集不兼容情况:
  
- 客户端或服务提供程序在方法或函数调用上设置 MAPI_UNICODE 标志, 且实现不支持 UNICODE。 设置 MAPI_UNICODE 指示作为输入传入的字符字符串是 unicode 字符串, 而传递回输出的字符串应为 unicode 字符串。
    
- 客户端或服务提供程序不会在方法或函数调用上设置 MAPI_UNICODE 标志, 且实现仅支持 UNICODE。
    

