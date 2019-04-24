---
title: MAPI 扩展错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b0a9fc55-f4ab-45d8-98cc-b040f9ef6aa4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e5bffa0753e3d8c86e737a96cfd303be7bcd97f3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351553"
---
# <a name="mapi-extended-errors"></a>MAPI 扩展错误

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
接口方法的实现者可以选择只返回成功 (S_OK) 和失败 (MAPI_E_CALL_FAILED), 也可以选择区分错误条件, 返回对情况有意义的错误值。 大多数情况下, 可以使用由 MAPICODE 中的 MAPI 定义的某个错误值。H 头文件。 但是, 对于预定义值不包含的情况, 可以使用值 MAPI_E_EXTENDED_ERROR。 MAPI_E_EXTENDED_ERROR 向呼叫者指明有关错误的详细信息。 调用方通过对返回 MAPI_E_EXTENDED_ERROR 的同一对象调用**GetLastError**方法来检索其他信息。 
  
 可以调用**GetLastError**以检索有关任何错误代码的信息, 而不仅仅是 MAPI_E_EXTENDED_ERROR。 许多 MAPI 对象都实现包含**GetLastError**方法的接口。 **GetLastError**返回一个**MAPIERROR**结构, 该结构在理论上包括由上一个方法调用生成的所有错误的串联。 有关详细信息, 请参阅[MAPIERROR](mapierror.md)。 作为呼叫者, 最好不要依赖于让此额外的错误信息提供, 因为不需要对象实施者提供该信息。 但是, 强烈建议在实施者返回 MAPI_E_EXTENDED_ERROR 时, 调用方可以使用有关错误的有用信息检索**MAPIERROR**结构。 
  
由于**GetLastError**也是 Windows SDK 的一部分的 API 函数, 因此很容易忘记在 mapi 中, **GetLastError**是接口方法, 只能在 mapi 对象上调用。 另一个容易犯的错误是在错误的对象上调用**GetLastError** 。 必须对生成错误的对象调用**GetLastError** 。 例如, 如果您的客户端进行会话呼叫, 并且 MAPI 将呼叫转发给服务提供商来执行此操作, 则客户端不应在服务提供程序对象上调用**GetLastError** 。 **IMAPISession:: GetLastError**是正确的呼叫;应对 session 对象调用**GetLastError** 。 有关详细信息, 请参阅[IMAPISession:: GetLastError](imapisession-getlasterror.md)。
  

