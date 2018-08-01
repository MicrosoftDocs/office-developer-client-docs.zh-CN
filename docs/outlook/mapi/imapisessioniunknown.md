---
title: IMAPISession IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession
api_type:
- COM
ms.assetid: 5650fa2a-6e62-451c-964e-363f7bee2344
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a37d8138547c8c4e9308dbb0ebbc6750b152d795
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775584"
---
# <a name="imapisession--iunknown"></a>IMAPISession : IUnknown

  
  
**适用于**： Outlook 
  
管理与 MAPI 登录会话关联的对象。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapix.h  <br/> |
|由公开：  <br/> |会话对象  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和 MAPI  <br/> |
|接口标识符：  <br/> |IID_IMAPISession  <br/> |
|指针类型：  <br/> |LPMAPISESSION  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](imapisession-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关以前会话错误的信息。  <br/> |
|[GetMsgStoresTable](imapisession-getmsgstorestable.md) <br/> |提供对消息存储表包含有关会话配置文件中的所有邮件存储的信息的访问。  <br/> |
|[OpenMsgStore](imapisession-openmsgstore.md) <br/> |打开的消息存储并返回进一步访问[IMsgStore](imsgstoreimapiprop.md)指针。  <br/> |
|[OpenAddressBook](imapisession-openaddressbook.md) <br/> |打开 MAPI 集成的通讯簿中，返回进一步访问[IAddrBook](iaddrbookimapiprop.md)指针。  <br/> |
|[OpenProfileSection](imapisession-openprofilesection.md) <br/> |打开当前配置文件的节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。  <br/> |
|[GetStatusTable](imapisession-getstatustable.md) <br/> |提供对状态表中，一个表，包含会话中所有 MAPI 资源的信息的访问。  <br/> |
|[OpenEntry](imapisession-openentry.md) <br/> |打开一个对象并返回进一步访问的接口指针。  <br/> |
|[CompareEntryIDs](imapisession-compareentryids.md) <br/> |比较两个条目标识符来确定它们是否引用同一个对象。  <br/> |
|[建议](imapisession-advise.md) <br/> |注册接收影响会话的指定事件的通知。  <br/> |
|[取消通知](imapisession-unadvise.md) <br/> |取消发送通知之前设置与**Advise**方法调用。  <br/> |
|**消息选项** <br/> | *不受支持或记录。*  <br/> |
|**QueryDefaultMessageOpt** <br/> | *不受支持或记录。*  <br/> |
|[EnumAdrTypes](imapisession-enumadrtypes.md) <br/> |已弃用。 返回会话中的所有传输提供程序可以处理的地址类型。  <br/> |
|[QueryIdentity](imapisession-queryidentity.md) <br/> |返回会话中提供的主要标识的对象的项标识符。  <br/> |
|[注销](imapisession-logoff.md) <br/> |结束 MAPI 会话。  <br/> |
|[SetDefaultStore](imapisession-setdefaultstore.md) <br/> |建立会话，作为默认的邮件存储的消息存储。  <br/> |
|[AdminServices](imapisession-adminservices.md) <br/> |返回对消息服务的更改[IMsgServiceAdmin](imsgserviceadminiunknown.md)指针。  <br/> |
|[ShowForm](imapisession-showform.md) <br/> |显示窗体。  <br/> |
|[PrepareForm](imapisession-prepareform.md) <br/> |创建数值令牌**ShowForm**方法用来访问的消息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

