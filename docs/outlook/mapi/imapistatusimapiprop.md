---
title: IMAPIStatus IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIStatus
api_type:
- COM
ms.assetid: 17b2aa43-0267-45b6-8c57-11b7a5c67333
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f90cf661c069ecd476bd02c5719147633a8392e0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408297"
---
# <a name="imapistatus--imapiprop"></a>IMAPIStatus : IMAPIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供有关 mapi 子系统、集成的通讯簿和 MAPI 后台处理程序的状态信息。 服务提供程序实现**IMAPIStatus** , 以提供有关其自己的状态的信息。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|公开者:  <br/> |状态对象  <br/> |
|实现者：  <br/> |服务提供商和 MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符:  <br/> |IID_IMAPIStatus  <br/> |
|指针类型:  <br/> |LPMAPISTATUS  <br/> |
|事务模型:  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[ValidateState](imapistatus-validatestate.md) <br/> |确认可用于 MAPI 资源或服务提供商的外部状态信息。  <br/> |
|[SettingsDialog](imapistatus-settingsdialog.md) <br/> |显示使用户能够更改服务提供程序的配置的属性表。  <br/> |
|[ChangePassword](imapistatus-changepassword.md) <br/> |在不显示用户界面的情况下修改服务提供程序的密码。  <br/> |
|[FlushQueues](imapistatus-flushqueues.md) <br/> |强制立即上载或下载所有等待发送或接收的邮件。  <br/> |
   
|**必需属性**|**访问**|
|:-----|:-----|
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_PROVIDER_DLL_NAME**([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RESOURCE_METHODS**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_STATUS_CODE**([PidTagStatusCode](pidtagstatuscode-canonical-property.md))  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

MAPI 实现的 status 对象支持以下方法:
  
|**Status 对象**|**支持的方法**|
|:-----|:-----|
|MAPI 子系统  <br/> |仅**ValidateState**  <br/> |
|MAPI 通讯簿  <br/> |仅**ValidateState**  <br/> |
|MAPI 后台处理程序  <br/> |**ValidateState**和**FlushQueues** <br/> |
   
MAPI 实现的 status 对象必须具有[IMAPIProp](imapipropiunknown.md)接口的只读版本的方法, 并支持**ValidateState**方法。 传输提供程序还应支持**FlushQueues**。 所有提供程序都应支持**SettingsDialog**;对**ChangePassword**的支持是可选的。 
  
客户端使用 status 对象执行配置, 并了解会话的状态。 它们通过调用服务提供程序登录对象或[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)方法的**OpenStatusEntry**方法来访问 status 对象, 以检索 status 对象。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

