---
title: IMAPIMessageSite IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite
api_type:
- COM
ms.assetid: 883448f5-0d3f-486d-80a3-7b961c209cd0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bf21ed1d41a61f600cfded777b699cf620c2e00f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321348"
---
# <a name="imapimessagesite--iunknown"></a>IMAPIMessageSite : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
操作邮件并由响应此类操作的表单查看器代码 (通常是客户端应用程序) 实现。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
|公开者:  <br/> |邮件站点对象  <br/> |
|实现者：  <br/> |表单查看器  <br/> |
|调用者：  <br/> |表单对象  <br/> |
|接口标识符:  <br/> |IID_IMAPIMessageSite  <br/> |
|指针类型:  <br/> |LPMAPIMESSAGESITE  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetSession](imapimessagesite-getsession.md) <br/> |返回在其中创建或打开当前邮件的 MAPI 会话。  <br/> |
|[GetStore](imapimessagesite-getstore.md) <br/> |如果存在这样的存储区, 则返回包含当前邮件的邮件存储区。  <br/> |
|[GetFolder](imapimessagesite-getfolder.md) <br/> |返回在其中创建或打开当前邮件的文件夹 (如果存在这样的文件夹)。  <br/> |
|[GetMessage](imapimessagesite-getmessage.md) <br/> |返回当前邮件。  <br/> |
|[GetFormManager](imapimessagesite-getformmanager.md) <br/> |返回一个表单管理器接口, 表单服务器可以使用该接口打开另一个表单服务器。  <br/> |
|[NewMessage](imapimessagesite-newmessage.md) <br/> |创建新邮件。  <br/> |
|[CopyMessage](imapimessagesite-copymessage.md) <br/> |将当前邮件复制到一个文件夹中。  <br/> |
|[MoveMessage](imapimessagesite-movemessage.md) <br/> |将当前邮件移动到文件夹中。  <br/> |
|[DeleteMessage](imapimessagesite-deletemessage.md) <br/> |删除当前邮件。  <br/> |
|[SaveMessage](imapimessagesite-savemessage.md) <br/> |请求保存当前邮件。  <br/> |
|[SubmitMessage](imapimessagesite-submitmessage.md) <br/> |请求将当前邮件排队等待传递。  <br/> |
|[GetSiteStatus](imapimessagesite-getsitestatus.md) <br/> |从邮件网站对象返回有关当前邮件的邮件网站功能的信息。  <br/> |
|[GetLastError](imapimessagesite-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关发生在邮件网站对象中的上一个错误的信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

