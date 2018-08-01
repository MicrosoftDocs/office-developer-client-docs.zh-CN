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
ms.openlocfilehash: e36a987174ffb2abb4c0f5fc95bf695f31af942e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775588"
---
# <a name="imapistatus--imapiprop"></a>IMAPIStatus : IMAPIProp

  
  
**适用于**： Outlook 
  
提供有关 MAPI 子系统、 集成的通讯簿中，和 MAPI 后台处理程序的状态信息。 服务提供商实现**IMAPIStatus**可提供有关其自身的状态信息。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |状态对象  <br/> |
|通过实现：  <br/> |服务提供商和 MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IMAPIStatus  <br/> |
|指针类型：  <br/> |LPMAPISTATUS  <br/> |
|事务模型：  <br/> |Nontransacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[ValidateState](imapistatus-validatestate.md) <br/> |确认可供 MAPI 资源或服务提供商的外部状态信息。  <br/> |
|[留待](imapistatus-settingsdialog.md) <br/> |显示使用户能够更改服务提供商的配置的属性表。  <br/> |
|[ChangePassword](imapistatus-changepassword.md) <br/> |不显示用户界面中修改服务提供商的密码。  <br/> |
|[FlushQueues](imapistatus-flushqueues.md) <br/> |强制等待发送或接收立即上载或下载的所有邮件。  <br/> |
   
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_PROVIDER_DLL_NAME**([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RESOURCE_METHODS**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_STATUS_CODE**([PidTagStatusCode](pidtagstatuscode-canonical-property.md))  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

MAPI 实现的状态对象支持下列方法：
  
|**状态对象**|**受支持的方法**|
|:-----|:-----|
|MAPI 子系统  <br/> |仅**ValidateState**  <br/> |
|MAPI 通讯簿  <br/> |仅**ValidateState**  <br/> |
|MAPI 后台处理程序  <br/> |**ValidateState**和**FlushQueues** <br/> |
   
MAPI 实现的状态对象所需具有[IMAPIProp](imapipropiunknown.md)接口的方法的只读版本和以支持**ValidateState**方法。 传输提供程序还应支持**FlushQueues**。 所有提供程序应支持**留待**;支持**ChangePassword**是可选的。 
  
客户端使用状态对象执行配置并了解会话的状态。 他们可以通过调用服务提供商登录对象的**OpenStatusEntry**方法或[IMAPISession::GetStatusTable](imapisession-getstatustable.md)方法来检索状态对象访问状态对象。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

