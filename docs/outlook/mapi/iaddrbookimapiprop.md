---
title: IAddrBook IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook
api_type:
- COM
ms.assetid: 9ccacbc0-10d5-40f9-a12b-d090a21d0d49
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0e39f2603a1eef45c456b7fb58744b79c6b75f16
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775253"
---
# <a name="iaddrbook--imapiprop"></a>IAddrBook : IMAPIProp

  
  
**适用于**： Outlook 
  
支持对 MAPI 通讯簿的访问，包括操作，例如显示常见对话框;打开容器，邮件用户和通讯组列表;而在执行名称解析。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapix.h  <br/> |
|由公开：  <br/> |地址簿对象  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序，服务提供商  <br/> |
|接口标识符：  <br/> |IID_IAddrBook  <br/> |
|指针类型：  <br/> |LPADRBOOK  <br/> |
|事务模型：  <br/> |不可写  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[OpenEntry](iaddrbook-openentry.md) <br/> |打开的通讯簿条目，并返回可用于访问该条目的接口的指针。  <br/> |
|[CompareEntryIDs](iaddrbook-compareentryids.md) <br/> |比较两个条目标识符属于特定地址簿提供程序，以确定它们是否引用同一个通讯簿对象。  <br/> |
|[建议](iaddrbook-advise.md) <br/> |注册接收有关对一个或多个条目的更改的通知通讯簿中的客户端或服务提供程序。  <br/> |
|[取消通知](iaddrbook-unadvise.md) <br/> |取消以前建立的通讯簿条目的通知注册。  <br/> |
|[CreateOneOff](iaddrbook-createoneoff.md) <br/> |创建一个一次性地址的项标识符。  <br/> |
|[NewEntry](iaddrbook-newentry.md) <br/> |将一个新收件人添加到通讯簿容器或传出邮件的收件人列表。  <br/> |
|[ResolveName](iaddrbook-resolvename.md) <br/> |执行名称解析，分配给收件人列表中的收件人的项标识符。  <br/> |
|[地址](iaddrbook-address.md) <br/> |显示 Outlook 通讯簿对话框。  <br/> |
|[详细信息](iaddrbook-details.md) <br/> |显示一个对话框，显示有关特定通讯簿条目的详细信息。  <br/> |
|**RecipOptions** <br/> | *不受支持或记录。*  <br/> |
|**QueryDefaultRecipOpt** <br/> | *不受支持或记录。*  <br/> |
|[GetPAB](iaddrbook-getpab.md) <br/> |返回的项标识符指定为个人通讯簿 (PAB) 的容器。  <br/> |
|[SetPAB](iaddrbook-setpab.md) <br/> |指定为个人通讯簿 (PAB) 特定的容器。  <br/> |
|[GetDefaultDir](iaddrbook-getdefaultdir.md) <br/> |返回初始的通讯簿容器的项标识符。  <br/> |
|[SetDefaultDir](iaddrbook-setdefaultdir.md) <br/> |建立的最初可默认通讯簿容器为指定的容器。  <br/> |
|[GetSearchPath](iaddrbook-getsearchpath.md) <br/> |返回一个已排序的列表项标识符启动[ResolveName](iaddrbook-resolvename.md)方法的名称解析进程中包含的容器。  <br/> |
|[SetSearchPath](iaddrbook-setsearchpath.md) <br/> |设置中的配置文件的名称解析过程使用新的搜索路径。  <br/> |
|[PrepareRecips](iaddrbook-preparerecips.md) <br/> |通过在邮件系统，以供以后使用准备收件人列表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

