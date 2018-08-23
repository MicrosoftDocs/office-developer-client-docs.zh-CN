---
title: 启动新的撰写表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ffceaa03-76f2-42e0-b28d-226f1f9cc889
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 66aa5fe08b1c0be3906fa9a0483bbdec37c095c5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564498"
---
# <a name="launching-a-new-compose-form"></a><span data-ttu-id="b101c-103">启动新的撰写表单</span><span class="sxs-lookup"><span data-stu-id="b101c-103">Launching a New Compose Form</span></span>

  
  
<span data-ttu-id="b101c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b101c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b101c-105">窗体服务器实施应产生预期方法调用与其窗体服务器的以下序列和表单对象时客户端应用程序打开一个新邮件以撰写：</span><span class="sxs-lookup"><span data-stu-id="b101c-105">Form server implementers should expect the following sequence of method calls to their form server and form objects when a client application opens a new message for composing:</span></span>
  
1. <span data-ttu-id="b101c-106">客户端应用程序调用[IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md)方法来获取有关窗体服务器的邮件类的类信息。</span><span class="sxs-lookup"><span data-stu-id="b101c-106">The client application calls the [IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md) method to get class information about the form server's message class.</span></span> 
    
2. <span data-ttu-id="b101c-107">客户端应用程序调用[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)以获取新的窗体对象。</span><span class="sxs-lookup"><span data-stu-id="b101c-107">The client application calls [IMAPIFormMgr::CreateForm](imapiformmgr-createform.md) to get a new form object.</span></span> 
    
3. <span data-ttu-id="b101c-108">MAPI 窗体管理器加载窗体服务器中，如果它不是内存，并从窗体服务器获取[IMAPIForm](imapiformiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b101c-108">The MAPI form manager loads the form server, if it is not already in memory, and gets an [IMAPIForm](imapiformiunknown.md) interface from the form server.</span></span> 
    
4. <span data-ttu-id="b101c-109">客户端应用程序所需的结果**IMAPIForm**接口，并调用[IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)方法获取对象的[IPersistMessage](ipersistmessageiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b101c-109">The client application takes the resulting **IMAPIForm** interface and calls the [IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) method to get the object's [IPersistMessage](ipersistmessageiunknown.md) interface.</span></span> 
    
5. <span data-ttu-id="b101c-110">客户端应用程序调用[IPersistMessage::InitNew](ipersistmessage-initnew.md)方法[IMessage](imessageimapiprop.md)，视图上下文相关联的 form 对象并告知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="b101c-110">The client application calls the [IPersistMessage::InitNew](ipersistmessage-initnew.md) method to associate the form object with [IMessage](imessageimapiprop.md), view context, and advise sink objects.</span></span>
    
6. <span data-ttu-id="b101c-111">客户端应用程序调用[IMAPIForm::DoVerb](imapiform-doverb.md)方法来调用打开谓词。</span><span class="sxs-lookup"><span data-stu-id="b101c-111">The client application calls the [IMAPIForm::DoVerb](imapiform-doverb.md) method to invoke the open verb.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="b101c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b101c-112">See also</span></span>



[<span data-ttu-id="b101c-113">表单服务器交互</span><span class="sxs-lookup"><span data-stu-id="b101c-113">Form Server Interactions</span></span>](form-server-interactions.md)

