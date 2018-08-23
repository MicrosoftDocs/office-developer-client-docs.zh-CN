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
ms.openlocfilehash: 80acb1a1e4663a68efc4692ab67ec27bc369f4b0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566514"
---
# <a name="imapicontrol--iunknown"></a>IMAPIControl : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
启用和禁用按钮控件，并执行任务时客户端应用程序的用户单击已启用的控件。 服务提供商实现控件对象上对话框，例如配置的属性页，通过使用显示表定义创建自定义按钮。 
  
有关如何使用显示表格和控制对象的详细信息，请参阅[显示表](display-tables.md)。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |控件对象  <br/> |
|通过实现：  <br/> |服务提供商  <br/> |
|调用：  <br/> |MAPI  <br/> |
|接口标识符：  <br/> |IID_IMAPIControl  <br/> |
|指针类型：  <br/> |LPMAPICONTROL  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](imapicontrol-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前一个按钮控件错误的信息。  <br/> |
|[Activate](imapicontrol-activate.md) <br/> |执行显示一个对话框，或在客户端应用程序用户单击按钮控件时启动编程操作等任务。  <br/> |
|[GetState](imapicontrol-getstate.md) <br/> |检索值，该值指示是否启用或禁用按钮控件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

