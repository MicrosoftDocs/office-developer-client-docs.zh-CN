---
title: IMAPIControl IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIControl
api_type:
- COM
ms.assetid: 5a647e15-ba22-4a7c-b235-75cd76b77c1a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8dce1415ef8d18f4b786e92324c888f9a0845162
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414037"
---
# <a name="imapicontrol--iunknown"></a>IMAPIControl : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启用和禁用按钮控件，当客户端应用程序的用户单击启用的控件时执行任务。 服务提供程序实现控件对象，以在使用显示表定义的对话框（如配置属性表）上创建自定义按钮。 
  
有关如何使用显示表和控件对象的信息，请参阅 [显示表](display-tables.md)。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|公开者：  <br/> |Control 对象  <br/> |
|实现者：  <br/> |服务提供程序  <br/> |
|调用者：  <br/> |MAPI  <br/> |
|接口标识符：  <br/> |IID_IMAPIControl  <br/> |
|指针类型：  <br/> |LPMAPICONTROL  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](imapicontrol-getlasterror.md) <br/> |返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个按钮控件错误的信息。  <br/> |
|[Activate](imapicontrol-activate.md) <br/> |执行一个任务，如在客户端应用程序用户单击按钮控件时显示对话框或启动编程操作。  <br/> |
|[GetState](imapicontrol-getstate.md) <br/> |检索一个值，该值指示按钮控件是启用还是禁用。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

