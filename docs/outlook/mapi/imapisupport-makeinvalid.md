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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 595d5fdba28634b038838921102d3125135452a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775620"
---
# <a name="imapisupportmakeinvalid"></a>IMAPISupport::MakeInvalid

  
  
**适用于**： Outlook 
  
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
  
> [in]指向要失效的对象的指针。 必须从**iunknown 导出**派生的对象的接口。
    
 _ulRefCount_
  
> [in]对象的存在此参数引用计数。
    
 _cMethods_
  
> [in]中对象的 vtable 方法的计数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 对象已成功地标记为不可用。
    
## <a name="remarks"></a>说明

对于所有支持对象实现**IMAPISupport::MakeInvalid**方法。 要将失效的对象必须从**IUnknown**接口或派生自**IUnknown**接口派生。
  
 **MakeInvalid**对象的 vtable 替换存根 vtable 顺序的**IUnknown::AddRef**和**IUnknown::Release**方法执行预期的类似大小的标记为不可用对象。 但是，任何其他方法失败，返回值 MAPI_E_INVALID_OBJECT。 
  
## <a name="notes-to-callers"></a>给调用方的说明

服务提供商和消息服务通常在关闭时调用**MakeInvalid** 。 但是，可以随时调用**MakeInvalid** 。 例如，如果客户端版本不释放一些及其子对象的对象，则可以呼叫**MakeInvalid**立即以释放这些子对象。 
  
您必须拥有您尝试使失效的对象。 它必须是至少 16 个字节，而且必须在其 vtable 中的至少三种方法。 
  
您可以调用**MakeInvalid** ，然后执行任何关闭工作，如放弃关联的数据结构期间释放对象通常完成。 因为 MAPI 通过调用[MAPIFreeBuffer](mapifreebuffer.md)释放内存，然后释放对象，则不需要在内存中，保留代码以支持的对象。 您可以释放资源和呼叫**MakeInvalid**，然后忽略无效的对象。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

