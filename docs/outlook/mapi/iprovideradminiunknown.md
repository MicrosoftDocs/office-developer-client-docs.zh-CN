---
title: IProviderAdmin IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin
api_type:
- COM
ms.assetid: bdb4cdca-8dfd-4f90-9467-ec31cea3f518
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 559680b9ca4ea5be85718d8f9692df93f77b0edf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585750"
---
# <a name="iprovideradmin--iunknown"></a>IProviderAdmin : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
适用于邮件服务中的服务提供商。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |提供程序管理对象  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
|接口标识符：  <br/> |IID_IProviderAdmin  <br/> |
|指针类型：  <br/> |LPPROVIDERADMIN  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](iprovideradmin-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的提供程序的管理对象发生的错误的信息。  <br/> |
|[GetProviderTable](iprovideradmin-getprovidertable.md) <br/> |提供对邮件服务提供程序表中，消息服务的服务提供商的列表的访问。  <br/> |
|[CreateProvider](iprovideradmin-createprovider.md) <br/> |向消息服务的服务提供商。  <br/> |
|[DeleteProvider](iprovideradmin-deleteprovider.md) <br/> |删除消息服务的服务提供商。  <br/> |
|[OpenProfileSection](iprovideradmin-openprofilesection.md) <br/> |从当前配置文件中打开配置文件一节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。  <br/> |
   
## <a name="remarks"></a>注解

客户端可以通过调用[IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md)方法; **IProviderAdmin**界面得到指针服务提供商其消息服务的入口点函数调用时传递**IProviderAdmin**指针。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

