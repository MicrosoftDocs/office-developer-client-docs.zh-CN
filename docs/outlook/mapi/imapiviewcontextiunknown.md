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
ms.openlocfilehash: ae2729ec5620b6b408a5c999d4b6ede7143bed2f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584561"
---
# <a name="imapiviewcontext--iunknown"></a>IMAPIViewContext : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
管理客户端应用程序的表单查看器中的窗体。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|由公开：  <br/> |视图上下文对象  <br/> |
|通过实现：  <br/> |表单查看器  <br/> |
|调用：  <br/> |窗体对象  <br/> |
|接口标识符：  <br/> |IID_IMAPIViewContext  <br/> |
|指针类型：  <br/> |LPMAPIVIEWCONTEXT  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[SetAdviseSink](imapiviewcontext-setadvisesink.md) <br/> |管理窗体的注册中查看者接收有关更改的通知。  <br/> |
|[ActivateNext](imapiviewcontext-activatenext.md) <br/> |激活表单查看器中的下一页或上一页消息。  <br/> |
|[GetPrintSetup](imapiviewcontext-getprintsetup.md) <br/> |检索当前打印的信息。  <br/> |
|[GetSaveStream](imapiviewcontext-getsavestream.md) <br/> |检索用于保存当前消息流。  <br/> |
|[GetViewStatus](imapiviewcontext-getviewstatus.md) <br/> |检索当前的查看器状态。  <br/> |
|[时出错](imapiviewcontext-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面视图上下文对象中出现的错误的信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

