---
title: IMAPIPropGetIDsFromNames
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.GetIDsFromNames
api_type:
- COM
ms.assetid: e3f501a4-a8ee-43d7-bd83-c94e7980c398
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 28880b818bc80e31cae0c695d4aac92eb9555cac
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433582"
---
# <a name="imapipropgetidsfromnames"></a>IMAPIProp::GetIDsFromNames

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供与一个或多个属性名称对应的属性标识符。
  
```cpp
HRESULT GetIDsFromNames(
  ULONG cPropNames,
  LPMAPINAMEID FAR * lppPropNames,
  ULONG ulFlags,
  LPSPropTagArray FAR * lppPropTags
);
```

## <a name="parameters"></a>参数

 _cPropNames_
  
> [in]  _lppPropNames_ 参数指向的属性名称计数。 如果  _lppPropNames_ 为 NULL，  _则 cPropNames_ 参数必须为 0。 
    
 _lppPropNames_
  
> [in]指向属性名称数组或 NULL 的指针。 传递 NULL 请求对象具有相关信息的所有属性集内所有属性名称的属性标识符。 如果在 _ulFlags_ 参数中设置了 MAPI_CREATE 标志，则 _lppPropNames_ 参数不能为 NULL。 
    
 _ulFlags_
  
> [in]指示属性标识符的返回方法的标志的位掩码。 可以设置以下标志：
    
MAPI_CREATE 
  
> 将属性标识符（如果尚未分配）分配给  _lppPropNames_ 指向的属性名称数组中包含的一个或多个名称。 此标志在内部注册名称到标识符映射表中的标识符。
    
 _lppPropTags_
  
> [out]指向包含现有或新分配的属性标识符的属性标记数组的指针的指针。 此数组中属性标记的属性类型设置为 PT_UNSPECIFIED **。**
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回指定属性名称的标识符。
    
MAPI_E_NO_SUPPORT 
  
> 对象不支持命名属性。
    
MAPI_E_NOT_ENOUGH_MEMORY 
  
> 没有足够的内存来检索标识符。
    
MAPI_E_TOO_BIG 
  
> 由于需要返回过多的属性标记，因此无法执行该操作。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用整体成功，但无法返回一个或多个属性标识符。 每个不可用属性的相应属性类型都设置为 **PT_ERROR其标识符** 设置为零。 返回此警告时，请成功处理调用。 若要测试此警告，请使用 **HR_FAILED** 宏。 请参阅 [使用宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPIProp：：GetIDsFromNames** 方法检索一组属性标记，这些标记包含一个或多个命名属性的属性标识符。 **可以调用 IMAPIProp：：GetIDsFromNames** 以执行以下操作： 
  
- 创建新名称的标识符。
    
- 检索特定名称的标识符。
    
- 检索对象映射中包含的所有命名属性的标识符。
    
命名属性通常由邮件存储提供程序用于文件夹和邮件。 其他对象（如邮件用户和配置文件部分）可能不支持名称与属性标识符的关联，并且可能从 **GetIDsFromNames MAPI_E_NO_SUPPORT返回值**。
  
如果存在返回特定名称的标识符的错误 **，GetIDsFromNames** 将返回 MAPI_W_ERRORS_RETURNED并设置属性标记数组条目中的属性类型，该属性类型对应于 **PT_ERROR，** 标识符为零。 
  
名称到标识符映射由对象的 PR_MAPPING_SIGNATURE ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) 表示。  **PR_MAPPING_SIGNATURE** 包含 [一个 MAPIUID](mapiuid.md) 结构，该结构指示负责对象的服务提供商。 如果 **PR_MAPPING_SIGNATURE** 对象的属性相同，则假定这些对象使用相同的名称到标识符映射。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

在  _lppPropNames_ 参数指向的属性标记数组中传递回的标识符必须0x8000范围0xFFFE。 此数组中的条目的顺序必须与  _lppPropNames_ 指向的属性名称数组中传递的名称的顺序相同。 
  
如果支持容器上的命名属性，请对容器 (中所有对象使用相同的名称到标识符映射，即不要对邮件存储中每个文件夹或文件夹) 中的每个邮件使用不同的映射。
  
## <a name="notes-to-callers"></a>给调用方的说明

由于  _lppPropTags_ 指向的属性标记数组中返回的标识符的属性类型设置为 **PT_UNSPECIFIED，** 因此您必须调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法来检索准确类型。 
  
如果移动或复制具有命名属性的对象，并且源对象和目标对象具有不同的映射签名，如其 **PR_MAPPING_SIGNATURE** 属性的值所指示，则必须在这些操作过程中保留名称。 若要保留属性名称，请调整相应的属性标识符，以匹配目标对象的名称到标识符映射。 
  
某些对象对可命名的属性标识符的数量有限制。 如果调用 **GetIDsFromNames** 导致超出此限制，则该方法返回 MAPI_E_TOO_BIG。 在这种情况下，按标识符查询。 
  
有关详细信息，请参阅 [MAPI Named Properties](mapi-named-properties.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|SingleMAPIPropListCtrl.cpp  <br/> |CSingleMAPIPropListCtrl：：FindAllNamedPropsUsed  <br/> |MFCMAPI 使用 **IMAPIProp：：GetIDsFromNames** 方法获取已映射的所有命名属性的属性标记。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)
  
[IMAPIProp::SetProps](imapiprop-setprops.md)
  
[MAPINAMEID](mapinameid.md)
  
[MAPIUID](mapiuid.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 命名属性](mapi-named-properties.md)
  
[使用宏处理错误](using-macros-for-error-handling.md)

