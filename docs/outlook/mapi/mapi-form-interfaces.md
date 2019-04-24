---
title: MAPI 表单接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 611213c9-e758-4366-b193-fc62181d3d1f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f207f9550c61ad69fd1fc560cdb2084b7bb56c6f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351539"
---
# <a name="mapi-form-interfaces"></a><span data-ttu-id="a3ef3-103">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="a3ef3-103">MAPI Form Interfaces</span></span>

  
  
<span data-ttu-id="a3ef3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a3ef3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a3ef3-105">MAPI 定义了与表单相关的下列接口。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-105">MAPI defines the following interfaces relating to forms.</span></span>
  
|<span data-ttu-id="a3ef3-106">**接口名称**</span><span class="sxs-lookup"><span data-stu-id="a3ef3-106">**Interface name**</span></span>|<span data-ttu-id="a3ef3-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="a3ef3-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a3ef3-108">IMAPIForm</span><span class="sxs-lookup"><span data-stu-id="a3ef3-108">IMAPIForm</span></span>](imapiformiunknown.md) <br/> |<span data-ttu-id="a3ef3-109">操纵窗体对象并处理窗体对象命令。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-109">Manipulates form objects and handles form object commands.</span></span>  <br/> |
|[<span data-ttu-id="a3ef3-110">IMAPIFormAdviseSink</span><span class="sxs-lookup"><span data-stu-id="a3ef3-110">IMAPIFormAdviseSink</span></span>](imapiformadvisesinkiunknown.md) <br/> |<span data-ttu-id="a3ef3-111">确定窗体对象是否可以处理下一封邮件, 并更改该窗体对象的下一个或上一个状态。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-111">Determines if the form object can handle the next message and changes the next or previous state of the form object.</span></span>  <br/> |
|[<span data-ttu-id="a3ef3-112">IMAPIFormContainer</span><span class="sxs-lookup"><span data-stu-id="a3ef3-112">IMAPIFormContainer</span></span>](imapiformcontaineriunknown.md) <br/> |<span data-ttu-id="a3ef3-113">支持针对特定表单容器安装、卸载和解析表单服务器。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-113">Supports installation, deinstallation, and resolution of form servers against a specific form container.</span></span>  <br/> |
|[<span data-ttu-id="a3ef3-114">IMAPIFormFactory</span><span class="sxs-lookup"><span data-stu-id="a3ef3-114">IMAPIFormFactory</span></span>](imapiformfactoryiunknown.md) <br/> |<span data-ttu-id="a3ef3-115">支持使用可配置的运行时窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-115">Supports the use of configurable run-time form servers.</span></span>  <br/> |
|[<span data-ttu-id="a3ef3-116">IMAPIFormInfo</span><span class="sxs-lookup"><span data-stu-id="a3ef3-116">IMAPIFormInfo</span></span>](imapiforminfoimapiprop.md) <br/> |<span data-ttu-id="a3ef3-117">使客户端应用程序能够使用特定于邮件类的属性。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-117">Enables client applications to work with properties that are specific to a message class.</span></span>  <br/> |
|[<span data-ttu-id="a3ef3-118">IMAPIFormMgr</span><span class="sxs-lookup"><span data-stu-id="a3ef3-118">IMAPIFormMgr</span></span>](imapiformmgriunknown.md) <br/> |<span data-ttu-id="a3ef3-119">使客户端应用程序能够获取有关表单服务器、激活表单服务器和在邮件系统中安装表单服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-119">Enables client applications to get information about form servers, activates form servers, and installs form servers in the messaging system.</span></span>  <br/> |
|[<span data-ttu-id="a3ef3-120">IMAPIMessageSite</span><span class="sxs-lookup"><span data-stu-id="a3ef3-120">IMAPIMessageSite</span></span>](imapimessagesiteiunknown.md) <br/> |<span data-ttu-id="a3ef3-121">用于操作与表单对象相关联的邮件。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-121">Used to manipulate messages associated with form objects.</span></span>  <br/> |
|[<span data-ttu-id="a3ef3-122">IMAPIViewAdviseSink</span><span class="sxs-lookup"><span data-stu-id="a3ef3-122">IMAPIViewAdviseSink</span></span>](imapiviewadvisesinkiunknown.md) <br/> |<span data-ttu-id="a3ef3-123">通知客户端应用程序表单对象中发生了事件。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-123">Notifies client applications that an event has occurred in the form object.</span></span>  <br/> |
|[<span data-ttu-id="a3ef3-124">IMAPIViewContext</span><span class="sxs-lookup"><span data-stu-id="a3ef3-124">IMAPIViewContext</span></span>](imapiviewcontextiunknown.md) <br/> |<span data-ttu-id="a3ef3-125">用于响应 form 对象中的下一个、上一个和删除命令。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-125">Used to respond to Next, Previous, and Delete commands in the form object.</span></span>  <br/> |
|[<span data-ttu-id="a3ef3-126">IPersistMessage</span><span class="sxs-lookup"><span data-stu-id="a3ef3-126">IPersistMessage</span></span>](ipersistmessageiunknown.md) <br/> |<span data-ttu-id="a3ef3-127">用于在邮件存储中保存、初始化和加载 form 对象。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-127">Used to save, initialize, and load form objects to and from message storage.</span></span>  <br/> |
   
<span data-ttu-id="a3ef3-128">有关 MAPI 表单接口的方法的详细信息, 请参阅这些接口的文档。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-128">For more information about the methods of the MAPI form interfaces, see the documentation for these interfaces.</span></span> <span data-ttu-id="a3ef3-129">您无需实现所有 MAPI 表单接口即可创建自定义窗体。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-129">You do not have to implement all of the MAPI form interfaces in order to create a custom form.</span></span> <span data-ttu-id="a3ef3-130">窗体本身只需要实现**IPersistMessage**、 **IMAPIForm**和**IMAPIFormAdviseSink**接口。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-130">A form itself requires only that you implement the **IPersistMessage**, **IMAPIForm**, and **IMAPIFormAdviseSink** interfaces.</span></span> <span data-ttu-id="a3ef3-131">此外, 还最好实现**IMAPIFormFactory**和**IMAPIFormInfo**。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-131">Additionally, it is also a good idea to implement **IMAPIFormFactory** and **IMAPIFormInfo**.</span></span> <span data-ttu-id="a3ef3-132">**IMAPIFormFactory**对于 OLE 合规性非常有用, **IMAPIFormInfo**支持编写完善的客户端应用程序, 以便更好地使用表单。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-132">**IMAPIFormFactory** is useful for OLE compliance, and **IMAPIFormInfo** enables well-written client applications to make better use of your forms.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a3ef3-133">严格来说, **IMAPIFormAdviseSink**是一个可选接口。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-133">Strictly speaking, **IMAPIFormAdviseSink** is an optional interface.</span></span> <span data-ttu-id="a3ef3-134">但是, 强烈建议您在表单服务器中实现它。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-134">However, it is strongly recommended that you implement it in your form servers.</span></span> <span data-ttu-id="a3ef3-135">此接口对于在邮件客户端和窗体服务器之间进行有效交互非常关键, 尤其是当处理多个窗体服务器的邮件类的邮件时。</span><span class="sxs-lookup"><span data-stu-id="a3ef3-135">This interface is critical to efficient interaction between messaging clients and form servers, especially when several messages of your form server's message class are being dealt with.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a3ef3-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3ef3-136">See also</span></span>



[<span data-ttu-id="a3ef3-137">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="a3ef3-137">MAPI Forms</span></span>](mapi-forms.md)

