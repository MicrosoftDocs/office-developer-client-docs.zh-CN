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
ms.openlocfilehash: bedec72e8371d0e8aa69415d2f0dc77b4c62ff76
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437530"
---
# <a name="iprovideradmin--iunknown"></a>IProviderAdmin : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用邮件服务中的服务提供程序。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|公开者：  <br/> |提供程序管理对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
|接口标识符：  <br/> |IID_IProviderAdmin  <br/> |
|指针类型：  <br/> |LPPROVIDERADMIN  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](iprovideradmin-getlasterror.md) <br/> |返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关提供程序管理对象发生的上一个错误的信息。  <br/> |
|[GetProviderTable](iprovideradmin-getprovidertable.md) <br/> |提供对邮件服务提供程序表（邮件服务中的服务提供程序列表）的访问权限。  <br/> |
|[CreateProvider](iprovideradmin-createprovider.md) <br/> |将服务提供程序添加到邮件服务。  <br/> |
|[DeleteProvider](iprovideradmin-deleteprovider.md) <br/> |从邮件服务中删除服务提供商。  <br/> |
|[OpenProfileSection](iprovideradmin-openprofilesection.md) <br/> |从当前配置文件中打开配置文件部分，并返回 [IProfSect](iprofsectimapiprop.md) 指针以进一步访问。  <br/> |
   
## <a name="remarks"></a>备注

客户端可以通过调用 [IMsgServiceAdmin：：AdminProviders](imsgserviceadmin-adminproviders.md)方法获取指向 **IProviderAdmin** 接口的指针;当调用服务的邮件服务的入口点函数时，会向服务提供商传递 **IProviderAdmin** 指针。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

