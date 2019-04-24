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
ms.openlocfilehash: 1362b1131d937ef240aa1962db8c1b5116786c67
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347780"
---
# <a name="hristoragefromstream"></a>HrIStorageFromStream

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将**IStorage**接口分层到**IStream**对象。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
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
  
> 实时指向实现**IStream**的**IUnknown**对象的指针。 
    
 _lpInterface_
  
> 实时指向 stream 对象的接口标识符 (IID) 的指针。 以下任何值都可以在_lpInterface_参数中传递: NULL、IID_IStream 或 IID_ILockBytes。 在_lpInterface_中传递 NULL 与传递 IID_IStream 相同。 
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制存储对象相对于流的创建方式。 默认设置为 STGSTRM_RESET, 它将为存储对象提供只读访问权限, 并在流的位置0处启动该对象。 可以任意组合设置以下标志, 除了所述:
    
STGSTRM_CREATE 
  
> 为 stream 对象创建一个新的存储对象。 如果设置了 STGSTRM_RESET 标志, 则不能设置此标志。 
    
STGSTRM_CURRENT 
  
> 在流的当前位置启动存储。 如果设置了 STGSTRM_RESET 标志, 则不能设置此标志。 
    
STGSTRM_MODIFY 
  
> 允许呼叫服务提供程序对返回的存储进行写入。 如果设置了 STGSTRM_RESET 标志, 则不能设置此标志。 
    
STGSTRM_RESET 
  
> 在位置零处启动存储。 如果设置了任何其他标志, 则不能设置此标志。 
    
 _lppStorageOut_
  
> 排除指向返回的**IStorage**对象的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

邮件存储提供程序支持附件使用**IStorage**接口的**HrIStorageFromStream**函数。 存储提供程序必须实现**IStream**接口。 **HrIStorageFromStream**为**IStream**对象提供**IStorage**接口。 可以在_lpUnkIn_中传递**ILockBytes**或**IStream**接口。 
  

