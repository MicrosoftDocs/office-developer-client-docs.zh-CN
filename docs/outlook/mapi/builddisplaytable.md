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
ms.openlocfilehash: 8c5e6078be05ff846b7737ff53e9a6338fcb2141
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431594"
---
# <a name="builddisplaytable"></a>BuildDisplayTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
根据一个或多个 [DTPAGE](dtpage.md) 结构中包含的属性页数据创建显示表。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
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
  
> [in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。 
    
 _lpAllocateMore_
  
> [in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配额外的内存。 
    
 _lpFreeBuffer_
  
> [in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。 
    
 _lpMalloc_
  
> 未使用;应设置为 NULL。 
    
 _hInstance_
  
> [in] **BuildDisplayTable** 从中检索资源的 MAPI 对象的实例。 
    
 _cPages_
  
> [in]_lpPage_ 参数指向的数组中的 [DTPAGE](dtpage.md)结构计数。 
    
 _lpPage_
  
> [in]指向包含有关要构建的显示表页的信息的 **DTPAGE** 结构的数组的指针。 
    
 _ulFlags_
  
> [in]标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。 
    
 _lppTable_
  
> [out]指向显示表的指针的指针，显示表公开 [IMAPITable](imapitableiunknown.md) 接口。 
    
 _lppTblData_
  
> [in， out]指向在 _lppTable_ 参数中返回的表上公开 [ITableData](itabledataiunknown.md)接口的表数据对象的指针的指针。 如果不需要表数据对象，则  _lppTblData_ 应设置为 NULL，而不是指针值。 
    
## <a name="return-value"></a>返回值

无
  
## <a name="remarks"></a>备注

MAPI 使用 _lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 指向的函数进行大多数内存分配和处理，尤其是当调用 [IMAPIProp：：GetProps](imapiprop-getprops.md)和 [IMAPITable：：QueryRows](imapitable-queryrows.md)等对象接口时，分配供客户端应用程序使用的内存。  
  
## <a name="notes-to-callers"></a>给调用方的说明

所有可能内容都从对话框资源中读取，包括：
  
- 页面标题，即从资源中的对话框标题读取 [的 DTBLPAGE](dtblpage.md)结构的 _ulbLpszLabel_ 成员。 
    
- 所有控件标题，即其他控件结构的  _ulbLpszLabel_ 成员，从资源中的控件文本读取。 
    
 **BuildDisplayTable** 使用对话框资源的信息覆盖输入控件结构中传递的任何内容，这意味着 **BuildDisplayTable** 的调用方无法动态指定页面或控件标题。 需要让 **BuildDisplayTable** 这样做的调用方在  _lppTableData_ 中返回表数据对象并更改其行;或者他们可以在表数据对象中手动生成显示表。 
  
如果  _lppTableData_ 未设置为 NULL，则提供程序负责在表数据对象处理完显示表后释放该对象。 
  

