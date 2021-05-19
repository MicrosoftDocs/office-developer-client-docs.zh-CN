---
title: 接收文件夹表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5ff1a5e3-5b96-4f08-9b9b-aeb14304b23b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b291167a0457eaaf4f3bcb48ab36d6c6e6512fcc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417348"
---
# <a name="receive-folder-tables"></a>接收文件夹表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
接收文件夹表包含指定为邮件存储的接收文件夹的所有文件夹的信息。 接收文件夹是放置特定邮件类的传入邮件的文件夹。 邮件存储提供程序实现接收文件夹表，客户端应用程序通过调用 [IMsgStore：：GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) 方法来使用它们。 
  
下列属性在接收文件夹表中设置了所需的列：
  
 **PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))  
  
 **PR_MESSAGE_CLASS (** [PidTagMessageClass](pidtagmessageclass-canonical-property.md))  
  
 **PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md) 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

