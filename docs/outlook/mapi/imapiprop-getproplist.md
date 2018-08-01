---
title: IMAPIPropGetPropList
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.GetPropList
api_type:
- COM
ms.assetid: 0069c223-32bb-4286-b763-39fd45dc263b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0457007334ad8cc69dade3abd5859dd0d5f7af7f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775521"
---
# <a name="imapipropgetproplist"></a>IMAPIProp::GetPropList

  
  
**适用于**： Outlook 
  
返回所有属性的属性标记。 
  
```cpp
HRESULT GetPropList(
  ULONG ulFlags,
  LPSPropTagArray FAR * lppPropTagArray
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志的控件中返回的属性标记的字符串的格式。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _lppPropTagArray_
  
> [输出]指向包含对象的属性的所有标记属性标记数组的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回所有属性标记。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
## <a name="remarks"></a>说明

**IMAPIProp::GetPropList**方法检索当前对象支持的每个属性的属性标记。 如果对象当前不支持任何属性， **GetPropList**将返回与设置为 0 的**cValues**成员属性标记数组。 
  
返回由**GetPropList**属性的范围而有所不同商的。 某些服务提供商不包括呼叫者不具有访问这些属性。 所有提供程序返回类型**PT_OBJECT**的属性。
  
如果对象不支持 Unicode， **GetPropList**将返回 MAPI_E_BAD_CHARWIDTH，即使没有为对象定义的字符串属性。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

远程传输提供程序就完全等同于指定此处实现**GetPropList** 。 没有任何特殊的问题。 您的实现应，当然，返回相同的属性所支持的[IMAPIProp::GetProps](imapiprop-getprops.md)方法的列表。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放所指的_lppPropTagArray_属性标记数组。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |GetPropsNULL  <br/> |MFCMAPI 使用**IMAPIProp::GetPropList**方法来获取要传递给**GetProps**属性列表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

