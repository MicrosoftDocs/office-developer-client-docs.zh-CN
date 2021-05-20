---
title: LAUNCHWIZARDENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.LAUNCHWIZARDENTRY
api_type:
- COM
ms.assetid: 5778dffa-f01b-46b3-9c19-862793740918
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c1509918eb587c17deebf95317cf57b4ab19928a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437383"
---
# <a name="launchwizardentry"></a>LAUNCHWIZARDENTRY

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义一个函数，用于启动配置文件向导应用程序，以便向配置文件中添加一个或多个邮件服务。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiwz.h  <br/> |
|定义的函数实现方：  <br/> |MAPI  <br/> |
|由调用的已定义函数：  <br/> |客户端应用程序  <br/> |
   
```cpp
HRESULT LAUNCHWIZARDENTRY(
  HWND hParentWnd,
  ULONG ulFlags,
  LPCSTR FAR * lppszServiceNameToAdd,
  ULONG cbBufferMax,
  LPSTR lpszNewProfileName
);
```

## <a name="parameters"></a>参数

 _hParentWnd_
  
> [in]调用方父窗口的句柄。 如果调用方没有父窗口，  _则 hParentWnd_ 参数应为 NULL。 
    
 _ulFlags_
  
> [in]指示配置文件向导选项的标志的位掩码。 可以设置以下标志：
    
MAPI_PW_ADD_SERVICE_ONLY 
  
> 配置文件向导仅添加通过  _lppszServiceNameToAdd_ 参数列出的邮件服务，不显示用于选择邮件服务的页面。 
    
MAPI_PW_FIRST_PROFILE 
  
> 要创建的配置文件是此工作站的第一个配置文件。 
    
MAPI_PW_HIDE_SERVICES_LIST 
  
> 不应显示配置文件向导用于选择邮件服务的页面。 
    
MAPI_PW_LAUNCHED_BY_CONFIG 
  
> 配置文件向导由控制面板配置应用程序启动。 
    
MAPI_PW_PROVIDER_UI_ONLY 
  
> 应只显示服务提供商的配置对话框，并且不应显示配置文件向导的页面。 只有在设置了此标志时，才能MAPI_PW_ADD_SERVICE_ONLY此标志。 
    
 _lppszServiceNameToAdd_
  
> [in]指向包含要添加到配置文件的邮件服务的名称的字符串数组的指针。 数组必须以 NULL 值终止。 
    
 _cbBufferMax_
  
> [in]  _lpszNewProfileName_ 参数指向的缓冲区的大小。 
    
 _lpszNewProfileName_
  
> [out]指向字符串缓冲区的指针，其中基于 **LAUNCHWIZARDENTRY** 的函数返回所创建配置文件的名称。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。 
    
MAPI_E_CALL_FAILED 
  
> 意外或未知来源的错误阻止了操作完成。 可能包括初始化配置文件向导的 MAPI 子系统失败、无法访问默认配置文件以及从对话框返回错误。
    
## <a name="remarks"></a>备注

**LAUNCHWIZARDENTRY** 函数原型的 MAPI 实现是 MAPI 配置文件向导应用程序的入口点。 MAPI 将此入口点命名 **LaunchWizard**。 
  
在  _ulFlags_ 参数中设置 MAPI_PW_ADD_SERVICE_ONLY 标志时，以下规则适用： 
  
- the MAPI_PW_LAUNCHED_BY_CONFIG flag inhibits the welcome page from being displayed. 
    
- 只有在MAPI_PW_HIDE_SERVICES_LIST配置文件MAPI_PW_PROVIDER_UI_ONLY时，默认和默认配置文件标记才有用。 在这种情况下，这些标志确定要显示哪个配置文件向导页。 
    
- 如果存在默认配置文件，则不显示任何"配置文件向导"页。 
    
- 如果存在默认配置文件，则只有一个邮件服务通过  _lppszServiceNameToAdd_ 参数列出，并且该邮件服务已经在默认配置文件中，则配置文件向导将返回 S_OK而不向配置文件添加任何内容。 
    
对于要添加到配置文件中的每个邮件服务，配置文件向导将基于 [MSGSERVICEENTRY](msgserviceentry.md) 原型调用服务的入口点函数。 对于从要添加到配置文件的邮件服务中选定的每个服务提供程序，配置文件向导将基于 [WIZARDENTRY](wizardentry.md) 原型调用提供程序的入口点函数。 在交互式配置过程中，属性页中的每个用户事件都会导致配置文件向导基于 [SERVICEWIZARDDLGPROC](servicewizarddlgproc.md) 原型调用提供程序的回调函数。 
  
如果要添加到配置文件的服务提供商支持"配置文件向导"页，则必须允许以编程方式配置配置文件。
  

