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
ms.openlocfilehash: aba61d4acf7c1f9a5d91fa15f1ca6b16f173bcb2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426133"
---
# <a name="imsgserviceadmin--iunknown"></a>IMsgServiceAdmin : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对配置文件中的邮件服务进行更改。
  
|||
|:-----|:-----|
|标头文件：  <br/> |MapiX  <br/> |
|公开者:  <br/> |邮件服务管理对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符:  <br/> |IID_IMsgServiceAdmin  <br/> |
|指针类型:  <br/> |LPSERVICEADMIN  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](imsgserviceadmin-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关邮件服务管理对象生成的最后一个错误的信息。  <br/> |
|[GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) <br/> |提供对邮件服务表 (配置文件中的邮件服务列表) 的访问权限。  <br/> |
|[CreateMsgService](imsgserviceadmin-createmsgservice.md) <br/> |向当前配置文件添加邮件服务。  <br/> <br/>**注意**: 此方法已弃用。 改用[IMsgServiceAdmin2:: CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md) 。           |
|[DeleteMsgService](imsgserviceadmin-deletemsgservice.md) <br/> |从配置文件中删除邮件服务。  <br/> |
|[CopyMsgService](imsgserviceadmin-copymsgservice.md) <br/> |将邮件服务复制到配置文件中。  <br/> |
|[RenameMsgService](imsgserviceadmin-renamemsgservice.md) <br/> |已弃用。 为邮件服务分配一个新名称。  <br/> |
|[ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) <br/> |重新配置邮件服务。  <br/> |
|[OpenProfileSection](imsgserviceadmin-openprofilesection.md) <br/> |打开当前配置文件的一个部分, 并返回一个[IProfSect](iprofsectimapiprop.md)指针以供进一步访问。  <br/> |
|[MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md) <br/> |设置用于传递邮件的传输提供程序的调用顺序。  <br/> |
|[AdminProviders](imsgserviceadmin-adminproviders.md) <br/> |返回一个指针, 该指针提供对提供程序管理对象的访问权限。  <br/> |
|[SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md) <br/> |将邮件服务指定为配置文件的主标识的供应商。  <br/> |
|[GetProviderTable](imsgserviceadmin-getprovidertable.md) <br/> |提供对提供程序表的访问权限 (配置文件中的服务提供程序的列表)。  <br/> |
   
## <a name="remarks"></a>说明

实现可以通过以下两种方式获取指向**IMsgServiceAdmin**接口的指针: 调用[IMAPISession:: AdminServices](imapisession-adminservices.md)方法或调用[IProfAdmin:: AdminServices](iprofadmin-adminservices.md)方法。 对于主要关注配置文件配置的客户端, **IProfAdmin:: AdminServices**是获取**IMsgServiceAdmin**接口的首选方法, 因为它不会登录到 MAPI 会话的提供程序。 如果客户端要求对活动配置文件进行更改, 则应调用**IMAPISession:: AdminServices**以获取**IMsgServiceAdmin**指针。 请注意, 虽然 MAPI 不允许删除正在使用的配置文件, 但没有防止客户端删除配置文件中的所有邮件服务的安全措施。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

