---
title: IMAPISupportIStorageFromStream
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.IStorageFromStream
api_type:
- COM
ms.assetid: da9e8fdc-dfc5-4ecc-9f9b-b76921b92d7c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7200e7d226eb148fef094ab8540990644d2d4c99
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316585"
---
# <a name="imapisupportistoragefromstream"></a>IMAPISupport::IStorageFromStream

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
实现存储对象以访问流。
  
```cpp
HRESULT IStorageFromStream(
  LPUNKNOWN lpUnkIn,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPSTORAGE FAR * lppStorageOut
);
```

## <a name="parameters"></a>参数

 _lpUnkIn_
  
> 实时指向 stream 对象的指针。
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示用于访问由_lpUnkIn_指向的流的接口。 以下任何值都是有效的: IID_IStream、IID_ILockBytes 或**null**, 这表示[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口应用于访问流。 
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制存储对象相对于 stream 对象的创建方式。 默认情况下, 将创建具有只读访问权限的存储, 并且流在存储区中的位置0处开始。 可以设置以下标志:
    
STGSTRM_CREATE 
  
> 应为 stream 对象创建一个新的存储对象。
    
STGSTRM_CURRENT 
  
> 存储对象应从流的当前位置开始。
    
STGSTRM_MODIFY 
  
> 调用方应具有对返回的存储对象的读/写权限。
    
STGSTRM_RESET 
  
> 存储对象应在位置0处开始。
    
 _lppStorageOut_
  
> 排除指向指向存储对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建存储对象。
    
## <a name="remarks"></a>注解

**IMAPISupport:: IStorageFromStream**方法是为所有服务提供程序支持对象实现的。 服务提供程序调用**IStorageFromStream**以创建用于打开特定属性的存储对象。 拥有自己的[IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx)接口实现的服务提供程序无需调用**IStorageFromStream**。 
  
由**IStorageFromStream**创建的存储对象将调用 stream 的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法来增加其引用计数, 然后在释放存储时递减计数。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当调用其中一个对象的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以使用**IStorage**接口打开属性时, 请执行以下任务: 
  
1. 打开一个 stream 对象, 该对象具有对属性的读/写权限。
    
2. 在内部将属性 stream 标记为存储对象。
    
3. 调用**IStorageFromStream**以生成存储对象。 
    
4. 返回指向此存储对象的指针。
    
如果实现使用 storage 对象的其他接口, 请创建一个包装存储对象的对象, 并实现更高级别的[IUnknown:: QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)方法。 
  
如果使用**IStorage**创建属性, 则不允许使用**IStream**接口打开该属性。 相反, 如果属性是使用**IStream**创建的, 则不允许使用**IStorage**接口打开属性。 
  
有一个例外, 可以使用**IStreamDocfile**接口将存储对象从一个容器传输到另一个容器, 但必须在**OpenProperty**方法的 lpInterface 中传递 IID_IStreamDocfile 接口标识符。 __ 参数。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

