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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2c824b6b994bfb31b5e6ac7fed0eeae88c47cdba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410355"
---
# <a name="imapistatuschangepassword"></a>IMAPIStatus::ChangePassword

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
修改服务提供商的密码，而不显示用户界面。 此方法在服务提供商实现的状态对象中受支持（ 可选）。
  
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
  
> [in]指向新密码的指针。
    
 _ulFlags_
  
> [in]控制密码格式的标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 密码采用 Unicode 格式。 如果未MAPI_UNICODE，则密码采用 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 密码修改成功。
    
MAPI_E_NO_ACCESS 
  
> _lpOldPass_ 指向的旧密码无效。 
    
MAPI_E_NO_SUPPORT 
  
> status 对象不支持此操作，如状态对象的 PR_RESOURCE_METHODS ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)属性中缺少STATUS_CHANGE_PASSWORD 标志) 。
    
## <a name="remarks"></a>备注

并非所有状态对象都支持 **IMAPIStatus：：ChangePassword** 方法。 它仅受要求客户端输入密码的服务提供商支持。 MAPI 实现的所有状态对象都不支持密码更改操作。 
  
 **ChangePassword** 以编程方式修改密码，无需用户交互。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

远程传输提供程序实现 **此处指定的 ChangePassword。** 没有特别注意事项。 
  
## <a name="see-also"></a>另请参阅



[PidTagResourceMethods 规范属性](pidtagresourcemethods-canonical-property.md)
  
[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)

