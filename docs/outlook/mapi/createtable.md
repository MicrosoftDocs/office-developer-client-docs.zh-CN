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
ms.openlocfilehash: e8c399569e68b8cb55d803733ed93105ea0be799
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435010"
---
# <a name="createtable"></a>CreateTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为[ITableData](itabledataiunknown.md)对象创建结构和对象句柄, 该对象可用于创建表格内容。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
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
  
> 实时指向 table 数据对象的接口标识符 (IID) 的指针。 有效的接口标识符为 IID_IMAPITableData。 在_lpInterface_参数中传递 NULL 还会导致在_lppTableData_参数中返回的表数据对象将转换为 table 数据对象的标准接口。 
    
 _lpAllocateBuffer_
  
> 实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。 
    
 _lpAllocateMore_
  
> 实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于分配更多内存。 
    
 _lpFreeBuffer_
  
> 实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。 
    
 _lpvReserved_
  
> 实时保留必须为零。 
    
 _ulTableType_
  
> 实时作为[IMAPITable:: GetStatus](imapitable-getstatus.md)的一部分提供给客户端应用程序或服务提供程序的表类型将返回其表视图中的数据。 可能的值是： 
    
TBLTYPE_DYNAMIC 
  
> 表的内容是动态的, 并且可以随着基础数据的变化而变化。 
    
TBLTYPE_KEYSET 
  
> 表中的行是固定的, 但这些行中的值是动态的, 并且可以随着基础数据的变化而变化。 
    
TBLTYPE_SNAPSHOT 
  
> 该表是静态的, 并且在基础数据发生更改时内容不会更改。 
    
 _ulPropTagIndexColumn_
  
> 实时更改表数据时使用的列的索引号。 
    
 _lpSPropTagArrayColumns_
  
> 实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含一个由属性标记数组组成的数组, 这些标记指明了对象为其保留数据的表中所需的属性。 
    
 _lppTableData_
  
> 排除指向返回的 table 数据对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>说明

" _lpAllocateBuffer_"、" _lpAllocateMore_" 和 " _lpFreeBuffer_ " 输入参数分别指向 " [MAPIAllocateBuffer](mapiallocatebuffer.md)"、" [MAPIAllocateMore](mapiallocatemore.md)" 和 " [MAPIFreeBuffer](mapifreebuffer.md) " 函数。 调用**CreateTable**的客户端应用程序传递到刚刚命名的 MAPI 函数的指针。服务提供程序将指向其初始化调用中收到的这些函数的指针传递给这些函数, 或通过调用[IMAPISupport:: GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法检索这些函数。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable : IUnknown](imapitableiunknown.md)

