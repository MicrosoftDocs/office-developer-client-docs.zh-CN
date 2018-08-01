---
title: MSGSERVICEENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MSGSERVICEENTRY
api_type:
- COM
ms.assetid: 655774a6-588c-44c7-903b-4497b7eccbc2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9af170f3445757eb96b9fe78c7cbea2c29ef4612
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776542"
---
# <a name="msgserviceentry"></a>MSGSERVICEENTRY

  
  
**适用于**： Outlook 
  
定义以支持消息服务配置邮件服务入口点函数的原型。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
|通过实施定义的函数：  <br/> |消息服务  <br/> |
|定义的函数调用：  <br/> |MAPI  <br/> |
   
```cpp
HRESULT MSGSERVICEENTRY(
  HINSTANCE hInstance,
  LPMALLOC lpMalloc,
  LPMAPISUP lpMAPISup,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG ulContext,
  ULONG cValues,
  LPSPropValue lpProps,
  LPPROVIDERADMIN lpProviderAdmin,
  LPMAPIERROR FAR * lppMapiError
);
```

## <a name="parameters"></a>参数

 _hInstance_
  
> [in]服务 providerDLL 实例的句柄。 窗口的句通常用于检索资源。 
    
 _lpMalloc_
  
> [in]对内存分配器对象公开的 OLE **IMalloc**接口的指针。 邮件服务可能需要使用某些如**IStream**接口时使用此分配方法。 
    
 _lpMAPISup_
  
> [in]指向[IMAPISupport: IUnknown](imapisupportiunknown.md)接口实现。 
    
 _ulUIParam_
  
> [in]用于将用户界面的信息传递给函数或零特定于实现的值。 _UlUIParam_参数配置对话框的父窗口句柄并且的类型为 HWND （强制转换为 ULONG_PTR）。 值为零表示没有父窗口。 
    
 _ulFlags_
  
> [in]标志指示的服务项功能的选项的位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
MSG_SERVICE_UI_READ_ONLY 
  
> 该服务的配置用户界面应显示当前配置，但不是允许用户更改它。 
    
SERVICE_UI_ALLOWED 
  
> 允许有必要，将显示配置对话框。 SERVICE_UI_ALLOWED 标志设置时，应显示对话框才_lpProps_属性值数组为空或不包含无效的配置。 如果未设置 SERVICE_UI_ALLOWED，如果设置了 SERVICE_UI_ALWAYS 标志，可能仍被显示对话框。 
    
UI_CURRENT_PROVIDER_FIRST 
  
> 活动的提供程序的配置对话框将显示在其他对话框顶部的请求。 
    
SERVICE_UI_ALWAYS 
  
> 需要邮件服务，以显示配置对话框。 如果未设置 SERVICE_UI_ALWAYS 标志，配置对话框可能仍显示如果设置了 SERVICE_UI_ALLOWED 标志和_lpProps_属性值数组中没有有效的配置信息。 SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 必须设置为允许一个用户界面来显示。 
    
 _ulContext_
  
> [in]MAPI 当前正在执行配置操作。 _UlContext_参数将包含下列值之一： 
    
MSG_SERVICE_CONFIGURE 
  
> 配置文件中应将该服务的配置更改。 如果设置了 SERVICE_UI_ALWAYS 标志，该服务应显示其配置对话框。 如果设置了 SERVICE_UI_ALLOWED 标志且_lpProps_参数为空或不包含有效的配置数据，则还应显示对话框。 如果_lpProps_包含有效数据，应显示没有对话框，并且该服务应使用此数据进行配置更改。 
    
MSG_SERVICE_CREATE 
  
> 正在向一个配置文件添加服务。 如果设置了 SERVICE_UI_ALWAYS 或 SERVICE_UI_ALLOWED 标志，该服务应显示其配置对话框。 设置既标志，如果出现故障的服务。 
    
MSG_SERVICE_DELETE 
  
> 正在删除服务从配置文件。 在接收此事件，该服务应返回 S_OK。
    
MSG_SERVICE_INSTALL 
  
> 该服务已从网络、 软盘或其他外部介质安装到用户的工作站。 后接收此事件，该服务通常返回 S_OK。 
    
MSG_SERVICE_PROVIDER_CREATE 
  
> 该服务创建提供程序的其他实例的请求。 如果服务支持此操作，它应调用[IProviderAdmin::CreateProvider](iprovideradmin-createprovider.md)。 如果服务不支持此操作，它可以返回 MAPI_E_NO_SUPPORT。 
    
MSG_SERVICE_PROVIDER_DELETE 
  
> 服务删除提供程序实例的请求。 如果服务支持此操作，它应调用[IProviderAdmin::DeleteProvider](iprovideradmin-deleteprovider.md)。 如果服务不支持此操作，它可以返回 MAPI_E_NO_SUPPORT。
    
MSG_SERVICE_UNINSTALL 
  
> 正在删除服务。 接收此事件之后, 服务可以执行之前服务结束，然后返回成功值应该执行任何清理任务。 如果用户取消删除，该服务应返回 MAPI_E_USER_CANCEL。 
    
 _cValues_
  
> [in]Count 属性值数组中的指向_lpProps_参数。 _CValues_参数的值为零，如果 MAPI 没有属性值传递。 
    
 _lpProps_
  
> [in]指向数组可选[SPropValue](spropvalue.md)结构指示函数将使用中配置邮件服务的提供程序支持的属性值。 如果_ulContext_参数设置为 MSG_SERVICE_CONFIGURE，该函数仅使用此参数。 此参数常用将传递给基于文件的服务，如个人通讯簿服务文件的路径。 如果不_ulFlags_参数中传递 MSG_SERVICE_CONFIGURE 标志，则_lpProps_参数必须为零。 
    
 _lpProviderAdmin_
  
> [in]指向该函数可用于为当前消息服务中的特定提供程序查找配置文件部分[IProviderAdmin:IUnknown](iprovideradminiunknown.md)接口的指针。 
    
 _lppMapiError_
  
> [输出]指向[MAPIERROR](mapierror.md)结构。 与[MAPIAllocateBuffer](mapiallocatebuffer.md)函数分配结构。 所有成员都是可选的尽管大多数结构将有效的错误消息中包含字符串_lpszError_成员。 是否存在_lpszComponent_或_lpszError_结构的成员，必须最终到[MAPIFreeBuffer](mapifreebuffer.md)的基本结构上一次调用释放其内存。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_E_UNCONFIGURED 
  
> 尚未配置服务提供商。 
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
MAPI_E_NO_SUPPORT 
  
> 提供程序不支持对其对象的更改，或不支持的更改的通知。 
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现仅支持 Unicode。
    
## <a name="remarks"></a>说明

使用**MSGSERVICEENTRY**函数原型定义的函数启用消息服务来配置自己或执行其他特定于服务的操作。 该函数主要提供一个对话框，在其中用户可以向消息服务更改特定的设置。 它还可以使用_lpProps_参数中传递的属性值数组支持编程配置。 除非服务支持配置文件向导中，需要它的编程配置是可选的。 
  
MAPI 从控制面板应用程序或向客户端应用程序调用[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)或[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)响应中调用此入口点。 
  
MAPI 将函数名的消息服务使用**MSGSERVICEENTRY**原型，但首选名称**ServiceEntry**置于没有限制。 没有任何限制上的第几个函数，并且单个提供程序 DLL 可以包含多个函数。 但是，仅之一功能可以进行命名**ServiceEntry**。 
  
消息服务可以使用[BuildDisplayTable](builddisplaytable.md)函数和[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)方法简化配置对话框框实施。 
  
有可能，用户可以取消 MSG_SERVICE_UNINSTALL 操作。 在这种情况下， **ServiceEntry**函数应检查以验证该服务不会删除，并返回 MAPI_E_USER_CANCEL，如果服务保持已安装的用户。 
  
基于**MSGSERVICEENTRY**原型函数返回列出的 HRESULT 值之一。 MAPI 客户端的呼叫[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)响应时转发此值。 
  
导出服务条目函数的消息服务必须消息服务的一节中包括的**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 和**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 属性MAPISVC.INF。 
  

