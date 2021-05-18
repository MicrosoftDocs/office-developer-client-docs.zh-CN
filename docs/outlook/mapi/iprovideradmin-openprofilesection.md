---
title: IProviderAdminOpenProfileSection
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin.OpenProfileSection
api_type:
- COM
ms.assetid: b73cf770-8817-4a23-bd14-7b76fedef214
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b3ac1b2cf8335c5e0953fdcf61b2b5d466fbb724
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405658"
---
# <a name="iprovideradminopenprofilesection"></a>IProviderAdmin::OpenProfileSection

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从当前配置文件中打开配置文件部分，并返回 [IProfSect](iprofsectimapiprop.md) 指针以进一步访问。 
  
```cpp
HRESULT OpenProfileSection(
  LPMAPIUID lpUID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPPROFSECT FAR * lppProfSect
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> [in]指向 [MAPIUID](mapiuid.md) 结构的指针，其中包含要打开的配置文件节的唯一标识符。 客户端不得为  _lpUID_ 参数传递 NULL。 服务提供商可以传递 NULL，以在从邮件服务入口点函数调用时检索 **MAPIUID。** 
    
 _lpInterface_
  
> [in]指向接口标识符的 (IID) 表示用于访问配置文件节的接口。 传递 NULL 会导致返回的 **IProfSect** (配置文件) 接口。 
    
 _ulFlags_
  
> [in]控制配置文件节打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 启用 **OpenProfileSection** 以成功返回，可能在配置文件部分对调用方完全可用之前。 如果配置文件部分不可用，则后续调用它可能会引发错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，使用只读权限打开对象，调用方不应假定已授予读/写权限。 不允许客户端对配置文件的提供程序分区具有读/写权限。
    
MAPI_FORCE_ACCESS
  
> 允许访问所有配置文件节，甚至是单个服务提供商拥有的内容。
    
 _lppProfSect_
  
> [out]指向指向配置文件节的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开配置文件部分。
    
MAPI_E_NO_ACCESS 
  
> 试图修改只读配置文件节或访问用户权限不足的对象。
    
MAPI_E_NOT_FOUND 
  
> 请求的配置文件部分不存在。
    
## <a name="remarks"></a>备注

**IProviderAdmin：：OpenProfileSection** 方法打开配置文件部分，使呼叫者能够读取活动配置文件的信息，并可能向活动配置文件中写入信息。 
  
客户端无法使用 **OpenProfileSection** 方法打开属于提供程序的配置文件节。 
  
多个客户端或服务提供商可以同时打开具有只读权限的配置文件部分。 但是，当使用读/写权限打开配置文件节时，无论访问类型如何，都不得进行其他调用来打开该节。 如果使用只读权限打开配置文件节，则后续调用请求读/写权限将失败，MAPI_E_NO_ACCESS。 同样，如果分区以读/写权限打开，则后续调用请求只读权限也将失败。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果请求 **OpenProfileSection** 在 _ulFlags_ 中传递 MAPI_MODIFY，在 _lpUID_ 中传递未知 **MAPIUID，** 打开不存在的配置文件节，将创建配置文件节。 
  
如果请求 **OpenProfileSection** 打开具有只读权限的不存在的节，它将返回MAPI_E_NOT_FOUND。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> |OpenProfileSection  <br/> |MFCMAPI 使用 **IProviderAdmin：：OpenProfileSection** 方法从当前配置文件打开配置文件节。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIUID](mapiuid.md)
  
[IProviderAdmin : IUnknown](iprovideradminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

