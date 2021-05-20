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
ms.openlocfilehash: da71e9dd5f2fc20bb1daf528f4466ea29507bf06
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429822"
---
# <a name="iaddrbook--imapiprop"></a>IAddrBook : IMAPIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
支持访问 MAPI 通讯簿，并包括显示常见对话框等操作;打开容器、邮件用户和通讯组列表;执行名称解析。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix.h  <br/> |
|公开者：  <br/> |通讯簿对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序、服务提供商  <br/> |
|接口标识符：  <br/> |IID_IAddrBook  <br/> |
|指针类型：  <br/> |LPADRBOOK  <br/> |
|事务模型：  <br/> |不可写  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[OpenEntry](iaddrbook-openentry.md) <br/> |打开通讯簿条目，并返回一个指向可用于访问该条目的接口的指针。  <br/> |
|[CompareEntryIDs](iaddrbook-compareentryids.md) <br/> |比较属于特定通讯簿提供程序的两个条目标识符，以确定它们是否引用同一通讯簿对象。  <br/> |
|[建议](iaddrbook-advise.md) <br/> |注册客户端或服务提供商以接收有关通讯簿中一个或多个条目更改的通知。  <br/> |
|[非企业](iaddrbook-unadvise.md) <br/> |取消以前为通讯簿条目建立的通知注册。  <br/> |
|[CreateOneOff](iaddrbook-createoneoff.md) <br/> |为一次地址创建条目标识符。  <br/> |
|[NewEntry](iaddrbook-newentry.md) <br/> |将新收件人添加到通讯簿容器或传出邮件的收件人列表。  <br/> |
|[ResolveName](iaddrbook-resolvename.md) <br/> |执行名称解析，将条目标识符分配给收件人列表中的收件人。  <br/> |
|[Address](iaddrbook-address.md) <br/> |显示Outlook通讯簿对话框。  <br/> |
|[详细信息](iaddrbook-details.md) <br/> |显示一个对话框，其中显示有关特定通讯簿条目的详细信息。  <br/> |
|**RecipOptions** <br/> | *不支持或记录。*  <br/> |
|**QueryDefaultRecipOpt** <br/> | *不支持或记录。*  <br/> |
|[GetPAB](iaddrbook-getpab.md) <br/> |返回指定为 PAB 用户的个人通讯簿的容器 (标识符) 。  <br/> |
|[SetPAB](iaddrbook-setpab.md) <br/> |将特定容器指定为 PAB (个人通讯簿) 。  <br/> |
|[GetDefaultDir](iaddrbook-getdefaultdir.md) <br/> |返回初始通讯簿容器的条目标识符。  <br/> |
|[SetDefaultDir](iaddrbook-setdefaultdir.md) <br/> |将指定的容器建立为最初可用的默认通讯簿容器。  <br/> |
|[GetSearchPath](iaddrbook-getsearchpath.md) <br/> |返回由 [ResolveName](iaddrbook-resolvename.md) 方法启动的名称解析过程中要包含的容器的条目标识符的有序列表。  <br/> |
|[SetSearchPath](iaddrbook-setsearchpath.md) <br/> |设置配置文件中用于名称解析过程的新搜索路径。  <br/> |
|[PrepareRecips](iaddrbook-preparerecips.md) <br/> |准备收件人列表供邮件系统稍后使用。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

