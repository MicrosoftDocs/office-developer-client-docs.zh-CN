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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436382"
---
# <a name="imapiform--iunknown"></a>IMAPIForm : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
允许表单查看器使用表单视图上下文和表单通知、执行表单谓词和关闭表单。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
|公开者：  <br/> |表单对象  <br/> |
|实现者：  <br/> |表单服务器  <br/> |
|调用者：  <br/> |表单查看器  <br/> |
|接口标识符：  <br/> |IID_IMAPIForm  <br/> |
|指针类型：  <br/> |LPMAPIFORM  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[SetViewContext](imapiform-setviewcontext.md) <br/> |建立表单的视图上下文。  <br/> |
|[GetViewContext](imapiform-getviewcontext.md) <br/> |返回窗体的当前视图上下文。  <br/> |
|[ShutdownForm](imapiform-shutdownform.md) <br/> |关闭表单。  <br/> |
|[DoVerb](imapiform-doverb.md) <br/> |请求表单执行与特定动词关联的任何任务。  <br/> |
|[建议](imapiform-advise.md) <br/> |注册窗体查看器，以接收有关影响窗体的事件的通知。  <br/> |
|[非企业](imapiform-unadvise.md) <br/> |通过调用 Advise 取消之前建立的表单查看器的通知 **注册**。  <br/> |
|[GetLastError](imapiform-getlasterror.md) <br/> |返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关表单对象发生的上一个错误的信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

