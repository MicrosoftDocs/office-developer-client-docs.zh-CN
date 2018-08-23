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
ms.openlocfilehash: f2cc9a6f97fa51a255f8c24c2bb52c912aef7718
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566248"
---
# <a name="launchwizardentry"></a>LAUNCHWIZARDENTRY

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
定义启动配置文件向导应用程序以便向一个配置文件中添加一个或多个消息服务的函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiwz.h  <br/> |
|通过实施定义的函数：  <br/> |MAPI  <br/> |
|定义的函数调用：  <br/> |客户端应用程序  <br/> |
   
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
  
> [in]呼叫者的父窗口的句柄。 如果呼叫者没有父窗口， _hParentWnd_参数应为 NULL。 
    
 _ulFlags_
  
> [in]指示用于配置文件向导选项标志的位掩码。 可以设置以下标志：
    
MAPI_PW_ADD_SERVICE_ONLY 
  
> 配置文件向导是添加了通过_lppszServiceNameToAdd_参数列出这些消息服务并不显示其页面，以便选择消息服务。 
    
MAPI_PW_FIRST_PROFILE 
  
> 要创建的配置文件是为此工作站的第一个。 
    
MAPI_PW_HIDE_SERVICES_LIST 
  
> 不应显示用于选择消息服务的配置文件向导的页。 
    
MAPI_PW_LAUNCHED_BY_CONFIG 
  
> 配置文件向导已启动控制面板配置应用程序。 
    
MAPI_PW_PROVIDER_UI_ONLY 
  
> 应显示仅服务提供商的配置对话框，并不应出现配置文件向导的页面。 如果设置了 MAPI_PW_ADD_SERVICE_ONLY 标志，则仅可以设置此标志。 
    
 _lppszServiceNameToAdd_
  
> [in]指针指向包含消息服务都添加到配置文件的名称的字符串数组。 数组必须终止 NULL 值。 
    
 _cbBufferMax_
  
> [in]_LpszNewProfileName_参数指向缓冲区的大小。 
    
 _lpszNewProfileName_
  
> [输出]指向基于**LAUNCHWIZARDENTRY**函数为其返回创建配置文件的名称的字符串缓冲区。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_E_CALL_FAILED 
  
> 意外或未知的原点出现错误，无法完成操作。 可能的用途包括未能初始化 MAPI 子系统的配置文件向导，从对话框返回无法访问默认配置文件，而是一个错误。
    
## <a name="remarks"></a>注解

**LAUNCHWIZARDENTRY**函数原型的 MAPI 实现的 MAPI 配置文件向导应用程序的入口点。 MAPI 命名**LaunchWizard**此入口点。 
  
当 MAPI_PW_ADD_SERVICE_ONLY 标志设置_ulFlags_参数中时，下列规则适用： 
  
- MAPI_PW_LAUNCHED_BY_CONFIG 标志禁止显示欢迎页。 
    
- 仅当没有默认配置文件时，MAPI_PW_HIDE_SERVICES_LIST 和 MAPI_PW_PROVIDER_UI_ONLY 标志是很有用。 在这种情况下这些标志确定页是要显示哪些配置文件向导。 
    
- 如果存在默认配置文件，配置文件向导页都将显示。 
    
- 如果存在默认配置文件，只有一个邮件服务列出通过_lppszServiceNameToAdd_参数，并且邮件服务已存在于默认配置文件中，配置文件向导不到配置文件中添加任何返回 S_OK。 
    
对于要添加到配置文件中每个邮件服务，配置文件向导调用基于[MSGSERVICEENTRY](msgserviceentry.md)原型服务的入口点函数。 从邮件服务中选择要添加到配置文件的每个服务提供商，对于配置文件向导调用基于[WIZARDENTRY](wizardentry.md)原型的提供程序的入口点函数。 交互式配置过程中在属性页中每个用户事件导致配置文件向导来调用基于[SERVICEWIZARDDLGPROC](servicewizarddlgproc.md)原型的提供程序的回调函数。 
  
如果要添加到配置文件服务提供商支持的配置文件向导页面，它必须允许编程对配置文件配置。
  

