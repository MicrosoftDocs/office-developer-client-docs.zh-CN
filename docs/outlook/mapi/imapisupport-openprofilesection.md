---
title: IMAPISupportOpenProfileSection
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.OpenProfileSection
api_type:
- COM
ms.assetid: cd1fa994-9531-46c4-94e5-505e7f90b884
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2f45028219f0f5f4cc881db3bc512626b3ad2f4c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775641"
---
# <a name="imapisupportopenprofilesection"></a>IMAPISupport::OpenProfileSection

  
  
**适用于**： Outlook 
  
打开当前配置文件的节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。 
  
```cpp
HRESULT OpenProfileSection(
LPMAPIUID lpUid,
ULONG ulFlags,
LPPROFSECT FAR * lppProfileObj
);
```

## <a name="parameters"></a>参数

 _lpUid_
  
> [in]指向标识配置文件部分，要打开的[MAPIUID](mapiuid.md)结构的指针。 _LpUid_参数传递 NULL 将打开呼叫者的配置文件一节。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开配置文件部分。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenProfileSection**成功返回可能之前配置文件节是完全访问呼叫者。 如果配置文件部分不可访问，则进行后续对象呼叫会导致错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，以只读方式打开对象和呼叫者以为，读/写权限授予不起作用。 
    
 _lppProfileObj_
  
> [输出]指向打开配置文件部分的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开配置文件部分。
    
MAPI_E_NO_ACCESS 
  
> 尝试来修改只读的配置文件节或访问其呼叫者没有足够的权限的对象。
    
MAPI_E_NOT_FOUND 
  
> 没有与_lpEntryID_中传递的项标识符的配置文件一节。
    
MAPI_E_UNKNOWN_FLAGS 
  
> 使用保留或不受支持的标志，而且，因此，该操作未完成。
    
## <a name="remarks"></a>说明

对于所有支持对象实现**IMAPISupport::OpenProfileSection**方法。 服务提供商和消息服务调用**OpenProfileSection**以打开配置文件一节并检索指向其**IProfSect**接口实现。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **OpenProfileSection**打开配置文件部分作为只读的除非_ulFlags_参数中设置 MAPI_MODIFY 标记和您的权限就足够了。 设置此标志不保证读/写权限;您已被授予的权限取决于您的访问级别和对象。 
  
如果**OpenProfileSection**尝试打开以只读方式不存在配置文件一节，则将返回 MAPI_E_NOT_FOUND。 如果**OpenProfileSection**尝试打开以读/写不存在配置文件部分，它会创建配置文件部分，并返回**IProfSect**指针。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIUID](mapiuid.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

