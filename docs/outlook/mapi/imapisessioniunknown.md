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
ms.openlocfilehash: 1c1a66f61fe1533e436f4e35a542f53d938b4d01
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413379"
---
# <a name="imapisession--iunknown"></a>IMAPISession : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
管理与 MAPI 登录会话关联的对象。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix.h  <br/> |
|公开者：  <br/> |会话对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和 MAPI  <br/> |
|接口标识符：  <br/> |IID_IMAPISession  <br/> |
|指针类型：  <br/> |LPMAPISESSION  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](imapisession-getlasterror.md) <br/> |返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个会话错误的信息。  <br/> |
|[GetMsgStoresTable](imapisession-getmsgstorestable.md) <br/> |提供对包含有关会话配置文件中所有邮件存储的信息的邮件存储表的访问。  <br/> |
|[OpenMsgStore](imapisession-openmsgstore.md) <br/> |打开邮件存储并返回 [IMsgStore](imsgstoreimapiprop.md) 指针以进一步访问。  <br/> |
|[OpenAddressBook](imapisession-openaddressbook.md) <br/> |打开 MAPI 集成通讯簿，返回 [IAddrBook](iaddrbookimapiprop.md) 指针以进一步访问。  <br/> |
|[OpenProfileSection](imapisession-openprofilesection.md) <br/> |打开当前配置文件的一部分并返回 [IProfSect](iprofsectimapiprop.md) 指针以进一步访问。  <br/> |
|[GetStatusTable](imapisession-getstatustable.md) <br/> |提供对状态表（包含有关会话中所有 MAPI 资源的信息的表）的访问权限。  <br/> |
|[OpenEntry](imapisession-openentry.md) <br/> |打开对象并返回接口指针以进一步访问。  <br/> |
|[CompareEntryIDs](imapisession-compareentryids.md) <br/> |比较两个条目标识符以确定它们是否引用同一个对象。  <br/> |
|[建议](imapisession-advise.md) <br/> |注册以接收影响会话的指定事件的通知。  <br/> |
|[非企业](imapisession-unadvise.md) <br/> |取消发送以前通过调用 **Advise** 方法设置的通知。  <br/> |
|**MessageOptions** <br/> | *不支持或记录。*  <br/> |
|**QueryDefaultMessageOpt** <br/> | *不支持或记录。*  <br/> |
|[EnumAdrTypes](imapisession-enumadrtypes.md) <br/> |已弃用。 返回会话中所有传输提供程序可以处理的地址类型。  <br/> |
|[QueryIdentity](imapisession-queryidentity.md) <br/> |返回提供会话的主标识的对象的条目标识符。  <br/> |
|[注销](imapisession-logoff.md) <br/> |结束 MAPI 会话。  <br/> |
|[SetDefaultStore](imapisession-setdefaultstore.md) <br/> |将邮件存储建立为会话的默认邮件存储。  <br/> |
|[AdminServices](imapisession-adminservices.md) <br/> |返回一 [个 IMsgServiceAdmin](imsgserviceadminiunknown.md) 指针，用于对邮件服务进行更改。  <br/> |
|[ShowForm](imapisession-showform.md) <br/> |显示窗体。  <br/> |
|[PrepareForm](imapisession-prepareform.md) <br/> |创建一个 **数值令牌，ShowForm** 方法使用该令牌访问邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

