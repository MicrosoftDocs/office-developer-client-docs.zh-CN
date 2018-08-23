---
title: IMsgServiceAdminCopyMsgService
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.CopyMsgService
api_type:
- COM
ms.assetid: a13c6757-358f-421a-9a76-de7483501613
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 791dfe094aa0ff1aab656b56fbdf7d59e880b92e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593730"
---
# <a name="imsgserviceadmincopymsgservice"></a>IMsgServiceAdmin::CopyMsgService

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
将邮件服务复制到一个配置文件。 
  
```cpp
HRESULT CopyMsgService(
  LPMAPIUID lpUID,
  LPSTR lpszDisplayName,
  LPCIID lpInterfaceToCopy,
  LPCIID lpInterfaceDst,
  LPVOID lpObjectDst,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> [in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要复制的消息服务的唯一标识符。 
    
 _lpszDisplayName_
  
> [in]此参数已被弃用。 
    
 _lpInterfaceToCopy_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问要复制的消息服务的配置文件部分的接口的指针。 在正在使用的标准配置文件部分接口[IProfSect](iprofsectimapiprop.md)，结果传递 NULL。
    
 _lpInterfaceDst_
  
> [in]指向 IID 值，该值代表要用于访问_lpObjectDst_参数指向的对象的接口的指针。 在正在使用的会话接口[IMAPISession](imapisessioniunknown.md)，结果传递 NULL。 _LpInterfaceDst_参数还可以设置为 IID_IMsgServiceAdmin。 
    
 _lpObjectDst_
  
> [in]指向与会话或消息服务管理对象的指针的指针。 对象的类型应对应于_lpInterfaceDst_中传递的界面标识符。 有效对象的指针是 LPMAPISESSION 和 LPSERVICEADMIN。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何复制邮件服务。 可以设置以下标志：
    
SERVICE_UI_ALWAYS 
  
> 请求邮件服务始终显示配置属性表。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功复制邮件服务。
    
MAPI_E_NO_ACCESS 
  
> 邮件服务已配置文件中，并且不允许多个实例本身。
    
MAPI_E_NOT_FOUND 
  
> 指向_lpUID_ **MAPIUID**不引用现有消息服务。 
    
## <a name="remarks"></a>注解

**IMsgServiceAdmin::CopyMsgService**方法将消息服务复制到配置文件、 活动配置文件或另一个配置文件。 包含要复制的消息服务的配置文件和目标不具有的相同的配置文件，但也可以是。 
  
不用于复制操作调用消息服务的入口点函数。 复制的消息服务都有为其原始相同的配置设置。 若要更改这些设置，客户端应调用[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法。 
  
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)
  
[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

