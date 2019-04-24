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
# <a name="launching-a-form-server"></a><span data-ttu-id="d9467-103">启动表单服务器</span><span class="sxs-lookup"><span data-stu-id="d9467-103">Launching a Form Server</span></span>

  
  
<span data-ttu-id="d9467-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9467-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9467-105">当从持久存储 (即表单库) 中加载表单以显示消息时发生的一系列交互, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="d9467-105">The series of interactions that occurs when a form is loaded from persistent storage (that is, from a form library) to display a message is as follows:</span></span>
  
1. <span data-ttu-id="d9467-106">邮件客户端获取邮件的邮件类、邮件标记和邮件状态。</span><span class="sxs-lookup"><span data-stu-id="d9467-106">The messaging client gets the message's message class, message flags, and message status.</span></span> <span data-ttu-id="d9467-107">此步骤是可选的;如果在步骤2中未提供这些数据片段, 则表单管理器将检索它们。</span><span class="sxs-lookup"><span data-stu-id="d9467-107">This step is optional; if these pieces of data are not provided in step 2, the form manager will retrieve them.</span></span>
    
2. <span data-ttu-id="d9467-108">邮件客户端使用目标邮件调用[IMAPIFormMgr:: LoadForm](imapiformmgr-loadform.md) 。</span><span class="sxs-lookup"><span data-stu-id="d9467-108">The messaging client calls [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) with the target message.</span></span> 
    
3. <span data-ttu-id="d9467-109">表单管理器从相应的表单库加载表单服务器。</span><span class="sxs-lookup"><span data-stu-id="d9467-109">The form manager loads the form server from the appropriate form library.</span></span> <span data-ttu-id="d9467-110">如果未安装目标邮件的表单服务器, 则表单管理器也会安装该表单的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="d9467-110">If the form server for the target message is not installed, the form manager installs the form's executable files, as well.</span></span>
    
4. <span data-ttu-id="d9467-111">表单管理器调用[IUnknown::](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)用于获取表单对象的[IMAPIForm: iunknown](imapiformiunknown.md)和[IPersistMessage: iunknown](ipersistmessageiunknown.md)接口的表单对象上的 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="d9467-111">The form manager calls [IUnknown::QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) on the form object to obtain the form object's [IMAPIForm : IUnknown](imapiformiunknown.md) and [IPersistMessage : IUnknown](ipersistmessageiunknown.md) interfaces.</span></span> 
    
5. <span data-ttu-id="d9467-112">表单管理器调用[IPersistMessage::](ipersistmessage-load.md)使用消息站点和查看器对象的邮件接口进行加载。</span><span class="sxs-lookup"><span data-stu-id="d9467-112">The form manager calls [IPersistMessage::Load](ipersistmessage-load.md) with the message site and message interfaces from the viewer object.</span></span> 
    
6. <span data-ttu-id="d9467-113">form 对象回调到邮件客户端的[IMAPIMessageSite:: GetSiteStatus](imapimessagesite-getsitestatus.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d9467-113">The form object calls back to the messaging client's [IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md) method.</span></span> 
    
7. <span data-ttu-id="d9467-114">表单管理器使用来自邮件客户端的视图上下文界面调用 form 对象的[IMAPIForm:: SetViewContext](imapiform-setviewcontext.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d9467-114">The form manager calls the form object's [IMAPIForm::SetViewContext](imapiform-setviewcontext.md) method with the view context interface from the messaging client.</span></span> 
    
8. <span data-ttu-id="d9467-115">form 对象回调到邮件客户端的[IMAPIViewContext:: SetAdviseSink](imapiviewcontext-setadvisesink.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d9467-115">The form object calls back to the messaging client's [IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md) method.</span></span> 
    
9. <span data-ttu-id="d9467-116">form 对象回调到邮件客户端的[IMAPIViewContext:: GetViewStatus](imapiviewcontext-getviewstatus.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d9467-116">The form object calls back to the messaging client's [IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md) method.</span></span> 
    
10. <span data-ttu-id="d9467-117">邮件客户端通过查看器对象和邮件网站对象的视图上下文界面调用 form 对象的[IMAPIForm:: Advise](imapiform-advise.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d9467-117">The messaging client calls the form object's [IMAPIForm::Advise](imapiform-advise.md) method with the view context interfaces from the viewer object and the message site object.</span></span> 
    
11. <span data-ttu-id="d9467-118">邮件客户端调用 form 对象的[IMAPIForm::D overb](imapiform-doverb.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d9467-118">The messaging client calls the form object's [IMAPIForm::DoVerb](imapiform-doverb.md) method.</span></span> 
    
12. <span data-ttu-id="d9467-119">form 对象创建其用户界面 (如有必要), 并与用户进行交互。</span><span class="sxs-lookup"><span data-stu-id="d9467-119">The form object creates its user interface, if necessary, and interacts with the user.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d9467-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9467-120">See also</span></span>



[<span data-ttu-id="d9467-121">表单服务器交互</span><span class="sxs-lookup"><span data-stu-id="d9467-121">Form Server Interactions</span></span>](form-server-interactions.md)

