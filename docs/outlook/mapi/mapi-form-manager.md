---
title: MAPI 表单管理器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0bbbd06-d47d-45ad-8179-2372d1d023d0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3059183103ca2552505486b5ec54366729ae4ec3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430194"
---
# <a name="mapi-form-manager"></a><span data-ttu-id="6f7f8-103">MAPI 表单管理器</span><span class="sxs-lookup"><span data-stu-id="6f7f8-103">MAPI Form Manager</span></span>

  
  
<span data-ttu-id="6f7f8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f7f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6f7f8-105">表单管理器是一个实现[IMAPIFormMgr](imapiformmgriunknown.md)接口的对象。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-105">A form manager is an object that implements the [IMAPIFormMgr](imapiformmgriunknown.md) interface.</span></span> <span data-ttu-id="6f7f8-106">大多数组织将使用 MAPI 提供的窗体管理器, 称为 "默认表单管理器"。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-106">Most organizations will use the form manager supplied with MAPI, referred to as the default form manager.</span></span> <span data-ttu-id="6f7f8-107">但是, 如果需要, 组织可以将默认表单管理器替换为自定义表单管理器。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-107">However, an organization can replace the default form manager with a custom form manager if desired.</span></span> <span data-ttu-id="6f7f8-108">表单管理器负责查找表单库中的表单、加载表单以响应用户请求, 以及将表单安装到用户的本地表单库、文件夹表单库或个人表单库中。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-108">The form manager takes care of locating forms within form libraries, loading forms in response to user requests, and installing forms into a user's local form library, folder form library, or personal form library.</span></span> 
  
<span data-ttu-id="6f7f8-109">若要使用户与邮件进行交互, 必须创建并激活邮件邮件类的窗体服务器实例以显示该邮件, 并对邮件执行请求的操作。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-109">For a user to interact with a message, an instance of the form server for the message's message class must be created and activated to display the message and carry out the requested operation on the message.</span></span> <span data-ttu-id="6f7f8-110">如[MAPI 表单库](mapi-form-libraries.md)主题中所述, 表单的实现可以存在于多个不同的位置 (表单库) 中, 并且不能保证当用户要进行交互时, 窗体或其服务器将在本地可用或处于运行状态。使用它。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-110">As described in the topic [MAPI Form Libraries](mapi-form-libraries.md), a form's implementation can exist in several different locations (form libraries) and there is no guarantee that a form or its server will be locally available or in a running state when a user wants to interact with it.</span></span> <span data-ttu-id="6f7f8-111">表单管理器负责查找和激活表单的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-111">The form manager takes care of the details of locating and activating the form.</span></span>
  
<span data-ttu-id="6f7f8-112">客户端使用由表单管理器提供的服务来查找和激活表单。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-112">Clients use services provided by the form manager to find and activate forms.</span></span> <span data-ttu-id="6f7f8-113">**IMAPIFormMgr**接口由表单管理器实现, 并由客户端调用以访问其服务。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-113">The **IMAPIFormMgr** interface is implemented by the form manager and is called by clients to access its services.</span></span> <span data-ttu-id="6f7f8-114">表单管理器是一个重要的组件, 因为它隐藏了从邮件客户端查找和激活表单的几乎所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-114">The form manager is an essential component because it hides almost all the details of finding and activating forms from messaging clients.</span></span> 
  
<span data-ttu-id="6f7f8-115">加载表单服务器时, 默认表单管理器会从第一个表单库加载表单, 在该表单库中找到表单的邮件类的实现。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-115">When loading form servers, the default form manager loads the form from the first form library in which an implementation for the form's message class is found.</span></span> <span data-ttu-id="6f7f8-116">默认表单管理器将按以下顺序搜索表单库:</span><span class="sxs-lookup"><span data-stu-id="6f7f8-116">The default form manager searches the form libraries in the following order:</span></span>
  
1. <span data-ttu-id="6f7f8-117">用户的本地表单库。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-117">The user's local form library.</span></span> <span data-ttu-id="6f7f8-118">将首先搜索此表单库, 因为如果在本地表单库中安装了该实现, 则它可以最快地访问表单实现。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-118">This form library is searched first because it provides the fastest access to a form's implementation if the implementation is installed in the local form library.</span></span>
    
2. <span data-ttu-id="6f7f8-119">邮件容器的文件夹表单库—存储正在加载的邮件所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-119">The folder form library of the message's container — the folder in which the message being loaded is stored.</span></span>
    
3. <span data-ttu-id="6f7f8-120">用户的个人表单库。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-120">The user's personal form library.</span></span>
    
<span data-ttu-id="6f7f8-121">自定义表单管理器可以按任何顺序搜索可用的表单库, 也可以实现其他表单库, 如组织范围的表单库。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-121">A custom form manager can search the available form libraries in any order, or can implement other form libraries such as an organization-wide form library.</span></span> <span data-ttu-id="6f7f8-122">有关表单库的更多详细信息, 请参阅[MAPI 表单库](mapi-form-libraries.md)。</span><span class="sxs-lookup"><span data-stu-id="6f7f8-122">For more details on form libraries, see [MAPI Form Libraries](mapi-form-libraries.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6f7f8-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f7f8-123">See also</span></span>



[<span data-ttu-id="6f7f8-124">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="6f7f8-124">MAPI Forms</span></span>](mapi-forms.md)

