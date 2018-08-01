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
ms.openlocfilehash: 5f3bcda3beb29fa91629ea1639522ef24dc6eb32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778593"
---
# <a name="receive-folder-tables"></a><span data-ttu-id="9aa01-103">接收文件夹表</span><span class="sxs-lookup"><span data-stu-id="9aa01-103">Receive Folder Tables</span></span>

  
  
<span data-ttu-id="9aa01-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9aa01-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9aa01-105">接收文件夹表包含指定为邮件存储区的接收文件夹的所有文件夹的信息。</span><span class="sxs-lookup"><span data-stu-id="9aa01-105">A receive folder table contains information for all the folders designated as receive folders for a message store.</span></span> <span data-ttu-id="9aa01-106">接收文件夹是特定邮件类别的传入消息的放置位置的文件夹。</span><span class="sxs-lookup"><span data-stu-id="9aa01-106">A receive folder is a folder where incoming messages of a particular message class are placed.</span></span> <span data-ttu-id="9aa01-107">消息存储提供程序实现接收文件夹表和通过[IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)方法调用的客户端应用程序使用它们。</span><span class="sxs-lookup"><span data-stu-id="9aa01-107">Message store providers implement receive folder tables and client applications use them by making a call to the [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) method.</span></span> 
  
<span data-ttu-id="9aa01-108">以下属性构成所需的列中设置收到文件夹表：</span><span class="sxs-lookup"><span data-stu-id="9aa01-108">The following properties make up the required column set in receive folder tables:</span></span>
  
 <span data-ttu-id="9aa01-109">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9aa01-109">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span> 
  
 <span data-ttu-id="9aa01-110">**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9aa01-110">**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md))</span></span> 
  
 <span data-ttu-id="9aa01-111">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9aa01-111">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9aa01-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9aa01-112">See also</span></span>



[<span data-ttu-id="9aa01-113">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="9aa01-113">MAPI Tables</span></span>](mapi-tables.md)

