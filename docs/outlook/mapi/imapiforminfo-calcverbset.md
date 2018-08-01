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
ms.openlocfilehash: 362afb1efeddeae72cc19256c377cb2c0f7ecba0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775409"
---
# <a name="imapiforminfocalcverbset"></a>IMAPIFormInfo::CalcVerbSet

  
  
**适用于**： Outlook 
  
到谓词窗体所使用的完整集合中返回的指针。
  
```cpp
HRESULT CalcVerbSet(
  ULONG ulFlags,
  LPMAPIVERBARRAY FAR * ppMAPIVerbArray
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]返回控制的字符串类型的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _ppMAPIVerbArray_
  
> [输出]指向包含窗体的谓词返回[SMAPIVerbArray](smapiverbarray.md)结构的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
## <a name="remarks"></a>说明

客户端应用程序调用**IMAPIFormInfo::CalcVerbSet**方法以获取指向由窗体的动作设置。 在**SMAPIVerbArray**结构中返回_ppMAPIVerbArray_参数中，返回动词顺序的索引号;每个动作索引是其**lVerb**成员中找到的。 客户端应用程序可以使用动词数组动态生成菜单、 隐藏或显示按钮，等等。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MFCOutput.cpp  <br/> |_OutputFormInfo  <br/> |MFCMAPI 编写窗体信息对象的调试输出时使用**IMAPIFormInfo::CalcVerbSet**方法。  <br/> |
   
## <a name="see-also"></a>另请参阅



[SMAPIVerbArray](smapiverbarray.md)
  
[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

