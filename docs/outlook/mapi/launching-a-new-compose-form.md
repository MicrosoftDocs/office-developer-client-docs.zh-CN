---
title: 启动新的撰写窗体
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ffceaa03-76f2-42e0-b28d-226f1f9cc889
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 29d53ba1242014a501a01d161c19dade164f393a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270054"
---
# <a name="launching-a-new-compose-form"></a><span data-ttu-id="67ea4-103">启动新的撰写窗体</span><span class="sxs-lookup"><span data-stu-id="67ea4-103">Launching a New Compose Form</span></span>

  
  
<span data-ttu-id="67ea4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="67ea4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="67ea4-105">当客户端应用程序打开一条用于撰写的新消息时，表单服务器实施者应希望其表单服务器和表单对象的方法调用顺序如下：</span><span class="sxs-lookup"><span data-stu-id="67ea4-105">Form server implementers should expect the following sequence of method calls to their form server and form objects when a client application opens a new message for composing:</span></span>
  
1. <span data-ttu-id="67ea4-106">客户端应用程序调用 [IMAPIFormMgr：：ResolveMessageClass](imapiformmgr-resolvemessageclass.md) 方法来获取有关表单服务器的邮件类的类信息。</span><span class="sxs-lookup"><span data-stu-id="67ea4-106">The client application calls the [IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md) method to get class information about the form server's message class.</span></span> 
    
2. <span data-ttu-id="67ea4-107">客户端应用程序调用 [IMAPIFormMgr：：CreateForm](imapiformmgr-createform.md) 获取新的表单对象。</span><span class="sxs-lookup"><span data-stu-id="67ea4-107">The client application calls [IMAPIFormMgr::CreateForm](imapiformmgr-createform.md) to get a new form object.</span></span> 
    
3. <span data-ttu-id="67ea4-108">MAPI 表单管理器加载表单服务器（如果它尚未在内存中）并且从表单服务器获取 [IMAPIForm](imapiformiunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="67ea4-108">The MAPI form manager loads the form server, if it is not already in memory, and gets an [IMAPIForm](imapiformiunknown.md) interface from the form server.</span></span> 
    
4. <span data-ttu-id="67ea4-109">客户端应用程序获取生成的 **IMAPIForm** 接口并调用 [IUnknown：：QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) 方法来获取对象的 [IPersistMessage](ipersistmessageiunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="67ea4-109">The client application takes the resulting **IMAPIForm** interface and calls the [IUnknown::QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) method to get the object's [IPersistMessage](ipersistmessageiunknown.md) interface.</span></span> 
    
5. <span data-ttu-id="67ea4-110">客户端应用程序调用 [IPersistMessage：：InitNew](ipersistmessage-initnew.md) 方法将表单对象与 [IMessage、](imessageimapiprop.md)视图上下文以及建议接收对象关联。</span><span class="sxs-lookup"><span data-stu-id="67ea4-110">The client application calls the [IPersistMessage::InitNew](ipersistmessage-initnew.md) method to associate the form object with [IMessage](imessageimapiprop.md), view context, and advise sink objects.</span></span>
    
6. <span data-ttu-id="67ea4-111">客户端应用程序调用 [IMAPIForm：:D oVerb](imapiform-doverb.md) 方法来调用打开动词。</span><span class="sxs-lookup"><span data-stu-id="67ea4-111">The client application calls the [IMAPIForm::DoVerb](imapiform-doverb.md) method to invoke the open verb.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="67ea4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67ea4-112">See also</span></span>



[<span data-ttu-id="67ea4-113">表单服务器交互</span><span class="sxs-lookup"><span data-stu-id="67ea4-113">Form Server Interactions</span></span>](form-server-interactions.md)

