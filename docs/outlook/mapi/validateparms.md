---
title: ValidateParms
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ValidateParms
api_type:
- COM
ms.assetid: 3ede1a35-4acc-4b8f-a1bd-027f35798a37
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7b29eab30677dae7f720cecd9fde71e8bbbf752c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579716"
---
# <a name="validateparms"></a>ValidateParms

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
调用检查参数客户端应用程序已传递给服务提供商的内部函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapival.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |服务提供商  <br/> |
   
```cpp
HRESULT ValidateParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a>参数

 _eMethod_
  
> [in]通过枚举，指定要验证的方法。 
    
 _第一_
  
> [in]堆栈上第一个参数的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 所有参数都是有效的。 
    
MAPI_E_CALL_FAILED 
  
> 一个或多个参数不是有效的。
    
## <a name="remarks"></a>注解

MAPI 和服务之间传递参数提供程序将假定它们正确，且经过仅调试验证与[CheckParms](checkparms.md)宏。 提供程序应检查所有参数中传递的客户端应用程序，但客户端应假定 MAPI 和提供程序参数正确。 使用**HR_FAILED**宏来测试返回值。 
  
 **ValidateParms**称为根据调用的代码是否为 C 或 c + + 的不同。 C + + 将传递到每个方法的调用，以将成为显式 c，是对象的地址称为，_此_隐式参数。 第一个参数， _eMethod_，是从接口和正在进行验证的方法进行的枚举和告知所期望堆栈上找到的参数。 第二个参数是不同的 C 和 c + +。 在 c + + 调用_第一个_，并且正在进行验证的方法的第一个参数。 C 语言， _ppThis_，第二个参数是第一个参数方法它始终是对象指针的地址。 在这两种情况下，第二个参数提供的方法的参数列表的开头的地址和基于_eMethod_、 下移堆栈和验证参数。 
  
提供程序实现**IMAPIProp** **IMAPITable**等公共接口应始终检查以确保一致性使跨所有提供商使用**ValidateParms**函数的参数。 对于某些复杂参数类型，而是根据使用已定义其他参数验证函数。 请参阅以下功能的参考主题： 
  
- [FBadColumnSet](fbadcolumnset.md)
    
- [FBadEntryList](fbadentrylist.md)
    
- [FBadProp](fbadprop.md)
    
- [FBadProp](fbadprop.md)
    
- [FBadRestriction](fbadrestriction.md)
    
- [FBadRestriction](fbadrestriction.md)
    
- [FBadRglpszW](fbadrglpszw.md)
    
- [FBadRow](fbadrow.md)
    
- [FBadRowSet](fbadrowset.md)
    
- [FBadSortOrderSet](fbadsortorderset.md)
    
继承的方法将相同参数验证用作它们所继承的接口。 例如，检查**IMessage**和**IMAPIProp**参数应是相同。 
  
## <a name="see-also"></a>另请参阅



[UlValidateParms](ulvalidateparms.md)

