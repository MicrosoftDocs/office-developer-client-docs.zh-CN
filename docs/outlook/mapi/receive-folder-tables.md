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
# <a name="receive-folder-tables"></a><span data-ttu-id="92a57-103">接收文件夹表</span><span class="sxs-lookup"><span data-stu-id="92a57-103">Receive Folder Tables</span></span>

  
  
<span data-ttu-id="92a57-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="92a57-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="92a57-105">接收文件夹表包含指定为邮件存储区的接收文件夹的所有文件夹的信息。</span><span class="sxs-lookup"><span data-stu-id="92a57-105">A receive folder table contains information for all the folders designated as receive folders for a message store.</span></span> <span data-ttu-id="92a57-106">接收文件夹是一个文件夹, 其中放置了特定邮件类别的传入邮件。</span><span class="sxs-lookup"><span data-stu-id="92a57-106">A receive folder is a folder where incoming messages of a particular message class are placed.</span></span> <span data-ttu-id="92a57-107">邮件存储提供程序实现接收文件夹表和客户端应用程序通过调用[IMsgStore:: GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)方法来使用它们。</span><span class="sxs-lookup"><span data-stu-id="92a57-107">Message store providers implement receive folder tables and client applications use them by making a call to the [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) method.</span></span> 
  
<span data-ttu-id="92a57-108">以下属性组成了在接收文件夹表中设置的必需列:</span><span class="sxs-lookup"><span data-stu-id="92a57-108">The following properties make up the required column set in receive folder tables:</span></span>
  
 <span data-ttu-id="92a57-109">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="92a57-109">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span> 
  
 <span data-ttu-id="92a57-110">**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="92a57-110">**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md))</span></span> 
  
 <span data-ttu-id="92a57-111">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="92a57-111">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="92a57-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92a57-112">See also</span></span>



[<span data-ttu-id="92a57-113">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="92a57-113">MAPI Tables</span></span>](mapi-tables.md)

