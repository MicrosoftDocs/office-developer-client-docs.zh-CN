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
ms.openlocfilehash: 5247ca71c88b9c0f8591a732746a17204265741c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775529"
---
# <a name="imapipropgetidsfromnames"></a>IMAPIProp::GetIDsFromNames

  
  
**适用于**： Outlook 
  
提供属性的标识符的对应于一个或多个属性的名称。
  
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
  
> [in]_LppPropNames_参数指向的属性名称的计数。 如果_lppPropNames_为 NULL，则_cPropNames_参数必须为 0。 
    
 _lppPropNames_
  
> [in]一个指向数组属性名称，则为 NULL。 传递空请求中所有的属性集有关哪些对象有信息的所有属性名属性标识符。 如果_ulFlags_参数中设置 MAPI_CREATE 标志， _lppPropNames_参数必须不为 NULL。 
    
 _ulFlags_
  
> [in]位掩码的标志，指示应如何返回属性的标识符。 可以设置以下标记：
    
MAPI_CREATE 
  
> 指派属性标识符，如果一个具有尚未分配，到一个或多个所指的_lppPropNames_属性名称数组中包含的名称。 此标志内部注册名称为标识符映射表中的标识符。
    
 _lppPropTags_
  
> [输出]指向为数组属性标记包含现有或新分配属性标识符的指针的指针。 在此数组中的属性标记的属性类型设置为**PT_UNSPECIFIED**。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回的指定的属性名称的标识符。
    
MAPI_E_NO_SUPPORT 
  
> 对象不支持命名的属性。
    
MAPI_E_NOT_ENOUGH_MEMORY 
  
> 内存不足的可用以检索这些标识符。
    
MAPI_E_TOO_BIG 
  
> 无法执行操作，因为它要求要返回的属性标记太多。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用成功总体上讲，但不是会返回一个或多个属性标识符。 不可用的每个属性的相应属性类型设置为**PT_ERROR**和其标识符为零。 返回此警告时，处理为成功的呼叫。 若要测试此警告，请使用**HR_FAILED**宏。 请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

**IMAPIProp::GetIDsFromNames**方法检索保留一个或多个命名属性的属性标识符的属性标记的数组。 **IMAPIProp::GetIDsFromNames**可调用它以执行下列操作： 
  
- 创建新的名称标识符。
    
- 检索特定的名称标识符。
    
- 检索所有命名属性的对象映射中包含的标识符。
    
命名的属性通常使用文件夹和消息的消息存储提供程序。 其他对象，如消息用户和配置文件节，可能不支持的关联属性标识符的名称，并可能会返回 MAPI_E_NO_SUPPORT 来自**GetIDsFromNames**。
  
如果没有返回特定名称的标识符的错误， **GetIDsFromNames**返回 MAPI_W_ERRORS_RETURNED，并设置对应于**PT_ERROR**和标识符为零的名称属性标记数组项中的属性类型。 
  
由对象的**PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) 属性表示名称-标识符映射。 **PR_MAPPING_SIGNATURE**包含指示服务提供程序负责对象[MAPIUID](mapiuid.md)结构。 如果两个对象相同的**PR_MAPPING_SIGNATURE**属性，则假定这些对象使用相同的名称为标识符映射。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

返回_lppPropNames_参数指向该属性标记数组中传递的标识符必须 0x8000 到 0xFFFE 范围中。 该数组中的条目必须与属性名称数组中传递的名称相同的顺序指向通过_lppPropNames_。 
  
如果您支持的容器上的命名的属性，用于您的容器中的所有对象的相同的名称为标识符映射 （也就是说，不要都使用不同映射的每个文件夹中保存邮件或文件夹中的每个邮件）。
  
## <a name="notes-to-callers"></a>给调用方的说明

由于所指的_lppPropTags_属性标记数组中返回标识符的属性类型设置为**PT_UNSPECIFIED**，，必须调用[IMAPIProp::SetProps](imapiprop-setprops.md)方法来检索准确的类型。 
  
如果您移动或复制对象命名属性，和源和目标对象具有不同映射签名由其**PR_MAPPING_SIGNATURE**属性的值，您必须在这些操作保留名称。 若要保留属性名称，请调整相应属性的标识符匹配的目标对象的名称为标识符映射。 
  
某些对象有他们可以命名属性标识符的数限制。 如果调用**GetIDsFromNames**导致超过此限制，则该方法返回 MAPI_E_TOO_BIG。 在这种情况下，查询的标识符。 
  
有关详细信息，请参阅[MAPI 命名属性](mapi-named-properties.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|SingleMAPIPropListCtrl.cpp  <br/> |CSingleMAPIPropListCtrl::FindAllNamedPropsUsed  <br/> |MFCMAPI 使用**IMAPIProp::GetIDsFromNames**方法获取属性标记为已被映射的所有命名属性。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)
  
[IMAPIProp::SetProps](imapiprop-setprops.md)
  
[MAPINAMEID](mapinameid.md)
  
[MAPIUID](mapiuid.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 命名属性](mapi-named-properties.md)
  
[使用宏进行错误处理](using-macros-for-error-handling.md)

