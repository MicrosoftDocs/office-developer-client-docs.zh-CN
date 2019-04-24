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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316658"
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
  
> 保留必须为零。
    
 _lpObject_
  
> 实时指向要无效的对象的指针。 对象的接口必须从**IUnknown**派生。
    
 _ulRefCount_
  
> 实时对象的当前引用计数。
    
 _cMethods_
  
> 实时对象的 vtable 中的方法数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功将该对象标记为不可用。
    
## <a name="remarks"></a>注解

**IMAPISupport:: MakeInvalid**方法是为所有支持对象实现的。 要使其失效的对象必须从**iunknown**接口或从**iunknown**派生的接口派生。
  
 **MakeInvalid**通过将对象的 vtable 替换为大小相同且**iunknown:: AddRef**和**IUnknown:: Release**方法按预期执行的存根 vtable, 将对象标记为不可用。 但是, 任何其他方法都将失败, 返回值 MAPI_E_INVALID_OBJECT。 
  
## <a name="notes-to-callers"></a>给调用方的说明

服务提供商和邮件服务通常会在关机时调用**MakeInvalid** 。 但是, 可以随时调用**MakeInvalid** 。 例如, 如果客户端释放对象而不释放它的一些子对象, 则可以立即调用**MakeInvalid**以释放这些子对象。 
  
您必须拥有试图使其无效的对象。 它的长度必须至少为16个字节, 并且在 vtable 中至少有三个方法。 
  
您可以调用**MakeInvalid** , 然后执行任何关闭工作 (如丢弃关联的数据结构), 这通常在对象的发布过程中完成。 支持该对象的代码不需要保留在内存中, 因为 MAPI 通过调用[MAPIFreeBuffer](mapifreebuffer.md)来释放内存, 然后释放该对象。 您可以释放资源, 调用**MakeInvalid**, 然后忽略无效的对象。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

