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
  
> 实时由_lppPropNames_参数指向的属性名称的计数。 如果_lppPropNames_为 NULL, 则_cPropNames_参数必须为0。 
    
 _lppPropNames_
  
> 实时指向属性名称数组的指针或 NULL。 向所有属性集中的所有属性名称传递 NULL 请求属性标识符, 该对象包含的所有属性集的信息。 如果在_ulFlags_参数中设置了 MAPI_CREATE 标志, 则_lppPropNames_参数不得为 NULL。 
    
 _ulFlags_
  
> 实时指示应如何返回属性标识符的标志的位掩码。 可以设置以下标志:
    
MAPI_CREATE 
  
> 如果尚未将属性标识符分配给由_lppPropNames_指向的属性名称数组中包含的一个或多个名称, 则将该标识符分配给它。 此标志在内部注册名称到标识符的映射表中的标识符。
    
 _lppPropTags_
  
> 排除指向包含现有或新分配的属性标识符的属性标记数组的指针的指针。 此数组中的属性标记的属性类型设置为**PT_UNSPECIFIED**。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回指定属性名称的标识符。
    
MAPI_E_NO_SUPPORT 
  
> 对象不支持命名属性。
    
MAPI_E_NOT_ENOUGH_MEMORY 
  
> 内存不足, 无法检索标识符。
    
MAPI_E_TOO_BIG 
  
> 无法执行操作, 因为它需要返回过多的属性标记。
    
MAPI_W_ERRORS_RETURNED 
  
> 调用全部成功, 但无法返回一个或多个属性标识符。 每个不可用属性的相应属性类型都设置为**PT_ERROR** , 其标识符设置为零。 返回此警告时, 请将呼叫处理为成功。 若要测试此警告, 请使用**HR_FAILED**宏。 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

**IMAPIProp:: GetIDsFromNames**方法检索包含一个或多个命名属性的属性标识符的属性标记的数组。 可以调用**IMAPIProp:: GetIDsFromNames**以执行以下操作: 
  
- 为新名称创建标识符。
    
- 检索特定名称的标识符。
    
- 检索对象映射中包含的所有命名属性的标识符。
    
命名属性通常由邮件存储提供程序用于文件夹和邮件。 其他对象 (如邮件用户和配置文件节) 可能不支持将名称与属性标识符关联, 并且可能会从**GetIDsFromNames**返回 MAPI_E_NO_SUPPORT。
  
如果有错误返回特定名称的标识符, **GetIDsFromNames**将返回 MAPI_W_ERRORS_RETURNED, 并将属性标记数组项中对应于名称的属性类型设置为**PT_ERROR** , 并将标识符设置为零。 
  
名称到标识符的映射由对象的**PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) 属性表示。 **PR_MAPPING_SIGNATURE**包含一个[MAPIUID](mapiuid.md)结构, 该结构指示负责对象的服务提供程序。 如果两个对象的**PR_MAPPING_SIGNATURE**属性相同, 则假定这些对象使用相同的名称与标识符的映射。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您传递回由_lppPropNames_参数指向的属性标记数组中的标识符必须位于0x8000 到0xFFFE 范围中。 此数组中的条目必须与通过_lppPropNames_指向的属性名称数组中传递的名称的顺序相同。 
  
如果支持容器上的命名属性, 请对容器中的所有对象使用相同的名称与标识符映射 (即, 不要对邮件存储区中的每个文件夹或文件夹中的每封邮件使用不同的映射)。
  
## <a name="notes-to-callers"></a>给调用方的说明

由于_lppPropTags_指向的属性标记数组中返回的标识符的属性类型设置为**PT_UNSPECIFIED**, 因此您必须调用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法以检索准确的类型。 
  
如果使用命名属性移动或复制对象, 并且源对象和目标对象的映射签名与它们的**PR_MAPPING_SIGNATURE**属性的值所表示的映射签名不同, 则必须在这些操作过程中保留这些名称。 若要保留属性名称, 请调整相应的属性标识符, 使其与目标对象的名称与标识符的映射相匹配。 
  
某些对象的属性标识符的数目与它们可以命名的数目有一定的限制。 如果对**GetIDsFromNames**的调用导致超出此限制, 则此方法将返回 MAPI_E_TOO_BIG。 在这种情况下, 按标识符进行查询。 
  
有关详细信息, 请参阅[MAPI 命名属性](mapi-named-properties.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|SingleMAPIPropListCtrl  <br/> |CSingleMAPIPropListCtrl:: FindAllNamedPropsUsed  <br/> |MFCMAPI 使用**IMAPIProp:: GetIDsFromNames**方法获取已映射的所有命名属性的属性标记。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)
  
[IMAPIProp::SetProps](imapiprop-setprops.md)
  
[MAPINAMEID](mapinameid.md)
  
[MAPIUID](mapiuid.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 命名属性](mapi-named-properties.md)
  
[使用宏进行错误处理](using-macros-for-error-handling.md)

