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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408724"
---
# <a name="callerrelease"></a>CALLERRELEASE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义一个回调函数，该函数可在发布表视图时释放表数据对象。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|定义的函数实现方：  <br/> |客户端应用程序和服务提供商  <br/> |
|由调用的已定义函数：  <br/> |MAPI  <br/> |
   
```cpp
void CALLERRELEASE(
  ULONG_PTR ulCallerData,
  LPTABLEDATA lpTblData,
  LPMAPITABLE lpVue
);
```

## <a name="parameters"></a>参数

 _ulCallerData_
  
> [in]MAPI 保存的调用方数据与表视图一起传递给 **基于 CALLERRELEASE** 的回调函数。 数据提供有关要发布的表视图的上下文。 
    
 _lpTblData_
  
> [in]指向要发布的表视图基础的表数据对象的 [ITableData ： IUnknown](itabledataiunknown.md) 接口的指针。 
    
 _lpVue_
  
> [in]指向要发布的 [表视图的 IMAPITable ： IUnknown](imapitableiunknown.md) 接口的指针。 这是创建要释放的对象的 [ITableData：：HrGetView](itabledata-hrgetview.md)方法 _的 lppMAPITable_ 参数中返回的表对象的接口。 
    
## <a name="return-value"></a>返回值

无 
  
## <a name="remarks"></a>备注

已填充表数据对象的客户端应用程序或服务提供商可以调用 [ITableData：：HrGetView](itabledata-hrgetview.md) 来创建表的只读排序视图。 对 **HrGetView 的** 调用将指针传递给基于 **CALLERRELEASE** 的回调函数以及要与表视图一起保存的上下文。 当表视图的引用计数返回零并释放视图时 **，IMAPITable** 实现将调用回调函数，在  _ulCallerData_ 参数中传递上下文。 
  
基于 **CALLERRELEASE** 的回调函数的常见用途是释放基础表数据对象，并且不需要在后续处理过程中跟踪它。 
  

