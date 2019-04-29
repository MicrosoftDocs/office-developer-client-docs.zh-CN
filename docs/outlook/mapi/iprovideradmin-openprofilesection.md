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
  
从当前配置文件打开一个配置文件部分, 并返回一个[IProfSect](iprofsectimapiprop.md)指针以供进一步访问。 
  
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
  
> 实时指向[MAPIUID](mapiuid.md)结构的指针, 该结构包含要打开的配置文件部分的唯一标识符。 客户端不得为_lpUID_参数传递 NULL。 服务提供程序可以传递 NULL 以在其邮件服务入口点函数调用时检索**MAPIUID** 。 
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问配置文件部分的接口。 在要返回的配置文件节的标准接口 (**IProfSect**) 中传递 NULL 结果。 
    
 _ulFlags_
  
> 实时用于控制如何打开 profile 节的标志的位掩码。 可以设置以下标志:
    
MAPI_DEFERRED_ERRORS 
  
> 使**OpenProfileSection**能够成功返回, 这可能在配置文件部分完全可用于调用程序之前。 如果 "配置文件" 部分不可用, 则对其进行后续调用可能会引发错误。 
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 使用只读权限打开对象, 并且调用方不应在假定已授予读/写权限时才起作用。 不允许客户端对配置文件的提供程序部分执行读/写权限。
    
MAPI_FORCE_ACCESS
  
> 允许访问所有配置文件部分, 甚至包括各个服务提供商拥有的部分。
    
 _lppProfSect_
  
> 排除指向指向配置文件部分的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开 "配置文件" 部分。
    
MAPI_E_NO_ACCESS 
  
> 试图修改只读配置文件部分或访问用户具有的权限不足的对象。
    
MAPI_E_NOT_FOUND 
  
> 请求的配置文件部分不存在。
    
## <a name="remarks"></a>说明

**IProviderAdmin:: OpenProfileSection**方法打开一个配置文件部分, 使呼叫者能够从活动配置文件中读取信息, 也可能将信息写入到活动配置文件。 
  
客户端无法使用**OpenProfileSection**方法打开属于提供程序的配置文件部分。 
  
多个客户端或服务提供商可以同时打开具有只读权限的配置文件节。 但是, 当使用读/写权限打开配置文件节时, 不能进行任何其他调用来打开该节, 而不管 access 的类型如何。 如果使用只读权限打开配置文件部分, 则对请求读/写权限的后续调用将会失败, 并出现 MAPI_E_NO_ACCESS。 同样, 如果某个部分是以读/写权限打开的, 则对请求只读权限的后续调用也会失败。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果您通过在_ulFlags_中传递 MAPI_MODIFY 和_lpUID_中的未知**MAPIUID**来请求**OpenProfileSection**打开不存在的配置文件部分, 则将创建该配置文件部分。 
  
如果您请求**OpenProfileSection**打开一个具有只读权限的不存在的节, 则它将返回 MAPI_E_NOT_FOUND。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProfileFunctions  <br/> |OpenProfileSection  <br/> |MFCMAPI 使用**IProviderAdmin:: OpenProfileSection**方法从当前配置文件中打开配置文件节。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIUID](mapiuid.md)
  
[IProviderAdmin : IUnknown](iprovideradminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

