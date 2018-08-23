---
title: IMsgServiceAdmin IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin
api_type:
- COM
ms.assetid: 5905b9e9-c462-451d-a49f-1f3a8aa506a6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cf275c66a60ed977c442b468b7c9951325db5120
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593513"
---
# <a name="imsgserviceadmin--iunknown"></a>IMsgServiceAdmin : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
对配置文件中的消息服务进行更改。
  
|||
|:-----|:-----|
|头文件：  <br/> |MapiX.h  <br/> |
|由公开：  <br/> |消息服务管理对象  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IMsgServiceAdmin  <br/> |
|指针类型：  <br/> |LPSERVICEADMIN  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](imsgserviceadmin-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含信息由消息服务管理对象生成的最后一个错误。  <br/> |
|[GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) <br/> |提供对邮件服务表，该配置文件中的消息服务的列表的访问。  <br/> |
|[CreateMsgService](imsgserviceadmin-createmsgservice.md) <br/> |向当前配置文件的消息服务。  <br/> <br/>**注意**： 此方法已被弃用。 请改用[IMsgServiceAdmin2::CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md) 。           |
|[DeleteMsgService](imsgserviceadmin-deletemsgservice.md) <br/> |从配置文件中删除的消息服务。  <br/> |
|[CopyMsgService](imsgserviceadmin-copymsgservice.md) <br/> |将邮件服务复制到一个配置文件。  <br/> |
|[RenameMsgService](imsgserviceadmin-renamemsgservice.md) <br/> |已弃用。 将新的名称分配给邮件服务。  <br/> |
|[ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) <br/> |重新配置的消息服务。  <br/> |
|[OpenProfileSection](imsgserviceadmin-openprofilesection.md) <br/> |打开当前配置文件的节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。  <br/> |
|[MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md) <br/> |设置中的传输提供程序调用将邮件传递的顺序。  <br/> |
|[AdminProviders](imsgserviceadmin-adminproviders.md) <br/> |返回提供访问提供程序管理对象的指针。  <br/> |
|[SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md) <br/> |指定要配置文件的主标识的供应商的消息服务。  <br/> |
|[GetProviderTable](imsgserviceadmin-getprovidertable.md) <br/> |提供对提供程序表中，在配置文件中的服务提供商的列表的访问。  <br/> |
   
## <a name="remarks"></a>注解

实现可以通过以下两种**IMsgServiceAdmin**界面得到指针： 通过调用[IMAPISession::AdminServices](imapisession-adminservices.md)方法或通过调用[IProfAdmin::AdminServices](iprofadmin-adminservices.md)方法。 对于主要关心配置文件配置的客户端， **IProfAdmin::AdminServices**是首选的方式获取**IMsgServiceAdmin**接口，因为未登录到 MAPI 会话的提供程序。 如果客户端需要能够对活动配置文件进行更改，然后应该调用**IMAPISession::AdminServices**获取**IMsgServiceAdmin**指针。 注意虽然 MAPI 不允许使用要删除的配置文件，没有任何安全措施，以防止客户端配置文件中删除所有邮件服务。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

