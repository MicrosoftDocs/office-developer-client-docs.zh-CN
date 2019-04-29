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
ms.openlocfilehash: 56a5f153dbd563397b9216af32a715692d0876d7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427876"
---
# <a name="msgserviceentry"></a>MSGSERVICEENTRY

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义用于支持邮件服务配置的邮件服务入口点函数的原型。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|定义的函数实现者:  <br/> |邮件服务  <br/> |
|定义的函数调用者:  <br/> |MAPI  <br/> |
   
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
  
> 实时服务 providerDLL 的实例的句柄。 该句柄通常用于检索资源。 
    
 _lpMalloc_
  
> 实时指向用于公开 OLE **IMalloc**接口的内存分配器对象的指针。 在使用某些接口 (如**IStream**) 时, 邮件服务可能需要使用此分配方法。 
    
 _lpMAPISup_
  
> 实时指向 IMAPISupport 的指针[: IUnknown](imapisupportiunknown.md)接口实现。 
    
 _ulUIParam_
  
> 实时用于将用户界面信息传递给函数或零的特定于实现的值。 _ulUIParam_参数是 "配置" 对话框的父窗口句柄, 其类型为 HWND (转换为 ULONG_PTR)。 如果值为零, 则表示没有父窗口。 
    
 _ulFlags_
  
> 实时指示服务输入函数选项的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 
    
MSG_SERVICE_UI_READ_ONLY 
  
> 服务的配置用户界面应显示当前配置, 但不允许用户对其进行更改。 
    
SERVICE_UI_ALLOWED 
  
> 允许显示配置对话框 (如有必要)。 设置 SERVICE_UI_ALLOWED 标志后, 仅当_lpProps_属性值数组为空或不包含有效配置时, 才应显示对话框。 如果未设置 SERVICE_UI_ALLOWED, 则在设置 SERVICE_UI_ALWAYS 标志的情况下, 可能仍会显示一个对话框。 
    
UI_CURRENT_PROVIDER_FIRST 
  
> 请求活动提供程序的 "配置" 对话框显示在其他对话框的上方。 
    
SERVICE_UI_ALWAYS 
  
> 需要邮件服务显示 "配置" 对话框。 如果未设置 SERVICE_UI_ALWAYS 标志, 则在设置了 SERVICE_UI_ALLOWED 标志且在_lpProps_属性值数组中不提供有效的配置信息的情况下, 可能仍会显示 "配置" 对话框。 必须将 SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 设置为允许显示用户界面。 
    
 _ulContext_
  
> 实时MAPI 当前正在执行的配置操作。 _ulContext_参数将包含以下值之一: 
    
MSG_SERVICE_CONFIGURE 
  
> 应在配置文件中进行对服务配置的更改。 如果设置了 SERVICE_UI_ALWAYS 标志, 则服务应显示其 "配置" 对话框。 如果设置了 SERVICE_UI_ALLOWED 标志, 并且_lpProps_参数为空或不包含有效的配置数据, 也应显示对话框。 如果_lpProps_包含有效数据, 则不应显示任何对话框, 并且该服务应使用此数据进行配置更改。 
    
MSG_SERVICE_CREATE 
  
> 正在将服务添加到配置文件。 如果设置了 SERVICE_UI_ALWAYS 或 SERVICE_UI_ALLOWED 标志, 则该服务应显示其 "配置" 对话框。 如果两个标志都未设置, 则服务应失败。 
    
MSG_SERVICE_DELETE 
  
> 正在从配置文件中删除该服务。 在收到此事件之后, 服务应返回 S_OK。
    
MSG_SERVICE_INSTALL 
  
> 已从网络、软盘或其他外部媒体将该服务安装到用户的工作站上。 在收到此事件之后, 服务通常返回 S_OK。 
    
MSG_SERVICE_PROVIDER_CREATE 
  
> 请求服务创建提供程序的其他实例。 如果服务支持此操作, 则应调用[IProviderAdmin:: CreateProvider](iprovideradmin-createprovider.md)。 如果服务不支持此操作, 则可以返回 MAPI_E_NO_SUPPORT。 
    
MSG_SERVICE_PROVIDER_DELETE 
  
> 请求服务删除提供程序实例。 如果服务支持此操作, 则应调用[IProviderAdmin::D eleteprovider](iprovideradmin-deleteprovider.md)。 如果服务不支持此操作, 则可以返回 MAPI_E_NO_SUPPORT。
    
MSG_SERVICE_UNINSTALL 
  
> 正在删除服务。 在收到此事件之后, 服务可以执行任何应在服务结束之前完成的清理任务, 然后返回成功值。 如果用户取消了删除操作, 服务应返回 MAPI_E_USER_CANCEL。 
    
 _cValues_
  
> 实时由_lpProps_参数指向的数组中的属性值的计数。 如果 MAPI 不传递属性值, 则_cValues_参数的值为零。 
    
 _lpProps_
  
> 实时指向[SPropValue](spropvalue.md)结构的可选数组的指针, 该数组指示函数将在配置消息服务时使用的提供程序支持属性的值。 如果将_ulContext_参数设置为 MSG_SERVICE_CONFIGURE, 则此函数仅使用此参数。 此参数通常用于将路径传递到基于文件的服务 (如个人通讯簿服务) 的文件。 如果未在_ulFlags_参数中传递 MSG_SERVICE_CONFIGURE 标志, 则_lpProps_参数必须为零。 
    
 _lpProviderAdmin_
  
> 实时指向[IProviderAdmin: IUnknown](iprovideradminiunknown.md)接口的指针, 该函数可使用该接口为当前邮件服务中的特定提供程序定位配置文件节。 
    
 _lppMapiError_
  
> 排除指向[MAPIERROR](mapierror.md)结构的指针。 结构是使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数分配的。 所有成员都是可选的, 但大多数结构将包含_lpszError_成员中的有效错误消息字符串。 如果存在结构的_lpszComponent_或_lpszError_成员, 则它们的内存最终必须通过对基础结构上的[MAPIFreeBuffer](mapifreebuffer.md)的单个调用来释放。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。 
    
MAPI_E_UNCONFIGURED 
  
> 尚未配置服务提供程序。 
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
MAPI_E_NO_SUPPORT 
  
> 提供程序不支持对其对象的更改或不支持更改通知。 
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
## <a name="remarks"></a>说明

使用**MSGSERVICEENTRY**函数原型定义的函数使邮件服务能够自行配置或执行其他特定于服务的操作。 该函数主要提供一个对话框, 用户可以在其中更改特定于邮件服务的设置。 它还可以使用在_lpProps_参数中传递的属性值数组支持编程配置。 编程配置是可选的, 除非服务支持配置文件向导 (需要它)。 
  
MAPI 从 "控制面板" 应用程序或响应调用[IMsgServiceAdmin:: CreateMsgService](imsgserviceadmin-createmsgservice.md)或[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)的客户端应用程序调用此入口点。 
  
MAPI 对邮件服务对**MSGSERVICEENTRY**原型使用的函数名称没有限制, 但优先于名称**ServiceEntry**。 函数的序号没有限制, 并且单个提供程序 DLL 可以包含多个函数。 但是, 其中只有一个函数可命名为**ServiceEntry**。 
  
邮件服务可以使用[BuildDisplayTable](builddisplaytable.md)函数和[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)方法来简化配置对话框的实现。 
  
用户可以取消 MSG_SERVICE_UNINSTALL 操作。 在这种情况下, **ServiceEntry**函数应与用户进行确认, 以验证是否不应删除服务, 如果服务仍保持安装, 则返回 MAPI_E_USER_CANCEL。 
  
基于**MSGSERVICEENTRY**原型的函数返回列出的 HRESULT 值之一。 当响应客户端对[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)的调用时, MAPI 将转发此值。 
  
导出服务条目函数的邮件服务必须在的 "邮件服务" 部分中包含**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 和**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 属性MAPISVC.INF。 
  

