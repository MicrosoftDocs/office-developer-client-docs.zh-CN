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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318093"
---
# <a name="builddisplaytable"></a>BuildDisplayTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从包含在一个或多个[DTPAGE](dtpage.md)结构中的属性页数据创建显示表。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
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
  
> 实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。 
    
 _lpAllocateMore_
  
> 实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于分配更多内存。 
    
 _lpFreeBuffer_
  
> 实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。 
    
 _lpMalloc_
  
> 未经应设置为 NULL。 
    
 _hInstance_
  
> 实时**BuildDisplayTable**从中检索资源的 MAPI 对象的实例。 
    
 _cPages_
  
> 实时由_lpPage_参数指向的数组中的[DTPAGE](dtpage.md)结构的计数。 
    
 _lpPage_
  
> 实时指向**DTPAGE**结构数组的指针, 该数组包含要生成的显示表页的相关信息。 
    
 _ulFlags_
  
> 实时标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 
    
 _lppTable_
  
> 排除指向显示[IMAPITable](imapitableiunknown.md)接口的显示表的指针的指针。 
    
 _lppTblData_
  
> [in, out]指向指向表数据对象的指针的指针, 该对象公开在_lppTable_参数中返回的表上的[ITableData](itabledataiunknown.md)接口。 如果不需要表数据对象, 则应将_lppTblData_设置为 NULL, 而不是指针值。 
    
## <a name="return-value"></a>返回值

无
  
## <a name="remarks"></a>注解

MAPI 将_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指向的函数用于大多数内存分配和释放, 尤其是在调用对象接口时分配内存供客户端应用程序使用。例如[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

可从对话框资源中读取所有可能的内容, 其中包括:
  
- 页面标题即[DTBLPAGE](dtblpage.md)结构的_ulbLpszLabel_成员从该资源的对话框标题中读取。 
    
- 所有控件标题即从资源中的控件文本读取的其他控件结构的_ulbLpszLabel_成员。 
    
 **BuildDisplayTable**将使用对话框资源中的信息覆盖输入控制结构中传递的任何内容, 这意味着**BuildDisplayTable**的调用方无法动态指定页面或控件标题。 需要执行此操作的调用方可以让**BuildDisplayTable**返回_lppTableData_中的表数据对象并更改其中的行;也可以改为将显示表手动构建在表数据对象中。 
  
如果_lppTableData_未设置为 NULL, 则提供程序将负责在完成显示表后释放表数据对象。 
  

