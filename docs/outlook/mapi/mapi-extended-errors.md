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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405609"
---
# <a name="mapi-extended-errors"></a>MAPI 扩展错误

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
接口方法的实现者可以选择仅返回成功值 (S_OK) 失败值 (MAPI_E_CALL_FAILED) 或区分错误条件，返回对情况有意义的错误值。 大多数情况都可以使用 MAPICODE 中 MAPI 定义的错误值之一。H 头文件。 但是，对于预定义值未涵盖的情况，可以使用MAPI_E_EXTENDED_ERROR值。 MAPI_E_EXTENDED_ERROR向调用方指示有关错误的详细信息可用。 调用方通过调用返回的同一对象的 **GetLastError** 方法来检索其他MAPI_E_EXTENDED_ERROR。 
  
 **可以调用 GetLastError** 来检索有关任何错误代码的信息，而不仅是MAPI_E_EXTENDED_ERROR。 许多 MAPI 对象实现包含 **GetLastError 方法的** 接口。 **GetLastError** 返回一个 **MAPIERROR** 结构，理论上，它包含由上一个方法调用生成的所有错误的串联。 有关详细信息，请参阅 [MAPIERROR](mapierror.md)。 作为调用方，不要依赖于提供此额外错误信息是明智的，因为对象实现程序不需要提供它。 但是，强烈建议每当实现者返回MAPI_E_EXTENDED_ERROR，它们使调用方能够检索包含有关错误的有用信息的 **MAPIERROR** 结构。 
  
由于 **GetLastError** 也是属于 Windows SDK 的 API 函数，因此很容易忘记在 MAPI 中 **，GetLastError** 是接口方法，并且只能在 MAPI 对象上调用。 另一个容易出错的错误是在错误的对象上调用 **GetLastError。** **必须在生成错误的对象上调用 GetLastError。** 例如，如果客户端进行会话调用，而 MAPI 将呼叫转发给服务提供商以执行此工作，则客户端不应对服务提供商对象调用 **GetLastError。** **IMAPISession：：GetLastError** 是正确的调用;**应在会话对象上调用 GetLastError。** 有关详细信息，请参阅 [IMAPISession：：GetLastError](imapisession-getlasterror.md)。
  

