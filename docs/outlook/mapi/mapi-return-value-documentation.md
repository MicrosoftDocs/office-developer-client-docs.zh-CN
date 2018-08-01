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
ms.openlocfilehash: f2b8f87987f93ec152d4986131a6b7990273c28d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776318"
---
# <a name="mapi-return-value-documentation"></a>MAPI 返回值文档

  
  
**适用于**： Outlook 
  
本参考中的引用条目文档仅这些客户端应用程序需要一些处理的返回值。 返回值指示常见错误条件，可以通过检查失败推导不包含文档中。 例如，很多接口方法可以返回 MAPI_E_INVALID_PARAMETER，如果呼叫者指定输入参数的错误值。 此值未通常列出集中预期的返回值的原因是存在不需要专门为 MAPI_E_INVALID_PARAMETER 查找和无需从任何其他错误处理也不同。 另一方面，某些服务提供程序不支持事件通知，并将所做的客户端通过**IMAPISession** **Advise**方法返回 MAPI_E_NO_SUPPORT。 由于客户端需要显式检查此值，并提供用于处理它所表示的条件的代码应发生此错误，MAPI_E_NO_SUPPORT 纳入[IMAPISession::Advise](imapisession-advise.md)返回值的列表。
  
下表描述通常会返回从方法和函数，并且需要进行客户端或服务提供程序需要显式处理的错误值。 这些值分为四个类别： 表示无效输入的数据、 指示资源问题值、 指示字符集不兼容，值和指示来源未知失败的值。
  
|**返回值**|**说明**|
|:-----|:-----|
|MAPI_E_INVALID_PARAMETER  <br/> |一个或多个参数传递到方法或函数不是有效。  <br/> |
|MAPI_E_UNKNOWN_FLAGS  <br/> |一个或多个 flags 参数值不是有效的。  <br/> |
|MAPI_E_DISK_ERROR  <br/> |出现问题写入或从磁盘读取。  <br/> |
|MAPI_E_NOT_ENOUGH_DISK  <br/> |没有足够的磁盘空间时无法完成操作。  <br/> |
|MAPI_E_NOT_ENOUGH_MEMORY  <br/> |没有足够的内存已无法完成操作。  <br/> |
|MAPI_E_NOT_ENOUGH_RESOURCES  <br/> |没有足够的系统资源已无法完成操作。  <br/> |
|MAPI_E_BAD_CHARWIDTH  <br/> |呼叫者和实现支持的字符集中存在不兼容。  <br/> |
|MAPI_E_CALL_FAILED  <br/> |出现意外的或未知的原点而言的错误。  <br/> |
   
MAPICODE 列出了表示 MAPI 返回值的常量。H 头文件。 部分常量将映射到 Win32 错误;在 Win32 标头文件中，WINERROR 找不到这些常量为数字值的映射。H。
  
可以通过任一参数验证 API 函数 MAPI 或一组的宏提供确定传入呼叫者的无效数据有关的错误。 
  
字符设置不兼容，则会发生发生以下情况之一：
  
- 客户端或服务提供程序设置的方法或函数调用 MAPI_UNICODE 标志和实现不支持 Unicode。 设置 MAPI_UNICODE 指示作为输入中传递的字符串的 Unicode 字符串和字符串传递回作为输出会为 Unicode 字符串。
    
- 客户端或服务提供程序的方法或函数调用未设置 MAPI_UNICODE 标志和实现仅支持 Unicode。
    

