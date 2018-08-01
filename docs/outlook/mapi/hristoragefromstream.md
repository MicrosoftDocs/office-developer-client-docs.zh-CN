---
title: HrIStorageFromStream
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrIStorageFromStream
api_type:
- HeaderDef
ms.assetid: 1cdc95b8-a156-4600-9e20-caaa02680e87
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bd2d0a662585e8aba91250786f88dd310fe37e32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775179"
---
# <a name="hristoragefromstream"></a>HrIStorageFromStream

  
  
**适用于**： Outlook 
  
Layers **IStorage**接口到**IStream**对象。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT HrIStorageFromStream(
  LPUNKNOWN lpUnkIn,
  PIID lpInterface,
  ULONG ulFlags,
  LPSTORAGE FAR * lppStorageOut
);
```

## <a name="parameters"></a>参数

 _lpUnkIn_
  
> [in]为实现**IStream**的**IUnknown**对象的指针。 
    
 _lpInterface_
  
> [in]Stream 对象的接口标识符 (IID) 的指针。 可以在_lpInterface_参数中传递的任何以下值： NULL、 IID_IStream 或 IID_ILockBytes。 在_lpInterface_传递 NULL 是传递 IID_IStream 相同。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何存储对象是相对于流创建。 默认设置是 STGSTRM_RESET，其中提供存储对象的只读访问并在位置零流的启动它。 可以在以下标志设置以任意组合，除所述：
    
STGSTRM_CREATE 
  
> 创建新的存储对象的 stream 对象。 如果设置了 STGSTRM_RESET 标志，则不能设置此标志。 
    
STGSTRM_CURRENT 
  
> 启动存储 stream 的当前的位置。 如果设置了 STGSTRM_RESET 标志，则不能设置此标志。 
    
STGSTRM_MODIFY 
  
> 允许写入返回的存储调用服务提供程序。 如果设置了 STGSTRM_RESET 标志，则不能设置此标志。 
    
STGSTRM_RESET 
  
> 启动存储位置为零。 如果设置了任何其他标志，则不能设置此标志。 
    
 _lppStorageOut_
  
> [输出]为返回**IStorage**对象指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

消息存储提供程序支持的附件使用**IStorage**接口的**HrIStorageFromStream**函数。 存储提供程序必须实现**IStream**接口。 **HrIStorageFromStream** **IStream**对象提供的**IStorage**接口。 就可以传递**ILockBytes**或中_lpUnkIn_ **IStream**接口。 
  

