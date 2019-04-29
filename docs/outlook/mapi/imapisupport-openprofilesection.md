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
  
打开当前配置文件的一个部分, 并返回一个[IProfSect](iprofsectimapiprop.md)指针以供进一步访问。 
  
```cpp
HRESULT OpenProfileSection(
LPMAPIUID lpUid,
ULONG ulFlags,
LPPROFSECT FAR * lppProfileObj
);
```

## <a name="parameters"></a>参数

 _lpUid_
  
> 实时指向标识要打开的配置文件部分的[MAPIUID](mapiuid.md)结构的指针。 为_lpUid_参数传递 NULL 将打开调用者的配置文件部分。 
    
 _ulFlags_
  
> 实时用于控制如何打开 profile 节的标志的位掩码。 可以设置以下标志:
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenProfileSection**在配置文件节对调用方完全可访问之前成功返回。 如果 profile 节不可访问, 则进行后续的对象调用可能会导致错误。 
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 对象以只读方式打开, 并且在假定已授予读/写权限时, 调用方不应这样做。 
    
 _lppProfileObj_
  
> 排除指向打开的配置文件部分的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开 "配置文件" 部分。
    
MAPI_E_NO_ACCESS 
  
> 试图修改只读配置文件部分或访问呼叫者具有的权限不足的对象。
    
MAPI_E_NOT_FOUND 
  
> 没有与_lpEntryID_中传递的条目标识符相关联的配置文件部分。
    
MAPI_E_UNKNOWN_FLAGS 
  
> 使用了保留或不受支持的标志, 因此操作未完成。
    
## <a name="remarks"></a>说明

**IMAPISupport:: OpenProfileSection**方法是为所有支持对象实现的。 服务提供程序和邮件服务调用**OpenProfileSection**以打开配置文件部分, 并检索指向其**IProfSect**接口实现的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **OpenProfileSection**将配置文件节以只读方式打开, 除非您在_ulFlags_参数中设置了 MAPI_MODIFY 标志, 并且您的权限已足够。 设置此标志不能保证读/写权限;您授予的权限取决于您的访问级别和对象。 
  
如果**OpenProfileSection**尝试以只读方式打开不存在的配置文件节, 则它将返回 MAPI_E_NOT_FOUND。 如果**OpenProfileSection**尝试以读/写方式打开不存在的配置文件节, 则它会创建 "配置文件" 部分并返回**IProfSect**指针。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIUID](mapiuid.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

