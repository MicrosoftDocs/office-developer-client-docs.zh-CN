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
ms.openlocfilehash: f2669f703827924493387c4beac0b64b25672860
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329573"
---
# <a name="validateparms"></a>ValidateParms

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
调用内部函数以检查客户端应用程序已传递给服务提供程序的参数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapival.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
   
```cpp
HRESULT ValidateParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a>参数

 _eMethod_
  
> 实时通过枚举指定要验证的方法。 
    
 _第一_
  
> 实时指向堆栈上第一个参数的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 所有参数都有效。 
    
MAPI_E_CALL_FAILED 
  
> 一个或多个参数无效。
    
## <a name="remarks"></a>注解

假定在 MAPI 和服务提供程序之间传递的参数是正确的, 并且仅使用[CheckParms](checkparms.md)宏进行调试验证。 提供程序应检查客户端应用程序传入的所有参数, 但客户端应假定 MAPI 和提供程序参数正确。 使用**HR_FAILED**宏可测试返回值。 
  
 根据调用代码是 c 还是 c + +, 将以不同的方式调用**ValidateParms** 。 c + + 将一个称为_this_的隐式参数传递给每个方法调用, 这将在 C 中变为显式, 而是对象的地址。 第一个参数_eMethod_是从要验证的接口和方法中获取的枚举器, 它指示要在堆栈上查找的参数。 第二个参数对于 C 和 c + + 是不同的。 在 c + + 中,_首先_调用它, 并且是要验证的方法的第一个参数。 C 语言_ppThis_的第二个参数是方法的第一个参数的地址, 它始终是对象指针。 在这两种情况下, 第二个参数都提供方法的参数列表开头的地址, 基于_eMethod_, 在堆栈中向下移动并验证参数。 
  
实现通用接口 (如**IMAPITable**和**IMAPIProp** ) 的提供程序应始终使用**ValidateParms**函数检查参数, 以确保所有提供程序的一致性。 已为某些复杂参数类型定义了其他参数验证函数, 这些函数将根据需要改用。 请参阅以下函数的参考主题: 
  
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
    
继承的方法使用与它们继承的接口相同的参数验证。 例如, **IMessage**和**IMAPIProp**的参数检查应相同。 
  
## <a name="see-also"></a>另请参阅



[UlValidateParms](ulvalidateparms.md)

