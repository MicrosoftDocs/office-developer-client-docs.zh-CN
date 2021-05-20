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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429689"
---
# <a name="mapi-return-value-documentation"></a>MAPI 返回值文档

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本参考文档中的引用条目仅返回需要客户端应用程序进行一些处理的返回值。 返回指示常见错误条件且可通过检查失败而推断的值不包含在文档中。 例如，如果调用方为输入参数MAPI_E_INVALID_PARAMETER错误值，则许多接口方法都可以返回值。 此值通常未在预期返回值集合中列出，因为不需要专门查找 MAPI_E_INVALID_PARAMETER也无需以不同于任何其他错误的方式处理该值。 另一方面，某些服务提供商不支持事件通知，并且将MAPI_E_NO_SUPPORT通过 **IMAPISession** 的 **Advise** 方法返回通知。 由于客户端需要显式检查此值并提供用于处理它表示的条件的代码（如果发生这种情况，MAPI_E_NO_SUPPORT 会包含在 [IMAPISession：：Advise](imapisession-advise.md)的返回值列表中。
  
下表描述了通常从方法和函数返回的错误值，并且需要在客户端或服务提供商的一部分进行显式处理。 这些值分为四类：表示无效输入数据的值、指示资源问题的值、指示字符集不兼容的值和指示未知来源失败的值。
  
|**返回值**|**说明**|
|:-----|:-----|
|MAPI_E_INVALID_PARAMETER  <br/> |传入方法或函数的一个或多个参数无效。  <br/> |
|MAPI_E_UNKNOWN_FLAGS  <br/> |标记参数的一个或多个值已无效。  <br/> |
|MAPI_E_DISK_ERROR  <br/> |写入磁盘或从磁盘读取时出现问题。  <br/> |
|MAPI_E_NOT_ENOUGH_DISK  <br/> |磁盘空间不足，无法完成操作。  <br/> |
|MAPI_E_NOT_ENOUGH_MEMORY  <br/> |没有足够的内存来完成该操作。  <br/> |
|MAPI_E_NOT_ENOUGH_RESOURCES  <br/> |没有足够的系统资源来完成该操作。  <br/> |
|MAPI_E_BAD_CHARWIDTH  <br/> |调用方和实现支持的字符集中存在不兼容。  <br/> |
|MAPI_E_CALL_FAILED  <br/> |发生意外或未知来源错误。  <br/> |
   
表示 MAPI 返回值的常量列在 MAPICODE 中。H 头文件。 某些常量映射到 Win32 错误;可以在 Win32 头文件 WINERROR.H 中找到这些常量与数值的映射。
  
有关调用方传入的无效数据的错误可以通过 MAPI 提供的参数验证 API 函数或一组宏来确定。 
  
出现以下任一情况时，会出现字符集不兼容情况：
  
- 客户端或服务提供商在方法MAPI_UNICODE函数调用上设置该标志，而实现不支持 Unicode。 setting MAPI_UNICODE indicates that character strings passed in as input are Unicode strings and that character strings passed back as output are expected to Unicode strings.
    
- 客户端或服务提供商不会在方法或MAPI_UNICODE上设置该标志，并且实现仅支持 Unicode。
    

