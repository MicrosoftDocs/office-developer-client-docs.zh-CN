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
ms.openlocfilehash: 656e5c5532edfc6c791ca30aa30f4c4d96847295
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775530"
---
# <a name="imapipropopenproperty"></a>IMAPIProp::OpenProperty

**适用于**： Outlook 
  
返回可用于访问属性的接口的指针。
  
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
  
> [in]要访问的属性属性标记。 必须属性标记中包含的标识符和类型。
    
 _lpiid_
  
> [in]指向要用于访问属性的接口的标识符的指针。 _Lpiid_参数不为**null**。
    
 _ulInterfaceOptions_
  
> [in]与_lpiid_参数标识的界面相关的数据。 
    
 _ulFlags_
  
> [in]控制在对属性的访问的标志的位掩码。 可以设置以下标志：
    
MAPI_CREATE 
  
> 如果该属性不存在，应创建它。 如果属性不存在，则应丢弃属性的当前值。 当呼叫者设置 MAPI_CREATE 标志时，它也应设置 MAPI_MODIFY 标志。
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenProperty**返回成功，原因可能是之前的对象是对呼叫者完全可用。 如果对象不可用，则进行后续对象呼叫会引发错误。 
    
MAPI_MODIFY 
  
> MAPI_MODIFY 是在这些情况下所必需的：
    
  - 当打开一个流属性，如**IID_IStream**，对其进行修改。
    
  - 当打开嵌入的邮件附件，如[PR_ATTACH_DATA_OBJ](pidtagattachdataobject-canonical-property.md)打开**IID_IMessage**，对其进行修改。
    
 _lppUnk_
  
> [输出]指向要用于属性访问所请求的接口的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回请求的接口指针。
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 此属性不支持所请求的接口。
    
MAPI_E_NO_ACCESS 
  
> 呼叫者具有权限不足，无法访问的属性。
    
MAPI_E_NO_SUPPORT 
  
> 对象不能提供给请求的接口通过此属性的访问。
    
MAPI_E_NOT_FOUND 
  
> 请求的属性不存在，MAPI_CREATE _ulFlags_参数中未设置。 
    
MAPI_E_INVALID_PARAMETER 
  
> 属性类型标记中的设置为 PT_UNSPECIFIED。
    
## <a name="remarks"></a>说明

**IMAPIProp::OpenProperty**方法提供了访问通过特定接口属性。 **OpenProperty**是[IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPIProp::SetProps](imapiprop-setprops.md)方法的替代方法。 当**GetProps**或**SetProps**失败由于属性是太长或太复杂时，调用**OpenProperty**。 **OpenProperty**通常用于访问类型 PT_OBJECT 的属性。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要访问邮件附件，打开具有不同的接口标识符，具体取决于附件的类型的**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性。 下表介绍如何为不同类型的附件调用**OpenProperty** : 
  
|**附件的类型**|**要使用的接口标识符**|
|:-----|:-----|
|二进制数  <br/> |IID_IStream  <br/> |
|字符串  <br/> |IID_IStream  <br/> |
|Message  <br/> |IID_IMessage  <br/> |
|OLE 2.0  <br/> |IID_IStreamDocfile  <br/> |
   
**IStreamDocfile**是基于 OLE 2.0 复合文件的[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)接口导数。 **IStreamDocfile**是用于访问 OLE 2.0 附件，因为它涉及开销最少的最佳选择。 包含可通过[IStorage](http://msdn.microsoft.com/en-us/library/aa380015%28VS.85%29.aspx)接口的结构化存储中存储的数据的这些属性，可以使用 IID_IStreamDocFile。 
  
有关如何使用**OpenProperty**带附件的详细信息，请参阅**PR_ATTACH_DATA_OBJ**属性，然后[打开附件](opening-an-attachment.md)。
  
不要使用**IStream**指针接收调用其[Seek](http://msdn.microsoft.com/en-us/library/aa380043%28v=VS.85%29.aspx)或[SetSize](http://msdn.microsoft.com/en-us/library/aa380044%28v=VS.85%29.aspx)方法，除非您使用零位置或大小变量。 此外，不要依赖_plibNewPosition_输出参数从**Seek**调用返回的值。 
  
如果您调用**OpenProperty**访问**IStream**接口的属性，请使用该接口仅对其进行更改。 请务尝试使用任何其他更新属性[IMAPIProp: IUnknown](imapipropiunknown.md)方法，如**SetProps**或[IMAPIProp::DeleteProps](imapiprop-deleteprops.md)。 
  
不要尝试使用**OpenProperty**多次打开一个属性。 结果不确定的因为它们可能会商的变化。 
  
如果您需要修改以打开属性，请设置 MAPI_MODIFY 标志。 如果您不能确定对象是否支持属性，但是您认为应，设置 MAPI_CREATE 和 MAPI_MODIFY 标志。 只要 MAPI_CREATE 设置，还必须设置 MAPI_MODIFY。
  
您负责改革到一个适合于_lpiid_参数中指定的接口返回_lppUnk_参数中的接口指针。 您还必须使用返回的指针完与其调用其[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法。 
  
有时_ulFlags_参数中设置标志没有足够可用于指示对所需的属性的访问类型。 您可以将其他数据，如标志，放在_ulInterfaceOptions_参数。 此数据是相关的接口。 一些接口 （如**IStream**) 使用它，而且有些则没有。 例如，当打开**IStream**与要修改的属性时，除了 MAPI_MODIFY _ulInterfaceOptions_参数中设置 STGM_WRITE 标志。 通过使用[IMAPITable](imapitableiunknown.md)界面打开一个表，可以将_ulInterfaceOptions_设为 MAPI_UNICODE 以指示是否保留字符串属性表中的列应为 Unicode 格式。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|StreamEditor.cpp  <br/> |CStreamEditor::ReadTextStreamFromProperty  <br/> |MFCMAPI 使用**IMAPIProp::OpenProperty**方法检索到大型文本和二进制属性流接口。  <br/> |
   
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

