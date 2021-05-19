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
  
创建可用于创建表内容的 [ITableData](itabledataiunknown.md) 对象的结构和对象句柄。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向表数据 (IID) 接口标识符的指针。 有效的接口标识符IID_IMAPITableData。 在  _lpInterface_ 参数中传递 NULL 还会导致  _lppTableData_ 参数中返回的表数据对象被强制转换到表数据对象的标准接口。 
    
 _lpAllocateBuffer_
  
> [in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。 
    
 _lpAllocateMore_
  
> [in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配额外的内存。 
    
 _lpFreeBuffer_
  
> [in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。 
    
 _lpvReserved_
  
> [in]保留;必须为零。 
    
 _ulTableType_
  
> [in]作为 [IMAPITable：：GetStatus](imapitable-getstatus.md) 的一部分提供给客户端应用程序或服务提供商的表类型在其表视图上返回数据。 可能的值是： 
    
TBLTYPE_DYNAMIC 
  
> 该表的内容是动态的，并且可能会随着基础数据的变化而更改。 
    
TBLTYPE_KEYSET 
  
> 表中的行是固定的，但这些行中的值是动态的，并且可能会随着基础数据的变化而更改。 
    
TBLTYPE_SNAPSHOT 
  
> 该表是静态表，在基础数据更改时不会更改内容。 
    
 _ulPropTagIndexColumn_
  
> [in]更改表数据时使用的列的索引号。 
    
 _lpSPropTagArrayColumns_
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，该结构包含一组属性标记，指示对象保存数据的表中所需的属性。 
    
 _lppTableData_
  
> [out]指向返回的表数据对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

_lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 输入参数分别指向 [MAPIAllocateBuffer、MAPIAllocateMore](mapiallocatebuffer.md)和 [MAPIFreeBuffer](mapifreebuffer.md)函数。  [](mapiallocatemore.md) 调用 **CreateTable** 的客户端应用程序将传递指向刚命名的 MAPI 函数的指针;服务提供商将指针传递给其在其初始化调用中收到的或通过调用 [IMAPISupport：：GetMemAllocRoutines](imapisupport-getmemallocroutines.md) 方法检索的函数。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable : IUnknown](imapitableiunknown.md)

