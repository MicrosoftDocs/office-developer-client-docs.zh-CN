---
title: IMAPISupportGetSvcConfigSupportObj
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.GetSvcConfigSupportObj
api_type:
- COM
ms.assetid: 56c3bdae-a3a8-4334-b6d2-a89c6820d72e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6de0fed4df9d23e67c3520ffb019a961b890f988
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411307"
---
# <a name="imapisupportgetsvcconfigsupportobj"></a>IMAPISupport::GetSvcConfigSupportObj

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建邮件服务支持对象。
  
```cpp
HRESULT GetSvcConfigSupportObj(
  ULONG ulFlags,
  LPMAPISUP FAR * lppSvcSupport
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _lppSvcSupport_
  
> 排除指向新邮件服务支持对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功创建了配置支持对象。
    
## <a name="remarks"></a>说明

**IMAPISupport:: GetSvcConfigSupportObj**方法是为所有支持对象实现的。 服务提供程序调用**GetSvcConfigSupportObj**以创建要传递给邮件服务入口点函数的配置支持对象。 
  
邮件服务入口点函数基于[MSGSERVICEENTRY](msgserviceentry.md)原型, 并由[IMsgServiceAdmin](imsgserviceadminiunknown.md)接口的方法调用。 邮件服务入口点函数允许邮件服务在配置文件发生更改时配置自身或执行其他操作。 邮件服务入口点函数可通过显示属性表或通过传递给[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法的属性值数组来支持配置更改。 
  
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)
  
[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)
  
[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

