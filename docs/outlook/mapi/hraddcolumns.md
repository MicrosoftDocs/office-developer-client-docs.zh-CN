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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348193"
---
# <a name="hraddcolumns"></a>HrAddColumns

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将列添加或移动到现有表的开头。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapiutil  <br/> |
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
  
> 实时指向受影响的 MAPI 表的指针。
    
 _lpproptagColumnsNew_
  
> 实时指向**SPropTagArray**结构的指针, 该结构包含要添加或移动到表开头的属性的属性标记数组。 
    
 _lpAllocateBuffer_
  
> 实时指向**MAPIAllocateBuffer**函数的指针。 用于分配内存。 
    
 _lpFreeBuffer_
  
> 实时指向**MAPIFreeBuffer**函数的指针。 用于释放内存。 
    
## <a name="return-value"></a>返回值

 **S_OK**
  
> 调用成功, 并已移动或添加指定的列。
    
## <a name="remarks"></a>注解

**HrAddColumns**函数等效于使用_lpfnFilterColumns_设置为 NULL 的**HrAddColumnsEx** 。 
  
## <a name="see-also"></a>另请参阅



[HrAddColumnsEx](hraddcolumnsex.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropTagArray](sproptagarray.md)

