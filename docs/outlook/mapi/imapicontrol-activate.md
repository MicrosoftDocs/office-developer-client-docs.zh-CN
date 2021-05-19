---
title: IMAPIControlActivate
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIControl.Activate
api_type:
- COM
ms.assetid: 2b641030-2429-4217-a648-0a9f3d1a1b29
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d3b47e423daf428c67761d13deef1ae0858c91c0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418013"
---
# <a name="imapicontrolactivate"></a>IMAPIControl::Activate

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
执行一个任务，如在客户端应用程序用户单击按钮控件时显示对话框或启动编程操作。
  
```cpp
HRESULT Activate(
  ULONG ulFlags,
  ULONG_PTR ulUIParam
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _ulUIParam_
  
> [in]显示按钮控件的对话框的父窗口的句柄。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 按钮控件已成功激活。
    
## <a name="remarks"></a>备注

**IMAPIControl：：Activate** 方法在用户单击按钮控件后执行任务。 单击后，作为处理显示表的一部分，MAPI 在首次调用 [IMAPIControl：：GetState](imapicontrol-getstate.md)后调用 **Activate，** 以确定按钮是否已启用。 
  
若要详细了解如何实现 Activate **和其他** [IMAPIControl ： IUnknown](imapicontroliunknown.md) 方法，请参阅 [Control Object Implementation](control-object-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIControl::GetState](imapicontrol-getstate.md)
  
[IMAPIControl : IUnknown](imapicontroliunknown.md)

