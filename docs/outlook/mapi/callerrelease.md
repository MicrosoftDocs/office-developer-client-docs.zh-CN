---
title: CALLERRELEASE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- CALLERRELEASE
api_type:
- HeaderDef
ms.assetid: 80ba893d-3380-4db1-9175-f5b84cb57def
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9a22550e60c9de38236a9f612c7e60f50f18978f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331841"
---
# <a name="callerrelease"></a>CALLERRELEASE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义在释放表视图时可释放表数据对象的回调函数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|定义的函数实现者:  <br/> |客户端应用程序和服务提供程序  <br/> |
|定义的函数调用者:  <br/> |MAPI  <br/> |
   
```cpp
void CALLERRELEASE(
  ULONG_PTR ulCallerData,
  LPTABLEDATA lpTblData,
  LPMAPITABLE lpVue
);
```

## <a name="parameters"></a>参数

 _ulCallerData_
  
> 实时由 MAPI 保存在表视图中并传递给基于**CALLERRELEASE**的回调函数的调用方数据。 数据提供有关要释放的表视图的上下文。 
    
 _lpTblData_
  
> 实时指向要释放的表视图基础的表数据对象的[ITableData: IUnknown](itabledataiunknown.md)接口的指针。 
    
 _lpVue_
  
> 实时指向要释放的表视图的[IMAPITable: IUnknown](imapitableiunknown.md)接口的指针。 这是在创建要释放的对象的[ITableData:: HrGetView](itabledata-hrgetview.md)方法的_lppMAPITable_参数中返回的 table 对象的接口。 
    
## <a name="return-value"></a>返回值

无 
  
## <a name="remarks"></a>注解

填充了 table data 对象的客户端应用程序或服务提供程序可以调用[ITableData:: HrGetView](itabledata-hrgetview.md)以创建表的只读、排序视图。 对**HrGetView**的调用会将指针传递给基于**CALLERRELEASE**的回调函数, 还会传递与表视图一起保存的上下文。 当表视图的引用计数返回到零, 并且正在释放视图时, **IMAPITable**实现将调用回调函数, 并在_ulCallerData_参数中传递上下文。 
  
基于**CALLERRELEASE**的回调函数的常见用途是释放基础表数据对象, 而无需在后续处理期间对其进行跟踪。 
  

