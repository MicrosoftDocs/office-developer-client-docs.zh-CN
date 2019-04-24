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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341375"
---
# <a name="iaddrbook--imapiprop"></a>IAddrBook : IMAPIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
支持对 MAPI 通讯簿的访问, 包括显示常见对话框等操作。打开容器、邮件用户和通讯组列表;并执行名称解析。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix  <br/> |
|公开者:  <br/> |通讯簿对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序、服务提供商  <br/> |
|接口标识符:  <br/> |IID_IAddrBook  <br/> |
|指针类型:  <br/> |LPADRBOOK  <br/> |
|事务模型:  <br/> |不可写  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[OpenEntry](iaddrbook-openentry.md) <br/> |打开通讯簿条目并返回指向可用于访问该条目的接口的指针。  <br/> |
|[CompareEntryIDs](iaddrbook-compareentryids.md) <br/> |对属于特定通讯簿提供程序的两个条目标识符进行比较, 以确定它们是否引用相同的通讯簿对象。  <br/> |
|[她们](iaddrbook-advise.md) <br/> |注册客户端或服务提供商, 以接收有关通讯簿中的一个或多个条目的更改通知。  <br/> |
|[Unadvise](iaddrbook-unadvise.md) <br/> |取消之前为通讯簿条目建立的通知注册。  <br/> |
|[CreateOneOff](iaddrbook-createoneoff.md) <br/> |为一次性地址创建条目标识符。  <br/> |
|[NewEntry](iaddrbook-newentry.md) <br/> |将新的收件人添加到通讯簿容器或传出邮件的收件人列表中。  <br/> |
|[ResolveName](iaddrbook-resolvename.md) <br/> |执行名称解析, 将条目标识符分配给收件人列表中的收件人。  <br/> |
|[Address](iaddrbook-address.md) <br/> |显示 "Outlook 通讯簿" 对话框。  <br/> |
|[Details](iaddrbook-details.md) <br/> |显示一个对话框, 显示有关特定通讯簿条目的详细信息。  <br/> |
|**RecipOptions** <br/> | *不支持或记录。*  <br/> |
|**QueryDefaultRecipOpt** <br/> | *不支持或记录。*  <br/> |
|[GetPAB](iaddrbook-getpab.md) <br/> |返回指定为 "个人通讯簿" (PAB) 的容器的条目标识符。  <br/> |
|[SetPAB](iaddrbook-setpab.md) <br/> |指定特定的容器作为个人通讯簿 (PAB)。  <br/> |
|[GetDefaultDir](iaddrbook-getdefaultdir.md) <br/> |返回初始通讯簿容器的条目标识符。  <br/> |
|[SetDefaultDir](iaddrbook-setdefaultdir.md) <br/> |将指定的容器建立为最初可用的默认通讯簿容器。  <br/> |
|[GetSearchPath](iaddrbook-getsearchpath.md) <br/> |返回要包含在由[ResolveName](iaddrbook-resolvename.md)方法启动的名称解析进程中的容器的条目标识符的已排序列表。  <br/> |
|[SetSearchPath](iaddrbook-setsearchpath.md) <br/> |在用于名称解析过程的配置文件中设置新的搜索路径。  <br/> |
|[PrepareRecips](iaddrbook-preparerecips.md) <br/> |准备收件人列表, 以供邮件系统以后使用。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

