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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392058"
---
# <a name="imapiformadvisesink--iunknown"></a>IMAPIFormAdviseSink : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
允许表单服务器表单查看器从接收通知。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
|由公开：  <br/> |窗体告知接收器对象  <br/> |
|实现者：  <br/> |表单服务器  <br/> |
|调用者：  <br/> |表单查看器  <br/> |
|接口标识符：  <br/> |IID_IMAPIFormAdviseSink  <br/> |
|指针类型：  <br/> |LPMAPIFORMADVISESINK  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[OnChange](imapiformadvisesink-onchange.md) <br/> |指示在表单查看器的状态发生更改。  <br/> |
|[OnActivateNext](imapiformadvisesink-onactivatenext.md) <br/> |指示表单是否可以处理的下一条消息以显示的邮件类。  <br/> |
   
## <a name="remarks"></a>说明

表单服务器表单使用建议接收器对象而不是其 form 对象并将其包含实现**IMAPIFormAdviseSink** 。 因此，表单查看器应产生预期失败的调用窗体[IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)方法来获取此接口的指针。 
  
窗体服务器调用注册通知的查看者的[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)方法。 包含用作参数对**IMAPIFormAdviseSink**实施的指针。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

