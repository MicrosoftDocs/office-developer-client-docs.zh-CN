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
  
> [in]指向 stream 对象的指针。
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问  _lpUnkIn_ 指向的流的接口。 以下任一值均有效：IID_IStream、IID_ILockBytes 或 **null，** 指示 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 接口应该用于访问流。 
    
 _ulFlags_
  
> [in]控制存储对象的创建方式（相对于流对象）的位掩码。 默认情况下，使用只读访问权限创建存储，并且流从存储中的位置零开始。 可以设置以下标志：
    
STGSTRM_CREATE 
  
> 应为流对象创建一个新的存储对象。
    
STGSTRM_CURRENT 
  
> 存储对象应从流的当前位置开始。
    
STGSTRM_MODIFY 
  
> 调用方应具有对返回的存储对象的读/写权限。
    
STGSTRM_RESET 
  
> 存储对象应从零位置开始。
    
 _lppStorageOut_
  
> [out]指向存储对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建存储对象。
    
## <a name="remarks"></a>备注

**IMAPISupport：：IStorageFromStream** 方法针对所有服务提供商支持对象实现。 服务提供商调用 **IStorageFromStream** 来创建用于打开特定属性的存储对象。 具有自己的 [IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx) 接口实现的服务提供商不需要调用 **IStorageFromStream**。 
  
**IStorageFromStream** 创建的存储对象调用流的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法来增加其引用计数，然后在释放存储时减量。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用其中一个对象 [的 IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法以使用 **IStorage** 接口打开属性时，请执行以下任务： 
  
1. 使用属性的读/写权限打开 stream 对象。
    
2. 在内部将属性流标记为存储对象。
    
3. 调用 **IStorageFromStream** 以生成存储对象。 
    
4. 返回指向此存储对象的指针。
    
如果实现使用存储对象的其他接口，请创建包装存储对象并实现更高级别的 [IUnknown：：QueryInterface 方法的对象](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 。 
  
如果属性是使用 **IStorage** 创建的，则不允许使用 **IStream** 接口打开该属性。 相反，如果属性是使用 IStream 创建的，则不允许使用 **IStorage** 接口 **打开它**。 
  
可以使用 **IStreamDocfile** 接口将存储对象从一个容器流式传输到另一个容器，但 IID_IStreamDocfile 接口标识符必须在 **OpenProperty** 方法的  _lpInterface_ 参数中传递。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

