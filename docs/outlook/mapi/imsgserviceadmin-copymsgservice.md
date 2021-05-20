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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 72b4ab1fec10b2e91c7609af6644a54d29ed5e02
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432119"
---
# <a name="imsgserviceadmincopymsgservice"></a>IMsgServiceAdmin::CopyMsgService

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件服务复制到配置文件中。 
  
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
  
> [in]指向 [MAPIUID](mapiuid.md) 结构的指针，其中包含要复制的邮件服务的唯一标识符。 
    
 _lpszDisplayName_
  
> [in]此参数已被弃用。 
    
 _lpInterfaceToCopy_
  
> [in]指向 IID (的接口标识符) 表示用于访问要复制的邮件服务的配置文件节的接口的指针。 传递 NULL 会导致使用标准配置文件节接口[IProfSect。](iprofsectimapiprop.md)
    
 _lpInterfaceDst_
  
> [in]指向 IID 的指针，该指针代表用于访问  _lpObjectDst_ 参数指向的对象的接口。 传递 NULL 会导致会话接口 [IMAPISession](imapisessioniunknown.md)被使用。 _还可以将 lpInterfaceDst_ 参数设置为 IID_IMsgServiceAdmin。 
    
 _lpObjectDst_
  
> [in]指向指向会话或邮件服务管理对象的指针的指针。 对象的类型应与在  _lpInterfaceDst 中传递的接口标识符相对应_。 有效的对象指针是 LPMAPISESSION 和 LPSERVICEADMIN。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> [in]控制邮件服务复制方式的标志的位掩码。 可以设置以下标志：
    
SERVICE_UI_ALWAYS 
  
> 请求邮件服务始终显示配置属性表。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制邮件服务。
    
MAPI_E_NO_ACCESS 
  
> 邮件服务已位于配置文件中，并且不允许自身的多个实例。
    
MAPI_E_NOT_FOUND 
  
> _lpUID_ 指向的 **MAPIUID** 不引用现有邮件服务。 
    
## <a name="remarks"></a>备注

**IMsgServiceAdmin：：CopyMsgService** 方法将邮件服务复制到配置文件（活动配置文件或其他配置文件）。 包含要复制的邮件服务和目标的配置文件不需要是同一个配置文件，但可以相同。 
  
不为复制操作调用邮件服务的入口点函数。 复制的邮件服务的配置设置与原始邮件服务相同。 若要更改这些设置，客户端应调用 [IMsgServiceAdmin：：ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) 方法。 
  
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)
  
[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

