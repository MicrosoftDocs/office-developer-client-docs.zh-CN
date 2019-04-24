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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348921"
---
# <a name="opentnefstream"></a>OpenTnefStream

**适用于**：Outlook 2013 | Outlook 2016 
  
由传输提供程序调用, 以启动 MAPI 传输中性封装格式 (TNEF) 会话。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Tnef  <br/> |
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
  
> 实时传递一个支持对象或传递为 NULL。 
    
_lpStream_
  
> 实时指向存储流对象 OLE **IStream**接口的指针, 该接口为 TNEF 流消息提供源或目标。 
    
_lpszStreamName_
  
> 实时一个指向 TNEF 对象使用的数据流的名称的指针。 如果调用方在其对**OpenTnefStream**的调用中设置了 TNEF_ENCODE 标志 ( _ulFlags_参数), 则_lpszName_参数必须指定一个非 null 的指针, 该指针指向包含为文件命名有效的任何字符的非 null 字符串。 MAPI 不允许包含字符 "["、"]" 或 ":" 的字符串名称, 即使文件系统允许使用它们。 为_lpszName_传递的字符串的大小不得超过 MAX_PATH 的值, 即包含路径名的字符串的最大长度。 
    
_ulFlags_
  
> 实时用于指示函数模式的标志的位掩码。 可以设置以下标志:
    
TNEF_BEST_DATA 
  
> 所有可能的属性都将映射到其下层属性, 但当由于转换为下层属性而导致数据丢失时, 该属性也会在 encapsulations 中进行编码。 请注意, 这将导致 TNEF 流中的信息重复。 如果未指定其他模式, 则 TNEF_BEST_DATA 为默认值。 
    
TNEF_COMPATIBILITY 
  
> 提供与旧客户端应用程序的向后兼容性。 使用此标志编码的 TNEF 流会将所有可能的属性映射到其相应的低级别属性。 此模式还会导致低级别客户端所需的某些属性的默认设置。 
    
  > [!CAUTION]
  > 此标志已过时, 不应使用。 
  
TNEF_DECODE 
  
> 以只读访问权限打开指定流中的 TNEF 对象。 如果传输提供程序想要函数初始化对象以进行后续解码, 则必须设置此标志。
    
TNEF_ENCODE 
  
> 将打开指定流上的 TNEF 对象以进行读/写权限。 如果传输提供程序希望函数为后续编码初始化对象, 则必须设置此标志。
    
TNEF_PURE 
  
> 将所有属性编码为 MAPI 封装块。 因此, "纯" TNEF 文件将由 attMAPIProps、attAttachment、attRenddata 和 attRecipTable 组成。 此模式非常适合在不需要向后兼容性时使用。
    
_lpMessage_
  
> 实时指向邮件对象的指针, 作为带有附件的已解码邮件的目标或带有附件的已编码邮件的来源。 目标邮件的任何属性可能会被编码邮件的属性覆盖。
    
_wKey_
  
> 实时TNEF 对象用来将附件与邮件文本中插入的文本标记相匹配的搜索关键字。 此值在邮件中应是相对唯一的。
    
_lppTNEF_
  
> 排除指向新 TNEF 对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

**OpenTnefStream**函数创建的 TNEF 对象随后调用 OLE 方法**IUnknown:: AddRef**为 support 对象、stream 对象和 message 对象添加引用。 传输提供程序可以释放对所有三个对象的引用, 并对 OLE 方法**IUnknown::** 在 TNEF 对象上进行一次调用。 
  
**OpenTnefStream**分配并初始化 tnef 对象**ITnef**接口, 以便提供程序在将 MAPI 邮件**IMessage**接口编码为 TNEF 流邮件时使用。 此外, 函数还可以设置对象, 以便提供程序在后续调用[ITnef:: ExtractProps](itnef-extractprops.md)将 TNEF 流邮件解码为 MAPI 邮件时使用该对象。 若要释放 TNEF 对象并关闭会话, 传输提供程序必须在对象上调用继承的**IUnknown:: Release**方法。 
  
此函数是 TNEF 访问的原始入口点, 已由[OpenTnefStreamEx](opentnefstreamex.md)替换, 但仍用于兼容已使用 TNEF 的。 
  
## <a name="see-also"></a>另请参阅

- [IMAPISupport : IUnknown](imapisupportiunknown.md)
- [IXPProvider::TransportLogon](ixpprovider-transportlogon.md)

