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
ms.openlocfilehash: 52fd844954f41d5d09b5e78f7c23ff6f7469bb43
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776573"
---
# <a name="opentnefstreamex"></a>OpenTnefStreamEx

**适用于**： Outlook 
  
创建可用于编码或到使用 TNEF 数据流解码 message 对象由传输或网关和消息存储传输中性封装格式 (TNEF) 对象。 这是 TNEF 访问的入口点。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Tnef.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |传输提供程序  <br/> |
   
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
  
> [in]通过一个支持对象，或传入 NULL。 如果为空，则_lpAddressBook_参数应为非空。 
    
_lpStream_
  
> [in]指向存储 stream 对象，如提供源或目标 TNEF 流邮件 OLE **IStream**接口的指针。 
    
_lpszStreamName_
  
> [in]指针，指向 TNEF 对象使用的数据流的名称。 如果呼叫者具有**OpenTnefStream**其调用设置 TNEF_ENCODE 标志 （ _ulFlags_参数）， _lpszName_参数必须指定一个非空指向视为有效命名文件任何个字符组成的非空字符串。 MAPI 不允许包括字符的字符串名称"["，"]"，或":"，即使在文件系统允许其使用。 为_lpszName_参数传递的字符串的大小不能超过 MAX_PATH，包含路径名称的字符串的最大长度的值。 
    
_ulFlags_
  
> [in]用于指示该函数的模式的标志位掩码。 可以设置以下标志：
    
TNEF_BEST_DATA 
  
> 所有可能的属性映射到其下层属性，但存在由于转换到低级别属性可能的数据丢失时，请封装还编码的属性。 请注意，这将导致 TNEF 用于将 stream 中的重复信息。 如果未不指定任何其他模式，则 TNEF_BEST_DATA 是默认值。 
    
TNEF_COMPATIBILITY 
  
> 提供向后兼容的旧客户端应用程序。 TNEF 流编码使用此标志将所有可能的属性映射到其相应的向下级属性。 此模式也会导致下层客户端所需的某些属性的默认设置。 
    
  > [!CAUTION]
  > 此标志已过时，不应使用。 
  
TNEF_DECODE 
  
> 指示流上的 TNEF 对象打开具有只读访问权限。 传输提供程序必须设置此标志，如果函数初始化后续解码的对象。
    
TNEF_ENCODE 
  
> 指示流上的 TNEF 对象为读/写权限打开。 传输提供程序必须设置此标志，如果函数初始化后续编码的对象。
    
TNEF_PURE 
  
> 编码为的 MAPI 封装基块的所有属性。 因此，一个"纯"TNEF 文件组成，最属性 attMAPIProps、 attAttachment、 attRenddata 和 attRecipTable。 需要无向后兼容性时，此模式非常适合于使用。
    
_lpMessage_
  
> [in]邮件作为附件已解码的消息的目标或带附件的编码邮件的源对象的指针。 编码的邮件的属性时可以覆盖目标邮件的任何属性。
    
_wKeyVal_
  
> [in]TNEF 对象用于匹配附件消息文本中插入的文本标记搜索键。 此值应该消息是相对唯一。 
    
_lpAddressBook_
  
> [in]指向用于获取寻址信息项标识符的通讯簿对象的指针。 
    
_lppTNEF_
  
> [输出]为新的 TNEF 对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

**OpenTnefStreamEx**函数是[OpenTnefStream](opentnefstream.md)，TNEF 访问的原始入口点的建议的替代。 
  
更高版本创建**OpenTnefStreamEx**函数的 TNEF 对象调用 OLE 方法**IUnknown::AddRef**添加支持对象、 stream 对象中，和 message 对象的引用。 传输提供程序可以发布给 OLE 方法**IUnknown::Release** TNEF 对象上的单个调用进行的所有三个对象的引用。 
  
**OpenTnefStreamEx**分配并初始化 TNEF 对象的 MAPI 邮件编码到 TNEF 流邮件中使用的提供程序。 此外，此函数可以设置到 MAPI 邮件解码 TNEF 流消息后面对[ITnef::ExtractProps](itnef-extractprops.md)中使用的提供程序的对象。 若要释放 TNEF 对象和关闭会话，传输提供程序必须在对象上调用继承的**IUnknown::Release**方法。 
  
_WKeyVal_参数的基本值不能为零，不应**OpenTnefStreamEx**每次调用相同。 而是使用随机数基于从运行时库的随机数字生成器系统时间。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|File.cpp  <br/> |LoadFromTNEF  <br/> |MFCMAPI 使用**OpenTnefStreamEx**方法打开 TNEF 文件流，因此可能提取属性。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IMAPISupport : IUnknown](imapisupportiunknown.md)
- [IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

