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
ms.openlocfilehash: f089fa2c608fb9fcb7deba2e061c5cf5886aa02f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414786"
---
# <a name="imapipropgetproplist"></a>IMAPIProp::GetPropList

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回所有属性的属性标记。 
  
```cpp
HRESULT GetPropList(
  ULONG ulFlags,
  LPSPropTagArray FAR * lppPropTagArray
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时标志的位掩码, 用于控制返回的属性标记中的字符串的格式。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _lppPropTagArray_
  
> 排除指向包含对象所有属性的标记的属性标记数组的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回所有属性标记。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
## <a name="remarks"></a>说明

**IMAPIProp:: GetPropList**方法检索对象当前支持的每个属性的属性标记。 如果该对象当前不支持任何属性, 则**GetPropList**将返回**cValues**成员设置为0的属性标记数组。 
  
**GetPropList**返回的属性范围因提供程序而异。 某些服务提供程序排除了呼叫者无权访问的那些属性。 所有提供程序都返回**PT_OBJECT**类型的属性。
  
如果该对象不支持 Unicode, **GetPropList**将返回 MAPI_E_BAD_CHARWIDTH, 即使没有为该对象定义任何字符串属性也是如此。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

远程传输提供程序完全按照此处指定的方式实现**GetPropList** 。 没有特殊的顾虑。 当然, 您的实现应返回与[IMAPIProp:: GetProps](imapiprop-getprops.md)方法支持的相同的属性列表。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放_lppPropTagArray_指向的属性标记数组。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions  <br/> |GetPropsNULL  <br/> |MFCMAPI 使用**IMAPIProp:: GetPropList**方法获取要传递给**GetProps**的属性列表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

