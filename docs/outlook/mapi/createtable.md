---
title: CreateTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- CreateTable
api_type:
- HeaderDef
ms.assetid: 106ce3d8-d0bf-4a0e-9a15-dc8988d0eb58
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5d4717dad51e7e6b90da59d285268761eec84d7b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564148"
---
# <a name="createtable"></a>CreateTable

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
创建结构和[ITableData](itabledataiunknown.md)对象可用于创建目录对象句柄。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE CreateTable(
  LPCIID lpInterface,
  ALLOCATEBUFFER FAR * lpAllocateBuffer,
  ALLOCATEMORE FAR * lpAllocateMore,
  FREEBUFFER FAR * lpFreeBuffer,
  LPVOID lpvReserved,
  ULONG ulTableType,
  ULONG ulPropTagIndexColumn,
  LPSPropTagArray lpSPropTagArrayColumns,
  LPTABLEDATA FAR * lppTableData
);
```

## <a name="parameters"></a>参数

 _lpInterface_
  
> [in]指向表数据对象的界面标识符 (IID) 的指针。 有效的接口标识符是 IID_IMAPITableData。 _LpInterface_参数中传递 NULL 还会导致_lppTableData_参数将强制转换为标准接口表数据对象中返回的表数据对象。 
    
 _lpAllocateBuffer_
  
> [in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。 
    
 _lpAllocateMore_
  
> [in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存。 
    
 _lpFreeBuffer_
  
> [in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。 
    
 _lpvReserved_
  
> [in]保留;必须为零。 
    
 _ulTableType_
  
> [in]可供客户端应用程序或服务提供商作为其表视图上的[IMAPITable::GetStatus](imapitable-getstatus.md)返回数据的一部分表类型。 可能的值是： 
    
TBLTYPE_DYNAMIC 
  
> 表的内容是动态，并且可以更改基础数据集更改。 
    
TBLTYPE_KEYSET 
  
> 表中的行固定的但这些行中的值是动态，并可以更改基础数据集更改。 
    
TBLTYPE_SNAPSHOT 
  
> 表是静态的在基础数据更改时不更改内容。 
    
 _ulPropTagIndexColumn_
  
> [in]更改表数据时使用的列的索引号。 
    
 _lpSPropTagArrayColumns_
  
> [in]指向[SPropTagArray](sproptagarray.md)结构，其中包含数组属性标记，指示其对象包含数据的表中所需的属性。 
    
 _lppTableData_
  
> [输出]指向对返回的表格数据对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>注解

_LpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_输入的参数分别指向[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)，和[MAPIFreeBuffer](mapifreebuffer.md)函数。 调用**CreateTable**客户端应用程序中指针传递给 MAPI 函数只名为;服务提供商将指针传递给它在其初始化呼叫中收到或与调用[IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法检索这些函数。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable : IUnknown](imapitableiunknown.md)

