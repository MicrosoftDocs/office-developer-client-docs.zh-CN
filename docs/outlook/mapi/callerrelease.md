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
ms.openlocfilehash: 69ee06ef8c8f5499dec41232d3dc7b374b15a744
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774616"
---
# <a name="callerrelease"></a>CALLERRELEASE

  
  
**适用于**： Outlook 
  
定义一个在释放表视图时，可以释放表数据对象的回调函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实施定义的函数：  <br/> |客户端应用程序和服务提供商  <br/> |
|定义的函数调用：  <br/> |MAPI  <br/> |
   
```cpp
void CALLERRELEASE(
  ULONG_PTR ulCallerData,
  LPTABLEDATA lpTblData,
  LPMAPITABLE lpVue
);
```

## <a name="parameters"></a>参数

 _ulCallerData_
  
> [in]呼叫者数据，由 MAPI 保存与表视图并传递给**CALLERRELEASE**基于回调函数。 数据提供有关要发布的表视图的上下文。 
    
 _lpTblData_
  
> [in]指向[ITableData: IUnknown](itabledataiunknown.md)基础正在发布表视图的表数据对象的接口。 
    
 _lpVue_
  
> [in]指向[IMAPITable: IUnknown](imapitableiunknown.md)正在发布表视图的接口。 这是用于创建要释放的对象的[ITableData::HrGetView](itabledata-hrgetview.md)方法的_lppMAPITable_参数中返回的 table 对象的接口。 
    
## <a name="return-value"></a>返回值

无 
  
## <a name="remarks"></a>说明

客户端应用程序或已填充表数据对象的服务提供商可以调用[ITableData::HrGetView](itabledata-hrgetview.md)创建只读、 已排序的表的视图。 对**HrGetView**的调用将指针传递给**CALLERRELEASE**基于回调函数以及与表视图保存的上下文。 当表视图的引用计数返回为零，即被释放视图**IMAPITable**实现调用_ulCallerData_参数中传递上下文的回调函数。 
  
**CALLERRELEASE**基于回调函数的一个常见用途是发行版基础表数据对象并没有以跟踪其后续处理过程中。 
  

