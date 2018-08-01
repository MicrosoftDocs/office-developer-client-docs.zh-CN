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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a73c87f172b4c97379bb9cd117679d3947c188af
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775622"
---
# <a name="imapisupportistoragefromstream"></a>IMAPISupport::IStorageFromStream

  
  
**适用于**： Outlook 
  
实现的存储对象访问的流。
  
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
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问由_lpUnkIn_指向流的接口的指针。 有有效的下列值： IID_IStream、 IID_ILockBytes，或**为空**，指示是否应使用[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)接口访问流。 
    
 _ulFlags_
  
> [in]位掩码的标志控制如何存储对象是相对于 stream 对象创建的。 默认情况下存储创建具有只读访问权限和流开始，在存储中的位置为零。 可以设置以下标志：
    
STGSTRM_CREATE 
  
> 应为 stream 对象创建新的存储对象。
    
STGSTRM_CURRENT 
  
> 存储对象应在当前位置的 stream 的开始。
    
STGSTRM_MODIFY 
  
> 呼叫者应具有对返回的存储对象的读/写权限。
    
STGSTRM_RESET 
  
> 存储对象应开始位置为零。
    
 _lppStorageOut_
  
> [输出]指向存储对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建的存储对象。
    
## <a name="remarks"></a>说明

**IMAPISupport::IStorageFromStream**方法将执行所有服务提供商支持对象。 服务提供商调用**IStorageFromStream**可创建用于打开特定属性的存储对象。 [IStorage](http://msdn.microsoft.com/en-us/library/aa380015%28VS.85%29.aspx)接口自己实现服务提供商不需要调用**IStorageFromStream**。 
  
时释放存储，由**IStorageFromStream**创建的存储对象将调用的流[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)方法来增加其引用计数，然后递减计数。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当您对象之一的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法调用与**IStorage**接口打开属性时，请执行以下任务： 
  
1. 打开 stream 对象的属性的读/写权限。
    
2. 内部将属性流标记为存储对象。
    
3. 调用**IStorageFromStream**生成的存储对象。 
    
4. 返回到此存储对象的指针。
    
如果使用的存储对象的附加接口实现，创建包装存储对象的对象和实现更高级别的[IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)方法。 
  
不允许打开与**IStream**接口，如果**IStorage**与创建它的属性。 相反，不允许打开与**IStorage**接口，如果**IStream**与创建它的属性。 
  
有一个例外，它是可以接受使用**IStreamDocfile**接口 stream 从一个容器到另一个存储对象，但必须**OpenProperty**方法_中传递 IID_IStreamDocfile 接口标识符 lpInterface_参数。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

