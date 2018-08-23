---
title: MAPI 字符集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: fbe63916-b3eb-4ea7-bc42-80a8b0281b03
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5f7da3da8d23b28e13c39570b8f5971cb75a3310
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582530"
---
# <a name="mapi-character-sets"></a>MAPI 字符集

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 兼容的客户端应用程序和服务提供商可以使用 ANSI 字符 （单字节） 或 Unicode 字符 （双字节）。 不支持 OEM 字符集。 OEM 字符串传递给 MAPI 方法或函数将导致该方法或函数失败。 使用 OEM 字符集中的文件名的客户端应用程序必须注意之前将它们传递给 MAPI 方法或函数将其转换为 ANSI。
  
支持 Unicode 字符集是可选的同时为客户端和服务提供程序。 所有服务提供商应都编写自己的代码，以便他们可以编译而不考虑它们支持 Unicode。 客户端编译有条件地，具体取决于其级别的支持，但服务提供商不。 他们不应有字符集更改时重新编译。 在服务提供程序代码中为 nothing 应条件。 
  
当客户端或服务提供程序支持 Unicode 使方法调用包含字符串作为输入或输出参数，它们会设置 MAPI_UNICODE 标志。 设置此标志指示的实现的所有传入字符串是否 Unicode 字符串。 输出，设置传递的所有字符串都后从实现此标志请求应为 Unicode 字符串如果可能。 支持 Unicode 的方法实现方注释将遵守请求;不提供 Unicode 支持的方法实现方注释将不符合要求。 不在 Unicode 格式的字符串属性是类型 PT_STRING8。
  
MAPI 头文件 MAPIDEFS 中定义**fMapiUnicode**常量。H 以表示默认字符集。 如果客户端或服务提供程序支持 Unicode， **fMapiUnicode**设置为 MAPI_UNICODE。 客户端和不支持 Unicode 的服务提供商设置**fMapiUnicode**为零。 
  
服务提供程序不支持 Unicode 应：
  
- 拒绝执行字符集之间的转换。
    
- 从不方法调用中传递 MAPI_UNICODE 标志。
    
- 当传入 MAPI_UNICODE 标志，则返回 MAPI_E_BAD_CHARWIDTH。
    
- 显式声明 ANSI 字符串属性。 
    
服务提供商还可以返回 MAPI_E_BAD_CHARWIDTH 仅支持 Unicode 和客户端时不要传递 MAPI_UNICODE 标志。 
  
 MAPI 的当前版本中支持 Unicode，在下列方法： 
  
[IAddrBook::Address](iaddrbook-address.md)
  
[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)
  
[IAddrBook::Details](iaddrbook-details.md)
  
[IAddrBook::ResolveName](iaddrbook-resolvename.md)
  
[IMAPIProp::GetLastError](imapiprop-getlasterror.md)（仅适用于**IAddrBook**实现） 
  
对于这些方法，调用方可以预期任何返回的字符串为 Unicode 字符串。 从 MAPI 实现的任何其他方法返回的字符串将 ANSI 字符串。
  

