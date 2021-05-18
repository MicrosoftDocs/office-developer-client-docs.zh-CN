---
title: IMAPIFormAdviseSink IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormAdviseSink
api_type:
- COM
ms.assetid: 180022af-4c1c-408c-a3fe-ed075cef79ab
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 68c2af0cd8d7ccddf6aa6017cfb830b196ac0771
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286602"
---
# <a name="imapiformadvisesink--iunknown"></a>IMAPIFormAdviseSink : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使表单服务器能够接收来自表单查看器的通知。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
|公开者：  <br/> |表单建议接收对象  <br/> |
|实现者：  <br/> |表单服务器  <br/> |
|调用者：  <br/> |表单查看器  <br/> |
|接口标识符：  <br/> |IID_IMAPIFormAdviseSink  <br/> |
|指针类型：  <br/> |LPMAPIFORMADVISESINK  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[OnChange](imapiformadvisesink-onchange.md) <br/> |指示表单查看器的状态发生了更改。  <br/> |
|[OnActivateNext](imapiformadvisesink-onactivatenext.md) <br/> |指示表单是否可以处理要显示的下一封邮件的邮件类。  <br/> |
   
## <a name="remarks"></a>备注

表单服务器使用表单建议接收对象来实现 **IMAPIFormAdviseSink，而不是将 IMAPIFormAdviseSink** 与其 form 对象一起包含。 因此，表单查看者应预期对表单 [的 IUnknown：：QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 方法的调用失败，以获取指向此接口的指针。 
  
表单服务器调用查看器的 [IMAPIViewContext：：SetAdviseSink](imapiviewcontext-setadvisesink.md) 方法来注册通知。 指向 **IMAPIFormAdviseSink** 实现指针作为参数包含在内。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

