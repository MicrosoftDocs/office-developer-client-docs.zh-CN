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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e7f13acc34a77b79057d32fd4049db7222dadf49
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411384"
---
# <a name="imapisupportopenprofilesection"></a>IMAPISupport::OpenProfileSection

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开当前配置文件的一部分并返回 [IProfSect](iprofsectimapiprop.md) 指针以进一步访问。 
  
```cpp
HRESULT OpenProfileSection(
LPMAPIUID lpUid,
ULONG ulFlags,
LPPROFSECT FAR * lppProfileObj
);
```

## <a name="parameters"></a>参数

 _lpUid_
  
> [in]指向标识要打开的配置文件节的 [MAPIUID](mapiuid.md) 结构的指针。 为  _lpUid_ 参数传递 NULL 将打开呼叫者的配置文件部分。 
    
 _ulFlags_
  
> [in]控制配置文件节打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **OpenProfileSection** 在调用方完全访问配置文件节之前成功返回。 如果配置文件节不可访问，则进行后续的对象调用可能会导致错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，对象以只读模式打开，并且调用方不应在已授予读/写权限的假设下工作。 
    
 _lppProfileObj_
  
> [out]指向指向打开的配置文件节的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开配置文件部分。
    
MAPI_E_NO_ACCESS 
  
> 尝试修改只读配置文件节或访问调用方权限不足的对象。
    
MAPI_E_NOT_FOUND 
  
> 没有与在  _lpEntryID_ 中传递的条目标识符相关联的配置文件节。
    
MAPI_E_UNKNOWN_FLAGS 
  
> 已使用保留或不受支持的标志，因此操作无法完成。
    
## <a name="remarks"></a>备注

**IMAPISupport：：OpenProfileSection** 方法针对所有支持对象实现。 服务提供程序和邮件服务调用 **OpenProfileSection** 以打开配置文件部分并检索指向其 **IProfSect 接口** 实现指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **OpenProfileSection** 以只读模式打开配置文件节，除非在  _ulFlags_ 参数中设置 MAPI_MODIFY 标志，并且您的权限已足够。 设置此标志并不能保证读/写权限;授予的权限取决于您的访问级别和对象。 
  
如果 **OpenProfileSection** 尝试以只读模式打开不存在的配置文件节，它将返回MAPI_E_NOT_FOUND。 如果 **OpenProfileSection** 尝试以读/写模式打开不存在的配置文件节，它将创建配置文件节并返回 **IProfSect** 指针。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIUID](mapiuid.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

