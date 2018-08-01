---
title: ITableDataHrGetView
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrGetView
api_type:
- COM
ms.assetid: 0e2a47be-497b-4031-87ce-60b2635e25f7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a913f2f3a72a365ec7d5078eccf31c4212ca83a5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776091"
---
# <a name="itabledatahrgetview"></a>ITableData::HrGetView

  
  
**适用于**： Outlook 
  
创建表视图中，返回到[IMAPITable](imapitableiunknown.md)实现的指针。 
  
```cpp
HRESULT HrGetView(
  LPSSortOrderSet lpSSortOrderSet,
  CALLERRELEASE FAR * lpfCallerRelease,
  ULONG_PTR ulCallerData,
  LPMAPITABLE FAR * lppMAPITable
);
```

## <a name="parameters"></a>参数

 _lpSSortOrderSet_
  
> [in]指向介绍表视图的排序顺序排序顺序结构的指针。 如果_lpSSortOrderSet_参数中传递 NULL，则视图未排序。 
    
 _lpfCallerRelease_
  
> [in]指向[CALLERRELEASE](callerrelease.md)原型 MAPI 调用时释放视图所基于的回调函数的指针。 如果_lpfCallerRelease_参数中传递 NULL，则没有函数调用上的视图的版本。 
    
 _ulCallerData_
  
> [in]必须使用新的视图保存并传递给回调函数使用的数据所指的_lpfCallerRelease_。
    
 _lppMAPITable_
  
> [输出]为指向新创建的视图的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功创建的视图。
    
## <a name="remarks"></a>说明

**ITableData::HrGetView**方法在表中， _lpSSortOrderSet_参数指向的顺序排序创建只读视图的数据。 光标置于视图中的第一行开头处。 返回**IMAPITable**接口实现用于访问该视图。 
  
服务提供商调用**HrGetView**时所需向表格的客户端访问。 **HrGetView**创建视图，并返回**IMAPITable**指针。 服务提供商反过来传递到客户端的指针。 当客户端完成使用表后，并将调用其[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法时， **HrGetView**调用_lpfCallerRelease_参数指向的回调函数。 
  
如果服务提供商需要具有一个自定义的列设置的视图返回到客户端或限制，提供程序可以调用视图的[IMAPITable::SetColumns](imapitable-setcolumns.md)和[IMAPITable::Restrict](imapitable-restrict.md)方法才允许客户端访问。 
  
## <a name="see-also"></a>另请参阅



[CALLERRELEASE](callerrelease.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)
  
[SSortOrderSet](ssortorderset.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

