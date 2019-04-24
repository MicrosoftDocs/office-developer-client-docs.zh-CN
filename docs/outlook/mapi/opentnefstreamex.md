---
title: OpenTnefStreamEx
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OpenTnefStreamEx
api_type:
- COM
ms.assetid: eb84c408-2d8b-453b-92f4-5fd8851b84ca
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 178ab67875d8fb442500dd412dbafe4403deee16
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348571"
---
# <a name="opentnefstreamex"></a>OpenTnefStreamEx

**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个传输中性封装格式 (TNEF) 对象, 该对象可用于将邮件对象编码或解码为 TNEF 数据流, 以供传输或网关和邮件存储使用。 这是 TNEF 访问的入口点。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Tnef  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |传输提供程序  <br/> |
   
```cpp
HRESULT OpenTnefStreamEx(
  LPVOID lpvSupport,
  LPSTREAM lpStream,
  LPSTR lpszStreamName,
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  WORD wKeyVal,
  LPADDRESSBOOK lpAddressBook,
  LPITNEF FAR * lppTNEF
);
```

## <a name="parameters"></a>参数

_lpvSupport_
  
> 实时传递一个支持对象或传递为 NULL。 如果为 null, 则_lpAddressBook_参数应为非 NULL。 
    
_lpStream_
  
> 实时指向存储流对象 (如 OLE **IStream**接口) 的指针, 该对象提供 TNEF 流消息的源或目标。 
    
_lpszStreamName_
  
> 实时一个指向 TNEF 对象使用的数据流的名称的指针。 如果调用方在其对**OpenTnefStream**的调用中设置了 TNEF_ENCODE 标志 ( _ulFlags_参数), 则_lpszName_参数必须指定一个非 null 的指针, 该指针指向包含为文件命名有效的任何字符的非 null 字符串。 MAPI 不允许包含字符 "["、"]" 或 ":" 的字符串名称, 即使文件系统允许使用它们。 为_lpszName_参数传递的字符串的大小不得超过 MAX_PATH 的值, 即包含路径名的字符串的最大长度。 
    
_ulFlags_
  
> 实时用于指示函数模式的标志的位掩码。 可以设置以下标志:
    
TNEF_BEST_DATA 
  
> 所有可能的属性都将映射到其下层属性, 但当由于转换为下层属性而导致数据丢失时, 该属性也会在 encapsulations 中进行编码。 请注意, 这将导致 TNEF 流中的信息重复。 如果未指定其他模式, 则 TNEF_BEST_DATA 为默认值。 
    
TNEF_COMPATIBILITY 
  
> 提供与旧客户端应用程序的向后兼容性。 使用此标志编码的 TNEF 流会将所有可能的属性映射到其相应的低级别属性。 此模式还会导致低级别客户端所需的某些属性的默认设置。 
    
  > [!CAUTION]
  > 此标志已过时, 不应使用。 
  
TNEF_DECODE 
  
> 以只读访问权限打开指定流中的 TNEF 对象。 如果函数要初始化对象以进行后续解码, 则传输提供程序必须设置此标志。
    
TNEF_ENCODE 
  
> 将打开指定流上的 TNEF 对象以进行读/写权限。 如果函数要为后续编码初始化对象, 则传输提供程序必须设置此标志。
    
TNEF_PURE 
  
> 将所有属性编码为 MAPI 封装块。 因此, "纯" TNEF 文件最多包含属性 attMAPIProps、attAttachment、attRenddata 和 attRecipTable。 此模式非常适合在不需要向后兼容性时使用。
    
_lpMessage_
  
> 实时指向邮件对象的指针, 作为带有附件的已解码邮件的目标或带有附件的已编码邮件的来源。 目标邮件的任何属性都可以由已编码邮件的属性覆盖。
    
_wKeyVal_
  
> 实时TNEF 对象用来将附件与邮件文本中插入的文本标记相匹配的搜索关键字。 此值在邮件中应是相对唯一的。 
    
_lpAddressBook_
  
> 实时指向用于获取条目标识符寻址信息的通讯簿对象的指针。 
    
_lppTNEF_
  
> 排除指向新 TNEF 对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

**OpenTnefStreamEx**函数是[OpenTnefStream](opentnefstream.md)的建议替换, 即 TNEF access 的原始入口点。 
  
**OpenTnefStreamEx**函数创建的 TNEF 对象随后调用 OLE 方法**IUnknown:: AddRef**为 support 对象、stream 对象和 message 对象添加引用。 传输提供程序可以释放对所有三个对象的引用, 并对 OLE 方法**IUnknown::** 在 TNEF 对象上进行一次调用。 
  
**OpenTnefStreamEx**为提供程序分配和初始化 tnef 对象, 以便在将 MAPI 邮件编码为 TNEF 流邮件时使用。 或者, 此函数可以设置对象, 以便提供程序在后续调用[ITnef:: ExtractProps](itnef-extractprops.md)将 TNEF 流邮件解码为 MAPI 邮件时使用该对象。 若要释放 TNEF 对象并关闭会话, 传输提供程序必须在对象上调用继承的**IUnknown:: Release**方法。 
  
_wKeyVal_参数的基值不得为零, 并且对于每个**OpenTnefStreamEx**调用不应相同。 相反, 请根据来自运行时库随机编号生成器的系统时间使用随机数字。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|文件 .cpp  <br/> |LoadFromTNEF  <br/> |MFCMAPI 使用**OpenTnefStreamEx**方法打开 TNEF 文件上的流, 以便可以提取属性。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IMAPISupport : IUnknown](imapisupportiunknown.md)
- [IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

