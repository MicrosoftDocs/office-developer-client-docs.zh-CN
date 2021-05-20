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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436799"
---
# <a name="validateparms"></a>ValidateParms

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
调用内部函数以检查客户端应用程序已传递给服务提供商的参数。 
  
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
  
> [in]通过枚举指定要验证的方法。 
    
 _第一_
  
> [in]指向堆栈上第一个参数的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 所有参数都有效。 
    
MAPI_E_CALL_FAILED 
  
> 其中一个或多个参数无效。
    
## <a name="remarks"></a>备注

在 MAPI 和服务提供商之间传递的参数被认为是正确的，并且只接受 [CheckParms 宏的调试](checkparms.md) 验证。 提供程序应检查客户端应用程序传入的所有参数，但客户端应假定 MAPI 和提供程序参数正确。 使用 **HR_FAILED** 宏测试返回值。 
  
 **ValidateParms** 的调用方式不同，具体取决于调用代码是 C 还是 C++。 C++ 将隐式参数（称为  _this）_ 传递给每个方法调用，该方法调用在 C 中变为显式，并且是对象的地址。 第一个参数  _eMethod_ 是一个从正在验证的接口和方法所创建枚举器，并告知期望在堆栈上找到的参数。 对于 C 和 C++，第二个参数不同。 在 C++ 中，它称为  _First_，它是要验证的方法的第一个参数。 C 语言的第二个参数  _ppThis_ 是方法的第一个参数的地址，该方法始终是对象指针。 在这两种情况下，第二个参数都提供方法参数列表开头的地址，并基于  _eMethod_ 向下移动堆栈并验证参数。 
  
实现常见接口（如 **IMAPITable** 和 **IMAPIProp）** 的提供程序应始终使用 **ValidateParms** 函数检查参数，以确保所有提供程序之间的一致性。 为要在适当使用某些复杂参数类型定义了其他参数验证函数。 有关以下函数，请参阅参考主题： 
  
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
    
继承的方法使用的参数验证与继承自的接口相同。 例如 **，IMessage** 和 **IMAPIProp** 的参数检查应该相同。 
  
## <a name="see-also"></a>另请参阅



[UlValidateParms](ulvalidateparms.md)

