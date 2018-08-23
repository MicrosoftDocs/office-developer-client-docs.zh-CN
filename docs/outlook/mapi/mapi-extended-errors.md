---
title: MAPI 扩展错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b0a9fc55-f4ab-45d8-98cc-b040f9ef6aa4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5a9499e2a980cbc00eb11c5199bb7329b255c7b2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592659"
---
# <a name="mapi-extended-errors"></a>MAPI 扩展错误

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
接口方法的实施者可以选择只返回 (S_OK) 成功和失败 (MAPI_E_CALL_FAILED) 或区分错误条件，返回尽可能多的错误值，如意义的情况。 大多数情况下可以使用由 MAPI MAPICODE 中定义的错误值之一。H 头文件。 但是，对于不包含的预定义的值，可以使用 MAPI_E_EXTENDED_ERROR 的值的情况。 MAPI_E_EXTENDED_ERROR 指示呼叫者有关错误的详细信息可用。 呼叫者的返回 MAPI_E_EXTENDED_ERROR 同一对象上调用**GetLastError**方法来检索的其他信息。 
  
 **GetLastError**可调用它以检索任何错误代码，而不是只 MAPI_E_EXTENDED_ERROR 有关的信息。 许多 MAPI 对象实现包括**GetLastError**方法的接口。 **GetLastError**返回的单个**MAPIERROR**结构，理论上来说，包括的所有以前方法调用生成的错误串联。 有关详细信息，请参阅[MAPIERROR](mapierror.md)。 为呼叫者，则不最好取决于因为对象实施，无需提供其具有此额外可用的错误信息。 但是，强烈建议，只要实施返回 MAPI_E_EXTENDED_ERROR，它们使呼叫者在检索有关错误的有用信息**MAPIERROR**结构。 
  
由于**GetLastError**也是属于 Windows SDK API 函数，它可以轻松地忘记了 MAPI， **GetLastError**是接口方法和仅可以 MAPI 对象上调用。 另一个简单的错误进行错误的对象上调用**时出错**。 必须在生成错误的对象上调用**时出错**。 例如，如果您的客户端发出呼叫，会话并 MAPI 转发到服务提供商的呼叫进行的工作，您的客户端不应调用**GetLastError**上的服务提供程序对象。 **IMAPISession::GetLastError**是正确的调用中;应在会话对象上调用**时出错**。 有关详细信息，请参阅[IMAPISession::GetLastError](imapisession-getlasterror.md)。
  

