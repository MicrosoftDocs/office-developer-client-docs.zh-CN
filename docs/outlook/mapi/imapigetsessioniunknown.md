---
title: IMAPIGetSession IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIGetSession
api_type:
- COM
ms.assetid: d1b662e2-1516-46b2-ba94-4092d79b5a39
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0b861a11b6bc1d590225a0c99b20f8be38edfd2b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436648"
---
# <a name="imapigetsession--iunknown"></a>IMAPIGetSession : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对与支持对象相关联的当前 MAPI 会话的访问权限。 mapi 提供程序可以查询其 MAPI 支持对象的此接口。 有关支持对象的详细信息, 请参阅[支持对象概述](support-object-overview.md)。
  
|||
|:-----|:-----|
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |MAPI 提供程序  <br/> |
|接口标识符:  <br/> |IID_IMAPIGetSession  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetMAPISession](imapigetsession-getmapisession.md) <br/> |调用以获取指向当前 MAPI 会话的指针。  <br/> |
   
## <a name="see-also"></a>另请参阅



[GetMAPISession](imapigetsession-getmapisession.md)
  
[IMAPISupport](imapisupportiunknown.md)


[MAPI 接口](mapi-interfaces.md)
  
[支持对象概述](support-object-overview.md)

