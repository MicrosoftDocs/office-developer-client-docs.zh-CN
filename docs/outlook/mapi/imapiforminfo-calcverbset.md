---
title: IMAPIFormInfoCalcVerbSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo.CalcVerbSet
api_type:
- COM
ms.assetid: 0170dc9d-dc72-48e2-a522-374f199b18ea
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: babff746af16d51ca154d049943f6be7e9fab589
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428779"
---
# <a name="imapiforminfocalcverbset"></a>IMAPIFormInfo::CalcVerbSet

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个指针, 指向表单使用的完整的一组谓词。
  
```cpp
HRESULT CalcVerbSet(
  ULONG ulFlags,
  LPMAPIVERBARRAY FAR * ppMAPIVerbArray
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于控制返回的字符串类型的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _ppMAPIVerbArray_
  
> 排除指向指向包含表单的谓词的返回[SMAPIVerbArray](smapiverbarray.md)结构的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
## <a name="remarks"></a>说明

客户端应用程序调用**IMAPIFormInfo:: CalcVerbSet**方法以获取指向表单使用的一组谓词的指针。 在_ppMAPIVerbArray_参数中返回的**SMAPIVerbArray**结构中, 按照索引号的顺序返回谓词;在其**lVerb**成员中找到每个动词的索引。 客户端应用程序可以使用谓词数组来动态构建菜单、隐藏或显示按钮, 等等。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MFCOutput  <br/> |_OutputFormInfo  <br/> |MFCMAPI 在为表单信息对象编写调试输出时使用**IMAPIFormInfo:: CalcVerbSet**方法。  <br/> |
   
## <a name="see-also"></a>另请参阅



[SMAPIVerbArray](smapiverbarray.md)
  
[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

