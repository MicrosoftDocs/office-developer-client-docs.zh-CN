---
title: MAPI 字符集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: fbe63916-b3eb-4ea7-bc42-80a8b0281b03
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 898883d8c93b69762883a502b7a4313b3417d0d3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319073"
---
# <a name="mapi-character-sets"></a>MAPI 字符集

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
符合 MAPI 的客户端应用程序和服务提供程序可以使用 ANSI 字符 (单字节) 或 Unicode 字符 (双字节)。 OEM 字符集不受支持。 传递给 MAPI 方法或函数的 OEM 字符串将导致该方法或函数失败。 使用 OEM 字符集中的文件名的客户端应用程序必须在将它们传递给 MAPI 方法或函数之前, 将其转换为 ANSI。
  
对于客户端和服务提供程序, 支持 Unicode 字符集是可选的。 所有服务提供程序都应编写自己的代码, 以便无论它们是否支持 Unicode, 都可以编译它们。 客户端根据其支持级别进行了条件编译, 但服务提供商不会这样做。 在字符集发生更改时, 不必重新编译这些设置。 服务提供程序代码中的任何内容都不应有条件。 
  
当支持 Unicode 的客户端或服务提供程序发出的方法调用包含作为输入或输出参数的字符串时, 它们将设置 MAPI_UNICODE 标志。 设置此标志指示所有传入字符串均为 Unicode 字符串的实现。 在输出时, 设置此标志将请求从实现传递回来的所有字符串都应为 Unicode 字符串 (如果可能)。 支持 Unicode 的方法实施者将符合请求;不提供 Unicode 支持的方法实施者将不符合这些要求。 不是 Unicode 格式的字符串属性的类型为 PT_STRING8。
  
MAPI 在头文件 mapidefs.h 中定义**fMapiUnicode**常量。H 表示默认字符集。 如果客户端或服务提供程序支持 Unicode, 则**fMapiUnicode**设置为 MAPI_UNICODE。 不支持 Unicode 的客户端和服务提供程序将**fMapiUnicode**设置为零。 
  
不支持 Unicode 的服务提供程序应执行以下操作:
  
- 拒绝在字符集之间执行转换。
    
- 从不在方法调用中传递 MAPI_UNICODE 标志。
    
- 在传入 MAPI_UNICODE 标志时返回 MAPI_E_BAD_CHARWIDTH。
    
- 显式声明 ANSI 字符串属性。 
    
如果服务提供程序仅支持 Unicode, 并且客户端未传递 MAPI_UNICODE 标志, 则服务提供程序也可以返回 MAPI_E_BAD_CHARWIDTH。 
  
 当前版本的 MAPI 在以下方法中支持 Unicode: 
  
[IAddrBook::Address](iaddrbook-address.md)
  
[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)
  
[IAddrBook::Details](iaddrbook-details.md)
  
[IAddrBook::ResolveName](iaddrbook-resolvename.md)
  
[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)(仅限**IAddrBook**实现) 
  
对于这些方法, 调用方可以预期任何返回的字符串为 Unicode 字符串。 从任何其他方法的 MAPI 实现返回的字符串将是 ANSI 字符字符串。
  

