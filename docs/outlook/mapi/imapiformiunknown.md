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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: fce8bc45d5cc87c238288653ab989b62076ad451
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775422"
---
# <a name="imapiform--iunknown"></a>IMAPIForm: IUnknown

  
  
**适用于**： Outlook 
  
启用表单查看器处理窗体视图上下文和窗体通知，来执行窗体动词和关闭窗体。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|由公开：  <br/> |窗体对象  <br/> |
|通过实现：  <br/> |表单服务器  <br/> |
|调用：  <br/> |表单查看器  <br/> |
|接口标识符：  <br/> |IID_IMAPIForm  <br/> |
|指针类型：  <br/> |LPMAPIFORM  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[SetViewContext](imapiform-setviewcontext.md) <br/> |建立窗体视图上下文。  <br/> |
|[GetViewContext](imapiform-getviewcontext.md) <br/> |返回表单的当前视图上下文。  <br/> |
|[ShutdownForm](imapiform-shutdownform.md) <br/> |关闭表单。  <br/> |
|[DoVerb](imapiform-doverb.md) <br/> |请求窗体执行任何任务它将与特定动词。  <br/> |
|[建议](imapiform-advise.md) <br/> |注册的窗体查看有关影响窗体的事件通知。  <br/> |
|[取消通知](imapiform-unadvise.md) <br/> |使用窗体查看器通过调用**Advise**以前建立取消通知注册。  <br/> |
|[时出错](imapiform-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的 form 对象发生的错误的信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

