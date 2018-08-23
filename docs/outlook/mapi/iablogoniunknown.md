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
ms.openlocfilehash: 4421fcde6ccd2f2ac6245927d9d5d63ddc5200af
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573514"
---
# <a name="iablogon--iunknown"></a>IABLogon : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
访问通讯簿提供程序中的资源。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
|由公开：  <br/> |通讯簿登录对象  <br/> |
|通过实现：  <br/> |通讯簿提供程序  <br/> |
|调用：  <br/> |MAPI  <br/> |
|接口标识符：  <br/> |IID_IABLogon  <br/> |
|指针类型：  <br/> |LPABLOGON  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](iablogon-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关以前的通讯簿提供程序错误的信息。  <br/> |
|[注销](iablogon-logoff.md) <br/> |启动注销过程。  <br/> |
|[OpenEntry](iablogon-openentry.md) <br/> |打开的容器，消息用户或通讯组列表，并返回指向接口实现，以提供更多访问的指针。  <br/> |
|[CompareEntryIDs](iablogon-compareentryids.md) <br/> |比较两个条目标识符来确定它们是否引用同一个对象。  <br/> |
|[建议](iablogon-advise.md) <br/> |注册呼叫者接收影响的容器，消息用户或通讯组列表的指定事件的通知。  <br/> |
|[取消通知](iablogon-unadvise.md) <br/> |取消以前已设置为**Advise**方法的调用的通知。  <br/> |
|[OpenStatusEntry](iablogon-openstatusentry.md) <br/> |打开提供程序的状态对象。  <br/> |
|[OpenTemplateID](iablogon-opentemplateid.md) <br/> |打开具有数据驻留在承载通讯簿提供程序中的收件人条目。  <br/> |
|[GetOneOffTable](iablogon-getoneofftable.md) <br/> |返回一个一次性模板，用于创建要添加到的传出邮件的收件人列表的收件人的表。  <br/> |
|[PrepareRecips](iablogon-preparerecips.md) <br/> |通过在邮件系统，以供以后使用准备收件人列表。  <br/> |
   
## <a name="remarks"></a>注解

**IABLogon**接口的方法的常规信息，请参阅[实现服务提供程序登录名](implementing-service-provider-logon.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

