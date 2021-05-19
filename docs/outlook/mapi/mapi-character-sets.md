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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417551"
---
# <a name="mapi-character-sets"></a>MAPI 字符集

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
符合 MAPI 的客户端应用程序和服务提供商可以使用 ANSI 字符 (字节字符) Unicode 字符 (双字节) 。 不支持 OEM 字符集。 传递给 MAPI 方法或函数的 OEM 字符串将导致该方法或函数失败。 处理 OEM 字符集内文件名的客户端应用程序在将它们传递到 MAPI 方法或函数之前，必须小心将其转换为 ANSI。
  
对于客户端和服务提供商，支持 Unicode 字符集是可选的。 所有服务提供商都应编写其代码，以便无论它们是否支持 Unicode，都可以进行编译。 客户端有条件地编译，具体取决于其支持级别，但服务提供商没有。 当字符集更改时，它们不应重新编译。 服务提供程序代码中没有任何内容应具有条件。 
  
当支持 Unicode 的客户端或服务提供商进行包含字符串作为输入或输出参数的方法调用时，它们MAPI_UNICODE标志。 设置此标志将指示实现所有传入字符串都是 Unicode 字符串。 在输出上，如果可能，设置此标志将请求从实现传递回的所有字符串应为 Unicode 字符串。 支持 Unicode 的方法实施者将符合请求;不提供 Unicode 支持的方法实施者将不符合。 非 Unicode 格式的字符串属性的类型PT_STRING8。
  
MAPI 定义头文件 MAPIDEFS 中的 **fMapiUnicode** 常量。H 表示默认字符集。 如果客户端或服务提供商支持 Unicode， **则 fMapiUnicode** 将设置为 MAPI_UNICODE。 不支持 Unicode 的客户端和服务提供商将 **fMapiUnicode 设置为** 零。 
  
不支持 Unicode 的服务提供商应：
  
- 拒绝在字符集之间执行转换。
    
- 从不在方法MAPI_UNICODE传递该标志。
    
- 返回MAPI_E_BAD_CHARWIDTH传入MAPI_UNICODE时返回值。
    
- 显式声明 ANSI 字符串属性。 
    
当服务提供商仅支持 Unicode MAPI_E_BAD_CHARWIDTH客户端不传递 Unicode 标志时，它们也可以返回MAPI_UNICODE值。 
  
 MAPI 的当前版本支持以下方法中的 Unicode： 
  
[IAddrBook::Address](iaddrbook-address.md)
  
[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)
  
[IAddrBook::Details](iaddrbook-details.md)
  
[IAddrBook::ResolveName](iaddrbook-resolvename.md)
  
[IMAPIProp：：GetLastError](imapiprop-getlasterror.md) (**IAddrBook** 实现)  
  
对于这些方法，调用方预期任何返回的字符串为 Unicode 字符串。 从任何其他方法的 MAPI 实现返回的字符串将是 ANSI 字符串。
  

