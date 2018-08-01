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
ms.openlocfilehash: 276a2bd84156e9b396df71f51130e6704ad7c7fb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776030"
---
# <a name="iprovideradminopenprofilesection"></a>IProviderAdmin::OpenProfileSection

  
  
**适用于**： Outlook 
  
从当前配置文件中打开配置文件一节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。 
  
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
  
> [in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要打开的配置文件节的唯一标识符。 客户端必须_lpUID_参数传递 NULL。 服务提供商可以传递 NULL 时从其消息服务入口点函数检索**MAPIUID** 。 
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问配置文件部分的接口的指针。 在配置文件部分的标准界面，(**IProfSect**) 返回结果传递 NULL。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开配置文件部分。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 使**OpenProfileSection**返回成功，可能之前在配置文件部分，对呼叫者完全可用。 如果配置文件部分不可用，进行后续呼叫到它会引发错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，对象打开具有只读权限，并以为，读/写权限授予不起作用呼叫者。 客户端不允许提供程序的配置文件的分区的读/写权限。
    
MAPI_FORCE_ACCESS
  
> 允许对所有配置文件节，即使他们拥有单独的服务提供程序的访问。
    
 _lppProfSect_
  
> [输出]指向配置文件部分的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开配置文件部分。
    
MAPI_E_NO_ACCESS 
  
> 尝试来修改只读的配置文件节或访问其用户没有足够的权限的对象。
    
MAPI_E_NOT_FOUND 
  
> 请求的配置文件节不存在。
    
## <a name="remarks"></a>说明

**IProviderAdmin::OpenProfileSection**方法将打开配置文件部分，使呼叫者读取信息和可能在当前配置文件中写入信息。 
  
客户端无法打开使用**OpenProfileSection**方法属于提供程序的配置文件部分。 
  
多个客户端或服务提供商可以同时打开配置文件部分具有只读权限。 但是，具有读/写权限打开配置文件部分时，可以不进行任何其他呼叫以打开部分，而不考虑的访问类型。 如果具有只读权限打开配置文件一节，以请求读/写权限的后续调用将失败并 MAPI_E_NO_ACCESS。 同样，如果部分具有读/写权限打开，也将失败的后续调用以请求只读权限。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果您请求的**OpenProfileSection**打开不存在配置文件一节中_ulFlags_传递 MAPI_MODIFY，并将创建未知的**MAPIUID** _lpUID_，配置文件部分中。 
  
如果您请求**OpenProfileSection**具有只读权限打开不存在的节，则将返回 MAPI_E_NOT_FOUND。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> |OpenProfileSection  <br/> |MFCMAPI 使用**IProviderAdmin::OpenProfileSection**方法从当前配置文件中打开配置文件一节。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIUID](mapiuid.md)
  
[IProviderAdmin : IUnknown](iprovideradminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

