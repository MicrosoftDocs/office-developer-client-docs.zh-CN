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
  
定义邮件服务入口点函数的原型以支持邮件服务配置。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi.h  <br/> |
|定义的函数实现方：  <br/> |邮件服务  <br/> |
|由调用的已定义函数：  <br/> |MAPI  <br/> |
   
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
  
> [in]服务提供程序DLL 实例的句柄。 句柄通常用于检索资源。 
    
 _lpMalloc_
  
> [in]指向公开 OLE **IMalloc 接口的内存分配器对象的** 指针。 使用某些接口（如 **IStream）** 时，邮件服务可能需要使用此分配方法。 
    
 _lpMAPISup_
  
> [in]指向 [IMAPISupport ： IUnknown](imapisupportiunknown.md) 接口实现指针。 
    
 _ulUIParam_
  
> [in]用于将用户界面信息传递给函数或零的特定于实现的值。 _ulUIParam_ 参数是配置对话框的父窗口句柄，其类型为 HWND (强制转换到ULONG_PTR) 。 值为零表示没有父窗口。 
    
 _ulFlags_
  
> [in]指示服务输入函数选项的标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。 
    
MSG_SERVICE_UI_READ_ONLY 
  
> 服务的配置用户界面应显示当前配置，但不允许用户更改它。 
    
SERVICE_UI_ALLOWED 
  
> 允许显示配置对话框（如有必要）。 设置 SERVICE_UI_ALLOWED 标志时，对话框应仅在  _lpProps_ 属性值数组为空或不包含有效配置时显示。 如果未SERVICE_UI_ALLOWED，则设置该对话框时，SERVICE_UI_ALWAYS显示一个对话框。 
    
UI_CURRENT_PROVIDER_FIRST 
  
> 请求将活动提供程序的配置对话框显示在其他对话框的顶部。 
    
SERVICE_UI_ALWAYS 
  
> 需要邮件服务显示配置对话框。 如果未SERVICE_UI_ALWAYS，如果设置了 SERVICE_UI_ALLOWED 标志，并且  _lpProps_ 属性值数组中未提供有效的配置信息，则仍可能会显示配置对话框。 必须SERVICE_UI_ALLOWED或SERVICE_UI_ALWAYS用户界面，以允许显示用户界面。 
    
 _ulContext_
  
> [in]MAPI 当前正在执行的配置操作。 _ulContext_ 参数将包含下列值之一： 
    
MSG_SERVICE_CONFIGURE 
  
> 应在配置文件中更改服务的配置。 如果SERVICE_UI_ALWAYS，服务应显示其配置对话框。 如果设置了 lpProps 参数，SERVICE_UI_ALLOWED  _lpProps_ 参数为空或不包含有效的配置数据，则还应显示该对话框。 如果  _lpProps_ 包含有效数据，则不应显示任何对话框，服务应该使用此数据进行配置更改。 
    
MSG_SERVICE_CREATE 
  
> 服务将添加到配置文件中。 如果设置了 SERVICE_UI_ALWAYS 或 SERVICE_UI_ALLOWED 标志，则服务应显示其配置对话框。 如果未设置任何标志，则服务应失败。 
    
MSG_SERVICE_DELETE 
  
> 服务正在从配置文件中删除。 收到此事件后，服务应返回S_OK。
    
MSG_SERVICE_INSTALL 
  
> 服务已从网络、软盘或其他外部介质安装到用户的工作站。 收到此事件后，该服务通常会返回S_OK。 
    
MSG_SERVICE_PROVIDER_CREATE 
  
> 请求服务创建提供程序的其他实例。 如果服务支持此操作，则它应调用 [IProviderAdmin：：CreateProvider](iprovideradmin-createprovider.md)。 如果服务不支持此操作，则它会返回MAPI_E_NO_SUPPORT。 
    
MSG_SERVICE_PROVIDER_DELETE 
  
> 请求服务删除提供程序实例。 如果服务支持此操作，则它应调用 [IProviderAdmin：:D eleteProvider](iprovideradmin-deleteprovider.md)。 如果服务不支持此操作，则它会返回MAPI_E_NO_SUPPORT。
    
MSG_SERVICE_UNINSTALL 
  
> 服务正在删除。 收到此事件后，该服务可以执行应在服务结束之前完成的任何清理任务，然后返回一个成功值。 如果用户取消删除，服务应返回MAPI_E_USER_CANCEL。 
    
 _cValues_
  
> [in]  _lpProps_ 参数指向的数组中的属性值计数。 如果 MAPI 未传递任何属性值，  _则 cValues_ 参数的值为零。 
    
 _lpProps_
  
> [in]指向 [SPropValue](spropvalue.md) 结构的可选数组的指针，指示函数将在配置邮件服务时使用的提供程序支持属性的值。 如果  _ulContext_ 参数设置为 MSG_SERVICE_CONFIGURE。 此参数通常用于传递基于文件的服务（如个人通讯簿服务）的文件的路径。 如果未在  _ulFlags_ 参数中传递 MSG_SERVICE_CONFIGURE 标志，则  _lpProps_ 参数必须为零。 
    
 _lpProviderAdmin_
  
> [in]指向 [IProviderAdmin：IUnknown](iprovideradminiunknown.md) 接口的指针，该接口可用于在当前邮件服务中查找特定提供程序的配置文件部分。 
    
 _lppMapiError_
  
> [out]指向 [MAPIERROR 结构的](mapierror.md) 指针。 该结构通过 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数进行分配。 虽然大多数结构将在  _lpszError_ 成员中包含有效的错误消息字符串，但所有成员都是可选的。 如果存在  _结构的 lpszComponent_ 或  _lpszError_ 成员，最终必须通过对基本结构上的 [MAPIFreeBuffer](mapifreebuffer.md) 的单个调用释放其内存。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。 
    
MAPI_E_UNCONFIGURED 
  
> 尚未配置服务提供商。 
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 操作。 
    
MAPI_E_NO_SUPPORT 
  
> 提供程序不支持更改其对象，或者不支持更改通知。 
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，并且实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
## <a name="remarks"></a>备注

使用 **MSGSERVICEENTRY** 函数原型定义的函数使邮件服务可以配置自身或执行其他特定于服务的操作。 函数主要提供一个对话框，用户可以在对话框中更改特定于邮件服务的设置。 它还可以使用传入  _lpProps_ 参数的属性值数组来支持编程配置。 编程配置是可选的，除非该服务支持配置文件向导，而该向导是必需的。 
  
MAPI 从控制面板应用程序或响应调用 [IMsgServiceAdmin：：CreateMsgService](imsgserviceadmin-createmsgservice.md) 或 [IMsgServiceAdmin：：ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)的客户端应用程序调用此入口点。 
  
MAPI 对邮件服务用于 **MSGSERVICEENTRY** 原型的函数名称没有限制，但首选名称 **ServiceEntry**。 对函数的序号没有限制，并且单个提供程序 DLL 可以包含多个函数。 但是，只能将其中一个函数命名为 **ServiceEntry**。 
  
邮件服务可以使用 [BuildDisplayTable](builddisplaytable.md) 函数和 [IMAPISupport：:D oConfigPropsheet](imapisupport-doconfigpropsheet.md) 方法来简化配置对话框实现。 
  
用户可以取消一个MSG_SERVICE_UNINSTALL操作。 在这种情况下 **，ServiceEntry** 函数应检查用户以确认不应删除该服务，并返回MAPI_E_USER_CANCEL服务是否仍已安装。 
  
基于 **MSGSERVICEENTRY** 原型的函数返回列出的 HRESULT 值之一。 MAPI 在响应客户端对 [IMsgServiceAdmin：：ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)的调用时转发此值。 
  
导出服务条目功能的邮件服务必须包括 MAPISVC.INF 的邮件服务部分中的 **PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 和 **PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 属性。 
  

