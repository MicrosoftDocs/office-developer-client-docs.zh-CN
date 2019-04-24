---
title: IMAPIForm IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm
api_type:
- COM
ms.assetid: e9059739-51b4-4574-bd0f-709eb5144ae7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 172cbf9478d3206742df61d211051594e69ab173
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321775"
---
# <a name="imapiform--iunknown"></a>IMAPIForm : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使表单查看者能够使用表单视图上下文和表单通知, 执行表单谓词和关闭表单。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
|公开者:  <br/> |表单对象  <br/> |
|实现者：  <br/> |表单服务器  <br/> |
|调用者：  <br/> |表单查看器  <br/> |
|接口标识符:  <br/> |IID_IMAPIForm  <br/> |
|指针类型:  <br/> |LPMAPIFORM  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[SetViewContext](imapiform-setviewcontext.md) <br/> |建立窗体的视图上下文。  <br/> |
|[GetViewContext](imapiform-getviewcontext.md) <br/> |返回窗体的当前视图上下文。  <br/> |
|[ShutdownForm](imapiform-shutdownform.md) <br/> |关闭表单。  <br/> |
|[DoVerb](imapiform-doverb.md) <br/> |请求表单执行与特定谓词相关联的任何任务。  <br/> |
|[她们](imapiform-advise.md) <br/> |注册表单查看器, 以获取有关影响表单的事件的通知。  <br/> |
|[Unadvise](imapiform-unadvise.md) <br/> |取消之前通过调用**Advise**建立的表单查看器对通知的注册。  <br/> |
|[GetLastError](imapiform-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个错误发生于表单对象的相关信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

