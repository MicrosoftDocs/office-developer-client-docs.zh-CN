---
title: IMAPIPropOpenProperty
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.OpenProperty
api_type:
- COM
ms.assetid: e400e6cc-4e36-43fc-9304-b688a0a7fd77
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7bf1d6912e44319c36e288cd3870218e8c4e45ff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319808"
---
# <a name="imapipropopenproperty"></a>IMAPIProp::OpenProperty

**适用于**：Outlook 2013 | Outlook 2016 
  
返回指向可用于访问属性的接口的指针。
  
```cpp
HRESULT OpenProperty(
  ULONG ulPropTag,
  LPCIID lpiid,
  ULONG ulInterfaceOptions,
  ULONG ulFlags,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a>参数

 _ulPropTag_
  
> 实时要访问的属性的属性标记。 标识符和类型都必须包含在属性标记中。
    
 _lpiid_
  
> 实时指向要用于访问属性的接口的标识符的指针。 _lpiid_参数不能为**null**。
    
 _ulInterfaceOptions_
  
> 实时与_lpiid_参数标识的接口相关的数据。 
    
 _ulFlags_
  
> 实时控制对属性的访问权限的标志的位掩码。 可以设置以下标志:
    
MAPI_CREATE 
  
> 如果该属性不存在, 则应创建该属性。 如果属性存在, 则应放弃属性的当前值。 当呼叫者设置 MAPI_CREATE 标志时, 它还应设置 MAPI_MODIFY 标志。
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenProperty**成功返回, 这可能是在将对象完全提供给调用程序之前。 如果该对象不可用, 则进行后续的对象调用可能会引发错误。 
    
MAPI_MODIFY 
  
> 在以下情况下, MAPI_MODIFY 是必需的:
    
  - 打开 stream 属性 (如**IID_IStream**) 进行修改时。
    
  - 打开嵌入的邮件附件 (如使用**IID_IMessage**打开的[PR_ATTACH_DATA_OBJ](pidtagattachdataobject-canonical-property.md)时), 以对其进行修改。
    
 _lppUnk_
  
> 排除指向要用于属性访问的请求接口的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回请求的接口指针。
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 此属性不支持所请求的接口。
    
MAPI_E_NO_ACCESS 
  
> 调用方权限不足, 无法访问属性。
    
MAPI_E_NO_SUPPORT 
  
> 对象无法通过请求的接口提供对此属性的访问。
    
MAPI_E_NOT_FOUND 
  
> 请求的属性不存在, 并且未在_ulFlags_参数中设置 MAPI_CREATE。 
    
MAPI_E_INVALID_PARAMETER 
  
> 将标记中的属性类型设置为 PT_UNSPECIFIED。
    
## <a name="remarks"></a>注解

**IMAPIProp:: OpenProperty**方法通过特定接口提供对属性的访问。 **OpenProperty**是[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPIProp:: SetProps](imapiprop-setprops.md)方法的替代方法。 当**GetProps**或**SetProps**由于属性太大或太复杂而失败时, 请调用**OpenProperty**。 **OpenProperty**通常用于访问 PT_OBJECT 类型的属性。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要访问邮件附件, 请使用不同的接口标识符打开**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性, 具体取决于附件的类型。 下表介绍了如何为不同类型的附件调用**OpenProperty** : 
  
|**附件的类型**|**要使用的接口标识符**|
|:-----|:-----|
|Binary  <br/> |IID_IStream  <br/> |
|字符串  <br/> |IID_IStream  <br/> |
|消息  <br/> |IID_IMessage  <br/> |
|OLE 2。0  <br/> |IID_IStreamDocfile  <br/> |
   
**IStreamDocfile**是基于 OLE 2.0 复合文件的[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口的导数。 **IStreamDocfile**是访问 OLE 2.0 附件的最佳选择, 因为它涉及最少量的开销。 您可以将 IID_IStreamDocFile 用于包含通过[IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx)接口提供的结构化存储区中存储的数据的那些属性。 
  
有关如何将**OpenProperty**与附件一起使用的详细信息, 请参阅**PR_ATTACH_DATA_OBJ**属性和[打开附件](opening-an-attachment.md)。
  
请勿使用您收到的**IStream**指针调用其[Seek](https://msdn.microsoft.com/library/aa380043%28v=VS.85%29.aspx)或[SetSize](https://msdn.microsoft.com/library/aa380044%28v=VS.85%29.aspx)方法, 除非您使用零位置或大小变量。 此外, 不要依赖于从**Seek**调用返回的_plibNewPosition_输出参数的值。 
  
如果调用**OpenProperty**以使用**IStream**接口访问属性, 请仅使用该接口对其进行更改。 请勿尝试使用任何其他[IMAPIProp: IUnknown](imapipropiunknown.md)方法 (如**SetProps**或[IMAPIProp::D eleteprops](imapiprop-deleteprops.md)) 更新属性。 
  
请勿尝试多次打开**OpenProperty**属性。 结果是不确定的, 因为它们可能因提供程序而异。 
  
如果需要修改要打开的属性, 请设置 MAPI_MODIFY 标志。 如果您不确定对象是否支持该属性, 但您认为它是应的, 请设置 MAPI_CREATE 和 MAPI_MODIFY 标志。 只要设置了 MAPI_CREATE, 也必须设置 MAPI_MODIFY。
  
您负责将_lppUnk_参数中返回的接口指针 recasting 为一个适用于_lpiid_参数中指定的接口的接口指针。 完成后, 还必须使用返回的指针调用其[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法。 
  
有时, 在_ulFlags_参数中设置标志不足以指示对所需属性的访问类型。 您可以在_ulInterfaceOptions_参数中放置其他数据 (如 flags)。 此数据依赖于接口。 某些接口 (如**IStream**) 使用它, 而其他接口则不使用。 例如, 当您打开要使用**IStream**修改的属性时, 除了 MAPI_MODIFY 之外, 还应在_ulInterfaceOptions_参数中设置 STGM_WRITE 标志。 使用[IMAPITable](imapitableiunknown.md)接口打开表格时, 可以将_ulInterfaceOptions_设置为 MAPI_UNICODE, 以指示是否保留字符串属性的表中的列应采用 UNICODE 格式。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|StreamEditor  <br/> |CStreamEditor:: ReadTextStreamFromProperty  <br/> |MFCMAPI 使用**IMAPIProp:: OpenProperty**方法检索大型 text 和 binary 属性的 stream 接口。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [HrIStorageFromStream](hristoragefromstream.md) 
- [IMAPIProp::DeleteProps](imapiprop-deleteprops.md) 
- [IMAPIProp::GetProps](imapiprop-getprops.md)
- [IMAPIProp::SetProps](imapiprop-setprops.md)
- [IMAPISupport::IStorageFromStream](imapisupport-istoragefromstream.md)
- [IMAPITable : IUnknown](imapitableiunknown.md)
- [IMAPIProp : IUnknown](imapipropiunknown.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
- [打开附件](opening-an-attachment.md)

