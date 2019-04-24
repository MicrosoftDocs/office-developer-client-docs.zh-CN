---
title: IABLogon IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon
api_type:
- COM
ms.assetid: fe340182-f41e-42e7-b8e8-cc005b1e9a5f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fc8615fcd984623ae9c17c45fb7b51a4498a723b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348830"
---
# <a name="iablogon--iunknown"></a>IABLogon : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
访问通讯簿提供程序中的资源。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|公开者:  <br/> |通讯簿登录对象  <br/> |
|实现者：  <br/> |通讯簿提供程序  <br/> |
|调用者：  <br/> |MAPI  <br/> |
|接口标识符:  <br/> |IID_IABLogon  <br/> |
|指针类型:  <br/> |LPABLOGON  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](iablogon-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构, 该结构包含以前的通讯簿提供程序错误的相关信息。  <br/> |
|[注销](iablogon-logoff.md) <br/> |启动注销过程。  <br/> |
|[OpenEntry](iablogon-openentry.md) <br/> |打开容器、邮件用户或通讯组列表, 并返回指向接口实现的指针, 以提供进一步的访问权限。  <br/> |
|[CompareEntryIDs](iablogon-compareentryids.md) <br/> |对两个条目标识符进行比较, 以确定它们是否引用同一个对象。  <br/> |
|[她们](iablogon-advise.md) <br/> |注册调用方, 以接收影响容器、邮件用户或通讯组列表的指定事件的通知。  <br/> |
|[Unadvise](iablogon-unadvise.md) <br/> |取消以前通过调用**Advise**方法而设置的通知。  <br/> |
|[OpenStatusEntry](iablogon-openstatusentry.md) <br/> |打开提供程序的 status 对象。  <br/> |
|[OpenTemplateID](iablogon-opentemplateid.md) <br/> |打开包含驻留在主机通讯簿提供程序中的数据的收件人条目。  <br/> |
|[GetOneOffTable](iablogon-getoneofftable.md) <br/> |返回一个一次性模板表, 用于创建要添加到传出邮件的收件人列表中的收件人。  <br/> |
|[PrepareRecips](iablogon-preparerecips.md) <br/> |准备收件人列表, 以供邮件系统以后使用。  <br/> |
   
## <a name="remarks"></a>注解

有关**IABLogon**接口的方法的一般信息, 请参阅[实现服务提供程序登录](implementing-service-provider-logon.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

