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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 375a0f1d39b09b7ad453120f20752e00ffda0e15
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278713"
---
# <a name="itabledatahrgetview"></a>ITableData::HrGetView

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建表视图，返回指向 [IMAPITable](imapitableiunknown.md) 实现指针。 
  
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
  
> [in]指向用于描述表视图的排序顺序的排序顺序结构的指针。 如果在  _lpSSortOrderSet_ 参数中传递 NULL，则不对视图进行排序。 
    
 _lpfCallerRelease_
  
> [in]指向基于 [CALLERRELEASE](callerrelease.md) 原型的回调函数的指针，MAPI 在发布视图时调用该原型。 如果在  _lpfCallerRelease_ 参数中传递 NULL，则发布视图时不调用任何函数。 
    
 _ulCallerData_
  
> [in]必须使用新视图保存并传递给  _lpfCallerRelease_ 指向的回调函数的数据。
    
 _lppMAPITable_
  
> [out]指向指向新创建的视图的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建视图。
    
## <a name="remarks"></a>备注

**ITableData：：HrGetView** 方法创建表中数据的只读视图，按 _lpSSortOrderSet_ 参数指向的顺序进行排序。 光标放置在视图中第一行的开头。 返回 **用于访问视图的 IMAPITable** 接口实现。 
  
当服务提供商需要向客户端授予对表的访问权限时，将调用 **HrGetView。** **HrGetView** 创建视图并返回 **IMAPITable** 指针。 服务提供商反过来将指针传递给客户端。 当客户端使用完表并调用其 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 方法时 **，HrGetView** 将调用  _lpfCallerRelease_ 参数指向的回调函数。 
  
如果服务提供商需要向客户端返回具有自定义列集或限制的视图，则提供程序可以在允许客户端访问之前调用该视图的 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 和 [IMAPITable：：Restrict](imapitable-restrict.md) 方法。 
  
## <a name="see-also"></a>另请参阅



[CALLERRELEASE](callerrelease.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)
  
[SSortOrderSet](ssortorderset.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

