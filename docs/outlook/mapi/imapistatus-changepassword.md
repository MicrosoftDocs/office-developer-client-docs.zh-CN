---
title: IMAPIStatusChangePassword
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIStatus.ChangePassword
api_type:
- COM
ms.assetid: 0cd1026a-342d-4d05-91ed-d3decced5bf3
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e09a1de5f85edd7e352a090c573fed9ca16f017f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565548"
---
# <a name="imapistatuschangepassword"></a>IMAPIStatus::ChangePassword

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
不显示用户界面中修改服务提供商的密码。 （可选） 在服务提供商实现的状态对象支持使用此方法。
  
```cpp
HRESULT ChangePassword(
  LPSTR lpOldPass,
  LPSTR lpNewPass,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpOldPass_
  
> [in]指向旧密码的指针。
    
 _lpNewPass_
  
> [in]一个指向新密码。
    
 _ulFlags_
  
> [in]位掩码的标志的控制的密码的格式。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 密码是以 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，密码为 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 密码修改成功。
    
MAPI_E_NO_ACCESS 
  
> 由_lpOldPass_指向旧密码无效。 
    
MAPI_E_NO_SUPPORT 
  
> 状态对象不支持此操作，如缺少 STATUS_CHANGE_PASSWORD 标志状态对象的**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中所示。
    
## <a name="remarks"></a>注解

并非所有状态对象都支持**IMAPIStatus::ChangePassword**方法。 它只受服务提供商的要求客户端输入密码。 MAPI 实现的状态对象都未支持密码更改操作。 
  
 **ChangePassword**修改密码以编程方式，无需用户交互。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

远程传输提供程序指定此处实现**ChangePassword** 。 没有任何特殊的注意事项。 
  
## <a name="see-also"></a>另请参阅



[PidTagResourceMethods 规范属性](pidtagresourcemethods-canonical-property.md)
  
[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)

