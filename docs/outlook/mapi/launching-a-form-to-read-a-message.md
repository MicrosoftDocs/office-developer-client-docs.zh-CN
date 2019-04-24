---
title: 启动要读取邮件的表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 54a4b805-2ab7-4fb7-b0ea-4a33ead27451
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 439927dc78941f086c025d77c76236497d3f4a15
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307810"
---
# <a name="launching-a-form-to-read-a-message"></a><span data-ttu-id="f72e3-103">启动要读取邮件的表单</span><span class="sxs-lookup"><span data-stu-id="f72e3-103">Launching a Form to Read a Message</span></span>

  
  
<span data-ttu-id="f72e3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f72e3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f72e3-105">表单服务器实施者在客户端应用程序加载消息时, 应预计对其表单服务器和表单对象使用以下一系列方法调用:</span><span class="sxs-lookup"><span data-stu-id="f72e3-105">Form server implementers should expect the following sequence of method calls to their form server and form objects when a client application loads a message:</span></span>
  
1. <span data-ttu-id="f72e3-106">客户端应用程序使用调用[MAPIOpenFormMgr](mapiopenformmgr.md)函数打开表单管理器。</span><span class="sxs-lookup"><span data-stu-id="f72e3-106">The client application opens the form manager with a call to the [MAPIOpenFormMgr](mapiopenformmgr.md) function.</span></span> 
    
2. <span data-ttu-id="f72e3-107">客户端应用程序调用[IMAPIFormMgr:: LoadForm](imapiformmgr-loadform.md)方法, 该方法返回具有[IMAPIForm](imapiformiunknown.md)的对象。</span><span class="sxs-lookup"><span data-stu-id="f72e3-107">The client application calls the [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) method, which returns an object with [IMAPIForm](imapiformiunknown.md).</span></span> <span data-ttu-id="f72e3-108">如果窗体管理器将不用于进一步的窗体激活, 现在就可以发布它。</span><span class="sxs-lookup"><span data-stu-id="f72e3-108">The form manager may be released now if it will not be used for further form activations.</span></span> <span data-ttu-id="f72e3-109">请注意, 对**LoadForm**的调用可能需要一段时间, 因为在继续之前, 表单管理器可能必须安装表单服务器的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="f72e3-109">Note that a call to **LoadForm** may take some time because the form manager may have to install the form server's executable files before proceeding.</span></span> 
    
3. <span data-ttu-id="f72e3-110">(可选) 客户端应用程序可以准备[IMAPIViewContext](imapiviewcontextiunknown.md) , 以控制可能导致 form 对象加载该文件夹中的上一个或下一个邮件的操作。</span><span class="sxs-lookup"><span data-stu-id="f72e3-110">Optionally, the client application can prepare [IMAPIViewContext](imapiviewcontextiunknown.md) to control operations that may cause the form object to load the previous or next message in the folder.</span></span> <span data-ttu-id="f72e3-111">客户端应用程序可以使用[IMAPIForm:: SetViewContext](imapiform-setviewcontext.md)方法更改在**LoadForm**调用中设置的默认视图上下文。</span><span class="sxs-lookup"><span data-stu-id="f72e3-111">The client application can use the [IMAPIForm::SetViewContext](imapiform-setviewcontext.md) method to change the default view context that was set in the **LoadForm** call.</span></span> 
    
4. <span data-ttu-id="f72e3-112">客户端应用程序调用[IPersistMessage:: load](ipersistmessage-load.md)方法将邮件数据加载到 form 对象中。</span><span class="sxs-lookup"><span data-stu-id="f72e3-112">The client application calls the [IPersistMessage::Load](ipersistmessage-load.md) method to load message data into the form object.</span></span> 
    
5. <span data-ttu-id="f72e3-113">客户端应用程序调用[IMAPIForm::D overb](imapiform-doverb.md)调用 open 谓词, 以传递可选的[IMAPIViewContext](imapiviewcontextiunknown.md)接口指针。</span><span class="sxs-lookup"><span data-stu-id="f72e3-113">The client application calls [IMAPIForm::DoVerb](imapiform-doverb.md) to invoke the open verb, passing the optional [IMAPIViewContext](imapiviewcontextiunknown.md) interface pointer.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="f72e3-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f72e3-114">See also</span></span>



[<span data-ttu-id="f72e3-115">表单服务器交互</span><span class="sxs-lookup"><span data-stu-id="f72e3-115">Form Server Interactions</span></span>](form-server-interactions.md)

