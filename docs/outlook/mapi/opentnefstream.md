---
title: OpenTnefStream
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OpenTnefStream
api_type:
- COM
ms.assetid: 912d7799-53ce-42a7-9fbd-f9a6a3a56047
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 524b52026010b9a06d5822b48b7c04bbf90a113e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423956"
---
# <a name="opentnefstream"></a>OpenTnefStream

**适用于**：Outlook 2013 | Outlook 2016 
  
由传输提供程序调用，以启动 TNEF (MAPI 传输中性) 格式。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Tnef.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |传输提供程序  <br/> |
   
```cpp
HRESULT OpenTnefStream(
  LPVOID lpvSupport,
  LPSTREAM lpStream,
  LPSTR lpszStreamName, 
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  WORD wKey,
  LPITNEF FAR * lppTNEF
);
```

## <a name="parameters"></a>参数

_lpvSupport_
  
> [in]传递支持对象，或传递 NULL。 
    
_lpStream_
  
> [in]指向存储流对象 OLE **IStream** 接口的指针，该接口提供 TNEF 流消息的源或目标。 
    
_lpszStreamName_
  
> [in]指向 TNEF 对象使用的数据流名称的指针。 如果调用方在调用 **OpenTnefStream** 时设置了 TNEF_ENCODE 标志 ( _ulFlags_ 参数) ，_则 lpszName_ 参数必须指定一个非 null 指针，该字符串包含任何视为对命名文件有效的字符。 MAPI 不允许包括字符"["、"]"或"："的字符串名称，即使文件系统允许其使用。 为  _lpszName_ 传递的字符串的大小不能超过 MAX_PATH 的值，即包含路径名的字符串的最大长度。 
    
_ulFlags_
  
> [in]用于指示函数模式的标志的位掩码。 可以设置以下标志：
    
TNEF_BEST_DATA 
  
> 所有可能的属性都映射到其下层属性中，但是当由于转换为下层属性而可能丢失数据时，还会在封装中对该属性进行编码。 请注意，这可能会导致 TNEF 流中信息重复。 TNEF_BEST_DATA未指定其他模式，则此参数为默认值。 
    
TNEF_COMPATIBILITY 
  
> 提供与旧版客户端应用程序的向后兼容性。 使用此标志编码的 TNEF 流将所有可能的属性映射到其相应的下层属性。 此模式还会导致低级别客户端所需的某些属性的默认值。 
    
  > [!CAUTION]
  > 此标志已过时，不应使用。 
  
TNEF_DECODE 
  
> 通过只读访问打开指示流上的 TNEF 对象。 如果传输提供程序希望函数初始化对象以用于后续解码，则必须设置此标志。
    
TNEF_ENCODE 
  
> 为获得读/写权限，打开指示流上的 TNEF 对象。 如果传输提供程序希望函数初始化对象以用于后续编码，则必须设置此标志。
    
TNEF_PURE 
  
> 将所有属性编码到 MAPI 封装块中。 因此，"纯"TNEF 文件最多包含 attMAPIProps、attAttachment、attRenddata 和 attRecipTable。 此模式非常适合无需向后兼容性时使用。
    
_lpMessage_
  
> [in]指向邮件对象的指针，作为带附件的已解码邮件的目标或带附件的编码邮件的源。 已编码邮件的属性可能会覆盖目标邮件的任何属性。
    
_wKey_
  
> [in]TNEF 对象用于将附件与邮件文本中插入的文本标记相匹配的搜索键。 此值在邮件中应相对唯一。
    
_lppTNEF_
  
> [out]指向新 TNEF 对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

**OpenTnefStream** 函数创建的 TNEF 对象稍后会调用 OLE 方法 **IUnknown：：AddRef** 以添加对支持对象、流对象和 message 对象的引用。 传输提供程序可以释放对 TNEF 对象上 OLE 方法 **IUnknown：：Release** 的单个调用的所有三个对象的引用。 
  
**OpenTnefStream** 分配和初始化 TNEF 对象 **ITnef** 接口，供提供程序用于将 MAPI 消息 **IMessage** 接口编码为 TNEF 流消息。 或者，该函数可以设置提供程序的对象，以用于后续调用 [ITnef：：ExtractProps](itnef-extractprops.md) 以将 TNEF 流消息解码为 MAPI 消息。 若要释放 TNEF 对象并关闭会话，传输提供程序必须对该对象调用继承的 **IUnknown：：Release** 方法。 
  
此函数是 TNEF 访问的原始入口点，已被 [OpenTnefStreamEx](opentnefstreamex.md) 取代，但仍用于兼容已使用 TNEF 的项。 
  
## <a name="see-also"></a>另请参阅

- [IMAPISupport : IUnknown](imapisupportiunknown.md)
- [IXPProvider::TransportLogon](ixpprovider-transportlogon.md)

