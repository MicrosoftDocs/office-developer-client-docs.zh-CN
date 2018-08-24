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
ms.openlocfilehash: ffc47e924b7a0f94db66adbffe01b2cdc619dc8c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580731"
---
# <a name="hraddcolumns"></a>HrAddColumns

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
添加或移到现有表的起点的列。
  
|||
|:-----|:-----|
|头文件：  <br/> |mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商。  <br/> |
   
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
  
> [in]指向受影响的 MAPI 表。
    
 _lpproptagColumnsNew_
  
> [in]指向**SPropTagArray**结构，其中包含要添加或移至表格的开头的属性的属性标记的数组。 
    
 _lpAllocateBuffer_
  
> [in]指向**MAPIAllocateBuffer**函数指针。 用于分配内存。 
    
 _lpFreeBuffer_
  
> [in]指向**MAPIFreeBuffer**函数指针。 使用以释放内存。 
    
## <a name="return-value"></a>返回值

 **S_OK**
  
> 调用成功，并指定的列已移动或添加。
    
## <a name="remarks"></a>注解

**HrAddColumns**函数等效于**HrAddColumnsEx**使用_lpfnFilterColumns_设置为 NULL。 
  
## <a name="see-also"></a>另请参阅



[HrAddColumnsEx](hraddcolumnsex.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropTagArray](sproptagarray.md)

