---
title: 启动表单服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a439e75a-92b3-4830-9dfc-e723d046be7b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: dec8706ba00356660ec82c25e0213ef3e638691d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270047"
---
# <a name="launching-a-form-server"></a><span data-ttu-id="9afd6-103">启动表单服务器</span><span class="sxs-lookup"><span data-stu-id="9afd6-103">Launching a Form Server</span></span>

  
  
<span data-ttu-id="9afd6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9afd6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9afd6-105">从持久性存储库加载表单时发生的一系列 (，即从表单库) 显示消息的交互如下所示：</span><span class="sxs-lookup"><span data-stu-id="9afd6-105">The series of interactions that occurs when a form is loaded from persistent storage (that is, from a form library) to display a message is as follows:</span></span>
  
1. <span data-ttu-id="9afd6-106">邮件客户端获取邮件的邮件类、邮件标志和邮件状态。</span><span class="sxs-lookup"><span data-stu-id="9afd6-106">The messaging client gets the message's message class, message flags, and message status.</span></span> <span data-ttu-id="9afd6-107">此步骤是可选的;如果步骤 2 中未提供这些部分数据，则表单管理器将检索它们。</span><span class="sxs-lookup"><span data-stu-id="9afd6-107">This step is optional; if these pieces of data are not provided in step 2, the form manager will retrieve them.</span></span>
    
2. <span data-ttu-id="9afd6-108">消息客户端使用目标消息[调用 IMAPIFormMgr：：LoadForm。](imapiformmgr-loadform.md)</span><span class="sxs-lookup"><span data-stu-id="9afd6-108">The messaging client calls [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) with the target message.</span></span> 
    
3. <span data-ttu-id="9afd6-109">表单管理器从相应的表单库加载表单服务器。</span><span class="sxs-lookup"><span data-stu-id="9afd6-109">The form manager loads the form server from the appropriate form library.</span></span> <span data-ttu-id="9afd6-110">如果未安装目标邮件的表单服务器，则表单管理器也安装表单的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="9afd6-110">If the form server for the target message is not installed, the form manager installs the form's executable files, as well.</span></span>
    
4. <span data-ttu-id="9afd6-111">表单管理器对表单对象调用 [IUnknown：：QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) 以获取表单对象的 [IMAPIForm ： IUnknown](imapiformiunknown.md) 和 [IPersistMessage ： IUnknown](ipersistmessageiunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="9afd6-111">The form manager calls [IUnknown::QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) on the form object to obtain the form object's [IMAPIForm : IUnknown](imapiformiunknown.md) and [IPersistMessage : IUnknown](ipersistmessageiunknown.md) interfaces.</span></span> 
    
5. <span data-ttu-id="9afd6-112">表单管理器使用查看器对象的消息网站和消息界面调用[IPersistMessage：：Load。](ipersistmessage-load.md)</span><span class="sxs-lookup"><span data-stu-id="9afd6-112">The form manager calls [IPersistMessage::Load](ipersistmessage-load.md) with the message site and message interfaces from the viewer object.</span></span> 
    
6. <span data-ttu-id="9afd6-113">表单对象将调用回消息客户端的 [IMAPIMessageSite：：GetSiteStatus](imapimessagesite-getsitestatus.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="9afd6-113">The form object calls back to the messaging client's [IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md) method.</span></span> 
    
7. <span data-ttu-id="9afd6-114">表单管理器使用消息客户端中的视图上下文接口调用表单对象的 [IMAPIForm：：SetViewContext](imapiform-setviewcontext.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="9afd6-114">The form manager calls the form object's [IMAPIForm::SetViewContext](imapiform-setviewcontext.md) method with the view context interface from the messaging client.</span></span> 
    
8. <span data-ttu-id="9afd6-115">表单对象将调用回消息客户端的 [IMAPIViewContext：：SetAdviseSink](imapiviewcontext-setadvisesink.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="9afd6-115">The form object calls back to the messaging client's [IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md) method.</span></span> 
    
9. <span data-ttu-id="9afd6-116">表单对象将调用回消息客户端的 [IMAPIViewContext：：GetViewStatus](imapiviewcontext-getviewstatus.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="9afd6-116">The form object calls back to the messaging client's [IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md) method.</span></span> 
    
10. <span data-ttu-id="9afd6-117">消息客户端使用查看器对象和消息网站对象的视图上下文接口调用表单对象的 [IMAPIForm：：Advise](imapiform-advise.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="9afd6-117">The messaging client calls the form object's [IMAPIForm::Advise](imapiform-advise.md) method with the view context interfaces from the viewer object and the message site object.</span></span> 
    
11. <span data-ttu-id="9afd6-118">消息客户端调用表单对象的 [IMAPIForm：:D oVerb](imapiform-doverb.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="9afd6-118">The messaging client calls the form object's [IMAPIForm::DoVerb](imapiform-doverb.md) method.</span></span> 
    
12. <span data-ttu-id="9afd6-119">窗体对象将创建其用户界面（如有必要）并与用户交互。</span><span class="sxs-lookup"><span data-stu-id="9afd6-119">The form object creates its user interface, if necessary, and interacts with the user.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9afd6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9afd6-120">See also</span></span>



[<span data-ttu-id="9afd6-121">表单服务器交互</span><span class="sxs-lookup"><span data-stu-id="9afd6-121">Form Server Interactions</span></span>](form-server-interactions.md)

