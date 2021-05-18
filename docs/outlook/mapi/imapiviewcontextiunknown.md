---
title: IMAPIViewContext IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext
api_type:
- COM
ms.assetid: d566ff39-92c1-4a14-85e5-1c406825f805
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: db0c375218755c3a28475e2ebce2d097fb789f75
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406029"
---
# <a name="imapiviewcontext--iunknown"></a>IMAPIViewContext : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在客户端应用程序的表单查看器中管理表单。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
|公开者：  <br/> |查看上下文对象  <br/> |
|实现者：  <br/> |表单查看器  <br/> |
|调用者：  <br/> |表单对象  <br/> |
|接口标识符：  <br/> |IID_IMAPIViewContext  <br/> |
|指针类型：  <br/> |LPMAPIVIEWCONTEXT  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[SetAdviseSink](imapiviewcontext-setadvisesink.md) <br/> |管理表单的注册以接收有关查看器中更改的通知。  <br/> |
|[ActivateNext](imapiviewcontext-activatenext.md) <br/> |激活窗体查看器中的下一封邮件或上一封邮件。  <br/> |
|[GetPrintSetup](imapiviewcontext-getprintsetup.md) <br/> |检索当前打印信息。  <br/> |
|[GetSaveStream](imapiviewcontext-getsavestream.md) <br/> |检索用于保存当前消息的流。  <br/> |
|[GetViewStatus](imapiviewcontext-getviewstatus.md) <br/> |检索当前查看器状态。  <br/> |
|[GetLastError](imapiviewcontext-getlasterror.md) <br/> |返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关视图上下文对象中发生的上一个错误的信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

