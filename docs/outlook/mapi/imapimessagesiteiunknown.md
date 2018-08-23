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
ms.openlocfilehash: cffa3024b8533f07f8f76fa5bbac219e23d61bdb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589502"
---
# <a name="imapimessagesite--iunknown"></a>IMAPIMessageSite : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
处理邮件，并通过这种操作响应表单查看器代码 （通常客户端应用程序） 实现。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|由公开：  <br/> |消息网站对象  <br/> |
|通过实现：  <br/> |表单查看器  <br/> |
|调用：  <br/> |窗体对象  <br/> |
|接口标识符：  <br/> |IID_IMAPIMessageSite  <br/> |
|指针类型：  <br/> |LPMAPIMESSAGESITE  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[GetSession](imapimessagesite-getsession.md) <br/> |返回当前消息是创建或打开的 MAPI 会话。  <br/> |
|[GetStore](imapimessagesite-getstore.md) <br/> |如果存在此类存储，返回包含当前邮件的邮件存储区。  <br/> |
|[GetFolder](imapimessagesite-getfolder.md) <br/> |如果存在此类的文件夹，则返回已创建或打开，当前邮件文件夹。  <br/> |
|[GetMessage](imapimessagesite-getmessage.md) <br/> |返回当前邮件。  <br/> |
|[GetFormManager](imapimessagesite-getformmanager.md) <br/> |返回一个窗体管理器接口，窗体服务器可用于打开窗体的另一台服务器。  <br/> |
|[NewMessage](imapimessagesite-newmessage.md) <br/> |创建新邮件。  <br/> |
|[CopyMessage](imapimessagesite-copymessage.md) <br/> |将当前的邮件复制到一个文件夹。  <br/> |
|[MoveMessage](imapimessagesite-movemessage.md) <br/> |将当前邮件移动到文件夹中。  <br/> |
|[DeleteMessage](imapimessagesite-deletemessage.md) <br/> |删除当前邮件。  <br/> |
|[SaveMessage](imapimessagesite-savemessage.md) <br/> |保存当前消息的请求。  <br/> |
|[SubmitMessage](imapimessagesite-submitmessage.md) <br/> |当前邮件在排队等待传送的请求。  <br/> |
|[GetSiteStatus](imapimessagesite-getsitestatus.md) <br/> |返回信息有关邮件消息网站对象中为当前消息的网站的功能。  <br/> |
|[时出错](imapimessagesite-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的错误消息网站对象发生的信息。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

