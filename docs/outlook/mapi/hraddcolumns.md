---
title: HrAddColumns
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8c980257-9372-4478-b635-bd91d0a66af9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 465b685038bc3d906e468c7d7b06e9c20e1fd3c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422472"
---
# <a name="hraddcolumns"></a>HrAddColumns

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
向现有表格的开头添加或移动列。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序。  <br/> |
   
```cpp
HRESULT HrAddColumns(
  LPMAPITABLE lptbl,
  LPSPropTagArray lpproptagColumnsNew,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPFREEBUFFER lpFreeBuffer
);
```

## <a name="parameters"></a>参数

 _lptbl_
  
> [in]指向受影响的 MAPI 表的指针。
    
 _lpproptagColumnsNew_
  
> [in]指向 **SPropTagArray** 结构的指针，其中包含要添加或移动到表开头的属性的属性标记数组。 
    
 _lpAllocateBuffer_
  
> [in]指向 **MAPIAllocateBuffer 函数的** 指针。 用于分配内存。 
    
 _lpFreeBuffer_
  
> [in]指向 **MAPIFreeBuffer 函数的** 指针。 用于释放内存。 
    
## <a name="return-value"></a>返回值

 **S_OK**
  
> 调用成功，并移动或添加指定的列。
    
## <a name="remarks"></a>备注

**HrAddColumns** 函数等效于将 **HrAddColumnsEx** 与 _将 lpfnFilterColumns_ 设置为 NULL。 
  
## <a name="see-also"></a>另请参阅



[HrAddColumnsEx](hraddcolumnsex.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropTagArray](sproptagarray.md)

