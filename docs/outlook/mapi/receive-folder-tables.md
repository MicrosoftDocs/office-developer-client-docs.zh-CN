---
title: 接收文件夹表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5ff1a5e3-5b96-4f08-9b9b-aeb14304b23b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b88545ede6275bd834fad5869d972e2860a6c77e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573178"
---
# <a name="receive-folder-tables"></a>接收文件夹表

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
接收文件夹表包含指定为邮件存储区的接收文件夹的所有文件夹的信息。 接收文件夹是特定邮件类别的传入消息的放置位置的文件夹。 消息存储提供程序实现接收文件夹表和通过[IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)方法调用的客户端应用程序使用它们。 
  
以下属性构成所需的列中设置收到文件夹表：
  
 **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md)) 
  
 **PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 
  
 **PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

