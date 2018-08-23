---
title: BuildDisplayTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- BuildDisplayTable
api_type:
- HeaderDef
ms.assetid: 0846415b-6fe1-4504-8620-108af6719015
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3b5268f0b033126083a463f72e47c64957df07eb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577686"
---
# <a name="builddisplaytable"></a>BuildDisplayTable

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
创建一个或多个[DTPAGE](dtpage.md)结构中包含的属性页数据显示表。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
STDAPI BuildDisplayTable(
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPALLOCATEMORE lpAllocateMore,
  LPFREEBUFFER lpFreeBuffer,
  LPMALLOC lpMalloc,
  HINSTANCE hInstance,
  UINT cPages,
  LPDTPAGE lpPage,
  ULONG ulFlags,
  LPMAPITABLE * lppTable,
  LPTABLEDATA * lppTblData
);
```

## <a name="parameters"></a>参数

 _lpAllocateBuffer_
  
> [in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。 
    
 _lpAllocateMore_
  
> [in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存。 
    
 _lpFreeBuffer_
  
> [in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。 
    
 _lpMalloc_
  
> 未使用;应设置为 NULL。 
    
 _hInstance_
  
> [in]**BuildDisplayTable**从中检索资源 MAPI 对象的实例。 
    
 _cPages_
  
> [in]由_lpPage_参数指向[DTPAGE](dtpage.md)结构数组中的计数。 
    
 _lpPage_
  
> [in]指针指向包含信息显示表页要生成的**DTPAGE**结构的数组。 
    
 _ulFlags_
  
> [in]Flags 的位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
 _lppTable_
  
> [输出]为显示表，该表公开[IMAPITable](imapitableiunknown.md)接口指针的指针。 
    
 _lppTblData_
  
> [传入、 传出]指向向 table 数据对象公开返回_lppTable_参数中的表上的[ITableData](itabledataiunknown.md)接口的指针的指针。 如果需要没有表数据对象，您应_lppTblData_的设置为 NULL 而不是一个指针值。 
    
## <a name="return-value"></a>返回值

无
  
## <a name="remarks"></a>注解

MAPI 使用所指的_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_对于大多数内存分配和释放，尤其是用于客户端应用程序分配内存，调用对象接口时的功能如[IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

所有内容可能读取对话框资源，包括：
  
- 页面标题的、 读取资源中的对话框标题的[DTBLPAGE](dtblpage.md)结构的_ulbLpszLabel_成员。 
    
- 是的所有控件标题、 读取资源中的控件文本其他控制结构的_ulbLpszLabel_成员。 
    
 **BuildDisplayTable**覆盖任何传递中与信息的输入的控件结构，从对话框资源，这意味着**BuildDisplayTable**的调用方动态无法指定页或控件的标题。 呼叫者需执行的操作可具有**BuildDisplayTable** _lppTableData_中返回的表数据对象，并更改中; 行或他们可以改为在表数据对象中手动构建显示表。 
  
如果_lppTableData_未设置为 NULL，提供程序负责完成与显示表格释放的表数据对象。 
  

