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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416830"
---
# <a name="hristoragefromstream"></a>HrIStorageFromStream

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将 **IStorage 接口** 分层到 **IStream** 对象上。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向实现 **IStream 的 IUnknown** **对象的指针**。 
    
 _lpInterface_
  
> [in]指向流对象的 IID (接口) 指针。 可以在  _lpInterface_ 参数中传递以下任何值：NULL、IID_IStream 或 IID_ILockBytes。 在  _lpInterface_ 中传递 NULL 与传递空IID_IStream。 
    
 _ulFlags_
  
> [in]控制存储对象相对于流的创建方式的标志的位掩码。 默认设置为 STGSTRM_RESET，这将为存储对象提供只读访问权限，并启动该对象，位置为流零。 以下标志可以任意组合进行设置，除非已指出：
    
STGSTRM_CREATE 
  
> 为流对象创建新的存储对象。 如果设置了此标志，则STGSTRM_RESET设置此标志。 
    
STGSTRM_CURRENT 
  
> 在流的当前位置开始存储。 如果设置了此标志，则STGSTRM_RESET设置此标志。 
    
STGSTRM_MODIFY 
  
> 允许调用服务提供商写入返回的存储。 如果设置了此标志，则STGSTRM_RESET设置此标志。 
    
STGSTRM_RESET 
  
> 从零位置开始存储。 如果设置了任何其他标志，则不能设置此标志。 
    
 _lppStorageOut_
  
> [out]指向返回的 **IStorage 对象的指针** 的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

邮件存储提供程序使用附件的 **IStorage** 接口支持 **HrIStorageFromStream** 函数。 存储提供程序必须实现 **IStream** 接口。 **HrIStorageFromStream** 为 **IStream** 对象提供 **IStorage** 接口。 可以传递 **ILockBytes** 或 _lpUnkIn_ 中的 **IStream** 接口。 
  

