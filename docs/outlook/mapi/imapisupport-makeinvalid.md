---
title: IMAPISupportMakeInvalid
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.MakeInvalid
api_type:
- COM
ms.assetid: c630ecaf-b19c-4991-9779-e13cc492c755
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 84e87f8a8d3c419afc4b86e200aeaba57e6a85f1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427491"
---
# <a name="imapisupportmakeinvalid"></a>IMAPISupport::MakeInvalid

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将对象标记为不可用。
  
```cpp
HRESULT MakeInvalid(
ULONG ulFlags,
LPVOID lpObject,
ULONG ulRefCount,
ULONG cMethods
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 保留;必须为零。
    
 _lpObject_
  
> [in]指向要失效的对象的指针。 对象的接口必须派生自 **IUnknown**。
    
 _ulRefCount_
  
> [in]对象的当前引用计数。
    
 _cMethods_
  
> [in]对象 vtable 中的方法计数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 对象已成功标记为不可用。
    
## <a name="remarks"></a>备注

**IMAPISupport：：MakeInvalid** 方法针对所有支持对象实现。 要失效的对象必须派生自 **IUnknown** 接口或派生自 **IUnknown** 的接口。
  
 **MakeInvalid** 将对象的 vtable 替换为 **IUnknown：：AddRef** 和 **IUnknown：：Release** 方法按预期执行的大小类似的存根 vtable，从而将对象标记为不可用。 但是，任何其他方法都失败，返回值 MAPI_E_INVALID_OBJECT。 
  
## <a name="notes-to-callers"></a>给调用方的说明

服务提供程序和邮件服务通常在关闭时调用 **MakeInvalid。** 但是，随时都可以调用 **MakeInvalid。** 例如，如果客户端释放对象而不释放其一些子对象，您可以立即调用 **MakeInvalid** 以释放这些子对象。 
  
您必须拥有您尝试失效的对象。 其 vtable 中必须至少有 16 个字节长且至少有三个方法。 
  
可以调用 **MakeInvalid，** 然后执行通常在对象发布期间完成的任何关闭工作，例如放弃关联的数据结构。 支持对象的代码无需保存在内存中，因为 MAPI 通过调用 [MAPIFreeBuffer](mapifreebuffer.md) 释放内存，然后释放对象。 您可以释放资源，调用 **MakeInvalid**，然后忽略失效的对象。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

