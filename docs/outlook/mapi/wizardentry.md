---
title: WIZARDENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.WIZARDENTRY
api_type:
- COM
ms.assetid: e807c6b5-06cd-4ade-9d9e-69ba6abd1614
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 907984a80dbb6c5464f95def1481d002f9d6638a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430677"
---
# <a name="wizardentry"></a>WIZARDENTRY

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义一个服务提供程序入口点函数，配置文件向导会调用它来检索足够的信息以显示提供程序的配置属性表。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiwz.h  <br/> |
|定义的函数实现方：  <br/> |服务提供程序  <br/> |
|由调用的已定义函数：  <br/> |MAPI 配置文件向导  <br/> |
   
```cpp
ULONG WIZARDENTRY(
  HINSTANCE hProviderDLLInstance,
  LPSTR FAR * lpcsResourceName,
  DLGPROC FAR * lppDlgProc,
  LPMAPIPROP lpMAPIProp,
  LPMAPISUPPORTOBJECT lpMapiSupportObject
);
```

## <a name="parameters"></a>参数

 _hProviderDLLInstance_
  
> [in]服务提供程序的 DLL 的实例句柄。 
    
 _lpcsResourceName_
  
> [out]指向包含对话框资源的完整名称的字符串的指针，该对话框资源应在配置过程中由配置文件向导显示。 字符串的最大大小（包括 NULL 终止符）为 32 个字符。 
    
 _lppDlgProc_
  
> [out]指向标准 Windows对话框过程，该对话框过程由配置文件向导调用以通知提供程序各种事件。 
    
 _lpMAPIProp_
  
> [in]指向提供对配置属性的访问的属性接口实现指针。 
    
 _lpMapiSupportObject_
  
> [in]指向适用于此会话的 MAPI 支持对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功调用服务提供商的 **WIZARDENTRY** 函数。 
    
MAPI_E_CALL_FAILED 
  
> 意外或未知来源的错误阻止了操作完成。
    
## <a name="remarks"></a>备注

配置文件向导在准备好显示服务提供商的配置用户界面时调用基于 **WIZARDENTRY** 的函数。 配置完所有提供程序后，配置文件向导会通过调用 [IMsgServiceAdmin：：ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)将配置属性写入配置文件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

基于 **WIZARDENTRY** 的函数的名称必须放在 MAPISVC.INF WIZARD_ENTRY_NAME中。 
  
资源名称是将在"配置文件向导"窗格中呈现的对话框资源的名称。 传递回的资源需要包含单个对话框资源的所有页面。 当配置文件向导收到此资源时，它将忽略对话框样式，而不是控件样式，并创建所有控件作为"配置文件向导"页的子项。 所有控件最初都是隐藏的。 提供程序应确保其控件的坐标从零开始或从零开始，并且它们不能超过最大宽度 200 个对话框单位和最大高度 150 个对话框单位。 低于 400 的控件标识符为配置文件向导保留。 "配置文件向导"在提供程序的用户界面上方以粗体显示提供程序的标题。 
  
提供程序应保留  _lpMAPIProp_ 参数中提供的属性接口指针，供将来参考。 配置文件向导只处理一组最基本的属性，提供程序可以使用属性接口实现来包括其他属性。 在配置过程中，提供程序应将其配置属性添加到实现属性接口的对象中。 配置所有提供程序后，配置文件向导会将这些属性添加到配置文件中。 
  
有关如何使用此函数的信息，请参阅 [支持邮件服务配置](supporting-message-service-configuration.md)。 
  

