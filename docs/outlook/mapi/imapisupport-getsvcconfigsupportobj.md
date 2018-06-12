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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5d7e3e89f15b1bc08c7ce9faab0d0a6326300e70
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775609"
---
# <a name="imapisupportgetsvcconfigsupportobj"></a>IMAPISupport::GetSvcConfigSupportObj

  
  
**适用于**： Outlook 
  
创建一个邮件服务支持对象。
  
```cpp
HRESULT GetSvcConfigSupportObj(
  ULONG ulFlags,
  LPMAPISUP FAR * lppSvcSupport
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _lppSvcSupport_
  
> [输出]为指向新消息服务支持对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建配置支持对象。
    
## <a name="remarks"></a>备注

对于所有支持对象实现**IMAPISupport::GetSvcConfigSupportObj**方法。 服务提供商调用**GetSvcConfigSupportObj**创建配置支持对象以传递给消息服务入口点函数。 
  
消息服务入口点函数基于[MSGSERVICEENTRY](msgserviceentry.md)原型和[IMsgServiceAdmin](imsgserviceadminiunknown.md)接口方法调用。 消息服务入口点函数允许消息服务配置自己或更改配置文件时执行其他操作。 消息服务的入口点函数可支持配置更改，通过显示属性表或属性值数组传递给[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法。 
  
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin: IUnknown](imsgserviceadminiunknown.md)
  
[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)
  
[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)
  
[IProfAdmin: IUnknown](iprofadminiunknown.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

