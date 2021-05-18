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
  
返回一个指向可用于访问属性的接口的指针。
  
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
  
> [in]要访问的属性的属性标记。 标识符和类型都必须包含在属性标记中。
    
 _lpiid_
  
> [in]指向用于访问属性的接口的标识符的指针。 _lpiid_ 参数不能为 **null**。
    
 _ulInterfaceOptions_
  
> [in]与  _lpiid_ 参数标识的接口相关的数据。 
    
 _ulFlags_
  
> [in]控制对属性的访问的标志的位掩码。 可以设置以下标志：
    
MAPI_CREATE 
  
> 如果该属性不存在，应创建该属性。 如果该属性存在，应放弃该属性的当前值。 当调用方设置 MAPI_CREATE 标志时，它还应设置 MAPI_MODIFY 标志。
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **OpenProperty** 在对象完全可供调用方使用之前成功返回。 如果该对象不可用，则进行后续对象调用可能会引发错误。 
    
MAPI_MODIFY 
  
> MAPI_MODIFY需要执行以下操作：
    
  - 打开流属性（如 **IID_IStream）** 以修改它。
    
  - 打开嵌入的邮件附件（如使用 PR_ATTACH_DATA_OBJ[](pidtagattachdataobject-canonical-property.md)打开IID_IMessage）进行修改。 
    
 _lppUnk_
  
> [out]指向要用于属性访问的请求接口的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回请求的接口指针。
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 此属性不支持请求的接口。
    
MAPI_E_NO_ACCESS 
  
> 调用方没有足够的权限来访问属性。
    
MAPI_E_NO_SUPPORT 
  
> 对象无法通过请求的接口提供对此属性的访问。
    
MAPI_E_NOT_FOUND 
  
> 请求的属性不存在，并且MAPI_CREATE  _ulFlags_ 参数中未设置。 
    
MAPI_E_INVALID_PARAMETER 
  
> 标记中的属性类型设置为 PT_UNSPECIFIED。
    
## <a name="remarks"></a>备注

**IMAPIProp：：OpenProperty** 方法通过特定接口提供对属性的访问。 **OpenProperty** 是 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 [IMAPIProp：：SetProps 方法的替代方法](imapiprop-setprops.md) 。 当 **GetProps 或** **SetProps** 因属性过大或过于复杂而失败时，调用 **OpenProperty**。 **OpenProperty** 通常用于访问类型为 PT_OBJECT。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要访问邮件附件，请PR_ATTACH_DATA_OBJ (不同的接口标识符打开[PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性，具体取决于附件的类型。  下表介绍如何为不同类型的附件调用 **OpenProperty：** 
  
|**附件类型**|**使用的接口标识符**|
|:-----|:-----|
|二进制  <br/> |IID_IStream  <br/> |
|String  <br/> |IID_IStream  <br/> |
|邮件  <br/> |IID_IMessage  <br/> |
|OLE 2.0  <br/> |IID_IStreamDocfile  <br/> |
   
**IStreamDocfile** 是基于 OLE 2.0 复合文件的 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 接口的派生对象。 **IStreamDocfile** 是访问 OLE 2.0 附件的最佳选择，因为它涉及的开销最少。 您可以为IID_IStreamDocFile [IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx) 接口提供的结构化存储中存储的数据的属性使用数据。 
  
若要详细了解如何将 **OpenProperty** 与附件一同使用，请参阅 **PR_ATTACH_DATA_OBJ** 属性和 [打开附件](opening-an-attachment.md)。
  
除非使用零位置或大小变量，否则请勿使用收到的 **IStream** 指针调用 [其 Seek](https://msdn.microsoft.com/library/aa380043%28v=VS.85%29.aspx) 或 [SetSize](https://msdn.microsoft.com/library/aa380044%28v=VS.85%29.aspx) 方法。 此外，不要依赖于从 Seek 调用返回  _的 plibNewPosition_ 输出 **参数** 的值。 
  
如果调用 **OpenProperty** 以使用 **IStream** 接口访问属性，请仅使用该接口进行更改。 不要尝试使用任何其他 [IMAPIProp ： IUnknown](imapipropiunknown.md) 方法（如 **SetProps** 或 [IMAPIProp：:D eleteProps）更新属性](imapiprop-deleteprops.md)。 
  
不要尝试用 **OpenProperty** 多次打开属性。 结果未定义，因为它们因提供程序而异。 
  
如果需要修改要打开的属性，请设置MAPI_MODIFY标记。 如果不确定对象是否支持 属性，但认为应该支持，请设置 MAPI_CREATE 和 MAPI_MODIFY 标志。 设置MAPI_CREATE时，MAPI_MODIFY必须同时设置该设置。
  
您负责将  _lppUnk_ 参数中返回的接口指针重新广播到适用于  _lpiid_ 参数中指定的接口的接口指针。 完成操作后，还必须使用返回的指针调用其 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) 方法。 
  
有时，在  _ulFlags_ 参数中设置标志不足以指示对所需属性的访问类型。 可以将其他数据（如标志）放在  _ulInterfaceOptions_ 参数中。 此数据依赖于接口。 某些接口 (**IStream**) ，而其他接口则不使用。 例如，当您打开要通过 **IStream** 修改的属性时，除 MAPI_MODIFY 之外，在  _ulInterfaceOptions_ 参数中设置 STGM_WRITE 标记。 使用 [IMAPITable](imapitableiunknown.md) 接口打开表时，可以将  _ulInterfaceOptions_ 设置为 MAPI_UNICODE 以指示包含字符串属性的表中的列是否应该采用 Unicode 格式。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|StreamEditor.cpp  <br/> |CStreamEditor：：ReadTextStreamFromProperty  <br/> |MFCMAPI 使用 **IMAPIProp：：OpenProperty** 方法检索大文本和二进制属性的流接口。  <br/> |
   
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

